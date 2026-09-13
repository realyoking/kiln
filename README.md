🔥 Kiln — Build what you think!

An AI-powered, single-file website generator. Describe your idea in plain English and watch AI design, write, and launch a complete website in real time — right in your browser.

Bring Your Own Key (BYOK). No backend. No accounts. No middleman. Your API key never leaves your browser.

---

✨ Overview

Kiln is a fully client-side web application that turns natural-language prompts into complete, self-contained HTML websites. Powered by any OpenAI-compatible LLM endpoint, it streams the generated code live and renders a preview instantly — all within a single index.html file.

Whether you want a landing page for a coffee roaster, a portfolio for a photographer, or a splash page for a hardware startup, Kiln builds it from a single sentence.

---

🚀 Features

· 🧠 AI Website Generation — Describe an idea; get a complete, production-ready HTML document.
· 🔑 Bring Your Own Key — Works with OpenAI, OpenRouter, Groq, Together, Ollama, LM Studio, and any OpenAI-compatible endpoint.
· ⚡ Real-Time Streaming Preview — See the site render as it's being generated.
· 💬 Conversational Iteration — Ask for changes ("make it darker", "add a pricing section") and get a full regenerated site.
· 👁️ Dual View Modes — Toggle between Live Preview and Syntax-Highlighted Code.
· ⬇️ Export Anywhere — Copy to clipboard, download as .html, or open in a full-screen preview.
· 🎨 Stunning Atmosphere — Animated embers, drifting orbs, and a warm kiln-fire aesthetic.
· 📱 Fully Responsive — Optimized for desktop, tablet, and mobile.
· 🔒 Privacy-First — All config stored in localStorage. Requests go directly from your browser to your chosen provider.
· 📦 Zero Dependencies — No build step, no framework, no package manager. Just open the file.

---

🖼️ How It Works

```
┌─────────────────┐    prompt     ┌──────────────────────┐
│   You describe  │ ────────────▶ │  OpenAI-compatible   │
│   your idea     │               │  LLM endpoint        │
└─────────────────┘               └──────────┬───────────┘
                                             │ streams HTML
                                             ▼
                                  ┌──────────────────────┐
                                  │  Live preview iframe │
                                  │  + Code viewer       │
                                  └──────────────────────┘
```

1. Describe — Type your idea or pick a suggestion chip.
2. Generate — Kiln streams a single self-contained HTML file from your chosen model.
3. Preview & Iterate — Watch it render live, then chat to refine.
4. Export — Copy, download, or open the result.

---

🛠️ Getting Started

1. Clone or download

```bash
git clone https://github.com/your-username/kiln.git
cd kiln
```

2. Open the app

Just open index.html in any modern browser:

```bash
open index.html      # macOS
start index.html     # Windows
xdg-open index.html  # Linux
```

No build step. No server required. For best results, serve over http://localhost to avoid CORS quirks with some providers:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

3. Connect your API

Click "Connect API" (top-right) and enter:

Field Example
Base URL https://api.openai.com/v1
API Key sk-...
Model gpt-4o-mini

Or pick a preset — OpenAI, OpenRouter, Groq, Together, Ollama, or LM Studio.

Click Fetch models to auto-populate a list from your endpoint, then Save & connect.

---

🔌 Supported Providers

Kiln works with any OpenAI-compatible /chat/completions endpoint. Verified presets include:

Provider Base URL Notes
OpenAI https://api.openai.com/v1 GPT-4o, GPT-4o-mini, o-series
OpenRouter https://openrouter.ai/api/v1 Access to dozens of models
Groq https://api.groq.com/openai/v1 Extremely fast inference
Together https://api.together.xyz/v1 Open-source models
Ollama http://localhost:11434/v1 Local, no key needed
LM Studio http://localhost:1234/v1 Local, no key needed

💡 Tip: For local providers (Ollama, LM Studio), leave the API key blank.

---

⌨️ Usage

Keyboard Shortcuts

Shortcut Action
Enter Submit prompt / build site
Shift + Enter New line in prompt
Esc Close modal / settings

Tips for Best Results

· Be specific. "A brutalist portfolio for a ceramicist with a dark warm palette" beats "make a website."
· Iterate in steps. Build the structure first, then refine colors, copy, and sections.
· Use a strong model. Larger models (GPT-4o, Claude via OpenRouter, Llama 3.3 70B) produce far better designs.
· Enable CORS-friendly providers if you get network errors (OpenAI, OpenRouter, Groq, and local servers work best).

---

🗂️ Project Structure

```
kiln/
└── index.html      # The entire application — HTML, CSS, and JS in one file
```

That's it. Everything — styling, animations, the API client, the streaming parser, the preview renderer — lives in a single self-contained file.

Internal Architecture

Section Responsibility
Tokens & Reset CSS custom properties, color system, typography scale
Atmosphere Animated background orbs, horizon glow, ember canvas particles
Screens Home hero + Chat workspace with responsive layouts
BYOK Config localStorage-backed settings, model fetching, connection sync
Streaming Client SSE parser for text/event-stream chat completions
Preview Engine Live iframe rendering + syntax highlighting
State Machine Project brief, HTML buffer, generation phases, abort control

---

🎨 Customization

All design tokens live in :root:

```css
:root{
  --ink:#f8f0e6;        /* primary text */
  --muted:#c9b39a;      /* secondary text */
  --or:#ff7a1a;         /* signature orange */
  --amber:#ffb066;      /* accent */
  --line:rgba(255,255,255,.11);
}
```

Change these to rebrand instantly. The ember particle colors are defined in the SPR array:

```js
const SPR = [[255,150,60],[255,105,30],[255,195,120]];
```

The AI's behavior is governed by SYSTEM_PROMPT — edit it to change design rules, enforce specific frameworks, or alter output format.

---

🔒 Privacy & Security

· ✅ Your API key is stored only in localStorage — it never touches a third-party server.
· ✅ Requests go directly from your browser to your chosen provider.
· ✅ Generated sites are sandboxed in an iframe with allow-scripts and allow-forms only (no allow-same-origin), preventing access to the parent page.
· ⚠️ Do not deploy this publicly with a shared key. Since the key lives client-side, anyone with access to the browser can read it. Kiln is designed for personal, local use.

---

🧪 Browser Support

Browser Status
Chrome / Edge ✅ Fully supported
Firefox ✅ Fully supported
Safari 16+ ✅ Supported
Mobile browsers ✅ Responsive layout

Requires ES2020+ and fetch with streaming support.

---

🛣️ Roadmap

□ Project history / saved generations
□ Multi-page site support
□ Image generation integration
□ Export to framework (React, Vue)
□ Custom system prompt editor in UI
□ Share via URL (compressed HTML)

---

🤝 Contributing

Contributions are welcome! Since this is a single-file project, the workflow is simple:

1. Fork the repo
2. Make your changes to index.html
3. Test across browsers
4. Submit a pull request

Please keep the zero-dependency philosophy intact — no build tools, no npm, no bundlers.

---

📄 License

Released under the MIT License. See LICENSE for details.

---

🙏 Acknowledgements

· Fonts: Clash Display & Satoshi by Indian Type Foundry · Instrument Serif
· Icons: Lucide
· Inspiration: Every maker who ever thought "I could build that."

---

<p align="center">
  <strong>🔥 Kiln</strong><br>
  <em>Build what you think.</em>
</p>
