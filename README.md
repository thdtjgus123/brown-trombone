# Brown Trombone

A browser-based fart synthesizer based on CompuFart.
Compiled from Cmajor DSP to WebAssembly and driven by the Web Audio API.
Also playable by MIDI keyboard and controller.

## What is this?

Nothing here is pre-recorded — every sound is computed live in your browser by a
real-time physical model of the human sphincter. The UI shows a cross-section that
reacts to the sound parameters in real time.

## Play

- Press and hold anywhere inside the dashed pad.
  - **Left / Right** = Strain (end constricts / relaxes)
  - **Down** = Cheek (whole canal clenches)
  - **Mouse wheel over the pad** = Pinch (sphincter centre tightens / opens)
- SPACE = hold to fart, F1–F5 = presets, Z / X = pitch bend
- Computer keyboard piano: white keys `Q W E R T Y U I O P`, black keys `1 2 3 4 5 6 7 8 9 0`
- MIDI: any note plays at that pitch, pitch bend passes through.
  Use the MIDI panel to LEARN CC knobs for Pinch / Strain / Cheek.
- Mouse wheel over the Pitch ADSR = envelope amount.

## Deploy

Fully static — host this folder anywhere that serves files over HTTPS:

```
# GitHub Pages / Netlify / Cloudflare Pages: upload the folder contents as-is
# local test:
python -m http.server 8799
```

No server, no build step, no accounts. Files:

```
index.html            app shell + UI + audio wiring
cmaj_CompuFart.js     CompuFart patch compiled to WebAssembly (Cmajor webaudio export)
cmaj_api/             Cmajor runtime helpers used by the patch module
```

## Credits

Engine: **CompuFart** © Audolon (alexmfink), MIT licence — https://github.com/alexmfink/compufart
Inspired by **Pink Trombone** by Neil Thapen — https://daffy.tv/pink-trombone/
Vibe-coded by **Cybersonus** (https://pearlorigin.org, https://x.com/cybersonus)