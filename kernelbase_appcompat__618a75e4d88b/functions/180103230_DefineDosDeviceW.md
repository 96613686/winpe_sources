# DefineDosDeviceW

- ea: `0x180103230`
- end: `0x1801033f5`
- name: `DefineDosDeviceW`
- size: `453`
- prototype: `BOOL __stdcall(DWORD dwFlags, LPCWSTR lpDeviceName, LPCWSTR lpTargetPath)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callees

- `0x1800393f0`
- `0x18004b9d0`
- `0x18004cc30`
- `0x18004ce20`
- `0x180103230`
- `0x1801033fc`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1801033e4`
- `ntdll!RtlFreeUnicodeString` at `0x1801033e4`
- `ntdll!RtlInitUnicodeString` at `0x180103377`
- `ntdll!RtlInitUnicodeString` at `0x180103377`
- `ntdll!RtlUpcaseUnicodeChar` at `0x1801a23b4`
- `ntdll!RtlUpcaseUnicodeChar` at `0x1801a23b4`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1801033c2`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1801033c2`
- `ntdll!RtlSetLastWin32Error` at `0x18010335f`
- `ntdll!RtlSetLastWin32Error` at `0x18010335f`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801032b6`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801032e7`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801032b6`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801032e7`

## string_xrefs

- `0x1801a23e9`: `USER32.DLL`

## pseudocode

```c

```
