# IsCertAcceptable

- ea: `0x180057c6c`
- end: `0x180058106`
- name: `IsCertAcceptable`
- size: `1178`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCert)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180056e80`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180057c6c`
- `0x1800593d0`
- `0x1800e32b4`
- `0x1800e7206`

## import_xrefs

- `msvcrt!malloc` at `0x180057d5e`
- `msvcrt!malloc` at `0x180057d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057f6d`
- `ncrypt!NCryptOpenStorageProvider` at `0x180057e18`
- `ncrypt!NCryptOpenStorageProvider` at `0x180057e18`
- `ncrypt!NCryptGetProperty` at `0x180057e7c`
- `ncrypt!NCryptGetProperty` at `0x180057e7c`
- `ncrypt!NCryptFreeObject` at `0x18005803c`
- `ncrypt!NCryptFreeObject` at `0x18005805f`
- `ncrypt!NCryptFreeObject` at `0x180058078`
- `ncrypt!NCryptFreeObject` at `0x18005803c`
- `ncrypt!NCryptFreeObject` at `0x18005805f`
- `ncrypt!NCryptFreeObject` at `0x180058078`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180057f5f`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180057f5f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180057cfe`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180057dbe`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180057cfe`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180057dbe`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180058046`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180058046`

## pseudocode

```c

```
