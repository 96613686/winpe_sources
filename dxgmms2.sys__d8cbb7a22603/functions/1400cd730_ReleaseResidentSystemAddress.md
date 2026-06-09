# ReleaseResidentSystemAddress

- ea: `0x1400cd730`
- end: `0x1400cd82c`
- name: `ReleaseResidentSystemAddress`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400cd840`

## callees

- `0x14004c13c`
- `0x1400cd730`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x1400cd7c3`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400cd7c3`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400cd798`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400cd798`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400cd7e6`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400cd7e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd7d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd7d4`
- `watchdog!WdLogSingleEntry5` at `0x1400cd816`
- `watchdog!WdLogSingleEntry5` at `0x1400cd816`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400cd7f4`

## pseudocode

```c

```
