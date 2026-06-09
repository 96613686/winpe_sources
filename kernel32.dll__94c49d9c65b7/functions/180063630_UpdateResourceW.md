# UpdateResourceW

- ea: `0x180063630`
- end: `0x18006384e`
- name: `UpdateResourceW`
- size: `542`
- prototype: `BOOL __stdcall(HANDLE hUpdate, LPCWSTR lpType, LPCWSTR lpName, WORD wLanguage, LPVOID lpData, DWORD cb)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x1800634e0`

## callees

- `0x18004a42c`
- `0x180062378`
- `0x1800629c4`
- `0x180062b10`
- `0x180062d18`
- `0x180063630`
- `0x18007a7d1`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18006365b`
- `ntdll!RtlSetLastWin32Error` at `0x18006368f`
- `ntdll!RtlSetLastWin32Error` at `0x18006365b`
- `ntdll!RtlSetLastWin32Error` at `0x18006368f`
- `ntdll!RtlFreeHeap` at `0x18006378c`
- `ntdll!RtlFreeHeap` at `0x1800637aa`
- `ntdll!RtlFreeHeap` at `0x180063843`
- `ntdll!RtlFreeHeap` at `0x18006378c`
- `ntdll!RtlFreeHeap` at `0x1800637aa`
- `ntdll!RtlFreeHeap` at `0x180063843`
- `ntdll!RtlAllocateHeap` at `0x180063762`
- `ntdll!RtlAllocateHeap` at `0x180063762`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006373d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006373d`
- `KERNELBASE!GlobalFree` at `0x180063811`
- `KERNELBASE!GlobalFree` at `0x180063811`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180063664`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800636b7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180063664`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800636b7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800636df`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063708`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800637ff`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063822`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800636df`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063708`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800637ff`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180063822`

## pseudocode

```c

```
