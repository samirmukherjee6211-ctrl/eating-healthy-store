# Deployment Guide

## Deploy to Vercel

### Step 1: Push to GitHub

```bash
# Initialize git repository (if not already done)
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit - Eating Healthy store"

# Add your GitHub repository
git remote add origin https://github.com/YOUR_USERNAME/eating-healthy-store.git

# Push to GitHub
git push -u origin main
```

### Step 2: Deploy on Vercel

1. Go to [vercel.com](https://vercel.com)
2. Click "Add New Project"
3. Import your GitHub repository
4. Vercel will auto-detect the settings
5. Click "Deploy"

### Step 3: Configure Custom Domain

1. In Vercel dashboard, go to your project
2. Click "Settings" → "Domains"
3. Add your domain: `www.eatinghealthly.shop`
4. Follow Vercel's DNS configuration instructions
5. Update your domain's DNS records:
   - Add CNAME record: `www` → `cname.vercel-dns.com`
   - Or A record pointing to Vercel's IP

### Step 4: Configure Dodo Payments Success URLs

Update your Dodo Payments products with the correct success URLs:

1. **eBook Only ($19.99)**
   - Product ID: `pdt_0NXJET4Qf0Ieqli4Mp6wQ`
   - Success URL: `https://www.eatinghealthly.shop/thankyou.html`

2. **Discounted Bundle ($29.98)**
   - Product ID: `pdt_0NXJEoeS9L1S3pXqDouHr`
   - Success URL: `https://www.eatinghealthly.shop/thankyou-bundle.html?discount=true`

3. **Full Bundle ($39.98)**
   - Product ID: `pdt_0NXJEvovUCrPUR7LvI5CA`
   - Success URL: `https://www.eatinghealthly.shop/thankyou-bundle.html`

### Step 5: Test Everything

1. Visit your live site: `https://www.eatinghealthly.shop`
2. Test the checkout flow
3. Verify payment redirects work
4. Test download links on thank you pages
5. Check mobile responsiveness

## Environment Variables (if needed later)

If you need to add environment variables:

1. Go to Vercel dashboard → Settings → Environment Variables
2. Add your variables
3. Redeploy

## Troubleshooting

### Images not loading
- Make sure all image files are committed to git
- Check file names match exactly (case-sensitive)

### Payment redirect not working
- Verify Dodo Payments success URLs are correct
- Check that URLs use HTTPS

### Custom domain not working
- Wait 24-48 hours for DNS propagation
- Verify DNS records are correct
- Check Vercel domain settings

## Support

For deployment issues, contact Vercel support or check their [documentation](https://vercel.com/docs).
