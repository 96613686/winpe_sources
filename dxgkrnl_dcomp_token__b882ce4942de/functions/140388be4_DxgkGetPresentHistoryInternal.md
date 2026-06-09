# DxgkGetPresentHistoryInternal

- ea: `0x140388be4`
- end: `0x140389d87`
- name: `DxgkGetPresentHistoryInternal`
- size: `4515`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `3`
- callee_count: `34`
- tags: `broker_com_uri`

## callers

- `0x1400099e0`
- `0x1402530e0`
- `0x1403889a0`

## callees

- `0x14000e568`
- `0x140012380`
- `0x140012b14`
- `0x140013860`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400155fc`
- `0x1400159a0`
- `0x140015a00`
- `0x1400161c8`
- `0x140016300`
- `0x14001a2ec`
- `0x14001ab20`
- `0x14001b890`
- `0x14001c910`
- `0x14001d070`
- `0x14001d0e4`
- `0x14001e084`
- `0x1400344ec`
- `0x1400346c0`
- `0x14003c1cc`
- `0x140042a60`
- `0x14004a714`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1401e5360`
- `0x140323280`
- `0x140323854`
- `0x140359cd0`
- `0x140388a64`
- `0x140388be4`
- `0x140389d90`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14038991d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14038991d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140388e21`
- `ntoskrnl!PsGetCurrentProcess` at `0x140388e21`
- `ntoskrnl!PsGetProcessSessionId` at `0x140388e30`
- `ntoskrnl!PsGetProcessSessionId` at `0x140388e30`
- `ntoskrnl!KeReleaseSemaphore` at `0x140389006`
- `ntoskrnl!KeReleaseSemaphore` at `0x140389006`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140388fd2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140388fd2`
- `watchdog!WdLogSingleEntry2` at `0x140389530`
- `watchdog!WdLogSingleEntry2` at `0x1403896dd`
- `watchdog!WdLogSingleEntry2` at `0x140389771`
- `watchdog!WdLogSingleEntry2` at `0x14038983c`
- `watchdog!WdLogSingleEntry2` at `0x140389a98`
- `watchdog!WdLogSingleEntry2` at `0x140389c56`
- `watchdog!WdLogSingleEntry2` at `0x140389530`
- `watchdog!WdLogSingleEntry2` at `0x1403896dd`
- `watchdog!WdLogSingleEntry2` at `0x140389771`
- `watchdog!WdLogSingleEntry2` at `0x14038983c`
- `watchdog!WdLogSingleEntry2` at `0x140389a98`
- `watchdog!WdLogSingleEntry2` at `0x140389c56`
- `watchdog!WdLogSingleEntry0` at `0x14038926c`
- `watchdog!WdLogSingleEntry0` at `0x1403898ae`
- `watchdog!WdLogSingleEntry0` at `0x14038997e`
- `watchdog!WdLogSingleEntry0` at `0x1403899cc`
- `watchdog!WdLogSingleEntry0` at `0x140389b3f`
- `watchdog!WdLogSingleEntry0` at `0x140389b8f`
- `watchdog!WdLogSingleEntry0` at `0x14038926c`
- `watchdog!WdLogSingleEntry0` at `0x1403898ae`
- `watchdog!WdLogSingleEntry0` at `0x14038997e`
- `watchdog!WdLogSingleEntry0` at `0x1403899cc`
- `watchdog!WdLogSingleEntry0` at `0x140389b3f`
- `watchdog!WdLogSingleEntry0` at `0x140389b8f`
- `watchdog!WdLogSingleEntry5` at `0x1403891c6`
- `watchdog!WdLogSingleEntry5` at `0x1403891c6`
- `watchdog!WdLogSingleEntry1` at `0x1403895c1`
- `watchdog!WdLogSingleEntry1` at `0x140389667`
- `watchdog!WdLogSingleEntry1` at `0x1403897dc`
- `watchdog!WdLogSingleEntry1` at `0x14038992d`
- `watchdog!WdLogSingleEntry1` at `0x1403895c1`
- `watchdog!WdLogSingleEntry1` at `0x140389667`
- `watchdog!WdLogSingleEntry1` at `0x1403897dc`
- `watchdog!WdLogSingleEntry1` at `0x14038992d`

## string_xrefs

- `0x140389b71`: `pToken->Token.Flip.Flags.IndependentFlip`
- `0x1403899fe`: `TokenSize > 0`
- `0x140389bbf`: `pToken->Token.Flip.Flags.IndependentFlipStage == D3DKMT_FLIPMODEL_INDEPENDENT_FLIP_STAGE_FLIP_SUBMITTED || pToken->Token.Flip.Flags.IndependentFlipStage == D3DKMT_FLIPMODEL_INDEPENDENT_FLIP_STAGE_FLIP_COMPLETE`

## pseudocode

```c

```
