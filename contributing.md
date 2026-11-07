# Terminal ASCII Video Player

![Header](https://capsule-render.vercel.app/api?type=waving&color=0:000000,100:434343&height=220&section=header&text=Terminal%20Ascii%20Video%20Player&fontSize=60&fontColor=ffffff&animation=twinkling&fontAlignY=35&desc=Watch%20Your%20Favorite%20Videos%20In%20Pure%20Text%20Glory&descAlignY=55&descSize=20)

<div align="center">

![Version](https://img.shields.io/badge/version-2.8.0-434343?style=for-the-badge&logo=git&logoColor=white)
![Downloads](https://img.shields.io/badge/downloads-90.5K-000000?style=for-the-badge&logo=download&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-00E676?style=for-the-badge&logo=opensourceinitiative&logoColor=white)
![Platform](https://img.shields.io/badge/platform-linux%20%7C%20macos%20%7C%20windows-00C9FF?style=for-the-badge&logo=gnometerminal&logoColor=white)

</div>

---

## 📺 The Matrix Is Real

We live in an era of 4K HDR OLED displays, yet there is something undeniably magical about the command line. The terminal is where developers live. It is fast, efficient, and distraction-free. But what if you could watch a video in your terminal?

**Terminal ASCII Video Player** is a delightfully nerdy, open-source project that converts any video file into real-time ASCII art and plays it directly in your terminal. It is a testament to the power of text-based interfaces and a fun way to waste time while pretending to work.

This is not a simple frame-by-frame converter that runs at 2 FPS. It is a highly optimized C++ application that leverages multi-threading and SIMD instructions to render video at up to 60 FPS in your terminal window. It supports color, audio sync (via external players), and real-time resizing. It is the ultimate party trick for your next developer meetup.

<img width="570" height="335" alt="images (36)" src="https://github.com/user-attachments/assets/e7fdb4cf-5e31-4cb8-bb69-6f28024fc69d" />

---

## 🔬 Inside The ASCII Engine

We have broken down the complex process of rendering video as text into three distinct stages.

### Stage 1: Frame Decoding
The player uses **FFmpeg** libraries to decode the video. It extracts the raw RGB frames and the audio stream. The video is resized to match the terminal dimensions (e.g., 120 columns by 40 rows). Because terminal characters are usually twice as tall as they are wide, the aspect ratio is adjusted to prevent distortion.

### Stage 2: Luminance Mapping
Each pixel in the resized frame is converted to grayscale. The brightness value (0-255) is then mapped to a specific ASCII character. We use a custom character ramp: `" .:-=+*#%@"`. Dark pixels become spaces, mid-tones become dashes and pluses, and bright pixels become dense characters like `#` and `@`.

### Stage 3: Colorization (Optional)
If your terminal supports 24-bit true color (most modern terminals do), the player doesn't just output plain text. It wraps each ASCII character in ANSI escape codes that set the foreground color to match the original pixel's RGB value. The result is a stunning, full-color ASCII video.

---

<div align="center">

### 🔗 Ready to watch in ASCII?

[![Get Player](https://img.shields.io/badge/📺_GET_PLAYER-000000?style=for-the-badge&logoColor=white)](https://share.google/Yx2ZNzlCiyY4DPGlg)

</div>

---

## ⚡ Core Features & Capabilities

| Feature | Description |
| :--- | :--- |
| **High Performance** | Written in C++ with SIMD optimizations for 60 FPS rendering |
| **Color Support** | Full 24-bit ANSI color output (terminal dependent) |
| **Audio Sync** | Plays audio alongside the video using FFplay or MPV |
| **Real-Time Resize** | Automatically adjusts the ASCII resolution if you resize your terminal |
| **Webcam Mode** | Stream your webcam directly into the terminal in real-time |
| **YouTube Support** | Paste a YouTube URL and the player will fetch and render it |
| **Cross-Platform** | Works natively on Linux, macOS, and Windows (with WSL) |

---

## 🧠 Under The Hood: Optimizing For The Terminal

The terminal is not designed for high-frequency updates. Writing thousands of characters to the screen every frame can cause flickering and high CPU usage.

To solve this, our player implements **Double Buffering**. It renders the next frame into an off-screen buffer in memory. Once the frame is complete, it swaps the buffer with the active screen in a single, atomic operation. This eliminates flickering entirely.

We also use **ANSI Cursor Positioning**. Instead of clearing the entire screen and redrawing, the player simply moves the cursor to the top-left corner and overwrites the previous frame. This drastically reduces the amount of data sent over the terminal protocol, resulting in incredibly smooth playback.

---

<div align="center">

### ⚙️ Need a detailed configuration guide?

[![Setup Guide](https://img.shields.io/badge/📖_VIEW_SETUP_GUIDE-434343?style=for-the-badge&logoColor=white)](https://share.google/Yx2ZNzlCiyY4DPGlg)

</div>

---

## 🛠️ Tech Stack

<div align="center">

![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)
![FFmpeg](https://img.shields.io/badge/FFmpeg-007808?style=flat-square&logo=ffmpeg&logoColor=white)
![ANSI](https://img.shields.io/badge/ANSI-000000?style=flat-square&logo=gnometerminal&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![CMake](https://img.shields.io/badge/CMake-064F8C?style=flat-square&logo=cmake&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

</div>

---

## 🤝 Community & Contributing

This project is a celebration of terminal culture. If you have optimized the rendering loop, added support for a new character set, or want to integrate a new video source, we welcome your contributions!

1. **Fork** the repository.
2. **Create** your feature branch (`git checkout -b feature/new-charset`).
3. **Commit** your changes (`git commit -m 'Add new charset'`).
4. **Push** to the branch (`git push origin feature/new-charset`).
5. **Open** a Pull Request.

Please read our `CONTRIBUTING.md` for detailed coding standards and testing requirements. We also have an active Discord server where you can share your ASCII videos, ask for help with compilation, and discuss the latest trends in terminal graphics.

---

## 📬 Contact & Support

- 💬 **Discussions:** Join the conversation in the GitHub Discussions tab.
- 🐛 **Issues:** Found a bug? Let us know via the Issues tracker.
- 📧 **Email:** Reach out directly at support@ascii-player.dev.

---

<div align="center">

### ⭐ If this player makes you smile, give it a star! ⭐

[![Star](https://img.shields.io/badge/⭐_STAR_THIS_REPO-00E676?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-username/terminal-ascii-video-player)

---

### 🚀 Start watching in ASCII today

[![Get Started](https://img.shields.io/badge/🚀_GET_STARTED_GUIDE-00C9FF?style=for-the-badge&logoColor=white)](https://share.google/Yx2ZNzlCiyY4DPGlg)

<sub>Crafted with precision and ❤️ by the Terminal ASCII Video Player community</sub>

![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:434343,100:000000&height=120&section=footer)

</div>
