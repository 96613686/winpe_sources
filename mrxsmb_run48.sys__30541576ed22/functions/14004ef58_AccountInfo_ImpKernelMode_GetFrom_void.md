# AccountInfo<ImpKernelMode>::GetFrom(void *)

- ea: `0x14004ef58`
- end: `0x14004f082`
- name: `?GetFrom@?$AccountInfo@VImpKernelMode@@@@QEAAJPEAX@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14004e27c`
- `0x14004e6ec`

## callees

- `0x14004ef58`
- `0x14004f114`
- `0x14004f19c`
- `0x14004f294`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004efcb`
- `ntoskrnl!ExAllocatePool2` at `0x14004f012`
- `ntoskrnl!ExAllocatePool2` at `0x14004efcb`
- `ntoskrnl!ExAllocatePool2` at `0x14004f012`

## string_xrefs

- `0x14004efe2`: `Error Allocating buffer in LookupAccountSid: %d`
- `0x14004efaa`: `Error in LookupAccountSid(Pre): %d`
- `0x14004f04c`: `Error in LookupAccountSid(Post): %d`

## pseudocode

```c

```
