# IsIdle

- ea: `0x1400e05dc`
- end: `0x1400e0668`
- name: `IsIdle`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400e0378`

## callees

- `0x1400e05dc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e05f0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e05f0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e0601`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e0601`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e0630`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e0630`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e063c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e063c`

## pseudocode

```c

```
