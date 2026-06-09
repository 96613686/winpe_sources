# FindNextFileW

- ea: `0x180080070`
- end: `0x180080331`
- name: `FindNextFileW`
- size: `705`
- prototype: `BOOL __stdcall(HANDLE hFindFile, LPWIN32_FIND_DATAW lpFindFileData)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007fc70`
- `0x18007fdc0`
- `0x18015dff0`

## callees

- `0x18004b9d0`
- `0x180080070`
- `0x180194eb9`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800800bb`
- `ntdll!RtlEnterCriticalSection` at `0x1800800bb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800802e4`
- `ntdll!RtlLeaveCriticalSection` at `0x180195864`
- `ntdll!RtlLeaveCriticalSection` at `0x1800802e4`
- `ntdll!RtlLeaveCriticalSection` at `0x180195864`
- `ntdll!RtlSetLastWin32Error` at `0x1800802ce`
- `ntdll!RtlSetLastWin32Error` at `0x180080321`
- `ntdll!RtlSetLastWin32Error` at `0x1800802ce`
- `ntdll!RtlSetLastWin32Error` at `0x180080321`
- `ntdll!NtQueryDirectoryFileEx` at `0x1800801f9`
- `ntdll!NtQueryDirectoryFileEx` at `0x1800801f9`
- `ntdll!RtlAllocateHeap` at `0x1800802a1`
- `ntdll!RtlAllocateHeap` at `0x1800802a1`

## pseudocode

```c

```
