# Chess

This chess game was made during the second week of App Academy. We followed a
very structured set of instructions to make this game. The goal of this project
was to teach us and practice with object oriented programming.

## Given Instructions

## Phase I: Pieces

There are many different kinds of pieces in chess, and each moves a specific way. Based on their moves, they can be placed in three categories:

Sliding pieces (Bishop/Rook/Queen)
Stepping pieces (Knight/King)
The pawn (do this last)
Start by writing a Piece parent class that contains the functionality common to all pieces. A key method of Piece is #moves, which should return an array of places a Piece can move to. Of course, every piece will move differently, so you can't write (implement) the #moves method of Piece without subclasses.

You can make subclasses for SlidingPiece and SteppingPiece. The SlidingPiece class can implement #moves, but it needs to know what directions a piece can move in (diagonal, horizontally/vertically, both). A subclass of SlidingPiece (Bishop/Rook/Queen) will need to implement a method #move_dirs, which SlidingPiece#moves will use.

Your Piece will need to (1) track its position and (2) hold a reference to the Board. The SlidingPiece in particular needs the Board so it knows to stop sliding when blocked by another piece. Don't allow a piece to move into a square already occuppied by the same color piece, or to move a sliding piece past a piece that blocks it.

For now, do not worry if a move would leave a player in check.

## Phase II: Board and Board#check(color)

Your Board class should hold a 2-dimensional array (an array of arrays). Each position in the board either holds a Piece, or nil if no piece is present there. Write code to setup the board on initialize.

The Board class should have a method #in_check?(color) that returns whether a player is in check. You can implement this by (1) finding the position of the king on the board then (2) seeing if any of the opposing pieces can move to that position.

The Board class should have a #move(start, end_pos) method. This should update the 2d grid and also the moved piece's position. You'll want to raise an exception if: (a) there is no piece at start or (b) the piece cannot move to end_pos.
