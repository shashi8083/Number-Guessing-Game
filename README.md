# Number-Guessing-Game
//Task2 of Java Programming


import java.util.Random;
import java.util.Scanner;

public class GuessTheNumber {
    public static void main(String[] args) {
        int minRange = 1;
        int maxRange = 100;
        int maxAttempts = 10;
        int score = 0;
        
        System.out.println("Welcome to Guess the Number!");
        System.out.println("I have generated a random number between " + minRange + " and " + maxRange + ".");
        System.out.println("You have " + maxAttempts + " attempts to guess the number. Let's begin!");
        
        Random random = new Random();
        int randomNumber = random.nextInt(maxRange - minRange + 1) + minRange;
        
        Scanner scanner = new Scanner(System.in);
        boolean guessedCorrectly = false;
        
        for (int attempt = 1; attempt <= maxAttempts; attempt++) {
            System.out.print("Attempt " + attempt + ": Enter your guess: ");
            int guess = scanner.nextInt();
            
            if (guess == randomNumber) {
                guessedCorrectly = true;
                score = maxAttempts - attempt + 1;
                break;
            } else if (guess < randomNumber) {
                System.out.println("Too low!");
            } else {
                System.out.println("Too high!");
            }
        }
        
        if (guessedCorrectly) {
            System.out.println("Congratulations! You guessed the number correctly in " + score + " attempts.");
        } else {
            System.out.println("Oops! You couldn't guess the number. The correct number was: " + randomNumber);
        }
        
        System.out.println("Thank you for playing Guess the Number!");
    }
}
