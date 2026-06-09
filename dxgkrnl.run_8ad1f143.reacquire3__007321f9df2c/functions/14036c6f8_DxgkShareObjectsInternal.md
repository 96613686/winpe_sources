# DxgkShareObjectsInternal

- ea: `0x14036c6f8`
- end: `0x14036d1ab`
- name: `DxgkShareObjectsInternal`
- size: `2739`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, __int64, ACCESS_MASK DesiredAccess, __int64, __int64)`
- caller_count: `5`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x14009cca0`
- `0x14019a070`
- `0x14019db00`
- `0x1401b85a4`
- `0x14036c630`

## callees

- `0x140012380`
- `0x140012b14`
- `0x140013860`
- `0x14001ab20`
- `0x14001b890`
- `0x14001cbe0`
- `0x14001d0e4`
- `0x14001d77c`
- `0x140030860`
- `0x140033bd4`
- `0x140044c90`
- `0x140047790`
- `0x14004885c`
- `0x14004fc88`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a0240`
- `0x1401e5360`
- `0x1402467a0`
- `0x140322090`
- `0x140323854`
- `0x14036c6f8`
- `0x14036d1b4`
- `0x14036d238`
- `0x14036d808`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14036cfb4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14036cfb4`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14036d01b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14036d01b`
- `ntoskrnl!KeStackAttachProcess` at `0x14036cfd0`
- `ntoskrnl!KeStackAttachProcess` at `0x14036cfd0`
- `ntoskrnl!ObCloseHandle` at `0x14036d146`
- `ntoskrnl!ObCloseHandle` at `0x14036d146`
- `ntoskrnl!ObInsertObject` at `0x14036d000`
- `ntoskrnl!ObInsertObject` at `0x14036d000`
- `watchdog!WdLogSingleEntry2` at `0x14036ca48`
- `watchdog!WdLogSingleEntry2` at `0x14036cad6`
- `watchdog!WdLogSingleEntry2` at `0x14036cbbd`
- `watchdog!WdLogSingleEntry2` at `0x14036ccc0`
- `watchdog!WdLogSingleEntry2` at `0x14036cd05`
- `watchdog!WdLogSingleEntry2` at `0x14036ce0d`
- `watchdog!WdLogSingleEntry2` at `0x14036ce54`
- `watchdog!WdLogSingleEntry2` at `0x14036ca48`
- `watchdog!WdLogSingleEntry2` at `0x14036cad6`
- `watchdog!WdLogSingleEntry2` at `0x14036cbbd`
- `watchdog!WdLogSingleEntry2` at `0x14036ccc0`
- `watchdog!WdLogSingleEntry2` at `0x14036cd05`
- `watchdog!WdLogSingleEntry2` at `0x14036ce0d`
- `watchdog!WdLogSingleEntry2` at `0x14036ce54`
- `watchdog!WdLogSingleEntry3` at `0x14036ca16`
- `watchdog!WdLogSingleEntry3` at `0x14036d03b`
- `watchdog!WdLogSingleEntry3` at `0x14036d092`
- `watchdog!WdLogSingleEntry3` at `0x14036ca16`
- `watchdog!WdLogSingleEntry3` at `0x14036d03b`
- `watchdog!WdLogSingleEntry3` at `0x14036d092`
- `watchdog!WdLogSingleEntry0` at `0x14036caa9`
- `watchdog!WdLogSingleEntry0` at `0x14036cb3c`
- `watchdog!WdLogSingleEntry0` at `0x14036cc67`
- `watchdog!WdLogSingleEntry0` at `0x14036cdb4`
- `watchdog!WdLogSingleEntry0` at `0x14036cefa`
- `watchdog!WdLogSingleEntry0` at `0x14036caa9`
- `watchdog!WdLogSingleEntry0` at `0x14036cb3c`
- `watchdog!WdLogSingleEntry0` at `0x14036cc67`
- `watchdog!WdLogSingleEntry0` at `0x14036cdb4`
- `watchdog!WdLogSingleEntry0` at `0x14036cefa`
- `watchdog!WdLogSingleEntry1` at `0x14036c824`
- `watchdog!WdLogSingleEntry1` at `0x14036c8bc`
- `watchdog!WdLogSingleEntry1` at `0x14036c90c`
- `watchdog!WdLogSingleEntry1` at `0x14036c948`
- `watchdog!WdLogSingleEntry1` at `0x14036d0ea`
- `watchdog!WdLogSingleEntry1` at `0x14036c824`
- `watchdog!WdLogSingleEntry1` at `0x14036c8bc`
- `watchdog!WdLogSingleEntry1` at `0x14036c90c`
- `watchdog!WdLogSingleEntry1` at `0x14036c948`
- `watchdog!WdLogSingleEntry1` at `0x14036d0ea`

## string_xrefs

- `0x14036ce83`: `Cannot share object: Shared sync object 0x%I64x does not use NT security sharing. Returning 0x%I64x.`
- `0x14036cd34`: `Cannot share object: Keyed mutex 0x%I64x does not use NT security sharing. Returning 0x%I64x.`

## pseudocode

```c

```
