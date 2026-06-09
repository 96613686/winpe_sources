# SecureBlobHelper(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,bool)

- ea: `0x1016baf1`
- end: `0x1016bbcf`
- name: `?SecureBlobHelper@@YGJPAU_CRYPTOAPI_BLOB@@0_N@Z`
- size: `222`
- prototype: `HRESULT __userpurge@<eax>(_CRYPTOAPI_BLOB *in@<ecx>, _CRYPTOAPI_BLOB *out@<edx>, bool fProtect)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1016bbd5`
- `0x1016bd10`

## callees

- `0x1006c080`
- `0x1016baf1`
- `0x101711b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1016bb44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1016bb44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1016bb6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1016bb6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1016bb95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1016bb95`
- `CRYPT32!CryptUnprotectData` at `0x1016bb3a`
- `CRYPT32!CryptUnprotectData` at `0x1016bb3a`
- `CRYPT32!CryptProtectData` at `0x1016bb2d`
- `CRYPT32!CryptProtectData` at `0x1016bb2d`

## string_xrefs

- `0x1016bb27`: `MSXMLsec`

## pseudocode

```c

```
