# Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::TryAcquire(NDIS_MINIPORT_POLICY_OWNER)

- ea: `0x140166200`
- end: `0x14016629e`
- name: `?TryAcquire@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAA_NW4NDIS_MINIPORT_POLICY_OWNER@@@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14015dd60`
- `0x1401661c0`

## callees

- `0x140166200`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140166264`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016628e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140166264`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14016628e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016620e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14016620e`
- `ntoskrnl!KeReadStateEvent` at `0x140166230`
- `ntoskrnl!KeReadStateEvent` at `0x140166230`
- `ntoskrnl!KeClearEvent` at `0x140166244`
- `ntoskrnl!KeClearEvent` at `0x140166244`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140166220`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140166220`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140166258`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140166282`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140166258`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140166282`

## pseudocode

```c

```
