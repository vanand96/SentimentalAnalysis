# SENTIMENT ANALYSIS ON VACCINATION TWEETS
* [Github](https://github.com/vanand96/SentimentalAnalysis)
    * [Jupyter Notebook](https://github.com/vanand96/SentimentalAnalysis/blob/master/SentimentAnalysis.ipynb)
    * [Tweets Streaming](https://github.com/vanand96/SentimentalAnalysis/blob/master/TweetRead.py)
    * [Dataset](https://github.com/vanand96/SentimentalAnalysis/blob/master/vaccination2.csv)
    * [Tweets Streaming screen capture](https://github.com/vanand96/SentimentalAnalysis/blob/master/img/Tweets.png)
    * [pyLDAvis interactive chart capture](https://github.com/vanand96/SentimentalAnalysis/blob/master/img/image.png)


#### All the code is available in SentimentAnalysis.ipynb and TweetRead.py
   * [Jupyter Notebook](https://github.com/vanand96/SentimentalAnalysis/blob/master/SentimentAnalysis.ipynb)
   * [Tweets Streaming](https://github.com/vanand96/SentimentalAnalysis/blob/master/TweetRead.py)

#### SentimentAnalysis.ipynb contains project description, learning outcomes, issued faced and packages to be installed for running jupyter notebook.

#### Screen captures of tweet streaming and visualization of topic keywords can be found in img folder
   * [Tweets Streaming](https://github.com/vanand96/SentimentalAnalysis/blob/master/img/Tweets.png)
   * [pyLDAvis interactive](https://github.com/vanand96/SentimentalAnalysis/blob/master/img/image.png)

#### Before running this notebook please make sure to update access token, access screcret, consumer key and consumer secret in SentimentAnalysis.ipynb and TweetRead.py        
   ## `Developed by:`
    Anand Vadavelli
    Harshitha Sai Atluri

   ## 1. `OVERVIEW`

     This project read the twitter for vaccination and performs sentiment analysis using word cloud and vader. This project also uses tweepy api to search for the tweets and also spark streaming to read  the tweets 
 
   ## 2. `LEARNING`
   
     SENTIMENTAL ANALYSIS
     TOPIC MODEL ANALYSIS
     TWEETS STREAMING USING APACHE SPARK

   ## 3. `PREREQUISITES`

     Run "Anaconda" as `Administrator` and install the below packages
     pip install tweepy
     pip install matplotlib
     pip install seaborn
     pip install pandas
     pip install wordcloud
     pip install nltk
     pip install punkt
     pip install vaderSentiment
     pip install gensim
     pip install textblob
      
   ## 4. `SOURCE CODE`
        [1] Importing required packages and libraries
        
        [2],[3] Starting the spark session and reading the CSV file 

        [4],[5] Identifying how the data looks like and columns present in the dataframe.
 
        [6],[7] Collecting requirements to do analysis and checking for filtering of data
        
        [8] Functions to process the data
        
        [9] Datacleaning and making up original list
 
        [10] Creation  and conversion of dataframes from pandas to spark

        [11] Displaying the dataframe obtained
        
        [12] Merging the cleaned dataframe with the original one.
        
        [13] Displaying the dataframe after merging

       Data Analysis
       =============
         
        [14] Finding out the commonly used words in tweets by cleaning process (Word cloud)
        
        [15] Showing the plot of word cloud

         Sentiment Analysis using VADER
         ==============================

         [16] Downloading the required package to handle the emojis and slangs.
         
         [17] Using SentimenIntensityAnalyzer to obtain the polarity scores

         [18],[19],[20] Calculating the polarity scores for different categories like pos, neu, neg , compound 
         
         [21] Creation of dataframe in spark for the obtained polarity scores.

         [22] Summary of polarity scores
         
         [23],[24],[25] Merging the polarity scores to original dataframe and dispalying it
        
         [26] Printing the schema of the merged dataframe and displaying it.

         [27] Functions to analyze how the hashtags are useful in the tweet sentiment

         [28] Assigning different dataframe to each category based on their compound score (<0,==0, >0)

         Hashtags with Positive polarity
         ===============================
        
         [29] Calculation of positive tweets
         
         [30],[31]  Plotting the obtained positive tweets on a bargraph as well as heatmap

         Hashtags with Negative polarity
         ===============================

         [32] Calculation of negative tweets
         
         [33],[34]  Plotting the obtained negative tweets on a bargraph as well as heatmap

         Hashtags with Neutral polarity
         ==============================

         [35] Calculation of neutral tweets
         
         [36],[37]  Plotting the obtained neutral tweets on a bargraph as well as heatmap
     
         TOPIC MODEL ANALYSIS
         ====================

         [38] Importing all the required packages and preparing the stopwords downloaded using nltk.corpus 
      
         [39] Cleaning the sentences using Gensim's simple_preprocess()
 
         [40] Assigning tokens to the words and removing unnecessary punctuations

         [41] Building the bigram and trigram uso=ing Gensim's Phrases Model

         [42] Removing the stop words and preparing the obtained bigram and trigram to lemmatize
 
         [43],[44],[45],[46] Function calling in a sequential manner for lemmatization

         [47] Creating a dictionary and Corpus required for Topic Model Analysis

         [48] Building LDA(Linear Discriminant Analysis) Model
       
         [49] Viewing topics in LDA model
           
         [50] Computing the perplexity and coherence score ---> to indicate the quality of the model

         [51] Visualization of the keywords in the topics ==> Using "pyLDAvis"

         TWEEPY API SEARCH AND TWITTER HASHTAGS STREAMING USING APACHE SPARK
         ===================================================================

         [52] Importing all the required packages to load the twitter data
         
         [53] Provide the credentials of your "OWN" Twitter developer account.

         [54] Provide your consumerKey and consumerSecret to authenticate

         [55] Getting the access token and secret set up 

         [56] Creating new functions for the wait on the rate limit

         [57],[58] Getting upto 1000 tweets for certain keyword

         [59] Creating the dataframe in spark for the tweets obtained from the Twitter API

         [60] Count of the tweets

         [61] Printing the schema of the tweets

         [62] Displaying the tweets along with the date
   
         [63] Displaying the text content in each tweet

        Alternative method tried for Streaming of Twitter data
        ======================================================

         [64] Importing required packages in spark
         
         [65] Initializing the spark StreamingContext object and specifying the host IP address( YOUR LOCALHOST ADDRESS) 
              and the port number (PORT NUMBER OF YOUR LOCALHOST/ YOU CAN CHANGE THE PORT ) it is listening to.

         [66] Getting the lines of the stream window upto 20.

         [67] Naming the tweet column names
      
         [68] Mapping the tweets and sorting them based on the tweet count and also creating the temporary table

        Before starting the tweet stream :
           Update TweetRead.py with your twitter access token, secret, cosumer token, secret

         [69] Now start the spark streaming

         [70],[71] Importing packages and plotting the hashtags

   ## 5. `Issues`
          ERROR OCCURED: Py4JJavaError: An error occurred while calling o23.sql.
          : org.apache.spark.sql.AnalysisException: Table or view not found: tweets_stream; line 1 pos 23;
          'Project ['tag, 'count]
          
          We were unable to capture the streaming tweets into a spark dataframe. Code complained about unable to identify spark dataframe created 

