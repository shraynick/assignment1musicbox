# Assignment One – “Music Box”

A browser-based generative step sequencer built with [Tone.js]. It plays a short tune on demand, lets you explore scales, octaves, groove, sound design, and “interandom” variations. This build includes a polished UI, theme toggle, preset save/load, and one-click audio recording.

> Open the HTML with VS Code’s **Live Server**. Click **Play** to unlock audio. Chrome recommended.

---

## ✨ Highlights

- **Generative music box** (16-step loop) for melody + bass + hats
- **Scales** (major/minor, modes, pentatonic, blues, whole-tone, chromatic)
- **Octaves 2–6**, plus **Transpose** (±12 semitones)
- **Interandom** variations with **seeded randomness** (reproducible)
- **Timing feel**: Swing, Humanize, and accented downbeats
- **Sound design**: Low-pass Filter, Reverb, safe Master Volume
- **Theme toggle** (Light/Dark)
- **Pattern selector** (Motif, Arp Up/Down, Up-Down, Random Walk)
- **Preset Save/Load** (JSON copy/paste)
- **Record to WAV** (download from the page)
- **Ultra-stable**: one `Tone.Loop('16n')`, no BPM ramps, no time-synced FX

---

## 📂 Project Structure
Everything is self-contained in the HTML (no external local JS/CSS files). Tone.js is loaded via CDN.

---

## 🚀 Getting Started

1. **Open in VS Code**  
   File → Open Folder… → select the `Assignment One` folder.

2. **Launch with Live Server**  
   - Install the **Live Server** extension (if not already).
   - Right-click `Assignment One – Music Box.html` → **Open with Live Server**.
   - Your browser opens to `http://localhost:PORT/…`.

3. **Play**  
   Click **Play** to unlock audio and start the tune. Use **Pause** / **Stop** as needed.  
   Tip: Press **Spacebar** to toggle Play/Pause.

> Note: Live Server may create `.vscode/settings.json` with a port number; that’s normal and harmless.

---

## 🎹 Musical Controls

- **BPM**: 60–160  
- **Scale**: C Major, A Minor, Harmonic/Melodic Minor, Dorian, Phrygian, Lydian, Mixolydian, Locrian, C/A pentatonics, E Blues, Whole-Tone, Chromatic  
  - **Notes label** shows the actual set being used.
- **Octave**: 2–6  
- **Transpose**: ±12 semitones (shifts everything up/down)

### Patterns
- **Motif** (default)
- **Arp Up**
- **Arp Down**
- **Arp Up-Down**
- **Random Walk**

### Interandom (Generative Variation)
- **Interandom** toggle: nudges some steps/rests each run
- **Seed**: numeric; same seed → same variation
- **New Variation**: generates a new seed, instantly updating the pattern

### Playback Length / Looping
- **Loop** on: repeats indefinitely  
- **Loop** off: auto-stops after **N measures** (set with *Length*)

---

## 🥁 Feel & Sound Design

- **Swing**: offsets even 8ths for groove (0–100)  
- **Humanize**: subtle timing jitter  
- **Accents**: downbeats (0,4,8,12) hit a bit harder  
- **Master Volume**: overall level (capped for safety)  
- **Filter Cutoff**: 200–8k Hz (darker ↔ brighter)  
- **Reverb Wet**: 0–100%

---

## 🎨 UI & Quality-of-Life

- **Theme**: 🌗 button toggles Light/Dark
- **Now Playing**: mini progress bar across the measure
- **Visual Step Tracer**: highlights the current step in melody & bass rows
- **Spacebar**: play/pause shortcut

---

## 💾 Presets

Save your current configuration to JSON and reload it later.

- **Save Preset**: Opens a modal with your current settings (copy the JSON).
- **Load Preset**:  
  1) Click **Load Preset** to open the modal,  
  2) Paste JSON,  
  3) Click **Load Preset** again to apply.

Preset fields: bpm, scale, octave, transpose, loop, length, interandom, seed, swing, humanize, pattern, masterVol, reverbWet, cutoff, theme.

---

## ⏺️ Recording

- Click **⏺️ Record** to start capturing audio from the app.  
- Click **⏹️ Stop Rec** to finish; a **Download WAV** link appears.  
- Uses the browser’s **MediaRecorder** via a split from the output bus.

> Recording support varies by browser. Chrome desktop works well. If you see a recording error, try a different browser or disable extensions.

---

## 🧠 How It Works (Brief)

- A single **`Tone.Loop('16n')`** advances a 16-step bar for melody/bass/hats.  
- Melody notes come from the selected **scale** and **octave**; **transpose** shifts by semitones.  
- **Interandom + seed** produces small, reproducible mutations to the pattern.  
- **No parameter ramps** or note-synced FX (like synced delays) are used → avoids floating-point edge cases (e.g., negative times).

---

## 🧪 Troubleshooting

- **No sound until I click**: Browsers block audio until a user gesture—click **Play** once.  
- **Nothing plays**: Use **Chrome** and **Live Server** instead of `file://`.  
- **Play/Pause/Stop confusion**:  
  - **Play** starts fresh if stopped, resumes if paused.  
  - **Pause** toggles run/pause.  
  - **Stop** hard-stops and resets.  
- **Recording not working**: Some environments block MediaRecorder (e.g., strict cross-origin rules). Try Chrome desktop; disable extensions.  
- **`.vscode/settings.json` appeared**: Normal—Live Server writes its port here. It doesn’t affect the app.

---

## 📝 Submission Checklist

- [ ] Folder is named `Assignment One` (or your course format)  
- [ ] Contains:
  - [ ] `Assignment One – Music Box.html`
  - [ ] `README.md`
- [ ] Tested via **Live Server** (Chrome)  
- [ ] Clicked **Play** → audio starts  
- [ ] Verified **Loop off** + **Length** auto-stops  
- [ ] (Optional) Saved a **Preset** JSON for grading  
- [ ] (Optional) Exported a short **WAV** recording

---

## 🙋 Reflection (example you can adapt)

- **Design**: I optimized stability (one `Tone.Loop`), safety (capped gain), and clarity (step tracer, scale labels).  
- **Enhancements**: Theme toggle, presets, recording, arpeggio patterns, transpose.  
- **Challenges**: Browser audio unlock and Tone timing edge cases; solved by avoiding BPM ramps and time-synced FX.  
- **Learning**: Mapping scales to pitches, seeded randomness, balancing synthesis with safe gain staging, and building an approachable musical UI.

---

Built with ❤️ using [Tone.js].  
[Tone.js]: https://tonejs.github.io/