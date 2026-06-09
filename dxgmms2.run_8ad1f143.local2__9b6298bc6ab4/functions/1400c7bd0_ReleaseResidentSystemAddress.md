# ReleaseResidentSystemAddress

- ea: `0x1400c7bd0`
- end: `0x1400c7ccc`
- name: `ReleaseResidentSystemAddress`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400c7ce0`

## callees

- `0x14004ba2c`
- `0x1400c7bd0`

## import_xrefs

- `ntoskrnl!MmUnmapReservedMapping` at `0x1400c7c38`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400c7c38`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400c7c63`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400c7c63`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400c7c86`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400c7c86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c7c74`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c7c74`
- `watchdog!WdLogSingleEntry5` at `0x1400c7cb6`
- `watchdog!WdLogSingleEntry5` at `0x1400c7cb6`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400c7c94`

## pseudocode

```c

```
