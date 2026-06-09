# GetTempFileNameW

- ea: `0x1800836d0`
- end: `0x180083a54`
- name: `GetTempFileNameW`
- size: `900`
- prototype: `UINT __stdcall(LPCWSTR lpPathName, LPCWSTR lpPrefixString, UINT uUnique, LPWSTR lpTempFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1801144a0`

## callees

- `0x18004b9d0`
- `0x1800533cc`
- `0x180083140`
- `0x1800836d0`
- `0x18013877c`
- `0x180194ec5`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180083941`
- `ntdll!RtlSetLastWin32Error` at `0x180083941`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800838b1`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800838b1`
- `ntdll!RtlInitUnicodeStringEx` at `0x180083723`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800837aa`
- `ntdll!RtlInitUnicodeStringEx` at `0x180083723`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800837aa`
- `ntdll!NtClose` at `0x18008390d`
- `ntdll!NtClose` at `0x18008390d`
- `ntdll!RtlIntegerToChar` at `0x180083854`
- `ntdll!RtlIntegerToChar` at `0x180083854`
- `ntdll!RtlAnsiCharToUnicodeChar` at `0x18008386c`
- `ntdll!RtlAnsiCharToUnicodeChar` at `0x18008386c`

## pseudocode

```c

```
