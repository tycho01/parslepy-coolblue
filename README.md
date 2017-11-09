# Usage:
```bash
cd /opt/kafka
bin/zookeeper-server-start.sh config/zookeeper.properties
bin/kafka-server-start.sh config/server.properties

scrapy crawl Kafka -a crawl='y' 
scrapy crawl Parsley -a parselet='parselets/nytimes.yml' 
scrapy crawl Parsley -a parselet='parselets/coolblue.yml' 
-a domain='nytimes.com' -a url='http://www.nytimes.com/pages/technology/' -t jl -o -
-a domain='www.coolblue.nl' -a url='https://www.coolblue.nl/product/697284/samsung-ww80j6403ew-eco-bubble.html' -t jl -o -
 > results/nytimes.jl
 > results/coolblue.jl

scrapy crawl Parsley -a parselet='parselets/coolblue.yml' -a domain='www.coolblue.nl' -a url='http://coolblue.nl/product/697284/' -t jl -o - > results/coolblue.jl

scrapy crawl Kafka -a crawl='y' -a domain='nytimes.com' -a url='http://www.nytimes.com/pages/technology/' -t jl -o -

https://www.coolblue.nl/ons-assortiment

python parse.py -i results/coolblue_prods.jl -o results/bar.jl -p parselets/coolblue.yml
```
