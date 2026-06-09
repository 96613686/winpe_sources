# StgCreateStorageEx

- ea: `0x180039ef0`
- end: `0x18003a10c`
- name: `StgCreateStorageEx`
- size: `540`
- prototype: `HRESULT __stdcall(const WCHAR *pwcsName, DWORD grfMode, DWORD stgfmt, DWORD grfAttrs, STGOPTIONS *pStgOptions, PSECURITY_DESCRIPTOR pSecurityDescriptor, const IID *const riid, void **ppObjectOpen)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18001eef0`
- `0x1800333e0`
- `0x180033544`
- `0x180034f28`
- `0x180039e68`
- `0x180039ef0`
- `0x18003aa00`
- `0x18003b3cc`
- `0x180042800`
- `0x180043160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a054`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a047`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a047`
- `ext-ms-win-kernel32-file-l1-1-0!DuplicateEncryptionInfoFileExt` at `0x18003a0a9`
- `ext-ms-win-kernel32-file-l1-1-0!DuplicateEncryptionInfoFileExt` at `0x18003a0a9`

## pseudocode

```c

```
