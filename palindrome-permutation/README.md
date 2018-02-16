# Leetcode: Palindrome Permutation     :BLOG:Medium:


---

Palindrome Permutation  

---

Similar Problems:  

-   Tag: [#palindrome](https://brain.dennyzhang.com/tag/palindrome)

---

Given a string, determine if a permutation of the string could form a palindrome.  

For example,  
"code" -> False, "aab" -> True, "carerac" -> True.  

Github: [challenges-leetcode-interesting](https://github.com/DennyZhang/challenges-leetcode-interesting/tree/master/palindrome-permutation)  

Credits To: [leetcode.com](https://leetcode.com/problems/palindrome-permutation/description/)  

Leave me comments, if you have better ways to solve.  

    ## Blog link: https://brain.dennyzhang.com/palindrome-permutation
    ## Basic Ideas: hashmap
    ##
    ## Complexity: Time O(n), Space O(1)
    ##             The character is a limited set, thus the space is O(1)
    class Solution:
        def canPermutePalindrome(self, s):
            """
            :type s: str
            :rtype: bool
            """
            import collections
            d = collections.defaultdict(lambda: 0)
            for ch in s:
                d[ch] += 1
    
            odd_count = 0
            for ch in d:
                if d[ch]%2 == 1: odd_count += 1
                if odd_count >= 2: return False
            return True