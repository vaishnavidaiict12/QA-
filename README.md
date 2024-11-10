Selenium WebDriver Test Automation for Amazon Search and Product Details Verification


This task uses Selenium WebDriver to automate the testing of search functionality and product details on Amazon. It verifies the presence of key product information such as title, price, and rating, and takes screenshots at each validation point.

Project Setup and Running Instructions
Prerequisites
Python (version 3.6 or above) installed on your machine.
Google Chrome installed (compatible with the chromedriver).
ChromeDriver (compatible with your installed version of Chrome).
Selenium library installed.


Step 1: Clone the Repository

git clone <repository-url>
cd selenium-amazon-test

Step 2: Install Required Python Packages
Install the necessary Python packages by running:

pip install selenium

Step 3: Download ChromeDriver
Download chromedriver compatible with your version of Chrome from ChromeDriver - WebDriver for Chrome.
Place the downloaded chromedriver in your project directory or add it to your system path.

Step 4: Set Up Directory for Screenshots
The script saves screenshots in a directory named testcase11. Make sure this directory exists or let the script create it for you.

Step 5: Running the Script
To run the script, execute:
python test_script.py

The script will open a Chrome browser, navigate to Amazon, perform the search, and validate the product details. It will save screenshots in the testcase11 directory.

 Note: You can directly do this in jupyter notebook also . 

 Code Overview
Dependencies
The script imports the following modules:

python
Copy code
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.common.exceptions import TimeoutException
import time
import os
Script Logic
Initialize WebDriver: Sets up the Chrome WebDriver and opens the Amazon homepage.
Define Helper Functions:
wait_for_element: Waits for an element to be visible on the page.
scroll_and_highlight: Scrolls to the element, highlights it, and takes a screenshot.
Test Function - test_search_and_product_details:
Opens the Amazon homepage and searches for "Laptop".
Validates that search results are displayed, each containing title, price, and rating (for the first three results).
Clicks on the first product to navigate to the details page and validates the presence of product title, price, and availability.
Error Handling: Catches assertion and timeout errors, logging them appropriately.
Cleanup: Closes the browser after the test is complete.


Expected Output
Console Output: Displays the result (pass/fail) for each validation point.
Screenshots: Captures screenshots at each validation point:
search_results.png: Search results page.
product_1_title.png, product_1_price.png, etc., for each product detail.
product_details_title.png, product_details_price.png, product_details_availability.png on the product details page.


Example of Console Output
Clicked 'Continue' button.
Entered invalid email.
Screenshot saved as testcase11/screenshots/invalid_email_format.png
Test Case 1: Passed

Notes:
Adjust the sleep time (time.sleep) or use explicit waits as needed, depending on page load times.
The test includes error handling for cases when elements such as price or rating may not be present for all products.






