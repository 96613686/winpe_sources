# DxgkShareObjectsInternal

- ea: `0x14036c738`
- end: `0x14036d1eb`
- name: `DxgkShareObjectsInternal`
- size: `2739`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, __int64, ACCESS_MASK DesiredAccess, __int64, __int64)`
- caller_count: `5`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x14009d770`
- `0x14019e070`
- `0x1401a1dc0`
- `0x1401bb1a4`
- `0x14036c670`

## callees

- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001cd10`
- `0x14001d214`
- `0x14001d94c`
- `0x140030a30`
- `0x140033da4`
- `0x140044ef0`
- `0x140047990`
- `0x140048a5c`
- `0x14004fe88`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1401e76e0`
- `0x140249494`
- `0x140328e00`
- `0x14032a5c4`
- `0x14036c738`
- `0x14036d1f4`
- `0x14036d278`
- `0x14036d848`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14036cff4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14036cff4`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14036d05b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14036d05b`
- `ntoskrnl!KeStackAttachProcess` at `0x14036d010`
- `ntoskrnl!KeStackAttachProcess` at `0x14036d010`
- `ntoskrnl!ObCloseHandle` at `0x14036d186`
- `ntoskrnl!ObCloseHandle` at `0x14036d186`
- `ntoskrnl!ObInsertObject` at `0x14036d040`
- `ntoskrnl!ObInsertObject` at `0x14036d040`
- `watchdog!WdLogSingleEntry2` at `0x14036ca88`
- `watchdog!WdLogSingleEntry2` at `0x14036cb16`
- `watchdog!WdLogSingleEntry2` at `0x14036cbfd`
- `watchdog!WdLogSingleEntry2` at `0x14036cd00`
- `watchdog!WdLogSingleEntry2` at `0x14036cd45`
- `watchdog!WdLogSingleEntry2` at `0x14036ce4d`
- `watchdog!WdLogSingleEntry2` at `0x14036ce94`
- `watchdog!WdLogSingleEntry2` at `0x14036ca88`
- `watchdog!WdLogSingleEntry2` at `0x14036cb16`
- `watchdog!WdLogSingleEntry2` at `0x14036cbfd`
- `watchdog!WdLogSingleEntry2` at `0x14036cd00`
- `watchdog!WdLogSingleEntry2` at `0x14036cd45`
- `watchdog!WdLogSingleEntry2` at `0x14036ce4d`
- `watchdog!WdLogSingleEntry2` at `0x14036ce94`
- `watchdog!WdLogSingleEntry3` at `0x14036ca56`
- `watchdog!WdLogSingleEntry3` at `0x14036d07b`
- `watchdog!WdLogSingleEntry3` at `0x14036d0d2`
- `watchdog!WdLogSingleEntry3` at `0x14036ca56`
- `watchdog!WdLogSingleEntry3` at `0x14036d07b`
- `watchdog!WdLogSingleEntry3` at `0x14036d0d2`
- `watchdog!WdLogSingleEntry0` at `0x14036cae9`
- `watchdog!WdLogSingleEntry0` at `0x14036cb7c`
- `watchdog!WdLogSingleEntry0` at `0x14036cca7`
- `watchdog!WdLogSingleEntry0` at `0x14036cdf4`
- `watchdog!WdLogSingleEntry0` at `0x14036cf3a`
- `watchdog!WdLogSingleEntry0` at `0x14036cae9`
- `watchdog!WdLogSingleEntry0` at `0x14036cb7c`
- `watchdog!WdLogSingleEntry0` at `0x14036cca7`
- `watchdog!WdLogSingleEntry0` at `0x14036cdf4`
- `watchdog!WdLogSingleEntry0` at `0x14036cf3a`
- `watchdog!WdLogSingleEntry1` at `0x14036c864`
- `watchdog!WdLogSingleEntry1` at `0x14036c8fc`
- `watchdog!WdLogSingleEntry1` at `0x14036c94c`
- `watchdog!WdLogSingleEntry1` at `0x14036c988`
- `watchdog!WdLogSingleEntry1` at `0x14036d12a`
- `watchdog!WdLogSingleEntry1` at `0x14036c864`
- `watchdog!WdLogSingleEntry1` at `0x14036c8fc`
- `watchdog!WdLogSingleEntry1` at `0x14036c94c`
- `watchdog!WdLogSingleEntry1` at `0x14036c988`
- `watchdog!WdLogSingleEntry1` at `0x14036d12a`

## string_xrefs

- `0x14036cec3`: `Cannot share object: Shared sync object 0x%I64x does not use NT security sharing. Returning 0x%I64x.`
- `0x14036cd74`: `Cannot share object: Keyed mutex 0x%I64x does not use NT security sharing. Returning 0x%I64x.`

## pseudocode

```c

```
