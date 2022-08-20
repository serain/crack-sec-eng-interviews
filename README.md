# Cracking the Security Engineer Interviews

> This interview preparation checklist was assembled by collecting information from various sources _before_ I sat any interviews. The following doesn't reflect anything I learned while interviewing.

This is a list of technical topics I reviewed before interviewing for Security Engineer positions at some high-profile tech companies. Behavioral interviews are not in scope here.

Some of these companies will be more interested in your software and infrastructure engineering skills than your security credentials. You should be comfortable interviewing at a mid-level Software Engineer level or above, regardless of the security role and position you are applying for. You should also be comfortable with designing systems with scale in mind and understand some of the issues you're likely to encounter there.

A few general guidelines:

- For everything discussed here you should have more than surface level knowledge, but not necessarily in-depth. If you bring something up, expect interviewers to press you on it.
- Be ready to discuss some interesting projects you've tackled in the past. This is important.
- Non-coding interviews will tend to be "high breadth, medium depth" and fast-paced.
- Make sure you treat coding interviews as a pairing session with the interviewer; explain everything you are doing and why you're doing it.
- You've got an hour to convince the interviewer that you know a lot of stuff. Don't hesitate to volunteer information if you have something interesting to say related to the topic at hand; if you can go deeper then go deeper, don't just answer the questions.
- Where possible, steer the interview in directions you are most knowledgeable in.
- As always, don't be afraid to say you don't know something before giving it your best guess.
- Be pleasant; they're trying to figure out if you're the kind of person they want to work with.

Finally, you'll need to tailor this to whatever role you're applying for; if you're applying for a Mobile Security Engineer position you'll obviously need to prepare some of that.

## Table of Contents

### Fundamentals

- [OS & Memory Management](#os--memory-management)
- [Memory Corruption](#memory-corruption)
- [Linux](#linux)
- [Networking](#networking)
- [Cryptography](#cryptography)

### Engineering

- [System Design](#system-design)
- [Threat Modelling](#threat-modelling)
- [Algorithms](#algorithms)
- [Data Structures](#data-structures)
- [Python](#python)

### Security

- [Code Review](#code-review)
- [Machine Learning](#machine-learning)
- [Web Application](#wep-application)
- [Infrastructure / k8s / Cloud](#infrastructure--k8s--cloud)
- [Red Teaming](#red-teaming)
- [Detection](#detection)
- [Incident Management](#incident-management)

## OS & Memory Management

You should be able to discuss operating system fundamentals, memory management, and common issues you may encounter.

### YouTube Playlists

- [Harvey Mudd College Operating Systems class](https://www.youtube.com/playlist?list=PL2Yggtk_pK6-R9ehjj0AoTnWrNOLChuld)

### Readings

- [MIT's Software Construction class](https://web.mit.edu/6.005/www/fa15/) (especially chapters on concurrency, thread safety etc.)

### Question Prep

- Memory leaks
- Dynamic linker
- Memory layout of a program
- Heap
- Stack
- Race conditions
- Processes
- Threads
- Deadlocks
- Concurrency issues
- Memory paging
- Pipes
- Scheduling
- Pointers

## Memory Corruption

You're unlikely to be quizzed in-depth on binary exploitation for the average Security Engineer role, but you should know the basics and be capable of explaining their remediations.

### Question Prep

- Stack buffer overflows
- Heap overflows
- ROP chaining
- Return to libc
- DEP
- NX
- ASLR
- Compiler security features of GCC and how they work
- Smart pointers

## Linux

You should understand Linux' security model, why SELinux/AppArmor exist and what they can protect against, and show that you can debug your way around in Linux. Probably a good idea to be able to talk about eBPF and how it's being used by some projects.

### Question Prep

- SELinux
- AppArmor
- Seccomp
- Capabilities
- Namespaces
- cgroups
- Access controls: MAC vs DAC
- /proc
- dmesg
- syslog
- strace/ptrace/ltrace
- ldd
- systemd
- eBPF

## Networking

Be able to talk about some of these things. For example if the topic is "TLS" you should be able to describe the handshake, how a session master key is derived, the kind of crypto involved... What problems are gRPC and HTTP/2.0 solving and how are they doing that?

### Question Prep

- OSI 7 Layers
- Explain NAT
- Describe TCP handshake
- Explain how traceroute works
- DNS (SOA, CNAME...)
- BGP
- TLS (handshakes, encryption, signing etc.)
- gRPC
- HTTP 2.0

## Cryptography

Be capable of explaining each of these in details, including flows, parameters involved, crypto decisions that could be made, the problems they are solving...

### Question Prep

- HMAC
- U2F / FIDO
- PKI
- JWT
- OAuth
- OpenID Connect
- PKCE

## System Design

There's a ton of mock system design interviews on YouTube. Watch them during your lunch break, on the toilet, before you go to bed...

Practice by mocking these out yourself and talk to yourself while you're doing it; pretend you're both the interviewer and the interviewee.

Keep in mind that most of the companies you're talking to are delivering services on a massive scale, and that'll also be the case for their internal security solutions. You need to be able to explain how and why your solution can scale to their needs.

### YouTube Playlists

- [Exponent Mock Interviews](https://www.youtube.com/watch?v=KYExYE_9nIY&list=PLrtCHHeadkHp92TyPt1Fj452_VGLipJnL)

### Articles

- [System Design Primer](https://github.com/donnemartin/system-design-primer)

### Books

- [System Design Interview](https://www.goodreads.com/en/book/show/54109255)

## Threat Modelling

If you're comfortable designing systems, you should be comfortable interpreting system designs and identifying the points at risk. Cover trust boundaries and explain why issues often happen at the intersection of systems and trust boundaries. Cover the split responsability model for modern environments and focus on what's in scope.

Practice by drawing diagrams for systems you are familiar with and model those threats.

I take the following approach:

1. Flag assets of interest to attackers
2. Identify threat actors
3. Start from entry points available to each threat actor
4. Dump all attack vectors you can think of
5. Discuss mitigations

## Algorithms

Start reviewing the following topics with [Geeks for Geeks](https://www.geeksforgeeks.org/) and then start grinding [LeetCode](https://leetcode.com/). You should be smashing through medium level LeetCode challenges and the occasional hard challenge. Don't listen to the haters; this can be a lot of fun if you get into it.

### Books

- [Cracking the Coding Interview](https://www.crackingthecodinginterview.com/)

### General

- Big O notation
- No free lunch theorem

### String/Array

- Reverse an array without affecting special characters
- Given a string, find the length of its longest running substring with no repeating characters
- Given two strings, detect if one is a Caesar cipher of the other
- Given a list of string words of size n, check if there is any pair of words that can be joined (in any order) to form a palindrome, then return the pair of words forming a palindrome.
- Find all palindromic decompositions of a given string s.

### Linked List

- Insertion of node in a linked list
- Delete a given node in a linked list
- Merge a linked list into another at alternate positions
- Detect and remove loop in a linked list
- Reverse a Linked List

### Sorting

- Quicksort
- Merge sort
- Bubble sort
- Insertion sort
- Selection sort
- Heap sort

### Searching

- Linear search
- Binary search
- Bloom filter
- Hashmap / Hashtable

### Graph

- Breadth First Search
- Depth First Search
- Shortest path from source to all vertices (Dijkstra's algorithm)
- Minimum Spanning Tree (Prim's algorithm)

### Binary Tree

- Find minimum depth of Binary Tree
- Check whether binary tree is a full binary tree or not

## Data Structures

You should know the time and space complexity of common operations on these data structures along with their use cases.

- Dictionaries, Maps, Hashtables
- Heaps
- Arrays
- Sets and multisets
- Stacks (LIFO)
- Queues (FIFO)
- Priority queues
- Linked lists
- Binary search tree

## Python

You'll be expected to be fluent with at least one programming language. Python is a good choice for interviews. You should know how memory is managed, and a bit about how data structures are implemented under the hood and the time complexity of common operations on them.

### Books

- [Python tricks: the book](https://www.goodreads.com/en/book/show/36990732)

### Articles

- [Time Complexity (Python docs)](https://wiki.python.org/moin/TimeComplexity)

### YouTube Playlists

- [Python Interview Questions](https://www.youtube.com/watch?v=vtRKuNmA-qc&list=PLexlA-2msjTRjdA3pUJBv0g-SL9ZeSWDV)

### Question Prep

- Generators
- dunder functions
- debugging with pdb
- Garbage collection in Python

## Code Review

Be comfortable performing a security code review during an interview. Pick a few "Damn Vulnerable" web apps and make sure you can spot all the issues in a timely manner.

### Targets

- [Damn Vulnerable Python Web Application](https://github.com/anxolerd/dvpwa)

## Machine Learning

I was applying for roles to work in and around ML. Replace this section with whatever makes sense for the role you are applying for.

### Articles

- [Stealing Neural Networks With Model Extraction Attacks](https://www.youtube.com/watch?v=Jxvi9eCDrnQ)
- [Demystifying the Membership Inference Attack](https://medium.com/disaitek/demystifying-the-membership-inference-attack-e33e510a0c39)
- [Poisoning attacks on Machine Learning](https://towardsdatascience.com/poisoning-attacks-on-machine-learning-1ff247c254db)
- [Zen and the Art of Adversarial Machine Learning](https://github.com/moohax/Talks/blob/master/slides/Blackhat_EU_21.pdfs)

### Question Prep

- Neural networks
- Neural networks as universal approximators and caveats
- Reinforcement learning
- Activation functions, why and why these?
- Adversarial samples and defenses
- Random forests
- Linear regression
- Decision trees
- Model extraction approaches
- Membership inferrence and limitations
- Poisoning attacks, different types depending on attacker access

## Wep Application

All the basic web app stuff.

### Question Prep

- Password storage, salt and pepper
- Deserialization
- SQL injection, XSS, CSRF, SSRF, XXE...
- Content Security Policy
- Subresource Integrity
- Same-Origin Policy
- DNS rebinding
- h2c smuggling
- http request smuggling
- cookie security

## Infrastructure / k8s / Cloud

All the basic cloud stuff.

### Articles

- [NSA Kubernetes Hardening Guide](https://www.nsa.gov/Press-Room/News-Highlights/Article/Article/2716980/nsa-cisa-release-kubernetes-hardening-guidance/)

### Question Prep

- Secret management (rotation, Vault, managed solutions, k8s solutions...)
- Confused deputy issues
- Service to service auth/z
- ABAC vs RBAC
- Kyverno
- Pod Security Admission
- Container sandboxing, gVisor, Kata, Firecracker

## Red Teaming

All the basic red team stuff. Be capable of explaining a full attack chain, and give examples for each step. Explain C2 infrastructure, persistence, egress...

## Detection

Have some knowledge of indicators of compromise and detection methods, especially for any offensive stuff you are ready to talk about.

## Incident Management

Show that you know what to do when shit hits the fan. How do you organise incident response, roles/responsibilities etc. Explain the value of post-mortems and remedial actions.
