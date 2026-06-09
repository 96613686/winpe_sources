# _NewLocalMachineKeyNameString

- ea: `0x180040d50`
- end: `0x180040e77`
- name: `_NewLocalMachineKeyNameString`
- size: `295`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18007d750`

## callees

- `0x180040d50`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180040dd7`
- `ntoskrnl!ExAllocatePool2` at `0x180040dd7`
- `ntoskrnl!SkIsSecureKernel` at `0x180040e42`
- `ntoskrnl!SkIsSecureKernel` at `0x180040e42`
- `ntoskrnl!SkAllocatePool` at `0x180040e64`
- `ntoskrnl!SkAllocatePool` at `0x180040e64`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180040e01`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180040e13`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180040e01`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180040e13`

## string_xrefs

- `0x180040d6e`: `\Registry\Machine\`

## pseudocode

```c

```
