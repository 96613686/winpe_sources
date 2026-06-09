# BCryptConfigureContextFunction

- ea: `0x18006ae80`
- end: `0x18006b195`
- name: `BCryptConfigureContextFunction`
- size: `789`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, PCRYPT_CONTEXT_FUNCTION_CONFIG pConfig)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180022788`

## callees

- `0x180018af0`
- `0x180018e40`
- `0x180021d90`
- `0x180021f8c`
- `0x180025aa0`
- `0x1800267d0`
- `0x180041124`
- `0x1800497e0`
- `0x18004cb68`
- `0x18006ae80`
- `0x18006d3d4`
- `0x18006e41c`
- `0x18006fd88`
- `0x180072964`
- `0x180073440`
- `0x180073bfc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006b0fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006b10f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006b0fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006b10f`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006b0ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006b0ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b0b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b0b7`

## pseudocode

```c

```
