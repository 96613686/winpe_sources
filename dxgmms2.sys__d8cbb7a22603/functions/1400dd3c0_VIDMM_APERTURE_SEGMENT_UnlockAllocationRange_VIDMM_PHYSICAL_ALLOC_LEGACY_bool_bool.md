# VIDMM_APERTURE_SEGMENT::UnlockAllocationRange(VIDMM_PHYSICAL_ALLOC_LEGACY *,bool,bool)

- ea: `0x1400dd3c0`
- end: `0x1400dd61b`
- name: `?UnlockAllocationRange@VIDMM_APERTURE_SEGMENT@@UEAAXPEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_N1@Z`
- size: `603`
- prototype: `void __fastcall(VIDMM_APERTURE_SEGMENT *__hidden this, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool, bool)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x140004268`
- `0x140058f50`
- `0x140059080`
- `0x140059380`
- `0x1400dd3c0`
- `0x14010d210`
- `0x140110ae0`
- `0x14011ac38`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400dd48b`
- `ntoskrnl!KeStackAttachProcess` at `0x1400dd48b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400dd5ac`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400dd5ac`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dd426`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dd426`
- `watchdog!WdLogSingleEntry0` at `0x1400dd517`
- `watchdog!WdLogSingleEntry0` at `0x1400dd517`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400dd41a`

## string_xrefs

- `0x1400dd551`: `Encountered a fault trying to copy to the user VA from the guaranteed forward progress VA.\n`

## pseudocode

```c

```
