# HcsClient::OperationTracker::CompletePendingOperationsOnExitEvent(_GUID const &,long,ushort const *)

- ea: `0x180049f24`
- end: `0x18004a269`
- name: `?CompletePendingOperationsOnExitEvent@OperationTracker@HcsClient@@AEAAXAEBU_GUID@@JPEBG@Z`
- size: `837`
- prototype: `void(HcsClient::OperationTracker *__hidden this, const struct _GUID *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180048d5c`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x18001fea4`
- `0x180020494`
- `0x1800216cc`
- `0x180026224`
- `0x180029f2c`
- `0x180047ea8`
- `0x180048740`
- `0x180049a58`
- `0x180049f24`
- `0x18004b2b0`
- `0x18004cbf0`
- `0x18004cc30`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a0de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a0de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049fb5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049fb5`

## string_xrefs

- `0x180049f73`: `ClientLib_CompleteAllOperations`

## pseudocode

```c

```
