# PeekNamedPipe

- ea: `0x1800b2ba0`
- end: `0x1800b2da1`
- name: `PeekNamedPipe`
- size: `513`
- prototype: `BOOL __stdcall(HANDLE hNamedPipe, LPVOID lpBuffer, DWORD nBufferSize, LPDWORD lpBytesRead, LPDWORD lpTotalBytesAvail, LPDWORD lpBytesLeftThisMessage)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800134a0`
- `0x1800b2ba0`
- `0x180188eb9`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x1800b2c86`
- `ntdll!NtFsControlFile` at `0x1800b2c86`
- `ntdll!NtWaitForSingleObject` at `0x1800b2ca3`
- `ntdll!NtWaitForSingleObject` at `0x1800b2ca3`
- `ntdll!NtCreateEvent` at `0x1800b2c42`
- `ntdll!NtCreateEvent` at `0x1800b2c42`
- `ntdll!NtClose` at `0x1800b2d42`
- `ntdll!NtClose` at `0x18018b0f6`
- `ntdll!NtClose` at `0x1800b2d42`
- `ntdll!NtClose` at `0x18018b0f6`
- `ntdll!RtlFreeHeap` at `0x1800b2d37`
- `ntdll!RtlFreeHeap` at `0x1800b2d8f`
- `ntdll!RtlFreeHeap` at `0x18018b0ec`
- `ntdll!RtlFreeHeap` at `0x1800b2d37`
- `ntdll!RtlFreeHeap` at `0x1800b2d8f`
- `ntdll!RtlFreeHeap` at `0x18018b0ec`
- `ntdll!RtlAllocateHeap` at `0x1800b2be6`
- `ntdll!RtlAllocateHeap` at `0x1800b2be6`

## pseudocode

```c

```
