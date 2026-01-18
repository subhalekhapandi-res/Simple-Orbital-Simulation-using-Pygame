# Orb Viz (pygame) — Solar System Visualization

A small orbital mechanics visualization implemented in a Jupyter notebook using pygame. The notebook `orb_viz_pygame.ipynb` simulates a simplified Solar System (Sun + planets) using Newtonian gravity and draws the planetary orbits in real time with zoom support.

## Features
- Simulates Sun, Earth, Mars, Mercury, Venus, Jupiter, Saturn, Uranus, Neptune
- Newtonian gravitational attraction between bodies
- Orbit trails drawn as lines
- Zoom in/out using the mouse wheel
- Simple HUD showing "Solar System" title and per-planet distance to Sun

## Files
- `orb_viz_pygame.ipynb` — Jupyter notebook containing the simulation code.

## Requirements
- Python 3.8+
- pygame (tested with pygame 2.x)
- A display (pygame opens a window).

## Running

Option A — Run in Jupyter
1. Open the notebook in JupyterLab / Jupyter Notebook.
2. Run the cells from top to bottom. The final cell calls `main()` which launches a pygame window.

Note: Running pygame windows from within some notebook environments can be problematic depending on how the environment handles GUI windows. Running the notebook locally is recommended.

Option B — Convert to a script and run
1. Extract the Python cells and save them to `orb_viz_pygame.py` (make sure the `main()` call exists at the bottom).
2. Run:
```bash
python orb_viz_pygame.py
```

## Controls
- Mouse wheel up: Zoom in
- Mouse wheel down: Zoom out
- Window close button: Quit the simulation

Zoom limits and step are defined in the notebook:
- ZOOM_STEP (default: 0.1)
- MIN_ZOOM (default: 0.2)
- MAX_ZOOM (default: 5.0)

## Key parameters you may want to tweak
- Planet sizes and masses are defined when creating each `Planet` instance in `main()`.
- `Planet.SCALE` controls how real distances (meters) map to screen pixels.
- `Planet.TIMESTEP` controls the simulation timestep (seconds per simulation step). Default is one day (3600*24). Reducing TIMESTEP improves integration accuracy but slows down how quickly orbits evolve on-screen.
- `WIDTH` / `HEIGHT` control window size.
- Adjust `clock.tick(60)` to change render frame cap.

## Implementation notes
- Positions and velocities are stored in SI units (meters & m/s).
- The gravitational constant G and astronomical unit (AU) are defined in the `Planet` class.
- Orbits are recorded as lists of (x, y) and drawn using `pygame.draw.lines`.
- Distances to Sun are rendered in kilometers (rounded).

## License
This project is provided as-is for educational/demonstration purposes. Feel free to reuse or adapt the code.

