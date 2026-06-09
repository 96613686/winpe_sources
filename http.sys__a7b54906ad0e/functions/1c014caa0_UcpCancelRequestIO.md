# UcpCancelRequestIO

- ea: `0x1c014caa0`
- end: `0x1c014cd08`
- name: `UcpCancelRequestIO`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1c0055488`

## callees

- `0x1c0015f24`
- `0x1c0055d64`
- `0x1c008f21c`
- `0x1c008f680`
- `0x1c014caa0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1c014cca3`
- `ntoskrnl!IofCompleteRequest` at `0x1c014cca3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c014ccbd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c014ccbd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c014cb02`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c014cb02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c014ccc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c014ccc9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c014caea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c014caea`

## pseudocode

```c

```
