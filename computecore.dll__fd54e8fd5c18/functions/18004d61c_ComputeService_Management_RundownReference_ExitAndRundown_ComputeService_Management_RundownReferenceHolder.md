# ComputeService::Management::RundownReference::ExitAndRundown(ComputeService::Management::RundownReferenceHolder &&)

- ea: `0x18004d61c`
- end: `0x18004d693`
- name: `?ExitAndRundown@RundownReference@Management@ComputeService@@QEAAX$$QEAVRundownReferenceHolder@23@@Z`
- size: `119`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c4b4`
- `0x18002ce10`
- `0x180035da4`
- `0x180037750`

## callees

- `0x18000b948`
- `0x18004d61c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d675`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d630`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d630`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18004d65b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18004d65b`

## string_xrefs

- `0x18004d681`: `onecore\vm\compute\shared\rundownreference\rundownreference.cpp`

## pseudocode

```c

```
