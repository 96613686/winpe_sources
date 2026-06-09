# UxTlAllocateConnectionForLookaside

- ea: `0x1c0016390`
- end: `0x1c001647a`
- name: `UxTlAllocateConnectionForLookaside`
- size: `234`
- prototype: `ALLOCATE_FUNCTION_EX`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1c0016390`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00163b3`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00163b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0027bfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0027bfc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0016449`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0027beb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0016449`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0027beb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00163e7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00163e7`

## pseudocode

```c

```
