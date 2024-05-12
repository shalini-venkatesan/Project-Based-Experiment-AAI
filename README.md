<H3> NAME SHALINI V</H3>
<H3>REGISTER NO. 212222240096</H3>
<H3>DATE:</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
step 1: Download facebook information form the settings
step 2: Store it in thr excel sheet
step 3: Import neccessary library in python
step 4: Sentiment analysis involves working out whether a piceof text is positive,negative or neutral
step 5: VADER takes into account the intensity of the sentiment.
step 6: A data frame is a 2-D structure in the form of a table 
step 7: End the program.
<H3>Program:</H3>
```py
import pandas as pd
import nltk
from nltk.sentiment.vader import SentimentIntensityAnalyzer
nltk.downloader.download('vader_lexicon')
file = '/content/data_file.xlsx'
import os

if not os.path.exists(file):
    raise FileNotFoundError("File not found: {}".format(file))

if not os.access(file, os.R_OK):
    raise PermissionError("Permission denied: {}".format(file))

xl = pd.ExcelFile(file)

dfs = xl.parse(xl.sheet_names[0])
print(dfs)

sid = SentimentIntensityAnalyzer()
str1 = "UTC+05:30"
for data in dfs:
  a = data.find(str1)
  if(a==-1):
    ss = sid.polarity_scores(data)
    print(data)
    for k in ss:
      print(k,ss[k])
```
<H3>Output:</H3>

![image](https://github.com/shalini-venkatesan/Project-Based-Experiment-AAI/assets/118720291/3030f28d-453b-45d2-be22-0eebe31d16ef)

![image](https://github.com/shalini-venkatesan/Project-Based-Experiment-AAI/assets/118720291/4135073a-627a-4898-936d-b82bd79ba49f)

<H3>Inference:</H3>
Analyze textual data from a Facebook dataset, assuming that timestamps contain "UTC+05:30". If a timestamp doesn't contain this string, it's considered textual data for sentiment analysis.
