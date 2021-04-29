##### Problem Description
Classify reddit posts based on the post content. Use classfication modeling techniques to predict which sub-redit a post belongs to.

##### Data collection
We are using an API hosted on api.pushshift.io to collect posts from a given subreddit. 
pushshift API accepts requests in following format
https://api.pushshift.io/reddit/search/submission?subreddit=todayilearned
For the purpose of this project I am collection posts from 'todayilearned' and 'motorcycles' sub-reddit. Posts are saved offline in an .csv file which can then be accessed to extract posts and related data into a Pandas DataFrame

##### Data wrangling/clean up
Create a DataFrame by reading .csv files. All missing values were replaced with empty strings.
Merged 'selftext' and 'title' column into one column.

##### Model creation and validation
1. Split input data into X and y.
2. Pre-process X by  using a regex to remove punctuation, urls, line feed, tab spaces, carriage returns
3. Remove 'TIL' from each document. Every 'todayilearned' sub-reddit post begins with TIL.
4. Use spaCy NLP library to tokenize and lemmatize each document
5. Build LogisticRegression model using CountVectorizer and TfifdVectorizers transfomers on both raw & pre-processed X data
6. Build LogisticRegression model using CountVectorizer and TfifdVectorizers transfomers on pre-processed X data
7. Build a DecisionTreeClassifier model



