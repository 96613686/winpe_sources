# UserSidToRecoveryFileName(ushort const *,ushort * *)

- ea: `0x180018528`
- end: `0x180018638`
- name: `?UserSidToRecoveryFileName@@YAJPEBGPEAPEAG@Z`
- size: `272`
- prototype: `__int64 __fastcall(PCWSTR pszMore, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x180018384`
- `0x1800184a8`

## callees

- `0x180018528`
- `0x18001aa50`
- `0x18004b460`
- `0x180093d38`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800185d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800185d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018608`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018608`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001857d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001857d`

## pseudocode

```c

```
