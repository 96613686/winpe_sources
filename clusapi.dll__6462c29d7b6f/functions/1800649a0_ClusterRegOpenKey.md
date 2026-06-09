# ClusterRegOpenKey

- ea: `0x1800649a0`
- end: `0x180064b4f`
- name: `ClusterRegOpenKey`
- size: `431`
- prototype: `LONG __stdcall(HKEY hKey, LPCWSTR lpszSubKey, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180037ae8`
- `0x180063f44`
- `0x180064430`

## callees

- `0x18001236c`
- `0x180025478`
- `0x180061138`
- `0x180063adc`
- `0x180063cb0`
- `0x1800649a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064b10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064b10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064ae5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064ae5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064a0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064a77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064a0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064a77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800649d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064a2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800649d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064a2b`

## string_xrefs

- `0x180064aa5`: `ApiOpenKey`

## pseudocode

```c

```
