# Bee-Bot Simulator

An educational programming game that teaches sequencing and logic by having children program a robot bee to visit numbered targets in order on a grid.

## Files

| File | Description |
|------|-------------|
| `index.html` | Main game with 30 levels (Easy/Medium/Hard) |
| `beebotdragable.html` | Sandbox mode with configurable spider count |
| `config.json` | Level definitions (targets, spiders per level) |
| `gameconfig.json` | Game settings (grid size, initial position, drag-and-drop) |
| `beebot.png` | Bee-Bot sprite |
| `spider.png` | Spider obstacle sprite |
| `flower.png` | Target image for sandbox mode |
| `images/img1-7.png` | Target images used in levels |

## How to Play

1. Open `index.html` in a web browser
2. Use the arrow buttons to add movement commands to the program
3. Press **Go!** to execute the program
4. Guide the Bee-Bot to visit all numbered targets **in order** (1, 2, 3...)

## Controls

### On-Screen Buttons
| Button | Function |
|--------|----------|
| Forward (↑) | Move forward one cell |
| Backward (↓) | Move backward one cell |
| Left (←) | Turn 90° left |
| Right (→) | Turn 90° right |
| Go! | Execute the program |
| Home | Return Bee-Bot to start position |
| Clear | Remove all commands |
| Pen | Toggle pen to draw path |
| Next | Skip to next level |

### Keyboard Shortcuts
| Key | Function |
|-----|----------|
| Arrow Up | Add forward command |
| Arrow Down | Add backward command |
| Arrow Left | Add left turn command |
| Arrow Right | Add right turn command |
| Enter | Execute program |
| Escape | Clear program |
| H | Return to home position |
| P | Toggle pen |

## Game Modes

### Level Mode (`index.html`)
- 30 levels with increasing difficulty
- **Easy** (1-10): 2 targets, 1 spider
- **Medium** (11-20): 3 targets, 3 spiders
- **Hard** (21-30): 4 targets, 5 spiders
- Visit targets in numbered order to advance

### Sandbox Mode (`beebotdragable.html`)
- Single level with configurable spider count (0-10)
- Drag-and-drop to reposition Bee-Bot and target
- Spider collision enabled

## Drag and Drop

Both modes support drag-and-drop when enabled in `gameconfig.json`:
- Drag the Bee-Bot to reposition it
- Drag targets to new locations
- Items cannot be placed on occupied cells

## Configuration

### gameconfig.json
```json
{
  "settings": {
    "backgroundColor": "#e2e8f0",
    "initialBeeBotPosition": { "x": 2, "y": 0, "dir": 0 },
    "gridSize": 4,
    "enableDragAndDrop": true
  }
}
```

- `backgroundColor`: Canvas background color
- `initialBeeBotPosition`: Starting position (x, y) and direction (0=N, 90=E, 180=S, 270=W)
- `gridSize`: Number of cells per row/column
- `enableDragAndDrop`: Allow repositioning via drag-and-drop

### config.json
Defines levels with targets and spider count:
```json
{
  "levels": [
    {
      "level": 1,
      "difficulty": "Easy",
      "spiders": 1,
      "targets": ["images/img1.png", "images/img2.png"]
    }
  ]
}
```

## Technical Details

- Pure HTML/CSS/JavaScript (no build tools required)
- 3-layer canvas system: background, path, bot rendering
- Smooth animation with configurable speed
- Responsive design with fullscreen support
- Touch and mouse input support

## Browser Support

- Chrome/Edge
- Firefox
- Safari
- Mobile browsers (touch support)
