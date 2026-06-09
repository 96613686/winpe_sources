# CTrackedWorkload::ProcessCompletedInstances(CContext *,unsigned __int64 *,uint,unsigned __int64,CCriticalSection::CLock &)

- ea: `0x1800cbc84`
- end: `0x1800cbe18`
- name: `?ProcessCompletedInstances@CTrackedWorkload@@AEAAXPEAVCContext@@PEA_KI_KAEAUCLock@CCriticalSection@@@Z`
- size: `404`
- prototype: `void __fastcall(CTrackedWorkload *__hidden this, struct CContext *, unsigned __int64 *, unsigned int, unsigned __int64, struct CCriticalSection::CLock *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800cb538`
- `0x1800cb8e4`

## callees

- `0x1800aa990`
- `0x1800cbc84`
- `0x1800cc27c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbd07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbd07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbd1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbd1c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800cbd12`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800cbd12`

## pseudocode

```c

```
