# ReleaseInlineControl

- ea: `0x1400dfa54`
- end: `0x1400dfb9c`
- name: `ReleaseInlineControl`
- size: `328`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400bd6a4`
- `0x1400be3c0`
- `0x1400be464`
- `0x1400df5f8`
- `0x1400df860`
- `0x1400ecce0`

## callees

- `0x14000b998`
- `0x1400d0af0`
- `0x1400d0b64`
- `0x1400dfa54`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400dfb5f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400dfb5f`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfa86`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfaaf`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfada`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfb8f`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfa86`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfaaf`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfada`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfb8f`

## pseudocode

```c

```
