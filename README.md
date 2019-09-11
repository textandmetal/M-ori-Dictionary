# Māori-Dictionary

A small collection of words, word combinations, placenames, proverbs etc

Using a list of [3000 words](https://www.ef.edu/english-resources/english-vocabulary/top-3000-words/) as a keyword search at https://maoridictionary.co.nz we were able to return 14,561 unique results.


    #!/usr/bin/env bash
    # This script was written by textandmetal@gmail.com

    # Read from dictionary file and download as keyword search from maoridictionary.co.nz
    while read i; do 
      clear
      wget "https://maoridictionary.co.nz/search?idiom=&phrase=&proverb=&loan=&histLoanWords=&keywords=$i"
    done < dictionary.txt

The list was generated with:

    grep -h "\<h2\ class\=\"title" | sed s/\<h2\ class=\"title\ \ \\>//" | sort | unique > list.txt

They tidied up in vim with a macro.
