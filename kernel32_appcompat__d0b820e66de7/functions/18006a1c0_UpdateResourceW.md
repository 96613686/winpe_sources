# UpdateResourceW

- ea: `0x18006a1c0`
- end: `0x18006a433`
- name: `UpdateResourceW`
- size: `627`
- prototype: `BOOL __stdcall(HANDLE hUpdate, LPCWSTR lpType, LPCWSTR lpName, WORD wLanguage, LPVOID lpData, DWORD cb)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x18006a040`

## callees

- `0x18004e9d8`
- `0x180068cf4`
- `0x1800693bc`
- `0x180069518`
- `0x180069748`
- `0x18006a1c0`
- `0x180082751`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18006a1eb`
- `ntdll!RtlSetLastWin32Error` at `0x18006a22b`
- `ntdll!RtlSetLastWin32Error` at `0x18006a1eb`
- `ntdll!RtlSetLastWin32Error` at `0x18006a22b`
- `ntdll!RtlFreeHeap` at `0x18006a34d`
- `ntdll!RtlFreeHeap` at `0x18006a371`
- `ntdll!RtlFreeHeap` at `0x18006a422`
- `ntdll!RtlFreeHeap` at `0x18006a34d`
- `ntdll!RtlFreeHeap` at `0x18006a371`
- `ntdll!RtlFreeHeap` at `0x18006a422`
- `ntdll!RtlAllocateHeap` at `0x18006a31d`
- `ntdll!RtlAllocateHeap` at `0x18006a31d`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006a2f2`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006a2f2`
- `KERNELBASE!GlobalFree` at `0x18006a3e4`
- `KERNELBASE!GlobalFree` at `0x18006a3e4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006a1fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006a25a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006a1fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006a25a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006a288`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006a2b7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006a3cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006a3fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006a288`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006a2b7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006a3cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18006a3fb`

## pseudocode

```c

```
