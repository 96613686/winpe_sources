# DragDropTelemetryHelper::GetProcessNameFromId(ulong,ushort *,ulong)

- ea: `0x180035a20`
- end: `0x180035ab8`
- name: `?GetProcessNameFromId@DragDropTelemetryHelper@@SA_NKPEAGK@Z`
- size: `152`
- prototype: `bool __fastcall(unsigned int processId, wchar_t *processName, unsigned int processId)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002f63c`
- `0x18003c554`

## callees

- `0x180035a20`

## import_xrefs

- `KERNELBASE!GetPackageFullName` at `0x180035a65`
- `KERNELBASE!GetPackageFullName` at `0x180035a65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035aa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035aa4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180035a44`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180035a44`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180035a8f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180035a8f`

## pseudocode

```c

```
