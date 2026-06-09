# BaseDllFindIniFileNameMapping

- ea: `0x18002f3f0`
- end: `0x18002f5ad`
- name: `BaseDllFindIniFileNameMapping`
- size: `445`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010f0c`

## callees

- `0x18002f3f0`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18002f4a4`
- `ntdll!RtlEqualUnicodeString` at `0x18002f52c`
- `ntdll!RtlEqualUnicodeString` at `0x18002f4a4`
- `ntdll!RtlEqualUnicodeString` at `0x18002f52c`
- `ntdll!RtlGetSuiteMask` at `0x18002f4ae`
- `ntdll!RtlGetSuiteMask` at `0x18002f4ae`
- `ntdll!RtlPrefixUnicodeString` at `0x18002f48f`
- `ntdll!RtlPrefixUnicodeString` at `0x18002f4c7`
- `ntdll!RtlPrefixUnicodeString` at `0x18002f48f`
- `ntdll!RtlPrefixUnicodeString` at `0x18002f4c7`
- `ntdll!RtlInitUnicodeString` at `0x18002f44d`
- `ntdll!RtlInitUnicodeString` at `0x18002f46f`
- `ntdll!RtlInitUnicodeString` at `0x18002f44d`
- `ntdll!RtlInitUnicodeString` at `0x18002f46f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18002f47f`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18002f47f`

## pseudocode

```c

```
