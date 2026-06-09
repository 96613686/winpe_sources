# NtDxgkOpenNativeFenceFromNtHandleInternal(_D3DKMT_OPENNATIVEFENCEFROMNTHANDLE *,bool)

- ea: `0x140249b7c`
- end: `0x14024a44d`
- name: `?NtDxgkOpenNativeFenceFromNtHandleInternal@@YAJPEAU_D3DKMT_OPENNATIVEFENCEFROMNTHANDLE@@_N@Z`
- size: `2257`
- prototype: `__int64 __fastcall(struct _D3DKMT_OPENNATIVEFENCEFROMNTHANDLE *, bool)`
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x14024c1b0`

## callees

- `0x140012540`
- `0x140015b30`
- `0x140015f30`
- `0x14001683c`
- `0x140018054`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001cff0`
- `0x14001f2f0`
- `0x1400309f0`
- `0x140030a30`
- `0x140033da4`
- `0x1400440b8`
- `0x140048a5c`
- `0x1400674c4`
- `0x14006ac0c`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x1401e76e0`
- `0x14024915c`
- `0x140249b7c`
- `0x14032a5c4`
- `0x140334ce0`
- `0x1403b162c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024a330`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14024a330`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14024a324`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14024a324`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140249f24`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140249f24`
- `ntoskrnl!RtlIsZeroMemory` at `0x140249c92`
- `ntoskrnl!RtlIsZeroMemory` at `0x140249c92`
- `watchdog!WdLogSingleEntry2` at `0x140249d4e`
- `watchdog!WdLogSingleEntry2` at `0x140249dee`
- `watchdog!WdLogSingleEntry2` at `0x140249f4c`
- `watchdog!WdLogSingleEntry2` at `0x140249f78`
- `watchdog!WdLogSingleEntry2` at `0x14024a3a4`
- `watchdog!WdLogSingleEntry2` at `0x140249d4e`
- `watchdog!WdLogSingleEntry2` at `0x140249dee`
- `watchdog!WdLogSingleEntry2` at `0x140249f4c`
- `watchdog!WdLogSingleEntry2` at `0x140249f78`
- `watchdog!WdLogSingleEntry2` at `0x14024a3a4`
- `watchdog!WdLogSingleEntry3` at `0x140249fce`
- `watchdog!WdLogSingleEntry3` at `0x14024a04a`
- `watchdog!WdLogSingleEntry3` at `0x140249fce`
- `watchdog!WdLogSingleEntry3` at `0x14024a04a`
- `watchdog!WdLogSingleEntry0` at `0x140249c63`
- `watchdog!WdLogSingleEntry0` at `0x140249cee`
- `watchdog!WdLogSingleEntry0` at `0x14024a2c7`
- `watchdog!WdLogSingleEntry0` at `0x140249c63`
- `watchdog!WdLogSingleEntry0` at `0x140249cee`
- `watchdog!WdLogSingleEntry0` at `0x14024a2c7`
- `watchdog!WdLogSingleEntry1` at `0x140249bd0`
- `watchdog!WdLogSingleEntry1` at `0x140249cb1`
- `watchdog!WdLogSingleEntry1` at `0x140249e62`
- `watchdog!WdLogSingleEntry1` at `0x14024a404`
- `watchdog!WdLogSingleEntry1` at `0x140249bd0`
- `watchdog!WdLogSingleEntry1` at `0x140249cb1`
- `watchdog!WdLogSingleEntry1` at `0x140249e62`
- `watchdog!WdLogSingleEntry1` at `0x14024a404`

## string_xrefs

- `0x140249e99`: `Cannot open native fence on an DXGADAPTER (0x%I64x) that does not support native GPU fences`

## pseudocode

```c

```
