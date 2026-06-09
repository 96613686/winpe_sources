# GetPhysicallyInstalledSystemMemory

- ea: `0x1800bb110`
- end: `0x1800bb569`
- name: `GetPhysicallyInstalledSystemMemory`
- size: `1113`
- prototype: `BOOL __stdcall(PULONGLONG TotalMemoryInKilobytes)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x1800bb110`
- `0x1800bb570`
- `0x1800bb7b0`
- `0x1800bb900`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800bb1b8`
- `ntdll!RtlSetLastWin32Error` at `0x1800bb4a0`
- `ntdll!RtlSetLastWin32Error` at `0x1800bb1b8`
- `ntdll!RtlSetLastWin32Error` at `0x1800bb4a0`
- `ntdll!RtlFreeHeap` at `0x1800bb247`
- `ntdll!RtlFreeHeap` at `0x1800bb34e`
- `ntdll!RtlFreeHeap` at `0x1800bb371`
- `ntdll!RtlFreeHeap` at `0x1800bb247`
- `ntdll!RtlFreeHeap` at `0x1800bb34e`
- `ntdll!RtlFreeHeap` at `0x1800bb371`
- `ntdll!RtlAllocateHeap` at `0x1800bb2a6`
- `ntdll!RtlAllocateHeap` at `0x1800bb3b2`
- `ntdll!RtlAllocateHeap` at `0x1800bb45b`
- `ntdll!RtlAllocateHeap` at `0x1800bb2a6`
- `ntdll!RtlAllocateHeap` at `0x1800bb3b2`
- `ntdll!RtlAllocateHeap` at `0x1800bb45b`

## pseudocode

```c

```
