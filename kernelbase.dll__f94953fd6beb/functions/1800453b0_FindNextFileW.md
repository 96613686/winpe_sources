# FindNextFileW

- ea: `0x1800453b0`
- end: `0x18004564c`
- name: `FindNextFileW`
- size: `668`
- prototype: `BOOL __stdcall(HANDLE hFindFile, LPWIN32_FIND_DATAW lpFindFileData)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180044ff0`
- `0x180045130`
- `0x180153430`

## callees

- `0x1800134a0`
- `0x1800453b0`
- `0x180188eb9`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800453fb`
- `ntdll!RtlEnterCriticalSection` at `0x1800453fb`
- `ntdll!RtlLeaveCriticalSection` at `0x18004560c`
- `ntdll!RtlLeaveCriticalSection` at `0x1801896f4`
- `ntdll!RtlLeaveCriticalSection` at `0x18004560c`
- `ntdll!RtlLeaveCriticalSection` at `0x1801896f4`
- `ntdll!RtlSetLastWin32Error` at `0x1800455fc`
- `ntdll!RtlSetLastWin32Error` at `0x180045642`
- `ntdll!RtlSetLastWin32Error` at `0x1800455fc`
- `ntdll!RtlSetLastWin32Error` at `0x180045642`
- `ntdll!NtQueryDirectoryFileEx` at `0x180045533`
- `ntdll!NtQueryDirectoryFileEx` at `0x180045533`
- `ntdll!RtlAllocateHeap` at `0x1800455d5`
- `ntdll!RtlAllocateHeap` at `0x1800455d5`

## pseudocode

```c

```
