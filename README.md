[![Build Status](https://img.shields.io/travis/mlucchini/bot.ai.svg)](https://travis-ci.org/mlucchini/bot.ai)
[![Heroku Deployment](https://heroku-badge.herokuapp.com/?app=kitt-ai&root=metadata&svg=1)](https://kitt-ai.herokuapp.com)

# bot.ai

A minimal chatbot platform.

### Usage

Python 2:

```sh
make run
make test
```

Docker:

```sh
docker-compose up
```

### Approaches

##### Intent recognition

The user input is compared to submitted labelled expressions with cosine similarity using an average of word vectors ([spaCy](https://spacy.io), [doc2vec](http://radimrehurek.com/gensim/models/doc2vec.html), [word2vec](http://radimrehurek.com/gensim/models/word2vec.html)). The intent associated with the closest match is returned. The next natural improvements could be to use an RNN-LSTM neural network instead, trained with Keras, to preserve word sequence and word dependencies and also to fine-train the [GloVe](https://nlp.stanford.edu/projects/glove/) word vectors currently used.

API: `http://localhost:5000/entities?text=<input>`
