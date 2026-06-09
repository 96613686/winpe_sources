# IsDiskOnCluster

- ea: `0x1800822b8`
- end: `0x1800823e9`
- name: `IsDiskOnCluster`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800824f4`

## callees

- `0x18003a2a4`
- `0x1800822b8`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180082399`
- `ntdll!RtlSetLastWin32Error` at `0x180082399`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800823b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800823b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082333`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082333`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18008237b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18008237b`

## pseudocode

```c

```
