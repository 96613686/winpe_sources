# CRegistry::GetValue(wchar_t const *,uchar *,ulong *)

- ea: `0x1800368b4`
- end: `0x180036931`
- name: `?GetValue@CRegistry@@QEAAHPEB_WPEAEPEAK@Z`
- size: `125`
- prototype: `int(CRegistry *__hidden this, const wchar_t *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180034aa4`

## callees

- `0x1800368b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800368cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800368ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800368cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800368ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036909`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036909`

## pseudocode

```c

```
