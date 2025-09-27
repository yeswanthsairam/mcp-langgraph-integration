# 🤖 Multi-Agent AI System with MCP Framework

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![LangChain](https://img.shields.io/badge/LangChain-Latest-green.svg)](https://langchain.com)
[![Google Gemini](https://img.shields.io/badge/Gemini-2.0--flash-orange.svg)](https://ai.google.dev)
[![MCP](https://img.shields.io/badge/MCP-Protocol-purple.svg)](https://modelcontextprotocol.org)

An intelligent agent system that integrates Google Gemini AI with external tools through the Model Context Protocol (MCP), enabling real-time weather queries and mathematical calculations through natural language interaction.

## ✨ Features

- **🧠 Google Gemini Integration**: Powered by Gemini 2.0 Flash for intelligent responses
- **🌤️ Real-time Weather Data**: Live weather updates via OpenWeatherMap API  
- **🔢 Mathematical Calculations**: Built-in calculator server for complex computations
- **⚡ Async Architecture**: High-performance concurrent processing using asyncio
- **🔧 MCP Protocol**: Seamless tool integration and server management
- **🖥️ Cross-platform**: Works on macOS, Windows, and Linux

## 🏗️ Architecture

```
┌─────────────────┐    ┌──────────────────┐    ┌────────────────┐
│   Google Gemini │◄──►│   LangGraph      │◄──►│  MCP Client    │
│   (AI Engine)   │    │   (Workflow)     │    │ (MultiServer)  │
└─────────────────┘    └──────────────────┘    └───────┬────────┘
                                                        │
                            ┌───────────────────────────┼───────────────────────┐
                            ▼                           ▼                       ▼
                   ┌─────────────────┐         ┌─────────────────┐    ┌─────────────────┐
                   │ Weather Server  │         │Calculator Server│    │   Extensible    │
                   │ (Go + OpenWM)   │         │   (Python)      │    │  MCP Servers    │
                   └─────────────────┘         └─────────────────┘    └─────────────────┘
```

## 🚀 Quick Start

### Prerequisites
- Python 3.8+ 
- Go 1.19+ (for weather server)
- Google Gemini API Key
- OpenWeatherMap API Key

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yeswanthsairam/mcp-langgraph-integration.git
   cd mcp-langgraph-integration
   ```

2. **Create virtual environment**:
   ```bash
   python3 -m venv myenv
   source myenv/bin/activate  # On Windows: myenv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r mcp-openweather/requirements.txt
   pip install mcp-server-calculator
   ```

4. **Build weather server** (if needed):
   ```bash
   cd mcp-openweather
   go build -o mcp-weather.exe main.go
   cd ..
   ```

5. **Configure environment variables**:
   ```bash
   # Create .env file in project root
   echo "GOOGLE_API_KEY=your_google_api_key_here" > .env
   echo "OWM_API_KEY=your_openweathermap_key_here" >> .env
   ```

6. **Run the application**:
   ```bash
   python 1.py
   ```

## 💻 Usage Examples

The system responds to natural language queries:

### Weather Queries
```
→ What's the weather in Tokyo?
→ Show me London's current temperature
→ Is it raining in New York?
```

### Mathematical Operations  
```
→ Calculate 25 * 4 + 10
→ What's the square root of 144?
→ Solve 2^8
```

### Combined Queries
```
→ What's the temperature in Paris and multiply it by 2?
→ Get Delhi weather and calculate temperature in Fahrenheit
```

## 📁 Project Structure

```
mcp-langgraph-integration/
├── 1.py                          # Main application
├── .env                          # Environment variables (not in repo)
├── .gitignore                    # Git ignore file
└── mcp-openweather/              # Weather server
    ├── main.go                   # Go weather service
    ├── go.mod                    # Go dependencies
    ├── requirements.txt          # Python dependencies
    ├── Dockerfile               # Container configuration
    └── LICENSE                  # License file
```

## 🛠️ Technologies Used

| Component | Technology | Purpose |
|-----------|------------|---------|
| **AI Engine** | Google Gemini 2.0 Flash | Natural language processing |
| **Workflow** | LangGraph | Agent orchestration |
| **Protocol** | MCP (Model Context Protocol) | Tool integration |
| **Weather API** | OpenWeatherMap | Real-time weather data |
| **Weather Server** | Go | High-performance weather service |
| **Calculator** | Python | Mathematical computations |
| **Async Runtime** | asyncio | Concurrent processing |

## 🔐 Security Features

- ✅ **API Key Protection**: Environment variables with `.gitignore`
- ✅ **Input Validation**: Proper error handling and validation
- ✅ **Secure Communication**: STDIO transport protocol
- ✅ **No Hardcoded Secrets**: All credentials externalized

## 📈 Performance

- **Concurrent Processing**: Multiple tool calls handled simultaneously
- **Async I/O**: Non-blocking API calls and server communication  
- **Efficient Memory Usage**: Optimized for long-running sessions
- **Fast Response Times**: < 2 seconds for typical queries

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](mcp-openweather/LICENSE) file for details.

## 🙋‍♂️ Author

**Yeswanth Sai Ram**
- GitHub: [@yeswanthsairam](https://github.com/yeswanthsairam)

## 🌟 Acknowledgments

- [Google Gemini AI](https://ai.google.dev/) for the powerful language model
- [OpenWeatherMap](https://openweathermap.org/) for weather data
- [LangChain](https://langchain.com/) for the agent framework
- [Model Context Protocol](https://modelcontextprotocol.org/) for tool integration

---

**⭐ If you found this project helpful, please give it a star on GitHub!**
