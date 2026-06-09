# CKsPin::Property_ConnectionDataFormat(_IRP *,KSIDENTIFIER *,KSDATAFORMAT *)

- ea: `0x1800401c0`
- end: `0x18004035d`
- name: `?Property_ConnectionDataFormat@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEATKSDATAFORMAT@@@Z`
- size: `413`
- prototype: `static int(struct _IRP *, struct KSIDENTIFIER *, union KSDATAFORMAT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000b7bc`
- `0x180019cc0`
- `0x1800401c0`
- `0x18005573c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180040341`
- `ntoskrnl!KeReleaseMutex` at `0x180040341`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040251`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040299`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800402ff`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040251`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040299`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800402ff`

## pseudocode

```c

```
