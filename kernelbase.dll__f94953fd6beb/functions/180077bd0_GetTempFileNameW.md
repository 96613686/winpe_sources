# GetTempFileNameW

- ea: `0x180077bd0`
- end: `0x180077f29`
- name: `GetTempFileNameW`
- size: `857`
- prototype: `UINT __stdcall(LPCWSTR lpPathName, LPCWSTR lpPrefixString, UINT uUnique, LPWSTR lpTempFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18010b5a0`

## callees

- `0x1800134a0`
- `0x18004873c`
- `0x180077680`
- `0x180077bd0`
- `0x18012eecc`
- `0x180188ec5`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180077e1c`
- `ntdll!RtlSetLastWin32Error` at `0x180077e1c`
- `ntdll!RtlIsDosDeviceName_U` at `0x180077d99`
- `ntdll!RtlIsDosDeviceName_U` at `0x180077d99`
- `ntdll!RtlInitUnicodeStringEx` at `0x180077c23`
- `ntdll!RtlInitUnicodeStringEx` at `0x180077ca4`
- `ntdll!RtlInitUnicodeStringEx` at `0x180077c23`
- `ntdll!RtlInitUnicodeStringEx` at `0x180077ca4`
- `ntdll!NtClose` at `0x180077def`
- `ntdll!NtClose` at `0x180077def`
- `ntdll!RtlIntegerToChar` at `0x180077d48`
- `ntdll!RtlIntegerToChar` at `0x180077d48`
- `ntdll!RtlAnsiCharToUnicodeChar` at `0x180077d5a`
- `ntdll!RtlAnsiCharToUnicodeChar` at `0x180077d5a`

## pseudocode

```c

```
