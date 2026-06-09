# GetVolumePathNamesForVolumeNameW

- ea: `0x1800e7ec0`
- end: `0x1800e8395`
- name: `GetVolumePathNamesForVolumeNameW`
- size: `1237`
- prototype: `BOOL __stdcall(LPCWSTR lpszVolumeName, LPWCH lpszVolumePathNames, DWORD cchBufferLength, PDWORD lpcchReturnLength)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callees

- `0x18004b9d0`
- `0x18004c490`
- `0x1800533cc`
- `0x180053c30`
- `0x1800e7ec0`
- `0x1801369c9`
- `0x18013877c`
- `0x180194eb9`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800e82a2`
- `ntdll!RtlSetLastWin32Error` at `0x1800e8304`
- `ntdll!RtlSetLastWin32Error` at `0x1800e82a2`
- `ntdll!RtlSetLastWin32Error` at `0x1800e8304`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e7ef8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800e7ef8`
- `ntdll!RtlFreeHeap` at `0x1800e8151`
- `ntdll!RtlFreeHeap` at `0x1800e81ea`
- `ntdll!RtlFreeHeap` at `0x1800e8240`
- `ntdll!RtlFreeHeap` at `0x1800e8294`
- `ntdll!RtlFreeHeap` at `0x1800e833f`
- `ntdll!RtlFreeHeap` at `0x1800e837d`
- `ntdll!RtlFreeHeap` at `0x1800e8151`
- `ntdll!RtlFreeHeap` at `0x1800e81ea`
- `ntdll!RtlFreeHeap` at `0x1800e8240`
- `ntdll!RtlFreeHeap` at `0x1800e8294`
- `ntdll!RtlFreeHeap` at `0x1800e833f`
- `ntdll!RtlFreeHeap` at `0x1800e837d`
- `ntdll!RtlAllocateHeap` at `0x1800e8027`
- `ntdll!RtlAllocateHeap` at `0x1800e80df`
- `ntdll!RtlAllocateHeap` at `0x1800e8262`
- `ntdll!RtlAllocateHeap` at `0x1800e8027`
- `ntdll!RtlAllocateHeap` at `0x1800e80df`
- `ntdll!RtlAllocateHeap` at `0x1800e8262`

## string_xrefs

- `0x1800e8083`: `\\.\MountPointManager`

## pseudocode

```c

```
