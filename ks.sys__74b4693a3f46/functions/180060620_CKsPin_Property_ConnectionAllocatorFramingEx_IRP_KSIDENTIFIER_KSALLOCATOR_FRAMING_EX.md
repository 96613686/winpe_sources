# CKsPin::Property_ConnectionAllocatorFramingEx(_IRP *,KSIDENTIFIER *,KSALLOCATOR_FRAMING_EX *)

- ea: `0x180060620`
- end: `0x1800607d3`
- name: `?Property_ConnectionAllocatorFramingEx@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSALLOCATOR_FRAMING_EX@@@Z`
- size: `435`
- prototype: `static int(struct _IRP *, struct KSIDENTIFIER *, struct KSALLOCATOR_FRAMING_EX *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000b7bc`
- `0x18000dddc`
- `0x180019cc0`
- `0x180060620`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1800606d6`
- `ntoskrnl!KeReleaseMutex` at `0x1800606d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x180060685`
- `ntoskrnl!KeWaitForSingleObject` at `0x180060685`

## pseudocode

```c

```
