# FveTransformCleanup

- ea: `0x1400e7df8`
- end: `0x1400e8045`
- name: `FveTransformCleanup`
- size: `589`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14005a27c`
- `0x140079a40`
- `0x14007d420`
- `0x1400ca9e8`
- `0x1400e7dd0`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x1400d93d0`
- `0x1400e7df8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e7ea5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400e7ea5`
- `ntoskrnl!IoFreeMdl` at `0x1400e7f5a`
- `ntoskrnl!IoFreeMdl` at `0x1400e7f5a`
- `ntoskrnl!KeBugCheckEx` at `0x1400e8014`
- `ntoskrnl!KeBugCheckEx` at `0x1400e8038`
- `ntoskrnl!KeBugCheckEx` at `0x1400e8014`
- `ntoskrnl!KeBugCheckEx` at `0x1400e8038`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7ed2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7f07`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7f3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7f92`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7fb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7ed2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7f07`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7f3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7f92`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e7fb4`

## pseudocode

```c

```
