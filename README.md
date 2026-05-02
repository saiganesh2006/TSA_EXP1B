# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 02-05-2026

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
df = pd.read_csv('Combined12.csv')
col = 'temp_mean(c)'
df[col] = df[col].fillna(method='ffill')
original = df[col]
log_data = np.log(original + 1)   
diff_data = original.diff().dropna()
seasonal = original - original.rolling(window=12).mean()
plt.figure(figsize=(12,8))

plt.subplot(4,1,1)
plt.plot(original)
plt.title('Original Data')

plt.subplot(4,1,2)
plt.plot(log_data)
plt.title('Log Transformed Data')

plt.subplot(4,1,3)
plt.plot(diff_data)
plt.title('Differenced Data')

plt.subplot(4,1,4)
plt.plot(seasonal)
plt.title('Seasonal Adjusted Data')

plt.tight_layout()
plt.show()
```
### OUTPUT:
ORIGINAL TIME SERIES:

<img width="1336" height="215" alt="image" src="https://github.com/user-attachments/assets/5d5952f2-85f1-427b-b1f5-d9d9af3a01f1" />


REGULAR DIFFERENCING:

<img width="1338" height="213" alt="image" src="https://github.com/user-attachments/assets/936ca4fc-af21-45e1-ba71-6a3fea47ef31" />


SEASONAL ADJUSTMENT:

<img width="1358" height="215" alt="image" src="https://github.com/user-attachments/assets/78ab3431-1634-4391-9fda-23ede33e81f2" />

LOG TRANSFORMATION:

<img width="1335" height="219" alt="image" src="https://github.com/user-attachments/assets/a8f860ac-a969-4646-80f0-4e56161c7285" />


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
