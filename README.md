# RC AI A1109

A browser-based 3D racing game. The GitHub Pages entry point is `index.html`.

## Publish with GitHub Pages

1. Upload `index.html` and this `README.md` to the root of your GitHub repository.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select branch `main` and folder `/ (root)`, then save.
5. Open the Pages URL shown by GitHub.

No Python installation is required for GitHub Pages or for players visiting the published site.

## Test locally (optional)

From the folder containing `index.html`, run:

```bash
py -m http.server 8000
```

Then open `http://localhost:8000`.

## Multiplayer

### Online Multiplayer (main multiplayer mode)

- One player selects **Online Multiplayer → Create room**.
- The host chooses a lap count from 1 to 8 and shares the six-character room code.
- Friends choose **Online Multiplayer**, enter the code, and select **Join room**.
- The host can start once at least one other racer has joined. Up to four racers can play.
- Each online player drives with **W A S D**, **Shift** for boost, and **Space** for handbrake.
- The host controls **Play Again** after the online results screen.

Online networking uses PeerJS and WebRTC data channels. PeerJS Cloud is used for signaling by default; game-state data is sent peer-to-peer after the connection is established. Internet access is required. PeerJS Cloud is a shared service, so room-ID collisions or network/firewall restrictions can occasionally prevent a connection. If a room cannot be created, create a new one; if a friend cannot join, check the code and try again.

### Keyboard Shortcuts Mode

This is a separate offline split-screen mode for multiple people sharing one computer. Choose **Keyboard shortcuts mode · Same PC** in the multiplayer panel. The host selects 2–4 players and 1–8 laps.

- Player 1: W A S D, Shift boost, Space handbrake
- Player 2: Arrow keys, / boost, . handbrake
- Player 3: I J K L, U boost, O handbrake
- Player 4: Numpad 8 4 5 6, Numpad 0 boost, Numpad . handbrake

## Career saves

Career progress, stars, cars, and unopened chests are saved in the browser's local storage for that browser and site origin. Clearing site data or changing browsers/devices can remove or separate that save.

## External libraries

- Three.js 0.160.0 for 3D rendering.
- PeerJS 1.5.5 for online peer-to-peer connections.

Both are loaded from jsDelivr at runtime, so the game needs an internet connection.
