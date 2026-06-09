# FveTransformCleanup

- ea: `0x1400e51a8`
- end: `0x1400e53dd`
- name: `FveTransformCleanup`
- size: `565`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14005822c`
- `0x140077a10`
- `0x14007b380`
- `0x1400c6f58`
- `0x1400e5180`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x1400d3750`
- `0x1400e51a8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e5255`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e5255`
- `ntoskrnl!IoFreeMdl` at `0x1400e530a`
- `ntoskrnl!IoFreeMdl` at `0x1400e530a`
- `ntoskrnl!KeBugCheckEx` at `0x1400e53ac`
- `ntoskrnl!KeBugCheckEx` at `0x1400e53d0`
- `ntoskrnl!KeBugCheckEx` at `0x1400e53ac`
- `ntoskrnl!KeBugCheckEx` at `0x1400e53d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e5282`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e52b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e52ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e532a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e534c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e5282`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e52b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e52ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e532a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e534c`

## pseudocode

```c

```
