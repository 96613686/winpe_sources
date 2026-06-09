# GetVolumePathNamesForVolumeNameW

- ea: `0x1800dfdc0`
- end: `0x1800e024c`
- name: `GetVolumePathNamesForVolumeNameW`
- size: `1164`
- prototype: `BOOL __stdcall(LPCWSTR lpszVolumeName, LPWCH lpszVolumePathNames, DWORD cchBufferLength, PDWORD lpcchReturnLength)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callees

- `0x1800134a0`
- `0x180013ec0`
- `0x18004873c`
- `0x180048f30`
- `0x1800dfdc0`
- `0x18012d119`
- `0x18012eecc`
- `0x180188eb9`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800e0171`
- `ntdll!RtlSetLastWin32Error` at `0x1800e01cd`
- `ntdll!RtlSetLastWin32Error` at `0x1800e0171`
- `ntdll!RtlSetLastWin32Error` at `0x1800e01cd`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800dfdf8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800dfdf8`
- `ntdll!RtlFreeHeap` at `0x1800e003f`
- `ntdll!RtlFreeHeap` at `0x1800e00d2`
- `ntdll!RtlFreeHeap` at `0x1800e0121`
- `ntdll!RtlFreeHeap` at `0x1800e0169`
- `ntdll!RtlFreeHeap` at `0x1800e0202`
- `ntdll!RtlFreeHeap` at `0x1800e023a`
- `ntdll!RtlFreeHeap` at `0x1800e003f`
- `ntdll!RtlFreeHeap` at `0x1800e00d2`
- `ntdll!RtlFreeHeap` at `0x1800e0121`
- `ntdll!RtlFreeHeap` at `0x1800e0169`
- `ntdll!RtlFreeHeap` at `0x1800e0202`
- `ntdll!RtlFreeHeap` at `0x1800e023a`
- `ntdll!RtlAllocateHeap` at `0x1800dff21`
- `ntdll!RtlAllocateHeap` at `0x1800dffd3`
- `ntdll!RtlAllocateHeap` at `0x1800e013d`
- `ntdll!RtlAllocateHeap` at `0x1800dff21`
- `ntdll!RtlAllocateHeap` at `0x1800dffd3`
- `ntdll!RtlAllocateHeap` at `0x1800e013d`

## string_xrefs

- `0x1800dff77`: `\\.\MountPointManager`

## pseudocode

```c

```
