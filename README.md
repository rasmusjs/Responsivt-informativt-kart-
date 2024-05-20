# **Prøv ut kartet på** [https://kart.skramzy.no/](https://kart.skramzy.no/)
# Bakgrunn for oppgaven

Oppdragsgiven Norconsult Digital, med omfattende domenekunnskap og erfaring innen veiforvaltning og kritisk infrastruktur, ønsket å utforske potensialet for å samle flere fagsystemer til en enhetlig løsning. Med dette kunne man lettere se sammenhengen mellom ulike systemer. Vår oppgave var å lage et konseptbevis (proof of concept), hvor vi henter data fra flere fiktive fagsystemer og illustrere de i kart, for å vise nytteverdien av en slik løsning

# Dagens problem

Det finnes et hav av karttjenester i det offentlige og internt i Norconsult. Systemene snakker ikke sammen og er helt uavhengige av hverandre. Tjenestene er heller ikke mobiltilpasset, noe som gjør det vanskelig å bruke på en bygge- eller anleggsplass effektivt. For å kunne bruke de ulike systemene trenger man en viss grad av ekspertise for domenet. Det hadde derfor vært svært tidsbesparende å kunne samle flere fagsystemer inn i ett system med kun det som er nødvendig for brukeren.

# Mulige løsninger for applikasjonen

1. **Webapplikasjon med JavaScript-rammeverk**:
   
   - **Fordeler**; kjennskap til teknologiene, plattformuavhengighet og lettere vedlikehold.
   - **Ulemper**; begrenset systemtilgang (GPS, kamera) og mulig lavere ytelse.

2. **Webapplikasjon med WebAssembly**:
   
   - **Fordeler**; plattformuavhengighet, lettere vedlikehold og bedre ytelse.
   - **Ulemper**; kompleksitet, begrenset støtte og begrenset systemtilgang.

3. **Native applikasjoner**:
   
   - **Fordeler**; best ytelse og systemtilgang.
   - **Ulemper**; flere kodebaser, plattformavhengighet og vedlikehold.

# Løsning
Vi valgte å lage en webapplikasjon med JavaScript-rammeverk og egen backend. Dette på grunn av kjennskap til teknologien, mulighet til støtte fra oppdragsgiver og plattformuavhengighet. Disse aspektene veide tyngre enn mulig lavere ytelse og dårligere systemtilgang. 

# Gjennomføring

Applikasjonen bruker frontend-teknologier; Vue (med Nuxt, TypeScript). OpenLayers ble brukt for å vise kartet og objekter. Karttypene vi støtter er veikart, landkart, flyfoto og gråtonekart. Vi har også støtte for ulike kartprojeksjoner som WGS84 og ETRS89 for de ulike objektene. I backend har vi et system som transformerer data fra ulike kilder. Fagsystemene våre var RegObs (skred) og Miljøskade (forurensinger). Systemene er skrevet i C# med ASP.NET Core som rammeverk. Vi har støtte for Kartverket og Statens Vegvesen som eksterne kilder. **Arbeidsmetodikk**: prosjeket ble gjennomført med en agil tilnærming basert på Scrum, kombinert med testdrevet utvikling. Testtypene vi har benyttet oss av er enhets- , intergrasjons-, bruker- og sluttbrukertesting.

# Evaluering

Brukeren får en god oversikt over hvor en hendelse har skjedd samt relevant saksinformasjon. Brukere slipper å gå gjennom flere karttjenester. Det er enkelt visuelt å skille mellom store mengder av informasjon ved hjelp av grupperinger, farger, ikoner og omriss. Applikasjonen forenkler innsamlingen av data fra ulike fagsystemer og visualiserer dem på en universell og responsiv måte med støtte for ulike enheter. Oppdragsgiver så nytteverdien av et slikt verktøy. På grunn av tidsbegrensninger kunne vi imidlertid ikke optimalisere løsningen ytterligere for mobile enheter. Det var også et ønske fra oppdragsgiveren om å videreutvikle søkefunksjonaliteten.

