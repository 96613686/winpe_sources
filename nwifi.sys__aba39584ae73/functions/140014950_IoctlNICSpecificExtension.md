# IoctlNICSpecificExtension

- ea: `0x140014950`
- end: `0x140014ae6`
- name: `IoctlNICSpecificExtension`
- size: `406`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140020104`
- `0x140033a14`

## callees

- `0x14000d21c`
- `0x140014950`
- `0x140015e24`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140014991`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014a91`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014991`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014a91`
- `ntoskrnl!KeBugCheck` at `0x140014a71`
- `ntoskrnl!KeBugCheck` at `0x140014a71`
- `ntoskrnl!KeSetEvent` at `0x1400149e1`
- `ntoskrnl!KeSetEvent` at `0x140014abb`
- `ntoskrnl!KeSetEvent` at `0x1400149e1`
- `ntoskrnl!KeSetEvent` at `0x140014abb`

## pseudocode

```c

```
