# CKsPin::Support_Connection(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x180060bd0`
- end: `0x180060ca3`
- name: `?Support_Connection@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `211`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18000b7bc`
- `0x180060bd0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180060c47`
- `ntoskrnl!KeReleaseMutex` at `0x180060c47`
- `ntoskrnl!KeWaitForSingleObject` at `0x180060c1b`
- `ntoskrnl!KeWaitForSingleObject` at `0x180060c1b`

## pseudocode

```c

```
