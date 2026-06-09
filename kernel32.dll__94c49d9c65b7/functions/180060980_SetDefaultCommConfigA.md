# SetDefaultCommConfigA

- ea: `0x180060980`
- end: `0x1800609fd`
- name: `SetDefaultCommConfigA`
- size: `125`
- prototype: `BOOL __stdcall(LPCSTR lpszName, LPCOMMCONFIG lpCC, DWORD dwSize)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000f920`
- `0x180060980`
- `0x180060a10`

## import_xrefs

- `ntdll!RtlInitAnsiStringEx` at `0x1800609a7`
- `ntdll!RtlInitAnsiStringEx` at `0x1800609a7`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800609d2`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800609d2`
- `ntdll!RtlFreeUnicodeString` at `0x1800609f3`
- `ntdll!RtlFreeUnicodeString` at `0x18007b89c`
- `ntdll!RtlFreeUnicodeString` at `0x1800609f3`
- `ntdll!RtlFreeUnicodeString` at `0x18007b89c`

## pseudocode

```c

```
