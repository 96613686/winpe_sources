# GetCurrentActiveKey(_GPOINFO *,HKEY__ * *,int)

- ea: `0x1800483b0`
- end: `0x180048764`
- name: `?GetCurrentActiveKey@@YAHPEAU_GPOINFO@@PEAPEAUHKEY__@@H@Z`
- size: `948`
- prototype: `__int64 __fastcall(struct _GPOINFO *, HKEY *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180074c88`
- `0x18009e370`

## callees

- `0x180003770`
- `0x18000a504`
- `0x180022bd4`
- `0x1800336a0`
- `0x1800483b0`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800484d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004858b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800485e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004874e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800484d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004858b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800485e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004874e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004847c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004847c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800484b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004859e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800485f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800484b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004859e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800485f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048687`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004854c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004854c`

## string_xrefs

- `0x180048622`: `GetCurrentActiveKey: Failed to read reg key: %s`
- `0x180048657`: `GetCurrentActiveKey: Failed to read reg key: %s`

## pseudocode

```c

```
