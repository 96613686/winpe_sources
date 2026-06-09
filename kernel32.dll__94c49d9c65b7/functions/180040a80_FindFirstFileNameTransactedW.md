# FindFirstFileNameTransactedW

- ea: `0x180040a80`
- end: `0x180040b00`
- name: `FindFirstFileNameTransactedW`
- size: `128`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, DWORD dwFlags, LPDWORD StringLength, PWSTR LinkName, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180040a80`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180040aa7`
- `ntdll!RtlGetCurrentTransaction` at `0x180040aa7`
- `ntdll!RtlSetCurrentTransaction` at `0x180040ad3`
- `ntdll!RtlSetCurrentTransaction` at `0x180040af1`
- `ntdll!RtlSetCurrentTransaction` at `0x180040ad3`
- `ntdll!RtlSetCurrentTransaction` at `0x180040af1`
- `ntdll!RtlSetCurrentTransaction` at `0x18007b272`
- `ntdll!RtlSetLastWin32Error` at `0x180040ab7`
- `ntdll!RtlSetLastWin32Error` at `0x180040ab7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180040ae6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x180040ae6`

## pseudocode

```c

```
