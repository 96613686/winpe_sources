# CWin32OS::ExecMethod(CInstance const &,ushort * const,CInstance *,CInstance *,long)

- ea: `0x1800bcbb0`
- end: `0x1800bd090`
- name: `?ExecMethod@CWin32OS@@EEAAJAEBVCInstance@@QEAGPEAV2@2J@Z`
- size: `1248`
- prototype: `int(CWin32OS *__hidden this, const struct CInstance *, unsigned __int16 *const, struct CInstance *, struct CInstance *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001712c`
- `0x180041890`
- `0x180084a08`
- `0x180084b74`
- `0x1800bcbb0`
- `0x1800bd098`
- `0x1800bd5d0`
- `0x1800fc980`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800bcc00`
- `msvcrt!_wcsicmp` at `0x1800bccdc`
- `msvcrt!_wcsicmp` at `0x1800bccfa`
- `msvcrt!_wcsicmp` at `0x1800bcd0e`
- `msvcrt!_wcsicmp` at `0x1800bcd34`
- `msvcrt!_wcsicmp` at `0x1800bcd5a`
- `msvcrt!_wcsicmp` at `0x1800bceb6`
- `msvcrt!_wcsicmp` at `0x1800bcc00`
- `msvcrt!_wcsicmp` at `0x1800bccdc`
- `msvcrt!_wcsicmp` at `0x1800bccfa`
- `msvcrt!_wcsicmp` at `0x1800bcd0e`
- `msvcrt!_wcsicmp` at `0x1800bcd34`
- `msvcrt!_wcsicmp` at `0x1800bcd5a`
- `msvcrt!_wcsicmp` at `0x1800bceb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bce59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bce59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bce8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd00a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bce8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd00a`
- `api-ms-win-core-sysinfo-l1-2-0!SetSystemTime` at `0x1800bcc7b`
- `api-ms-win-core-sysinfo-l1-2-0!SetSystemTime` at `0x1800bcc7b`
- `framedynos!?GetSYSTEMTIME@WBEMTime@@QEBAHPEAU_SYSTEMTIME@@@Z` at `0x1800bcc71`
- `framedynos!?GetSYSTEMTIME@WBEMTime@@QEBAHPEAU_SYSTEMTIME@@@Z` at `0x1800bcc71`
- `framedynos!?IsOk@WBEMTime@@QEBA_NXZ` at `0x1800bcc5f`
- `framedynos!?IsOk@WBEMTime@@QEBA_NXZ` at `0x1800bcc5f`
- `framedynos!?GetDateTime@CInstance@@QEBA_NPEBGAEAVWBEMTime@@@Z` at `0x1800bcc55`
- `framedynos!?GetDateTime@CInstance@@QEBA_NPEBGAEAVWBEMTime@@@Z` at `0x1800bcc55`
- `framedynos!??0WBEMTime@@QEAA@XZ` at `0x1800bcc31`
- `framedynos!??0WBEMTime@@QEAA@XZ` at `0x1800bcc31`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800bcee2`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800bcee2`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bcc96`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bcf45`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bcf95`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bd01f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bd061`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bcc96`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bcf45`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bcf95`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bd01f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800bd061`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800bcf63`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800bcfc6`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800bcf63`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x1800bcfc6`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800bcca6`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x1800bcca6`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800bcc18`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800bceca`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800bcef2`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800bcf1a`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800bcc18`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800bceca`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800bcef2`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x1800bcf1a`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800bcdc5`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800bce2b`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800bcf0a`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800bcf32`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800bcdc5`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800bce2b`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800bcf0a`
- `framedynos!?GetDWORD@CInstance@@QEBA_NPEBGAEAK@Z` at `0x1800bcf32`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800bce78`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800bce78`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800bcd90`
- `framedynos!?GetStatus@CInstance@@QEBA_NPEBGAEA_NAEAG@Z` at `0x1800bcd90`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bd02a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bd039`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bd02a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800bd039`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x1800bd000`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x1800bd000`
- `api-ms-win-core-shutdown-l1-1-0!AbortSystemShutdownW` at `0x1800bce86`
- `api-ms-win-core-shutdown-l1-1-0!AbortSystemShutdownW` at `0x1800bce86`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x1800bcf79`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x1800bcfdc`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x1800bcf79`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x1800bcfdc`

## string_xrefs

- `0x1800bcec0`: `Comment`
- `0x1800bced8`: `Comment`
- `0x1800bcc37`: `SeSystemtimePrivilege`
- `0x1800bccaf`: `SeSystemtimePrivilege`

## pseudocode

```c

```
