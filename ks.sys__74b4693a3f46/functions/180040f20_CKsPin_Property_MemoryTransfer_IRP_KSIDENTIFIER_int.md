# CKsPin::Property_MemoryTransfer(_IRP *,KSIDENTIFIER *,int *)

- ea: `0x180040f20`
- end: `0x18004103e`
- name: `?Property_MemoryTransfer@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAH@Z`
- size: `286`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x18000b7bc`
- `0x180019c60`
- `0x180040f20`
- `0x180057948`
- `0x18006509c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180041016`
- `ntoskrnl!KeReleaseMutex` at `0x180041016`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040fd1`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040fd1`

## pseudocode

```c

```
