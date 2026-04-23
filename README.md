# Sliding Puzzle for Even G2

A classic sliding puzzle (3×3 / 4×4) for [Even Realities G2](https://www.evenrealities.com/) smart glasses.

> **Status:** v1.0.1 submitted to Even Hub — currently under review.

## Features

- **3×3** (8-puzzle) and **4×4** (15-puzzle) modes
- **Auto save & resume** — pick up exactly where you left off, even after exiting the app
- **Text-only rendering** — no image upload, fast single-frame updates on-glass
- **English / Japanese** supported

## Preview (on-glass)

Title (with a saved game):

```
★ Ｓｌｉｄｉｎｇ　Ｐｕｚｚｌｅ ★

［Ｃｏｎｔｉｎｕｅ　３ｘ３］
　３ｘ３
　４ｘ４
```

In-game:

```
Ｐｕｚｚｌｅ　Ｍｏｖｅｓ：１２

┃　１┃　②┃　３┃
┃　４┃　５┃　６┃
┃　７┃　８┃　　┃

Ｓｗｉｐｅ：Ｓｅｌｅｃｔ　Ｔａｐ：Ｍｏｖｅ
```

Solved:

```
Ｐｕｚｚｌｅ　★Ｓｏｌｖｅｄ！　１２

[board]

Ｔａｐ：Ｎｅｗ　　Ｓｗｉｐｅ：Ｔｉｔｌｅ
```

Circled digits (①–⑮) mark the currently focused tile.

## Controls

| Input | Action |
|---|---|
| Swipe up / down | Cycle focus through movable tiles |
| Tap | Move focused tile / start a new puzzle / select menu item |
| Double-tap | Exit confirmation dialog (Even Hub page-lifecycle convention) |

## Try it

- **Browser demo:** https://r-tkbyc.github.io/even-sliding-puzzle/
- **On-glass:** install via Even Hub once approved. Or sideload the bundled `sliding-puzzle.ehpk` through the dev portal.

## Development

### Requirements

- Node.js 20+
- `@evenrealities/evenhub-cli` 0.1.12 or later

### Build & run

```bash
npm install
npm run dev      # local browser dev at :5173
npm run build    # production build into dist/
npm run pack     # build + package into .ehpk
```

## Tech stack

- TypeScript + Vite (flat asset output, required by `evenhub-cli`)
- `@evenrealities/even_hub_sdk`
- Bridge + `localStorage` hybrid persistence (`bridge.setLocalStorage` / `bridge.getLocalStorage`)
- Fullwidth Unicode rendering technique (popularized by [dmi3-dev/eventrix](https://github.com/dmi3-dev/eventrix))

## Credits

- Persistence pattern referenced from [EvenSolitaire](https://github.com/even-realities/EvenSolitaire)
- Even G2 SDK notes aggregated by [nickustinov/even-g2-notes](https://github.com/nickustinov/even-g2-notes)

## Author

Built by **TakeMotions**.
