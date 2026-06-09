# SockGetSingleValue

- ea: `0x180008670`
- end: `0x18000888c`
- name: `SockGetSingleValue`
- size: `540`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, __int64, CHAR *, _DWORD *, ULONG ResultLength)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000980c`

## callees

- `0x180008670`
- `0x18004ed64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000881f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000881f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180008812`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180008812`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800087ac`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800087ac`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180008726`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180008726`
- `ntdll!RtlAllocateHeap` at `0x1800086be`
- `ntdll!RtlAllocateHeap` at `0x1800086f6`
- `ntdll!RtlAllocateHeap` at `0x1800086be`
- `ntdll!RtlAllocateHeap` at `0x1800086f6`
- `ntdll!RtlFreeHeap` at `0x1800087c9`
- `ntdll!RtlFreeHeap` at `0x1800087f0`
- `ntdll!RtlFreeHeap` at `0x18000883a`
- `ntdll!RtlFreeHeap` at `0x180008858`
- `ntdll!RtlFreeHeap` at `0x1800087c9`
- `ntdll!RtlFreeHeap` at `0x1800087f0`
- `ntdll!RtlFreeHeap` at `0x18000883a`
- `ntdll!RtlFreeHeap` at `0x180008858`
- `ntdll!NtQueryValueKey` at `0x18000874a`
- `ntdll!NtQueryValueKey` at `0x18000874a`

## string_xrefs

- `0x180008709`: `DatabasePath`

## pseudocode

```c

```
