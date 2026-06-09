# GetTypeByNameA

- ea: `0x18002cc30`
- end: `0x18002ccc4`
- name: `GetTypeByNameA`
- size: `148`
- prototype: `INT __stdcall(LPSTR lpServiceName, LPGUID lpServiceType)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18002cc30`
- `0x18002ccd0`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002cc6a`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002cc6a`
- `ntdll!RtlNtStatusToDosError` at `0x18002cc7c`
- `ntdll!RtlNtStatusToDosError` at `0x18002cc7c`
- `ntdll!RtlInitAnsiString` at `0x18002cc51`
- `ntdll!RtlInitAnsiString` at `0x18002cc51`
- `ntdll!RtlFreeUnicodeString` at `0x18002ccaf`
- `ntdll!RtlFreeUnicodeString` at `0x18002ccaf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cc8a`

## pseudocode

```c

```
