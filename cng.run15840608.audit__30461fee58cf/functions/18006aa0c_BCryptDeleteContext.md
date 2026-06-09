# BCryptDeleteContext

- ea: `0x18006aa0c`
- end: `0x18006ac43`
- name: `BCryptDeleteContext`
- size: `567`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1800256c8`

## callees

- `0x18001ba40`
- `0x18001bd90`
- `0x180024cd0`
- `0x180024ecc`
- `0x1800274e0`
- `0x1800289e0`
- `0x180029710`
- `0x18002c2b0`
- `0x180040594`
- `0x18004c328`
- `0x18006aa0c`
- `0x18006d830`
- `0x180071f64`
- `0x1800729c0`
- `0x1800731fc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006abc8`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006abc8`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006ab94`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006ab94`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006aba0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006aba0`

## pseudocode

```c

```
