# DXR — Direct VSL Page

Statische Direct-VSL-Landingpage für DigitalXResults. Custom Bunny-HLS-Player (kein Bunny-Branding, kein Seekbar/Skip), DXR Light-Mode-Branding, Proof-Section mit Testimonials.

## Struktur

```
index.html            # komplette Page (HTML + CSS + JS inline)
assets/
  logo_dark.webp      # DXR Logo (Navy/Blau) — für hellen Hintergrund
  logo_white.webp     # DXR Logo (weiß) — Reserve für dunkle Flächen
  brian_moncada.webp
  sebastian_szalinski.webp
  michael_bogner.webp
netlify.toml          # Netlify Deploy-Config (publish = ".")
```

## Konfiguration

Alle Stellschrauben sitzen im `CONFIG`-Block unten in `index.html`:

| Key | Bedeutung |
|---|---|
| `HLS_URL` | Bunny HLS Playlist (`.m3u8`) des VSL-Videos |
| `CTA_REVEAL_SECONDS` | Sekunde, ab der der „Call buchen"-Button erscheint (Preview = 4, Live = echter Pitch-Timestamp) |
| `BOOKING_URL` | Calendly / Perspective Booking-Link für den CTA (aktuell `#`) |
| `FAKE_EXPONENT` | Tempo der dekorativen Progress-Bar (< 1 = vorne schneller) |
| `ALLOW_PAUSE` | `true` = Klick aufs Video pausiert/startet, `false` = komplett gelockt |

Video-Wechsel: nur `HLS_URL` und das `poster`-Attribut des `<video>`-Tags auf die neue Bunny-ID setzen.

## Deployment (Netlify)

1. Repo mit Netlify verbinden (New site from Git → dieses Repo).
2. Build command: *leer lassen*. Publish directory: `.` (steht in `netlify.toml`).
3. Deploy → Custom Domain in den Netlify Domain-Settings verbinden.

Reines statisches Hosting, kein Build-Step nötig.
