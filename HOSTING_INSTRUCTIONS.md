# How to Host MethodX Solutions on GitHub Pages (with Free HTTPS)

Since your code is already in a GitHub repository, you can host your website completely for free directly from GitHub. This is the easiest method and **GitHub automatically provides a free SSL/HTTPS certificate for you.**

Follow these steps to deploy:

## Step 1: Turn on GitHub Pages
1. Go to your repository on **GitHub.com**.
2. Click on the **Settings** tab (the gear icon near the top right).
3. On the left sidebar, scroll down and click on **Pages**.
4. Under the "Build and deployment" section, look for the **Source** dropdown and select **Deploy from a branch**.
5. Under **Branch**, select `main` (or `master`), leave the folder as `/ (root)`, and click **Save**.

*Within 1-2 minutes, your website will be live! GitHub will show a message at the top of that settings page saying: "Your site is live at `https://[your-username].github.io/[your-repo-name]`".*

## Step 2: Connect Your Custom Domain (`methodxsol.com`)
Now that GitHub is hosting your site, you just need to tell it to use your actual domain name:
1. Stay on that exact same **Pages** settings screen in GitHub.
2. Scroll down to the **Custom domain** section.
3. Type in your domain name (e.g., `methodxsol.com`) and click **Save**.
4. GitHub will automatically start provisioning your free HTTPS certificate (this check might take a few minutes). Check the box that says **Enforce HTTPS** once it becomes available/clickable.

## Step 3: Point Your DNS to GitHub
Finally, you just need to go to whoever you bought your domain from (e.g., GoDaddy, Namecheap, Route 53) and point your domain to GitHub's servers:
1. Delete any existing "A records" that are pointing to your old AWS S3 bucket.
2. Create **four A Records** pointing to GitHub's IP addresses:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
3. Create a **CNAME Record** for `www` and point it to your default GitHub Pages URL (e.g., `[your-username].github.io`).

**That's it!** Every time you push a new `git commit` to your repository, your live website will automatically update instantly, and it will remain fully secured with HTTPS. You can completely turn off your AWS S3 bucket.
