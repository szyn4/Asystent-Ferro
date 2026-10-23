# Asystent-Ferro

Asystent-Ferro to prywatne, wewnętrzne narzędzie jednego sprzedawcy na Allegro. Korzysta z niego wyłącznie właściciel konta — Bartosz Szymczak (GitHub: [szyn4](https://github.com/szyn4)) — i tylko na własnym koncie sprzedażowym. Nie jest to aplikacja publiczna i nie jest oferowana innym użytkownikom.

## Do czego służy

Narzędzie służy do analizy własnej sprzedaży na Allegro, wyłącznie w trybie odczytu:

- codziennego sprawdzania statusu ofert i wykrywania tych, które się zakończyły albo zniknęły,
- alertów niskiego stanu magazynowego (`stock.available`),
- podsumowań sprzedaży na podstawie zamówień,
- podobnych zestawień raportowych.

## Zakres dostępu do Allegro REST API

Dostęp jest tylko do odczytu. Używane są między innymi zasoby:

- `GET /sale/offers`
- `GET /sale/product-offers/{offerId}`
- `GET /order/checkout-forms`

Narzędzie nie tworzy, nie zmienia i nie kończy ofert oraz nie wysyła wiadomości do kupujących.

## Częstotliwość i autoryzacja

Zapytania wychodzą kilka razy dziennie, w ramach zaplanowanego raportu dobowego, i mieszczą się w limitach Allegro. Uwierzytelnianie odbywa się przez OAuth (device flow) z użyciem tokenów odświeżania, bez nadmiernego generowania nowych tokenów.

## User-Agent

W każdym żądaniu do API wysyłany jest nagłówek:

```
Asystent-Ferro/1.0 (+https://github.com/szyn4/Asystent-Ferro)
```

Ta strona jest stroną informacyjną wskazaną w tym nagłówku.

## Kontakt

Kontakt w sprawach tej integracji: [Issues w tym repozytorium](https://github.com/szyn4/Asystent-Ferro/issues) albo profil GitHub [szyn4](https://github.com/szyn4).

## English summary

Asystent-Ferro is a private, internal tool of one Allegro seller. It is used only by the account owner, Bartosz Szymczak (GitHub: [szyn4](https://github.com/szyn4)), and only on that owner’s own seller account. It is not a public application and is not offered to other users.

Its purpose is read-only analysis of the owner’s own sales: a daily check of offer status (offers that ended or disappeared), low-stock alerts (`stock.available`), sales summaries based on orders, and similar reporting.

API access is read-only. Endpoints used include `GET /sale/offers`, `GET /sale/product-offers/{offerId}`, and `GET /order/checkout-forms`. The tool does not create, modify, or end offers, and it does not send messages to buyers.

It makes a few requests per day as a scheduled daily report, well within Allegro rate limits. Authorization uses the OAuth device flow with refresh tokens, without excessive token generation.

User-Agent: `Asystent-Ferro/1.0 (+https://github.com/szyn4/Asystent-Ferro)`

Contact: [GitHub Issues](https://github.com/szyn4/Asystent-Ferro/issues) in this repository, or the profile [github.com/szyn4](https://github.com/szyn4).
