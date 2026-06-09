# VidMmRotateLegacyAllocation(VIDMM_GLOBAL *,VIDMM_PHYSICAL_ALLOC *,_MM_ROTATE_DIRECTION,long (*)(_MDL *,_MDL *,void *),VIDMM_ROTATE_COPY_CONTEXT *,VIDMM_ROTATE_FLAGS)

- ea: `0x140122d88`
- end: `0x14012300a`
- name: `?VidMmRotateLegacyAllocation@@YAJPEAVVIDMM_GLOBAL@@PEAUVIDMM_PHYSICAL_ALLOC@@W4_MM_ROTATE_DIRECTION@@P6AJPEAU_MDL@@3PEAX@ZPEAUVIDMM_ROTATE_COPY_CONTEXT@@TVIDMM_ROTATE_FLAGS@@@Z`
- size: `642`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x1400982d0`
- `0x1400a0d94`
- `0x1400a5258`
- `0x1400cfc6c`
- `0x1400d4d5c`
- `0x1400d6b24`
- `0x14011a8c0`
- `0x140125884`

## callees

- `0x140004268`
- `0x140059030`
- `0x1400c115c`
- `0x1401043b8`
- `0x14012062c`
- `0x140122d88`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140122f7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140122fc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140122fe9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140122f7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140122fc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140122fe9`
- `watchdog!WdLogSingleEntry5` at `0x140122f57`
- `watchdog!WdLogSingleEntry5` at `0x140122f57`
- `watchdog!WdLogSingleEntry1` at `0x140122e4b`
- `watchdog!WdLogSingleEntry1` at `0x140122e4b`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140122f32`
- `dxgkrnl!g_IsInternalRelease` at `0x140122f25`

## string_xrefs

- `0x140122e5c`: `Failed to create rotate MDL for physical allocation 0x%.16x`

## pseudocode

```c

```
