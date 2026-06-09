# BCryptQueryContextConfiguration

- ea: `0x18006ba8c`
- end: `0x18006bbdc`
- name: `BCryptQueryContextConfiguration`
- size: `336`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG *pcbBuffer, PCRYPT_CONTEXT_CONFIG *ppBuffer)`
- caller_count: `1`
- callee_count: `7`
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
- `0x18006ba8c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x18006bba2`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006bba2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006bbae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006bbae`

## pseudocode

```c

```
