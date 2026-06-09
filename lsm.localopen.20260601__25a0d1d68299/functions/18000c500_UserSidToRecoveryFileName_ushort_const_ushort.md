# UserSidToRecoveryFileName(ushort const *,ushort * *)

- ea: `0x18000c500`
- end: `0x18000c623`
- name: `?UserSidToRecoveryFileName@@YAJPEBGPEAPEAG@Z`
- size: `291`
- prototype: `__int64 __fastcall(PCWSTR pszMore, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18000c314`
- `0x18000c468`

## callees

- `0x180009580`
- `0x18000c500`
- `0x18004e850`
- `0x180099258`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c5b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c5b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c5ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c5ec`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c555`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000c555`

## pseudocode

```c

```
