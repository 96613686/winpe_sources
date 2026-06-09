# DragDropTelemetryHelper::GetProcessNameFromId(ulong,ushort *,ulong)

- ea: `0x18002a420`
- end: `0x18002a4d7`
- name: `?GetProcessNameFromId@DragDropTelemetryHelper@@SA_NKPEAGK@Z`
- size: `183`
- prototype: `bool __fastcall(unsigned int processId, wchar_t *processName, unsigned int processId)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180029a6c`
- `0x18002a198`

## callees

- `0x18002a420`

## import_xrefs

- `KERNELBASE!GetPackageFullName` at `0x18002a46b`
- `KERNELBASE!GetPackageFullName` at `0x18002a46b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4bc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002a444`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002a444`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18002a4a1`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18002a4a1`

## pseudocode

```c

```
