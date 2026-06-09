# VIDMM_GLOBAL::TransferPagesToDedicatedPartition(unsigned __int64)

- ea: `0x140047768`
- end: `0x140047908`
- name: `?TransferPagesToDedicatedPartition@VIDMM_GLOBAL@@QEAAJ_K@Z`
- size: `416`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400b514c`

## callees

- `0x1400045ec`
- `0x140047768`
- `0x140058680`

## import_xrefs

- `ntoskrnl!ZwManagePartition` at `0x1400477e5`
- `ntoskrnl!ZwManagePartition` at `0x140047889`
- `ntoskrnl!ZwManagePartition` at `0x1400477e5`
- `ntoskrnl!ZwManagePartition` at `0x140047889`
- `watchdog!WdLogSingleEntry1` at `0x140047800`
- `watchdog!WdLogSingleEntry1` at `0x1400478a4`
- `watchdog!WdLogSingleEntry1` at `0x1400478ce`
- `watchdog!WdLogSingleEntry1` at `0x140047800`
- `watchdog!WdLogSingleEntry1` at `0x1400478a4`
- `watchdog!WdLogSingleEntry1` at `0x1400478ce`

## string_xrefs

- `0x14004780c`: `Failed to create 64KB pages for partition transfer, Status=0x%x`

## pseudocode

```c

```
