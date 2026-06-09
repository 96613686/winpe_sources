# IsIdle

- ea: `0x1400e8a3c`
- end: `0x1400e8ac8`
- name: `IsIdle`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400e87d8`

## callees

- `0x1400e8a3c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e8a50`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e8a50`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e8a61`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e8a61`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e8a90`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e8a90`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e8a9c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e8a9c`

## pseudocode

```c

```
