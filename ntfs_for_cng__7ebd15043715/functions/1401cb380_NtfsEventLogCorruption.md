# NtfsEventLogCorruption

- ea: `0x1401cb380`
- end: `0x1401cbe16`
- name: `NtfsEventLogCorruption`
- size: `2710`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, unsigned int, char, char)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400c9540`

## callees

- `0x140007ea0`
- `0x140008278`
- `0x140020de0`
- `0x140059250`
- `0x1400b648c`
- `0x1401cb380`
- `0x1401cbe1c`
- `0x1401cbee0`
- `0x1401cbffc`
- `0x1401ccb48`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1401cb965`
- `ntoskrnl!EtwWrite` at `0x1401cb965`
- `ntoskrnl!_snwprintf_s` at `0x1401cb77d`
- `ntoskrnl!_snwprintf_s` at `0x1401cbb5b`
- `ntoskrnl!_snwprintf_s` at `0x1401cb77d`
- `ntoskrnl!_snwprintf_s` at `0x1401cbb5b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1401cb4ce`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1401cba89`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1401cb4ce`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1401cba89`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cb538`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cb799`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cbb77`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cb538`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cb799`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401cbb77`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401cb43d`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401cb43d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401cbdf6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402afdd3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1401cbdf6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402afdd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cbde3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402afdbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401cbde3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402afdbc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401cb4a5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401cb4a5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401cb4fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401cb4fd`

## string_xrefs

- `0x1401cbce6`: `EVENT_DATA_DESCRIPTOR array too small`
- `0x1401cbd24`: `EVENT_DATA_DESCRIPTOR array too small`
- `0x1401cbd8c`: `EVENT_DATA_DESCRIPTOR array too small`

## pseudocode

```c

```
