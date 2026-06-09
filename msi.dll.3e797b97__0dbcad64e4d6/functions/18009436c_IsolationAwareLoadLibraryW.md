# IsolationAwareLoadLibraryW

- ea: `0x18009436c`
- end: `0x180094436`
- name: `IsolationAwareLoadLibraryW`
- size: `202`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008d90`
- `0x180092314`
- `0x180092390`
- `0x1800942f0`
- `0x1800945b0`
- `0x18011812c`
- `0x1801b1840`
- `0x1801b2630`
- `0x1801c1aa0`
- `0x1801c1d4c`
- `0x1801c2698`
- `0x18021f6c0`
- `0x180220928`
- `0x180263800`

## callees

- `0x18009436c`
- `0x180094690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180094416`
- `KERNEL32!GetLastError` at `0x1802653b1`
- `KERNEL32!GetLastError` at `0x180094416`
- `KERNEL32!GetLastError` at `0x1802653b1`
- `KERNEL32!SetLastError` at `0x180094428`
- `KERNEL32!SetLastError` at `0x1802653dd`
- `KERNEL32!SetLastError` at `0x180094428`
- `KERNEL32!SetLastError` at `0x1802653dd`
- `KERNEL32!DeactivateActCtx` at `0x1800943e2`
- `KERNEL32!DeactivateActCtx` at `0x1802653cb`
- `KERNEL32!DeactivateActCtx` at `0x1800943e2`
- `KERNEL32!DeactivateActCtx` at `0x1802653cb`
- `KERNEL32!LoadLibraryW` at `0x1800943b5`
- `KERNEL32!LoadLibraryW` at `0x1800943b5`

## pseudocode

```c

```
