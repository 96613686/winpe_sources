# CRegistry::GetValue(wchar_t const *,ulong *)

- ea: `0x180036938`
- end: `0x1800369da`
- name: `?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z`
- size: `162`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002cc0`
- `0x18002ecc8`

## callees

- `0x180036938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036952`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800369c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036952`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800369c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800369a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800369a2`

## pseudocode

```c

```
