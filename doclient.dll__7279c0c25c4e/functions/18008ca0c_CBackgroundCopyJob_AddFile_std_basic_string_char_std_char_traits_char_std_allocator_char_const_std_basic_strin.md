# CBackgroundCopyJob::AddFile(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,uint,DownloadRange const *,unsigned __int64,std::shared_ptr<CBackgroundCopyFile> &)

- ea: `0x18008ca0c`
- end: `0x18008cc7d`
- name: `?AddFile@CBackgroundCopyJob@@QEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@00IPEBUDownloadRange@@_KAEAV?$shared_ptr@VCBackgroundCopyFile@@@3@@Z`
- size: `625`
- prototype: `__int64 __fastcall(CBackgroundCopyJob *this, const char *, const char *, __int64, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180010900`
- `0x180011110`

## callees

- `0x18000933c`
- `0x1800095a0`
- `0x18000a4fc`
- `0x18000cdd0`
- `0x1800199b4`
- `0x180019c5c`
- `0x18008ca0c`
- `0x18008eb44`
- `0x1800928e4`
- `0x1800a1ea4`
- `0x1800a9af0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008cac3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008caf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008cb1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008cc28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008cac3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008caf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008cb1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008cc28`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008cada`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008cc09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008cada`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008cc09`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008cc1f`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18008cc1f`

## string_xrefs

- `0x18008ca97`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008cbe7`: `CBackgroundCopyJob::AddFile`

## pseudocode

```c

```
