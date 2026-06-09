# VfpSnatPortManager::Initialize(IpAddress const &,bool,ushort,_GUID const &,_GUID const &,wil::basic_zstring_view<ushort>,ulong,ushort)

- ea: `0x18026f7c8`
- end: `0x18026fa84`
- name: `?Initialize@VfpSnatPortManager@@QEAAXAEBVIpAddress@@_NGAEBU_GUID@@2V?$basic_zstring_view@G@wil@@KG@Z`
- size: `700`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, __int64, __int64, __int64, int, __int16)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18026f36c`
- `0x180270e24`

## callees

- `0x18005f59c`
- `0x18005ffb8`
- `0x180061240`
- `0x1800663fc`
- `0x1800666b4`
- `0x180069104`
- `0x1800a19ac`
- `0x1800a47b8`
- `0x1801cf19c`
- `0x18026f7c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18026f9ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18026f9ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18026f807`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18026f807`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18026f929`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18026f929`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18026f95a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18026f95a`

## string_xrefs

- `0x18026fa09`: `onecore\vm\dv\net\hns\service\core\vfpsnatportmanager.cpp`
- `0x18026fa2c`: `onecore\vm\dv\net\hns\service\core\vfpsnatportmanager.cpp`
- `0x18026fa4f`: `onecore\vm\dv\net\hns\service\core\vfpsnatportmanager.cpp`
- `0x18026fa72`: `onecore\vm\dv\net\hns\service\core\vfpsnatportmanager.cpp`

## pseudocode

```c

```
