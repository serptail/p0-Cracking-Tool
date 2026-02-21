<p align="center">
  <a href="https://ko-fi.com/D1D11CZNM1">
    <img src="https://ko-fi.com/img/githubbutton_sm.svg" alt="Support me on Ko-fi" />
  </a>
</p>

# PolycryptZero (p0) - Hash Decryption Tool

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-GPLv3-green.svg)](LICENSE)
[![Release](https://img.shields.io/badge/Release-v1.0-orange.svg)](https://github.com/bitArtisan1/p0-Decryption-Tool/releases)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)

A hash cracking tool with a GUI. It supports wordlist, brute-force, rule-based, rainbow table, and AI-driven attack modes. The AI mode uses a GPT-2 style transformer model trained specifically for password generation.

<p align="center">
  <img src="https://github.com/user-attachments/assets/2c6cce0f-dd50-4462-84b4-778718667444" alt="Alt text" width="300"/>
</p>

## Features

- **Attack Modes**: Wordlist, brute-force, rule-based, probabilistic (AI), and rainbow tables
- **Hash Algorithms**: MD5, SHA family, bcrypt, BLAKE2, and 20+ others
- **AI Mode**: A custom GPT-2 style model that generates and predicts likely passwords
- **Rainbow Tables**: Bloom filter optimized storage backed by SQLite
- **GUI**: Dark theme with real-time progress tracking

The probabilistic mode runs an autoregressive transformer (see `src/train.py`) that predicts the next token in a sequence. You can tune the number of layers, attention heads, and embedding dimensions. It works the same way GPT-2 does — given a partial password, it predicts what comes next.

## Installation

### Option 1: Executable (Windows)
Download from [Releases](https://github.com/bitArtisan1/p0-Decryption-Tool/releases/tag/v1.0.0) and run `PolycryptZero.exe`. No Python needed.

### Option 2: From source
```bash
git clone https://github.com/bitArtisan1/p0-Decryption-Tool.git
cd p0-Decryption-Tool
pip install -r requirements.txt
python src/main.py
```

**Requirements**

- Python 3.11+
- `customtkinter`, `pycryptodome`, `numpy`, `onnxruntime`, `transformers`

## Usage

1. Enter the hash you want to crack
2. Select the algorithm
3. Pick an attack mode
4. Set up any required parameters (wordlist path, character set, etc.)
5. Hit start

For wordlist and rule-based modes, you'll need a password list. rockyou.txt is a common choice:

```cmd
curl -LO https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt
```

For probabilistic mode, point it at the included `onnx_model-output` directory.

## Attack Modes

- **Wordlist**: Hashes each entry in a password list and compares
- **Brute-force**: Tries every combination for a given character set and length
- **Rule-based**: Takes a wordlist and applies transformations like capitalization, leet speak substitutions, etc.
- **Probabilistic**: The AI model generates candidate passwords based on learned patterns. Point it at `onnx_model_output`
- **Rainbow Table**: Looks up precomputed hashes

## TODO

- Improve model architecture for better pattern matching
- Linux release
- CUDA support for probabilistic mode

## GUI

![p0](https://github.com/user-attachments/assets/96a9679e-bae8-4ffb-9f8c-9fc48e43cf8a)

## Legal Notice

This tool is for educational and personal use only. It's meant to demonstrate how password hashing, security vulnerabilities, and cracking techniques work.

By using it, you agree that:

- You're responsible for how you use it and any consequences that follow
- Using it to access accounts or systems you don't have permission to access is not allowed
- The developers aren't liable for any legal or ethical issues that come from misuse
- It should not be used for anything illegal or malicious

Use it responsibly and within the law. The name PolycryptZero™ and logo are not covered by the open-source license and may not be used in derivative projects or forks without permission.

## Support

If you find this useful — star the repo, share it, or send feedback. It helps.

<a href="https://ko-fi.com/D1D11CZNM1">
  <img src="https://github.com/user-attachments/assets/ba118768-9054-416f-b7b2-adaa69a53434" alt="Support me on Ko-fi" width="200" />
</a>

---
For issues or feature requests, open an issue on GitHub.
<center>
<div style="text-align: center;">
  <p align="center">
    <img src="https://github.com/user-attachments/assets/74c55d3e-6985-4a8a-afbd-46cc33e54e73" alt="octodance" width="110" height="110" style="margin-right: 100px;"/>
    <img src="https://github.com/user-attachments/assets/aeeda621-8287-4f89-bed3-8b89e09f85a5" alt="octodance" width="100" height="100"/>
  </p>
</div>
</center>
