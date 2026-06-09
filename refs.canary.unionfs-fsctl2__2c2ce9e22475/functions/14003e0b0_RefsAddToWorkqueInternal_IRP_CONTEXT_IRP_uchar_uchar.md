# RefsAddToWorkqueInternal(_IRP_CONTEXT *,_IRP *,uchar,uchar)

- ea: `0x14003e0b0`
- end: `0x14003e747`
- name: `?RefsAddToWorkqueInternal@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@EE@Z`
- size: `1687`
- prototype: `void(struct _IRP_CONTEXT *, struct _IRP *, unsigned __int8, unsigned __int8)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14003e090`
- `0x14003fbe0`
- `0x1400b9250`
- `0x1402e9840`

## callees

- `0x14003e0b0`
- `0x140041b40`
- `0x1400ca788`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14003e6f8`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003e6f8`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003e3d4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003e6e4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003e3d4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14003e6e4`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003e55b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003e575`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003e55b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003e575`
- `ntoskrnl!ExQueueWorkItem` at `0x14003e722`
- `ntoskrnl!ExQueueWorkItem` at `0x14003e722`
- `ntoskrnl!KeSetEvent` at `0x14003e368`
- `ntoskrnl!KeSetEvent` at `0x14003e623`
- `ntoskrnl!KeSetEvent` at `0x14003e368`
- `ntoskrnl!KeSetEvent` at `0x14003e623`
- `ntoskrnl!DbgPrintEx` at `0x14003e4f4`
- `ntoskrnl!DbgPrintEx` at `0x14003e4f4`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14003e521`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14003e521`
- `ntoskrnl!_strnicmp` at `0x14003e5a0`
- `ntoskrnl!_strnicmp` at `0x14003e5a0`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003e584`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14003e584`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14003e0fe`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14003e0fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003e2a1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003e2a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003e1bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003e2fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003e1bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003e2fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003e237`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003e3a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003e605`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003e66f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003e237`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003e3a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003e605`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003e66f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003e400`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003e400`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003e429`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003e460`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003e429`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003e460`
- `ntoskrnl!ExTryQueueWorkItem` at `0x14003e25e`
- `ntoskrnl!ExTryQueueWorkItem` at `0x14003e25e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003e2e2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003e6a5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003e2e2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003e6a5`

## pseudocode

```c

```
