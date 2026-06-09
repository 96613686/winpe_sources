# CKsPin::Property_ConnectionAllocatorFramingEx(_IRP *,KSIDENTIFIER *,KSALLOCATOR_FRAMING_EX *)

- ea: `0x1800607c0`
- end: `0x180060973`
- name: `?Property_ConnectionAllocatorFramingEx@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSALLOCATOR_FRAMING_EX@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, struct KSALLOCATOR_FRAMING_EX *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000b7bc`
- `0x18000dddc`
- `0x180019d00`
- `0x1800607c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180060876`
- `ntoskrnl!KeReleaseMutex` at `0x180060876`
- `ntoskrnl!KeWaitForSingleObject` at `0x180060825`
- `ntoskrnl!KeWaitForSingleObject` at `0x180060825`

## pseudocode

```c

```
