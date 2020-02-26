# WCST

This program implements Wisconsin Card Sorting (WCS) task in Java. 

WCS is a common neuropsychological test. Essentially, it presents several cards (usually 4), one of which matches a certain -given- card, in terms of either color, number or shape. 

In our implementation, a single query card displayed at the bottom of the GUI, and four other cards, i.e. options, are depicted over it. Any of these cards involve a single sort of shape (oeither circle, triange, square or star), with a different number (1-4) and a different color (red, green, blue, or yellow).

The game is based on the grounds of matching the query card to one of the options involving either the same shape, color, or number. Here, we call that property to be matched  simply  as the 'rule' of the game.  In addition,  a single set of cards (one query and four options) is termed as 'one round' of the game. 

The rule changes at random steps, i.e. after begin in effet for a random number of rounds. However, once it changes, the same rule persists for at least a minimum number rounds. The challenge of the game lies in the fact that there is no clue hinting the rule, or how long it will persist and the user needs to find it by trial and error. 

For determining the 'number of rounds of the current rule', we draw a random integer between 6 and 10. This means that any rule persists for at least 5 rounds but no more than 10 rounds. For choosing the rule, we draw a random integer between 1 and 3, where 'rule=1' means 'match the color',  'rule=2' means 'match the number', and 'rule=3' means 'match the shape'.

Upon quitting the game, a user log is saved as txt file in the current directory. There is a single line for each round of the game (or each attempt) with 14 columns. The columns involve the following information

01: Display time of the round in UNIX time stamp (msec)

02: Answer time in UNIX time stamp (msec)

03: Number of rounds for the current rule

04: Rule in effect (1 for shape, 2 for color, 3 for number)

05: 0 for fresh rule, 1 for continuing rule

06: Code for option card no.1 (integer code representing shape-color-number)

07: Code for option card no.2 (integer code representing shape-color-number)

08: Code for option card no.3 (integer code representing shape-color-number)

09: Code for option card no.4 (integer code representing shape-color-number)

10: Code for query card (integer code representing shape-color-number)

11: 0 for wrong answer, 1 for correct answer

12: Code for answer chosen (integer code representing the combination of shape-color-number)

13: Click location x-coordinate

14: Click location y-coordinate


