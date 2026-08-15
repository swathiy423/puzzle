# PuzzleCam — Gesture Capture

A browser-based photobooth app controlled entirely by hand gestures. No installation, backend, or additional dependencies are required.

## **DESCRIPTION**

PuzzleCam captures a photo using your hands as a "frame," transforms it into a 3×3 puzzle with a black-and-white photobooth effect, and lets you solve the puzzle using pinch gestures. Once completed, the puzzle is saved to a downloadable photo strip.

## **RUN THE APP**

You can use the deployed version directly in your browser:

**Live Demo:** https://puzzle-beta-eosin.vercel.app/

Open the link, allow camera access when prompted, and start using the gesture controls.

## **SYSTEM REQUIREMENTS**

- **Browser:** Chrome or Edge (recommended), Firefox
- **Hardware:** Webcam
- **Internet connection:** Required to load the MediaPipe model (~10 MB, only the first time)
- **Local server:** Only required when running the project locally

## **INSTALLATION AND SETUP**

### 1. Clone the Repository

```bash
git clone https://github.com/mishu006/Puzzle.git
cd Puzzle
```

### 2. Start a Local Server

The app uses ES modules and camera access, so it needs to run over HTTP when running locally.

Install the **Live Server** extension in VS Code and click **Go Live**.

### 3. Open in the Browser

```text
http://localhost:5500
```

Allow camera access when the browser asks for permission.

> **Note:** If you use the deployed Vercel version, you do not need to perform these local setup steps.

## **PROJECT STRUCTURE**

```text
Puzzle/
├── index.html        # Application entry point
├── app.js            # Complete application logic (tracking, puzzle, gallery)
├── css/
│   └── styles.css    # Styling and layout
└── .gitignore
```

## **GESTURE CONTROLS**

| Gesture | Action |
|---|---|
| Both hands making a pinch | Freeze the capture area and start the countdown |
| One hand pinching over a puzzle piece | Drag the puzzle piece |
| Closed fist (hold) | Save completed puzzle / Reset the board |

## **APPLICATION LOGIC**

1. Show both hands to the camera and use a pinch gesture to define the capture frame.
2. Hold the pinch during the countdown — the photo is captured automatically.
3. The photo is divided into a 3×3 puzzle with a black-and-white photobooth filter.
4. Rearrange the pieces using pinch-and-drag gestures.
5. Once the puzzle is completed, close your fist to save it to the photo strip with a fragmentation animation.
6. Download the complete photo strip once you have 3 saved puzzles.

## **TECHNOLOGY STACK**

- **MediaPipe Tasks Vision** `v0.10.14` — hand landmark detection
- **Canvas 2D API** — rendering, puzzle pieces, and photobooth effects
- **JavaScript (ES Modules)** — no frameworks
- **CSS Custom Properties** — theming and layout

All external dependencies are loaded through CDNs. No additional installation is required.

## **TROUBLESHOOTING**

### **The camera does not turn on**

Make sure no other application such as Teams, Zoom, Discord, or another browser tab is currently using the camera.

### **The app cannot load the model**

Check your internet connection. The MediaPipe model (~10 MB) is downloaded from `storage.googleapis.com`, while the runtime is loaded from `cdn.jsdelivr.net`. If either domain is blocked by your network, the application may not start.

### **The app shows a black screen**

If you are running the project locally, make sure you are opening it through a local HTTP server rather than directly opening the HTML file from your file explorer.

If you are using the deployed version, open the Vercel link instead:

**https://puzzle-beta-eosin.vercel.app/**

### **The pinch gesture is not detected**

Make sure you have good lighting and that both hands are clearly visible to the camera. Bring your index finger and thumb closer together until the yellow indicator appears on the screen.

## **BROWSER COMPATIBILITY**

| Browser | Support |
|---|---|
| Chrome / Edge | Recommended |
| Firefox | Compatible |
| Safari | Limited — may require additional permissions |
| Mobile | Limited — desktop recommended |

## **LIVE DEMO**

🎮 **Try PuzzleCam directly in your browser:**

**https://puzzle-beta-eosin.vercel.app/**

No installation is required for the live version. Simply open the link, grant camera permission, and start playing.

## **LICENSE**

MIT — free to use, modify, and share.
