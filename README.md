
import pytest
from selenium import webdriver
from selenium.webdriver.common.by import By

def test_addition_positive_numbers():
    driver = webdriver.Chrome()
    driver.get("https://your-calculator-url.com")  # Replace with actual URL

    # Click '1' and '2'
    driver.find_element(By.ID, "btn1").click()
    driver.find_element(By.ID, "btn2").click()

    # Click '+'
    driver.find_element(By.ID, "btn_plus").click()

    # Click '8'
    driver.find_element(By.ID, "btn8").click()

    # Click '='
    driver.find_element(By.ID, "btn_equals").click()

    # Verify output
    result = driver.find_element(By.ID, "display").text
    assert result == "20", f"Expected 20, but got {result}"

    driver.quit() 
