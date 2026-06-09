# CKsPin::Property_PinMDLcaching(_IRP *,KSIDENTIFIER *,KSPIN_MDL_CACHING_NOTIFICATION *)

- ea: `0x180041050`
- end: `0x180041213`
- name: `?Property_PinMDLcaching@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSPIN_MDL_CACHING_NOTIFICATION@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, struct KSPIN_MDL_CACHING_NOTIFICATION *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180019c60`
- `0x180041050`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1800411f7`
- `ntoskrnl!KeReleaseMutex` at `0x1800411f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800410f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800410f2`

## pseudocode

```c

```
