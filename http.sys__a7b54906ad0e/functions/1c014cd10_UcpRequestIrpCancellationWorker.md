# UcpRequestIrpCancellationWorker

- ea: `0x1c014cd10`
- end: `0x1c014ce6a`
- name: `UcpRequestIrpCancellationWorker`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1c0055900`

## callees

- `0x1c0015f24`
- `0x1c00495d0`
- `0x1c0055d64`
- `0x1c008f570`
- `0x1c008f680`
- `0x1c014cd10`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1c014ce04`
- `ntoskrnl!IofCompleteRequest` at `0x1c014ce04`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c014cda8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c014cda8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c014cd6a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c014cd6a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c014cdb4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c014cdb4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c014cd51`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c014cd51`

## pseudocode

```c

```
