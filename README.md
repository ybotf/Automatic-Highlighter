# Automatic-Highlighter

Program that generates a sequence of colour that corresponds to each work (highlighted words) based on some criteria.

## Part A
For the first automatic highlighter program,implement a C program that reads as input:
- A sentence. This is just a sequence of words split by whitespace, with no punctuation marks.
- A set of word tables. The set will only contain tables for words that appear in the sentence. Assume there are only 4 colours and they are represented as integers from 0 to 3: 0 is "no colour", 1 is "green", 2 is "yellow" and 3 is "blue".

![Screenshot from 2023-05-04 16-04-18](https://github.com/ybotf/Automatic-Highlighter/assets/56858161/f1922860-be74-4f42-afd8-441a8207c22d)

Then, it generates as the output:
- A sequence of colours, one per word. This should be a sequence of integer values, where each integer represent a colour, as above.

The output sequence of colours should follow an optimisation criterion: it is the sequence with the highest total score. For Part A, the total score is the sum of individual scores per word.


The goal is to the maximise the score given a sequence of words/colours The second term then simplifies this to maximise the score for each individual word/colour.


## Part B
Part B introduces an extra colour transition table. This table gives scores for colours given the previous colour. An example:

![Screenshot from 2023-05-04 16-51-16](https://github.com/ybotf/Automatic-Highlighter/assets/56858161/abed5cc1-bba3-449c-bc54-919b65bf822c)

In this example table, if the previous word is highlighted in blue and the current word is also blue (as in the "brute force" example above), this transition gives a score of 10.

For the second automatic highlighter, enhance the code in Part A. The input is now:

- A sentence. As in Part A.
- A set of word tables. As in Part A.
- A colour transition table. Each entry in this table has two integers, corresponding to previous colour and colour, and a score. Integers represents colours, as in Part A.

The output is the same as Part A: a sequence of integers that gives the optimal highlighting. However, the criterion of highest total score now needs to sum the colour transition scores as well. The program should follow a greedy approach: for every word from left to right, select the colour based on the maximum sum of two scores: the one from the word table and the one for the transition table.

## Part E
Use a dynamic programming solution. Where: 

- For the first word, there is no transition, so pick the best colour according to the word table.
- For the second word and afterwards, there are two options:
- Option 1: the best sequence includes the best colour for the previous word.
- Option 2: the best sequence does not include the best colour for the previous word.

Write a C program that implements the dynamic programming approach to get the best score for a sequence of colours. Inputs are the same as Part B, Output should be a single number containing the best score.

## Part F 
Modify the C program from Part E to get the best sequence of colours. Inputs and Outputs are the same as Part B. For this part, assume only 4 colours, as in Parts A and B.
