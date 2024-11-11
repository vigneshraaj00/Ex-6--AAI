# EX-06 Implementation of Semantic Analysis
### Aim: 
To perform Parts of speech identification and Synonym using Natural Language &emsp;&emsp;&emsp;&emsp;<br>Processing (NLP) techniques.
### Algorithm:
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.
### Program:
**Developed By: Vignesh raaj S**

**REGISTER NO:212223230239**
##### Importing NLTK and Resource Downloads
```Python
import nltk
nltk.download( 'punkt' )
nltk.download('wordnet')
nltk.download('omw-1.4')
from nltk.tokenize import word_tokenize
nltk.download( 'averaged_perceptron_tagger' )
from nltk.corpus import wordnet
```
##### Tokenization and Part-of-Speech Tagging
```Python
sentence=input()
words = word_tokenize(sentence)
pos_tags= nltk.pos_tag(words)
for word, tag in pos_tags:
    print(f"{word:<6} - {tag}")
```
##### Extracting Synonyms and Antonyms from Words
```Python
synonyms =[]
antonyms =[]
for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append (lemma.name())
            if lemma.antonyms():
                antonyms.append (lemma.antonyms()[0].name())
print ( "Synonyms : " ,set(synonyms))
print ( "Antonyms : " ,set(antonyms))
```

### Output:
##### Parts of Speech:
![image](https://github.com/user-attachments/assets/5af734f5-7d4c-4335-8e57-3fd079a7e424)

##### Synonyms and Antonyms:
![image](https://github.com/user-attachments/assets/409b7e1d-20ea-4805-8773-a9461e01f4e0)


### Result:
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.<br>
