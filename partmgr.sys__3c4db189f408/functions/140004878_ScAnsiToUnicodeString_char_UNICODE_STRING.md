# ScAnsiToUnicodeString(char *,_UNICODE_STRING *)

- ea: `0x140004878`
- end: `0x140004953`
- name: `?ScAnsiToUnicodeString@@YAJPEADPEAU_UNICODE_STRING@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(PCSZ SourceString, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140006300`
- `0x140009ba8`
- `0x14000ec70`

## callees

- `0x140004878`
- `0x140004960`
- `0x14000a530`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000490c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004939`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000490c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004939`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400048ef`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400048ef`
- `ntoskrnl!RtlxAnsiStringToUnicodeSize` at `0x1400048b6`
- `ntoskrnl!RtlxAnsiStringToUnicodeSize` at `0x1400048b6`
- `ntoskrnl!RtlInitAnsiString` at `0x1400048a5`
- `ntoskrnl!RtlInitAnsiString` at `0x1400048a5`

## pseudocode

```c

```
