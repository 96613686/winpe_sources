# InitClusterKeyValueStore(wchar_t const *,wchar_t const *,_CLUSTER *,_CRESOURCE *)

- ea: `0x18008aba4`
- end: `0x18008ae2a`
- name: `?InitClusterKeyValueStore@@YAPEAU_HKEYVALUESTORE@@PEB_W0PEAU_CLUSTER@@PEAU_CRESOURCE@@@Z`
- size: `646`
- prototype: `struct _HKEYVALUESTORE *__fastcall(const wchar_t *, const wchar_t *, struct _CLUSTER *, struct _CRESOURCE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18008ae30`

## callees

- `0x18001236c`
- `0x180025478`
- `0x18006f910`
- `0x180088a00`
- `0x18008aba4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008abe7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008abe7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ac32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ac7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008acde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ad6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008adcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ac32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ac7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008acde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ad6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008adcd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008abd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ac4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ad34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008abd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ac4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008ad34`

## string_xrefs

- `0x18008aca0`: `Failed to copy Manager Name into handle`
- `0x18008ad8f`: `Failed to copy Store Name into handle`

## pseudocode

```c

```
