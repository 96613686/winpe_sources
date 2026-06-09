# BasepGetVolumeDosLetterNameFromNTName

- ea: `0x180084400`
- end: `0x18008474a`
- name: `BasepGetVolumeDosLetterNameFromNTName`
- size: `842`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x180083ac0`

## callees

- `0x18004c490`
- `0x180053330`
- `0x180053c30`
- `0x180084400`
- `0x180194eb9`
- `0x180194ec5`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18008456f`
- `ntdll!RtlInitUnicodeString` at `0x18008456f`
- `ntdll!wcslen` at `0x180084480`
- `ntdll!wcslen` at `0x1800844c4`
- `ntdll!wcslen` at `0x180084480`
- `ntdll!wcslen` at `0x1800844c4`
- `ntdll!_wcsnicmp` at `0x18008442c`
- `ntdll!_wcsnicmp` at `0x18008442c`
- `ntdll!RtlSetLastWin32Error` at `0x1800846af`
- `ntdll!RtlSetLastWin32Error` at `0x18019dcb2`
- `ntdll!RtlSetLastWin32Error` at `0x1800846af`
- `ntdll!RtlSetLastWin32Error` at `0x18019dcb2`
- `ntdll!RtlFreeHeap` at `0x1800845f5`
- `ntdll!RtlFreeHeap` at `0x18008463b`
- `ntdll!RtlFreeHeap` at `0x1800846d4`
- `ntdll!RtlFreeHeap` at `0x180084739`
- `ntdll!RtlFreeHeap` at `0x1800845f5`
- `ntdll!RtlFreeHeap` at `0x18008463b`
- `ntdll!RtlFreeHeap` at `0x1800846d4`
- `ntdll!RtlFreeHeap` at `0x180084739`
- `ntdll!RtlAllocateHeap` at `0x1800844a9`
- `ntdll!RtlAllocateHeap` at `0x18008450b`
- `ntdll!RtlAllocateHeap` at `0x180084662`
- `ntdll!RtlAllocateHeap` at `0x1800844a9`
- `ntdll!RtlAllocateHeap` at `0x18008450b`
- `ntdll!RtlAllocateHeap` at `0x180084662`

## string_xrefs

- `0x180084462`: `\\.\MountPointManager`

## pseudocode

```c

```
