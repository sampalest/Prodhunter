# Prodhunter
This project search for products and notifies when a product is available.

## Allowed webs
* Amazon ES

## Config file
To configure this script, just complete this file with your credentials and products url.
<br>Example:

```yaml
---
webs:
  mediamarkt:
    - url: 'https://www.mediamarkt.es/es/product/<<prod>>.html'
      name: 'My super product'
    - url: 'https://www.mediamarkt.es/es/product/<<prod>>.html'
      name: 'My super product 2'
  eci:
    - url: 'https://www.elcorteingles.es/....'
      name: 'My super product'
    - url: 'https://www.elcorteingles.es/....'
      name: 'My super product 2'
  amazon:
    - url: 'https://www.amazon.es/dp/<<product-id>>'
      name: 'My super product'
    - url: 'https://www.amazon.es/<<amazon-prod-name>>/dp/<<product-id>>'
      name: 'My super product 2'
telegram:
  token: '0000000000:supertelegramtoken'
  chatID: 'chatid'
  message: 'Product stock' # General message for telegram chat
```

## Run
1. Install packages: 
```shell 
pipenv install
```
2. Virtualenv:
```shell 
pipenv shell
```
3. Run:
```shell
# Set your config file (by default config/config.yml)
python3 src/main.py --config-file path/to/your/config.yml
```

## Docker-compose
1. You need environment variables (`env_file: deploy/.env`)
```shell
# cd deploy...
cp .env.sample .env
```

2. docker-compose up
```shell
# Project root...
docker-compose up -d
```
