Given a user-written text (tweet or sentence), the model predicts one of four sentiment classes -:
 ```text✅ Positive – expresses a positive opinion
 ❌ Negative – expresses a negative opinion
 ⚪ Neutral – factual or emotionless statement
 🚫 Irrelevant – unrelated to sentiment or entity
```text

| Input Text                         | Predicted Sentiment |
| ---------------------------------- | ------------------- |
| *"I love this movie"*              | **Positive**        |
| *"This update ruined the game"*    | **Negative**        |
| *"I added this movie to my PC"*    | **Neutral**         |
| *"I am going to the market today"* | **Irrelevant**      |

```textDuring experimentation, multiple machine learning models were evaluated, including Logistic Regression, Naive Bayes, and Support Vector Machines (SVM) with different text vectorization techniques.
After comparison, Linear SVM with CountVectorizer was selected because it delivered the best accuracy and stability on high-dimensional text data.
```text

```textWhy a Single Classifier Was Not Enough -:
A single 4-class classifier struggled to correctly distinguish between:
Positive vs Neutral
Negative vs Neutral
Neutral vs Irrelevant
```

Two-Stage Classification Approach:-
```text
Input sentence
      ↓
Is this subjective?
      ↓
   Yes        No
    ↓          ↓
Positive /   Neutral /
Negative     Irrelevant
```
```text🔹 What does “Subjective” mean?
Subjective text expresses an opinion or emotion.
Examples:
“I love this movie” → Subjective
“This update ruined the game” → Subjective
```

```text🔹 What does “Not Subjective” mean?
Not subjective (objective) text contains facts or unrelated statements.
Examples:
“I added this movie to my PC” → Neutral
“The game was released in 2012” → Neutral
“I am going to the market today” → Irrelevant
```
