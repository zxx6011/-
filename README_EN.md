# Happy Birthday 🎂 — Interactive 3D E-card
<p>
<img src="https://img.shields.io/github/stars/mnbvcxzz1375/HappyBirthday" alt="stars" />
<img src="https://img.shields.io/github/issues/mnbvcxzz1375/HappyBirthday" alt="issues" />
<img src="https://img.shields.io/github/forks/mnbvcxzz1375/HappyBirthday" alt="forks" />
<img src="https://img.shields.io/github/license/mnbvcxzz1375/HappyBirthday" alt="license" />
<a href="https://app.netlify.com/sites/friendly-paprenjak-ad64b7/deploys"><img src="https://api.netlify.com/api/v1/badges/39d29171-f3b1-4172-932e-1f657058303a/deploy-status" alt="Netlify Status" /></a>
</p>
A browser-based birthday surprise page: 3D particle cake, gesture recognition, candle blowing animation, flipable greeting card...
Perfect for creating a personalized birthday web page for friends/partners/family.

> Open the link, allow camera and microphone, and enjoy the full interactive experience in your browser.

---

## Online Demo

- Demo address: <https://happybirthdayhyl.netlify.app/>
> Access may be slower on domestic networks. It is recommended to visit in a better network environment or use a proxy.

## How to Use

+ Modify the song: Download the song you want, put it in the src folder, and modify line 176 of `index.html` to your song.
   - `<source src="./src/your song" type="audio/mpeg">`

+ Modify the card content: At the beginning of line 760 of `index.html`, there are comments indicating which cards are the first and which are the second.

Replace the content in the HTML with your own content, then deploy on github pages or other hosting websites (such as netlify / Vercel).
- Netlify deployment (recommended for domestic users, not blocked by firewall)

   [![Deploy with NEtlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/mnbvcxzz1375/HappyBirthday)

+ If there are any issues with the camera or sound, you can open the Developer panel (`F12`') to see what's wrong
---

## Features

- 🎉 **3D Particle Birthday Cake**
  - Rendered particle scenes using Three.js, supporting different configurations such as cakes/text
  - Mouse drag / touch swipe / gesture recognition slide to rotate the view

- 🖐️ **Gesture-driven Entry Animation**
  - Hand gesture recognition based on MediaPipe Hands
  - Automatic countdown triggered by actions like raising hands to enter interactive mode

- 💨 **"Blow Out Candles" Interaction**
  - Microphone volume analysis based on Web Audio API
  - Blow into the microphone and the progress bar will gradually fill up
  - Support keyboard spacebar / mobile long press screen to simulate blowing

- 💌 **Flipable Greeting Card**
  - Celebration animation triggered after blowing out candles
  - Display flipable birthday greeting card with customizable content

- 🎨 **Real-time Color Palette**
  - Settings panel in the upper right corner of the page to adjust cake colors
  - Support multiple configurations such as base color / top color / cream color

- 📱 **Multi-device Compatibility**
  - Prioritized for desktop browsers (best experience)
  - Mobile access support (some devices may have permission or audio output differences, see notes below)

---

## Tech Stack

- **Three.js** — 3D scene and particle rendering
- **MediaPipe Hands** — Gesture detection and tracking
- **Web Audio API** — Microphone volume collection and "blowing" determination
- **Tailwind CSS** — Rapid page styling
- **Google Fonts** and other frontend resources

---

## Environment Requirements

- Modern browser (Recommended: Latest version of Chrome / Edge / Firefox)
- For gesture or candle blowing interactions:
  - **Camera** permission required (gesture recognition)
  - **Microphone** permission required (breath detection, or use key/long press instead)

> ⚠️ Note:
> Directly opening `index.html` with `file://` for local deployment will trigger browser security policies, causing camera/microphone unavailability.
> Please access through HTTP/HTTPS local server.

---

## Quick Start

### Method 1: VS Code + Live Server (Recommended)

1. Open the project root directory (containing `index.html`) with VS Code.
2. Install and enable the VS Code plugin **"Live Server"**.
3. Right-click on `index.html` and select **"Open with Live Server"**.
4. Browser will automatically open `http://127.0.0.1:xxxx/index.html` (port varies).

### Method 2: Any Static Server (using http-server as example)

Make sure Node.js and npm are installed, then run after entering the project root directory:

```bash
# If http-server is not yet installed
npm install -g http-server

# Start local static server (sample port 5500)
http-server -c-1 . -p 5500
# Then visit in browser
# http://localhost:5500/index.html
```

## Others:
- Deployment displays the `index.html` file in the root directory. Please modify to the actual filename as needed.
- There is also an `index_c.html` file in the root directory, which is another style page. There are some issues, such as the cake effect not being well presented. Can be modified by yourself if time permits.
- This project has poor compatibility with mobile devices. Android devices do not work well with built-in mobile browsers, and microphone and camera permissions are likely to be unavailable. Apple devices can be used normally. However, there is a common issue that the birthday song plays through the earpiece. For reconstruction recommendations, using a framework refactor may help avoid the above issues.