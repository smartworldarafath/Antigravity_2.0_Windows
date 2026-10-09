# Google Antigravity 2.0 - Core Application Source

This repository contains the application source code and frontend architecture of **Google Antigravity 2.0 (v2.19.1)** for analysis, customization, and mobile/Android adaptation planning.

---

## 📁 Repository Structure

```
├── electron/                 # Electron Host & Native OS Bridge (Node.js/TypeScript)
│   ├── main.js               # Application bootstrap, window manager & LS spawner
│   ├── languageServer.js     # Agent backend lifecycle & Gemini API bridge
│   ├── preload.js            # Secure ContextBridge API for Frontend
│   ├── ipcHandlers.js        # IPC communication (storage, dialog, notifications)
│   ├── hostBridgeServer.js   # ConnectRPC bridge between OS and language server
│   └── proto/                # Protobuf schemas (exa.host_bridge_pb.HostBridgeService)
│
├── web_frontend/             # Complete React Web Application (Jetski Web)
│   ├── index.html            # Main web entry point
│   ├── main.js               # Core React UI bundle (Chat canvas, artifacts, diffs)
│   ├── compiled_tailwind.css # Tailwind CSS styling & responsive classes
│   ├── jetbox.css            # Antigravity theme variables and layout styles
│   ├── diff_worker.js        # Code diff worker engine
│   ├── prism_bundle.js       # Code syntax highlighting
│   ├── audio_processor.js    # Voice input processing
│   └── symbols-icons/        # File & action icon assets
│
├── chrome-devtools-mcp/      # Chrome DevTools MCP Server & Diagnostic Tools
│
└── package.json              # App dependencies, metadata & RPC configurations
```

---

## 🚀 Key Architectural Details

1. **Host & Frontend Bridge:**
   - The frontend communicates with the Electron host via `preload.js` context bridge and ConnectRPC (`@connectrpc/connect`, `@bufbuild/protobuf`).
2. **Backend Engine:**
   - The agent backend runs as a language server, connecting to `https://generativelanguage.googleapis.com` (Gemini API) and internal Google tools.
3. **Android Porting Plan:**
   - The UI patterns in `web_frontend` can be adapted into **Jetpack Compose** or **Flutter**.
   - OS-level APIs handled by `electron/ipcHandlers.js` should be replaced with native Android SDK services (Android Storage Access Framework, NotificationManager, Room/DataStore).

---

## 👥 Contributors & Collaboration

Maintained by **smartworldarafath** and team for Google Antigravity application development.
