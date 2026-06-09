# CKsPin::Property_ConnectionDataFormat(_IRP *,KSIDENTIFIER *,KSDATAFORMAT *)

- ea: `0x1800401b0`
- end: `0x18004034d`
- name: `?Property_ConnectionDataFormat@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEATKSDATAFORMAT@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, union KSDATAFORMAT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000b7bc`
- `0x180019d00`
- `0x1800401b0`
- `0x1800558dc`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180040331`
- `ntoskrnl!KeReleaseMutex` at `0x180040331`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040241`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040289`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800402ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040241`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040289`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800402ef`

## pseudocode

```c

```
