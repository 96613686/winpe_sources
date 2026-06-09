# CClfsBaseFilePersisted::CreateAbsoluteContainerPath(_UNICODE_STRING const &,_UNICODE_STRING &)

- ea: `0x14006e00c`
- end: `0x14006e1d1`
- name: `?CreateAbsoluteContainerPath@CClfsBaseFilePersisted@@AEAAJAEBU_UNICODE_STRING@@AEAU2@@Z`
- size: `453`
- prototype: `int(CClfsBaseFilePersisted *__hidden this, const struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14005ed70`
- `0x140062ef8`

## callees

- `0x14000d778`
- `0x140018280`
- `0x14006e00c`
- `0x140075d10`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006e101`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006e115`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006e101`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14006e115`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e1bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b9f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e1bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b9f0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14006e15b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14006e15b`

## pseudocode

```c

```
