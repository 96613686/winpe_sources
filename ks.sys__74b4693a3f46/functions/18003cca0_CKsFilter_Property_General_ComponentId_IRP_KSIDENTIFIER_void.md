# CKsFilter::Property_General_ComponentId(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x18003cca0`
- end: `0x18003cd84`
- name: `?Property_General_ComponentId@CKsFilter@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `228`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18003cca0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18003cd6c`
- `ntoskrnl!KeReleaseMutex` at `0x18003cd6c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003cd1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003cd1a`

## pseudocode

```c

```
