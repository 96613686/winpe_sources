# BCryptConfigureContext

- ea: `0x18006accc`
- end: `0x18006ae79`
- name: `BCryptConfigureContext`
- size: `429`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, PCRYPT_CONTEXT_CONFIG pConfig)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180022788`

## callees

- `0x180018af0`
- `0x180021d90`
- `0x180021f8c`
- `0x180025aa0`
- `0x1800267d0`
- `0x180041124`
- `0x18006accc`
- `0x18006e014`
- `0x18006fd88`
- `0x180072964`
- `0x180073bfc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006ae08`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006ae08`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006add3`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006add3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006addf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006addf`

## pseudocode

```c

```
