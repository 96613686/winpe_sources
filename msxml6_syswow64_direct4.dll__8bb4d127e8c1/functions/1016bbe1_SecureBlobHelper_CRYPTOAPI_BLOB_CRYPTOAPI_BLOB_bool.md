# SecureBlobHelper(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,bool)

- ea: `0x1016bbe1`
- end: `0x1016bcbf`
- name: `?SecureBlobHelper@@YGJPAU_CRYPTOAPI_BLOB@@0_N@Z`
- size: `222`
- prototype: `HRESULT __userpurge@<eax>(_CRYPTOAPI_BLOB *in@<ecx>, _CRYPTOAPI_BLOB *out@<edx>, bool fProtect)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1016bcc5`
- `0x1016be00`

## callees

- `0x1006bff0`
- `0x1016bbe1`
- `0x101712a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1016bc34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1016bc34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1016bc5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1016bc5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1016bc85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1016bc85`
- `CRYPT32!CryptUnprotectData` at `0x1016bc2a`
- `CRYPT32!CryptUnprotectData` at `0x1016bc2a`
- `CRYPT32!CryptProtectData` at `0x1016bc1d`
- `CRYPT32!CryptProtectData` at `0x1016bc1d`

## string_xrefs

- `0x1016bc17`: `MSXMLsec`

## pseudocode

```c

```
