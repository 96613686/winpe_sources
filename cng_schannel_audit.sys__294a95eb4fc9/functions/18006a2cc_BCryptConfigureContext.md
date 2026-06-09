# BCryptConfigureContext

- ea: `0x18006a2cc`
- end: `0x18006a479`
- name: `BCryptConfigureContext`
- size: `429`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, PCRYPT_CONTEXT_CONFIG pConfig)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800256c8`

## callees

- `0x18001ba40`
- `0x180024cd0`
- `0x180024ecc`
- `0x1800289e0`
- `0x180029710`
- `0x180040594`
- `0x18006a2cc`
- `0x18006d614`
- `0x18006f388`
- `0x180071f64`
- `0x1800731fc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006a408`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006a408`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006a3d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006a3d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a3df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a3df`

## pseudocode

```c

```
