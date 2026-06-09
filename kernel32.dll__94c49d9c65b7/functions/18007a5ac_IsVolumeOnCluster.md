# IsVolumeOnCluster

- ea: `0x18007a5ac`
- end: `0x18007a68e`
- name: `IsVolumeOnCluster`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180054f30`

## callees

- `0x18007a15c`
- `0x18007a3a8`
- `0x18007a5ac`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18007a641`
- `ntdll!RtlSetLastWin32Error` at `0x18007a641`
- `ntdll!RtlFreeHeap` at `0x18007a679`
- `ntdll!RtlFreeHeap` at `0x18007a679`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a65c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a65c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007a5fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007a5fc`

## pseudocode

```c

```
