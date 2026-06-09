# FindFirstFileNameTransactedW

- ea: `0x180044650`
- end: `0x1800446ef`
- name: `FindFirstFileNameTransactedW`
- size: `159`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, DWORD dwFlags, LPDWORD StringLength, PWSTR LinkName, HANDLE hTransaction)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180044650`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180044677`
- `ntdll!RtlGetCurrentTransaction` at `0x180044677`
- `ntdll!RtlSetCurrentTransaction` at `0x1800446b0`
- `ntdll!RtlSetCurrentTransaction` at `0x1800446da`
- `ntdll!RtlSetCurrentTransaction` at `0x1800446b0`
- `ntdll!RtlSetCurrentTransaction` at `0x1800446da`
- `ntdll!RtlSetCurrentTransaction` at `0x1800832fa`
- `ntdll!RtlSetLastWin32Error` at `0x18004468d`
- `ntdll!RtlSetLastWin32Error` at `0x18004468d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x1800446c9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x1800446c9`

## pseudocode

```c

```
