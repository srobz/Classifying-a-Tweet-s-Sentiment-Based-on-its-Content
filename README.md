
# Classifying a Tweet's Sentiment Based on its Content
## Phase 4 Final Project



## Introduction

The purpose of this project is to build a model that can rate the sentiment of a tweet based on its content.



Following the Data Science approach of OSEMN, as outlined and detailed below, I was able to build a multi-class classifier with an accuracy of 67.15%.


## The Data Science Process: OSEMN

### Obtain

The data is from CrowdFlower and contains over 9000 tweets about Apple and Google products rated by humans as either postive, negative, or neither.

### Scrub

Here the data was cleaned and organized. Because this was a Natural Language Processing project this was also when text preprocessing occurred.

### Explore

Rather than answering questions throughout the exploratory data analysis, I chose to explore a few different things that I found interesting while cleaning the data:

  * Spread of Tweets
  * Tweet Length
  * Sentiment among Brands
  * Most Used Hashtags
  * Most Used Terms
  * Common Phrases

When I was done exploring these things I realized I had answered the following questions:


* How are the tweets spread?
    
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/TweetsPerEmotion.png)
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/TweetsPerBrand.png)

* What is the spread of tweet sentiment among brands?

![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/TweetsEmotionBrand.png)
    
* How much did preprocessing change the length of tweets?
    
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/CharacterCount.png)
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/TokenCount.png)

* Do four-word phrases (ngrams) help distinguish between sentiments?

![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/fourword.png)

I also created some Word Clouds:

# All Hashtags Word Cloud
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/hashtags.png)

# All Tokens Word Cloud
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/alltokens.png)

# Positive Tokens Word Cloud
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/postokens.png)

# Neutral Tokens Word Cloud
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/neutraltokens.png)

# Negative Tokens Word Cloud
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/negtokens.png)

# Apple Tokens Word Cloud
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/appletokens.png)

# Google Tokens Word Cloud
![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/googletokens.png)


### Model

I tried six different models with two different vectorizers each resulting in twelve baseline models. There were five top models, and from those I had 23 tuned models. 


### iNterpret

My final model was Logistic Regression using Count Vectorizer with class weight equal to balanced. This model had an accuracy of 67.15%. In general, our model was able to accurately classify a negative tweet as negative 39% of the time, a neutral tweet as neutral 77% of the time, and a positive tweet as positive 58% of the time. While that isn’t perfect, considering how imbalanced the dataset was this is pretty good.

![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/confmatrtes.png)

Regarding our precision recall curve; the curve for neutral is looking good and the score is enough that we would consider neutral to be a good classifier. The curve for positive is considerably worse at .63, and would be considered a bad classifier. The curve for negative is very bad, and performs worse than a random classifier would.

![graph](https://raw.githubusercontent.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/main/Visualizations/precrecall.png)


    

## Conclusion

The EDA provided us with a lot of information about this dataset, specifically that a majority of the sentiment surrounding the tweets was rated as neutral, so when going through the modeling process it makes sense that precision recall curves and roc curves for that class are the highest in every case. 

Although most of the tweets are about neutral content, looking deeper into negative and positive tweets will certainly provide more feedback to stakeholders. A majority of tweets about the brand Apple were neutral, and that is something that they should look into regarding the SXSW festival. In addition, the most common phrases that were seen among all sentiments were the same; they were generally about pop ups or products around the festival.


## Repository Organization
- ['Phase 4 Project - 1 - Data Cleaning.ipynb'](https://github.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/blob/main/Phase%204%20Project%20-%201%20-%20Data%20Cleaning.ipynb) : Jupyter notebook of Data Cleaning with code and comments
- ['Phase 4 Project - 2 - Data Exploration.ipynb'](https://github.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/blob/main/Phase%204%20Project%20-%202%20-%20Data%20Exploration.ipynb) : Jupyter notebook of Data Exploration with code and comments
- ['Phase 4 Project - 3 - Baseline Modeling.ipynb'](https://github.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/blob/main/Phase%204%20Project%20-%203%20-%20Baseline%20Modeling.ipynb) : Jupyter notebook of Baseline Modeling with code and comments
- ['Phase 4 Project - 4 Tuning and Final Models.ipynb'](https://github.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/blob/main/Phase%204%20Project%20-%204%20-%20Tuning%20and%20Final%20Models.ipynb) : Jupyter notebook of Tuning and Final Models with code and comments
- [Phase 4 Project Presentation.pdf](https://github.com/srobz/Module-3-Project/blob/main/Module%203%20Project%20Presentation.pdf) : Project presentation
- ['Visualizations'](https://github.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/tree/main/Visualizations) : Folder containing graphs used in ReadME and presentation
- ['Images'](https://github.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/tree/main/Images) : Folder containing images used in Phase 4 Project - 2 - Data Exploration.ipynb
- ['tweet_data.csv'](https://github.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/blob/main/tweet_data.csv) : Original dataset used for project
- ['CleanedDF.csv'](https://github.com/srobz/Classifying-a-Tweet-s-Sentiment-Based-on-its-Content/blob/main/CleanedDF.csv) : Updated dataset from the end of Phase 4 Project - 1 - Data Cleaning.ipynb
- [README.md] : ReadMe
