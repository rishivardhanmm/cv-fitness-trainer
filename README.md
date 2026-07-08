# PushCoach 🏋️

A single-page, browser-only AI push-up coach. It uses your webcam + Google MediaPipe **Pose Landmarker** to count reps in real time, and speaks to you like an energetic gym coach via the Web Speech API. Everything runs client-side — no backend, no login, no API keys — and works offline after the first load (once the CDN model is cached).

## Run it
Because cameras require a **secure context**, you can't just double-click the file (`file://` won't grant camera access). Serve it over `http://localhost` (treated as secure) or HTTPS. From this folder run any static server, e.g. `python -m http.server 8000` (or `npx serve`), then open **http://localhost:8000**. Click **Enable camera**, allow the permission prompt, then hit **Start**. Tune the workout by editing the constants at the top of the `<script>` in [index.html](index.html) (`TARGET_REPS`, `REST_SECONDS`, `UP_ANGLE`, `DOWN_ANGLE`, etc.).

## Camera position
Prop your phone or laptop **to the side** so the camera sees your **full body in profile** (head-to-feet, side-on) in good, even light — that clean side view is what lets it read your elbow angle and count accurately. If it loses you, the on-screen "I can't see you" warning appears and counting pauses until you're back in frame.
