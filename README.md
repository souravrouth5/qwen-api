# 🤖 Qwen API

<p align="center">
  <img src="./public/assets/Qwen.png" alt="Qwen API" width="180" />
</p>

> **A powerful OpenAI-compatible API powered by Qwen — with web search, deep research, image generation, file uploads, agentic tool calling, and more.**

---

## ✨ What We Offer

| # | Feature | Description |
|---|---|---|
| 1 | 💬 **Chat Completions** | Full conversational AI with session management |
| 2 | 🌊 **Streaming** | Real-time token streaming via SSE |
| 3 | 🧠 **Thinking Modes** | Control reasoning depth — `Auto`, `Thinking`, `Fast` |
| 4 | 🔍 **Web Search** | Live, grounded answers from real-time web results |
| 5 | 🔬 **Deep Research** | Multi-step autonomous research with synthesis |
| 6 | 🖥️ **Web Dev / Artifacts** | Generate runnable web apps and interactive components |
| 7 | 📊 **Slides Generation** | Create full presentation decks from a prompt |
| 8 | 🔧 **Function Tool Calling** | OpenAI-compatible agentic tool loop — server-side execution |
| 9 | 🖼️ **Image Generation** | Generate images from text prompts |
| 10 | ✏️ **Image Editing** | Edit images with a prompt |
| 11 | 📁 **File Upload** | Upload images, documents, and videos for use in chat |
| 12 | 🔑 **Token Management** | Validate and refresh your session token |
| 13 | 📋 **Model Listing** | Fetch all available models with full capabilities metadata |
| 14 | 🌐 **OpenAI Compatible** | Drop-in replacement for OpenAI — works with Cline, Cursor, Windsurf, CodeGPT |

---

## 🧠 Available Models

| Model | ID | 👁️ Vision | 💡 Thinking | 🌐 Search | 🎵 Audio | 📄 Document | 🎬 Video | Context |
|---|---|---|---|---|---|---|---|---|
| Qwen3.6-Plus | `qwen3.6-plus` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | 1M |
| Qwen3.6-Max-Preview | `qwen3.6-max-preview` | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | 262.144K |
| Qwen3.6-27B | `qwen3.6-27b` | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | 262.144K |
| Qwen3.5-Plus | `qwen3.5-plus` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | 1M |
| Qwen3.5-Omni-Plus | `qwen3.5-omni-plus` | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | 262.144K |
| Qwen3.6-35B-A3B | `qwen3.6-35b-a3b` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | 262.144K |
| Qwen3.5-Flash | `qwen3.5-flash` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | 1M |
| Qwen3.5-Max-Preview | `qwen3.5-max-2026-03-08` | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | 262.144K |
| Qwen3.6-Plus-Preview | `qwen3.6-plus-preview` | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | 1M |
| Qwen3.5-397B-A17B | `qwen3.5-397b-a17b` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | 262.144K |
| Qwen3.5-122B-A10B | `qwen3.5-122b-a10b` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | 262.144K |
| Qwen3.5-Omni-Flash | `qwen3.5-omni-flash` | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | 262.144K |
| Qwen3.5-27B | `qwen3.5-27b` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | 262.144K |
| Qwen3.5-35B-A3B | `qwen3.5-35b-a3b` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | 262.144K |
| Qwen3-Max | `qwen3-max-2026-01-23` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | 262.144K |
| Qwen3-235B-A22B-2507 | `qwen-plus-2025-07-28` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | 131.072K |
| Qwen3-Coder | `qwen3-coder-plus` | ✅ | ❌ | ❌ | ✅ | ✅ | ✅ | 1.048576M |
| Qwen3-VL-235B-A22B | `qwen3-vl-plus` | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | 262.144K |
| Qwen3-Omni-Flash | `qwen3-omni-flash-2025-12-01` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | 65.536K |
| Qwen2.5-Max | `qwen-max-latest` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | 131.072K |

> Model list is updated automatically every 5 days from the live API.

---

## 🔐 Authentication

Every request requires your Qwen session token:

```
Authorization: Bearer <your_qwen_token>
```

OpenAI-compatible routes also accept:

```
x-api-key: <your_qwen_token>
```

### Getting your token

1. Go to [chat.qwen.ai](https://chat.qwen.ai) and log in
2. Open DevTools → Console (`F12`)
3. Paste and run:

```js
javascript:(function(){if(window.location.hostname!=="chat.qwen.ai"){alert("🚀 This code is for chat.qwen.ai");window.open("https://chat.qwen.ai","_blank");return;}function getApiKeyData(){const token=localStorage.getItem("token");if(!token){alert("❌ qwen access_token not found !!!");return null;}return token;}async function copyToClipboard(text){try{await navigator.clipboard.writeText(text);return true;}catch(err){const textarea=document.createElement("textarea");textarea.value=text;textarea.style.position="fixed";textarea.style.opacity="0";document.body.appendChild(textarea);textarea.focus();textarea.select();const success=document.execCommand("copy");document.body.removeChild(textarea);return success;}}const apiKeyData=getApiKeyData();if(!apiKeyData)return;copyToClipboard(apiKeyData).then((success)=>{if(success){alert("🔑 Qwen access_token copied to clipboard !!! 🎉");}else{prompt("🔰 Qwen access_token:",apiKeyData);}});})();
```

4. Your token is copied to clipboard automatically.

> Tokens expire periodically. Use `GET /v1/refresh` to silently renew without opening a browser.

---

## 📡 Base URLs

| Surface | Base URL | Use for |
|---|---|---|
| Full API | `https://qwen-web-gateway.onrender.com/v1` | Full control — all features |
| OpenAI-compatible | `https://qwen-web-gateway.onrender.com/v1/openai` | Cline, Cursor, Windsurf, CodeGPT |

---

## 💡 Quick Start

### Basic chat

```js
const res = await fetch("https://qwen-web-gateway.onrender.com/v1/openai/chat/completions", {
  method: "POST",
  headers: {
    "Authorization": "Bearer <your_token>",
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    model: "qwen3.5-plus",
    messages: [{ role: "user", content: "Hello!" }],
    stream: false,
  }),
});
const data = await res.json();
console.log(data.choices[0].message.content);
```

### Streaming

```js
const res = await fetch("https://qwen-web-gateway.onrender.com/v1/openai/chat/completions", {
  method: "POST",
  headers: { "Authorization": "Bearer <your_token>", "Content-Type": "application/json" },
  body: JSON.stringify({
    model: "qwen3.5-plus",
    messages: [{ role: "user", content: "Tell me a joke" }],
    stream: true,
  }),
});
const reader = res.body.getReader();
const decoder = new TextDecoder();
while (true) {
  const { done, value } = await reader.read();
  if (done) break;
  console.log(decoder.decode(value));
}
```

### Web search

```js
body: JSON.stringify({
  model: "qwen3.5-plus",
  messages: [{ role: "user", content: "Latest AI news?" }],
  stream: true,
  tools: [{ type: "web_search" }],
})
```

### Deep research

```js
tools: [{ type: "deep_research" }]           // normal depth
tools: [{ type: "deep_research_advanced" }]  // advanced depth
```

### Image generation

```js
const res = await fetch("https://qwen-web-gateway.onrender.com/v1/images/generations", {
  method: "POST",
  headers: { "Authorization": "Bearer <your_token>", "Content-Type": "application/json" },
  body: JSON.stringify({
    prompt: "A futuristic city at sunset",
    size: "1920x1080",
  }),
});
const { data } = await res.json();
console.log(data[0].url);
```

### Thinking modes

```js
{ thinking_mode: "Auto" }      // model decides (default)
{ thinking_mode: "Thinking" }  // always reasons step by step
{ thinking_mode: "Fast" }      // skips reasoning, fastest
```

---

## 🤖 IDE Integration (Cline, Cursor, Windsurf, CodeGPT)

Point your IDE extension at the OpenAI-compatible surface:

| Setting | Value |
|---|---|
| Base URL | `https://qwen-web-gateway.onrender.com/v1/openai` |
| API Key | Your Qwen token |
| Model | Any ID from the models table above |

Sessions are managed automatically — each task gets its own chat, resuming a task picks up the correct conversation.

---

## 📖 API Reference

Full interactive API reference: **[qwen-web.readme.io →](https://qwen-web.readme.io/reference/listmodels)**

---

## 📝 Notes

- Tokens expire periodically — use `GET /v1/refresh` to silently renew
- `stream: true` returns SSE; `stream: false` returns OpenAI-compatible JSON
- `deep_research` and `deep_research_advanced` always force `thinking_mode: Fast`
- Image generation returns `{ data: [{ url }], content, usage }` — `content` is the model's description
- Function tool calling requires `stream: false` for the server-side agentic loop

---

## 📄 License

See [LICENSE](./LICENSE) for details.
