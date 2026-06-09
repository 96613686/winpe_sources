# KGT_TryGetProcessPathByNtQuery

- ea: `0x180040a84`
- end: `0x180040ba7`
- name: `KGT_TryGetProcessPathByNtQuery`
- size: `291`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c784`

## callees

- `0x18000af80`
- `0x180040a84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180040b5b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180040b5b`
- `ntdll!NtQuerySystemInformation` at `0x180040ae9`
- `ntdll!NtQuerySystemInformation` at `0x180040ae9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b8a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040aa7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040b39`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040aa7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040b39`

## string_xrefs

- `0x180040b72`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\telemetry-utils.cpp`

## pseudocode

```c

```
