# FsLibIoFailureAddTableEntry

- ea: `0x1402f8cf0`
- end: `0x1402f8ff0`
- name: `FsLibIoFailureAddTableEntry`
- size: `768`
- prototype: `__int64 __fastcall(int, int, int, int, PCANSI_STRING SourceString, PCUNICODE_STRING StringIn)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1402d4ec0`

## callees

- `0x1401e9a3c`
- `0x1402f8cf0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1402f8d54`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402f8d54`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402f8fcb`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402f8fcb`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1402f8e8d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1402f8f6f`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1402f8e8d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1402f8f6f`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1402f8e67`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1402f8f38`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1402f8e67`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1402f8f38`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402f8f19`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402f8f54`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402f8f19`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402f8f54`

## pseudocode

```c

```
