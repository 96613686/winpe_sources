# UpdateResourceA

- ea: `0x18006a040`
- end: `0x18006a1ad`
- name: `UpdateResourceA`
- size: `365`
- prototype: `BOOL __stdcall(HANDLE hUpdate, LPCSTR lpType, LPCSTR lpName, WORD wLanguage, LPVOID lpData, DWORD cb)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ccf0`
- `0x18006a040`
- `0x18006a1c0`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x18006a0d9`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18006a12f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18006a0d9`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18006a12f`
- `ntdll!strlen` at `0x18006a0af`
- `ntdll!strlen` at `0x18006a105`
- `ntdll!strlen` at `0x18006a0af`
- `ntdll!strlen` at `0x18006a105`
- `ntdll!RtlFreeUnicodeString` at `0x18006a175`
- `ntdll!RtlFreeUnicodeString` at `0x18006a186`
- `ntdll!RtlFreeUnicodeString` at `0x180083a9e`
- `ntdll!RtlFreeUnicodeString` at `0x180083aae`
- `ntdll!RtlFreeUnicodeString` at `0x18006a175`
- `ntdll!RtlFreeUnicodeString` at `0x18006a186`
- `ntdll!RtlFreeUnicodeString` at `0x180083a9e`
- `ntdll!RtlFreeUnicodeString` at `0x180083aae`
- `ntdll!RtlInitUnicodeString` at `0x18006a083`
- `ntdll!RtlInitUnicodeString` at `0x18006a096`
- `ntdll!RtlInitUnicodeString` at `0x18006a083`
- `ntdll!RtlInitUnicodeString` at `0x18006a096`

## pseudocode

```c

```
