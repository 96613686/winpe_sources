# VIDMM_SEGMENT::SuspendCpuAccess(VIDMM_PAGING_EXECUTION_CONTEXT *)

- ea: `0x1400d6b24`
- end: `0x1400d6ebe`
- name: `?SuspendCpuAccess@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z`
- size: `922`
- prototype: `int(VIDMM_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1400d0890`

## callees

- `0x14002d810`
- `0x14002d8cc`
- `0x14002da90`
- `0x14002dab4`
- `0x140031434`
- `0x14003196c`
- `0x14003a734`
- `0x14003b264`
- `0x140044fcc`
- `0x140058f50`
- `0x140059030`
- `0x14009e4a0`
- `0x1400d6b24`
- `0x140122d88`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d6e61`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d6e61`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d6e6d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d6e6d`
- `watchdog!WdLogSingleEntry5` at `0x1400d6d14`
- `watchdog!WdLogSingleEntry5` at `0x1400d6ea8`
- `watchdog!WdLogSingleEntry5` at `0x1400d6d14`
- `watchdog!WdLogSingleEntry5` at `0x1400d6ea8`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400d6cee`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400d6e82`

## pseudocode

```c

```
