# BCryptCreateContext

- ea: `0x18007493c`
- end: `0x180074ba6`
- name: `BCryptCreateContext`
- size: `618`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, PCRYPT_CONTEXT_CONFIG pConfig)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18002f7f8`

## callees

- `0x180025b70`
- `0x18002ee00`
- `0x18002effc`
- `0x180031610`
- `0x180032b10`
- `0x180033840`
- `0x1800363e0`
- `0x18004a570`
- `0x18007493c`
- `0x1800779d0`
- `0x180079528`
- `0x18007bd58`
- `0x18007c104`
- `0x18007d39c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180074b37`
- `ntoskrnl!RtlInitUnicodeString` at `0x180074b37`
- `ntoskrnl!ExReleaseResourceLite` at `0x180074b03`
- `ntoskrnl!ExReleaseResourceLite` at `0x180074b03`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180074b0f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180074b0f`

## pseudocode

```c

```
