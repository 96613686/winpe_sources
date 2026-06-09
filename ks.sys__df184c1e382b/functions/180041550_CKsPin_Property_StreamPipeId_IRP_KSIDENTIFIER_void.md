# CKsPin::Property_StreamPipeId(_IRP *,KSIDENTIFIER *,void * *)

- ea: `0x180041550`
- end: `0x18004167d`
- name: `?Property_StreamPipeId@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAPEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18000b7bc`
- `0x18000da50`
- `0x180041550`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180041625`
- `ntoskrnl!KeReleaseMutex` at `0x180041625`
- `ntoskrnl!KeWaitForSingleObject` at `0x180041609`
- `ntoskrnl!KeWaitForSingleObject` at `0x180041609`

## pseudocode

```c

```
