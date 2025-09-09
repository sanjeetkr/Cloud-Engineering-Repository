# Cloud Repository

--PASSWORDLESS AUTHENTICATION SETUP for Github--
====================================================================
The below steps are for MacBook

Setting Up SSH Keys for GitHub
Using SSH keys allows you to connect to GitHub without supplying your username and password each time.
Step 1: Check for Existing SSH Keys
1. Open your terminal.
2. Enter the following command to check for existing SSH keys: ls ~/.ssh
3. If you see files like id_rsa or id_ed25519, you might already have an SSH key. If not, continue to Step 2 to generate one.
Step 2: Generate a New SSH Key
1. Type the following command (replace your_email@example.com with your GitHub email): ssh-keygen -t ed25519 -C "your_email@example.com" Note: If you get an error about ed25519, use -t rsa instead.
2. When prompted:
    * Press Enter to save the key in the default location
Step 3: Start the SSH Agent
1. Start the SSH agent in the background with: eval "$(ssh-agent -s)"
2. Add your SSH key to the agent: ssh-add ~/.ssh/id_ed25519 Adjust the path if your key has a different name.
Step 4: Add SSH Key to GitHub
1. Copy your public SSH key to the clipboard: cat ~/.ssh/id_ed25519.pub Copy the output that appears in the terminal.
2. Go to GitHub SSH Keys in your browser.
3. Click "New SSH Key".
4. Paste your key into the "Key" field and add a descriptive title (e.g., "My Mac").
5. Click "Add SSH Key".
Step 5: Test SSH Connection to GitHub
1. In your terminal, type the following command: ssh -T git@github.com
2. If successful, you'll see a message like: Hi username! You've successfully authenticated, but GitHub does not provide shell access.
Step 6: Configure SSH for GitHub (Optional)
To ensure Git uses SSH instead of HTTPS by default:
1. Set GitHub to always use SSH by running: git config --global url."git@github.com:".insteadOf "https://github.com/"

