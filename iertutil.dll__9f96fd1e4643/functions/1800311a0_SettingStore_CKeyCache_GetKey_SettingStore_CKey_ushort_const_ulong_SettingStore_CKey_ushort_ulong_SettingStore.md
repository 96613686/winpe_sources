# SettingStore::CKeyCache::_GetKey(SettingStore::CKey *,ushort const *,ulong,SettingStore::CKey * *,ushort *,ulong,SettingStore::MATCH_TYPE *)

- ea: `0x1800311a0`
- end: `0x180031667`
- name: `?_GetKey@CKeyCache@SettingStore@@AEAAJPEAVCKey@2@PEBGKPEAPEAV32@PEAGKPEAW4MATCH_TYPE@2@@Z`
- size: `1223`
- prototype: `__int64 __fastcall(SettingStore::CKeyCache *__hidden this, struct SettingStore::CKey *, const unsigned __int16 *, unsigned int, struct SettingStore::CKey **, unsigned __int16 *, unsigned int, enum SettingStore::MATCH_TYPE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004b0dc`

## callees

- `0x1800311a0`
- `0x180031670`
- `0x180057098`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003154c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003154c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031532`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031532`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180031258`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800313ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180031258`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800313ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003133c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031562`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003133c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031562`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180031525`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180031525`

## pseudocode

```c

```
