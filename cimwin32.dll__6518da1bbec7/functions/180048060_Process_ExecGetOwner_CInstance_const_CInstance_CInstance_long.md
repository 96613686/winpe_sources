# Process::ExecGetOwner(CInstance const &,CInstance *,CInstance *,long)

- ea: `0x180048060`
- end: `0x180048335`
- name: `?ExecGetOwner@Process@@AEAAJAEBVCInstance@@PEAV2@1J@Z`
- size: `725`
- prototype: `int(Process *__hidden this, const struct CInstance *, struct CInstance *, struct CInstance *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180047f20`

## callees

- `0x180014c58`
- `0x180048060`
- `0x18004833c`
- `0x180075d2c`
- `0x1800f1678`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800480fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800482fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800480fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800482fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004830b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004830b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482cb`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18004809d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18004809d`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800480ca`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800480ca`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800480ba`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800481d5`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800480ba`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800481d5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18004829f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18004829f`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800481b1`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800481b1`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800481c3`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x180048251`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800481c3`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x180048251`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x180048221`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x180048221`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800480af`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800480e3`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180048110`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800480af`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800480e3`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180048110`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x18004814d`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180048174`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x18004814d`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180048174`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x18004813b`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x180048162`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x18004813b`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x180048162`
- `framedynos!??H@YA?AVCHString@@PEBGAEBV0@@Z` at `0x180048126`
- `framedynos!??H@YA?AVCHString@@PEBGAEBV0@@Z` at `0x180048126`
- `framedynos!?GetInstanceByPath@CWbemProviderGlue@@SAJPEBGPEAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x1800481e5`
- `framedynos!?GetInstanceByPath@CWbemProviderGlue@@SAJPEBGPEAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x1800481e5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004817f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004818a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048195`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800481a0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004825c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048267`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048272`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004827d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048288`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004817f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004818a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048195`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800481a0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004825c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048267`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048272`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004827d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048288`

## string_xrefs

- `0x18004821a`: `ProcessId`
- `0x1800480a4`: `__RELPATH`

## pseudocode

```c

```
