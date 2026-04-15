# Analytická geometrie

Tento repozitář obsahuje Beamer prezentaci k analytické geometrii pro II. ročník.
Hlavní zdroj je soubor [Analytická geometrie, Prezentace, Krajíček.tex](Analytická%20geometrie,%20Prezentace,%20Krajíček.tex), ze kterého se generuje PDF prezentace.

## Účel prezentace

Prezentace slouží jako úvod a přehled základních pojmů analytické geometrie.
Je zaměřená na práci s body, vektory a přímkami v kartézské soustavě souřadnic.

## Obsah

- vysvětlení, k čemu je analytická geometrie užitečná
- základní pojmy a slovní zásoba: bod, vektor, přímka, směrnice, normálový vektor, parametr, skalární součin a další
- rozdíl mezi bodem a vektorem
- určování vektorů pomocí změny souřadnic nebo dvojice bodů
- posunutí bodu vektorem
- sčítání vektorů
- střed úsečky
- velikost úsečky a vektoru
- obsahy v analytické geometrii
- parametrické vyjádření přímky
- cvičení k posunu, středům úseček, velikosti vektoru a parametrickému tvaru přímky
- řešení cvičení

Prezentace používá `TikZ`, `PGFPlots` a jednoduchou animaci pro ukázku pohybu po přímce.

## Sestavení

### Lokálně

K sestavení je potřeba TeX Live s `latexmk`.

Na Linuxu lze použít stejné balíčky jako v GitHub Actions:

```bash
sudo apt-get update
sudo apt-get install -y --no-install-recommends \
  latexmk \
  texlive-fonts-recommended \
  texlive-lang-czechslovak \
  texlive-latex-extra \
  texlive-latex-recommended \
  texlive-pictures \
  zip
```

Pak spusť:

```bash
latexmk \
  -pdf \
  -interaction=nonstopmode \
  -halt-on-error \
  -file-line-error \
  -jobname=analyticka-geometrie \
  "Analytická geometrie, Prezentace, Krajíček.tex"
```

Výstupem bude soubor `analyticka-geometrie.pdf`.

### GitHub Actions

Workflow v `.github/workflows/build-pdf.yml`:

- při pushi do `main` sestaví PDF
- vytvoří ZIP s PDF
- publikuje GitHub Release s tagem ve tvaru `vYYYY-MM-DD`

## Poznámky

- `.gitattributes` nastavuje LF normalizaci pro textové soubory.
- PDF je vedené jako binární soubor, aby Git nezkoušel textové diffy.
