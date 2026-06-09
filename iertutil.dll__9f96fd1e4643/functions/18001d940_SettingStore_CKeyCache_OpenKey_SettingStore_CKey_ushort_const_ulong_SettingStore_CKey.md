# SettingStore::CKeyCache::OpenKey(SettingStore::CKey *,ushort const *,ulong,SettingStore::CKey * *)

- ea: `0x18001d940`
- end: `0x18001e102`
- name: `?OpenKey@CKeyCache@SettingStore@@QEAAJPEAVCKey@2@PEBGKPEAPEAV32@@Z`
- size: `1986`
- prototype: `int(SettingStore::CKeyCache *__hidden this, struct SettingStore::CKey *, const unsigned __int16 *, unsigned int, struct SettingStore::CKey **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001b510`
- `0x18001d6e0`
- `0x18001e4a0`

## callees

- `0x18001d940`
- `0x18001ec54`
- `0x18001ef10`
- `0x18001f148`
- `0x180057098`
- `0x180078a00`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dd1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001dd1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dd03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001dd03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001da46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001db98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001da46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001db98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001db2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001dd3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001db2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001dd3c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001dcf6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001dcf6`

## pseudocode

```c

```
