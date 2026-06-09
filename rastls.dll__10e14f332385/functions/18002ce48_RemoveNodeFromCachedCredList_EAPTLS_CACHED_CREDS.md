# RemoveNodeFromCachedCredList(_EAPTLS_CACHED_CREDS *)

- ea: `0x18002ce48`
- end: `0x18002cfb3`
- name: `?RemoveNodeFromCachedCredList@@YAKPEAU_EAPTLS_CACHED_CREDS@@@Z`
- size: `363`
- prototype: `unsigned int __fastcall(HLOCAL hMem)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1800041c0`
- `0x180005ac0`
- `0x180022a48`
- `0x180051510`
- `0x1800535f0`
- `0x180056aac`
- `0x18006e0f8`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180026880`
- `0x180027c00`
- `0x18002ce48`
- `0x180032acc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cfa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cfa1`
- `CRYPT32!CertFreeCertificateContext` at `0x18002cf24`
- `CRYPT32!CertFreeCertificateContext` at `0x18002cf24`
- `SspiCli!FreeCredentialsHandle` at `0x18002cec8`
- `SspiCli!FreeCredentialsHandle` at `0x18002cec8`
- `ncrypt!NCryptFreeObject` at `0x18002cf0b`
- `ncrypt!NCryptFreeObject` at `0x18002cf0b`
- `CRYPTSP!CryptReleaseContext` at `0x18002cf15`
- `CRYPTSP!CryptReleaseContext` at `0x18002cf15`
- `rtutils!TraceDumpExA` at `0x18002cea8`
- `rtutils!TraceDumpExA` at `0x18002cea8`

## pseudocode

```c

```
