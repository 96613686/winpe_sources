# UpdateResourceA

- ea: `0x1800634e0`
- end: `0x18006361c`
- name: `UpdateResourceA`
- size: `316`
- prototype: `BOOL __stdcall(HANDLE hUpdate, LPCSTR lpType, LPCSTR lpName, WORD wLanguage, LPVOID lpData, DWORD cb)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000f920`
- `0x1800634e0`
- `0x180063630`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x180063567`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800635b1`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180063567`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800635b1`
- `ntdll!strlen` at `0x180063543`
- `ntdll!strlen` at `0x18006358d`
- `ntdll!strlen` at `0x180063543`
- `ntdll!strlen` at `0x18006358d`
- `ntdll!RtlFreeUnicodeString` at `0x1800635f1`
- `ntdll!RtlFreeUnicodeString` at `0x1800635fc`
- `ntdll!RtlFreeUnicodeString` at `0x18007b94b`
- `ntdll!RtlFreeUnicodeString` at `0x18007b955`
- `ntdll!RtlFreeUnicodeString` at `0x1800635f1`
- `ntdll!RtlFreeUnicodeString` at `0x1800635fc`
- `ntdll!RtlFreeUnicodeString` at `0x18007b94b`
- `ntdll!RtlFreeUnicodeString` at `0x18007b955`
- `ntdll!RtlInitUnicodeString` at `0x180063523`
- `ntdll!RtlInitUnicodeString` at `0x180063530`
- `ntdll!RtlInitUnicodeString` at `0x180063523`
- `ntdll!RtlInitUnicodeString` at `0x180063530`

## pseudocode

```c

```
