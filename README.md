# Sudoku Solver with Backtracking

A Python implementation of a Sudoku solver using the backtracking algorithm, with real-time visualization of the solving process.

## 🎯 Key Features

- Solves 9x9 Sudoku puzzles using backtracking
- Real-time visualization of the solving process
- Solution verification against known correct solutions
- Support for multiple pre-defined puzzles
- Clean and organized terminal output

## 🔍 About the Algorithm

This solver implements the **backtracking algorithm**, which is a fundamental technique in constraint satisfaction problems. Here's how it works:

1. Find an empty cell in the Sudoku grid
2. Try placing numbers 1-9 in that cell
3. Check if the placed number is valid according to Sudoku rules
4. If valid, recursively try to fill the rest of the grid
5. If placing a number leads to an invalid solution, backtrack and try the next number
6. If no number works, backtrack to the previous cell

The power of backtracking lies in its ability to:
- Systematically explore all possible solutions
- Efficiently prune invalid paths early
- Guarantee finding a solution if one exists
- Handle complex constraint satisfaction problems

## 📊 Complexity Analysis

### Time Complexity
- **Worst Case**: O(9^(n*n))
  - For a 9x9 grid, we have n=9
  - In the worst case, we need to try all numbers (1-9) for each cell
  - This happens when we need to backtrack frequently
  - Real puzzles usually perform much better due to pruning

- **Best Case**: O(n*n)
  - When the puzzle is already mostly filled
  - Only need to validate the solution
  - n represents the board dimension (9 for standard Sudoku)

### Space Complexity
- **Stack Space**: O(n*n)
  - Due to recursion depth
  - Maximum recursion depth equals the number of empty cells
  - For 9x9 grid, worst case is 81 recursive calls

- **Auxiliary Space**: O(1)
  - We modify the board in-place
  - No additional data structures needed
  - Constant extra space for variables

### Performance Optimization Tips
1. Start with cells having fewer possible choices
2. Use constraint propagation techniques
3. Implement forward checking
4. Cache validation results when possible

## 🚀 Usage

1. Clone the repository
2. Run the solver:
```bash
python sudoku_solver.py
```

The program will:
- Display the initial puzzle
- Wait for user input
- Show the solving process in real-time
- Verify the solution against known correct answers

## 📁 File Structure

- `sudoku_solver.py`: Main solver implementation
- `puzzles.py`: Collection of Sudoku puzzles
- `solutions.py`: Verified solutions for validation

## 🔧 Functions

- `solve(board)`: Main recursive solving function using backtracking
- `is_valid(board, num, pos)`: Validates number placement
- `print_sudoku(board)`: Formats and displays the Sudoku grid
- `is_empty(board)`: Finds empty cells in the grid

## 💡 Why Backtracking?

Backtracking is particularly effective for Sudoku because:
1. It systematically tries all possibilities
2. Immediately abandons invalid paths
3. Uses minimal memory compared to other approaches
4. Naturally handles the constraint-based nature of Sudoku

## 🎯 Performance Considerations

While the worst-case time complexity might seem high, the actual performance is usually much better because:
- Many invalid paths are pruned early
- Real Sudoku puzzles have unique solutions
- The constraint checking reduces the search space
- Well-designed puzzles often have strategic starting points

## 🤝 Contributing

Feel free to:
- Submit bug reports
- Propose new features
- Create pull requests

## 📝 License

This project is open source and available under the MIT License.
