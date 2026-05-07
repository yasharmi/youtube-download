# 📥 YouTube Downloader via GitHub Actions

> **Important:** Fork this repository first, then use your personal copy.

🌐 **Language:** English | [فارسی](README.md)

Automatically download YouTube videos using GitHub Actions — no software to install, no servers to maintain. Videos are saved directly to the repository and download links are available via **GitHub Releases**.

---

## ✨ Features

- 🚀 **Zero setup** — runs entirely on GitHub's servers
- 🔗 **Direct download links** via GitHub Releases
- 🎯 **Multiple quality options** — from audio-only to 1080p+
- 🔐 **Password-protected ZIP** support
- 🔄 **6 automatic fallback methods** for reliable downloading
- 🍪 **Cookie support** to bypass bot detection
- 📦 **Auto-split** large files into multi-part ZIPs

---

## ⚡ Quick Start

1. **Fork** this repository to your GitHub account
2. Go to the **Actions** tab
3. Select **YouTube Downloader**
4. Click **Run workflow**
5. Enter the video URL, quality, and optional password
6. Wait for the workflow to finish, then grab your file from **Releases** 🎉

> ⏱️ **Heads up:** Each download takes **2–15 minutes** depending on video size and quality. The extra time is due to dependency installation on GitHub's servers at the start of every run — this is completely normal.

Everything runs on GitHub's infrastructure — no local tools needed.

---

## 🛠️ Setup

### 1. Fork or Clone the Repository

Create your own copy of this repository on GitHub.

### 2. Make the Repository Public *(Recommended)*

Go to **Settings → General → Danger Zone → Change visibility → Public**

> If your repository is private, you must be logged into GitHub to download files.

### 3. You're Ready! 🎉

This workflow uses the built-in `GITHUB_TOKEN` — no additional configuration required.

---

## 📥 Downloading a Video

1. Go to the **Actions** tab
2. Click **YouTube Downloader**
3. Click **Run workflow**
4. Fill in the fields:

| Field | Description |
|-------|-------------|
| 🔗 **YouTube URL** | Full URL of the video or playlist |
| 🎬 **Quality** | `best`, `1080`, `720`, `480`, or `audio` (default: `best`) |
| 🔐 **Password** | Optional password to protect the ZIP file |

Once the workflow completes, head to the **Releases** tab for your download links.

---

## 📦 Getting Your Video

1. Go to the **Releases** tab of your repository
2. Open the latest release
3. Find the direct download links in the release description
4. Or browse the `videos/` folder in the repository to download directly

### Large Videos (Split into Multiple Parts)

If a video exceeds **90 MB**, it is automatically split into multi-part ZIPs:

```
video_name.zip
video_name.z01
video_name.z02
```

**To extract:**
1. Download **all parts** (`.zip` and `.z01`, `.z02`, ...)
2. Open the `.zip` file with **7-Zip** or **WinRAR** — all parts are combined automatically

---

## 🎬 Quality Options

| Value | Description |
|-------|-------------|
| `best` | Best available quality (default) |
| `1080` | Up to 1080p |
| `720` | Up to 720p |
| `480` | Up to 480p |
| `audio` | Audio only (MP3/M4A) |

---

## 🍪 Bot Detection / YouTube Login Required

If a download fails with *"Sign in to confirm you're not a bot"*, YouTube has blocked the request. Fix this by providing your browser cookies.

### Step 1 — Export Your Cookies

Install the **Get cookies.txt LOCALLY** extension:
- [Chrome Web Store](https://chrome.google.com/webstore/detail/get-cookiestxt-locally/cclelndahbckbenkjhflpdbgdldlbecc)
- [Firefox Add-ons](https://addons.mozilla.org/firefox/addon/cookies-txt/)

1. Log into [youtube.com](https://youtube.com) in your browser
2. Click the extension icon while on the YouTube page
3. Export cookies in **Netscape** format

### Step 2 — Add to GitHub Secrets

1. Go to **Settings → Secrets and variables → Actions** in your repository
2. Click **New repository secret**
3. Name: `YOUTUBE_COOKIES`
4. Value: paste the full contents of the `.txt` file
5. Click **Add secret**

> ⚠️ **Security Notice:** Cookies grant access to your YouTube account. Never commit them directly to the repository.

---

## 🔧 Troubleshooting

**Workflow didn't run**
- Check the **Actions** tab to see if a run is queued or in progress
- Make sure you have the necessary permissions on the repository

**Download failed**
- The workflow automatically tries 6 different download methods
- If all methods fail, the video may be private, deleted, or geo-blocked
- Try adding YouTube cookies for age-restricted or region-locked content

**Download link doesn't work**
- If the repository is private, you must be logged into GitHub
- Make the repository public to get publicly accessible download links

---

## 📄 License

This project is open source. Feel free to fork, modify, and share.

---

<div align="center">
  Made with ❤️ using <a href="https://github.com/yt-dlp/yt-dlp">yt-dlp</a> and <a href="https://github.com/features/actions">GitHub Actions</a>
</div>
