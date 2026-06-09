# BCryptRemoveContextFunction

- ea: `0x180075c0c`
- end: `0x180075e3a`
- name: `BCryptRemoveContextFunction`
- size: `558`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18002f7f8`

## callees

- `0x180025b70`
- `0x18002ee00`
- `0x18002effc`
- `0x180031610`
- `0x180032b10`
- `0x180033840`
- `0x18003adf0`
- `0x18004a570`
- `0x180052e40`
- `0x180075c0c`
- `0x180077e60`
- `0x18007b68c`
- `0x18007c104`
- `0x18007d39c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180075d9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x180075db2`
- `ntoskrnl!RtlInitUnicodeString` at `0x180075d9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x180075db2`
- `ntoskrnl!ExReleaseResourceLite` at `0x180075d5c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180075d5c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180075d68`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180075d68`

## pseudocode

```c

```
