# BasepGetVolumeGUIDFromNTName

- ea: `0x180078b3c`
- end: `0x180078e65`
- name: `BasepGetVolumeGUIDFromNTName`
- size: `809`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x180077f90`

## callees

- `0x180013ec0`
- `0x1800486a0`
- `0x180048f30`
- `0x180078b3c`
- `0x180188eb9`

## import_xrefs

- `ntdll!wcslen` at `0x180078b92`
- `ntdll!wcslen` at `0x180078bdf`
- `ntdll!wcslen` at `0x180078b92`
- `ntdll!wcslen` at `0x180078bdf`
- `ntdll!RtlSetLastWin32Error` at `0x180078da4`
- `ntdll!RtlSetLastWin32Error` at `0x180078e3b`
- `ntdll!RtlSetLastWin32Error` at `0x180078da4`
- `ntdll!RtlSetLastWin32Error` at `0x180078e3b`
- `ntdll!RtlFreeHeap` at `0x180078d95`
- `ntdll!RtlFreeHeap` at `0x180078dc9`
- `ntdll!RtlFreeHeap` at `0x180078e2b`
- `ntdll!RtlFreeHeap` at `0x180078e5a`
- `ntdll!RtlFreeHeap` at `0x180078d95`
- `ntdll!RtlFreeHeap` at `0x180078dc9`
- `ntdll!RtlFreeHeap` at `0x180078e2b`
- `ntdll!RtlFreeHeap` at `0x180078e5a`
- `ntdll!RtlAllocateHeap` at `0x180078bb6`
- `ntdll!RtlAllocateHeap` at `0x180078c21`
- `ntdll!RtlAllocateHeap` at `0x180078d4e`
- `ntdll!RtlAllocateHeap` at `0x180078bb6`
- `ntdll!RtlAllocateHeap` at `0x180078c21`
- `ntdll!RtlAllocateHeap` at `0x180078d4e`

## string_xrefs

- `0x180078b6a`: `\\.\MountPointManager`

## pseudocode

```c

```
