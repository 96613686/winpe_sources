# BCryptQueryContextFunctionConfiguration

- ea: `0x180075384`
- end: `0x18007550e`
- name: `BCryptQueryContextFunctionConfiguration`
- size: `394`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, ULONG *pcbBuffer, PCRYPT_CONTEXT_FUNCTION_CONFIG *ppBuffer)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002f7f8`

## callees

- `0x180025b70`
- `0x180025fb0`
- `0x18002ee00`
- `0x18002effc`
- `0x180032b10`
- `0x180033840`
- `0x180052e40`
- `0x180075384`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1800754d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800754d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800754e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800754e0`

## pseudocode

```c

```
