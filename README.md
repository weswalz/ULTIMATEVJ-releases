<p align="center">
  <img src="assets/uvj.png" width="200" alt="Ultimate VJ logo">
</p>

<h1 align="center">ULTIMATE VJ</h1>
<p align="center"><strong>Free VJ software. Native macOS. Built for Apple Silicon.</strong></p>
<p align="center">Trigger clips. Stack layers. Push pixels.</p>
<p align="center">
  <a href="https://github.com/weswalz/ULTIMATEVJ-releases/releases">Downloads</a> ·
  <a href="https://github.com/weswalz/homebrew-ultimatevj">Homebrew tap</a>
</p>

Ultimate VJ is a live visual performance app: a clip grid, layered compositing, ordered effect stacks, and procedural visuals you can actually play. Load your footage, build a set, map your controls, and send the composition to a clean output window.

Free to use. No account. No licence key.

## Install

**Apple Silicon · macOS 26 Tahoe or later · Homebrew**

```sh
brew update
brew tap weswalz/ultimatevj
brew install --cask weswalz/ultimatevj/ultimatevj
```

Prefer a ZIP? Open [Releases](https://github.com/weswalz/ULTIMATEVJ-releases/releases) and download the arm64 archive. Builds are Developer ID signed and Apple notarized. Each release includes a SHA-256 checksum.

## What you can do

- **Play a set from a clip matrix.** Organize media into banks and layers, trigger clips, adjust transport, and mix with layer opacity and a crossfader.
- **Build effect chains where they belong.** Clip, layer, group, and master scopes have ordered stacks. Transform a single source or process several layers together.
- **Generate visuals without a video file.** The current preview ships 28 built-in RenderWave shaders, including ZERO DAY, MEGALASERS, Liquid Chrome V2, Hypercube Tesseract V2, and Neural Constellation. Change their controls and save the look with the clip.
- **Put editable text in the composition.** Set the font, colour, alignment, and scale animation directly in a text clip.
- **Use physical controls.** MIDI Note and CC mapping, keyboard shortcuts, and Ableton Link tempo/bar-phase sync. Link does not sync transport start/stop.
- **Keep the controls off the output.** Run a clean fullscreen or windowed output while operating the console. Record the composition to silent video.
- **Inspect failures.** Optional runtime debugging records renderer timing, errors, and recent history. Export a local Markdown report when something goes wrong.

## Under the hood

The desktop UI uses **Swift, SwiftUI, and AppKit**. Rendering uses **Metal and Core Image**, with a compiled **RenderWave** runtime for procedural sources. Media decoding uses **FFmpeg**. Ableton Link handles tempo and bar phase.

Shader look thumbnails include saved source controls, effects, transforms, and opacity. Their GPU work runs off the UI thread, and stale results are discarded.

This repository distributes the packaged application. Application and RenderWave source code are not hosted here.

## Updates

In a Homebrew-managed installation, open **Settings → Updates → Check for Updates**. **Update and Restart** downloads through Homebrew, saves the current set for recovery, quits, installs, verifies the installed version and signature, and reopens the app with the saved set.

Or quit Ultimate VJ and run:

```sh
brew update
brew upgrade --cask weswalz/ultimatevj/ultimatevj
```

The [tap](https://github.com/weswalz/homebrew-ultimatevj/blob/main/Casks/ultimatevj.rb) specifies the version, archive URL, and checksum. The actual app download comes from this repository's release assets.

## Current status

**Venue evaluation preview.** Full playback soak, production workload performance, and physical venue output qualification are still pending. Update between shows.

There is no sustained frame-rate guarantee. Output is one selected physical display at a time. Syphon, NDI, and third-party FFGL/ISF plug-in hosting are not available. Recordings do not contain audio.

Read the notes attached to the build you install for its exact changes and limitations.
