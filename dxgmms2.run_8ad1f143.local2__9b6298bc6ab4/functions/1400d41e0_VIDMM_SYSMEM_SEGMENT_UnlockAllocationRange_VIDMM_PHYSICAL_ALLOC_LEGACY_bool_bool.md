# VIDMM_SYSMEM_SEGMENT::UnlockAllocationRange(VIDMM_PHYSICAL_ALLOC_LEGACY *,bool,bool)

- ea: `0x1400d41e0`
- end: `0x1400d4464`
- name: `?UnlockAllocationRange@VIDMM_SYSMEM_SEGMENT@@UEAAXPEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_N1@Z`
- size: `644`
- prototype: `void(VIDMM_SYSMEM_SEGMENT *__hidden this, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool, bool)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1400045ec`
- `0x140058680`
- `0x1400587c0`
- `0x140058ac0`
- `0x1400d41e0`
- `0x1400ed9e0`
- `0x14010c8cc`
- `0x140117138`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400d42b5`
- `ntoskrnl!KeStackAttachProcess` at `0x1400d42b5`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400d43d6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400d43d6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d424b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d424b`
- `watchdog!WdLogSingleEntry0` at `0x1400d4341`
- `watchdog!WdLogSingleEntry0` at `0x1400d4341`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400d423f`

## string_xrefs

- `0x1400d437b`: `Encountered a fault trying to copy to the user VA from the guaranteed forward progress VA`

## pseudocode

```c

```
