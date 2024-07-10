import java.util.*;
public class TicTacToe{
    private char[][] board;
    private char currentPlayer;
    public TicTacToe() {
        this.board = new char[3][3];
        this.currentPlayer = 'X';
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                board[i][j] = '-';
            }
        }
    }
    public void play() {
        Scanner sc= new Scanner(System.in);
        while (true) {
            printBoard();
            System.out.print("Enter row (0-2): ");
            int row = sc.nextInt();
            System.out.print("Enter column (0-2): ");
            int col = sc.nextInt();
            if (isValidMove(row, col)) {
                makeMove(row, col);
                if (hasWon()) {
                    printBoard();
                    System.out.println("Player " + currentPlayer + " wins!");
                    break;
                }
                switchPlayer();
            } else {
                System.out.println("Invalid move. Try again!");
            }
        }
    }

    private void printBoard() {
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                System.out.print(board[i][j] + " ");
            }
            System.out.println();
        }
    }

    private boolean isValidMove(int row, int col) {
        return row >= 0 && row < 3 && col >= 0 && col < 3 && board[row][col] == '-';
    }

    private void makeMove(int row, int col) {
        board[row][col] = currentPlayer;
    }

    private boolean hasWon() {
        for (int i = 0; i < 3; i++) {
            if (board[i][0] == currentPlayer && board[i][1] == currentPlayer && board[i][2] == currentPlayer) {
                return true;
            }
        }
        for (int i = 0; i < 3; i++) {
            if (board[0][i] == currentPlayer && board[1][i] == currentPlayer && board[2][i] == currentPlayer) {
                return true;
            }
        }
        if ((board[0][0] == currentPlayer && board[1][1] == currentPlayer && board[2][2] == currentPlayer) ||
                (board[0][2] == currentPlayer && board[1][1] == currentPlayer && board[2][0] == currentPlayer)) {
            return true;
        }
        return false;
    }
    private void switchPlayer() {
        currentPlayer = (currentPlayer == 'X')? 'O' : 'X';
    }

    public static void main(String[] args) {
        TicTacToe game = new TicTacToe();
        game.play();
    }
}
