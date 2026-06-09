# BasepGetVolumeDosLetterNameFromNTName

- ea: `0x180078834`
- end: `0x180078b35`
- name: `BasepGetVolumeDosLetterNameFromNTName`
- size: `769`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x180077f90`

## callees

- `0x180013ec0`
- `0x1800486a0`
- `0x180048f30`
- `0x180078834`
- `0x180188eb9`
- `0x180188ec5`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180078985`
- `ntdll!RtlInitUnicodeString` at `0x180078985`
- `ntdll!wcslen` at `0x1800788ae`
- `ntdll!wcslen` at `0x1800788e6`
- `ntdll!wcslen` at `0x1800788ae`
- `ntdll!wcslen` at `0x1800788e6`
- `ntdll!_wcsnicmp` at `0x180078860`
- `ntdll!_wcsnicmp` at `0x180078860`
- `ntdll!RtlSetLastWin32Error` at `0x180078aac`
- `ntdll!RtlSetLastWin32Error` at `0x180190d12`
- `ntdll!RtlSetLastWin32Error` at `0x180078aac`
- `ntdll!RtlSetLastWin32Error` at `0x180190d12`
- `ntdll!RtlFreeHeap` at `0x180078a05`
- `ntdll!RtlFreeHeap` at `0x180078a44`
- `ntdll!RtlFreeHeap` at `0x180078acb`
- `ntdll!RtlFreeHeap` at `0x180078b2a`
- `ntdll!RtlFreeHeap` at `0x180078a05`
- `ntdll!RtlFreeHeap` at `0x180078a44`
- `ntdll!RtlFreeHeap` at `0x180078acb`
- `ntdll!RtlFreeHeap` at `0x180078b2a`
- `ntdll!RtlAllocateHeap` at `0x1800788d1`
- `ntdll!RtlAllocateHeap` at `0x180078927`
- `ntdll!RtlAllocateHeap` at `0x180078a65`
- `ntdll!RtlAllocateHeap` at `0x1800788d1`
- `ntdll!RtlAllocateHeap` at `0x180078927`
- `ntdll!RtlAllocateHeap` at `0x180078a65`

## string_xrefs

- `0x180078890`: `\\.\MountPointManager`

## pseudocode

```c

```
