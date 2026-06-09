# GetComputerNameA

- ea: `0x180039700`
- end: `0x180039816`
- name: `GetComputerNameA`
- size: `278`
- prototype: `BOOL __stdcall(LPSTR lpBuffer, LPDWORD nSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180039700`
- `0x180039820`
- `0x180039b98`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18003980e`
- `ntdll!RtlSetLastWin32Error` at `0x18003980e`
- `ntdll!RtlFreeHeap` at `0x18003976f`
- `ntdll!RtlFreeHeap` at `0x1800397f3`
- `ntdll!RtlFreeHeap` at `0x18003976f`
- `ntdll!RtlFreeHeap` at `0x1800397f3`
- `ntdll!RtlAllocateHeap` at `0x1800397be`
- `ntdll!RtlAllocateHeap` at `0x1800397be`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800397a1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800397a1`

## pseudocode

```c

```
