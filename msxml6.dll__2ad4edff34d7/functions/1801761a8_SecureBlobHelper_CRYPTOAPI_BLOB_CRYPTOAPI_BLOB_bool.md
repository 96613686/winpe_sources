# SecureBlobHelper(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,bool)

- ea: `0x1801761a8`
- end: `0x18017628d`
- name: `?SecureBlobHelper@@YAJPEAU_CRYPTOAPI_BLOB@@0_N@Z`
- size: `229`
- prototype: `HRESULT __fastcall(_CRYPTOAPI_BLOB *in, _CRYPTOAPI_BLOB *out, bool fProtect)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800bc418`
- `0x1801762f4`

## callees

- `0x1801761a8`
- `0x180178528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180176213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180176213`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18017625a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18017625a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180176239`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180176239`
- `CRYPT32!CryptUnprotectData` at `0x180176209`
- `CRYPT32!CryptUnprotectData` at `0x180176209`
- `CRYPT32!CryptProtectData` at `0x1801761f6`
- `CRYPT32!CryptProtectData` at `0x1801761f6`

## string_xrefs

- `0x1801761ef`: `MSXMLsec`

## pseudocode

```c

```
