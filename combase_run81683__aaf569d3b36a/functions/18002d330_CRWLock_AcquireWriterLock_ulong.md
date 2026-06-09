# CRWLock::AcquireWriterLock(ulong)

- ea: `0x18002d330`
- end: `0x18002d6fc`
- name: `?AcquireWriterLock@CRWLock@@QEAAKK@Z`
- size: `972`
- prototype: `unsigned int __fastcall(CRWLock *this, unsigned int dwDesiredTimeout)`
- caller_count: `48`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002aa78`
- `0x18002ad18`
- `0x18002b568`
- `0x18002b76c`
- `0x18002b970`
- `0x18002bf7c`
- `0x18002c0b4`
- `0x18002c4c0`
- `0x18002c638`
- `0x18002c684`
- `0x18002c808`
- `0x18002cd2c`
- `0x18002cfcc`
- `0x18002d19c`
- `0x18002d710`
- `0x18002e86c`
- `0x18002ed60`
- `0x18003aa1c`
- `0x180079c5c`
- `0x18007a280`
- `0x18007b118`
- `0x18008abdc`
- `0x18008c140`
- `0x18008cf0c`
- `0x18008de60`
- `0x18008e0c4`
- `0x1800fd8b0`
- `0x1800fdb14`
- `0x180107fc8`
- `0x180109374`
- `0x180123284`
- `0x18012ac60`
- `0x18012cf5c`
- `0x1801343b8`
- `0x18013464c`
- `0x180137e18`
- `0x180145e58`
- `0x18016f77c`
- `0x1801731a4`
- `0x180173678`
- `0x1801739e8`
- `0x18017fcd8`
- `0x1801815e0`
- `0x18018175c`
- `0x1801d3be4`
- `0x1801d3f04`
- `0x1801d4078`
- `0x1801d4a80`

## callees

- `0x18002d330`
- `0x18002dd08`
- `0x18002deac`
- `0x1800e79b0`
- `0x18013360c`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18002d5e6`
- `ntdll!RtlDllShutdownInProgress` at `0x18002d5e6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d5f0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d5f0`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18002d4a8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18002d4a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d33d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d33d`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002d694`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18002d694`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d62d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d6d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d62d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d6d7`

## pseudocode

```c

```
