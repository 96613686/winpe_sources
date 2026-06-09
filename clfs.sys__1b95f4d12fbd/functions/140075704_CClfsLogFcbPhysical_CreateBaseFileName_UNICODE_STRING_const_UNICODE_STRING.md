# CClfsLogFcbPhysical::CreateBaseFileName(_UNICODE_STRING const &,_UNICODE_STRING &)

- ea: `0x140075704`
- end: `0x1400757b5`
- name: `?CreateBaseFileName@CClfsLogFcbPhysical@@CAJAEBU_UNICODE_STRING@@AEAU2@@Z`
- size: `177`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PUNICODE_STRING Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005f1c`
- `0x140076e00`

## callees

- `0x140018280`
- `0x140075704`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007577a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007577a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140075790`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140075790`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007574b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007574b`

## pseudocode

```c

```
