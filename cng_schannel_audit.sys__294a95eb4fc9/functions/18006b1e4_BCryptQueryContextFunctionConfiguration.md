# BCryptQueryContextFunctionConfiguration

- ea: `0x18006b1e4`
- end: `0x18006b36e`
- name: `BCryptQueryContextFunctionConfiguration`
- size: `394`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, ULONG *pcbBuffer, PCRYPT_CONTEXT_FUNCTION_CONFIG *ppBuffer)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800256c8`

## callees

- `0x18001ba40`
- `0x18001be80`
- `0x180024cd0`
- `0x180024ecc`
- `0x1800289e0`
- `0x180029710`
- `0x180048d50`
- `0x18006b1e4`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x18006b334`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006b334`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b340`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b340`

## pseudocode

```c

```
