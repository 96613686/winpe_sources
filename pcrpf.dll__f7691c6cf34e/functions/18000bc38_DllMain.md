# DllMain

- ea: `0x18000bc38`
- end: `0x18000bd16`
- name: `DllMain`
- size: `222`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800030e4`

## callees

- `0x180003cf0`
- `0x180007c5c`
- `0x18000b30c`
- `0x18000bc38`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000bcdb`
- `ntdll!RtlNtStatusToDosError` at `0x18000bcdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bce9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bce9`

## pseudocode

```c

```
