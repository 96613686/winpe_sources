# SecureBlobHelper(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,bool)

- ea: `0x180179e2c`
- end: `0x180179f30`
- name: `?SecureBlobHelper@@YAJPEAU_CRYPTOAPI_BLOB@@0_N@Z`
- size: `260`
- prototype: `HRESULT __fastcall(_CRYPTOAPI_BLOB *in, _CRYPTOAPI_BLOB *out, bool fProtect)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800bda70`
- `0x180179fa0`

## callees

- `0x180179e2c`
- `0x18017c1d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180179ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180179ea3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180179ef6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180179ef6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180179ecf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180179ecf`
- `CRYPT32!CryptUnprotectData` at `0x180179e93`
- `CRYPT32!CryptUnprotectData` at `0x180179e93`
- `CRYPT32!CryptProtectData` at `0x180179e7a`
- `CRYPT32!CryptProtectData` at `0x180179e7a`

## string_xrefs

- `0x180179e73`: `MSXMLsec`

## pseudocode

```c

```
