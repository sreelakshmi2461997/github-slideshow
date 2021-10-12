
import re

def passwordChecker(password):
    tooShort = "Your password is too short, it must be at least 10 characters"
    noNum = "Your password does not have a number. Please add at least one number."
    notMixed = "Your password is not mixed case. Please choose a password with mixed case."
    noSpec = "Your password does not have a valid special character. Please add at least one valid special character."
    if len(password) >= 10 and re.search(r'[0-9]', password) and re.search(r'[A-Z]', password) \
            and re.search(r'[a-z]', password) and re.search(r'[$!@%^&*#]', password):
        print("Your password is valid")
    elif len(password) < 10:
        print(tooShort, "\n" +str(noNum), "\n" + str(notMixed), "\n" + str(noSpec))
    elif len(password) >= 10 and re.search(r'[A-Z]', password) and re.search(r'[a-z]', password):
        print(noNum, "\n" + str(noSpec))
    elif len(password) >= 10 and re.search(r'[$!@%^&*#]', password):
        print(notMixed, "\n" + str(noNum))


password = str(input("Enter a password: "))
passwordChecker(password)
