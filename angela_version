##################### Extra Hard Starting Project ######################
import pandas
import datetime as dt
import smtplib
import random

MY_EMAIL = "YYY"
MY_PASSWORD = "XXX"

# 1. Update the birthdays.csv
data = pandas.read_csv("birthdays.csv")
data_dict = data.to_dict(orient="records")

# 2. Check if today matches a birthday in the birthdays.csv
now = dt.datetime.now()
month = now.month
day = now.day

for person in data_dict:
    if person["month"] == month and person["day"] == day:

# 3. If step 2 is true, pick a random letter from letter templates and replace the [NAME] with the person's actual name from birthdays.csv
        with open("letter_templates/letter_1.txt") as letter_1:
            letter_content_1 = letter_1.read()
        with open("letter_templates/letter_2.txt") as letter_2:
            letter_content_2 = letter_2.read()
        with open("letter_templates/letter_3.txt") as letter_3:
            letter_content_3 = letter_3.read()

        letters_list = [letter_content_1, letter_content_2, letter_content_3]
        random_letter = random.choice(letters_list)
        content = random_letter.replace("[NAME]", person["name"])

# 4. Send the letter generated in step 3 to that person's email address.
        with smtplib.SMTP("smtp.gmail.com") as connection:
            connection.starttls()
            connection.login(user=MY_EMAIL, password=MY_PASSWORD)
            connection.sendmail(
                from_addr=MY_EMAIL,
                to_addrs=person["email"],
                msg=f"Subject: Happy Birthday\n\n{content}")





