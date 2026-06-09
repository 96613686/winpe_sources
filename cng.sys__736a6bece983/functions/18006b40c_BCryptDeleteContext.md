# BCryptDeleteContext

- ea: `0x18006b40c`
- end: `0x18006b643`
- name: `BCryptDeleteContext`
- size: `567`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180022788`

## callees

- `0x180018af0`
- `0x180018e40`
- `0x180021d90`
- `0x180021f8c`
- `0x1800245a0`
- `0x180025aa0`
- `0x1800267d0`
- `0x180029370`
- `0x180041124`
- `0x18004cb68`
- `0x18006b40c`
- `0x18006e230`
- `0x180072964`
- `0x1800733c0`
- `0x180073bfc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006b5c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006b5c8`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006b594`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006b594`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b5a0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b5a0`

## pseudocode

```c

```
