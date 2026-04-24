# Face Recognition Pro

A best-in-class **browser-based face recognition app** — no servers, no installs, 100% client-side.

## Features

- **SSD MobileNet** face detector (high accuracy, better than TinyFaceDetector)
- **FaceNet 128-dim descriptors** — 99.38% LFW accuracy
- **68-point facial landmarks** with mesh overlay
- **Real-time liveness detection** — EAR blink counting (2 blinks = verified live)
- **Head pose estimation** — yaw from landmark geometry
- **Face quality scoring** — size + centering + confidence composite
- **Face alignment** — rotates to canonical pose before embedding
- **Multi-sample registration** — 3–5 samples averaged per person
- **Expression analysis** — 7 emotions with animated bars
- **Age + gender prediction**
- **Import/Export** face database as JSON (localStorage persisted)
- **Snap export** — PNG with overlays
- **Dark / Light theme** toggle
- **Fully responsive** — 3-panel desktop, stacked mobile

## Tech Stack

| Library | Purpose |
|---------|---------|
| [@vladmandic/face-api](https://github.com/vladmandic/face-api) | Face detection + recognition (maintained TF.js fork) |
| TensorFlow.js (bundled) | WebGL inference backend |
| GSAP 3.12.5 | UI animations |

## Usage

1. Open `index.html` in any modern browser
2. Allow camera access
3. Click **Start Camera**
4. **Register**: Enter a name → Capture 3–5 samples → Register
5. **Identify**: Registered faces are matched in real-time
6. Export/Import your face database as JSON

## How It Works

```
Camera Frame → SSD MobileNet Detection → 68-pt Landmarks
             → Face Alignment (eye geometry rotation)
             → FaceNet 128-dim Embedding
             → FaceMatcher (cosine distance)
             → Identity + Confidence + Liveness
```

## Live Demo

Deployed via Perplexity Computer.

## Local Development

No build step needed. Just serve the directory:

```bash
npx serve . -l 3000
```

## License

MIT
