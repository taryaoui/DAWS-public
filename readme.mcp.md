# DAWS MCP Server

![DAWS Logo](assets/logo.svg)

**DAWS MCP** is a secure, AI-powered Model Context Protocol (MCP) server that unifies your organization's data, projects, and business processes. It enables seamless integration with LLM-powered clients (Claude Desktop, Copilot, Cline, VS Code Copilot, etc.) for automation, analytics, and collaboration.

---

## 🚀 Quick Start

**Requirements:** Node.js >= 18, API Key (see below)

### Install & Launch

```sh
npx @da-ws-mcp
```

### Connect with Your Favorite MCP Client

- **Claude Desktop:** Add a new MCP server, command: `npx @da-ws-mcp`
- **GitHub Copilot:** Use Copilot's MCP integration, point to your DAWS MCP endpoint
- **Cline:** Configure Cline to use DAWS MCP as backend
- **VS Code Copilot:** Add DAWS MCP server in Copilot settings
- **Other MCP Clients:** Use `npx @da-ws-mcp` as the command to connect

---

## 🛠️ MCP Client Server JSON Installation Examples

Below are example JSON configurations for installing and connecting to DAWS MCP using different methods:

### 1. NPX (Preferred)

```json
"DAWS-MCP-NPX": {
  "command": "npx",
  "args": [
    "-y",
    "@da-ws-mcp/1.0.2"
  ],
  "type": "stdio"
}
```

### 2. Local Build

```json
"DAWS-MCP-NODE": {
  "type": "stdio",
  "command": "node",
  "args": [
    "PATH\\TO\\build\\index.js"
  ],
  "env": {
    "DWS_API_BASE": "API_BASE_URL",
    "DAWS_API_KEY": "API_KEY_VALUE"
  }
}
```

### 3. Streamable HTTP (SSE)

```json
"DAWS-MCP-SSE": {
  "transport": "streamable_http",
  "url": "https://DAWS_MCP_SSE_URL/mcp/",
  "headers": {
    "Accept": "application/json, text/event-stream"
  },
  "timeout": 60,
  "type": "http"
}
```

---

### Example: Start in Streamable HTTP (SSE) Mode

```sh
export MCP_TRANSPORT=sse
npx @da-ws-mcp
```

---

## API Key (Security)

DAWS MCP requires an API key for secure access. You can provide it:

- As an environment variable: `DAWS_API_KEY=your-key npx @da-ws-mcp`
- In the MCP client `initialize` request params:

```json
{
  "jsonrpc": "2.0",
  "method": "initialize",
  "params": {
    "DAWS_API_KEY": "user-specific-key-here"
  },
  "id": 1
}
```

> **API key management UI coming soon in DAWS platform.**

---

## Features

- Unified org, files, employees, directories, projects (CRUD coming soon)
- AI-driven automation & LLM integration
- Secure, role-based access
- Flexible: local, cloud, or container deployment

---

## Author & License

- **Rachid Taryaoui** ([LinkedIn](https://www.linkedin.com/in/taryaoui/) / [GitHub](https://github.com/taryaoui))
- License: MIT — see [LICENSE](LICENSE)

---

## About D&A Technologies

[D&A Technologies](https://da-technologies.ma/) — Digital transformation partner, 90+ certified experts, 150+ projects, 80+ clients. Salesforce partner since 2016. Offices in Paris & Casablanca.
