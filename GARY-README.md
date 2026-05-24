# Gary Nguyen — Web projekt

## Přehled
Web finančního poradce Ing. Garyho Nguyena. Minimalistický "old money" styl, pergamenová paleta, zlaté akcenty.

**Live URL:** https://gary-web.vercel.app  
**GitHub:** https://github.com/vaclavkraus-stock/gary-web  
**Vercel:** https://vercel.com/vaclavkraus-stock/gary-web  

---

## Soubory
```
~/Desktop/gary/
├── index.html        # Hlavní stránka
└── kalkulacky.html   # Finanční kalkulačky (7 kalkulaček)
```

---

## Jak nasadit změnu
Po každé úpravě souboru:
```bash
cd ~/Desktop/gary
git add .
git commit -m "popis co jsem zmenil"
git push
```
Vercel nasadí automaticky za ~30 sekund.

---

## Design systém

### Barvy
```css
--ink: #1A1714          /* Hlavní text */
--forest: #1B2A1E       /* Tmavá zelená — tlačítka, sidebar, CTA */
--gold: #8A6A30         /* Zlatá — akcenty, eyebrows */
--gold-2: #C4A05A       /* Světlejší zlatá */
--gold-pale: #E2CAA0    /* Velmi světlá zlatá — text na tmavém bg */
--parchment: #F6F0E4    /* Hlavní pozadí */
--parchment-2: #EDE5D4  /* Druhé pozadí */
--parchment-3: #E2D8C8  /* Třetí pozadí */
--muted: #5C5044        /* Tlumený text */
--line: #C8BAA0         /* Linky, bordery */
```

### Fonty
- **Playfair Display** — nadpisy, serif, elegantní
- **Inter** — tělo textu, navigace, labely

---

## index.html — Hlavní stránka

### Struktura sekcí (shora dolů)
1. **Nav** — logo + navigace + CTA tlačítko + hamburger na mobil
2. **Hero** — dvousloupcový: text vlevo, Garyho fotka vpravo
3. **Stats** — 3 čísla: 6+ let, 120+ klientů, 3 oblasti
4. **O mně** — dvousloupcový text, žádná duplicitní fotka
5. **Služby** — 3 karty: Reality / Finance / Kariéra (hover = tmavý sweep)
6. **GN divider** — dekorativní proužek s monogramem
7. **Proč spolupracovat** — 3 důvody s čísly
8. **Jak spolupracujeme** — 3 kroky procesu (hover = tmavý bg)
9. **Reference** — 3 citáty klientů
10. **Kontakt/CTA** — tmavá sekce, dvousloupcová
11. **Footer**

### Garyho fotka
Squarespace CDN URL (může přestat fungovat — Gary by měl dodat vlastní fotku):
```
https://images.squarespace-cdn.com/content/v1/68a973ff36b9310ba1a72ba8/0cabc20f-9582-444d-a5f3-56060579f1de/8F21ABE4-C791-4AD5-B7F8-83491BE16089.jpeg
```
Fallback: GN monogram v zlaté barvě

### Kontaktní údaje
- Tel: +420 721 003 272
- Email: gary.nguyen@bcas.cz
- Adresa: Trnitá 491/3, Brno
- LinkedIn: https://www.linkedin.com/in/gary-nguyen-78a714195/
- Facebook: https://www.facebook.com/gary.j.nguyen

---

## kalkulacky.html — Finanční kalkulačky

### 7 kalkulaček
1. **Vliv inflace** — kupní síla v čase
2. **Splátková kalkulačka** — výpočet hypotéky
3. **Stav jistiny v čase** — zůstatek úvěru
4. **Investiční kalkulačka** — složené úročení
5. **Hypotéka vs Investice** — srovnání strategií
6. **Bohatství v nemovitosti** — růst equity
7. **Investiční nemovitost** — cashflow a ROI

### Layout
- Desktop: sidebar vlevo (260px tmavý) + obsah vpravo
- Mobil: sidebar skrytý, sticky bar dole s tlačítkem "Změnit"
- Grafy: Chart.js 4.4.1

### Disclaimer
Zobrazí se při první interakci se sliderem. Právní doložka Broker Consulting.

### Slidery
Každý slider má vedle sebe číslo které se mění v reálném čase při posunu.

---

## Verze a Git historie (klíčové commity)
```
4e4f02c  fix slider hodnoty se aktualizuji v realnem case  ← STABILNÍ ZÁKLAD
64b3a91  editovatelne hodnoty v kalkulackach
62ac416  mobile optimalizace a lepsi disclaimer
31d3a8a  disclaimer pri interakci, vysvetlivky grafu
```

### Jak se vrátit na starší verzi
**Přes Vercel dashboard (nejjednodušší):**
1. vercel.com → projekt gary-web → Deployments
2. Najdi deployment → tři tečky → Promote to Production

**Přes terminal:**
```bash
cd ~/Desktop/gary
git log --oneline        # zobraz historii
git show HASH:kalkulacky.html > ~/Desktop/soubor.html  # vytáhni konkrétní verzi
```

---

## Technický stack
- **Hosting:** Vercel (auto-deploy z GitHub)
- **GitHub:** vaclavkraus-stock/gary-web
- **Fonts:** Google Fonts (Playfair Display, Inter)
- **Charts:** Chart.js 4.4.1 (CDN)
- **Žádný framework** — čistý HTML/CSS/JS

---

## Co Gary ještě potřebuje (TODO)
- [ ] Vlastní doména (garynguyen.cz) napojená na Vercel
- [ ] Vlastní fotka Garyho (nezávislá na Squarespace CDN)
- [ ] Více referencí klientů (aktuálně 3)
- [ ] Případně kontaktní formulář

---

## Jak editovat v novém chatu s Claudem

Řekni Claudovi:
> "Pracuju na webu pro Garyho Nguyena, finančního poradce. Web je na gary-web.vercel.app, soubory jsou v ~/Desktop/gary/ (index.html a kalkulacky.html), GitHub vaclavkraus-stock/gary-web. Styl je old money — pergamenová paleta, Playfair Display, tmavá zelená a zlatá. Chci [POPIS ZMĚNY]."

Claude pak opraví soubor, ty stáhneš a pushneš:
```bash
mv ~/Downloads/SOUBOR.html ~/Desktop/gary/SOUBOR.html
cd ~/Desktop/gary
git add . && git commit -m "popis" && git push
```
