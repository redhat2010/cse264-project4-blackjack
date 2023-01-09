[![Work in Repl.it](https://classroom.github.com/assets/work-in-replit-14baed9a392b3a25080506f3b7b6d57f295ec2978f6f33ec97e36a161684cbe9.svg)](https://classroom.github.com/online_ide?assignment_repo_id=4631157&assignment_repo_type=AssignmentRepo)
# CSE264 Project 4: Making a Blackjack 21 Game using HTML/CSS/DOM
## Due: Tuesday, May 3, 2021 at 11:59 PM

In this assignment, you will use HTML, CSS, and JavaScript on the Frontend to create a playable blackjack 21 game.

All the code and packages you need is in this GitHub Classroom repo. Do not install any other packages (unless given permission by the instructor)

### REST API for Cards
You will use the [Deck of Card API](http://deckofcardsapi.com/) as a way to create a Deck of Cards, take cards out of that deck, and manage the hands of the player and the dealer. It is a very simple API that provides images of cards, values, creating hands and decks, etc. The listed webpage has all the details on using the API. 

### Blackjack Game
Blackjack is a simple card game between a dealer and a player. The goals is to get 21 points, without going over 21 (busting). A player wins if they:
* get 21 points on the player's first two cards (called a "blackjack" or "natural"), without a dealer blackjack;
* reach a final score higher than the dealer without exceeding 21
* let the dealer draw additional cards until their hand exceeds 21 ("busted").

The game goes as follows:
* Both the dealer and the player get two cards from the deck. The first card from the dealer is visible to the player, the second is not.
* The player goes first, and is allowed to ask for another card (Hit), or end their turn (Stay). If the player goes over 21, the game is over and the dealer wins.
* Next the dealer gets to go. They flip their hidden card and must get new cards until they have at least 17 points. Then they stop once they reach or go beyond 17. If they go over 21, the player wins.
* If neither the player nor dealer go over 21, then whoever has the most points wins. If they have the same points, the game is a tie.

Number cards are worth the number listed on the card. Face cards (King, Queen, Jack) are worth 10 points. And Aces are worth 11 or 1 points (use the value that ensures you do not go over 21).

### Frontend layout
Your page should have a green (card table green) background. At the top center will be the dealer's hand, on the bottom center will be the players hand. On the right side of the dealer and player's hand will be a number showing the current points for that hand (labeled as such). On the left side of the player's hand will be two buttons. One label Hit me, which will give a new card to the player and another labeled "Stay", which will finish the player's turn. Between the player and the dealer on the left will be the deck of card (face down).

### Game Flow
The flow of the game (events that need to take place) are as follows:
* The moment the main HTML page loads, a modal (screen overlay, see [here] (https://semantic-ui.com/modules/modal.html) as an example) appears asking if the player wishes to play. Under that there is a green button labeled "Deal" which will start the game.
* Once the button is pressed, the modal goes away, and the player and dealer are dealt two cards. The dealer is given cards first, with an animation showing the card moving face down towards the dealer's hand. The second card dealt to the dealer is animated with a flip to reveal the card to the player. Then the player gets their cards, animated to move from the deck to the players hand. They are then both flipped face up to reveal the cards to the player. The score for the cards is displayed to the right of both the player and the dealer.
* Player can now press the "Hit Me" button to get another card. This card will be animated to move from the deck to the player's hand. The score total will also update. If the score goes above 21, the dealer's hand is completely revealed, and the player loses (go to the game over modal as described later in this section. 
* Once the player presses the "stay" button. The dealer starts their turn. The dealer's hand is completely revealed (and the score by the dealer's hand is now updated). The dealer will continue to add cards until they have at least a score of 17. If the dealer goes over 21, the game is over and the player wins. (Go to the game over screen).
* If both the player and dealer do not go over 21, then who ever has the highest number wins. If they have the same score, it is a tie. (Go to the game over modal)
* The game over modal will display who won, and a button asking if the player wishes to play again. If this button is pressed. The cards, score, etc are cleared, the modal goes away. And the player can play the game again. 

### Other considerations
* You do not need to change any Node.js or Express code for this project. This is only a frontend project. Most of your code will be changes to the pug view file, and /public/javascripts/main.js file.
* You can write Raw HTML files instead if you wish. Just replace the pug files to an HTML file in the route.
* You should not need to reload the page once it loads for the first time. Everything should be done by using JavaScript to change and update the DOM. Whem the game restarts, you chould clear the DOM to the start state of the game, and continue from there. Do you reload the webpage to play another game.
* You can use Semantic UI, or any other CSS library is you wish. You can update these in the layout.pug file in the views directory. 
* Some features in Semantic UI will require jQuery and SemanticUI.js. You can import these from cdnjs [https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js](https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js)
* You should use regular JS to update and change the DOM, not jQuery. 
* You can use any feature in Semantic UI (or similar CSS Library) that you would find useful.
* You will need to find an image for the back of the cards of your deck. This can be anything you want. 
* A simple example of CSS Animations using movements can be found [here](https://jsfiddle.net/h7tuehmo/3/)
* More details on CSS animations can also be found [here](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations) 

### Install and Run
You must have node.js running on your machine. Once you have cloned this project you can run `npm install` to install all the packages for this project. Then running `npm run dev` will run the dev version of this code, which will run this project with nodemon. Nodemon auto-restarts the node server every time you make a change to a file. Very helpful when you are writing and testing code.



### Grading
* **75 Points** - Game plays correctly (with correct scores, win and loss states, etc)
* **10 Points** - Animations work as stated in this README. 
* **10 Points** - Game can continue and replay without reloading page.
* **5 Points** -  Code is well commented and easy to read/follow.

* If code doesn't run/compile you can get no more than a 65, although this score can be much lower. But please write comments and a README to explain what you were trying to do. 


