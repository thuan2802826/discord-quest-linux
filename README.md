# Discord Quest Completer (Linux Edition) 🐧

A native Linux desktop application to complete Discord Quests without installing full games.

Forked from [markterence/discord-quest-completer](https://github.com/markterence/discord-quest-completer) with native Linux support, ultra-lightweight dummy runner, and performance improvements.

> [!IMPORTANT]
> **Disclaimer**: This tool is developed strictly for **educational and testing/experimental purposes only**. Please respect Discord's Terms of Service and game developers' policies. Use at your own risk.

---

## 📥 Downloads

Pre-built packages are available on the [Releases](https://github.com/thuan2802826/discord-quest-linux/releases) page:

- **Debian / Ubuntu / Linux Mint**: Download `.deb` package and install:
  ```bash
  sudo dpkg -i discord-quest-completer_*.deb
  ```
- **Fedora / RHEL / openSUSE**: Download `.rpm` package and install:
  ```bash
  sudo rpm -i Discord.Quest.Completer-*.rpm
  ```
- **AppImage (Any Linux distribution)**:
  ```bash
  chmod +x Discord.Quest.Completer_*.AppImage
  ./Discord.Quest.Completer_*.AppImage
  ```
- **Portable (No installation required)**:
  Download `discord-quest-completer-linux-x64-portable.tar.gz`, extract it anywhere, and double-click `start.sh`.

---

## ✨ Features for Linux

- **Native Linux Experience**: Built with Tauri and WebKitGTK.
- **Ultra-lightweight Runner**: Minimal C dummy runner (~5 KB) that emulates game processes with 0% CPU usage.
- **No Wine / Proton Needed**: Games are detected natively via process names on Linux.
- **Optimized Search**: Instant game filtering across 20,000+ titles.
- **Safe Directory Permissions**: Games are isolated in user space (`~/.local/share/discord-quest-completer/games`).

---

## 🎮 How to Use

1. Open **Discord Quest Completer**.
2. Search for the game required by your Discord Quest.
3. Click **Play** to start the dummy game process.
4. Open the Discord app — your status will show that you are playing the game.
5. Wait the required duration (usually 15 minutes) to complete the quest.
6. Click **Stop** when finished.

---

## 🛠️ Development & Building from Source

### Requirements
- Node.js 20+ & `pnpm`
- Rust stable toolchain
- System libraries: `libwebkit2gtk-4.1-dev`, `build-essential`

### Build Instructions
```bash
# 1. Install frontend dependencies
pnpm install

# 2. Build the lightweight Linux runner
pnpm run build:runner:linux
pnpm run copy:runner:linux

# 3. Run in development mode
pnpm run tauri:dev

# 4. Build release package (.deb)
pnpm run tauri build
```

---

## ❓ Frequently Asked Questions (FAQ)

### How does Discord detect games on Linux?
Discord for Linux scans active system processes for matching executable names in its detectable games list. This tool creates an idle native Linux process matching the required game name, allowing Discord to detect the game without Wine or full game files.

### Do I need Wine, Proton, or .NET Runtime on Linux?
No. Everything runs natively on Linux. The dummy game runner is a minimal native C binary (~5 KB) with zero external dependencies.

### Which Linux distributions are supported?
Any modern Linux distribution, including Ubuntu, Debian, Linux Mint, Fedora, Arch Linux, and openSUSE. Pre-built `.deb`, `.rpm`, AppImage, and portable standalone packages are available.

### Is it safe to complete Discord quests this way?
Yes. The app does not inject code into Discord, inspect memory, or modify system files. It merely runs an idle background process named after the game.

---

## ⚠️ Disclaimer / Tuyên bố miễn trừ trách nhiệm

- **Mục đích học tập và thử nghiệm / Educational Use Only**: This software is intended solely for educational, research, and testing purposes.
- **Tuân thủ điều khoản / Terms of Service**: Users are responsible for complying with Discord's Terms of Service and third-party game developer policies.
- **Miễn trừ trách nhiệm / Limitation of Liability**: The authors and maintainers are not responsible for any account suspensions, bans, data loss, or other consequences that may arise from using this tool. Use at your own discretion and risk.
- **Thương hiệu / Trademarks**: Discord and all game titles mentioned are trademarks of their respective owners. This project is open-source, non-commercial, and not affiliated with Discord Inc.

---

## 📄 License & Credits
- Original project by [markterence](https://github.com/markterence/discord-quest-completer).
- Licensed under the [MIT License](LICENSE).

