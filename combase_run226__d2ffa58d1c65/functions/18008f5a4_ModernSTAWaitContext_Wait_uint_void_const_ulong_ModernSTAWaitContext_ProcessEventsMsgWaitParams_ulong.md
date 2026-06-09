# ModernSTAWaitContext::Wait(uint,void * const *,ulong,ModernSTAWaitContext::ProcessEventsMsgWaitParams *,ulong *)

- ea: `0x18008f5a4`
- end: `0x180090014`
- name: `?Wait@ModernSTAWaitContext@@QEAAKIPEBQEAXKPEAUProcessEventsMsgWaitParams@1@PEAK@Z`
- size: `2672`
- prototype: `unsigned int __fastcall(ModernSTAWaitContext *this, unsigned int cHandlesOuter, void *const *pHandlesOuter, unsigned int dwTimeoutOuter, ModernSTAWaitContext::ProcessEventsMsgWaitParams *pProcessEventsMsgWaitParams, unsigned int *pdwLastError)`
- caller_count: `4`
- callee_count: `31`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008d388`
- `0x18008e758`
- `0x18008f120`
- `0x18008f470`

## callees

- `0x18007340c`
- `0x1800865f4`
- `0x18008dab4`
- `0x18008db2c`
- `0x18008dd50`
- `0x18008e300`
- `0x18008f420`
- `0x18008f5a4`
- `0x18009001c`
- `0x1800902f0`
- `0x1800903b8`
- `0x180090550`
- `0x180090594`
- `0x180090740`
- `0x180090780`
- `0x180090f44`
- `0x180091038`
- `0x180091500`
- `0x1800919fc`
- `0x180091df4`
- `0x1800c9830`
- `0x1800ebbe4`
- `0x1801457c0`
- `0x18014d5f4`
- `0x18016246c`
- `0x1801999b0`
- `0x18019a654`
- `0x1801b0c18`
- `0x1801b0e44`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008f6ff`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008f7d1`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008f6ff`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008f7d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008f63e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008f834`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008faf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008f63e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008f834`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008faf5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008f694`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008f880`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008fb2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008fd42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008f694`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008f880`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008fb2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008fd42`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18008f826`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18008f9a6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18008f826`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18008f9a6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetQueueStatus` at `0x18008fc28`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetQueueStatus` at `0x18008fc28`

## string_xrefs

- `0x18008fa36`: `onecore\com\combase\dcomrem\modernsta.cpp`
- `0x18008fc8f`: `onecore\com\combase\dcomrem\modernsta.cpp`
- `0x18008fe7b`: `onecore\com\combase\dcomrem\modernsta.cpp`
- `0x18008fee0`: `onecore\com\combase\dcomrem\modernsta.cpp`
- `0x18008ff54`: `onecore\com\combase\dcomrem\modernsta.cpp`
- `0x18008ffe3`: `onecore\com\combase\dcomrem\modernsta.cpp`
- `0x18008ff3c`: `Woken by FreeUnusedDLLs timer`
- `0x18008fec5`: `Woken by input, not in CoMsgWaitInProcessEvents`

## pseudocode

```c

```
