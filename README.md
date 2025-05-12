## Features and Best Practices Used

This project is a minimalist personal landing page with links to social platforms with a clean design and fast performance. Below are the best web development practices used in this site along with code examples.

---

### Font Preloading to Prevent FOUT

FOUT (Flash of Unstyled Text) occurs when the browser renders text with a fallback font before the custom font loads. Preloading the font ensures it’s fetched early to prevent this.

```html
<link rel="preload" href="https://fonts.gstatic.com/..." 
  as="font" type="font/woff2" crossorigin="anonymous" />
```

---

### Visibility Toggle Until Page Load

Hides the page content until all fonts and assets are loaded, preventing layout shifts or FOUT flashes.

```html
<style>
  html.loading { visibility: hidden; }
</style>
<script>
  document.documentElement.classList.add('loading');
  window.addEventListener('load', () => {
    document.documentElement.classList.remove('loading');
  });
</script>
```

---

### Responsive Meta Tag

Ensures the layout scales correctly on all screen sizes, especially mobile devices.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

---

### Semantic Meta Tags for SEO

Meta tags help search engines understand your page and how to index it.

```html
<meta name="description" content="Tanjim Aumy's..." />
<meta name="author" content="Tanjim Aumy" />
<meta name="robots" content="index, follow" />
<link rel="canonical" href="https://thassanaumy.github.io/" />
```

---

### Inline Font Declaration

Defines a custom font directly in the HTML using `@font-face`, giving control without needing an external CSS file.

```html
<style>
@font-face {
  font-family: 'Special Elite';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url('https://fonts.gstatic.com/...') format('woff2');
}
</style>
```

---

### Structured Data with JSON-LD for Rich Results

Structured data in JSON-LD format helps search engines understand the content of your page and display enhanced results in search.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Tanjim Aumy",
  "url": "https://thassanaumy.github.io/",
  "sameAs": [
    "https://x.com/thassanaumy",
    "https://instagram.com/thassanaumy",
    "https://youtube.com/@thassanaumy",
    "https://github.com/thassanaumy"
  ],
  "description": "Tanjim Aumy's...",
  "image": "https://thassanaumy.github.io/preview-image.png"
}
</script>
```

---

### Accessible, Semantic HTML

Using appropriate tags and ARIA labels improves screen reader compatibility and overall accessibility.

```html
<a href="https://github.com/thassanaumy" 
   target="_blank" 
   rel="noopener noreferrer" 
   aria-label="GitHub">
   <i class="fab fa-github"></i>GitHub
</a>
```

---

### Font Awesome for Vector Icons

Font Awesome provides scalable vector icons that look sharp on all screen sizes and resolutions.

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/..." />
```

Used in:
```html
<i class="fas fa-code-branch"></i> Source
```

---

### Mobile Responsiveness via Media Queries

Ensures font sizes, layout spacing, and positioning adapt to smaller screen sizes.

```html
<style>
@media (max-width: 600px) {
  .source-link {
    font-size: 0.75rem;
    bottom: 12px;
    right: 12px;
  }
}
</style>
```
