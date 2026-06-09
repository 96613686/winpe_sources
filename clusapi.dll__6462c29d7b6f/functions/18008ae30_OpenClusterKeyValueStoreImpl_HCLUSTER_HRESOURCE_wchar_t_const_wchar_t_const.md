# OpenClusterKeyValueStoreImpl(_HCLUSTER *,_HRESOURCE *,wchar_t const *,wchar_t const *)

- ea: `0x18008ae30`
- end: `0x18008af17`
- name: `?OpenClusterKeyValueStoreImpl@@YAPEAU_HKEYVALUESTORE@@PEAU_HCLUSTER@@PEAU_HRESOURCE@@PEB_W2@Z`
- size: `231`
- prototype: `struct _HKEYVALUESTORE *__fastcall(struct _HCLUSTER *, struct _HRESOURCE *, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180088994`
- `0x18008cdd0`

## callees

- `0x180014638`
- `0x1800149f8`
- `0x18006c010`
- `0x18006f910`
- `0x180088994`
- `0x18008aba4`
- `0x18008ae30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aef0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008ae76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008aef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008ae76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008aef8`

## string_xrefs

- `0x18008aec8`: `Failed to init the HKEYVALUESTORE with name '%ws' and storename '%ws'`
- `0x18008aed4`: `OpenClusterKeyValueStoreImpl`

## pseudocode

```c

```
