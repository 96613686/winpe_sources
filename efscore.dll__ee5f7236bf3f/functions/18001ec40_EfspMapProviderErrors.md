# EfspMapProviderErrors

- ea: `0x18001ec40`
- end: `0x18001ee80`
- name: `EfspMapProviderErrors`
- size: `576`
- prototype: `__int64 __fastcall(LPCWSTR pszProviderName, DWORD dwProvType)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180033c5c`
- `0x180035280`
- `0x180077e2c`

## callees

- `0x18001ec40`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed3e`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001ed9c`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001ed9c`
- `ncrypt!NCryptFreeObject` at `0x18001ee6d`
- `ncrypt!NCryptFreeObject` at `0x18001ee6d`
- `ncrypt!NCryptGetProperty` at `0x18001edfd`
- `ncrypt!NCryptGetProperty` at `0x18001edfd`
- `CRYPTSP!CryptGetProvParam` at `0x18001ed34`
- `CRYPTSP!CryptGetProvParam` at `0x18001ed34`
- `CRYPTSP!CryptReleaseContext` at `0x18001ee5e`
- `CRYPTSP!CryptReleaseContext` at `0x18001ee5e`
- `CRYPTSP!CryptAcquireContextW` at `0x18001ecb7`
- `CRYPTSP!CryptAcquireContextW` at `0x18001ecb7`

## pseudocode

```c

```
