# NdisFOidRequestComplete

- ea: `0x14000e760`
- end: `0x14000eb34`
- name: `NdisFOidRequestComplete`
- size: `980`
- prototype: `void __stdcall(NDIS_HANDLE NdisFilterHandle, PNDIS_OID_REQUEST OidRequest, NDIS_STATUS Status)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000e570`
- `0x14000e760`
- `0x1400100f0`
- `0x14001c1e0`
- `0x14001c6b0`
- `0x140023900`
- `0x14002ab60`
- `0x1400509b0`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000e80f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000e80f`
- `ntoskrnl!KeSetEvent` at `0x14000e7b2`
- `ntoskrnl!KeSetEvent` at `0x14000e7b2`
- `ntoskrnl!KeCancelTimer` at `0x14000e792`
- `ntoskrnl!KeCancelTimer` at `0x14000e792`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e916`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e8cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eb23`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e8cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000eb23`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e8ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e9b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e8ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e9b7`

## pseudocode

```c

```
