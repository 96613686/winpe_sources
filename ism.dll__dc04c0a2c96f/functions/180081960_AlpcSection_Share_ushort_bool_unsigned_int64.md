# AlpcSection::Share(ushort,bool,unsigned __int64 *)

- ea: `0x180081960`
- end: `0x180081bc0`
- name: `?Share@AlpcSection@@QEAAJG_NPEA_K@Z`
- size: `608`
- prototype: `__int64 __fastcall(AlpcSection *__hidden this, unsigned __int16, bool, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180143a80`

## callees

- `0x180081960`
- `0x1800a31bc`
- `0x1800a43b0`
- `0x1800f0990`
- `0x180141ea4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081a7b`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180081b45`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180081b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081b76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081b76`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180081a71`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180081a71`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800819f8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800819f8`

## pseudocode

```c

```
