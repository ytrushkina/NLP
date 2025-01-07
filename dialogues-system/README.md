## Dialogue System Assisting with Search

### Tools & Technologies
- Python, scikit-learn, StarSpace, NLTK, BeautifulSoup, AWS, Telegram

### Description
- A StackOverflow assistant bot that answers programming-related questions. Hosted on AWS, accessible via a Telegram Bot

### Source
- Developed as a final project of the NLP Course within the "Advanced Machine Learning" Specialization (HSE, Coursera)
- Code available upon request due to course restrictions

### Outcome
- Successfully implemented a functional dialogue system, demonstrating proficiency in NLP and cloud deployment

### Modules
1. **Data Preparation and Vectorization**
   - **Tools**: pandas, re, nltk
   - **Description**: Data loading and balancing the datasets of positive/negative examples. Tokenization and preprocessing, including lowercase conversion, stopwords removal, and splitting.
   
2. **Intent Recognition of User Message**
   - **Tools**: sklearn TfidfVectorizer, sklearn LogisticRegression
   - **Description**: Binary classification on Tf-Idf representations of text collections (StackOverflow posts and movie subtitles dialogues).
   - **Output**: `vectorizer.pkl`, `intent_recognizer.pkl`
   
3. **Chitchat Message Response Generation**
   - **Tools**: chatterbot, rasa-like rule-based generation
   - **Description**: Response generation based on a combination of a rule-based module and an NN engine from ChatterBot class.
   
4. **Programming Questions Handling**
   - **Programming Language Classification**
     - **Tools**: sklearn OneVsRestClassifier, LogisticRegression
     - **Description**: Logistic regression with Tf-Idf features.
     - **Output**: `tag_classifier.pkl`
   - **Ranking of StackOverflow Posts**
     - **Tools**: StarSpace, numpy, sklearn pairwise_distances_argmin
     - **Description**: Ranking posts according to their relevance based on similarity of post/question vector representations.
     - **Output**: Folder with pkl files for the posts.
   - **Return Feedback**
     - **Tools**: BeautifulSoup
     - **Description**: Based on the best post ID, return post title, detect post language, and wrap it into an answer template.
   
5. **Putting It All Together**
   - **DialogManager Class**: Manages all the above steps.
   - **Main Bot Script**: Handles the Telegram Bot conversation based on the DialogManager.
   - **Deployment**:
     - Setting up an AWS Virtual Machine.
     - Installing Docker container for Ubuntu with needed dependencies.
     - Copying project code and data to AWS instance.
     - Initializing the Telegram bot.

### Example
<img src="https://github.com/ytrushkina/NLP/blob/master/dialogues-system/screenshot.jpg" alt="Bot in Action" width="450"/>

