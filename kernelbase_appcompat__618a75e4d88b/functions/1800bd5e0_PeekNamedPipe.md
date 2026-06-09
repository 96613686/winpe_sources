# PeekNamedPipe

- ea: `0x1800bd5e0`
- end: `0x1800bd80c`
- name: `PeekNamedPipe`
- size: `556`
- prototype: `BOOL __stdcall(HANDLE hNamedPipe, LPVOID lpBuffer, DWORD nBufferSize, LPDWORD lpBytesRead, LPDWORD lpTotalBytesAvail, LPDWORD lpBytesLeftThisMessage)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18004b9d0`
- `0x1800bd5e0`
- `0x180194eb9`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x1800bd6d2`
- `ntdll!NtFsControlFile` at `0x1800bd6d2`
- `ntdll!NtWaitForSingleObject` at `0x1800bd6f5`
- `ntdll!NtWaitForSingleObject` at `0x1800bd6f5`
- `ntdll!NtCreateEvent` at `0x1800bd688`
- `ntdll!NtCreateEvent` at `0x1800bd688`
- `ntdll!NtClose` at `0x1800bd7a0`
- `ntdll!NtClose` at `0x18019724c`
- `ntdll!NtClose` at `0x1800bd7a0`
- `ntdll!NtClose` at `0x18019724c`
- `ntdll!RtlFreeHeap` at `0x1800bd78f`
- `ntdll!RtlFreeHeap` at `0x1800bd7f4`
- `ntdll!RtlFreeHeap` at `0x18019723c`
- `ntdll!RtlFreeHeap` at `0x1800bd78f`
- `ntdll!RtlFreeHeap` at `0x1800bd7f4`
- `ntdll!RtlFreeHeap` at `0x18019723c`
- `ntdll!RtlAllocateHeap` at `0x1800bd626`
- `ntdll!RtlAllocateHeap` at `0x1800bd626`

## pseudocode

```c

```
