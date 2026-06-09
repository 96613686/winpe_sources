# GetComputerNameA

- ea: `0x18003c730`
- end: `0x18003c865`
- name: `GetComputerNameA`
- size: `309`
- prototype: `BOOL __stdcall(LPSTR lpBuffer, LPDWORD nSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003c730`
- `0x18003c870`
- `0x18003cc68`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18003c857`
- `ntdll!RtlSetLastWin32Error` at `0x18003c857`
- `ntdll!RtlFreeHeap` at `0x18003c79f`
- `ntdll!RtlFreeHeap` at `0x18003c836`
- `ntdll!RtlFreeHeap` at `0x18003c79f`
- `ntdll!RtlFreeHeap` at `0x18003c836`
- `ntdll!RtlAllocateHeap` at `0x18003c7fb`
- `ntdll!RtlAllocateHeap` at `0x18003c7fb`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003c7d8`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003c7d8`

## pseudocode

```c

```
