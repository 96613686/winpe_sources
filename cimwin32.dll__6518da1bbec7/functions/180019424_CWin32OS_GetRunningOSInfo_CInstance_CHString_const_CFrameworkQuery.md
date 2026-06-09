# CWin32OS::GetRunningOSInfo(CInstance *,CHString const &,CFrameworkQuery *)

- ea: `0x180019424`
- end: `0x18001a292`
- name: `?GetRunningOSInfo@CWin32OS@@AEAAJPEAVCInstance@@AEBVCHString@@PEAVCFrameworkQuery@@@Z`
- size: `3694`
- prototype: `int(CWin32OS *__hidden this, struct CInstance *, const struct CHString *, struct CFrameworkQuery *)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180041570`
- `0x1800415f0`
- `0x1800416b0`

## callees

- `0x1800127e0`
- `0x180014c58`
- `0x180017680`
- `0x180017710`
- `0x180019424`
- `0x18001a298`
- `0x18001a310`
- `0x18001a39c`
- `0x18001a450`
- `0x18001a5c8`
- `0x18001a744`
- `0x180036818`
- `0x18008c0ac`
- `0x18008dc84`
- `0x18008dcb0`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x1800194e3`
- `msvcrt!_wsplitpath_s` at `0x1800194e3`
- `msvcrt!_ui64tow_s` at `0x180019b6b`
- `msvcrt!_ui64tow_s` at `0x180019ba4`
- `msvcrt!_ui64tow_s` at `0x180019c08`
- `msvcrt!_ui64tow_s` at `0x180019c40`
- `msvcrt!_ui64tow_s` at `0x180019c78`
- `msvcrt!_ui64tow_s` at `0x180019cb3`
- `msvcrt!_ui64tow_s` at `0x180019cf5`
- `msvcrt!_ui64tow_s` at `0x180019b6b`
- `msvcrt!_ui64tow_s` at `0x180019ba4`
- `msvcrt!_ui64tow_s` at `0x180019c08`
- `msvcrt!_ui64tow_s` at `0x180019c40`
- `msvcrt!_ui64tow_s` at `0x180019c78`
- `msvcrt!_ui64tow_s` at `0x180019cb3`
- `msvcrt!_ui64tow_s` at `0x180019cf5`
- `ntdll!RtlNtStatusToDosError` at `0x180019521`
- `ntdll!RtlNtStatusToDosError` at `0x180019521`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x18001950a`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x18001950a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180019792`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800198d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180019792`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800198d2`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180019a45`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180019a45`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800194ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180019a5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800194ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180019a5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180019564`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180019564`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180019a9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180019a9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001986d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001986d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a112`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001a039`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001a039`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a04c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a04c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a016`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a016`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180019595`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180019595`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a05c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a05c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800198a6`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180019917`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18001994a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800198a6`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180019917`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18001994a`
- `api-ms-win-core-psapi-l1-1-0!K32GetPerformanceInfo` at `0x1800199c0`
- `api-ms-win-core-psapi-l1-1-0!K32GetPerformanceInfo` at `0x1800199c0`
- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x180019b00`
- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x180019b00`
- `framedynos!?GetLocalOffsetForDate@WBEMTime@@SAJPEBU_SYSTEMTIME@@@Z` at `0x1800198dc`
- `framedynos!?GetLocalOffsetForDate@WBEMTime@@SAJPEBU_SYSTEMTIME@@@Z` at `0x1800198dc`
- `framedynos!??0WBEMTime@@QEAA@AEBU_SYSTEMTIME@@@Z` at `0x1800197a1`
- `framedynos!??0WBEMTime@@QEAA@AEBU_SYSTEMTIME@@@Z` at `0x1800197a1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800196d0`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800197bf`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180019e78`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800196d0`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800197bf`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180019e78`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800195ae`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800195ff`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180019617`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001962f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180019651`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180019669`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800196c7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180019f24`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800195ae`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800195ff`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180019617`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001962f`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180019651`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180019669`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800196c7`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180019f24`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18001976a`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180019adf`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18001976a`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180019adf`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800196f6`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180019709`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a091`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a0aa`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a0c3`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a107`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a13e`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800196f6`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180019709`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a091`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a0aa`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a0c3`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a107`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001a13e`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180019dad`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180019dad`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180019e63`
- `framedynos!?GetMethodContext@CInstance@@QEBAPEAVMethodContext@@XZ` at `0x180019e63`
- `framedynos!?GetInstancesByQuery@CWbemProviderGlue@@SAJPEBGPEAV?$TRefPointerCollection@VCInstance@@@@PEAVMethodContext@@0@Z` at `0x180019e8f`
- `framedynos!?GetInstancesByQuery@CWbemProviderGlue@@SAJPEBGPEAV?$TRefPointerCollection@VCInstance@@@@PEAVMethodContext@@0@Z` at `0x180019e8f`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x180019e6f`
- `framedynos!?GetNamespace@Provider@@IEAAAEBVCHString@@XZ` at `0x180019e6f`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180019464`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180019464`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180019b2c`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18001a0e7`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180019b2c`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18001a0e7`
- `framedynos!?IsPropertyRequired@CFrameworkQuery@@QEAA_NPEBG@Z` at `0x18001997e`
- `framedynos!?IsPropertyRequired@CFrameworkQuery@@QEAA_NPEBG@Z` at `0x18001997e`
- `framedynos!??0CThreadBase@@QEAA@W4THREAD_SAFETY_MECHANISM@0@@Z` at `0x180019e40`
- `framedynos!??0CThreadBase@@QEAA@W4THREAD_SAFETY_MECHANISM@0@@Z` at `0x180019e40`
- `framedynos!??1CThreadBase@@UEAA@XZ` at `0x180019f48`
- `framedynos!??1CThreadBase@@UEAA@XZ` at `0x180019f48`
- `framedynos!??0CHPtrArray@@QEAA@XZ` at `0x180019e56`
- `framedynos!??0CHPtrArray@@QEAA@XZ` at `0x180019e56`
- `framedynos!??1CHPtrArray@@QEAA@XZ` at `0x180019f3d`
- `framedynos!??1CHPtrArray@@QEAA@XZ` at `0x180019f3d`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x180019ea0`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x180019ebb`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x180019f60`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x180019ea0`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x180019ebb`
- `framedynos!?BeginRead@CThreadBase@@QEAAHK@Z` at `0x180019f60`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x180019ecc`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x180019f70`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x180019ecc`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x180019f70`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x180019edc`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x180019f80`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x180019edc`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x180019f80`
- `framedynos!?AddRef@CInstance@@QEAAJXZ` at `0x180019eed`
- `framedynos!?AddRef@CInstance@@QEAAJXZ` at `0x180019f91`
- `framedynos!?AddRef@CInstance@@QEAAJXZ` at `0x180019eed`
- `framedynos!?AddRef@CInstance@@QEAAJXZ` at `0x180019f91`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x180019ef7`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x180019f11`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x180019f9b`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x180019ef7`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x180019f11`
- `framedynos!?EndRead@CThreadBase@@QEAAXXZ` at `0x180019f9b`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x180019fa4`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x180019fa4`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800194fa`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800196e3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019720`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019737`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001974e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019781`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800197d2`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001981b`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019850`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019888`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800198c1`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019932`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019965`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019a05`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019a1c`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019a7a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019b8a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019c27`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019c5f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019c97`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019cd2`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019d14`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001a073`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001a162`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800194fa`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800196e3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019720`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019737`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001974e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019781`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800197d2`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001981b`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019850`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019888`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800198c1`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019932`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019965`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019a05`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019a1c`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019a7a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019b8a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180019c27`

## string_xrefs

- `0x18001973d`: `Win32_ComputerSystem`
- `0x1800195dd`: `ServicePackMinorVersion`
- `0x1800195c5`: `ServicePackMajorVersion`
- `0x18001987e`: `SystemDirectory`
- `0x180019a70`: `WindowsDirectory`
- `0x180019e88`: `SELECT __RELPATH FROM Win32_Process`
- `0x18001a00f`: `R2Brand.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWin32OS::GetRunningOSInfo(
        CWin32OS *this,
        struct CInstance *a2,
        const struct CHString *a3,
        struct CFrameworkQuery *a4)
{
  CWin32OS *v8; // rcx
  unsigned int CipherStrength; // eax
  NTSTATUS v10; // eax
  KUserdata *v11; // rcx
  unsigned int v12; // eax
  KUserdata *v13; // rcx
  unsigned int v14; // eax
  const unsigned __int16 *v15; // rax
  const struct CHString *LocalComputerName; // rax
  const unsigned __int16 *v17; // rax
  int LocalOffsetForDate; // eax
  unsigned int v19; // esi
  CWin32OS *v20; // rcx
  wchar_t *v21; // r8
  CWin32OS *v22; // rcx
  unsigned int v23; // edx
  SIZE_T TotalSize; // rbx
  unsigned __int64 v26; // rbx
  unsigned __int64 v27; // r15
  unsigned __int64 v28; // r14
  unsigned int Size; // eax
  const unsigned __int16 *v30; // rax
  _bstr_t *v31; // rax
  void *v32; // r8
  HRESULT v33; // ebx
  HRESULT v34; // eax
  unsigned int v35; // r15d
  struct MethodContext *MethodContext; // rbx
  const struct CHString *Namespace; // rax
  __int64 v38; // rax
  int v39; // esi
  CInstance *v40; // rbx
  CInstance *v41; // rax
  CInstance *v42; // r14
  CInstance *v43; // rax
  HMODULE Library; // rax
  HMODULE v45; // rbx
  unsigned int LastError; // ebx
  int SystemMetrics; // eax
  size_t DirCount; // [rsp+20h] [rbp-E0h]
  wchar_t *Filename; // [rsp+28h] [rbp-D8h]
  _BYTE v50[4]; // [rsp+50h] [rbp-B0h] BYREF
  LONG rgIndices; // [rsp+54h] [rbp-ACh] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v53[8]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pdwReturnedProductType; // [rsp+68h] [rbp-98h] BYREF
  int v55; // [rsp+70h] [rbp-90h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+78h] [rbp-88h] BYREF
  CInstance *v57; // [rsp+80h] [rbp-80h]
  LONG_PTR lParam[3]; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v60[7]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v61[24]; // [rsp+F8h] [rbp-8h] BYREF
  struct _ENUM_PAGE_FILE_INFORMATION Value; // [rsp+110h] [rbp+10h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+130h] [rbp+30h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+160h] [rbp+60h] BYREF
  struct _SYSTEMTIME v65; // [rsp+170h] [rbp+70h] BYREF
  _PERFORMANCE_INFORMATION pPerformanceInformation; // [rsp+180h] [rbp+80h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v68; // [rsp+304h] [rbp+204h]
  unsigned __int16 v69; // [rsp+306h] [rbp+206h]
  unsigned __int16 v70; // [rsp+308h] [rbp+208h]
  unsigned __int8 v71; // [rsp+30Ah] [rbp+20Ah]
  _MEMORYSTATUSEX v72; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v73[608]; // [rsp+350h] [rbp+250h] BYREF
  wchar_t v74[8]; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int128 v75; // [rsp+5C0h] [rbp+4C0h]
  __int16 v76; // [rsp+5D0h] [rbp+4D0h]
  wchar_t Drive[8]; // [rsp+600h] [rbp+500h] BYREF
  WCHAR LCData[264]; // [rsp+610h] [rbp+510h] BYREF
  unsigned __int16 v79[264]; // [rsp+820h] [rbp+720h] BYREF
  WCHAR Buffer[264]; // [rsp+A30h] [rbp+930h] BYREF

  CRegistry::CRegistry((CRegistry *)v73);
  memset_0(v74, 0, 0x44u);
  CipherStrength = CWin32OS::GetCipherStrength(v8);
  if ( CipherStrength )
    CInstance::SetWORD(a2, L"EncryptionLevel", CipherStrength);
  if ( GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    _wsplitpath_s(Buffer, Drive, 3u, 0, 0, 0, 0, 0, 0);
    CInstance::SetCharSplat(a2, L"SystemDrive", Drive);
  }
  v50[0] = 0;
  v10 = RtlCheckPortableOperatingSystem(v50);
  if ( v10 == -1073741275 )
  {
    v10 = 0;
    v50[0] = 0;
  }
  if ( !RtlNtStatusToDosError(v10) )
    CInstance::Setbool(a2, L"PortableOperatingSystem", v50[0] != 0);
  if ( (unsigned __int8)IsGetSystemMetricsPresent() && GetSystemMetrics(89) )
  {
    if ( !CWin32OS::m_wszOtherTypeDescriptionValue )
    {
      CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, &CWin32OS::m_csOtherTypeDescription);
      if ( !CWin32OS::m_wszOtherTypeDescriptionValue )
      {
        Library = LoadLibraryExW(L"R2Brand.dll", 0, 2u);
        v45 = Library;
        if ( Library )
        {
          if ( !LoadStringW(Library, 0x44Eu, &CWin32OS::m_wszOtherTypeDescriptionValue, 256) )
            GetLastError();
          FreeLibrary(v45);
        }
      }
      LeaveCriticalSection(lpCriticalSection);
    }
    CInstance::SetCharSplat(a2, L"OtherTypeDescription", &CWin32OS::m_wszOtherTypeDescriptionValue);
  }
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  GetVersionExW(&VersionInformation);
  pdwReturnedProductType = 0;
  if ( GetProductInfo(
         VersionInformation.dwMajorVersion,
         VersionInformation.dwMinorVersion,
         v68,
         v69,
         &pdwReturnedProductType) )
  {
    CInstance::SetDWORD(a2, L"OperatingSystemSKU", pdwReturnedProductType);
  }
  if ( VersionInformation.dwOSVersionInfoSize == 284 )
  {
    CInstance::SetWORD(a2, L"ServicePackMajorVersion", v68);
    CInstance::SetWORD(a2, L"ServicePackMinorVersion", v69);
    CInstance::SetDWORD(a2, L"ProductType", v71);
    CInstance::SetDWORD(a2, L"SuiteMask", v70);
    CInstance::SetDWORD(a2, L"OSProductSuite", v70);
  }
  if ( MEMORY[0x7FFE0268] )
  {
    v12 = KUserdata::NtProductType(v11);
    CInstance::SetDWORD(a2, L"ProductType", v12);
    v14 = KUserdata::SuiteMask(v13);
    CInstance::SetDWORD(a2, L"SuiteMask", v14);
  }
  rgIndices = 0;
  v55 = 0;
  LODWORD(lpCriticalSection) = 0;
  if ( (unsigned int)CWin32OS::GetNoExecuteProtection(v11, &rgIndices, &v55, (int *)&lpCriticalSection) )
  {
    CInstance::Setbool(a2, L"DataExecutionPrevention_Available", rgIndices != 0);
    CInstance::Setbool(a2, L"DataExecutionPrevention_32BitApplications", v55 != 0);
    CInstance::Setbool(a2, L"DataExecutionPrevention_Drivers", (_DWORD)lpCriticalSection != 0);
  }
  CInstance::SetByte(a2, L"DataExecutionPrevention_SupportPolicy", MEMORY[0x7FFE02D5] & 3);
  CInstance::SetDWORD(a2, L"MaxNumberOfProcesses", 0xFFFFFFFF);
  v15 = (const unsigned __int16 *)CHString::operator unsigned short const *(a3);
  CInstance::SetCharSplat(a2, L"Caption", v15);
  CInstance::Setbool(a2, L"Distributed", 0);
  CInstance::Setbool(a2, L"Primary", 1);
  CInstance::SetCharSplat(a2, L"Manufacturer", L"Microsoft Corporation");
  CInstance::SetCharSplat(a2, L"CreationClassName", L"Win32_OperatingSystem");
  CInstance::SetCharSplat(a2, L"CSCreationClassName", L"Win32_ComputerSystem");
  LocalComputerName = Provider::GetLocalComputerName(this);
  CInstance::SetCHString(a2, L"CSName", LocalComputerName);
  CInstance::SetCharSplat(a2, L"Status", L"OK");
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  WBEMTime::WBEMTime((WBEMTime *)&lpCriticalSection, &SystemTime);
  CInstance::SetDateTime(a2, L"LocalDateTime", (const struct WBEMTime *)&lpCriticalSection);
  v17 = (const unsigned __int16 *)CHString::operator unsigned short const *(a3);
  CInstance::SetCharSplat(a2, L"Description", v17);
  LODWORD(Filename) = LOWORD(VersionInformation.dwBuildNumber);
  LODWORD(DirCount) = VersionInformation.dwMinorVersion;
  StringCchPrintfW(v79, 0x104u, L"%d.%d.%hu", VersionInformation.dwMajorVersion, DirCount, Filename);
  CInstance::SetCharSplat(a2, L"Version", v79);
  StringCchPrintfW(v79, 0x104u, L"%hu", LOWORD(VersionInformation.dwBuildNumber));
  CInstance::SetCharSplat(a2, L"BuildNumber", v79);
  if ( VersionInformation.szCSDVersion[0] )
    CInstance::SetCharSplat(a2, L"CSDVersion", VersionInformation.szCSDVersion);
  if ( GetSystemDirectoryW(LCData, 0x104u) )
    CInstance::SetCharSplat(a2, L"SystemDirectory", LCData);
  if ( GetLocaleInfoW(0x800u, 1u, LCData, 260) )
    CInstance::SetCharSplat(a2, L"Locale", LCData);
  v65 = 0;
  GetSystemTime(&v65);
  LocalOffsetForDate = WBEMTime::GetLocalOffsetForDate(&v65);
  if ( LocalOffsetForDate == -1 )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    CRegistry::~CRegistry((CRegistry *)v73);
    return LastError;
  }
  LOWORD(rgIndices) = LocalOffsetForDate;
  CInstance::SetWBEMINT16(a2, L"CurrentTimeZone", (const __int16 *)&rgIndices);
  if ( GetLocaleInfoW(0x800u, 5u, LCData, 260) )
    CInstance::SetCharSplat(a2, L"CountryCode", LCData);
  if ( GetLocaleInfoW(0x800u, 0x1004u, LCData, 260) )
    CInstance::SetCharSplat(a2, L"CodeSet", LCData);
  if ( !a4 || CFrameworkQuery::IsPropertyRequired(a4, L"NumberOfProcesses") )
  {
    CThreadBase::CThreadBase(v60, 0);
    v60[0] = &TRefPointerCollection<CInstance>::`vftable';
    CHPtrArray::CHPtrArray((CHPtrArray *)v61);
    v35 = 0;
    MethodContext = CInstance::GetMethodContext(a2);
    Namespace = Provider::GetNamespace(this);
    v38 = CHString::operator unsigned short const *(Namespace);
    if ( (int)CWbemProviderGlue::GetInstancesByQuery(L"SELECT __RELPATH FROM Win32_Process", v60, MethodContext, v38) >= 0 )
    {
      if ( CThreadBase::BeginRead((CThreadBase *)v60, 0xFFFFFFFF) )
      {
        v39 = -1;
        v57 = 0;
        v40 = 0;
        if ( CThreadBase::BeginRead((CThreadBase *)v60, 0xFFFFFFFF) )
        {
          v39 = 0;
          if ( CHPtrArray::GetSize((CHPtrArray *)v61) )
          {
            v41 = (CInstance *)CHPtrArray::GetAt((CHPtrArray *)v61, 0);
            v40 = v41;
            if ( v41 )
              CInstance::AddRef(v41);
          }
          CThreadBase::EndRead((CThreadBase *)v60);
        }
        while ( 1 )
        {
          v57 = v40;
          if ( !v40 )
            break;
          ++v35;
          v42 = 0;
          if ( CThreadBase::BeginRead((CThreadBase *)v60, 0xFFFFFFFF) )
          {
            if ( (unsigned int)++v39 < CHPtrArray::GetSize((CHPtrArray *)v61) )
            {
              v43 = (CInstance *)CHPtrArray::GetAt((CHPtrArray *)v61, v39);
              v42 = v43;
              if ( v43 )
                CInstance::AddRef(v43);
            }
            CThreadBase::EndRead((CThreadBase *)v60);
          }
          CInstance::Release(v40);
          v40 = v42;
        }
      }
      CThreadBase::EndRead((CThreadBase *)v60);
    }
    CInstance::SetDWORD(a2, L"NumberOfProcesses", v35);
    v60[0] = &TRefPointerCollection<CInstance>::`vftable';
    TRefPointerCollection<CInstance>::Empty(v60);
    CHPtrArray::~CHPtrArray((CHPtrArray *)v61);
    CThreadBase::~CThreadBase((CThreadBase *)v60);
  }
  v19 = 0;
  if ( (unsigned __int8)IsGetSystemMetricsPresent() )
  {
    SystemMetrics = GetSystemMetrics(22);
    CInstance::Setbool(a2, L"Debug", SystemMetrics != 0);
  }
  memset_0(&pPerformanceInformation.cb + 1, 0, 0x64u);
  pPerformanceInformation.cb = 104;
  if ( K32GetPerformanceInfo(&pPerformanceInformation, 0x68u) )
  {
    v26 = (pPerformanceInformation.PageSize >> 10)
        * (pPerformanceInformation.CommitLimit - pPerformanceInformation.CommitTotal);
    v27 = (pPerformanceInformation.PageSize >> 10) * pPerformanceInformation.PhysicalTotal;
    v28 = (pPerformanceInformation.PageSize >> 10) * pPerformanceInformation.PhysicalAvailable;
    if ( _ui64tow_s((pPerformanceInformation.PageSize >> 10) * pPerformanceInformation.CommitLimit, v74, 0x22u, 10) )
    {
      *(_OWORD *)v74 = 0;
      v75 = 0;
      v76 = 0;
    }
    CInstance::SetCharSplat(a2, L"TotalVirtualMemorySize", v74);
    if ( _ui64tow_s(v26, v74, 0x22u, 10) )
    {
      *(_OWORD *)v74 = 0;
      v75 = 0;
      v76 = 0;
    }
    CInstance::SetCharSplat(a2, L"FreeVirtualMemory", v74);
    if ( _ui64tow_s(v28, v74, 0x22u, 10) )
    {
      *(_OWORD *)v74 = 0;
      v75 = 0;
      v76 = 0;
    }
    CInstance::SetCharSplat(a2, L"FreePhysicalMemory", v74);
    if ( _ui64tow_s(v27, v74, 0x22u, 10) )
    {
      *(_OWORD *)v74 = 0;
      v75 = 0;
      v76 = 0;
    }
    CInstance::SetCharSplat(a2, L"TotalVisibleMemorySize", v74);
  }
  memset(&Value, 0, sizeof(Value));
  if ( CWin32OS::GetPageFileTotalSizes(v20, &Value) )
  {
    TotalSize = Value.TotalSize;
    if ( _ui64tow_s(Value.TotalSize, v74, 0x22u, 10) )
    {
      *(_OWORD *)v74 = 0;
      v75 = 0;
      v76 = 0;
    }
    CInstance::SetCharSplat(a2, L"SizeStoredInPagingFiles", v74);
    if ( _ui64tow_s(TotalSize - Value.TotalInUse, v74, 0x22u, 10) )
    {
      *(_OWORD *)v74 = 0;
      v75 = 0;
      v76 = 0;
    }
    v21 = v74;
  }
  else
  {
    CInstance::SetCharSplat(a2, L"SizeStoredInPagingFiles", L"0");
    v21 = L"0";
  }
  CInstance::SetCharSplat(a2, L"FreeSpaceInPagingFiles", v21);
  memset_0(&v72, 0, sizeof(v72));
  v72.dwLength = 64;
  if ( GlobalMemoryStatusEx(&v72) )
  {
    if ( _ui64tow_s(v72.ullTotalVirtual >> 10, v74, 0x22u, 10) )
    {
      *(_OWORD *)v74 = 0;
      v75 = 0;
      v76 = 0;
    }
    CInstance::SetCharSplat(a2, L"MaxProcessMemorySize", v74);
  }
  if ( GetWindowsDirectoryW(LCData, 0x104u) )
    CInstance::SetCharSplat(a2, L"WindowsDirectory", LCData);
  CWin32OS::GetNTInfo(v22, a2);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  CHString::CHString((CHString *)v53, "Unknown");
  switch ( SystemInfo.wProcessorArchitecture )
  {
    case 0u:
      goto LABEL_40;
    case 6u:
      v23 = 221;
      goto LABEL_41;
    case 9u:
      v23 = 220;
      goto LABEL_41;
    case 5u:
LABEL_40:
      v23 = 219;
LABEL_41:
      LoadStringW((struct CHString *)v53, v23);
      break;
    case 0xCu:
      v23 = 223;
      goto LABEL_41;
  }
  CInstance::SetCHString(a2, L"OSArchitecture", (const struct CHString *)v53);
  CHStringArray::CHStringArray((CHStringArray *)lParam);
  if ( EnumUILanguagesW(EnumUILanguagesProc, 0x18u, (LONG_PTR)lParam)
    && (int)CHStringArray::GetSize((CHStringArray *)lParam) > 0 )
  {
    rgsabound = 0;
    VariantInit(&pvarg);
    rgsabound.lLbound = 0;
    rgsabound.cElements = CHStringArray::GetSize((CHStringArray *)lParam);
    pvarg.llVal = (LONGLONG)SafeArrayCreate(8u, 1u, &rgsabound);
    if ( pvarg.llVal )
    {
      pvarg.vt = 8200;
      for ( rgIndices = 0; ; ++rgIndices )
      {
        Size = CHStringArray::GetSize((CHStringArray *)lParam);
        if ( rgIndices >= Size )
        {
          CInstance::SetVariant(a2, L"MUILanguages", &pvarg);
          goto LABEL_70;
        }
        CHStringArray::GetAt(lParam, &lpCriticalSection, (unsigned int)rgIndices);
        v30 = CHString::GetBuffer((CHString *)&lpCriticalSection, 0);
        v31 = _bstr_t::_bstr_t((_bstr_t *)&v55, v30);
        v32 = *(_QWORD *)v31 ? **(void ***)v31 : 0LL;
        v33 = SafeArrayPutElement(pvarg.parray, &rgIndices, v32);
        _bstr_t::_Free((_bstr_t *)&v55);
        if ( v33 == -2147024882 )
          break;
        CHString::~CHString((CHString *)&lpCriticalSection);
      }
      v19 = -2147217402;
      CHString::~CHString((CHString *)&lpCriticalSection);
    }
    else
    {
      v19 = -2147217402;
    }
LABEL_70:
    v34 = VariantClear(&pvarg);
    if ( v34 < 0 )
      _com_issue_error(v34);
  }
  CHStringArray::~CHStringArray((CHStringArray *)lParam);
  CHString::~CHString((CHString *)v53);
  CRegistry::~CRegistry((CRegistry *)v73);
  return v19;
}

```

## disassembly

```asm
0x180019424  push    rbp
0x180019426  push    rbx
0x180019427  push    rsi
0x180019428  push    rdi
0x180019429  push    r12
0x18001942b  push    r13
0x18001942d  push    r14
0x18001942f  push    r15
0x180019431  lea     rbp, [rsp-0B58h]
0x180019439  sub     rsp, 0C58h
0x180019440  mov     rax, cs:__security_cookie
0x180019447  xor     rax, rsp
0x18001944a  mov     [rbp+0B90h+var_50], rax
0x180019451  mov     rsi, r9
0x180019454  mov     r15, r8
0x180019457  mov     rdi, rdx
0x18001945a  mov     r14, rcx
0x18001945d  lea     rcx, [rbp+0B90h+var_940]
0x180019464  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18001946a  nop
0x18001946b  xor     edx, edx; Val
0x18001946d  lea     r8d, [rdx+44h]; Size
0x180019471  lea     rcx, [rbp+0B90h+var_6E0]; void *
0x180019478  call    memset_0
0x18001947d  call    ?GetCipherStrength@CWin32OS@@AEAAKXZ; CWin32OS::GetCipherStrength(void)
0x180019482  xor     r12d, r12d
0x180019485  test    eax, eax
0x180019487  jz      short loc_18001949D
0x180019489  movzx   r8d, ax
0x18001948d  lea     rdx, aEncryptionleve; "EncryptionLevel"
0x180019494  mov     rcx, rdi
0x180019497  call    cs:__imp_?SetWORD@CInstance@@QEAA_NPEBGG@Z; CInstance::SetWORD(ushort const *,ushort)
0x18001949d  mov     ebx, 104h
0x1800194a2  mov     edx, ebx; uSize
0x1800194a4  lea     rcx, [rbp+0B90h+Buffer]; lpBuffer
0x1800194ab  call    cs:__imp_GetWindowsDirectoryW
0x1800194b1  test    eax, eax
0x1800194b3  jz      short loc_180019500
0x1800194b5  mov     [rsp+0C90h+ExtCount], r12; ExtCount
0x1800194ba  mov     [rsp+0C90h+Ext], r12; Ext
0x1800194bf  mov     [rsp+0C90h+FilenameCount], r12; FilenameCount
0x1800194c4  mov     [rsp+0C90h+Filename], r12; Filename
0x1800194c9  mov     [rsp+0C90h+DirCount], r12; DirCount
0x1800194ce  xor     r9d, r9d; Dir
0x1800194d1  lea     r8d, [r9+3]; DriveCount
0x1800194d5  lea     rdx, [rbp+0B90h+Drive]; Drive
0x1800194dc  lea     rcx, [rbp+0B90h+Buffer]; FullPath
0x1800194e3  call    cs:__imp__wsplitpath_s
0x1800194e9  lea     r8, [rbp+0B90h+Drive]
0x1800194f0  lea     rdx, aSystemdrive; "SystemDrive"
0x1800194f7  mov     rcx, rdi
0x1800194fa  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180019500  mov     [rsp+0C90h+var_C40], r12b
0x180019505  lea     rcx, [rsp+0C90h+var_C40]
0x18001950a  call    cs:__imp_RtlCheckPortableOperatingSystem
0x180019510  cmp     eax, 0C0000225h
0x180019515  jnz     short loc_18001951F
0x180019517  mov     eax, r12d
0x18001951a  mov     [rsp+0C90h+var_C40], r12b
0x18001951f  mov     ecx, eax; Status
0x180019521  call    cs:__imp_RtlNtStatusToDosError
0x180019527  test    eax, eax
0x180019529  jz      loc_18001A0F4
0x18001952f  call    IsGetSystemMetricsPresent
0x180019534  test    al, al
0x180019536  jnz     loc_180019FD0
0x18001953c  xor     edx, edx; Val
0x18001953e  mov     r8d, 118h; Size
0x180019544  lea     rcx, [rbp+0B90h+VersionInformation.dwMajorVersion]; void *
0x18001954b  call    memset_0
0x180019550  mov     r13d, 11Ch
0x180019556  mov     [rbp+0B90h+VersionInformation.dwOSVersionInfoSize], r13d
0x18001955d  lea     rcx, [rbp+0B90h+VersionInformation]; lpVersionInformation
0x180019564  call    cs:__imp_GetVersionExW
0x18001956a  mov     [rsp+0C90h+pdwReturnedProductType], r12d
0x18001956f  movzx   r9d, [rbp+0B90h+var_98A]; dwSpMinorVersion
0x180019577  movzx   r8d, [rbp+0B90h+var_98C]; dwSpMajorVersion
0x18001957f  lea     rax, [rsp+0C90h+pdwReturnedProductType]
0x180019584  mov     [rsp+0C90h+DirCount], rax; pdwReturnedProductType
0x180019589  mov     edx, [rbp+0B90h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x18001958f  mov     ecx, [rbp+0B90h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x180019595  call    cs:__imp_GetProductInfo
0x18001959b  test    eax, eax
0x18001959d  jz      short loc_1800195B4
0x18001959f  mov     r8d, [rsp+0C90h+pdwReturnedProductType]
0x1800195a4  lea     rdx, aOperatingsyste; "OperatingSystemSKU"
0x1800195ab  mov     rcx, rdi
0x1800195ae  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800195b4  cmp     [rbp+0B90h+VersionInformation.dwOSVersionInfoSize], r13d
0x1800195bb  jnz     short loc_180019635
0x1800195bd  movzx   r8d, [rbp+0B90h+var_98C]
0x1800195c5  lea     rdx, aServicepackmaj; "ServicePackMajorVersion"
0x1800195cc  mov     rcx, rdi
0x1800195cf  call    cs:__imp_?SetWORD@CInstance@@QEAA_NPEBGG@Z; CInstance::SetWORD(ushort const *,ushort)
0x1800195d5  movzx   r8d, [rbp+0B90h+var_98A]
0x1800195dd  lea     rdx, aServicepackmin; "ServicePackMinorVersion"
0x1800195e4  mov     rcx, rdi
0x1800195e7  call    cs:__imp_?SetWORD@CInstance@@QEAA_NPEBGG@Z; CInstance::SetWORD(ushort const *,ushort)
0x1800195ed  movzx   r8d, [rbp+0B90h+var_986]
0x1800195f5  lea     rdx, aProducttype; "ProductType"
0x1800195fc  mov     rcx, rdi
0x1800195ff  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180019605  movzx   r8d, [rbp+0B90h+var_988]
0x18001960d  lea     rdx, aSuitemask; "SuiteMask"
0x180019614  mov     rcx, rdi
0x180019617  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18001961d  movzx   r8d, [rbp+0B90h+var_988]
0x180019625  lea     rdx, aOsproductsuite; "OSProductSuite"
0x18001962c  mov     rcx, rdi
0x18001962f  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180019635  cmp     ds:7FFE0268h, r12b
0x18001963d  jz      short loc_18001966F
0x18001963f  call    ?NtProductType@KUserdata@@QEAAKXZ; KUserdata::NtProductType(void)
0x180019644  mov     r8d, eax
0x180019647  lea     rdx, aProducttype; "ProductType"
0x18001964e  mov     rcx, rdi
0x180019651  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180019657  call    ?SuiteMask@KUserdata@@QEAAKXZ; KUserdata::SuiteMask(void)
0x18001965c  mov     r8d, eax
0x18001965f  lea     rdx, aSuitemask; "SuiteMask"
0x180019666  mov     rcx, rdi
0x180019669  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18001966f  mov     [rsp+0C90h+rgIndices], r12d
0x180019674  mov     [rsp+0C90h+var_C20], r12d
0x180019679  mov     dword ptr [rsp+0C90h+lpCriticalSection], r12d
0x18001967e  lea     r9, [rsp+0C90h+lpCriticalSection]; int *
0x180019683  lea     r8, [rsp+0C90h+var_C20]; int *
0x180019688  lea     rdx, [rsp+0C90h+rgIndices]; int *
0x18001968d  call    ?GetNoExecuteProtection@CWin32OS@@AEAAHAEAH00@Z; CWin32OS::GetNoExecuteProtection(int &,int &,int &)
0x180019692  test    eax, eax
0x180019694  jnz     loc_18001A07E
0x18001969a  mov     r8b, ds:7FFE02D5h
0x1800196a2  and     r8b, 3
0x1800196a6  lea     rdx, aDataexecutionp_1; "DataExecutionPrevention_SupportPolicy"
0x1800196ad  mov     rcx, rdi
0x1800196b0  call    cs:__imp_?SetByte@CInstance@@QEAA_NPEBGE@Z; CInstance::SetByte(ushort const *,uchar)
0x1800196b6  or      r13d, 0FFFFFFFFh
0x1800196ba  mov     r8d, r13d
0x1800196bd  lea     rdx, aMaxnumberofpro; "MaxNumberOfProcesses"
0x1800196c4  mov     rcx, rdi
0x1800196c7  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800196cd  mov     rcx, r15
0x1800196d0  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800196d6  mov     r8, rax
0x1800196d9  lea     rdx, aCaption; "Caption"
0x1800196e0  mov     rcx, rdi
0x1800196e3  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800196e9  xor     r8d, r8d
0x1800196ec  lea     rdx, aDistributed; "Distributed"
0x1800196f3  mov     rcx, rdi
0x1800196f6  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800196fc  mov     r8b, 1
0x1800196ff  lea     rdx, aPrimary; "Primary"
0x180019706  mov     rcx, rdi
0x180019709  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18001970f  lea     r8, aMicrosoftCorpo; "Microsoft Corporation"
0x180019716  lea     rdx, aManufacturer; "Manufacturer"
0x18001971d  mov     rcx, rdi
0x180019720  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180019726  lea     r8, aWin32Operating_0; "Win32_OperatingSystem"
0x18001972d  lea     rdx, aCreationclassn; "CreationClassName"
0x180019734  mov     rcx, rdi
0x180019737  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18001973d  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x180019744  lea     rdx, aCscreationclas; "CSCreationClassName"
0x18001974b  mov     rcx, rdi
0x18001974e  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180019754  mov     rcx, r14
0x180019757  call    cs:__imp_?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ; Provider::GetLocalComputerName(void)
0x18001975d  mov     r8, rax
0x180019760  lea     rdx, aCsname; "CSName"
0x180019767  mov     rcx, rdi
0x18001976a  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180019770  lea     r8, aOk; "OK"
0x180019777  lea     rdx, aStatus; "Status"
0x18001977e  mov     rcx, rdi
0x180019781  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180019787  xorps   xmm0, xmm0
0x18001978a  movups  xmmword ptr [rbp+0B90h+SystemTime.wYear], xmm0
0x18001978e  lea     rcx, [rbp+0B90h+SystemTime]; lpSystemTime
0x180019792  call    cs:__imp_GetSystemTime
0x180019798  lea     rdx, [rbp+0B90h+SystemTime]
0x18001979c  lea     rcx, [rsp+0C90h+lpCriticalSection]
0x1800197a1  call    cs:__imp_??0WBEMTime@@QEAA@AEBU_SYSTEMTIME@@@Z; WBEMTime::WBEMTime(_SYSTEMTIME const &)
0x1800197a7  lea     r8, [rsp+0C90h+lpCriticalSection]
0x1800197ac  lea     rdx, aLocaldatetime; "LocalDateTime"
0x1800197b3  mov     rcx, rdi
0x1800197b6  call    cs:__imp_?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z; CInstance::SetDateTime(ushort const *,WBEMTime const &)
0x1800197bc  mov     rcx, r15
0x1800197bf  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800197c5  mov     r8, rax
0x1800197c8  lea     rdx, aDescription; "Description"
0x1800197cf  mov     rcx, rdi
0x1800197d2  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800197d8  movzx   eax, word ptr [rbp+0B90h+VersionInformation.dwBuildNumber]
0x1800197df  mov     dword ptr [rsp+0C90h+Filename], eax
0x1800197e3  mov     eax, [rbp+0B90h+VersionInformation.dwMinorVersion]
0x1800197e9  mov     dword ptr [rsp+0C90h+DirCount], eax
0x1800197ed  mov     r9d, [rbp+0B90h+VersionInformation.dwMajorVersion]
0x1800197f4  lea     r8, aDDHu; "%d.%d.%hu"
0x1800197fb  mov     rdx, rbx; unsigned __int64
0x1800197fe  lea     rcx, [rbp+0B90h+var_470]; unsigned __int16 *
0x180019805  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001980a  lea     r8, [rbp+0B90h+var_470]
0x180019811  lea     rdx, aVersion; "Version"
0x180019818  mov     rcx, rdi
0x18001981b  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180019821  movzx   r9d, word ptr [rbp+0B90h+VersionInformation.dwBuildNumber]
0x180019829  lea     r8, aHu; "%hu"
0x180019830  mov     rdx, rbx; unsigned __int64
0x180019833  lea     rcx, [rbp+0B90h+var_470]; unsigned __int16 *
0x18001983a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001983f  lea     r8, [rbp+0B90h+var_470]
0x180019846  lea     rdx, aBuildnumber; "BuildNumber"
0x18001984d  mov     rcx, rdi
0x180019850  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180019856  cmp     [rbp+0B90h+VersionInformation.szCSDVersion], r12w
0x18001985e  jnz     loc_18001A151
0x180019864  mov     edx, ebx; uSize
0x180019866  lea     rcx, [rbp+0B90h+LCData]; lpBuffer
0x18001986d  call    cs:__imp_GetSystemDirectoryW
0x180019873  test    eax, eax
0x180019875  jz      short loc_18001988E
0x180019877  lea     r8, [rbp+0B90h+LCData]
0x18001987e  lea     rdx, aSystemdirector; "SystemDirectory"
0x180019885  mov     rcx, rdi
0x180019888  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18001988e  mov     r9d, ebx; cchData
0x180019891  lea     r8, [rbp+0B90h+LCData]; lpLCData
0x180019898  mov     edx, 1; LCType
0x18001989d  mov     r15d, 800h
0x1800198a3  mov     ecx, r15d; Locale
0x1800198a6  call    cs:__imp_GetLocaleInfoW
0x1800198ac  test    eax, eax
0x1800198ae  jz      short loc_1800198C7
0x1800198b0  lea     r8, [rbp+0B90h+LCData]
0x1800198b7  lea     rdx, aLocale; "Locale"
0x1800198be  mov     rcx, rdi
0x1800198c1  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800198c7  xorps   xmm0, xmm0
0x1800198ca  movups  xmmword ptr [rbp+0B90h+var_B20.wYear], xmm0
0x1800198ce  lea     rcx, [rbp+0B90h+var_B20]; lpSystemTime
0x1800198d2  call    cs:__imp_GetSystemTime
0x1800198d8  lea     rcx, [rbp+0B90h+var_B20]
0x1800198dc  call    cs:__imp_?GetLocalOffsetForDate@WBEMTime@@SAJPEBU_SYSTEMTIME@@@Z; WBEMTime::GetLocalOffsetForDate(_SYSTEMTIME const *)
0x1800198e2  cmp     eax, r13d
0x1800198e5  jz      loc_18001A0CE
0x1800198eb  mov     word ptr [rsp+0C90h+rgIndices], ax
0x1800198f0  lea     r8, [rsp+0C90h+rgIndices]
0x1800198f5  lea     rdx, aCurrenttimezon; "CurrentTimeZone"
0x1800198fc  mov     rcx, rdi
0x1800198ff  call    cs:__imp_?SetWBEMINT16@CInstance@@QEAA_NPEBGAEBF@Z; CInstance::SetWBEMINT16(ushort const *,short const &)
0x180019905  mov     r9d, ebx; cchData
0x180019908  lea     r8, [rbp+0B90h+LCData]; lpLCData
0x18001990f  mov     edx, 5; LCType
0x180019914  mov     ecx, r15d; Locale
0x180019917  call    cs:__imp_GetLocaleInfoW
0x18001991d  test    eax, eax
0x18001991f  jz      short loc_180019938
0x180019921  lea     r8, [rbp+0B90h+LCData]
0x180019928  lea     rdx, aCountrycode; "CountryCode"
0x18001992f  mov     rcx, rdi
0x180019932  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180019938  mov     r9d, ebx; cchData
0x18001993b  lea     r8, [rbp+0B90h+LCData]; lpLCData
0x180019942  mov     edx, 1004h; LCType
0x180019947  mov     ecx, r15d; Locale
0x18001994a  call    cs:__imp_GetLocaleInfoW
0x180019950  test    eax, eax
0x180019952  jz      short loc_18001996B
0x180019954  lea     r8, [rbp+0B90h+LCData]
0x18001995b  lea     rdx, aCodeset; "CodeSet"
0x180019962  mov     rcx, rdi
0x180019965  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18001996b  test    rsi, rsi
0x18001996e  jz      loc_180019E3A
0x180019974  lea     rdx, aNumberofproces; "NumberOfProcesses"
0x18001997b  mov     rcx, rsi
0x18001997e  call    cs:__imp_?IsPropertyRequired@CFrameworkQuery@@QEAA_NPEBG@Z; CFrameworkQuery::IsPropertyRequired(ushort const *)
0x180019984  test    al, al
0x180019986  jnz     loc_180019E3A
0x18001998c  mov     esi, r12d
0x18001998f  call    IsGetSystemMetricsPresent
0x180019994  test    al, al
0x180019996  jnz     loc_18001A123
0x18001999c  xor     edx, edx; Val
0x18001999e  lea     r8d, [rdx+64h]; Size
0x1800199a2  lea     rcx, [rbp+0B90h+pPerformanceInformation+4]; void *
0x1800199a9  call    memset_0
0x1800199ae  mov     edx, 68h ; 'h'; cb
0x1800199b3  mov     [rbp+0B90h+pPerformanceInformation.cb], edx
0x1800199b9  lea     rcx, [rbp+0B90h+pPerformanceInformation]; pPerformanceInformation
0x1800199c0  call    cs:__imp_K32GetPerformanceInfo
0x1800199c6  mov     r13d, 0Ah
0x1800199cc  lea     r14d, [r13+18h]
0x1800199d0  test    eax, eax
0x1800199d2  jnz     loc_180019BBE
0x1800199d8  xorps   xmm0, xmm0
0x1800199db  movups  xmmword ptr [rbp+0B90h+Value], xmm0
0x1800199df  movups  [rbp+0B90h+var_B70], xmm0
  ... truncated ...
```
