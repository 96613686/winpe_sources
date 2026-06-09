# ExportCertificatePrivateKey

- ea: `0x18006e7c4`
- end: `0x18006ee3b`
- name: `ExportCertificatePrivateKey`
- size: `1655`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCertContext@<rcx>, __int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18009f2e8`

## callees

- `0x1800600e0`
- `0x18006ce6c`
- `0x18006d370`
- `0x18006d700`
- `0x18006e7c4`
- `0x18006ee50`
- `0x18006f090`
- `0x1800b7ba4`
- `0x1800babc4`
- `0x1800bec20`
- `0x1800bf63c`
- `0x180115094`
- `0x1801150dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed81`
- `ncrypt!NCryptFreeObject` at `0x18006e9cf`
- `ncrypt!NCryptFreeObject` at `0x18006e9cf`
- `ncrypt!NCryptExportKey` at `0x18006eba1`
- `ncrypt!NCryptExportKey` at `0x18006ee19`
- `ncrypt!NCryptExportKey` at `0x18006eba1`
- `ncrypt!NCryptExportKey` at `0x18006ee19`
- `ncrypt!NCryptGetProperty` at `0x18006ebfe`
- `ncrypt!NCryptGetProperty` at `0x18006ebfe`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006e926`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006e926`
- `bcrypt!BCryptGenRandom` at `0x18006e9b8`
- `bcrypt!BCryptGenRandom` at `0x18006e9b8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006ea8d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006ee30`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006ea8d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18006ee30`

## pseudocode

```c

```
