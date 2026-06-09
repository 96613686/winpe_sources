# AslFileMappingDelete

- ea: `0x18006d440`
- end: `0x18006d51c`
- name: `AslFileMappingDelete`
- size: `220`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180066d20`
- `0x18006d140`
- `0x180073a28`
- `0x1800740bc`

## callees

- `0x18006d440`

## import_xrefs

- `ntdll!ZwUnmapViewOfSection` at `0x18006d486`
- `ntdll!ZwUnmapViewOfSection` at `0x18006d486`
- `ntdll!ZwClose` at `0x18006d46d`
- `ntdll!ZwClose` at `0x18006d49b`
- `ntdll!ZwClose` at `0x18006d46d`
- `ntdll!ZwClose` at `0x18006d49b`
- `ntdll!RtlFreeHeap` at `0x18006d4c7`
- `ntdll!RtlFreeHeap` at `0x18006d4ec`
- `ntdll!RtlFreeHeap` at `0x18006d50b`
- `ntdll!RtlFreeHeap` at `0x18006d4c7`
- `ntdll!RtlFreeHeap` at `0x18006d4ec`
- `ntdll!RtlFreeHeap` at `0x18006d50b`

## pseudocode

```c

```
