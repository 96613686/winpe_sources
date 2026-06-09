# BaseDllFindIniFileNameMapping

- ea: `0x180031114`
- end: `0x180031309`
- name: `BaseDllFindIniFileNameMapping`
- size: `501`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e468`

## callees

- `0x180031114`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800311e0`
- `ntdll!RtlEqualUnicodeString` at `0x18003127e`
- `ntdll!RtlEqualUnicodeString` at `0x1800311e0`
- `ntdll!RtlEqualUnicodeString` at `0x18003127e`
- `ntdll!RtlGetSuiteMask` at `0x1800311f0`
- `ntdll!RtlGetSuiteMask` at `0x1800311f0`
- `ntdll!RtlPrefixUnicodeString` at `0x1800311c5`
- `ntdll!RtlPrefixUnicodeString` at `0x18003120f`
- `ntdll!RtlPrefixUnicodeString` at `0x1800311c5`
- `ntdll!RtlPrefixUnicodeString` at `0x18003120f`
- `ntdll!RtlInitUnicodeString` at `0x180031171`
- `ntdll!RtlInitUnicodeString` at `0x180031199`
- `ntdll!RtlInitUnicodeString` at `0x180031171`
- `ntdll!RtlInitUnicodeString` at `0x180031199`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800311af`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800311af`

## pseudocode

```c

```
