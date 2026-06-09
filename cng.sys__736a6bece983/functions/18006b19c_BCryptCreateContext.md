# BCryptCreateContext

- ea: `0x18006b19c`
- end: `0x18006b406`
- name: `BCryptCreateContext`
- size: `618`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, PCRYPT_CONTEXT_CONFIG pConfig)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180022788`

## callees

- `0x180018af0`
- `0x180021d90`
- `0x180021f8c`
- `0x1800245a0`
- `0x180025aa0`
- `0x1800267d0`
- `0x180029370`
- `0x180041124`
- `0x18006b19c`
- `0x18006e230`
- `0x18006fd88`
- `0x1800725b8`
- `0x180072964`
- `0x180073bfc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006b397`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006b397`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006b363`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006b363`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b36f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b36f`

## pseudocode

```c

```
