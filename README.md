# Intersection-Of-Two-Matrices
Write a program that reads two char matrices (A[][] and B[][]) of the same order M * N and prints the third matrix C[][] which is filled with the intersecting elements of A and B, otherwise set the element to '*'. On the first two lines, you receive M and N, then on 2 * M lines N characters – the matrices elements.
package MultidimensionalArrays.Lab;

        import java.util.Scanner;

public class P03IntersectionOfTwoMatrices {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int rows = Integer.parseInt(scanner.nextLine());
        int cols = Integer.parseInt(scanner.nextLine());

        char[][] matrix1 = readMatrex(scanner, rows, cols);
        char[][] matrix2 = readMatrex(scanner, rows, cols);
        char[][] matrix3 = new char[rows][cols];

        for (int row = 0; row < rows; row++) {
            for (int col = 0; col < cols; col++) {
                char first = matrix1[row][col];
                char second = matrix2[row][col];
                char fillChar = first == second ? first : '*';
                matrix3[row][col] = fillChar;
            }

        }

        for (char[] chars : matrix3) {
            for (char aChar : chars) {
                System.out.print(aChar + " ");
            }
            System.out.println();
        }


    }

    private static char[][] readMatrex(Scanner scanner, int rows, int cols) {

        char[][] matrix = new char[rows][cols];

        for (int row = 0; row < rows; row++) {
            char[] elements = scanner.nextLine().replaceAll("\\s+", "").toCharArray();
            for (int col = 0; col < cols; col++) {
                matrix[row][col] = elements[col];
            }
        }
        return matrix;
    }
}
