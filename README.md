# Neural-Network-Proc-Codes-with-Word2Vec
Word2Vec for Procedure Codes

For my master's degree I worked with a dual healthcare provider and insurance provider to solve a issue about populations within their
and primary care facilities. We wanted to make a predictive model to predict what people would be within the various populations from one
year to the next. 

To accomplish this, I used procedure codes from both the insurance and medical provider side of their business to make the prediction. The
assumption was that there was a relationship between care recieved and an individuals election to move between groups. Procedure codes share
some characteristics with words (contextual relationships, subtle differences between one code and another, and a vast quantity of different
procedure codes) so I decided to use the word2vec model to create an understanding of the procedure codes. I ended up with 5MM plus procedure
codes so there was sufficient codes to train a model. More would have been better, but as a proof of concept in applying the word2vec logic to
to procedure codes this worked well.

Once I created a word2vec matrix, I used the embeddings, patient/member visits and procedure codes, and other individual demographic information 
to predict what healthcare group they'd be in the following year. I used a unique model insofar as I used a hybrid neural network as my machine
learning algorithm. I ran the procedure codes through an RNN and the demographic information through a 'static' ANN. Then I merged those two 
neural networks together and passed the info through a final 'static' ANN layer to make predictions. This proved to be an effective way to 
combine sequential information and static information. I used Keras for the neural networks with a tensorflow backend and used gensim to train 
my word2vec procedure code embeddings. 

The output of this model was good as the predictions were pretty good, but I don't think that this is really the best use of 'procedure code
embeddings.' I used it this was to solve the problem given to me but there would likely be many other more interesting dependent variables on which
to predict with this info like this. Additionally, I used procedure codes since I had access to these codes, but icd codes would also work 
with the word embedding approach and likely offer untapped insights into the healthcare field. ICD codes would require many more millions
of rows with which to train the model but the data is out there and could tells us a lot about predicting disease or other health conditions. 


My apologies for not cleaning up the code more. I am in part putting this data up as a resource for myself in the even I need to go back and use some of the snippets I wrote for this exercise. If anyone has questions about my logic, thoughts, approach, or anything else do not hesitate to reach out. 
