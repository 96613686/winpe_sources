# FltpProcessIoCompletion

- ea: `0x180006590`
- end: `0x1800069d7`
- name: `FltpProcessIoCompletion`
- size: `1095`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180005b80`
- `0x180007500`
- `0x180016d10`
- `0x180060800`

## callees

- `0x180006590`
- `0x1800069e0`
- `0x180007230`
- `0x180009f20`
- `0x18001bc90`
- `0x18001ca30`
- `0x1800248e0`
- `0x180024c40`
- `0x180061e00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180006759`
- `ntoskrnl!ExFreePoolWithTag` at `0x180006801`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000699a`
- `ntoskrnl!ExFreePoolWithTag` at `0x180006759`
- `ntoskrnl!ExFreePoolWithTag` at `0x180006801`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000699a`
- `ntoskrnl!ExQueryDepthSList` at `0x18000673b`
- `ntoskrnl!ExQueryDepthSList` at `0x18000673b`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x18000678a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x18000678a`
- `ntoskrnl!ObfDereferenceObject` at `0x18000686b`
- `ntoskrnl!ObfDereferenceObject` at `0x18000686b`
- `ntoskrnl!IoGetStackLimits` at `0x1800065bd`
- `ntoskrnl!IoGetStackLimits` at `0x1800065bd`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800068b9`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800068b9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x180006838`
- `ntoskrnl!ExReleaseRundownProtection` at `0x180006838`
- `ntoskrnl!RtlWalkFrameChain` at `0x180006960`
- `ntoskrnl!RtlWalkFrameChain` at `0x180006960`

## pseudocode

```c

```
