# CDownloadPublisherUtilities::_GetPublisherAndIssuerNamesAndCertHashes(CDownloadSecurity::_hash_params *)

- ea: `0x1803c634c`
- end: `0x1803c6769`
- name: `?_GetPublisherAndIssuerNamesAndCertHashes@CDownloadPublisherUtilities@@CAJPEAU_hash_params@CDownloadSecurity@@@Z`
- size: `1053`
- prototype: `__int64 __fastcall(struct CDownloadSecurity::_hash_params *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1803c5ae0`

## callees

- `0x180007010`
- `0x1800096a0`
- `0x1803c5ce8`
- `0x1803c61a8`
- `0x1803c634c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1803c6695`
- `msvcrt!memcpy_s` at `0x1803c66f1`
- `msvcrt!memcpy_s` at `0x1803c6695`
- `msvcrt!memcpy_s` at `0x1803c66f1`
- `KERNEL32!GetLastError` at `0x1803c6447`
- `KERNEL32!GetLastError` at `0x1803c6447`
- `iertutil!__imp_IEGetSignatureInfoEx` at `0x1803c6397`
- `iertutil!__imp_IEGetSignatureInfoEx` at `0x1803c6397`
- `iertutil!__imp_?FreeWVTStateData@@YAXPEAX@Z` at `0x1803c6742`
- `iertutil!__imp_?FreeWVTStateData@@YAXPEAX@Z` at `0x1803c6742`
- `CRYPT32!CertFreeCertificateContext` at `0x1803c6729`
- `CRYPT32!CertFreeCertificateContext` at `0x1803c6729`
- `CRYPT32!CryptFindOIDInfo` at `0x1803c6626`
- `CRYPT32!CryptFindOIDInfo` at `0x1803c6647`
- `CRYPT32!CryptFindOIDInfo` at `0x1803c6626`
- `CRYPT32!CryptFindOIDInfo` at `0x1803c6647`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1803c6437`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1803c6495`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1803c656a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1803c65b6`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1803c6437`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1803c6495`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1803c656a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1803c65b6`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1803c64b2`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x1803c64b2`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1803c64d8`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1803c64d8`

## pseudocode

```c

```
