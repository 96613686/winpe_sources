# CKsFilter::Property_General_ComponentId(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x18003cc90`
- end: `0x18003cd74`
- name: `?Property_General_ComponentId@CKsFilter@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `228`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, _OWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b7bc`
- `0x18003cc90`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18003cd5c`
- `ntoskrnl!KeReleaseMutex` at `0x18003cd5c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003cd0a`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003cd0a`

## pseudocode

```c

```
