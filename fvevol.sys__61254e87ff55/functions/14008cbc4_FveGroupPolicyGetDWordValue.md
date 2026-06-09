# FveGroupPolicyGetDWordValue

- ea: `0x14008cbc4`
- end: `0x14008cc8a`
- name: `FveGroupPolicyGetDWordValue`
- size: `198`
- prototype: `__int64 __fastcall(PCWSTR Source, PCWSTR SourceString)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140052d14`
- `0x140063ca0`
- `0x140063e10`
- `0x140066554`
- `0x140066e1c`
- `0x14008b2f0`

## callees

- `0x14008cbc4`
- `0x140099114`
- `0x1400e08f4`
- `0x1400e6538`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008cc07`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008cc21`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008cc07`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008cc21`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008cc3b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008cc3b`

## string_xrefs

- `0x14008cbfb`: `\Registry\Machine\`

## pseudocode

```c

```
