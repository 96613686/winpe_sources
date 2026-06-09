# AslAnsiStringCreate

- ea: `0x180067d20`
- end: `0x180067dc0`
- name: `AslAnsiStringCreate`
- size: `160`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180032160`
- `0x180068e60`

## callees

- `0x180066c10`
- `0x180067d20`
- `0x1800682e8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180067da8`
- `ntdll!RtlFreeHeap` at `0x180067da8`
- `ntdll!RtlInitAnsiString` at `0x180067d89`
- `ntdll!RtlInitAnsiString` at `0x180067d89`

## string_xrefs

- `0x180067d69`: `AslAnsiStringCreate`

## pseudocode

```c

```
