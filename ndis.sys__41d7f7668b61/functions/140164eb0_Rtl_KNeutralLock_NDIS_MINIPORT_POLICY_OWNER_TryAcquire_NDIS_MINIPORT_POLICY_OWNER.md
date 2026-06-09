# Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::TryAcquire(NDIS_MINIPORT_POLICY_OWNER)

- ea: `0x140164eb0`
- end: `0x140164f4e`
- name: `?TryAcquire@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAA_NW4NDIS_MINIPORT_POLICY_OWNER@@@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140164d00`
- `0x140164e70`

## callees

- `0x140164eb0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164f14`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164f3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164f14`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140164f3e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140164ebe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140164ebe`
- `ntoskrnl!KeReadStateEvent` at `0x140164ee0`
- `ntoskrnl!KeReadStateEvent` at `0x140164ee0`
- `ntoskrnl!KeClearEvent` at `0x140164ef4`
- `ntoskrnl!KeClearEvent` at `0x140164ef4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140164ed0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140164ed0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164f08`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164f32`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164f08`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140164f32`

## pseudocode

```c

```
