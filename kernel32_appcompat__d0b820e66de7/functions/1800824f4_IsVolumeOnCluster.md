# IsVolumeOnCluster

- ea: `0x1800824f4`
- end: `0x1800825ef`
- name: `IsVolumeOnCluster`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180059fb0`

## callees

- `0x180082030`
- `0x1800822b8`
- `0x1800824f4`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18008258f`
- `ntdll!RtlSetLastWin32Error` at `0x18008258f`
- `ntdll!RtlFreeHeap` at `0x1800825d3`
- `ntdll!RtlFreeHeap` at `0x1800825d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800825b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800825b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082544`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082544`

## pseudocode

```c

```
