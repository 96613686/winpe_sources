# MigrateStatusData(_GPOINFO *,ushort const *,ushort const *)

- ea: `0x18009db40`
- end: `0x18009dd23`
- name: `?MigrateStatusData@@YAHPEAU_GPOINFO@@PEBG1@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct _GPOINFO *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800631a8`

## callees

- `0x180001f30`
- `0x180003770`
- `0x18005b2d0`
- `0x180075ec0`
- `0x18007d320`
- `0x18009db40`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009dbb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009dcfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009dbb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009dcfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009db85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009db85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dce2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dcf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dce2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dcf1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009dbdb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009dbdb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009dc25`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18009dc25`

## string_xrefs

- `0x18009db94`: `Software\Microsoft\Windows\CurrentVersion\Group Policy\Status\%ws\GPExtensions`

## pseudocode

```c

```
