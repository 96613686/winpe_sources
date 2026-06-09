# SetDefaultCommConfigA

- ea: `0x1800671c0`
- end: `0x180067250`
- name: `SetDefaultCommConfigA`
- size: `144`
- prototype: `BOOL __stdcall(LPCSTR lpszName, LPCOMMCONFIG lpCC, DWORD dwSize)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000ccf0`
- `0x1800671c0`
- `0x180067260`

## import_xrefs

- `ntdll!RtlInitAnsiStringEx` at `0x1800671e7`
- `ntdll!RtlInitAnsiStringEx` at `0x1800671e7`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180067219`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180067219`
- `ntdll!RtlFreeUnicodeString` at `0x180067240`
- `ntdll!RtlFreeUnicodeString` at `0x1800839dd`
- `ntdll!RtlFreeUnicodeString` at `0x180067240`
- `ntdll!RtlFreeUnicodeString` at `0x1800839dd`

## pseudocode

```c

```
