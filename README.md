# Programming Language: Python

# Question 1: Write a query that will display the results of the database diagram.

    SELECT
    r.race_year,
    r.race_name,
    d.driver_name,
    d.driver_nationality,
    c.team,
    r.points
    FROM
    results r
    INNER JOIN drivers d ON r.driver_id = d.driver_id
    INNER JOIN races r2 ON r.race_id = r2.race_id
    INNER JOIN circuits c ON r2.circuit_id = c.circuit_id
    WHERE
    r.race_year = 2020
    ORDER BY
    r.points DESC;


# Question 2: Write a Python function that checks whether a word or a phrase is Palindrome or not.

    def checkPalindrome(word):
      word = word.lower().replace(" ", "")
      return word == word[::-1]

# Example usage:
    print(checkPalindrome("madam"))
    print(checkPalindrome("kayak"))  
    print(checkPalindrome("racecar"))  
    print(checkPalindrome("nurses run"))


# Question 3: Write a Python function to check whether a string is a pangram or not.

    def checkPangram(s):
    List = []
    for i in range(26):
        List.append(False)
    for c in s.lower():
        if not c == " ":
            List[ord(c) - ord('a')] = True
    for ch in List:
        if ch == False:
            return False
    return True

# Program to test above functions
    sentence = "The quick brown fox jumps over the little lazy dog"

    if checkPangram(sentence):
    print('"' + sentence + '"')
    print("\nis a pangram")
    else:
    print('"' + sentence + '"')
    print("\nis not a pangram")




# Question 4: Write a program that takes an integer as input and returns the integer with reversed digit ordering.
    def reverse_digit(num):
    is_negative = num < 0
    reversed_str = str(abs(num))[::-1].lstrip('0')
    reversed_num = int(reversed_str)
    return -reversed_num if is_negative else reversed_num

# Examples
    print(reverse_digit(500)) 
    print(reverse_digit(-56))  
    print(reverse_digit(-90))  
    print(reverse_digit(91))


# Question 5: Write a program that accepts a string as input, capitalizes the first letter of each word in  the string, and then returns the result string.

    def words(string):
      words = string.split()
      words = [word.capitalize() for word in words]
      return " ".join(words)

# Examples:
    print(words("hi"))                 
    print(words("i love programming"))  
