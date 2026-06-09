# BaseRegGetKeySemantics

- ea: `0x180060db0`
- end: `0x18006121a`
- name: `BaseRegGetKeySemantics`
- size: `1130`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCUNICODE_STRING Source)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002c150`
- `0x18005cc70`
- `0x18005ebc0`
- `0x180061220`
- `0x180061370`
- `0x180061910`
- `0x180061d14`
- `0x1800a4bd0`
- `0x1800bcff0`
- `0x18018f578`

## callees

- `0x180060db0`
- `0x1801368e8`
- `0x180194eb9`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180060f15`
- `ntdll!RtlEqualUnicodeString` at `0x180060fa6`
- `ntdll!RtlEqualUnicodeString` at `0x1800610a7`
- `ntdll!RtlEqualUnicodeString` at `0x180060f15`
- `ntdll!RtlEqualUnicodeString` at `0x180060fa6`
- `ntdll!RtlEqualUnicodeString` at `0x1800610a7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180060e6b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180060e6b`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060e44`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060eec`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060f72`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060e44`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060eec`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060f72`
- `ntdll!NtQueryKey` at `0x180060fee`
- `ntdll!NtQueryKey` at `0x1800611b6`
- `ntdll!NtQueryKey` at `0x180060fee`
- `ntdll!NtQueryKey` at `0x1800611b6`
- `ntdll!RtlFreeHeap` at `0x1800611f4`
- `ntdll!RtlFreeHeap` at `0x1800611f4`
- `ntdll!RtlAllocateHeap` at `0x18006103b`
- `ntdll!RtlAllocateHeap` at `0x18006118f`
- `ntdll!RtlAllocateHeap` at `0x18006103b`
- `ntdll!RtlAllocateHeap` at `0x18006118f`

## string_xrefs

- `0x180060ed5`: `\Registry\User`

## pseudocode

```c

```
