# TikPort

**TikTok on your Roku.**

TikPort is an unofficial TikTok viewer for Roku devices, bringing TikTok-style video browsing and playback to your TV.

The project combines a Roku SceneGraph application with a Node.js backend powered by TokKit to retrieve TikTok video information and playback links.

> **Status:** In Development
> **Current Version:** 1.0.1

---

## Features

- **For You Feed** – Browse videos from a TikTok-style feed.
- **Video Playback** – Watch TikTok videos directly on your Roku.
- **Creator Information** – Display video creator information and descriptions.
- **Search** – Search for TikTok videos.
- **Roku Remote Navigation** – Navigate the application using your Roku remote.
- **Related Videos** – Retrieve additional videos as you browse.
- **Backend Integration** – Uses a Node.js backend to communicate with TikTok through TokKit.

Some features are still being developed or may not work reliably.

---

## How It Works

TikPort uses two main components:

### 1. Roku Application

The Roku application is built using:

- BrightScript
- Roku SceneGraph
- XML

It handles the user interface, remote navigation, video playback, and communication with the backend.

### 2. Backend

The backend is built with:

- Node.js
- TokKit (`@odion-cloud/tokkit.js`)
- HTTP API endpoints

The backend retrieves video information and provides the Roku application with the data needed to display and play videos.

---

## Requirements

### Hardware and Software

- A compatible Roku device
- A computer capable of running Node.js
- Node.js installed
- Roku Developer Mode enabled
- A network connection shared by the Roku and backend computer

### Development Tools

- Node.js
- npm
- Roku Developer Application Installer
- A code editor

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/TikPort.git
```

Navigate into the project directory:

```bash
cd TikPort
```

### 2. Set Up the Backend

Navigate to the backend directory.

Install the dependencies:

```bash
npm install
```

Start the backend using the start command configured in its `package.json`.

### 3. Configure the Roku Application

Open `MainScene.brs` and locate the backend address:

```brightscript
m.apiBase = "http://192.168.1.150:3000"
```

Replace the address with the LAN IP address of the computer running the backend.

Make sure the Roku and computer are connected to the same network.

### 4. Install on Roku

1. Enable Developer Mode on your Roku.
2. Open the Roku Developer Application Installer from a browser on your computer.
3. Package the Roku application.
4. Upload and install the package.
5. Launch TikPort.

---

## API Endpoints

The Roku application communicates with the backend through HTTP endpoints.

| Endpoint                     | Purpose                               |
| ---------------------------- | ------------------------------------- |
| `/api/feed?limit=50`         | Retrieve videos for the For You feed  |
| `/api/feed/next?videoId=...` | Retrieve additional or related videos |
| `/api/search?q=...`          | Search for videos                     |

The backend is responsible for retrieving and formatting the data before sending it to the Roku application.

---

## Known Issues

TikPort is still under active development. The following issues are currently known:

- **Freezes when Searching** – The application may freeze when attempting to search for videos.
- **Only 2 Videos** – The For You feed currently returns only two videos, even when requesting a larger batch.
- **Last Video Freezes the Entire App** – Reaching the last available video may cause TikPort to freeze or become completely unresponsive.

These issues are being investigated and will be addressed in future updates.

---

## Roadmap

Planned improvements include:

- [ ] Fix search-related freezing.
- [ ] Fix the two-video feed limitation.
- [ ] Fix freezing when reaching the last video.
- [ ] Improve video buffering and playback reliability.
- [ ] Improve video transitions.
- [ ] Add more reliable playback error handling.
- [ ] Improve feed loading and navigation.
- [ ] Develop SmartFeed for personalized recommendations.
- [ ] Improve creator information and video metadata.
- [ ] Prepare for a public release.

---

## Disclaimer

TikPort is an unofficial third-party project.

It is not affiliated with, endorsed by, or officially connected to TikTok, ByteDance, or Roku.

TikTok is a trademark of its respective owner. This project is intended for educational and development purposes.

Availability and functionality may depend on changes to TikTok's services and APIs.

---

## Contributing

Contributions, bug reports, and suggestions are welcome!

If you find a bug or have an idea for improving TikPort, feel free to open an issue or submit a pull request.

---

## Credits

- **TikPort** – Application development
- **TokKit** – TikTok data retrieval
- **Roku** – SceneGraph and BrightScript platform

---

**TikPort — Bringing TikTok to the big screen.**
