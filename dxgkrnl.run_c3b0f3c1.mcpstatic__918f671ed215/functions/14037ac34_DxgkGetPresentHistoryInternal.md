# DxgkGetPresentHistoryInternal

- ea: `0x14037ac34`
- end: `0x14037bdd7`
- name: `DxgkGetPresentHistoryInternal`
- size: `4515`
- prototype: `__int64 __fastcall(char *Src, int, __int64)`
- caller_count: `3`
- callee_count: `34`
- tags: `broker_com_uri`

## callers

- `0x140009ba0`
- `0x140256810`
- `0x14037a9f0`

## callees

- `0x14000e728`
- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x1400146ac`
- `0x140015290`
- `0x1400157bc`
- `0x140015b60`
- `0x140015bc0`
- `0x140016388`
- `0x1400164c0`
- `0x14001a38c`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001ca40`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001e254`
- `0x1400346bc`
- `0x140034890`
- `0x14003c42c`
- `0x140042cc0`
- `0x14004a914`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1401e76e0`
- `0x140329ff0`
- `0x14032a5c4`
- `0x14035a180`
- `0x14037aab4`
- `0x14037ac34`
- `0x14037bde0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14037b96d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14037b96d`
- `ntoskrnl!PsGetCurrentProcess` at `0x14037ae71`
- `ntoskrnl!PsGetCurrentProcess` at `0x14037ae71`
- `ntoskrnl!PsGetProcessSessionId` at `0x14037ae80`
- `ntoskrnl!PsGetProcessSessionId` at `0x14037ae80`
- `ntoskrnl!KeReleaseSemaphore` at `0x14037b056`
- `ntoskrnl!KeReleaseSemaphore` at `0x14037b056`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14037b022`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14037b022`
- `watchdog!WdLogSingleEntry2` at `0x14037b580`
- `watchdog!WdLogSingleEntry2` at `0x14037b72d`
- `watchdog!WdLogSingleEntry2` at `0x14037b7c1`
- `watchdog!WdLogSingleEntry2` at `0x14037b88c`
- `watchdog!WdLogSingleEntry2` at `0x14037bae8`
- `watchdog!WdLogSingleEntry2` at `0x14037bca6`
- `watchdog!WdLogSingleEntry2` at `0x14037b580`
- `watchdog!WdLogSingleEntry2` at `0x14037b72d`
- `watchdog!WdLogSingleEntry2` at `0x14037b7c1`
- `watchdog!WdLogSingleEntry2` at `0x14037b88c`
- `watchdog!WdLogSingleEntry2` at `0x14037bae8`
- `watchdog!WdLogSingleEntry2` at `0x14037bca6`
- `watchdog!WdLogSingleEntry0` at `0x14037b2bc`
- `watchdog!WdLogSingleEntry0` at `0x14037b8fe`
- `watchdog!WdLogSingleEntry0` at `0x14037b9ce`
- `watchdog!WdLogSingleEntry0` at `0x14037ba1c`
- `watchdog!WdLogSingleEntry0` at `0x14037bb8f`
- `watchdog!WdLogSingleEntry0` at `0x14037bbdf`
- `watchdog!WdLogSingleEntry0` at `0x14037b2bc`
- `watchdog!WdLogSingleEntry0` at `0x14037b8fe`
- `watchdog!WdLogSingleEntry0` at `0x14037b9ce`
- `watchdog!WdLogSingleEntry0` at `0x14037ba1c`
- `watchdog!WdLogSingleEntry0` at `0x14037bb8f`
- `watchdog!WdLogSingleEntry0` at `0x14037bbdf`
- `watchdog!WdLogSingleEntry5` at `0x14037b216`
- `watchdog!WdLogSingleEntry5` at `0x14037b216`
- `watchdog!WdLogSingleEntry1` at `0x14037b611`
- `watchdog!WdLogSingleEntry1` at `0x14037b6b7`
- `watchdog!WdLogSingleEntry1` at `0x14037b82c`
- `watchdog!WdLogSingleEntry1` at `0x14037b97d`
- `watchdog!WdLogSingleEntry1` at `0x14037b611`
- `watchdog!WdLogSingleEntry1` at `0x14037b6b7`
- `watchdog!WdLogSingleEntry1` at `0x14037b82c`
- `watchdog!WdLogSingleEntry1` at `0x14037b97d`

## string_xrefs

- `0x14037ba4e`: `TokenSize > 0`
- `0x14037bc0f`: `pToken->Token.Flip.Flags.IndependentFlipStage == D3DKMT_FLIPMODEL_INDEPENDENT_FLIP_STAGE_FLIP_SUBMITTED || pToken->Token.Flip.Flags.IndependentFlipStage == D3DKMT_FLIPMODEL_INDEPENDENT_FLIP_STAGE_FLIP_COMPLETE`
- `0x14037bbc1`: `pToken->Token.Flip.Flags.IndependentFlip`

## pseudocode

```c

```
