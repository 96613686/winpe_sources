# CreateSymbolicLinkTransactedA

- ea: `0x180073210`
- end: `0x1800732d6`
- name: `CreateSymbolicLinkTransactedA`
- size: `198`
- prototype: `BOOLEAN __stdcall(LPCSTR lpSymlinkFileName, LPCSTR lpTargetFileName, DWORD dwFlags, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callees

- `0x180028f60`
- `0x18005f110`
- `0x180073210`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180073267`
- `ntdll!RtlFreeUnicodeString` at `0x180073291`
- `ntdll!RtlFreeUnicodeString` at `0x1800732a2`
- `ntdll!RtlFreeUnicodeString` at `0x180073267`
- `ntdll!RtlFreeUnicodeString` at `0x180073291`
- `ntdll!RtlFreeUnicodeString` at `0x1800732a2`
- `ntdll!RtlSetLastWin32Error` at `0x1800732b7`
- `ntdll!RtlSetLastWin32Error` at `0x1800732b7`

## pseudocode

```c

```
