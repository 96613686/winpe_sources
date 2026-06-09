# GetHashOfAppContainerSid

- ea: `0x1800121e4`
- end: `0x180012354`
- name: `GetHashOfAppContainerSid`
- size: `368`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007298`
- `0x180008840`

## callees

- `0x180008754`
- `0x1800093ec`
- `0x18000af80`
- `0x18000b250`
- `0x1800110b8`
- `0x1800121e4`
- `0x18001235c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012317`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012317`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001232f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001232f`

## string_xrefs

- `0x180012213`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c

```
