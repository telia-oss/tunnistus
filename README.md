# Telia Tunnistus Pre-Production 

## Table of Contents

- [1. Endpoints](#1-endpoints)
  - [1.1 OpenID Connect Metadata](#11-openid-connect-metadata)
  - [1.2 Keys](#12-keys)
  - [1.3 OAuth2 Endpoints](#13-oauth2-endpoints)
  - [1.4 SAML Metadata](#14-saml-metadata)

- [2. Integration Document](#2-integration-document)

- [3. Regulatory Compliance Requirements for Strong Electronic Identification (Finland)](#3-regulatory-compliance-requirements-for-strong-electronic-identification-finland)
  - [3.1 General Information](#31-general-information)
  - [3.2 Official Announcements](#32-official-announcements)
  - [3.3 Regulation 72B: Identification and Trust Services](#33-regulation-72b-identification-and-trust-services)
  - [3.4 Technical Profiles](#34-technical-profiles)
    - [3.4.1 OpenID Connect (OIDC)](#341-openid-connect-oidc)
    - [3.4.2 SAML](#342-saml)

- [4. Examples](#4-examples)
  - [4.1 Tunnistus Python Sample Application](#41-tunnistus-python-sample-application)
  - [4.2 Sample Entity Statement](#42-sample-entity-statement)

- [5. Questions and Answers on the Traficom announcement to e-services](#5-questions-and-answers-on-the-traficom-announcement-to-e-services)

- [6. Questions and Answers on Telia Tunnistus key rotation](#6-questions-and-answers-on-telia-tunnistus-key-rotation)

---

## 1 Endpoints

### 1.1 OpenID Connect Metadata

- **Federation Entity Statement**  
  [`/.well-known/openid-federation`](https://tunnistus-pp.telia.fi/.well-known/openid-federation)

- **OIDC Provider Metadata**  
  [`/uas/.well-known/openid-configuration`](https://tunnistus-pp.telia.fi/uas/.well-known/openid-configuration)

- **OAuth 2.0 Provider Metadata**  
  [`/uas/.well-known/oauth-authorization-server`](https://tunnistus-pp.telia.fi/uas/.well-known/oauth-authorization-server)
<br/><br/>

### 1.2 Keys

- **JWKS (Public Keys)**  
  [`/uas/oauth2/metadata.jwks`](https://tunnistus-pp.telia.fi/uas/oauth2/metadata.jwks)

- **Signed JWKS**  
  [`/openid_provider/signed_jwks.jwt`](https://tunnistus-pp.telia.fi/openid_provider/signed_jwks.jwt)
<br/><br/>

### 1.3 OAuth2 Endpoints

- **Authorization Endpoint**  
  [`/uas/oauth2/authorization`](https://tunnistus-pp.telia.fi/uas/oauth2/authorization)

- **Token Endpoint**  
  [`/uas/oauth2/token`](https://tunnistus-pp.telia.fi/uas/oauth2/token)
<br/><br/>

### 1.4 SAML Metadata 

- **SAML IDP Metadata**  
  [`/uas/saml2/metadata.xml`](https://tunnistus-pp.telia.fi/uas/saml2/metadata.xml)

- **SAML Authorization Endpoint**  
  [`/uas/saml2/SingleSignOnService`](https://tunnistus-pp.telia.fi/uas/saml2/SingleSignOnService)
<br/><br/>

## 2 Integration Document

This guide provides instructions for integrating with the Telia Identification Broker Pre-Production Service, enabling strong electronic identification for test users. The service supports both OpenID Connect (OIDC) and Security Assertion Markup Language (SAML) protocols, offering secure authentication in compliance with Finnish regulations. It is intended for technical architects and developers seeking to connect their services to the Identification Broker Service.

📥 [Telia Tunnistus Integration Guide To Identification Broker Service (PDF)](files/Telia%20Tunnistus%20-%20Integration%20guide%20to%20identification%20broker%20service%20v2.34.pdf)
<br/><br/>

## 3 Regulatory Compliance Requirements for Strong Electronic Identification (Finland)

Below are official documents and directives related to electronic identification and trust services in Finland, provided by the Finnish Transport and Communications Agency (Traficom) and the National Cyber Security Centre (NCSC-FI).

### 3.1 General Information

- [Electronic Identification – General Information (FI)](https://www.kyberturvallisuuskeskus.fi/fi/toimintamme/saantely-ja-valvonta/sahkoinen-tunnistaminen)
<br/><br/>

### 3.2 Official Announcements

- [Liikenne- ja viestintäviraston tiedote 2025 (FI)](https://www.kyberturvallisuuskeskus.fi/sites/default/files/media/file/Liikenne-ja_viestint%C3%A4viraston_tiedote_2025.pdf)
- [Traficom Announcement 2025 (EN)](https://www.kyberturvallisuuskeskus.fi/sites/default/files/media/file/Traficom_Announcement_2025_EN.pdf)
<br/><br/>

### 3.3 Regulation 72B: Identification and Trust Services

- [Regulation 72B (FI)](https://www.kyberturvallisuuskeskus.fi/sites/default/files/media/file/M72B_2022_M%C3%84%C3%84R%C3%84YS_72B_tunnistus-_ja_luottamuspalvelut_julkaistu.pdf)
- [Explanatory Memorandum for Regulation 72B (FI)](https://www.kyberturvallisuuskeskus.fi/sites/default/files/media/file/M72B_2022_M%C3%84%C3%84R%C3%84YS_72B_tunnistus-_ja_luottamuspalvelut_PERUSTELUMUISTIO.pdf)
- [Regulation 72B (EN)](https://www.kyberturvallisuuskeskus.fi/sites/default/files/media/file/M72B_2022_M%C3%84%C3%84R%C3%84YS_72B_tunnistus-_ja_luottamuspalvelut_ENG_julkaistu.pdf)
- [Explanatory Memorandum for Regulation 72B (EN)](https://www.kyberturvallisuuskeskus.fi/sites/default/files/media/file/M72B_2022_M%C3%84%C3%84R%C3%84YS_72B_tunnistus-_ja_luottamuspalvelut_PERUSTELUMUISTIO_ENG.pdf)
<br/><br/>

### 3.4 Technical Profiles

#### 3.4.1 OpenID Connect (OIDC)

- [Traficom S213/2023 – OIDC Profile v2.2 for the Finnish Trust Network (EN)](https://www.kyberturvallisuuskeskus.fi/sites/default/files/media/file/Traficom_S213_2023_OIDC_Profile_v2_2_for_the_Finnish_Trust_Network_EN.pdf)

#### 3.4.2 SAML

- [Traficom S212/2023 – SAML Profile for the Finnish Trust Network (EN)](https://www.kyberturvallisuuskeskus.fi/sites/default/files/media/file/Traficom_S212_2023_SAML_Profile_for_the_Finnish_Trust_Network_EN.pdf)

> _Note: The interface descriptions are available in English only to ensure wide use and prevent interpretation differences._
<br/><br/>

## 4 Examples

### 4.1 Tunnistus Python Sample Application

Sample application integration with Python: https://github.com/telia-oss/tunnistus-python-sample

### 4.2 Sample Entity Statement

Sample Entity Stament for relying party application: https://github.com/telia-oss/tunnistus/tree/main/files/entity-statement-example

## 5 Questions and Answers on the Traficom announcement to e-services

**Q: How do I know if this applies to me?**<br/>
A: If your service relies on Finnish strong electronic identification methods — such as online banking credentials or the Mobile ID (Mobiilivarmenne) — then this applies to you.

**Q: How do I get started?**<br/>
A: Begin by reading Chapter 2 of the "Telia Tunnistus – Integration Guide to the Identification Broker Service" (version 2.29 or later).

**Q: I only have one key pair. Can I still test signed requests?**<br/>
A: Yes, you can use the same key pair for both signing and encryption. In that case, do not specify the key usage as 'sig' or 'enc'; omit the parameter entirely.<br/>However, for a more secure and scalable setup, it's recommended to use separate key pairs for signing and encryption.

**Q: I already have an OIDC integration with Telia Tunnistus. How can I test signed requests?**<br/>
A: If your OIDC integration is based on public keys, signed requests are already supported. You can begin testing right away.

**Q: Does this apply to SAML integrations?**<br/>
A: This requirement applies only to OIDC integrations, not to SAML-based connections.

**Q: How do I know whether my integration uses signed requests?**<br/>
A: Your authentication request should be structured like this:<br/>
https://tunnistus-pp.telia.fi/uas/oauth2/authorization?request=eyJhbGciOiJSUzI1NiIsImtp...<br/>
You can inspect this using your browser's developer tools. The only parameter must be "request", nothing else.<br/>If the request contains other parameters, they are ignored, and only the parameters included in the signed request object are processed.

**Q: Will you retrieve the JWKS URI daily or weekly to detect rotated keys, or should we use static keys for this integration?**<br/>
A: If automation is used, see the document Telia Tunnistus Integration Guide chapter 2.1 about Entity Statement. In the Finnish FTN integration case, the JWKS must be signed if keys are updated automatically. This requirement is mandated by Traficom. Signed JWKS can be provided using the OpenID Federation specification, either by sending an Entity Statement securely to Telia Tunnistus or by publishing a Federation endpoint.

**Q: Do you expect both signing keys?**<br/>
A: We recommend to user separate signing ("use": "sig") and encryption ("use": "enc") keys. This is the more future-proof approach. We sign the ID token with our signing key and encrypt it using your encryption key, so you must have the corresponding private key to decrypt it. While it is possible to use a single key without the "use" parameter, the recommended setup is to use separate keys for signing and encryption.

**Q: Do the keys require additional certificate metadata, or is the key material itself sufficient?**<br/>
A: Just the key material is sufficient. Public key information is provided in JSON Web Key (JWK) format. The key data is Base64-encoded without padding (= characters), and is included within a JSON object according to the key type. The keys must use the RSA algorithm with a minimum key length of 2048 bits.

Sample data:

```json
{
 "keys": [
 {
 "e": "AQAB",
 "kid": "34567947-2167-4a9c-8368-b199fe63b6e2",
 "kty": "RSA",
 "n": 
"yas1HSwbF85dr4YpMOlcupdZY4SEBPrCZMp5w6F9IxWewmhQSsa1fGa2t3_CKl0LgIM1nbJd1fr5CQKN_Hpb0u7H5N3Not4akhNqcZHGNI7xrwOn
OOIifwgQb2SF3J7xtKJJ0s8igQ5gxNm5rJyaeeJFxoR3tZC9lMbBpHdOiH7HXz3OOZIDbFm5da-i2u91T22UJgHBIZmXzl_7L3ZpIenSECRD9M3fuj9aVCNf3zKo67UuqaPdueRj_ywGqk94Iwr-FnmZ9NKpZe067VK4s2h-CufkGCAhKu9WVgSIHzSzIzCbLSfTXgMCpJyC4dw7TBzlvHOI3BgMjqrUqb3kkw",
 "use": "sig"
 },
 {
 "e": "AQAB",
 "kid": "ae29278f-87be-4914-bcfc-bdb659e8fe1d",
 "kty": "RSA",
 "n": "wDYW8Y_uZI9F9Qy0WrwYE6xkxEF8k4PTMUgl-ul3J7Lw-v9VuZtH2aSoX3LgTH_qpCGRIUZy7OPDYYXGV1phrVHs7-
NpevO4aXdTZOwUvjViFbTXO3RkTdh4f0d_YpA6RC2owI41BhE_FmShmPKNGskpyTNAp1E_eH1e_w4FM2g_sbwlDJQ1ckJSyXkDoGrW7Dbx34zlrQg
UgHdKtepSCX_b3WWLKD3KW7W3lmoeSpI9iLmPLJMiYHlBcd70dCBBQW24n2bSk1BLwiNVETWPfsNnFWA2t19Jl0u3vCHNCCdKi0WORtI-JiaXQSmPW9ZD2kiZUwYwRi8Cg6Z9a85ngQ",
 "use": "enc"
 }
 ]
}
```

## 6 Questions and Answers on Telia Tunnistus key rotation

**Q: How do I know if this applies to me?**<br/>
A: This applies to all integrations with Telia Tunnistus. Some integrations have already implemented automated key management. In that case no action is required. Otherwise you need to manually update the new keys to your service.

**Q: What is the plan?**<br/>
A: The plan is to rotate Telia Tunnistus OIDC and SAML keys. See the time table below:

ENV | DATE | NAME | ACTION
--- | --- | --- | ---
PRE-PROD |	12.1.2026 |	tunnistus-pp.telia.fi |	OIDC and SAML keys publication
PRE-PROD |	9.2.2026 |	tunnistus-pp.telia.fi |	OIDC and SAML keys deployment
PROD |	23.2.2026 |	tunnistus.telia.fi | OIDC and SAML keys publication
PROD |	20.4.2026 |	tunnistus.telia.fi | OIDC and SAML keys deployment

**Q: Where can I find the latest version of the key rotation document?**<br/>
A: The link to the latest key rotation document: 

📥 [Telia Tunnistus Key Rotation (PDF)](files/Telia%20Tunnistus%20Key%20Rotation%2020260107.pdf)

