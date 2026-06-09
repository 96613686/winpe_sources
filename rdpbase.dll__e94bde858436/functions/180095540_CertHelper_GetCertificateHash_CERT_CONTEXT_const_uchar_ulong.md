# CertHelper::GetCertificateHash(_CERT_CONTEXT const *,uchar * *,ulong *)

- ea: `0x180095540`
- end: `0x1800957e1`
- name: `?GetCertificateHash@CertHelper@@YAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z`
- size: `673`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, const struct _CERT_CONTEXT *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18008b024`

## callees

- `0x180001aa0`
- `0x1800787d4`
- `0x180078820`
- `0x180095540`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009559c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009568b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009559c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009568b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18009558e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18009567d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18009558e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18009567d`

## string_xrefs

- `0x1800955e4`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1800956d2`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x180095773`: `onecore\termsrv\rdp\win\security\certhelper.cpp`

## pseudocode

```c

```
