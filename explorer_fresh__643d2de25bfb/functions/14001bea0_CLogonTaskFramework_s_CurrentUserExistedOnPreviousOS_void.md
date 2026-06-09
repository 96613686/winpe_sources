# CLogonTaskFramework::s_CurrentUserExistedOnPreviousOS(void)

- ea: `0x14001bea0`
- end: `0x14001c01f`
- name: `?s_CurrentUserExistedOnPreviousOS@CLogonTaskFramework@@CA_NXZ`
- size: `383`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140046e8c`

## callees

- `0x14001b2c8`
- `0x14001bea0`
- `0x14001c028`
- `0x14001c440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001bf29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001bf29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001bf87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001bf87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001bf6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001bf6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001bf9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001bfb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001bf9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001bfb3`

## string_xrefs

- `0x14001bfd2`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001bfec`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001c006`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c

```
