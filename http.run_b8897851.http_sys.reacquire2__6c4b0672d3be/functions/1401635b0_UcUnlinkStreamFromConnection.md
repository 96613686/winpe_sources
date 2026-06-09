# UcUnlinkStreamFromConnection

- ea: `0x1401635b0`
- end: `0x1401636f0`
- name: `UcUnlinkStreamFromConnection`
- size: `320`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400c4a40`

## callees

- `0x1401635b0`
- `0x140163858`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1401636ad`
- `ntoskrnl!IofCompleteRequest` at `0x1401636ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140163688`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140163688`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016367c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14016367c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140163600`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140163600`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401635e8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401635e8`

## pseudocode

```c

```
