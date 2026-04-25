<div align="center">

# 📇 Digital Business Card

**Share your contact info with a single tap. No app install. No paper. Just a Shortcut.**

A fully native Apple Shortcut that generates a beautifully designed digital business card on your iPhone. Fill in your details once, tap run, and share the image anywhere.

<br/>

<img src="assets/thumbnail.png" alt="Digital Business Card · Shortcut" width="640"/>

<br/><br/>

<a href="https://www.icloud.com/shortcuts/a9389cdd28624595848a3b978c6f049e">
  <img src="assets/button-dark.svg" alt="Download Dark Theme" height="64"/>
</a>
&nbsp;
<a href="https://www.icloud.com/shortcuts/8ef8349704fa49ecb0b293131a7e0265">
  <img src="assets/button-light.svg" alt="Download Light Theme" height="64"/>
</a>

</div>

---

## ⬇ Installation

**Requirements**: iOS 15 or later · Shortcuts app (pre-installed on iOS)

1. Tap a download button above.
2. Shortcuts app opens with a preview — tap **Add Shortcut**.
3. First time only: if prompted, enable
   **Settings → Shortcuts → Allow Untrusted Shortcuts**.

That's it. The shortcut now lives in your library.

---

## 🚀 Quick Start

1. Open the shortcut and tap **Edit** (the ⋯ icon).
2. Fill in the **Dictionary** at the top with your details.
3. Tap **Done**, then tap the shortcut to run it.
4. The finished card is saved to your **Photos** app. Share it anywhere — AirDrop, Messages, email, or as a lock-screen wallpaper.

---

## 💡 Why?

There are plenty of paid apps on the App Store that do exactly this — generate a QR business card. Most of them lock basic customization behind subscriptions, push ads, or force their own branding onto your card. For something this simple, paying monthly feels wrong.

Apple Shortcuts is already on every iPhone. It's free, it runs offline, and every step is visible and editable. Fork it, swap the background, change the fonts, rearrange the layout — whatever fits your brand. No paywall, no telemetry, no "Pro" tier.

And because a business card holds your name, email, and phone number, privacy matters. Everything here runs locally on your device — no account, no server, no analytics. Your details never leave your iPhone unless you choose to share the final image.

Paper cards get lost. SaaS cards get held hostage. This one is just yours.

---

## 📸 Themes

Two themes ship out of the box, demonstrating the header logic — one with a custom logo, one with the organization name as text.

<table align="center">
  <tr>
    <td align="center"><img src="assets/screen-dark.jpg" width="280" alt="Dark · With Logo"/></td>
    <td align="center"><img src="assets/screen-light.jpg" width="280" alt="Light · No Logo"/></td>
  </tr>
  <tr>
    <td align="center"><b>Dark · With Logo</b></td>
    <td align="center"><b>Light · No Logo</b></td>
  </tr>
</table>

---

## 🎨 Customization

> 🎬 **Setup Walkthrough** — if you prefer watching over reading

<table align="center">
  <tr>
    <td align="center" valign="middle">
      <img src="assets/dbc-workflow.png" width="720" alt="4-step setup workflow: Open Edit → Fill Dictionary → Paste Base64 → Run Shortcut"/>
    </td>
    <td align="center" valign="middle">
      <img src="assets/demo.gif" width="200" alt="Setup walkthrough animation"/>
    </td>
  </tr>
  <tr>
    <td align="center"><sub><b>4 steps</b> — labeled flow</sub></td>
    <td align="center"><sub><b>In motion</b> — 2× speed loop · <a href="assets/demo.mp4">▶ original (42s)</a></sub></td>
  </tr>
</table>

---

### 5.1 Your Info

Fill in each field in the Dictionary. All values are plain text.

| Key | Example |
|---|---|
| Last Name | `Smith` |
| Middle Name | (optional) |
| First Name | `John` |
| Full Name | `John Smith` |
| TITLE | `Analyst` |
| TEL | `+1 555 123 4567` |
| Organization | `Acme Inc.` |
| EMAIL | `you@example.com` |
| URL | `https://your-site.com` |
| PHOTO | Base64 string or direct image URL (optional) |
| X-LINKEDIN | `https://linkedin.com/in/username` (optional) |

### 5.2 Header Logic

The top slot above the QR card follows this priority:

1. **Logo** — if you paste Base64 or an image URL in the Logo field
2. **Organization** — rendered as text, if Logo is blank
3. **Blank** — if both are empty

> **Override**: If your background already has a logo baked in, insert a single space character in the Logo field to force the header blank (avoids duplication).

### 5.3 Background

A default background is included — works out of the box.

To use your own:
- **Base64 string** — offline, renders instantly (recommended)
- **Direct image URL** — requires internet

Recommended size: **1290 × 2590 px**. See [Design Guide](#-design-guide) for full spec.

Need to convert an image to Base64? See the [Helper](#-image--base64-helper) below.

### 5.4 Where to Paste

Inside the shortcut, the Logo and Background fields are clearly labeled by comments. Find each comment, then paste your Base64 string (or image URL) into the **Text** action right below it.

<table align="center">
  <tr>
    <td align="center"><img src="assets/guide-logo.jpg" width="280" alt="Logo paste location"/></td>
    <td align="center"><img src="assets/guide-background.jpg" width="280" alt="Background paste location"/></td>
  </tr>
  <tr>
    <td align="center"><b>Logo</b><br/><sub>optional — skip if using Organization name</sub></td>
    <td align="center"><b>Background</b><br/><sub>optional — default included</sub></td>
  </tr>
</table>

> Both fields are optional. If you only fill in the Dictionary and leave Logo and Background blank, you'll still get a clean card with the default background and your Organization name as the header.

---

## 🔄 Image → Base64 Helper

To use a custom logo or background, you need a **Base64 string** — a long block of letters and numbers that represents your image as plain text.

<p align="center">
  <a href="https://sewon-p.github.io/#make-yours">
    <img src="assets/button-converter.svg" alt="Open Base64 Converter on sewon-p.github.io" height="64"/>
  </a>
</p>

<p align="center">
  <sub>Drag, drop, copy. 100% browser-side — nothing is uploaded.</sub>
</p>

**How it works**

1. Click the button above (or use any other Base64 image converter).
2. Drop your image. The tool gives you a long string back.
3. Copy it and paste into the Logo or Background field in the Dictionary.

**Important — the prefix**

The string you paste needs a short prefix at the very front so the shortcut knows what file type it is. The final value looks like this:

```
data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQ...(thousands more characters)
```

| Your image | Prefix to put in front |
|---|---|
| `.jpg` / `.jpeg` | `data:image/jpeg;base64,` |
| `.png` | `data:image/png;base64,` |

The converter above adds this prefix automatically. If you use a different tool that outputs only the raw string (starts with letters/numbers, no `data:` at the front), paste the matching prefix yourself before the string.

---

## 🖼 Design Guide

For creators making custom backgrounds.

<p align="center">
  <img src="assets/design-guide.svg" alt="Canvas and QR card layout diagram" width="100%"/>
</p>

### 8.1 Canvas

| Property | Value |
|---|---|
| Dimensions | **1290 × 2590 px** |
| Aspect | Portrait, 1 : 2.01 |
| Export | 1x base · 2x / 3x supported |

### 8.2 QR Card (White Slot)

| Property | Value |
|---|---|
| Size | **980 × 980 px** (square) |
| Position | Centered on canvas |
| Center point | `(645, 1295)` |
| Top-left corner | `(155, 805)` |
| Corner radius | **52 px** |
| Padding | 155 px sides · 805 px top/bottom |

### 8.3 QR Code Inside the Card

| Property | Value |
|---|---|
| Size | **820 × 820 px** |
| Inner padding | 80 px |
| Position | Centered within the white card |

### 8.4 Templates

🚧 **Coming soon.** Figma / Sketch / PSD templates will be added in a future release.

---

## 🤝 Contributing

- **Bug or idea** → [open an Issue](../../issues)
- **Share your custom background** → [GitHub Discussions](../../discussions) (coming soon)
- **Code improvements** → pull requests welcome

---

## ❓ FAQ

<details>
<summary>Does this need internet?</summary>

No, as long as your Logo and Background are stored as Base64 strings. If you use direct image URLs instead, internet is needed on every run.
</details>

<details>
<summary>Where is my data stored?</summary>

Everything stays on your device. The shortcut runs entirely locally in the Shortcuts app. The generated image is saved to your Photos library only.
</details>

<details>
<summary>The shortcut says "Untrusted" — is it safe?</summary>

Apple flags any shortcut not distributed through the official gallery as "untrusted". You can inspect every action before adding — no hidden scripts, no network calls beyond fetching images you specify.
</details>

<details>
<summary>How do I change fonts or colors?</summary>

Open the shortcut in edit mode and tweak the overlay text actions directly. Each text layer has its own font, size, and color settings.
</details>

<details>
<summary>How do I resize the logo?</summary>

Change the height in the logo resize action. Width auto-scales to keep the aspect ratio. Default: `200`.
</details>

<details>
<summary>My email or phone number gets clipped at the edge.</summary>

Lower the font size in the corresponding overlay action until it fits. Keep both EMAIL and TEL values at the same size for balance.
</details>

<details>
<summary>My QR code doesn't scan.</summary>

Make sure the QR image is at least 820 × 820 px and has enough contrast. If you're generating a vCard QR, test it with iPhone Camera before embedding.
</details>

---

## 📄 License

- **Code**: [MIT](LICENSE)
- **Gallery submissions** (future): CC BY-SA 4.0

## 🙏 Credits

Made by **Park Sewon**

If you ship something cool with this, I'd love to see it.
