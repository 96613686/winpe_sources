# WcRemoveFilesInDirectoryInternal

- ea: `0x18003551c`
- end: `0x1800358c0`
- name: `WcRemoveFilesInDirectoryInternal`
- size: `932`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180035434`
- `0x18003551c`

## callees

- `0x180004bd0`
- `0x180005704`
- `0x18003551c`
- `0x180035c00`
- `0x1800361b0`
- `0x1800364bc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180035589`
- `ntdll!RtlAllocateHeap` at `0x180035589`
- `ntdll!RtlFreeHeap` at `0x180035881`
- `ntdll!RtlFreeHeap` at `0x180035881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003573b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003573b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035810`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003584d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035810`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003584d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800357f6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800357f6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800356bb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800356bb`

## pseudocode

```c

```
