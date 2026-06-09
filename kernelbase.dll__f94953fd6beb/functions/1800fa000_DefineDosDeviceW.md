# DefineDosDeviceW

- ea: `0x1800fa000`
- end: `0x1800fa1a0`
- name: `DefineDosDeviceW`
- size: `416`
- prototype: `BOOL __stdcall(DWORD dwFlags, LPCWSTR lpDeviceName, LPCWSTR lpTargetPath)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callees

- `0x1800134a0`
- `0x1800145c0`
- `0x1800147a0`
- `0x1800222a0`
- `0x1800fa000`
- `0x1800fa1a8`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800fa195`
- `ntdll!RtlFreeUnicodeString` at `0x1800fa195`
- `ntdll!RtlInitUnicodeString` at `0x1800fa134`
- `ntdll!RtlInitUnicodeString` at `0x1800fa134`
- `ntdll!RtlUpcaseUnicodeChar` at `0x1801952ba`
- `ntdll!RtlUpcaseUnicodeChar` at `0x1801952ba`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800fa179`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800fa179`
- `ntdll!RtlSetLastWin32Error` at `0x1800fa122`
- `ntdll!RtlSetLastWin32Error` at `0x1800fa122`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800fa086`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800fa0b1`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800fa086`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800fa0b1`

## string_xrefs

- `0x1801952e9`: `USER32.DLL`

## pseudocode

```c

```
