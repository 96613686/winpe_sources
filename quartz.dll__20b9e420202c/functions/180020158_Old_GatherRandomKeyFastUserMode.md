# Old_GatherRandomKeyFastUserMode

- ea: `0x180020158`
- end: `0x18002033c`
- name: `Old_GatherRandomKeyFastUserMode`
- size: `484`
- prototype: `__int64 __fastcall(LPVOID lpInBuffer, DWORD nInBufferSize, LPVOID lpOutBuffer, LPDWORD lpBytesReturned)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002f154`

## callees

- `0x180020158`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800201b3`
- `KERNEL32!GetProcAddress` at `0x1800201df`
- `KERNEL32!GetProcAddress` at `0x1800201fc`
- `KERNEL32!GetProcAddress` at `0x1800201b3`
- `KERNEL32!GetProcAddress` at `0x1800201df`
- `KERNEL32!GetProcAddress` at `0x1800201fc`
- `KERNEL32!GetModuleHandleW` at `0x180020195`
- `KERNEL32!GetModuleHandleW` at `0x180020195`
- `KERNEL32!CloseHandle` at `0x1800202de`
- `KERNEL32!CloseHandle` at `0x1800202de`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180020315`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180020315`

## string_xrefs

- `0x18002018e`: `ntdll.dll`
- `0x1800201d5`: `NtOpenFile`

## pseudocode

```c

```
