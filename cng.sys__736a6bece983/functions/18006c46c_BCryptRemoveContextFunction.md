# BCryptRemoveContextFunction

- ea: `0x18006c46c`
- end: `0x18006c69a`
- name: `BCryptRemoveContextFunction`
- size: `558`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180022788`

## callees

- `0x180018af0`
- `0x180021d90`
- `0x180021f8c`
- `0x1800245a0`
- `0x180025aa0`
- `0x1800267d0`
- `0x1800317c0`
- `0x180041124`
- `0x1800497e0`
- `0x18006c46c`
- `0x18006e6c0`
- `0x180071eec`
- `0x180072964`
- `0x180073bfc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006c5ff`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006c612`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006c5ff`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006c612`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006c5bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006c5bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006c5c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006c5c8`

## pseudocode

```c

```
