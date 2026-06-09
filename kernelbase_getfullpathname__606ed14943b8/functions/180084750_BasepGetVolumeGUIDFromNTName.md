# BasepGetVolumeGUIDFromNTName

- ea: `0x180084750`
- end: `0x180084ac0`
- name: `BasepGetVolumeGUIDFromNTName`
- size: `880`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x180083ac0`

## callees

- `0x18004c490`
- `0x180053330`
- `0x180053c30`
- `0x180084750`
- `0x180194eb9`

## import_xrefs

- `ntdll!wcslen` at `0x1800847a6`
- `ntdll!wcslen` at `0x1800847ff`
- `ntdll!wcslen` at `0x1800847a6`
- `ntdll!wcslen` at `0x1800847ff`
- `ntdll!RtlSetLastWin32Error` at `0x1800849dc`
- `ntdll!RtlSetLastWin32Error` at `0x180084a8a`
- `ntdll!RtlSetLastWin32Error` at `0x1800849dc`
- `ntdll!RtlSetLastWin32Error` at `0x180084a8a`
- `ntdll!RtlFreeHeap` at `0x1800849c7`
- `ntdll!RtlFreeHeap` at `0x180084a07`
- `ntdll!RtlFreeHeap` at `0x180084a74`
- `ntdll!RtlFreeHeap` at `0x180084aaf`
- `ntdll!RtlFreeHeap` at `0x1800849c7`
- `ntdll!RtlFreeHeap` at `0x180084a07`
- `ntdll!RtlFreeHeap` at `0x180084a74`
- `ntdll!RtlFreeHeap` at `0x180084aaf`
- `ntdll!RtlAllocateHeap` at `0x1800847d0`
- `ntdll!RtlAllocateHeap` at `0x180084847`
- `ntdll!RtlAllocateHeap` at `0x18008497a`
- `ntdll!RtlAllocateHeap` at `0x1800847d0`
- `ntdll!RtlAllocateHeap` at `0x180084847`
- `ntdll!RtlAllocateHeap` at `0x18008497a`

## string_xrefs

- `0x18008477e`: `\\.\MountPointManager`

## pseudocode

```c

```
