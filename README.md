## Overview

This is a test/replica from original code: [edwardhdlu](https://github.com/edwardhdlu/q-trader) . It's implementation of Q-learning applied to (short-term) stock trading. The model uses n-day windows of closing prices to determine if the best action to take at a given time is to buy, sell or hold.

Additional controls added:
 - Buy: only when inventory == 0; not allowing opening multiple positions.
 - Sell: only when inventory == 1; not allowing net short position at the moment. 

## Running the Code

To train the model, download a training and test csv files from [Yahoo! Finance](https://ca.finance.yahoo.com/quote/%5EGSPC/history?p=%5EGSPC) into `data/`
```
python train.py GSPC_Train 20 1000
```

Then when training finishes (minimum 200 episodes for results):
```
python evaluate.py GSPC_Evaluate model_ep1000
```

## References

[Deep Q-Learning with Keras and Gym](https://keon.io/deep-q-learning/) - Q-learning overview and Agent skeleton code
