# Process::ExecGetOwnerSid(CInstance const &,CInstance *,CInstance *,long)

- ea: `0x180049054`
- end: `0x18004930a`
- name: `?ExecGetOwnerSid@Process@@AEAAJAEBVCInstance@@PEAV2@1J@Z`
- size: `694`
- prototype: `int(Process *__hidden this, const struct CInstance *, struct CInstance *, struct CInstance *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180047f20`

## callees

- `0x180014c58`
- `0x18004833c`
- `0x180049054`
- `0x180075d2c`
- `0x1800f1678`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800490ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180049124`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800490ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180049124`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049131`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490f8`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180049091`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180049091`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800490be`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800490be`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800490ae`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18004920e`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800490ae`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18004920e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800492d7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800492d7`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800491ea`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800491ea`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800491fc`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x180049283`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x1800491fc`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x180049283`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x180049250`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x180049250`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800490a3`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800490d7`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180049149`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800490a3`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800490d7`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180049149`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180049186`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800491ad`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180049186`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800491ad`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x180049174`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x18004919b`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x180049174`
- `framedynos!??H@YA?AVCHString@@AEBV0@PEBG@Z` at `0x18004919b`
- `framedynos!??H@YA?AVCHString@@PEBGAEBV0@@Z` at `0x18004915f`
- `framedynos!??H@YA?AVCHString@@PEBGAEBV0@@Z` at `0x18004915f`
- `framedynos!?GetInstanceByPath@CWbemProviderGlue@@SAJPEBGPEAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x18004921e`
- `framedynos!?GetInstanceByPath@CWbemProviderGlue@@SAJPEBGPEAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x18004921e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800491b8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800491c3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800491ce`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800491d9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004928e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180049299`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800492a4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800492b5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800492c0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800491b8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800491c3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800491ce`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800491d9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004928e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180049299`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800492a4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800492b5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800492c0`

## string_xrefs

- `0x180049249`: `ProcessId`
- `0x180049098`: `__RELPATH`

## pseudocode

```c

```
