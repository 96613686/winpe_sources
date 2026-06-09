# DxgkConnectCrossAdapterDoorbellInternal(_D3DKMT_CONNECTCROSSADAPTERDOORBELL *,bool)

- ea: `0x140263e1c`
- end: `0x1402647d7`
- name: `?DxgkConnectCrossAdapterDoorbellInternal@@YAJPEAU_D3DKMT_CONNECTCROSSADAPTERDOORBELL@@_N@Z`
- size: `2491`
- prototype: `__int64 __fastcall(struct _D3DKMT_CONNECTCROSSADAPTERDOORBELL *Src, bool)`
- caller_count: `1`
- callee_count: `28`
- tags: ``

## callers

- `0x140265480`

## callees

- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x140015f30`
- `0x140018ca8`
- `0x14001b9c0`
- `0x14001cff0`
- `0x14001d1a0`
- `0x140021cb0`
- `0x14002e1d0`
- `0x1400309f0`
- `0x140030a30`
- `0x140033da4`
- `0x140048a5c`
- `0x1400674c4`
- `0x140067754`
- `0x1400718f0`
- `0x14007bc4c`
- `0x14007bd18`
- `0x14007bdc4`
- `0x1400a0bd0`
- `0x1401e76e0`
- `0x14022eb64`
- `0x14022ed14`
- `0x1402300cc`
- `0x140230164`
- `0x140263e1c`
- `0x14032a5c4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402640df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402640df`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1402640d3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1402640d3`
- `watchdog!WdLogSingleEntry2` at `0x140263f56`
- `watchdog!WdLogSingleEntry2` at `0x140264103`
- `watchdog!WdLogSingleEntry2` at `0x140264270`
- `watchdog!WdLogSingleEntry2` at `0x140264382`
- `watchdog!WdLogSingleEntry2` at `0x14026444a`
- `watchdog!WdLogSingleEntry2` at `0x1402644c4`
- `watchdog!WdLogSingleEntry2` at `0x140264703`
- `watchdog!WdLogSingleEntry2` at `0x140263f56`
- `watchdog!WdLogSingleEntry2` at `0x140264103`
- `watchdog!WdLogSingleEntry2` at `0x140264270`
- `watchdog!WdLogSingleEntry2` at `0x140264382`
- `watchdog!WdLogSingleEntry2` at `0x14026444a`
- `watchdog!WdLogSingleEntry2` at `0x1402644c4`
- `watchdog!WdLogSingleEntry2` at `0x140264703`
- `watchdog!WdLogSingleEntry3` at `0x140264187`
- `watchdog!WdLogSingleEntry3` at `0x140264333`
- `watchdog!WdLogSingleEntry3` at `0x140264561`
- `watchdog!WdLogSingleEntry3` at `0x140264187`
- `watchdog!WdLogSingleEntry3` at `0x140264333`
- `watchdog!WdLogSingleEntry3` at `0x140264561`
- `watchdog!WdLogSingleEntry0` at `0x140264064`
- `watchdog!WdLogSingleEntry0` at `0x140264064`
- `watchdog!WdLogSingleEntry1` at `0x140263e70`
- `watchdog!WdLogSingleEntry1` at `0x140263f00`
- `watchdog!WdLogSingleEntry1` at `0x1402641e5`
- `watchdog!WdLogSingleEntry1` at `0x1402643f7`
- `watchdog!WdLogSingleEntry1` at `0x14026469c`
- `watchdog!WdLogSingleEntry1` at `0x14026474a`
- `watchdog!WdLogSingleEntry1` at `0x140263e70`
- `watchdog!WdLogSingleEntry1` at `0x140263f00`
- `watchdog!WdLogSingleEntry1` at `0x1402641e5`
- `watchdog!WdLogSingleEntry1` at `0x1402643f7`
- `watchdog!WdLogSingleEntry1` at `0x14026469c`
- `watchdog!WdLogSingleEntry1` at `0x14026474a`

## string_xrefs

- `0x14026478d`: `DxgkConnectCrossAdapterDoorbellInternal: Exception reading input, returning 0x%I64x`
- `0x1402643a7`: `DxgkConnectCrossAdapterDoorbellInternal: DXGSYNCOBJECT: 0x%I64x has not yet been opened on a cross-adapter, returning 0x%I64x`

## pseudocode

```c

```
