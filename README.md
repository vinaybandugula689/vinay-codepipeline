# National Taekwondo Championship - Live Score Website

A dynamic, real-time web application for displaying live taekwondo championship scores with an admin panel for score management.

## 🎯 Features

### Public-Facing Website
- **Live Score Display**: Real-time match scores with automatic updates
- **Multiple Weight Categories**: Support for all standard Fin and Fly weight categories
- **Match Status Tracking**: Live, Upcoming, and Completed matches
- **Responsive Design**: Works perfectly on desktop, tablet, and mobile devices
- **Category Filtering**: Filter matches by weight category
- **Timer Display**: Live round timers for ongoing matches
- **Modern UI**: Beautiful gradient design with animations

### Admin Panel
- **Match Management**: Create, edit, and delete matches
- **Score Updates**: Real-time score adjustment with quick increment buttons
- **Status Control**: Change match status (Upcoming → Live → Finished)
- **Filter System**: View matches by status
- **Persistent Storage**: All changes saved locally

## 📁 Project Structure

```
tkd-championship/
├── index.html          # Main public-facing page
├── admin.html          # Admin control panel
├── styles.css          # Main stylesheet
├── admin-styles.css    # Admin-specific styles
├── app.js              # Main application logic
├── admin.js            # Admin panel logic
└── README.md           # This file
```

## 🚀 Quick Start (Local Setup)

### Option 1: Simple File Opening
1. Download all files to a folder
2. Open `index.html` in your web browser
3. Open `admin.html` in another tab for score management

### Option 2: Local Server (Recommended)
If you have Python installed:

```bash
# Navigate to project folder
cd tkd-championship

# Python 3
python -m http.server 8000

# Open browser to:
# http://localhost:8000
```

Or use any local server:
- VS Code Live Server extension
- Node.js `http-server`
- XAMPP/WAMP/MAMP

## 🌐 Deployment Options (FREE)

Since you don't have a domain, here are the best free hosting options:

### 1. Netlify (RECOMMENDED - Easiest)
**Steps:**
1. Go to https://www.netlify.com/
2. Sign up (free)
3. Drag and drop your project folder
4. Get instant URL like: `your-site.netlify.app`

**Features:**
- Instant deployment
- Free SSL certificate
- Custom domain support (if you get one later)
- Auto-deploy from GitHub

### 2. GitHub Pages
**Steps:**
1. Create GitHub account (free)
2. Create new repository
3. Upload all files
4. Go to Settings → Pages
5. Enable Pages
6. Get URL: `yourusername.github.io/repo-name`

### 3. Vercel
**Steps:**
1. Go to https://vercel.com/
2. Sign up with GitHub
3. Import your repository
4. Deploy automatically
5. Get URL: `your-site.vercel.app`

### 4. Firebase Hosting
**Steps:**
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
```

### 5. Render
- Go to https://render.com/
- Deploy as static site
- Free tier available

## 💾 Data Persistence

Currently, the app uses **localStorage** for data persistence:
- Works perfectly for single-computer setups
- All data stays in the browser
- No backend needed

### Upgrading to Real-Time Database (Optional)

For true multi-device real-time updates, consider:

#### Firebase Realtime Database (FREE TIER)
```javascript
// Add to your HTML
<script src="https://www.gstatic.com/firebasejs/9.x.x/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.x.x/firebase-database.js"></script>

// Initialize Firebase
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  databaseURL: "YOUR_DATABASE_URL"
};
firebase.initializeApp(firebaseConfig);

// Replace localStorage with Firebase
const db = firebase.database();
db.ref('matches').on('value', (snapshot) => {
  matches = snapshot.val();
  renderMatches();
});
```

## 🎮 How to Use

### For Organizers (Admin Panel)

1. **Open Admin Panel**: Navigate to `admin.html`

2. **Add New Match**:
   - Select category and round
   - Enter fighter names and states
   - Set start time
   - Click "Create Match"

3. **Update Live Scores**:
   - Click "Edit" on any match
   - Use +1, +2, +3 buttons to add points
   - Change status to "Live" to show on main page
   - Update round and timer as needed
   - Click "Save Changes"

4. **Manage Matches**:
   - Filter by status (All, Live, Upcoming, Finished)
   - Delete matches if needed
   - Update match details anytime

### For Public Viewers

1. **Open Main Page**: Navigate to `index.html`
2. **View Live Matches**: See all ongoing matches at the top
3. **Filter by Category**: Click category buttons to filter
4. **Check Schedule**: View upcoming matches
5. **See Results**: Check completed matches with winners

## 🎨 Customization

### Change Colors
Edit `styles.css`:
```css
:root {
    --primary-color: #c41e3a;    /* Main red color */
    --secondary-color: #1e4d8b;  /* Blue accent */
    --accent-color: #ffd700;     /* Gold highlights */
}
```

### Add More Categories
Edit both HTML files, find the category sections and add:
```html
<option value="your-category">Your Category Name</option>
```

### Modify Auto-Update Interval
In `app.js`, change the interval (milliseconds):
```javascript
setInterval(() => {
    // Update code
}, 3000); // Change 3000 to desired milliseconds
```

## 📱 Mobile Access

Once deployed, participants and viewers can:
1. Access via any device with the URL
2. Add to home screen on mobile (works like an app)
3. View live scores in real-time
4. No app installation needed

## 🔐 Security Considerations

**Current Setup**: Admin panel is openly accessible
**For Production**: Add authentication:

### Simple Password Protection
```javascript
// Add to admin.js
const ADMIN_PASSWORD = "your-password";
const password = prompt("Enter admin password:");
if (password !== ADMIN_PASSWORD) {
    alert("Access denied!");
    window.location.href = "index.html";
}
```

### Or Use Firebase Auth
- Add Google/Email login
- Restrict database writes to authenticated users

## 🐛 Troubleshooting

### Scores Not Updating
- Check browser console for errors
- Ensure localStorage is enabled
- Try clearing browser cache

### Admin Changes Not Reflecting
- Make sure you're on the same domain/server
- Check if localStorage is working
- Refresh the public page

### Mobile Display Issues
- Clear cache on mobile browser
- Try different browser
- Check if JavaScript is enabled

## 📊 Future Enhancements

Potential additions:
- [ ] Live video streaming integration
- [ ] Bracket/tournament tree visualization
- [ ] Fighter profiles and statistics
- [ ] Photo gallery
- [ ] Multi-language support
- [ ] Export results to PDF/Excel
- [ ] SMS/Email notifications
- [ ] Live commentary feed
- [ ] Sponsor banner rotations
- [ ] Social media integration

## 📞 Support

For issues or questions:
1. Check the browser console for error messages
2. Verify all files are in the same directory
3. Ensure JavaScript is enabled in browser
4. Try a different browser

## 📜 License

Free to use for your championship event. Feel free to modify and customize as needed!

## 🙏 Credits

Built with pure HTML, CSS, and JavaScript - no frameworks needed!

---

**Good luck with your National Taekwondo Championship! 🥋🏆**
# vinay-codepipeline
