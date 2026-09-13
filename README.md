# PixelDraw 🎨

An interactive drawing system that turns physical marker movements into real-time artwork on a VGA monitor, built on the DE1-SoC FPGA board.

## How It Works
A webcam tracks a green marker using OpenCV HSV color-space filtering. The (x,y) coordinates are smoothed with an exponential moving average filter and streamed to a NIOS V processor over JTAG UART. The processor renders brush strokes onto a 320x240 VGA pixel buffer using Bresenham's line algorithm.

## Features
- Real-time marker tracking via webcam
- Variable brush sizes and rainbow color mode (hardware switch controlled)
- Shape detection — classifies strokes as lines, triangles, rectangles, or circles
- Etch-A-Sketch shake-to-clear gesture
- Undo buffer and cursor preview
- Save canvas to PC as a PNG image
- Decorative start screen

## Controls
| Input | Action |
|-------|--------|
| Spacebar | Toggle hover / draw mode |
| C | Clear canvas |
| S | Save canvas as PNG |
| ESC | Exit |
| Shake marker | Etch-A-Sketch clear |
| SW 7/8/9 | Color (blue/green/red) |
| SW 4/5/6 | Brush thickness |
| SW 3 | Rainbow mode |
| SW 2 | Symmetry mode |
| SW 1/0 | Fill / shape detection |
| KEY 0 | Commit drawing |
| KEY 1 | Undo |
| KEY 2 | Start |
| KEY 3 | Restart |

## Built With
- DE1-SoC FPGA (NIOS V processor)
- Python + OpenCV
- C (NIOS V firmware)
- VGA pixel buffer, JTAG UART

## Authors
Thenuk Fernando & Luca Mammone — ECE243 Final Project
