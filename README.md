# question-no-2900
Solution to the question no 2900 on leet code 

2900. Longest Unequal Adjacent Groups Subsequence I

You are given a string array words and a binary array groups both of length n, where words[i] is associated with groups[i].

Your task is to select the longest alternating subsequence from words. A subsequence of words is alternating if for any two consecutive strings in the sequence, their corresponding elements in the binary array groups differ. Essentially, you are to choose strings such that adjacent elements have non-matching corresponding bits in the groups array.

Formally, you need to find the longest subsequence of an array of indices [0, 1, ..., n - 1] denoted as [i0, i1, ..., ik-1], such that groups[ij] != groups[ij+1] for each 0 <= j < k - 1 and then find the words corresponding to these indices.

Return the selected subsequence. If there are multiple answers, return any of them.

Note: The elements in words are distinct.

Solution:

How it works:
Initialization:

dp[i] stores the length of the longest valid subsequence ending at index i.

prev[i] stores the index of the previous word in the sequence.

Main logic:

For each word i, it looks back at all previous words j to find a valid one (with a different group).

It updates dp[i] and prev[i] to build the longest sequence possible ending at i.

Reconstruction:

After finding the end of the longest sequence (endIndex), it backtracks using prev[] to collect the words.

Result:

Returns the longest sequence of words with alternating group values.

Example:
Given:words = ["a", "b", "c", "d"]
groups = [1, 2, 1, 2]
