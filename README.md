# THM-Tetrix.exe-CTF-Solution-Analysis
This is my first GitHub documentation! In this write‑up, I break down how I solved a TryHackMe challenge involving a Windows executable named Tetrix.exe. The goal was to extract the hidden flag from the binary.
Step 1 — Identify the File Type

First, I checked what kind of file it was:

file Tetrix.exe

Output:

PE32+ executable for MS Windows 5.02 (GUI), x86-64 (stripped to external PDB)
✔ What this means:

PE32+ → It's a 64‑bit Windows executable

GUI → It opens as a window, not a console app

Stripped → Debug information removed (common in CTFs)

🔍 Step 2 — Search for Readable Strings

Before doing deep reverse engineering, it's always smart to search for readable text inside the binary. Many CTF flags are stored in plaintext.

I used:

strings Tetrix.exe | grep -i THM
✔ Why search for "THM"?

TryHackMe flags almost always start with THM{...}.

🎉 Result

The flag appeared directly in the strings output — no reverse engineering needed.

🏁 Final Flag

The flag was successfully extracted using the strings command.

THM{I_CAN_READ_IT_ALL}

📚 Lessons Learned

Always try simple static analysis before advanced tools.

strings can solve many beginner-level CTF challenges.

Understanding file type info helps you decide what tools to use next.

🚀 Tools Used

Linux Terminal (file, strings, grep)

Kali Linux environment

✨ Final Thoughts

This was a great introduction to binary analysis and a good first GitHub documentation. More write‑ups coming soon!
