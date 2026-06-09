# BCryptRemoveContextFunction

- ea: `0x18006ba6c`
- end: `0x18006bc9a`
- name: `BCryptRemoveContextFunction`
- size: `558`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800256c8`

## callees

- `0x18001ba40`
- `0x180024cd0`
- `0x180024ecc`
- `0x1800274e0`
- `0x1800289e0`
- `0x180029710`
- `0x180030cc0`
- `0x180040594`
- `0x180048d50`
- `0x18006ba6c`
- `0x18006dcc0`
- `0x1800714ec`
- `0x180071f64`
- `0x1800731fc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006bbff`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006bc12`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006bbff`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006bc12`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006bbbc`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006bbbc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006bbc8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006bbc8`

## pseudocode

```c

```
