# TestAcquirePrivateKey(_CERT_CONTEXT const *)

- ea: `0x1800403d4`
- end: `0x1800404df`
- name: `?TestAcquirePrivateKey@@YAJPEBU_CERT_CONTEXT@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029650`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x1800403d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040422`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180040414`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180040414`
- `ncrypt!NCryptFreeObject` at `0x1800404c2`
- `ncrypt!NCryptFreeObject` at `0x1800404c2`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800404cc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800404cc`

## string_xrefs

- `0x180040428`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180040468`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`

## pseudocode

```c

```
