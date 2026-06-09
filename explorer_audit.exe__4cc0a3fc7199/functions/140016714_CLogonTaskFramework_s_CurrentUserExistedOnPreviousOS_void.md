# CLogonTaskFramework::s_CurrentUserExistedOnPreviousOS(void)

- ea: `0x140016714`
- end: `0x140016874`
- name: `?s_CurrentUserExistedOnPreviousOS@CLogonTaskFramework@@CA_NXZ`
- size: `352`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140010924`

## callees

- `0x140016714`
- `0x14001687c`
- `0x140016c10`
- `0x14001eba8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400167ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400167ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001679d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001679d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400167da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400167da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001680f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001680f`

## string_xrefs

- `0x140016827`: `shell\lib\logontasks\logontasks.cpp`
- `0x140016841`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001685b`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c

```
