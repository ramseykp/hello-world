# hello-world
first repository built with Github

import random

possibleanswers = []
number = 1
while number <= 1000:
    possibleanswers.append(number)
    number = number + 1



    

print("""Welcome to GUESS THAT NUMBER""")

ready = input("""Type "yes" or "no" to the following questions. Think up a number between 1 and 1000 and then type "OK" when you are ready.""").strip().lower()

if ready == "ok":
    while len(possibleanswers) != 1:

        low = possibleanswers[0]
        high = possibleanswers[-1]
        span = high - low
        middle = (span/2)+low
        C = round(int(middle))
        lessthan = input("Is your number less than {}?".format(C)).strip().lower()  
        if lessthan == "yes":
            possibleanswers = [number for number in possibleanswers if number < C]
        else:
            possibleanswers = [number for  number in possibleanswers if number >= C]

        low = possibleanswers[0]
        high = possibleanswers[-1]
        span = high - low
        middle = (span/2)+low
        C = round(int(middle))
        greaterthan = input("Is your number greater than {}?".format(C)).strip().lower()
        if greaterthan == "yes":
            possibleanswers = [number for number in possibleanswers if number > C]
        else:
            possibleanswers = [number for number in possibleanswers if number <= C]
            
print("Your number is {}! Well done.".format(*possibleanswers))
