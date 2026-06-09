# RegScan::FindFileRefs(void)

- ea: `0x180050754`
- end: `0x180050a2c`
- name: `?FindFileRefs@RegScan@@AEAAJXZ`
- size: `728`
- prototype: `__int64 __fastcall(RegScan *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180050b6c`

## callees

- `0x180005944`
- `0x180050754`
- `0x180050adc`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800509ad`
- `msvcrt!_wcsnicmp` at `0x1800509da`
- `msvcrt!_wcsnicmp` at `0x1800509ad`
- `msvcrt!_wcsnicmp` at `0x1800509da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180050943`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180050943`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180050855`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180050855`

## string_xrefs

- `0x1800509cd`: `CLSID`
- `0x1800507a3`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x1800507ee`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x1800508ec`: `com\complus\src\comcat\regscan\regscan.cpp`

## pseudocode

```c

```
