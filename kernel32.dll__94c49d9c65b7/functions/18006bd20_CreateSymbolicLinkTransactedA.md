# CreateSymbolicLinkTransactedA

- ea: `0x18006bd20`
- end: `0x18006bdcd`
- name: `CreateSymbolicLinkTransactedA`
- size: `173`
- prototype: `BOOLEAN __stdcall(LPCSTR lpSymlinkFileName, LPCSTR lpTargetFileName, DWORD dwFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callees

- `0x18000d6c0`
- `0x180059990`
- `0x18006bd20`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006bd77`
- `ntdll!RtlFreeUnicodeString` at `0x18006bd9b`
- `ntdll!RtlFreeUnicodeString` at `0x18006bda6`
- `ntdll!RtlFreeUnicodeString` at `0x18006bd77`
- `ntdll!RtlFreeUnicodeString` at `0x18006bd9b`
- `ntdll!RtlFreeUnicodeString` at `0x18006bda6`
- `ntdll!RtlSetLastWin32Error` at `0x18006bdb5`
- `ntdll!RtlSetLastWin32Error` at `0x18006bdb5`

## pseudocode

```c

```
