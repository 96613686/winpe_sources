# UcpStreamSendHeadersCompletionCommon

- ea: `0x1401653d8`
- end: `0x14016554a`
- name: `UcpStreamSendHeadersCompletionCommon`
- size: `370`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401653c0`
- `0x140165550`

## callees

- `0x14000a350`
- `0x1400c45fc`
- `0x1400c7aa8`
- `0x140165148`
- `0x1401653d8`
- `0x1401c3f58`
- `0x1401d945c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14016541d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14016541d`
- `ntoskrnl!IofCompleteRequest` at `0x1401654a6`
- `ntoskrnl!IofCompleteRequest` at `0x1401654a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016548b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016548b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401654c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401654c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016547f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016547f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140165461`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140165461`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140165449`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140165449`

## pseudocode

```c

```
