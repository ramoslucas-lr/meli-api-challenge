# 🛒 Busca de Produtos no Mercado Livre e Criação de Dataset 📊

Este projeto busca informações de produtos 📦 no Mercado Livre utilizando a API pública 🌐, processa esses dados 🔄 e cria um dataset (arquivo CSV 📄) com as informações relevantes.

## 🚀 Como Executar

1.  **Pré-requisitos**:
    * Python 🐍 instalado
    * Bibliotecas `requests`, `pandas` e `json` instaladas (você pode instalá-las usando `pip install requests pandas`)
    * Um token de acesso da API do Mercado Livre 🔑 (substitua `'APP_USR-SEU_TOKEN'` na variável `ACCESS_TOKEN`)
2.  **Executar o Notebook**:
    * Abra o notebook Jupyter `MercadoLivre_Dataset.ipynb` 📓.
    * Execute as células do notebook sequencialmente.
3.  **Resultado**:
    * Um arquivo CSV chamado `dataset.csv` será gerado na mesma pasta do notebook, contendo o dataset com as informações dos produtos 📝.

## ⚙️ Configurações

As seguintes variáveis de configuração são utilizadas:

* `ACCESS_TOKEN`: Token de acesso da API do Mercado Livre 🔑.
* `BASE_URL_SEARCH`: URL base para buscas na API 🔍.
* `BASE_URL_ITEM`: URL base para detalhes de itens na API 📦.
* `HEADERS`: Cabeçalhos da requisição, incluindo o token de acesso 🔐.
* `SEARCH_TERMS`: Lista de termos de pesquisa 📝.
* `SELECTED_COLUMNS`: Lista de colunas a serem incluídas no dataset final 📊.

## 🛠️ Funções Principais

* `fetch_search_results(search_term)`: Busca resultados de pesquisa para um termo 🔍.
* `extract_item_ids(search_results)`: Extrai IDs de itens dos resultados da pesquisa 🆔.
* `fetch_item_details(item_ids)`: Busca detalhes de itens usando seus IDs 📦.
* `get_all_attribute_keys(item_details)`: Obtém todas as chaves de atributo possíveis 🔑.
* `flatten_item_details(item_details, all_attributes)`: Achata os detalhes dos itens 📉.
* `select_and_order_columns(flattened_details, selected_columns)`: Seleciona e ordena colunas 📊.

## 📊 Processamento de Dados

O notebook executa os seguintes passos:

1.  Busca resultados de pesquisa para cada termo em `SEARCH_TERMS` 🔍.
2.  Extrai os IDs dos itens encontrados 🆔.
3.  Busca os detalhes completos de cada item 📦.
4.  Obtém todas as chaves de atributo possíveis 🔑.
5.  Achata os detalhes dos itens, movendo os atributos para o nível superior 📉.
6.  Seleciona e ordena as colunas desejadas 📊.
7.  Cria um DataFrame do pandas e salva em `dataset.csv` 📄.

## 📦 Dataset Gerado

O arquivo `dataset.csv` contém as seguintes colunas, conforme definidas em `SELECTED_COLUMNS`:

* `id` 🆔
* `site_id` 📍
* `title` 📝
* `seller_id` 🧑‍💼
* ... (e outras colunas definidas)
