# BCryptDeleteContext

- ea: `0x180074bac`
- end: `0x180074de3`
- name: `BCryptDeleteContext`
- size: `567`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x18002f7f8`

## callees

- `0x180025b70`
- `0x180025ec0`
- `0x18002ee00`
- `0x18002effc`
- `0x180031610`
- `0x180032b10`
- `0x180033840`
- `0x1800363e0`
- `0x18004a570`
- `0x180056428`
- `0x180074bac`
- `0x1800779d0`
- `0x18007c104`
- `0x18007cb60`
- `0x18007d39c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180074d68`
- `ntoskrnl!RtlInitUnicodeString` at `0x180074d68`
- `ntoskrnl!ExReleaseResourceLite` at `0x180074d34`
- `ntoskrnl!ExReleaseResourceLite` at `0x180074d34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180074d40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180074d40`

## pseudocode

```c

```
