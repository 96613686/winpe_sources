# IoctlWFDGetVisibleDevices(_IRP *,ulong *)

- ea: `0x14001a47c`
- end: `0x14001a6db`
- name: `?IoctlWFDGetVisibleDevices@@YAJPEAU_IRP@@PEAK@Z`
- size: `607`
- prototype: `__int64 __fastcall(struct _IRP *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000cb00`

## callees

- `0x14000d21c`
- `0x14001a47c`
- `0x140034968`
- `0x140038930`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001a4ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a689`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a4ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a689`
- `ntoskrnl!KeSetEvent` at `0x14001a52f`
- `ntoskrnl!KeSetEvent` at `0x14001a6bb`
- `ntoskrnl!KeSetEvent` at `0x14001a52f`
- `ntoskrnl!KeSetEvent` at `0x14001a6bb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a64c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a64c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a65d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a65d`

## pseudocode

```c

```
