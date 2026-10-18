# SreeOS

**A whole operating system that runs in your browser, or on your desktop.**
No server and no account: it works offline, and every file, app and setting stays on your device.

## What's inside

- **A real desktop.** Windows, a dock or taskbar, Launchpad, overview, notifications, a lock screen and users,
  plus macOS, Windows, Ubuntu and GNOME looks. Open windows come back when you return.
- **Apps.** Files, Editor, Docs, Photos, Preview, Calculator, Terminal, Browser, Task Manager, Settings,
  App Store, App Studio and PC, an x86 emulator that boots `.iso` and `.img` disk images.
- **A Terminal with real tools.** A shell with pipes and redirects, `apt`, `ps`/`kill`, plus `python`, `sqlite3`,
  `lua`, `git` and WASI programs, all running locally in WebAssembly.
- **Web apps.** Install WhatsApp Web, Gmail and others as apps with their own windows.
- **Your data, on your device.** Files live in the browser's private file system (OPFS). Back everything up
  to one file, encrypted with a password if you like, and restore it anywhere.
- **Desktop app.** The same OS in a native window for macOS, Windows and Linux (Tauri). Web apps open in
  native windows there.

## Principles

| | |
|---|---|
| **Offline first** | After the first visit SreeOS starts with the network unplugged. Big engines (Python, the PC emulator) download once, on first use. |
| **Local only** | There is no SreeOS server. Nothing you make leaves your device unless you send it somewhere. |
| **Network is opt-in** | Only the apps and sources you choose go online, such as an App Store catalog or a web app. |
| **Sandboxed apps** | Every app runs in a sandbox with no network access, and asks for what it needs: your files, notifications, the clipboard. |

## Repositories

| Repo | What it is |
|---|---|
| [sreeos](https://github.com/sreeos/sreeos) | The OS itself: a pnpm + Turborepo monorepo (React, TypeScript), the desktop app and the SreeOS Helper extension |
| [apps](https://github.com/sreeos/apps) | The official App Store catalog, live at [sreeos.github.io/apps](https://sreeos.github.io/apps/) |

## Build an app

A Sree app is a folder of HTML, CSS and JavaScript with a `manifest.json`. It gets the `window.sreeos` API for
files, notifications, settings and theming.

1. Open **App Studio** in SreeOS, start from a template and press **Run**.
2. Export it as a `.sreeapp`, or keep it as a folder.
3. Publish it with a pull request to [apps](https://github.com/sreeos/apps). CI checks it, hashes it and adds it
   to the catalog. See [CONTRIBUTING.md](https://github.com/sreeos/apps/blob/main/CONTRIBUTING.md).

You can also host your own catalog on any static host and add it under **App Store → Sources**.

---

Made by [Sumanta Kabiraj](https://github.com/sumantadotai).
