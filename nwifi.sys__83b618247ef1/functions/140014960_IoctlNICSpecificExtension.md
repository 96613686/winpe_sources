# IoctlNICSpecificExtension

- ea: `0x140014960`
- end: `0x140014af6`
- name: `IoctlNICSpecificExtension`
- size: `406`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140020104`
- `0x1400337f4`

## callees

- `0x14000d22c`
- `0x140014960`
- `0x140015e34`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400149a1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014aa1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400149a1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014aa1`
- `ntoskrnl!KeBugCheck` at `0x140014a81`
- `ntoskrnl!KeBugCheck` at `0x140014a81`
- `ntoskrnl!KeSetEvent` at `0x1400149f1`
- `ntoskrnl!KeSetEvent` at `0x140014acb`
- `ntoskrnl!KeSetEvent` at `0x1400149f1`
- `ntoskrnl!KeSetEvent` at `0x140014acb`

## pseudocode

```c

```
