# VIDMM_APERTURE_SEGMENT::UnlockAllocationRange(VIDMM_PHYSICAL_ALLOC_LEGACY *,bool,bool)

- ea: `0x1400d50d0`
- end: `0x1400d532b`
- name: `?UnlockAllocationRange@VIDMM_APERTURE_SEGMENT@@UEAAXPEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_N1@Z`
- size: `603`
- prototype: `void __fastcall(VIDMM_APERTURE_SEGMENT *__hidden this, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool, bool)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1400045ec`
- `0x140058680`
- `0x1400587c0`
- `0x140058ac0`
- `0x1400d50d0`
- `0x1400ed9e0`
- `0x140108ed0`
- `0x140117138`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400d519b`
- `ntoskrnl!KeStackAttachProcess` at `0x1400d519b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400d52bc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400d52bc`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d5136`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400d5136`
- `watchdog!WdLogSingleEntry0` at `0x1400d5227`
- `watchdog!WdLogSingleEntry0` at `0x1400d5227`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400d512a`

## string_xrefs

- `0x1400d5261`: `Encountered a fault trying to copy to the user VA from the guaranteed forward progress VA.\n`

## pseudocode

```c

```
