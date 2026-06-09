# Process::GetSidOrAccount(CInstance const &,CInstance *,ulong,int)

- ea: `0x18004833c`
- end: `0x180048988`
- name: `?GetSidOrAccount@Process@@AEAAKAEBVCInstance@@PEAV2@KH@Z`
- size: `1612`
- prototype: `unsigned int(Process *__hidden this, const struct CInstance *, struct CInstance *, unsigned int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180048060`
- `0x180049054`

## callees

- `0x18000ab30`
- `0x18000bef0`
- `0x18000cd50`
- `0x1800127e0`
- `0x180013ae0`
- `0x180016f88`
- `0x180022e7c`
- `0x18004833c`
- `0x180048990`
- `0x180048a10`
- `0x180048acc`
- `0x180049030`
- `0x18006c0a4`
- `0x180078ac8`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `msvcrt!free` at `0x1800487c4`
- `msvcrt!free` at `0x1800487c4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800483ce`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800483ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800484a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004858f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800485a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800484a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004858f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800485a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800483b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800483b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048910`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800484c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800484c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004897c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004897c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048902`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180048902`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180048406`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180048406`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800484e6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800484f2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800488bc`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800484e6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800484f2`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800488bc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048522`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048537`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048794`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048848`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048892`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800488e7`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048522`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048537`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048794`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048848`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180048892`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800488e7`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180048641`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180048641`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180048778`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180048825`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180048876`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180048778`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180048825`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180048876`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048543`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004854f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800485b7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800485c6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800487a8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004885a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180048543`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004854f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800485b7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800485c6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800487a8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004885a`

## string_xrefs

- `0x180048381`: `SeDebugPrivilege`
- `0x1800483ff`: `winsta.dll`
- `0x1800488f8`: `WinStationGetProcessSid`

## pseudocode

```c

```
