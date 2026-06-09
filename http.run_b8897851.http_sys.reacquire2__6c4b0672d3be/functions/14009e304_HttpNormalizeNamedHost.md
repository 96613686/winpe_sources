# HttpNormalizeNamedHost

- ea: `0x14009e304`
- end: `0x14009e83c`
- name: `HttpNormalizeNamedHost`
- size: `1336`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140026f7c`

## callees

- `0x140028c44`
- `0x14009e304`
- `0x1400a6dc8`
- `0x1401c3bc8`
- `0x1401c3f58`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x14009e464`
- `ntoskrnl!_wcsnicmp` at `0x14009e464`
- `ntoskrnl!RtlIdnToUnicode` at `0x14009e6f3`
- `ntoskrnl!RtlIdnToUnicode` at `0x14009e6f3`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x14009e72c`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x14009e72c`
- `ntoskrnl!RtlIdnToNameprepUnicode` at `0x14009e495`
- `ntoskrnl!RtlIdnToNameprepUnicode` at `0x14009e495`
- `ntoskrnl!ExAllocatePool3` at `0x14009e379`
- `ntoskrnl!ExAllocatePool3` at `0x14009e3bc`
- `ntoskrnl!ExAllocatePool3` at `0x14009e379`
- `ntoskrnl!ExAllocatePool3` at `0x14009e3bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009e4c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009e6b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009e4c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009e6b5`

## pseudocode

```c

```
