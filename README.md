# News Text Classification

This project classifies English news articles into four categories:

- World
- Sports
- Business
- Sci/Tech

The goal is to try different models and check their results.

## Dataset

I used the AG News dataset from Hugging Face.

The dataset has:
- 120,000 training articles
- 7,600 test articles
- 4 news categories

## Models

I used four models:

1. Bag of Words + Naive Bayes
2. TF-IDF + Logistic Regression
3. TF-IDF + Linear SVM
4. DistilBERT

For the first three models, I cleaned the text:
- Changed letters to lowercase
- Removed punctuation and numbers
- Removed common English words, such as “the” and “is”

For DistilBERT, I used the original text and its tokenizer.

## Results

The first three models used all 120,000 training articles
and the same 7,600 test articles.

| Model | Accuracy | Weighted F1 |
|---|---:|---:|
| Naive Bayes + BoW | 88.86% | 0.8881 |
| Logistic Regression + TF-IDF | 91.47% | 0.9146 |
| Linear SVM + TF-IDF | 91.32% | 0.9130 |

Logistic Regression had the highest accuracy in this test.

Accuracy shows how many predictions were correct.
F1 is another score used to check classification performance.

## DistilBERT experiment

I also tried DistilBERT on a small part of the dataset.

- Training articles: 1,000
- Test articles: 500
- Training epochs: 1

One epoch means the model goes through the training data once.

| Accuracy | Weighted F1 |
|---:|---:|
| 85.60% | 0.8548 |

DistilBERT used less training data and a smaller test set.
So these scores do not show which model is better overall.

## Charts

The notebook includes:
- The 10 most common words after text cleaning
- A confusion matrix for Logistic Regression
- A chart comparing the classical model scores

The confusion matrix shows which categories the model
predicts correctly and which categories it mixes up.

## Example

I tested the trained Logistic Regression model with a new sentence:

“The football team won the championship.”

Predicted category: Sports

You can change the sentence in the last code cell
to test another English news text.

## Key concepts

- fit(): trains a model using texts and their correct labels.
- predict(): uses the trained model to predict a category.
- Bag of Words: counts how often words appear in a text.
- TF-IDF: turns text into numbers using word frequency
  and how common each word is across the articles.
- DistilBERT: a model already trained on text.
  I trained it further for news classification.

## How to run

1. Download the notebook.
2. Open it in Google Colab.
3. Choose a GPU runtime for the DistilBERT part.
4. Run the cells from top to bottom.

The notebook has cells to install the required libraries.
It also downloads the dataset and DistilBERT model,
so an internet connection is needed.

Running all cells trains the models again.
The results may be slightly different each time.

## Limitations

This is a learning project for English news.
I have not tested it on other languages or other types of text.

The DistilBERT experiment used a small amount of data.
More experiments are needed to understand its performance.

## Author

Zuhra Rahimova
