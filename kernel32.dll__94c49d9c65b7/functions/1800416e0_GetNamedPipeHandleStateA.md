# GetNamedPipeHandleStateA

- ea: `0x1800416e0`
- end: `0x18004182f`
- name: `GetNamedPipeHandleStateA`
- size: `335`
- prototype: `BOOL __stdcall(HANDLE hNamedPipe, LPDWORD lpState, LPDWORD lpCurInstances, LPDWORD lpMaxCollectionCount, LPDWORD lpCollectDataTimeout, LPSTR lpUserName, DWORD nMaxUserNameSize)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f920`
- `0x1800416e0`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800417be`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800417be`
- `ntdll!RtlSetLastWin32Error` at `0x1800417fa`
- `ntdll!RtlSetLastWin32Error` at `0x1800417fa`
- `ntdll!RtlInitUnicodeString` at `0x1800417ad`
- `ntdll!RtlInitUnicodeString` at `0x1800417ad`
- `ntdll!RtlFreeHeap` at `0x1800417eb`
- `ntdll!RtlFreeHeap` at `0x1800417eb`
- `ntdll!RtlAllocateHeap` at `0x18004175b`
- `ntdll!RtlAllocateHeap` at `0x18004175b`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180041741`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180041741`
- `api-ms-win-core-namedpipe-l1-2-1!GetNamedPipeHandleStateW` at `0x180041799`
- `api-ms-win-core-namedpipe-l1-2-1!GetNamedPipeHandleStateW` at `0x18004181e`
- `api-ms-win-core-namedpipe-l1-2-1!GetNamedPipeHandleStateW` at `0x180041799`
- `api-ms-win-core-namedpipe-l1-2-1!GetNamedPipeHandleStateW` at `0x18004181e`

## pseudocode

```c

```
