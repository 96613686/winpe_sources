# NetioRegisterTriageDumpDataCallback

- ea: `0x14005b810`
- end: `0x14005b8cc`
- name: `NetioRegisterTriageDumpDataCallback`
- size: `188`
- prototype: `__int64 __usercall@<rax>(PKBUGCHECK_REASON_CALLBACK_RECORD CallbackRecord@<rcx>, PUCHAR Component)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14005b900`
- `0x140069028`

## callees

- `0x14005b660`
- `0x14005b810`
- `0x140078400`

## import_xrefs

- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x14005b88d`
- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x14005b88d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b8a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b8a5`

## pseudocode

```c

```
