# ComputeService::Management::RundownReference::Enter(void)

- ea: `0x18004d540`
- end: `0x18004d615`
- name: `?Enter@RundownReference@Management@ComputeService@@QEAA?AV?$optional@VRundownReferenceHolder@Management@ComputeService@@@std@@XZ`
- size: `213`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c380`
- `0x18002c41c`
- `0x18002c4b4`
- `0x18002ce10`
- `0x180035da4`
- `0x180036eac`
- `0x180037750`

## callees

- `0x18000b948`
- `0x18004d540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004d5ce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d555`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d593`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d555`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004d593`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004d5b6`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004d5b6`

## string_xrefs

- `0x18004d5ec`: `onecore\vm\compute\shared\rundownreference\rundownreference.cpp`
- `0x18004d603`: `onecore\vm\compute\shared\rundownreference\rundownreference.cpp`

## pseudocode

```c

```
