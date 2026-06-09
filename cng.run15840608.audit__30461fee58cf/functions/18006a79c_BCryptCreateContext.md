# BCryptCreateContext

- ea: `0x18006a79c`
- end: `0x18006aa06`
- name: `BCryptCreateContext`
- size: `618`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, PCRYPT_CONTEXT_CONFIG pConfig)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1800256c8`

## callees

- `0x18001ba40`
- `0x180024cd0`
- `0x180024ecc`
- `0x1800274e0`
- `0x1800289e0`
- `0x180029710`
- `0x18002c2b0`
- `0x180040594`
- `0x18006a79c`
- `0x18006d830`
- `0x18006f388`
- `0x180071bb8`
- `0x180071f64`
- `0x1800731fc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006a997`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006a997`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006a963`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006a963`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a96f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006a96f`

## pseudocode

```c

```
