# CKsFilter::SplitCopyOnDismissal(_KSPSTREAM_POINTER *,_KSPFRAME_HEADER *,CKsFilter *)

- ea: `0x180014510`
- end: `0x180014651`
- name: `?SplitCopyOnDismissal@CKsFilter@@CAXPEAU_KSPSTREAM_POINTER@@PEAU_KSPFRAME_HEADER@@PEAV1@@Z`
- size: `321`
- prototype: `void __fastcall(struct _KSPSTREAM_POINTER *, struct _KSPFRAME_HEADER *, struct CKsFilter *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000513c`
- `0x18000b7bc`
- `0x180010340`
- `0x1800104ec`
- `0x18001423c`
- `0x180014510`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001459a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001459a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800145f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x180014637`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800145f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x180014637`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800145c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800145c7`

## pseudocode

```c

```
