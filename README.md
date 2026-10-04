# 📚 Books to Scrape — Web Scraping Project

A Python web scraping project that extracts book information from [Books to Scrape](https://books.toscrape.com/) and stores the collected data in a Pandas DataFrame.

The project demonstrates the basics of **web scraping, HTML parsing, pagination, data extraction, and data handling using Python**.

## 🚀 Features

* Scrapes data from all **50 catalogue pages**
* Extracts information for each book
* Visits individual book pages to collect detailed information
* Handles relative URLs using `urljoin()`
* Stores the scraped data in a structured Pandas DataFrame
* Tracks the total number of books extracted
* Measures the scraping execution time

## 📊 Data Extracted

For every book, the project collects:

| Field            | Description                    |
| ---------------- | ------------------------------ |
| **Title**        | Name of the book               |
| **Category**     | Category/genre of the book     |
| **Price**        | Listed price of the book       |
| **Availability** | Stock availability information |
| **Rating**       | Book rating from 1 to 5 stars  |

## 🛠️ Technologies Used

* **Python**
* **Requests** — for sending HTTP requests
* **BeautifulSoup** — for parsing HTML
* **Pandas** — for storing and working with the scraped data
* **urllib** — for handling URLs
* **Jupyter Notebook** — for development and experimentation

## 📁 Project Structure

```text
BooksToScrape/
│
├── BooksToScrape.ipynb
└── README.md
```

## ⚙️ How It Works

### 1. Send a Request

The project first sends a GET request to the Books to Scrape website.

```python
res = requests.get(base_url)
```

The response status code is checked to make sure the request was successful.

### 2. Parse the HTML

BeautifulSoup is used to parse the HTML content:

```python
soup = BeautifulSoup(res.text, "html.parser")
```

This allows the required elements from the webpage to be located and extracted.

### 3. Extract Book Details

For each book, the scraper visits its individual page and extracts:

* Title
* Category
* Price
* Availability
* Rating

### 4. Scrape All 50 Pages

The scraper loops through all 50 catalogue pages:

```python
for page_num in range(1, 51):
```

For every page, it finds the books and then visits each individual book page to collect the required information.

### 5. Store the Data

The extracted information is stored in a list and converted into a Pandas DataFrame:

```python
df = pd.DataFrame(
    books_data,
    columns=['Title', 'Category', 'Price', 'Availability', 'Rating']
)
```

## 📦 Installation

Clone the repository:

```bash
git clone <YOUR_REPOSITORY_URL>
cd BooksToScrape
```

Install the required libraries:

```bash
pip install requests beautifulsoup4 pandas
```

## ▶️ Running the Project

Open the Jupyter Notebook:

```bash
jupyter notebook
```

Then open:

```text
BooksToScrape.ipynb
```

Run the cells sequentially to start the scraping process.

## 📈 Output

The final output is a Pandas DataFrame containing the scraped information for the books found across the 50 catalogue pages.

Example structure:

```text
| Title | Category | Price | Availability | Rating |
|-------|----------|-------|--------------|--------|
| Book 1 | Fiction | £XX.XX | In stock | Three |
| Book 2 | Travel | £XX.XX | In stock | Four |
| ... | ... | ... | ... | ... |
```

The scraper processes approximately **1,000 books** available across the catalogue.

## 🎯 Learning Outcomes

Through this project, I learned and practiced:

* Sending HTTP requests using Python
* Understanding HTTP response status codes
* Parsing HTML using BeautifulSoup
* Finding and extracting HTML elements
* Working with relative and absolute URLs
* Handling pagination
* Scraping data from individual detail pages
* Structuring scraped data using Pandas
* Measuring execution time of a scraping process

## ⚠️ Disclaimer

This project is created for **educational purposes** using the publicly available **Books to Scrape** website, which is specifically designed for practicing web scraping.

When scraping real websites, always check and respect their terms of service, `robots.txt`, rate limits, and applicable laws.

## 👨‍💻 Author

**Naman Mangla**

B.Tech CSE | AI/ML Enthusiast

---

⭐ If you found this project useful, consider giving the repository a star!
