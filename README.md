<div align="center">

# 🎮 LangForge

**AI-Powered Game Screenshot Translation Tool for Windows**

Capture your game screen · AI translates the text · Result overlays directly on the image  
Play any foreign-language game. Read everything. No interruptions.

[![Version](https://img.shields.io/badge/Version-V1.0.1--beta.6-blue?style=flat-square)]()
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%2F11-0078D6?style=flat-square&logo=windows)]()
[![Open Source](https://img.shields.io/badge/Open%20Source-GitHub-333?style=flat-square&logo=github)](https://github.com/toyakyo)
[![Ko-fi](https://img.shields.io/badge/Support-Ko--fi-ff5f5f?style=flat-square&logo=ko-fi)](https://ko-fi.com/toyakyo)
[![Patreon](https://img.shields.io/badge/Support-Patreon-%24100%2Fmo-orange?style=flat-square&logo=patreon)](https://www.patreon.com/cw/LangForge)

[📥 Download](https://goonsoft.tw2.nde.tw/tutorial/tutorial.php#download) •
[📖 Documentation](https://goonsoft.tw2.nde.tw/tutorial/tutorial.php) •
[💬 Community](https://www.facebook.com/groups/2150940378645437) •
[☕ Ko-fi](https://ko-fi.com/toyakyo) •
[💜 Patreon](https://www.patreon.com/cw/LangForge)

</div>

---

## 🌟 What is LangForge?

LangForge is an open-source AI-assisted game translation tool for Windows. It automatically detects your game window, captures the screen, and translates on-screen foreign text using your choice of AI engine — overlaying the result directly on the screenshot, positioned where the original text was.

Designed for players who want to enjoy Japanese, Korean, or any foreign-language game without switching windows or pausing to look things up.

> ⚠️ LangForge is under active development. Features and UI may change between versions.

---

## 🔥 Three Translation Modes

### 🔍 Local OCR + Google Translate — Zero Setup, Zero Cost
No API key. No account. No configuration whatsoever.  
LangForge uses **EasyOCR** locally to detect and position text, then routes through **Google Translate** (free, no quota limits) for the actual translation.  
**→ Best for: first-time users, or anyone who doesn't want to create API accounts.**

### 🦙 OLLAMA Local Engine — Full Offline AI
Runs entirely on your own machine. No internet after setup, no API costs, no data leaves your device.  
Requires installing [OLLAMA](https://ollama.com) and a vision-capable model (e.g. `llava`). A dedicated GPU is recommended.  
**→ Best for: privacy-focused users with decent hardware.**

### ☁️ Cloud Engines — Best Translation Quality
Supports **Gemini, Groq, Mistral** (free tiers available) and **OpenAI, Claude** (paid).  
LangForge automatically rotates engines when a free quota runs out — keeping translation running uninterrupted.  
**→ Best for: users who want the highest translation accuracy.**

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🖼️ **Overlay Translation** | Translated text positioned directly on the game screenshot |
| 🌐 **12 Languages** | Japanese, English, Korean, French, German, Spanish, Italian, Portuguese, Russian, and more |
| 📐 **Horizontal / Vertical Layout** | Supports both Western (L→R) and Japanese-style (top→bottom, R→L) text direction |
| 📋 **AI Walkthrough Analysis** | 3–5 actionable hints based on the current game screen |
| ⚡ **Auto-Capture** | Detects scene stability and triggers translation automatically |
| ⌨️ **Global Hotkeys** | Trigger translation or walkthrough without leaving your game |
| 🎬 **Session Recording** | Records your play session (screenshot every 500ms), replay and translate any frame later |
| 🗂️ **Translation History** | SQLite-backed records with screenshot, organized by game, window, and platform |
| 🔐 **Encrypted API Keys** | Keys encrypted with your machine ID (XOR + base64) before saving locally |
| 🖱️ **Click-to-Select Window** | Click directly on your game window to set it as target — no typing needed |
| 🌍 **Bilingual UI** | Supports 繁體中文 and English, auto-detects system language on first launch |
| 🔄 **Auto Engine Rotation** | Automatically switches to the next available engine when free quota runs out |
| 📊 **Quota Dashboard** | Real-time view of today's usage per model, with RPM and RPD tracking |
| 🛠️ **Platform Editor** | Add, rename, or remove game platforms and emulators directly in the UI |

---

## 🚀 Getting Started

### Option A — Zero Setup (Recommended for First-Time Users)

1. Download and run `LangForge.exe`
2. Select **🔍 Local OCR + Google Translate** as your engine
3. Set your target game window title in the **Capture** tab
4. Click **Capture & Translate** — done!

> No API key needed. No account required.

### Option B — Cloud Engine (Best Quality, Free)

1. Get a free **Gemini API Key** from [aistudio.google.com](https://aistudio.google.com/apikey) (Google account required, no credit card)
2. Run LangForge, select **☁ Cloud Engine → Gemini**
3. Paste your key and start translating

> For maximum free quota, also set up [Groq](https://console.groq.com/keys) and [Mistral](https://console.mistral.ai/) — LangForge rotates them automatically (1,500+ free translations/day combined).

### Option C — Fully Offline (OLLAMA)

1. Install [OLLAMA](https://ollama.com)
2. Run `ollama pull llava` to download a vision model
3. Start with `ollama serve`
4. In LangForge, select **🦙 Local Engine (OLLAMA)**

---

## 📋 Supported AI Engines

| Engine | Model | Free Daily Quota | Notes |
|--------|-------|-----------------|-------|
| **Gemini Flash** | gemini-2.5-flash | 20 RPD | Strong multilingual vision |
| **Gemini Lite** | gemini-3.1-flash-lite-preview | 500 RPD | Lightweight, high frequency |
| **Groq** | llama-4-scout-17b | 1,000 RPD | Fastest free option |
| **Mistral** | pixtral-12b-2409 | 500 RPD | Vision-specialized |
| **OpenAI** | gpt-4.1-mini / gpt-4.1 / gpt-4o | Paid | Most stable quality |
| **Claude** | Haiku / Sonnet / Opus | Paid | Strong semantic understanding |
| **🦙 OLLAMA** | Any vision model | Unlimited (local) | Fully offline, no API key |
| **🔍 OCR + Google** | EasyOCR + Google Translate | Unlimited (free) | Zero setup required |

> ⚠️ Free quota numbers are subject to change. Always check each provider's official announcements for the latest limits.

---

## 🔐 Security & Transparency

LangForge is verified using **Microsoft Process Monitor (Sysinternals)**.

The application makes **only the API calls required for translation** — to the AI engine you have selected. No data is sent to any developer-controlled server.

- ✅ API Keys stored locally in `configs.json`, encrypted with your machine ID
- ✅ No upload of screenshots or personal data
- ✅ No connection to developer servers
- ✅ No remote license verification
- ✅ SHA256 checksum published for every release
- ✅ Full source code available for inspection

**File Integrity Verification**

| Release | File | SHA256 |
|---------|------|--------|
| V1.0.1-beta.5 | `LangForge.exe` | `F73949570301C1D073DC75208852B3D6D9EA8ABD81859EFD56FA70D9089A1E6D` |

```powershell
# Verify in PowerShell
Get-FileHash .\LangForge.exe -Algorithm SHA256
```

> If the hash does not match, do **not** run the file. Re-download from the official page.

---

## 🛠️ Requirements

| Item | Requirement |
|------|-------------|
| OS | Windows 10 / 11 (64-bit recommended) |
| Network | Required for cloud engines; OLLAMA mode works offline |
| API Key | Required for cloud engines; not required for OLLAMA or OCR mode |
| OLLAMA | Optional — install from [ollama.com](https://ollama.com) for local engine |
| EasyOCR | Optional — `pip install easyocr` for local OCR mode |

---

## 📦 Installation (Running from Source)

```bash
# Install dependencies
pip install anthropic easyocr google-genai groq keyboard mistralai numpy openai pillow pywin32

# Run
python LangForge.py
```

---

## 📁 Project Structure

```
LangForge/
├── LangForge.py          # Main application
├── platforms.json        # Game platform definitions
├── emulators.json        # Emulator definitions
├── configs.json          # User config (auto-generated, API keys encrypted)
├── favicon.ico           # App icon
└── translation_logs/     # SQLite DB + screenshots (auto-generated)
    ├── langforge.db
    └── screenshots/
```

---

## 🗺️ Roadmap

- [x] Cloud engine support (Gemini, Groq, Mistral, OpenAI, Claude)
- [x] OLLAMA local engine
- [x] Local OCR + Google Translate mode (zero setup)
- [x] Session recording & playback
- [x] AI walkthrough analysis
- [x] Auto-capture with scene stability detection
- [x] Encrypted API key storage
- [x] Bilingual UI (繁中 / English)
- [x] Platform editor
- [ ] Multi-language UI (beyond zh/en)
- [ ] macOS / Linux support (planned)

---

## 💜 Support the Project

LangForge is built by a solo developer in spare time. If it's helped you enjoy a game you couldn't read before — or you just want to see where this project goes — your support means a lot.

| Platform | Link | Type |
|----------|------|------|
| ☕ Ko-fi | [ko-fi.com/toyakyo](https://ko-fi.com/toyakyo) | One-time or monthly |
| 💜 Patreon | [patreon.com/cw/LangForge](https://www.patreon.com/cw/LangForge) | $1 / month |
| 💬 FB Community | [LangForge Official Community](https://www.facebook.com/groups/2150940378645437) | Free to join |

---

## 📬 Links

| | |
|---|---|
| 🌐 Official Docs | https://goonsoft.tw2.nde.tw/tutorial/tutorial.php |
| 📥 Download | https://goonsoft.tw2.nde.tw/tutorial/tutorial.php#download |
| 💬 FB Community | https://www.facebook.com/groups/2150940378645437 |
| ☕ Ko-fi | https://ko-fi.com/toyakyo |
| 💜 Patreon | https://www.patreon.com/cw/LangForge |

---

## ⚠️ Disclaimer

LangForge is provided as-is during active development and may not be fully stable. Use at your own risk.  
API usage costs (if any) are the responsibility of the user based on their chosen AI engine provider.  
Translation results are AI-generated and may not always be accurate.

---

<div align="center">

*Copyright © 2026 GoOnSoft. All rights reserved.*  
*Built with ❤️ by Toya Kyo — Solo Developer from Taiwan 🇹🇼*

</div>
