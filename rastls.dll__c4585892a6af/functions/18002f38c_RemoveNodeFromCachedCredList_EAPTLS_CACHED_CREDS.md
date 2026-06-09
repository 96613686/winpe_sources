# RemoveNodeFromCachedCredList(_EAPTLS_CACHED_CREDS *)

- ea: `0x18002f38c`
- end: `0x18002f51c`
- name: `?RemoveNodeFromCachedCredList@@YAKPEAU_EAPTLS_CACHED_CREDS@@@Z`
- size: `400`
- prototype: `unsigned int __fastcall(HLOCAL hMem)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x180004560`
- `0x180005f80`
- `0x180025564`
- `0x1800542a0`
- `0x180056490`
- `0x180059c18`
- `0x180072a50`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180028404`
- `0x180029b64`
- `0x18002f38c`
- `0x1800356f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f503`
- `CRYPT32!CertFreeCertificateContext` at `0x18002f480`
- `CRYPT32!CertFreeCertificateContext` at `0x18002f480`
- `SspiCli!FreeCredentialsHandle` at `0x18002f412`
- `SspiCli!FreeCredentialsHandle` at `0x18002f412`
- `ncrypt!NCryptFreeObject` at `0x18002f45b`
- `ncrypt!NCryptFreeObject` at `0x18002f45b`
- `CRYPTSP!CryptReleaseContext` at `0x18002f46b`
- `CRYPTSP!CryptReleaseContext` at `0x18002f46b`
- `rtutils!TraceDumpExA` at `0x18002f3ec`
- `rtutils!TraceDumpExA` at `0x18002f3ec`

## pseudocode

```c

```
