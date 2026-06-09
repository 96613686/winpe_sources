# NdisFOidRequestComplete

- ea: `0x14001a6c0`
- end: `0x14001aa94`
- name: `NdisFOidRequestComplete`
- size: `980`
- prototype: `void __stdcall(NDIS_HANDLE NdisFilterHandle, PNDIS_OID_REQUEST OidRequest, NDIS_STATUS Status)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000a5a0`
- `0x14001a4d0`
- `0x14001a6c0`
- `0x14001c050`
- `0x140028080`
- `0x140028550`
- `0x140029620`
- `0x14004bfe0`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14001a76f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14001a76f`
- `ntoskrnl!KeSetEvent` at `0x14001a712`
- `ntoskrnl!KeSetEvent` at `0x14001a712`
- `ntoskrnl!KeCancelTimer` at `0x14001a6f2`
- `ntoskrnl!KeCancelTimer` at `0x14001a6f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a876`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a876`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a82f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001aa83`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a82f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001aa83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a80b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a917`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a80b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a917`

## pseudocode

```c

```
