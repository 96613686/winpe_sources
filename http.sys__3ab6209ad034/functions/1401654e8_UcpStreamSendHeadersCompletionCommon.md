# UcpStreamSendHeadersCompletionCommon

- ea: `0x1401654e8`
- end: `0x14016565a`
- name: `UcpStreamSendHeadersCompletionCommon`
- size: `370`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401654d0`
- `0x140165660`

## callees

- `0x14000a350`
- `0x1400c451c`
- `0x1400c79c8`
- `0x140165258`
- `0x1401654e8`
- `0x1401c3f58`
- `0x1401d945c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14016552d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14016552d`
- `ntoskrnl!IofCompleteRequest` at `0x1401655b6`
- `ntoskrnl!IofCompleteRequest` at `0x1401655b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016559b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016559b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401655d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401655d6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016558f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016558f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140165571`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140165571`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140165559`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140165559`

## pseudocode

```c

```
