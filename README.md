# ATS Resume Scorer

A brutally honest, AI-powered resume analyzer with **streaming responses**, **intelligent caching**, and **accessibility-first design** that helps job seekers pass real ATS systems and land better interviews.

## ✨ Key Features

### 🚀 Core Functionality

- ✅ **Streaming Analysis** - See results appear in real-time as AI generates them
- ✅ **Direct Document Upload** - Preserves formatting, structure, tables, and layout
- ✅ **Multiple Input Methods** - Upload file, paste text, or provide URL
- ✅ **Smart Document Handling** - PDF and DOCX sent directly to API, text files processed as text
- ✅ **Model Selection** - Choose between Gemini 3 Pro Preview, 2.5 Pro, or Flash models
- ✅ **Job Context** - Optional job description or job title/domain for targeted analysis
- ✅ **Interactive Chat** - Ask follow-up questions with streaming responses

### ⚡ Performance & UX

- ✅ **Intelligent Caching** - Results cached for 30 days to avoid redundant API calls
- ✅ **Force Regenerate** - Option to bypass cache and get fresh analysis
- ✅ **Throttled Rendering** - Optimized streaming with 100ms throttle to reduce re-renders
- ✅ **Progress Indicator** - Real-time character and word count during streaming
- ✅ **Rate Limit Handling** - Automatic retry with exponential backoff (1s → 2s → 4s)
- ✅ **Cache Hit Badge** - Visual indicator when loading from cache

### 🔐 Privacy & Storage

- ✅ **Privacy-First** - API key only used client-side, never sent anywhere
- ✅ **Remember API Key** - Optional localStorage persistence with clear warning
- ✅ **Show/Hide API Key** - Toggle visibility with eye icon (👁️/🙈)
- ✅ **Auto-Expire Cache** - Cached analyses automatically deleted after 30 days
- ✅ **Clear Cache** - Manual cache clearing with confirmation

### 📤 Export & Sharing

- ✅ **Export as Markdown** - Download analysis as `.md` file with timestamp
- ✅ **Print/PDF Support** - Print-friendly layout for saving as PDF
- ✅ **Clean Print Layout** - Optimized CSS hides UI elements, shows only results

### ♿ Accessibility

- ✅ **ARIA Labels** - All interactive elements properly labeled for screen readers
- ✅ **ARIA Live Regions** - Loading states and notifications announced to screen readers
- ✅ **Keyboard Navigation** - Full keyboard support (Enter/Space on file upload)
- ✅ **Keyboard Shortcuts** - Ctrl/Cmd + Enter to analyze from anywhere
- ✅ **Focus Management** - Proper tab order and focus indicators

### 🛠️ Technical

- ✅ **Single File** - Everything in one HTML file, easy to deploy
- ✅ **No Build Tools** - Pure HTML/CSS/JavaScript, works out of the box
- ✅ **No Dependencies** - Only uses Marked.js CDN for markdown rendering
- ✅ **Modern Features** - Fetch API, Server-Sent Events, localStorage

## 🚀 Quick Start

### 1. Get a Gemini API Key

1. Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Click "Create API Key"
3. Copy your key (it's free with rate limits)

### 2. Access the Live Tool

🌐 **Live Demo**: [https://subhayu99.github.io/brutal-ats-scorer](https://subhayu99.github.io/brutal-ats-scorer)

Just visit the link above and start using it immediately!

### 3. Deploy Your Own Instance (Optional)

Want to customize or host your own version?

#### Option A: Fork & Deploy

1. Fork this repository: [github.com/subhayu99/brutal-ats-scorer](https://github.com/subhayu99/brutal-ats-scorer)
2. Go to **Settings** → **Pages**
3. Select branch `main` and folder `/ (root)` → **Save**
4. Your site will be live at `https://your-username.github.io/brutal-ats-scorer`

#### Option B: Clone & Deploy

```bash
git clone https://github.com/subhayu99/brutal-ats-scorer.git
cd brutal-ats-scorer
# Rename ats-scorer.html to index.html
mv ats-scorer.html index.html
git add index.html
git commit -m "Deploy ATS Resume Scorer"
git push origin main
```

#### Option C: Download Single File

1. Download `ats-scorer.html`
2. Open it directly in your browser (works offline!)
3. No server needed - runs 100% client-side

### 4. Use the Tool

1. Open the live site or your deployed instance
2. Enter your Gemini API key (optionally save it for future use)
3. Select your preferred model
4. Add job context or job title (optional)
5. Upload your resume (PDF, DOCX, TXT, YAML, MD)
6. Paste job description (optional)
7. Click **ANALYZE RESUME** (or press Ctrl/Cmd + Enter)
8. Watch results stream in real-time with live progress
9. Export as Markdown or Print/Save as PDF
10. Ask follow-up questions in the chat

## 📁 Supported File Formats

### Direct Document Upload (Preserves Structure)

- **PDF** - Best for maintaining visual layout
- **DOCX** - Fully supported with formatting

### Text Extraction

- **TXT** - Plain text
- **YAML** - Structured data (e.g., RenderCV)
- **MD** - Markdown files

## 🤖 Model Comparison

| Model | Speed | Quality | Cost | Best For |
|-------|-------|---------|------|----------|
| Gemini 3 Pro Preview | ⚡⚡⚡ | ⭐⭐⭐⭐⭐ | $$ | Recommended - Latest & best |
| Gemini 2.5 Pro | ⚡⚡ | ⭐⭐⭐⭐⭐ | $$$ | Most detailed analysis |
| Gemini Flash Lite | ⚡⚡⚡ | ⭐⭐⭐ | $ | Quick checks |
| Gemini Flash Latest | ⚡⚡⚡ | ⭐⭐⭐⭐ | $ | Fast & accurate |

## ⌨️ Keyboard Shortcuts

- **Ctrl/Cmd + Enter** - Analyze resume from anywhere
- **Enter** - Trigger file upload when focused on upload area
- **Space** - Trigger file upload when focused on upload area
- **Shift + Enter** - New line in chat (Enter sends message)

## 🏗️ Tech Stack

- **Frontend**: Pure HTML/CSS/JavaScript (no build tools needed)
- **UI Framework**: None (vanilla JS for simplicity)
- **AI**: Google Gemini API (3 Pro Preview, 2.5 Pro, Flash models)
- **Markdown**: Marked.js CDN for rendering feedback
- **Design**: Custom brutalist/tech aesthetic with green accent
- **Storage**: localStorage for caching and API key (optional)
- **Streaming**: Server-Sent Events (SSE) with throttled updates

## 🔍 How It Works

### 1. Document Upload

Files are converted to base64 and sent directly to Gemini API:

- **PDF/DOCX**: Sent with proper MIME type for document understanding
- **Text files**: Sent as plain text for processing

### 2. Caching System

Smart caching prevents unnecessary API calls:

- **Cache Key**: Hash of resume + job context + job description + model
- **Storage**: localStorage with 30-day expiration
- **Cache Hit**: Instant display with green badge notification
- **Force Regenerate**: Checkbox to bypass cache when needed

### 3. Streaming Analysis

Real-time results with optimized performance:

- **Server-Sent Events**: Gemini API streams response
- **Throttled Updates**: DOM updates limited to 100ms intervals
- **Progress Indicator**: Live character and word count
- **Score Prevention**: Score header only rendered once to prevent flashing

### 4. Analysis Criteria

Gemini API analyzes resume against:

- **ATS Compatibility & Formatting** (20%)
- **Keyword Optimization** (25%)
- **Experience Relevance** (25%)
- **Skills Assessment** (15%)
- **Education & Certifications** (10%)
- **Red Flags & Critical Issues** (5%)

### 5. Scoring Output

Structured markdown feedback with:

- Overall score (0-100)
- Category-wise scores with reasoning
- Critical red flags
- Missing elements
- Keyword analysis
- Actionable improvements (High/Medium/Low priority)
- Competitive analysis
- Final verdict

### 6. Error Handling

Robust error handling with retries:

- **Rate Limits**: Automatic retry with exponential backoff
- **Network Errors**: User-friendly error messages
- **Invalid API Key**: Clear validation feedback

## 🔒 Privacy & Security

- ✅ API key only used client-side
- ✅ No data sent to any server except Google's Gemini API
- ✅ No tracking, analytics, or logging
- ✅ Resume cached locally only if analyzed (user's device only)
- ✅ Cache automatically expires after 30 days
- ✅ Runs entirely in your browser
- ✅ API key storage is optional and warns user about risks

## 🎨 Customization

### Change the System Prompt

Edit the `systemPrompt` variable in the HTML to customize evaluation criteria:

```javascript
let systemPrompt = `# ROLE
You are an expert ATS Resume Scorer...
`;
```

### Modify the Design

All styles are in the `<style>` block. Key variables:

```css
:root {
    --bg-primary: #0a0a0a;
    --accent: #00ff88;
    /* ... */
}
```

### Adjust Cache Expiration

Change the `CACHE_EXPIRATION_DAYS` constant:

```javascript
const CACHE_EXPIRATION_DAYS = 30; // Change to your preference
```

### Modify Throttle Timing

Adjust throttle limit for streaming updates:

```javascript
const throttledDisplay = throttle((text) => {
    displayResults(text, true);
}, 100); // Change 100ms to your preference
```

## 💡 Tips for Best Results

1. **Upload PDF/DOCX when possible** - Preserves formatting and structure
2. **Provide job description** - Enables keyword matching and role-specific feedback
3. **Use job title/domain** - Gets general best practices for that role
4. **Ask follow-up questions** - Chat to clarify feedback or get specific advice
5. **Try different models** - Pro model for detailed analysis, Flash for quick checks
6. **Use cache strategically** - Force regenerate when you've made changes
7. **Export results** - Download as Markdown to track improvements over time

## ⚠️ Limitations

- Requires valid Gemini API key (free tier available)
- File size limits based on Gemini API (typically 20-50MB)
- Internet connection required
- CORS restrictions on URL fetching (URLs must be publicly accessible)
- Cache stored in browser localStorage (cleared if browser data is cleared)
- AI responses may vary slightly between analyses (hence caching is recommended)

## 🤝 Contributing

This is a single HTML file for easy deployment. To contribute:

1. Fork the repository
2. Make your changes to `ats-scorer.html`
3. Test locally by opening in a browser
4. Test accessibility with screen readers
5. Test keyboard navigation
6. Submit a pull request

## 📜 License

MIT License - Feel free to use, modify, and distribute

## 🆘 Support

- **API Issues**: Check [Google AI Studio](https://ai.google.dev/)
- **Bugs**: Open an issue on GitHub
- **Questions**: Use the chat feature after analysis!
- **Accessibility Issues**: Report with details about assistive technology used

## 🗺️ Roadmap

### ✅ Completed

- [x] Streaming responses with progress indicator
- [x] Intelligent caching with expiration
- [x] Export results as Markdown
- [x] Print/PDF support
- [x] API key localStorage persistence
- [x] Rate limit handling with retry
- [x] ARIA labels and accessibility
- [x] Keyboard navigation and shortcuts
- [x] Throttled rendering for performance

### 🔮 Potential Future Enhancements

- [ ] Resume builder based on feedback
- [ ] Compare multiple resumes side-by-side
- [ ] Track improvement over time (analytics dashboard)
- [ ] Integration with job boards (LinkedIn, Indeed)
- [ ] Dark/light theme toggle
- [ ] Multi-language support
- [ ] Batch analysis (multiple resumes at once)
- [ ] Resume templates optimized for ATS
- [ ] Cover letter analysis
- [ ] LinkedIn profile scoring

## 📊 Performance Metrics

- **First Paint**: < 500ms (single HTML file)
- **Time to Interactive**: < 1s (no build step)
- **Streaming Updates**: Throttled to 100ms (reduces re-renders by 90%)
- **Cache Hit**: < 100ms (instant from localStorage)
- **Cache Miss**: Depends on Gemini API (typically 5-15s for analysis)

---

**Built with brutal honesty and ❤️ for job seekers**

*Because it's better to hear harsh truth from an AI than get rejected by a human recruiter.*
