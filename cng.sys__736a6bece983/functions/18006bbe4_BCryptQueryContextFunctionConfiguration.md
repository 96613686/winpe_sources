# BCryptQueryContextFunctionConfiguration

- ea: `0x18006bbe4`
- end: `0x18006bd6e`
- name: `BCryptQueryContextFunctionConfiguration`
- size: `394`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, ULONG *pcbBuffer, PCRYPT_CONTEXT_FUNCTION_CONFIG *ppBuffer)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180022788`

## callees

- `0x180018af0`
- `0x180018f30`
- `0x180021d90`
- `0x180021f8c`
- `0x180025aa0`
- `0x1800267d0`
- `0x1800497e0`
- `0x18006bbe4`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x18006bd34`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006bd34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006bd40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006bd40`

## pseudocode

```c

```
