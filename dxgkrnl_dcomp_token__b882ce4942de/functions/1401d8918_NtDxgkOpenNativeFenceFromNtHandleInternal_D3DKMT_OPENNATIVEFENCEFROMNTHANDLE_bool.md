# NtDxgkOpenNativeFenceFromNtHandleInternal(_D3DKMT_OPENNATIVEFENCEFROMNTHANDLE *,bool)

- ea: `0x1401d8918`
- end: `0x1401d9180`
- name: `?NtDxgkOpenNativeFenceFromNtHandleInternal@@YAJPEAU_D3DKMT_OPENNATIVEFENCEFROMNTHANDLE@@_N@Z`
- size: `2152`
- prototype: `__int64 __fastcall(struct _D3DKMT_OPENNATIVEFENCEFROMNTHANDLE *, bool)`
- caller_count: `1`
- callee_count: `23`
- tags: ``

## callers

- `0x140248bd0`

## callees

- `0x140012380`
- `0x140015970`
- `0x140015d70`
- `0x14001667c`
- `0x140017fb8`
- `0x14001b890`
- `0x14001bd70`
- `0x14001cec0`
- `0x14001f120`
- `0x140030820`
- `0x140030860`
- `0x140033bd4`
- `0x140043e58`
- `0x14004885c`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a0540`
- `0x1401d8918`
- `0x1401d9188`
- `0x1401e5360`
- `0x140323854`
- `0x14032df70`
- `0x1403b351c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401d9063`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401d9063`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401d9057`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401d9057`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d8cc0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d8cc0`
- `ntoskrnl!RtlIsZeroMemory` at `0x1401d8a2e`
- `ntoskrnl!RtlIsZeroMemory` at `0x1401d8a2e`
- `watchdog!WdLogSingleEntry2` at `0x1401d8aea`
- `watchdog!WdLogSingleEntry2` at `0x1401d8b8a`
- `watchdog!WdLogSingleEntry2` at `0x1401d8ce8`
- `watchdog!WdLogSingleEntry2` at `0x1401d8d14`
- `watchdog!WdLogSingleEntry2` at `0x1401d90d7`
- `watchdog!WdLogSingleEntry2` at `0x1401d8aea`
- `watchdog!WdLogSingleEntry2` at `0x1401d8b8a`
- `watchdog!WdLogSingleEntry2` at `0x1401d8ce8`
- `watchdog!WdLogSingleEntry2` at `0x1401d8d14`
- `watchdog!WdLogSingleEntry2` at `0x1401d90d7`
- `watchdog!WdLogSingleEntry3` at `0x1401d8d66`
- `watchdog!WdLogSingleEntry3` at `0x1401d8d66`
- `watchdog!WdLogSingleEntry0` at `0x1401d89ff`
- `watchdog!WdLogSingleEntry0` at `0x1401d8a8a`
- `watchdog!WdLogSingleEntry0` at `0x1401d8ffa`
- `watchdog!WdLogSingleEntry0` at `0x1401d89ff`
- `watchdog!WdLogSingleEntry0` at `0x1401d8a8a`
- `watchdog!WdLogSingleEntry0` at `0x1401d8ffa`
- `watchdog!WdLogSingleEntry1` at `0x1401d896c`
- `watchdog!WdLogSingleEntry1` at `0x1401d8a4d`
- `watchdog!WdLogSingleEntry1` at `0x1401d8bfe`
- `watchdog!WdLogSingleEntry1` at `0x1401d9137`
- `watchdog!WdLogSingleEntry1` at `0x1401d896c`
- `watchdog!WdLogSingleEntry1` at `0x1401d8a4d`
- `watchdog!WdLogSingleEntry1` at `0x1401d8bfe`
- `watchdog!WdLogSingleEntry1` at `0x1401d9137`

## string_xrefs

- `0x1401d8c35`: `Cannot open native fence on an DXGADAPTER (0x%I64x) that does not support native GPU fences`

## pseudocode

```c

```
