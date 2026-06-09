# BCryptConfigureContextFunction

- ea: `0x180074620`
- end: `0x180074935`
- name: `BCryptConfigureContextFunction`
- size: `789`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, PCRYPT_CONTEXT_FUNCTION_CONFIG pConfig)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18002f7f8`

## callees

- `0x180025b70`
- `0x180025ec0`
- `0x18002ee00`
- `0x18002effc`
- `0x180032b10`
- `0x180033840`
- `0x18004a570`
- `0x180052e40`
- `0x180056428`
- `0x180074620`
- `0x180076b74`
- `0x180077bbc`
- `0x180079528`
- `0x18007c104`
- `0x18007cbe0`
- `0x18007d39c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18007489c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800748af`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007489c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800748af`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007484b`
- `ntoskrnl!ExReleaseResourceLite` at `0x18007484b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180074857`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180074857`

## pseudocode

```c

```
