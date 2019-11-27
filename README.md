# Unsupervised-Sentiment-Analysis
How to extract sentiment from the data without any labels

Repo for towardsdatascience article: https://towardsdatascience.com/unsupervised-sentiment-analysis-a38bf1906483 about Unsupervised Sentiment Analysis on Polish Sentiment Dataset.

Analyzed dataset comes from wonderful article by Szymon Płotka: https://ermlab.com/en/blog/nlp/polish-sentiment-analysis-using-keras-and-word2vec/

Dataset was analyzed using Word2Vec algorithm, KMeans clustering, and tfidf weighting. Based on word embeddings trained for given dataset using gensim's Word2Vec implementation, there was an unsupervised sentiment analysis performed, which achieved scores presented below. Main steps included detection of negative and positive clusters in word vectors space with use of sklearn's implementation of KMeans clustering algorithm, which were then used to transform every sentence into vector of replaced sentiment scores for a given words in a sentence. Second vector for given sentence was obtained through replacing all words in a sentence with their corresponding tfidf-scores. Final prediction was obtained as a dot product from these two vectors for each sentence - if their dot product was positive, the overall sentiment was predicted as positive, and if dot product was negative, overall sentiment was predicted as negative. Details are described in the article linked at the begining, hope it will be useful for anyone! :) 

```
Confusion Matrix
╔═══════════╦════════════════════╦═══════════════╗
║           ║         0          ║       1       ║
╠═══════════╬════════════════════╬═══════════════╣
║     0     ║        9523        ║       306     ║
╠═══════════╬════════════════════╬═══════════════╣
║     1     ║       127125       ║     508277    ║
╚═══════════╩════════════════════╩═══════════════╝




╔═══════════╦════════════════════╗
║   Scores  ║                    ║
╠═══════════╬════════════════════╣
║ accuracy  ║ 0.802503           ║
║ precision ║ 0.999398           ║
║ recall    ║ 0.799930           ║
║ F1        ║ 0.888608           ║
╚═══════════╩════════════════════╝

```
