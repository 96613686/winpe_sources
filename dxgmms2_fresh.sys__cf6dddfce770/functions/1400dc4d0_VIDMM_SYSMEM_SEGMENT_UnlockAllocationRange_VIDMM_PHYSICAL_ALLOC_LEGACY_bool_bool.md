# VIDMM_SYSMEM_SEGMENT::UnlockAllocationRange(VIDMM_PHYSICAL_ALLOC_LEGACY *,bool,bool)

- ea: `0x1400dc4d0`
- end: `0x1400dc754`
- name: `?UnlockAllocationRange@VIDMM_SYSMEM_SEGMENT@@UEAAXPEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_N1@Z`
- size: `644`
- prototype: `void(VIDMM_SYSMEM_SEGMENT *__hidden this, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool, bool)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x140004268`
- `0x140058f50`
- `0x140059080`
- `0x140059380`
- `0x1400dc4d0`
- `0x1401104dc`
- `0x140110ae0`
- `0x14011ac38`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400dc5a5`
- `ntoskrnl!KeStackAttachProcess` at `0x1400dc5a5`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400dc6c6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400dc6c6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dc53b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dc53b`
- `watchdog!WdLogSingleEntry0` at `0x1400dc631`
- `watchdog!WdLogSingleEntry0` at `0x1400dc631`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400dc52f`

## string_xrefs

- `0x1400dc66b`: `Encountered a fault trying to copy to the user VA from the guaranteed forward progress VA`

## pseudocode

```c

```
