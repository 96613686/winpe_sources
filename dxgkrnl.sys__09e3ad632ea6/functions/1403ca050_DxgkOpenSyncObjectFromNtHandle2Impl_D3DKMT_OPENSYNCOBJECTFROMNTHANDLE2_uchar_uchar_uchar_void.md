# DxgkOpenSyncObjectFromNtHandle2Impl(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *,uchar,uchar,uchar,void *)

- ea: `0x1403ca050`
- end: `0x1403cab79`
- name: `?DxgkOpenSyncObjectFromNtHandle2Impl@@YAJPEAU_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2@@EEEPEAX@Z`
- size: `2857`
- prototype: `__int64 __fastcall(struct _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *, unsigned __int8, unsigned __int8, unsigned __int8, void *)`
- caller_count: `4`
- callee_count: `26`
- tags: ``

## callers

- `0x14026c76c`
- `0x1403ca010`
- `0x1403ca030`
- `0x1403ede38`

## callees

- `0x140012540`
- `0x140012cd4`
- `0x140013a20`
- `0x140015b30`
- `0x140015f30`
- `0x140018054`
- `0x14001b9c0`
- `0x14001bea0`
- `0x14001cff0`
- `0x14001d214`
- `0x14001f2f0`
- `0x140021cb0`
- `0x1400309f0`
- `0x140030a30`
- `0x140033da4`
- `0x1400440b8`
- `0x140048a5c`
- `0x14004bd6c`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x1401e76e0`
- `0x14032a5c4`
- `0x140334ce0`
- `0x1403b162c`
- `0x1403ca050`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ca4b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ca564`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ca9f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ca4b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ca564`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ca9f6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403ca9ea`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403ca9ea`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403ca4a8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403ca558`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403ca4a8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403ca558`
- `ntoskrnl!ObfDereferenceObject` at `0x1403caafc`
- `ntoskrnl!ObfDereferenceObject` at `0x1403caafc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403ca5b6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403ca5b6`
- `watchdog!WdLogSingleEntry2` at `0x1403ca306`
- `watchdog!WdLogSingleEntry2` at `0x1403ca5e5`
- `watchdog!WdLogSingleEntry2` at `0x1403ca676`
- `watchdog!WdLogSingleEntry2` at `0x1403caa55`
- `watchdog!WdLogSingleEntry2` at `0x1403ca306`
- `watchdog!WdLogSingleEntry2` at `0x1403ca5e5`
- `watchdog!WdLogSingleEntry2` at `0x1403ca676`
- `watchdog!WdLogSingleEntry2` at `0x1403caa55`
- `watchdog!WdLogSingleEntry3` at `0x1403ca787`
- `watchdog!WdLogSingleEntry3` at `0x1403ca787`
- `watchdog!WdLogSingleEntry0` at `0x1403ca274`
- `watchdog!WdLogSingleEntry0` at `0x1403ca2a8`
- `watchdog!WdLogSingleEntry0` at `0x1403ca42e`
- `watchdog!WdLogSingleEntry0` at `0x1403ca97e`
- `watchdog!WdLogSingleEntry0` at `0x1403ca274`
- `watchdog!WdLogSingleEntry0` at `0x1403ca2a8`
- `watchdog!WdLogSingleEntry0` at `0x1403ca42e`
- `watchdog!WdLogSingleEntry0` at `0x1403ca97e`
- `watchdog!WdLogSingleEntry1` at `0x1403ca128`
- `watchdog!WdLogSingleEntry1` at `0x1403ca1b2`
- `watchdog!WdLogSingleEntry1` at `0x1403ca47a`
- `watchdog!WdLogSingleEntry1` at `0x1403ca128`
- `watchdog!WdLogSingleEntry1` at `0x1403ca1b2`
- `watchdog!WdLogSingleEntry1` at `0x1403ca47a`

## string_xrefs

- `0x1403ca7be`: `Peer-to-Peer Native Fence 0x%I64x referenced by NT Handle 0x%I64x cannot be opened as a Monitored Fence. Returning 0x%I64x`

## pseudocode

```c

```
