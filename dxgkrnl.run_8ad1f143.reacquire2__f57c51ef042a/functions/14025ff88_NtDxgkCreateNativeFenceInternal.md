# NtDxgkCreateNativeFenceInternal

- ea: `0x14025ff88`
- end: `0x140260c4e`
- name: `NtDxgkCreateNativeFenceInternal`
- size: `3270`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `30`
- tags: ``

## callers

- `0x14025ff60`
- `0x140283b50`

## callees

- `0x140012380`
- `0x140015910`
- `0x140015970`
- `0x140015d70`
- `0x140017fb8`
- `0x14001b890`
- `0x14001bd70`
- `0x14001cec0`
- `0x14001f120`
- `0x140021ae0`
- `0x14002fdc0`
- `0x140030820`
- `0x140030860`
- `0x140030960`
- `0x140033bd4`
- `0x140034740`
- `0x140043e58`
- `0x14004885c`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a0540`
- `0x140196f20`
- `0x1401e5360`
- `0x1401e54cc`
- `0x14025ff88`
- `0x140281820`
- `0x14028cf68`
- `0x140323854`
- `0x1403af310`
- `0x1403b351c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140260b55`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140260b55`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140260b49`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140260b49`
- `ntoskrnl!RtlIsZeroMemory` at `0x14026028a`
- `ntoskrnl!RtlIsZeroMemory` at `0x1402602ab`
- `ntoskrnl!RtlIsZeroMemory` at `0x1402602cc`
- `ntoskrnl!RtlIsZeroMemory` at `0x14026028a`
- `ntoskrnl!RtlIsZeroMemory` at `0x1402602ab`
- `ntoskrnl!RtlIsZeroMemory` at `0x1402602cc`
- `watchdog!WdLogSingleEntry2` at `0x140260329`
- `watchdog!WdLogSingleEntry2` at `0x1402604aa`
- `watchdog!WdLogSingleEntry2` at `0x14026093a`
- `watchdog!WdLogSingleEntry2` at `0x140260329`
- `watchdog!WdLogSingleEntry2` at `0x1402604aa`
- `watchdog!WdLogSingleEntry2` at `0x14026093a`
- `watchdog!WdLogSingleEntry0` at `0x140260211`
- `watchdog!WdLogSingleEntry0` at `0x140260240`
- `watchdog!WdLogSingleEntry0` at `0x140260265`
- `watchdog!WdLogSingleEntry0` at `0x140260397`
- `watchdog!WdLogSingleEntry0` at `0x140260532`
- `watchdog!WdLogSingleEntry0` at `0x140260586`
- `watchdog!WdLogSingleEntry0` at `0x140260aec`
- `watchdog!WdLogSingleEntry0` at `0x140260211`
- `watchdog!WdLogSingleEntry0` at `0x140260240`
- `watchdog!WdLogSingleEntry0` at `0x140260265`
- `watchdog!WdLogSingleEntry0` at `0x140260397`
- `watchdog!WdLogSingleEntry0` at `0x140260532`
- `watchdog!WdLogSingleEntry0` at `0x140260586`
- `watchdog!WdLogSingleEntry0` at `0x140260aec`
- `watchdog!WdLogSingleEntry1` at `0x14025ffea`
- `watchdog!WdLogSingleEntry1` at `0x140260078`
- `watchdog!WdLogSingleEntry1` at `0x1402601bf`
- `watchdog!WdLogSingleEntry1` at `0x1402603f2`
- `watchdog!WdLogSingleEntry1` at `0x140260689`
- `watchdog!WdLogSingleEntry1` at `0x140260757`
- `watchdog!WdLogSingleEntry1` at `0x140260844`
- `watchdog!WdLogSingleEntry1` at `0x140260be1`
- `watchdog!WdLogSingleEntry1` at `0x140260c08`
- `watchdog!WdLogSingleEntry1` at `0x14025ffea`
- `watchdog!WdLogSingleEntry1` at `0x140260078`
- `watchdog!WdLogSingleEntry1` at `0x1402601bf`
- `watchdog!WdLogSingleEntry1` at `0x1402603f2`
- `watchdog!WdLogSingleEntry1` at `0x140260689`
- `watchdog!WdLogSingleEntry1` at `0x140260757`
- `watchdog!WdLogSingleEntry1` at `0x140260844`
- `watchdog!WdLogSingleEntry1` at `0x140260be1`
- `watchdog!WdLogSingleEntry1` at `0x140260c08`

## string_xrefs

- `0x140260786`: `VmBusSendCreateSyncObject failed, returning 0x%I64x`
- `0x1402604d9`: `Failed to acquire COREDEVICEACCESS for DXGDEVICE:0x%I64x, returning 0x%I64x`

## pseudocode

```c

```
