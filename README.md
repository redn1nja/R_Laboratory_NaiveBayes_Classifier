# R_Laboratory_NaiveBayes_Classifier

---------------------------------------------------------------------------------------------------------------------------------------------------

#### Team: Seryvko Ostap, Kostiuk Rostyslav, Sitarchuk Mariia.

---------------------------------------------------------------------------------------------------------------------------------------------------

## Main idea

Purpose of the method is to detect if the message is ham or spam.

To do this we can use Bayes formula:

P ( ham | message ) = P ( message | ham ) * P ( ham ) / P ( message )

But since we’re just trying to find our which probability is bigger ( ham or spam ) we can discard the divisor and just compare:

P ( message | ham ) * P ( ham )  ?  P ( message | spam ) * P ( spam )

And now we can calculate those probabilities.

## The general algorithm which is used is:

    1) Calculate the number of appearance of each word in ham and spam messages
    
    2) Calculate the probability of using each word in ham and spam messages
(conditional probability of using the word given that this message is ham/spam message)

We use Laplace smoothing (adding one to every count), so it wouldn’t be zero and we would receive useful information.

    3) After calculating each word’s probabilities, we multiply the results and compare the ham and spam probabilities of all message.
(if ham > spam, it is more likely that this message is ham and vice versa)

---------------------------------------------------------------------------------------------------------------------------------------------------

## Main functions:

    calculate_probabilies_ham
function where the probability that a certain word is a  ham word is calculated

    calculate_probabilies_spam
function where the probability that a certain word is a  ham word is calculated

    predict
function where the message is splited, transferred to calculate probabilities of each word and then results are multiplied and it is determined whether the message is spam or not

    score
function where the solution is compared with a test version

---------------------------------------------------------------------------------------------------------------------------------------------------

## Pros and cons of the method:

##### Pros of the method:

    1) The precision of the method = 72%
    2) The recal of the method = 86%
    3) The F1 score of the method = 0.78 (Good)

##### Cons of the method:

    1) Relatively low speed of testing (10 messages/min), but it depends on the power of a machine
    2) ...

---------------------------------------------------------------------------------------------------------------------------------------------------

### The method takes:
- a csv file (train.csv) to calculate probabilities of each word in each message in it
- a csv file (test.csv) to test the accuracy of the work
- a txt file (stop_words.txt) with usual english stop words to clean messages for proper work

---------------------------------------------------------------------------------------------------------------------------------------------------

## Examples of work:

![Screenshot from 2022-10-18 23-59-05](https://user-images.githubusercontent.com/91615985/196543800-522fe235-e43d-4ccd-b362-031e0170409a.png)
![Screenshot from 2022-10-18 23-59-16](https://user-images.githubusercontent.com/91615985/196543831-85cd930c-e750-4f8e-99c1-f21daebaf6ef.png)

---------------------------------------------------------------------------------------------------------------------------------------------------
