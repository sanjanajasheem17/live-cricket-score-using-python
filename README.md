# live-cricket-score-using-python
import requests
from bs4 import BeautifulSoupfrom time import sleep
url="http://static.cricinfo.com/rss/livescores.xml"
while true:
r=requests.get(url)
while r.status_code is not 200:
r=requests.get(url)
soup=BeautifulSoup(r.text,'html.parser')
data=soup.find_all("description")
score=data[1].text
print(score)
sleep(60)
