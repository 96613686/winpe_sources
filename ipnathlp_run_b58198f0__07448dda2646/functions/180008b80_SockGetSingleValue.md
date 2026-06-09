# SockGetSingleValue

- ea: `0x180008b80`
- end: `0x180008de0`
- name: `SockGetSingleValue`
- size: `608`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, ULONG)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009e48`

## callees

- `0x180008b80`
- `0x180052bf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d61`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180008d4e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180008d4e`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180008cd4`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180008cd4`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180008c42`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180008c42`
- `ntdll!RtlAllocateHeap` at `0x180008bce`
- `ntdll!RtlAllocateHeap` at `0x180008c0c`
- `ntdll!RtlAllocateHeap` at `0x180008bce`
- `ntdll!RtlAllocateHeap` at `0x180008c0c`
- `ntdll!RtlFreeHeap` at `0x180008cf7`
- `ntdll!RtlFreeHeap` at `0x180008d25`
- `ntdll!RtlFreeHeap` at `0x180008d82`
- `ntdll!RtlFreeHeap` at `0x180008da6`
- `ntdll!RtlFreeHeap` at `0x180008cf7`
- `ntdll!RtlFreeHeap` at `0x180008d25`
- `ntdll!RtlFreeHeap` at `0x180008d82`
- `ntdll!RtlFreeHeap` at `0x180008da6`
- `ntdll!NtQueryValueKey` at `0x180008c6c`
- `ntdll!NtQueryValueKey` at `0x180008c6c`

## string_xrefs

- `0x180008c25`: `DatabasePath`

## pseudocode

```c

```
