# GetNamedPipeHandleStateA

- ea: `0x1800454f0`
- end: `0x180045670`
- name: `GetNamedPipeHandleStateA`
- size: `384`
- prototype: `BOOL __stdcall(HANDLE hNamedPipe, LPDWORD lpState, LPDWORD lpCurInstances, LPDWORD lpMaxCollectionCount, LPDWORD lpCollectDataTimeout, LPSTR lpUserName, DWORD nMaxUserNameSize)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ccf0`
- `0x1800454f0`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800455e6`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800455e6`
- `ntdll!RtlSetLastWin32Error` at `0x18004562e`
- `ntdll!RtlSetLastWin32Error` at `0x18004562e`
- `ntdll!RtlInitUnicodeString` at `0x1800455cf`
- `ntdll!RtlInitUnicodeString` at `0x1800455cf`
- `ntdll!RtlFreeHeap` at `0x180045619`
- `ntdll!RtlFreeHeap` at `0x180045619`
- `ntdll!RtlAllocateHeap` at `0x180045571`
- `ntdll!RtlAllocateHeap` at `0x180045571`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180045551`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180045551`
- `api-ms-win-core-namedpipe-l1-2-1!GetNamedPipeHandleStateW` at `0x1800455b5`
- `api-ms-win-core-namedpipe-l1-2-1!GetNamedPipeHandleStateW` at `0x180045658`
- `api-ms-win-core-namedpipe-l1-2-1!GetNamedPipeHandleStateW` at `0x1800455b5`
- `api-ms-win-core-namedpipe-l1-2-1!GetNamedPipeHandleStateW` at `0x180045658`

## pseudocode

```c

```
