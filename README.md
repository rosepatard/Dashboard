# 📊 Reuters EMEA Planning Hub

A comprehensive suite of planning operations tools built for the Thomson Reuters EMEA advertising team.

---

## 🎯 Overview

The Reuters EMEA Planning Hub is an integrated platform that streamlines planning operations across four key workflows:

1. **Media Plan Tracker** - Track planner workload (new MPs and revisions)
2. **Campaign Reporting Request** - Request reporting setup for live campaigns
3. **Campaign Logger** - Log Direct and Programmatic campaigns to regional trackers
4. **Idea Box** - Submit process improvement ideas
5. **Campaign Dashboard** - Interactive dashboard to view and manage all campaigns

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────┐
│                  GitHub Pages                        │
│  ┌──────────────────┐    ┌───────────────────────┐ │
│  │  Planning Hub    │    │  Campaign Dashboard   │ │
│  │  (index.html)    │    │  (dashboard.html)     │ │
│  └────────┬─────────┘    └──────────┬────────────┘ │
└───────────┼────────────────────────┼────────────────┘
            │                         │
            ▼                         ▼
    ┌───────────────────────────────────────────┐
    │        Google Apps Scripts (APIs)          │
    ├───────────────────────────────────────────┤
    │  • MP Tracker API                         │
    │  • Reporting Email API                    │
    │  • Campaign Logger API                    │
    │  • Idea Box API                           │
    │  • Dashboard API (Read/Write)             │
    └──────────────┬────────────────────────────┘
                   │
                   ▼
    ┌───────────────────────────────────────────┐
    │         Google Sheets (Storage)            │
    ├───────────────────────────────────────────┤
    │  • MP Tracker Data                        │
    │  • EMEA Campaign Log (Europe/MENA tabs)   │
    │  • Team Ideas                             │
    └───────────────────────────────────────────┘
```

---

## 🚀 Features

### Planning Hub (index.html)

**Media Plan Tracker**
- Two-click logging for new media plans and revisions
- Captures planner name and timestamp
- Logs to Google Sheet for workload analysis

**Campaign Reporting Request**
- Form for requesting campaign reporting setup
- Captures: Campaign details, KPIs, components, frequency, PCA needs
- Sends formatted email to Customer Success Manager

**Campaign Logger**
- Seller/Market selection (5 sellers across Europe and MENA)
- Conditional forms for Direct vs Programmatic campaigns
- Writes to regional tabs (Europe or Middle East)
- Tracks: Team members, links, dates, budget, status

**Idea Box**
- Categorized idea submission
- Impact assessment
- Logs to Google Sheet for tracking

### Campaign Dashboard (dashboard.html)

**Viewing Features**
- Unified view of all Europe and Middle East campaigns
- Real-time stats cards (Total, by Region, by Type)
- Multi-filter system (Region, Seller, CM Owner, Type, Status)
- Search by campaign name or seller
- Sortable columns (Start Date, End Date, Budget)

**Editing Features**
- Inline campaign editing
- Update: Status, Start/End dates, PIO/GAM/Burt links, Notes
- Changes save directly to Google Sheet
- Auto-refresh after edits

**Data Display**
- Events participation
- Social/Deal status
- Team members (CS, CM, PM, AdOps)
- Clickable links (PIO, GAM, Burt)
- Budget with currency
- Properly formatted dates (DD/MM/YYYY)

---

## 📋 Tech Stack

**Frontend**
- HTML5, CSS3
- React 18 (Dashboard)
- Vanilla JavaScript (Hub)
- Responsive design
- IBM Plex Mono + DM Sans fonts

**Backend**
- Google Apps Script (API layer)
- Google Sheets (Database)

**Hosting**
- GitHub Pages (Static hosting)

**Design**
- Reuters brand colors (#d64000 orange, #212223 dark grey)
- Dark theme with orange accents
- Mobile-responsive

---

## 📊 Data Structure

### EMEA Campaign Log Sheet

**Two Tabs:**
- **Europe** - Dana Whitaker, Emma Ball, Katurah Horton campaigns
- **Middle East** - Cian Buckley, Tony Sarkis campaigns

**Column Structure (20 columns):**
```
1.  Timestamp
2.  Seller/Market
3.  Campaign Type (Direct/Programmatic)
4.  Campaign Name
5.  Events (Yes/No)
6.  CS Owner / Op Owner
7.  CM Owner
8.  Project Owner / Programmatic Type
9.  AdOps Owner
10. Social / Deal Accepted
11. PIO Link
12. GAM Link
13. Burt Link
14. Currency
15. Net Total
16. Start Date
17. End Date
18. Status of Campaign
19. Screengrabs (Direct only)
20. Notes/Comments/Updates
```

### Team Ideas Sheet

**Column Structure (7 columns):**
```
1. Timestamp
2. Submitted By
3. Category
4. Idea Title
5. Description
6. Potential Impact
7. Status (New/Reviewed/Implemented)
```

### MP Tracker Data Sheet

**Column Structure (3 columns):**
```
1. Timestamp (European format: DD/MM/YYYY HH:MM)
2. User (Planner name)
3. Type (New Media Plan / Revision)
```

---

## 🔧 Setup & Deployment

### Prerequisites
- Google account
- GitHub account
- GitHub Pages enabled repository

### Quick Start

1. **Clone/Download** the repository files
2. **Deploy Apps Scripts** (see detailed guides in setup docs)
3. **Update URLs** in HTML files with your Apps Script deployment URLs
4. **Push to GitHub Pages**
5. **Share URLs** with your team

### Detailed Setup Guides
- [Campaign Logger Setup](CAMPAIGN_LOGGER_SETUP.md)
- [Dashboard Setup](DASHBOARD_SETUP.md)

---

## 🔗 URLs & Endpoints

### Production URLs
- **Planning Hub:** `https://rosepatard.github.io/[repo-name]/index.html`
- **Campaign Dashboard:** `https://rosepatard.github.io/[repo-name]/dashboard.html`

### Apps Script Endpoints
```javascript
// Media Plan Tracker
const MP_TRACKER_URL = 'https://script.google.com/macros/s/.../exec';

// Reporting Email
const REPORTING_EMAIL_URL = 'https://script.google.com/macros/s/.../exec';

// Campaign Logger
const CAMPAIGN_LOGGER_URL = 'https://script.google.com/macros/s/.../exec';

// Idea Box
const IDEA_BOX_URL = 'https://script.google.com/macros/s/.../exec';

// Dashboard API
const DASHBOARD_API_URL = 'https://script.google.com/macros/s/.../exec';
```

---

## 👥 User Roles & Permissions

### Planners
- ✅ Log media plans and revisions
- ✅ Request campaign reporting
- ✅ Log new campaigns
- ✅ Submit ideas
- ✅ View dashboard
- ✅ Edit campaigns (status, dates, links, notes)

### Customer Success Manager (Rose Patard)
- ✅ All planner permissions
- ✅ Receives campaign reporting requests
- ✅ Manages Team Ideas sheet
- ✅ Full dashboard access

### Campaign Managers (Nyasson Allen, Chithiran Pugazhenthi)
- ✅ All planner permissions
- ✅ Edit campaigns on dashboard
- ✅ Update campaign status and notes

---

## 📱 Browser Support

- ✅ Chrome (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ✅ Mobile browsers (iOS Safari, Chrome Android)

---

## 🎨 Design System

### Colors
```css
--reuters-orange: #d64000
--reuters-dark: #212223
--reuters-grey: #404040
--bg-primary: #0a0a0b (dashboard only)
--bg-secondary: #16161a (dashboard only)
--bg-card: #1e1e24 (dashboard only)
```

### Typography
- **Display Font:** IBM Plex Mono (dashboard)
- **Body Font:** DM Sans (dashboard) / Inter (hub)
- **Monospace:** IBM Plex Mono

### Components
- Status pills (color-coded by status)
- Type badges (Direct = orange, Programmatic = purple)
- Modal overlays
- Sortable table headers
- Filter dropdowns
- Toast notifications

---

## 🔐 Security & Privacy

### Access Control
- **Planning Hub:** Public (anyone with link)
- **Campaign Dashboard:** Public (anyone with link can view AND edit)
- **Google Sheets:** Private (only authorized Google accounts)

### Data Privacy
- Username stored in browser localStorage
- No passwords or authentication required
- All data stored in Google Sheets (Thomson Reuters controlled)

### Recommendations
- Share URLs only with team members
- Do not post dashboard URL publicly
- Regularly review Google Sheets sharing settings

---

## 📈 Usage Analytics

### What Gets Tracked
The system tracks:
- Media plan creation events (timestamp, user, type)
- Campaign logging events (full campaign details)
- Idea submissions (timestamp, user, category, impact)
- Campaign updates (via dashboard editing)

### What Doesn't Get Tracked
- Page views
- User sessions
- Personal information beyond name

---

## 🐛 Troubleshooting

### Common Issues

**Problem:** Form submits but nothing appears in Google Sheet
- **Solution:** Check Apps Script URL is correct and script is deployed with "Who has access: Anyone"

**Problem:** Dashboard shows "Loading..." forever
- **Solution:** 
  1. Check DASHBOARD_API_URL is set correctly
  2. Open browser console (F12) for error details
  3. Verify Apps Script is deployed as Web App

**Problem:** CORS errors when editing campaigns
- **Solution:** Already fixed with `mode: 'no-cors'` in fetch requests

**Problem:** Dates showing weird format (ISO timestamps)
- **Solution:** Already fixed with date formatting functions

**Problem:** "Sheet not found" errors
- **Solution:** Ensure sheet tabs are named exactly "Europe" and "Middle East" (case-sensitive)

**Problem:** Email not receiving reporting requests
- **Solution:** Thomson Reuters blocks external Gmail senders - this is expected behavior

---

## 🔄 Maintenance

### Regular Tasks
- Review Team Ideas sheet weekly
- Archive completed campaigns quarterly
- Update seller list as team changes
- Review and update status options as needed

### Updates & Improvements
When adding new features:
1. Update Apps Script code
2. Deploy new version (Deploy → Manage deployments → Edit → New version)
3. Update HTML if needed
4. Push to GitHub Pages
5. Clear browser cache when testing

---

## 📝 Version History

### v3.0 (February 2026)
- ✅ Added Campaign Dashboard with full CRUD operations
- ✅ Added sortable columns (dates, budget)
- ✅ Added CM Owner filter
- ✅ Merged currency with budget display
- ✅ Updated CS Owner options (added Brooke Jorgensen)

### v2.0 (February 2026)
- ✅ Added Campaign Logger with seller/market tracking
- ✅ Added Idea Box
- ✅ Regional tab structure (Europe/Middle East)
- ✅ Four-tile hub interface

### v1.0 (November 2025)
- ✅ Initial Media Plan Tracker
- ✅ Campaign Reporting Request
- ✅ Two-button interface

---

## 👩‍💻 Development Team

**Built by:** Rose Patard  
**Role:** Customer Success & Analytics Manager, EMEA  
**Contact:** rose.patard@thomsonreuters.com

**With feedback from:**
- Nyasson Allen (Campaign Manager)
- Chithiran Pugazhenthi (Campaign Manager)
- Planning team members

---

## 🎓 Learning Resources

### For Customization
- [Google Apps Script Documentation](https://developers.google.com/apps-script)
- [React Documentation](https://react.dev)
- [GitHub Pages Guide](https://docs.github.com/en/pages)

### For Troubleshooting
- Browser console (F12) for JavaScript errors
- Apps Script execution logs for backend errors
- Google Sheet formula errors

---

## 📄 License

Internal use only - Thomson Reuters  
Not for external distribution

---

## 🙏 Acknowledgments

Special thanks to:
- The EMEA planning team for feature requests and testing
- Claude (Anthropic) for development assistance
- The Thomson Reuters team for supporting innovation

---

## 🚀 Future Enhancements

**Potential Features (Backlog):**
- Email notifications when campaign status changes
- Bulk status updates (select multiple campaigns)
- Export to Excel functionality
- Calendar view of campaign timelines
- Integration with Salesforce opportunities
- Mobile app version
- Activity log (audit trail of changes)
- MP Tracker analytics in dashboard
- Team Ideas integration in dashboard
- Automated reporting trigger based on status changes
- Campaign templates for faster logging
- Budget forecasting and tracking
- Performance metrics (CTR, conversions) integration

**Want to add a feature?** Use the Idea Box! 💡

---

## 📞 Support

For technical issues, feature requests, or questions:
1. Submit via **Idea Box** in the Planning Hub
2. Contact Rose Patard directly
3. Check browser console (F12) for error messages
4. Review setup documentation

---

## 📚 Documentation Index

- **README.md** (this file) - Project overview
- **CAMPAIGN_LOGGER_SETUP.md** - Campaign Logger deployment guide
- **DASHBOARD_SETUP.md** - Dashboard deployment guide
- **index.html** - Planning Hub main interface
- **dashboard.html** - Campaign Dashboard interface
- **campaign-logger-script.js** - Campaign Logger Apps Script
- **dashboard-api.js** - Dashboard API Apps Script
- **idea-box-script.js** - Idea Box Apps Script

---

**Last Updated:** February 19, 2026  
**Version:** 3.0  
**Status:** ✅ Production

---

*Built for the Reuters EMEA Planning Team*
