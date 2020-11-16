# hangman
Hangman Game
package project2;

import java.util.Scanner;

public class Project2 {
    public static void main(String[] args) {
        Scanner nameSurname = new Scanner(System.in);  //I wanted to login from user for his/her name and surname
        System.out.println("please enter the your name and surname: ");//and I printed screen
        String a = nameSurname.nextLine();
        System.out.println("welcome " + a);
        String[] values = {"Turkey", "Africa", "Afghanistan", "Azerbaijan", "Brazil",
                "Bulgaria", "China", "Cyprus", "Egypt", "England", "Finland",
                "France", "Georgia", "Greece", "Germany", "Holland", "Hungary",
                "india", "Japan", "Italy", "Mexico", "Poland", "Russia", "Spain",
                "Thailand"};//I created an array with 25 values
        int userdecision = 2;//user selects 2
        while (userdecision == 2) {//if the user selects 2, the loop will cycle continuously
        String secilen = "";//I created the math.random class to randomly take from the array.
        int b = (int) (Math.random() * (25));
        secilen = values[b];
        String low = secilen.toLowerCase();//I've converted the selected letter to small because java is case sensitive
        char[] tire = new char[low.length()];//I've created an array that takes hyphens until the selected letters.
        for (int i = 0; i < low.length(); i++) {//I have created a loop to the until characters of the selected word.
        tire[i] = '_';//we have put an underscore to discard the characters we get from outside.
        System.out.print(tire[i] + " ");//I printed the character on the screen
        }
       int remaining = low.length() * 2;//user created the right to have 2 times the right to experiment.
       System.out.println("Enter a letter. You have " + remaining + " left. Please enter (0) for guessing all word.");//I asked the user to enter words
       while (remaining > 0) {//I created loop until the trial right remains zero
       Scanner x = new Scanner(System.in);//I created a scanner object for user character entry
       String usercharacter = x.nextLine();
       String g = usercharacter.toLowerCase();//I've converted the selected letter to small because java is case sensitive
       if ("0".equals(g)) {//if the entered character is zero
                    System.out.println("Please enter your guess:");  //print user's forecast
                    Scanner input1 = new Scanner(System.in);
                    String guess = input1.nextLine();
       if (guess.equals(low))//if the guess is equal to the word
       {
       System.out.println(guess + " Correct! Please enter 2 for replay or enter 1 for exit.");//I printed screen
       userdecision = x.nextInt();
       if (userdecision == 1)//if the decision is 1, the program ends
       {
       System.exit(0);
       } else if (userdecision == 2) {//if decision 2
       break;//I ends the loop  and the program play again
       }
       } else//if not
       {
       System.out.println("Your answer is wrong.\n Please enter 2 for replay or enter 1 for exit");//I gave the user the option to play again
       userdecision = x.nextInt();
       }
       }
       int d = 0;//I have created and to increase and decrease the right
       for (int i = 0; i < low.length(); i++)//I have created a loop to the until characters of the selected word.
       {
       if (g.charAt(0) == low.charAt(i))//if the entered character matches a letter of the selected word
       {
        System.out.print(tire[i] = g.charAt(0)); //I assigned it a hyphen
        d++;
        } else {
       System.out.print(tire[i] + " ");//if not print the character
        }
        }
                    if (d == 0){ //if d=0
                      remaining--;//rights diminished and I printed screen
                      System.out.println(" Enter a letter. You have " + remaining + " left. Please enter (0) for guessing all word.");
                    }
                    else{//if not right are not diminished I printed screen
                      System.out.println(" Enter a letter. You have " + remaining + " left. Please enter (0) for guessing all word.");
                    }
                    if (remaining == 0){ //if if the right ends
                      System.out.println("Please enter 2 for replay or enter 1 for exit");//will it come out or will it play again? I wrote.
                      userdecision = x.nextInt();
                    if (userdecision == 1){//if user decision is 1
                        System.exit(0);//the program ends
                    }
                }
            }
        }
    }

}
