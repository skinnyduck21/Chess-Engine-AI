# Python Chess AI (Minimax + Alpha-Beta Pruning)

This is a fully functional **Chess Engine** written in Python using `pygame`. It features a custom AI opponent capable of looking ahead using the **Minimax algorithm** with **Alpha-Beta pruning** and advanced positional evaluation heuristics.

- **Engine:** Handles move generation, validation, castling, en passant, and checkmate/stalemate detection.
- **AI:** Minimax search (Depth 3) with Alpha-Beta pruning, transposition caching, and opening principles.
- **UI:** Graphical interface with move logging, valid move highlighting, and a live evaluation bar.
- **Cross-Platform:** Runs on Windows, macOS, and Linux (Ubuntu).

## Files
- `ChessMain.py` — The main driver (GUI, event loop, graphics)
- `ChessEngine.py` — The game state manager (rules, move generation)
- `SmartMoveFinder.py` — The AI logic (Minimax, heuristics, evaluation)
- `images/` — Folder containing piece assets (`wp.png`, `bK.png`, etc.)
- `requirements.txt` — List of dependencies (pygame)

## Installation & Setup

You can run this bot on any system (Windows, Mac, Ubuntu/Linux). It is recommended to use a **virtual environment**.

### 1. Prerequisite
Ensure you have **Python 3.8+** installed.

### 2. Create a Virtual Environment
This isolates the project dependencies from your system.

**Windows**
```powershell
# Open terminal in project folder
python -m venv venv
.\venv\Scripts\activate
```

**macOS / Ubuntu (Linux)**
```bash
# Open terminal in project folder
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

Once the virtual environment is active (you should see `(venv)` in your terminal), install `pygame` using the provided requirements file:
```bash
pip install -r requirements.txt
```

**requirements.txt** should contain:
```
pygame>=2.5.0
```

## How to Run

To start the game, execute:
```bash
python ChessMain.py
```

A window will open showing the chess board. You play as White (bottom), and the AI plays as Black (top).

## Controls
- **Mouse Left Click:** Select a piece / Make a move
- **Z:** Undo the last move (works for both player and AI)
- **R:** Reset the board to the starting position

## AI & Heuristics
The bot (`SmartMoveFinder.py`) uses several advanced techniques to produce strong gameplay.

### Algorithm
- **Minimax with Alpha-Beta Pruning** — efficient search tree pruning

### Piece-Square Tables
- Encourages knights to develop toward the center
- Incentivizes pawn advancement

### Opening Principles
- Penalizes early queen moves
- Rewards early development of minor pieces (Knights/Bishops)
- Rewards early castling

### Positional Evaluation
- **Bishop Pair:** bonus for retaining both bishops
- **Rook Structure:** rooks on open or semi-open files get rewarded
- **King Safety:** penalties for exposed kings; bonuses for pawn shields
- **Pawn Structure:** penalties for isolated or doubled pawns; bonuses for passed pawns

## Performance
- **Depth:** Default search depth is 3 (the AI looks 3 moves ahead)
- **Optimization:** Transposition table caching previously evaluated board states for faster and smarter decisions

## Features
- Full chess rules implementation including special moves (castling, en passant, pawn promotion)
- Checkmate and stalemate detection
- Move validation and legal move generation
- Visual feedback for valid moves
- Move history with undo functionality
- AI opponent with configurable difficulty

## Known Limitations
- No threefold repetition or fifty-move rule detection
- AI computation time may vary based on system performance
- Depth beyond 3 may cause noticeable delays on slower systems

## License
This project is open source and available for educational purposes.