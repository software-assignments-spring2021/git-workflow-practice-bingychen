# Dependency Confusion: How I Hacked Into Apple, Microsoft and Dozens of Other Companies
https://medium.com/@alex.birsan/dependency-confusion-4a5d60fec610

This article talks about a new vulnerability found recently in 2020 by Alex Birsan. This new vulnerability&mdash;called Dependency Confusion&mdash;exploits the fact that you are essentially trusting package installers like npm, PyPi, and RubyGems to run code on your machine. There is no guarantee that the package you are installing is malware-free. Due to this, many attackers tend to make fake packages with names very similar to known public packages, such as changing just one or two letters so the unattentive developer might write a typo when trying to install a new package. <br> 
<br>
To test the extent of this vulnerability and the range of companies it affects, Alex Birsan looked inside the *package.json* file of companies like PayPal and found some of the dependencies the companies use internally are publicly-known packages, while others are private packages developed by the company for the company. The most interesting part about this is the way this could be exploited. By creating malicious packages using the names of the private dependencies, when a company tries to install said package, will they install the public malicious package or the private 'real' package? Turns out, that by playing around with the version numbers, the attacker can always force any package installer to choose the public one over the private. This vulnerability was found in many big-name companies like Shopify, Netflix, Yelp, Uber, PayPal and Apple as part of their bug bounty programs. By submitting these findings, Birsan and his team was able to claim an average of $30,000 from *each* company. Incredible!

## Comments
Very interesting article! I will be sure to to double check my package names anytime before I install. <br>
-Varun Bhardwaj
