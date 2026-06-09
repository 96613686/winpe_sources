# PerfpAddCounterSet

- ea: `0x180098ee8`
- end: `0x180099116`
- name: `PerfpAddCounterSet`
- size: `558`
- prototype: `__int64 __fastcall(PVOID TableContext, void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180099120`

## callees

- `0x1800982b8`
- `0x180098ee8`
- `0x180194eb9`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180099012`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180099012`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180099048`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180099048`
- `ntdll!RtlInitializeSRWLock` at `0x180099076`
- `ntdll!RtlInitializeSRWLock` at `0x1800990be`
- `ntdll!RtlInitializeSRWLock` at `0x180099076`
- `ntdll!RtlInitializeSRWLock` at `0x1800990be`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18009902d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18009902d`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800990ab`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800990ab`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800990f1`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800990f1`

## pseudocode

```c

```
