<div align="center">

<img src="https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/blog/swift-transformers/swift-chat-ui.png" alt="Swift Chat UI" width="680"/>

# Swift Chat

**A macOS app for running and testing language models on-device using [`swift-transformers`](https://github.com/huggingface/swift-transformers).**

[![Swift](https://img.shields.io/badge/Swift-5.9+-F05138?logo=swift&logoColor=white)](https://swift.org)
[![Platform](https://img.shields.io/badge/Platform-macOS%2013%2B-lightgrey?logo=apple)](https://developer.apple.com/macos/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue)](LICENSE)
[![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Models-yellow)](https://huggingface.co/models?other=coreml)

[Overview](#overview) · [Requirements](#requirements) · [Getting Started](#getting-started) · [Features & Roadmap](#features--roadmap) · [License](#license)

</div>

---

## Overview

Swift Chat is a small macOS application that demonstrates how to integrate the [`swift-transformers`](https://github.com/huggingface/swift-transformers) library into a native Swift app. It lets you load and chat with language models that run **entirely on-device** using Apple's Core ML framework — no API keys, no internet connection required after model download.

This is a fork of the [original Hugging Face repo](https://github.com/huggingface/swift-chat). For background reading, see the companion post: [Running LLMs on-device with Swift and Core ML](https://huggingface.co/blog/swift-coreml-llm).

---

## Requirements

| | Minimum |
|---|---|
| macOS | 13.0 (Ventura) |
| Xcode | 15.0 |
| Swift | 5.9 |

> Apple Silicon (M1 or later) is strongly recommended for reasonable inference speed.

---

## Getting Started

### 1. Clone

```bash
git clone https://github.com/rchhabra13/swift-chat.git
cd swift-chat
```

### 2. Open in Xcode

```bash
open SwiftChat.xcodeproj
```

Swift Package Manager will automatically resolve dependencies, including `swift-transformers`.

### 3. Download a compatible model

The app requires a Core ML–converted language model. You can find compatible models on Hugging Face:

```bash
# Install the Hugging Face CLI if you don't have it
pip install huggingface_hub

# Download a model (example)
huggingface-cli download apple/OpenELM-270M-Instruct --local-dir ./Models
```

Browse available Core ML models → [huggingface.co/models?other=coreml](https://huggingface.co/models?other=coreml)

### 4. Build and run

Select your Mac as the target in Xcode and press `⌘R`.

---

## Features & Roadmap

For the full feature list and roadmap, see the [`swift-transformers` repository](https://github.com/huggingface/swift-transformers).

- [x] On-device inference via Core ML
- [x] Native SwiftUI chat interface
- [x] Streaming token generation
- [x] Multiple model support
- [ ] Model download from Hub at runtime
- [ ] System prompt configuration
- [ ] Token throughput display (tokens/sec)
- [ ] iOS support

---

## Contributing

Pull requests are welcome. For significant changes, please open an issue first to discuss what you'd like to change.

```bash
git checkout -b feature/your-feature
git commit -m "feat: describe your change"
git push origin feature/your-feature
# Open a pull request
```

---

## License

[Apache 2.0](LICENSE) © Hugging Face & contributors.
