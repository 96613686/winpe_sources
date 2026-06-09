# CImplement_LogicalFile::LoadPropertyValuesNT(CInstance *,ushort const *,ushort const *,ushort const *,_WIN32_FIND_DATAW *,ulong,void const *)

- ea: `0x180070cd0`
- end: `0x180071932`
- name: `?LoadPropertyValuesNT@CImplement_LogicalFile@@MEAAJPEAVCInstance@@PEBG11PEAU_WIN32_FIND_DATAW@@KPEBX@Z`
- size: `3170`
- prototype: `__int64 __fastcall(CImplement_LogicalFile *__hidden this, struct CInstance *, const unsigned __int16 *, const unsigned __int16 *, wchar_t *String1, struct _WIN32_FIND_DATAW *, unsigned int, const void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000fad8`
- `0x1800127e0`
- `0x180016900`
- `0x180017680`
- `0x18002ea18`
- `0x180031800`
- `0x180064ab4`
- `0x180070cd0`
- `0x1800fc902`
- `0x1800fc980`
- `0x1800fca40`
- `0x180110010`

## import_xrefs

- `msvcrt!_i64tow_s` at `0x1800718bc`
- `msvcrt!_i64tow_s` at `0x1800718bc`
- `msvcrt!wcsrchr` at `0x180071059`
- `msvcrt!wcsrchr` at `0x18007130b`
- `msvcrt!wcsrchr` at `0x180071059`
- `msvcrt!wcsrchr` at `0x18007130b`
- `msvcrt!_wcslwr` at `0x180070d5d`
- `msvcrt!_wcslwr` at `0x180070d6a`
- `msvcrt!_wcslwr` at `0x180071000`
- `msvcrt!_wcslwr` at `0x180070d5d`
- `msvcrt!_wcslwr` at `0x180070d6a`
- `msvcrt!_wcslwr` at `0x180071000`
- `msvcrt!_wcsicmp` at `0x18007147a`
- `msvcrt!_wcsicmp` at `0x18007178d`
- `msvcrt!_wcsicmp` at `0x1800717a5`
- `msvcrt!_wcsicmp` at `0x18007147a`
- `msvcrt!_wcsicmp` at `0x18007178d`
- `msvcrt!_wcsicmp` at `0x1800717a5`
- `ntdll!NtQueryInformationFile` at `0x18007181b`
- `ntdll!NtQueryInformationFile` at `0x18007181b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007182c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007182c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070ed5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800717e2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070ed5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800717e2`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800710f5`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800710f5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180070d90`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180070e11`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800710c6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180071122`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18007112e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180071202`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180070d90`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180070e11`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800710c6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180071122`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18007112e`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180071202`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180070e27`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x180070e27`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180071844`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180071865`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180071844`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180071865`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180070f97`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180070f97`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180070f52`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180071077`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18007138a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800713cc`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18007140b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180071425`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180071440`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180070f52`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180071077`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18007138a`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800713cc`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18007140b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180071425`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180071440`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180071228`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180071228`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x180070e32`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x180070e32`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x18007114d`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x18007116b`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x1800711da`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x18007114d`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x18007116b`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x1800711da`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800710ba`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800711bb`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800710ba`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800711bb`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18007123f`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18007129d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18007123f`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18007129d`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18007118d`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800711f3`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18007118d`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800711f3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070f80`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070fae`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070fc5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070fdc`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071254`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800712dc`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070f80`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070fae`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070fc5`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070fdc`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071254`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800712dc`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x180071602`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x180071625`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x18007165a`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x18007169b`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x180071602`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x180071625`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x18007165a`
- `framedynos!?SetDateTime@CInstance@@QEAA_NPEBGAEBVWBEMTime@@@Z` at `0x18007169b`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x180070dd0`
- `framedynos!?IsNull@CInstance@@QEBA_NPEBG@Z` at `0x180070dd0`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070e9d`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070f3f`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070f69`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071045`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18007109b`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800712ac`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18007132b`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071342`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071359`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071370`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800713ac`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800713eb`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800714d9`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800714ec`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071548`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800715b8`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800716d3`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800716ea`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800716fd`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071710`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071723`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18007173a`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071751`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070e9d`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070f3f`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180070f69`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071045`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18007109b`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800712ac`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18007132b`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071342`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071359`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071370`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800713ac`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800713eb`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800714d9`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800714ec`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071548`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800715b8`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800716d3`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800716ea`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800716fd`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071710`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071723`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18007173a`
- `framedynos!?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180071751`
- `framedynos!?s_strComputerName@Provider@@0VCHString@@A` at `0x180070f86`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x1800714a6`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180071515`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x18007157d`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x1800715ed`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180071610`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180071645`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180071686`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x1800714a6`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180071515`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x18007157d`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x1800715ed`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180071610`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180071645`
- `framedynos!??0WBEMTime@@QEAA@AEBU_FILETIME@@@Z` at `0x180071686`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180071116`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800718ce`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180071116`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800718ce`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800711a9`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180071214`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800711a9`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x180071214`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800718e4`
- `framedynos!?SetWBEMINT64@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800718e4`
- `framedynos!?GetDMTFNonNtfs@WBEMTime@@QEBAPEAGXZ` at `0x1800714b1`
- `framedynos!?GetDMTFNonNtfs@WBEMTime@@QEBAPEAGXZ` at `0x180071520`
- `framedynos!?GetDMTFNonNtfs@WBEMTime@@QEBAPEAGXZ` at `0x180071588`
- `framedynos!?GetDMTFNonNtfs@WBEMTime@@QEBAPEAGXZ` at `0x1800714b1`
- `framedynos!?GetDMTFNonNtfs@WBEMTime@@QEBAPEAGXZ` at `0x180071520`
- `framedynos!?GetDMTFNonNtfs@WBEMTime@@QEBAPEAGXZ` at `0x180071588`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180070e86`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180071234`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180071260`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18007126c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180071278`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18007128f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800718f0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180071907`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180070e86`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180071234`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180071260`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18007126c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180071278`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18007128f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800718f0`

## string_xrefs

- `0x180070f6f`: `Win32_ComputerSystem`
- `0x18007139e`: `Compressed`
- `0x1800713c5`: `Compressed`
- `0x180071084`: `Extension`
- `0x180071719`: `Extension`
- `0x18007153e`: `LastAccessed`
- `0x180071650`: `LastAccessed`
- `0x18007183a`: `AccessMask`
- `0x18007185b`: `AccessMask`
- `0x1800713a5`: `CompressionMethod`
- `0x1800714e2`: `InstallDate`
- `0x18007161b`: `InstallDate`
- `0x180070f48`: `Readable`
- `0x180071380`: `Writeable`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CImplement_LogicalFile::LoadPropertyValuesNT(
        CImplement_LogicalFile *this,
        struct CInstance *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        wchar_t *String1,
        struct _WIN32_FIND_DATAW *a6,
        unsigned int a7)
{
  char v10; // r13
  DWORD dwFileAttributes; // eax
  HANDLE v12; // rax
  __int64 v13; // rax
  wchar_t *v14; // r13
  wchar_t *cAlternateFileName; // rcx
  wchar_t *v16; // rax
  const unsigned __int16 *v17; // rdx
  unsigned int v18; // ebx
  const unsigned __int16 *v19; // r8
  wchar_t *v20; // rax
  CInstance *v21; // rcx
  bool v22; // r8
  CInstance *v23; // rcx
  bool v24; // r8
  __int64 v25; // rax
  OLECHAR *DMTFNonNtfs; // rax
  unsigned __int16 *v27; // r14
  OLECHAR *v28; // rax
  unsigned __int16 *v29; // r14
  OLECHAR *v30; // rax
  unsigned __int16 *v31; // r14
  __int64 v32; // rax
  const unsigned __int16 **v33; // rax
  unsigned int v34; // r8d
  const unsigned __int16 **v36; // [rsp+40h] [rbp-C0h] BYREF
  int FileInformation; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v38; // [rsp+50h] [rbp-B0h] BYREF
  CImplement_LogicalFile *v39; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v40; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v41[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  void *v44; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v45[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v46[608]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v47[608]; // [rsp+300h] [rbp+200h] BYREF
  wchar_t String[8]; // [rsp+560h] [rbp+460h] BYREF
  wchar_t Buffer[40]; // [rsp+570h] [rbp+470h] BYREF
  WCHAR FileName; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v51[1038]; // [rsp+5C2h] [rbp+4C2h] BYREF
  wchar_t v52[264]; // [rsp+9D0h] [rbp+8D0h] BYREF
  wchar_t Str[520]; // [rsp+BE0h] [rbp+AE0h] BYREF
  unsigned __int16 v54[520]; // [rsp+FF0h] [rbp+EF0h] BYREF

  v39 = this;
  *(_QWORD *)String = 0;
  StringCchCopyNW(String, 4u, a3, 3u);
  StringCchCopyNW(v52, 0x105u, a4, 0x104u);
  _wcslwr(String);
  _wcslwr(v52);
  FileName = 0;
  memset_0(v51, 0, sizeof(v51));
  CHString::CHString((CHString *)v45);
  if ( a6 )
  {
    v10 = 0;
    if ( CInstance::IsNull(a2, L"Name") )
    {
      StringCbPrintfW(&FileName, 0x410u, L"%s%s%s", a3, a4, a6->cFileName);
    }
    else
    {
      CHString::CHString((CHString *)&v38);
      CInstance::GetCHString(a2, L"Name", (struct CHString *)&v38);
      if ( CHString::GetLength((CHString *)&v38) )
        StringCchCopyNW(&FileName, 0x208u, v38, 0x103u);
      else
        StringCbPrintfW(&FileName, 0x410u, L"%s%s%s", a3, a4, a6->cFileName);
      CHString::~CHString((CHString *)&v38);
    }
  }
  else
  {
    v10 = 1;
    StringCbPrintfW(&FileName, 0x410u, L"%s\\", a3);
  }
  CInstance::SetWCHARSplat(a2, L"Name", &FileName);
  if ( a6 )
    dwFileAttributes = a6->dwFileAttributes;
  else
    dwFileAttributes = 0;
  v12 = CreateFileW(&FileName, 0, 7u, 0, 3u, dwFileAttributes | 0x2000000, 0);
  v44 = v12;
  if ( v12 == (HANDLE)-1LL )
  {
    if ( GetLastError() != 2 )
    {
      FileInformation = 1;
      goto LABEL_15;
    }
  }
  else
  {
    FileInformation = 0;
    if ( GetFileType(v12) == 1 )
    {
LABEL_15:
      if ( !CImplement_LogicalFile::GetAllProps(v39) )
        goto LABEL_110;
      if ( String1 )
      {
        v13 = -1;
        do
          ++v13;
        while ( String1[v13] );
        if ( v13 )
          CInstance::SetWCHARSplat(a2, L"FSName", String1);
      }
      CInstance::Setbool(a2, L"Readable", 1);
      CInstance::SetWCHARSplat(a2, L"Drive", String);
      CInstance::SetCharSplat(a2, L"CSCreationClassName", L"Win32_ComputerSystem");
      CInstance::SetCHString(a2, L"CSName", Provider::s_strComputerName);
      CInstance::SetCharSplat(a2, L"CreationClassName", L"CIM_LogicalFile");
      CInstance::SetCharSplat(a2, L"Status", L"OK");
      CInstance::SetCharSplat(a2, L"FSCreationClassName", L"Win32_FileSystem");
      if ( v10 )
      {
        StringCbPrintfW(&FileName, 0x410u, L"%s\\", a3);
        CInstance::SetWCHARSplat(a2, L"EightDotThreeFileName", (const unsigned __int16 *)&Data);
        CInstance::SetWCHARSplat(a2, L"Caption", &FileName);
        CInstance::SetWCHARSplat(a2, L"Path", (const unsigned __int16 *)&Data);
        CInstance::SetWCHARSplat(a2, L"Filename", (const unsigned __int16 *)&Data);
        CInstance::SetWCHARSplat(a2, L"Extension", (const unsigned __int16 *)&Data);
        CInstance::SetWCHARSplat(a2, L"Description", &FileName);
        CInstance::SetWCHARSplat(a2, L"FileType", L"Local Disk");
        goto LABEL_94;
      }
      v14 = 0;
      cAlternateFileName = a6->cAlternateFileName;
      if ( !a6->cAlternateFileName[0] )
        cAlternateFileName = a6->cFileName;
      v16 = _wcslwr(cAlternateFileName);
      StringCbPrintfW(v54, 0x410u, L"%s%s%s", String, v52, v16);
      CInstance::SetWCHARSplat(a2, L"EightDotThreeFileName", v54);
      if ( (a6->dwFileAttributes & 0x10) == 0 )
        v14 = wcsrchr(a6->cFileName, 0x2Eu);
      CInstance::Setbool(a2, L"Archive", (a6->dwFileAttributes & 0x20) != 0);
      if ( v14 )
      {
        CInstance::SetWCHARSplat(a2, L"Extension", v14 + 1);
        if ( (a7 & 4) == 0 )
          goto LABEL_47;
        if ( (a6->dwFileAttributes & 0x10) == 0 )
        {
          CRegistry::CRegistry((CRegistry *)v47);
          CHString::CHString((CHString *)&v38);
          _bstr_t::_bstr_t((_bstr_t *)&v36, v14 + 1);
          if ( v36 )
            v17 = *v36;
          else
            v17 = 0;
          CHString::CHString((CHString *)&IoStatusBlock, v17);
          CHString::CHString((CHString *)&v42);
          CHString::CHString((CHString *)&v40);
          CHString::Format((CHString *)&v40, L"%s %s", IoStatusBlock.Pointer, L"File");
          CHString::Format((CHString *)&v38, L"%s.%s", L"Software\\Classes\\", IoStatusBlock.Pointer);
          if ( !CRegistry::Open((CRegistry *)v47, HKEY_LOCAL_MACHINE, v38, 0x20019u)
            && !CRegistry::GetCurrentKeyValue((CRegistry *)v47, 0, (struct CHString *)&v42) )
          {
            CRegistry::CRegistry((CRegistry *)v46);
            CHString::Format((CHString *)&v38, L"%s%s", L"Software\\Classes\\", v42);
            if ( !CRegistry::Open((CRegistry *)v46, HKEY_LOCAL_MACHINE, v38, 0x20019u) )
            {
              CHString::CHString((CHString *)v41);
              if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v46, 0, (struct CHString *)v41) )
                CHString::operator=(&v40, v41);
              CHString::~CHString((CHString *)v41);
            }
            CRegistry::~CRegistry((CRegistry *)v46);
          }
          CInstance::SetCharSplat(a2, L"FileType", v40);
          CHString::~CHString((CHString *)&v40);
          CHString::~CHString((CHString *)&v42);
          CHString::~CHString((CHString *)&IoStatusBlock);
          _bstr_t::_Free((_bstr_t *)&v36);
          CHString::~CHString((CHString *)&v38);
          CRegistry::~CRegistry((CRegistry *)v47);
          goto LABEL_47;
        }
      }
      else
      {
        CInstance::SetWCHARSplat(a2, L"Extension", (const unsigned __int16 *)&Data);
        if ( (a7 & 4) == 0 )
          goto LABEL_47;
        if ( (a6->dwFileAttributes & 0x10) == 0 )
        {
          v19 = L"File";
LABEL_46:
          CInstance::SetCharSplat(a2, L"FileType", v19);
LABEL_47:
          StringCbCopyW(Str, 0x410u, a6->cFileName);
          if ( (a6->dwFileAttributes & 0x10) == 0 )
          {
            v20 = wcsrchr(Str, 0x2Eu);
            if ( v20 )
              *v20 = 0;
          }
          CInstance::SetWCHARSplat(a2, L"Filename", Str);
          CInstance::SetWCHARSplat(a2, L"Caption", &FileName);
          CInstance::SetWCHARSplat(a2, L"Path", v52);
          CInstance::SetWCHARSplat(a2, L"Description", &FileName);
          CInstance::Setbool(a2, L"Writeable", (a6->dwFileAttributes & 1) == 0);
          v21 = a2;
          if ( (a6->dwFileAttributes & 0x800) != 0 )
          {
            CInstance::SetWCHARSplat(a2, L"CompressionMethod", L"Compressed");
            v22 = (a6->dwFileAttributes & 0x800) != 0;
            v21 = a2;
          }
          else
          {
            v22 = 0;
          }
          CInstance::Setbool(v21, L"Compressed", v22);
          v23 = a2;
          if ( (a6->dwFileAttributes & 0x4000) != 0 )
          {
            CInstance::SetWCHARSplat(a2, L"EncryptionMethod", L"Encrypted");
            v24 = (a6->dwFileAttributes & 0x4000) != 0;
            v23 = a2;
          }
          else
          {
            v24 = 0;
          }
          CInstance::Setbool(v23, L"Encrypted", v24);
          CInstance::Setbool(a2, L"Hidden", (a6->dwFileAttributes & 2) != 0);
          CInstance::Setbool(a2, L"System", (a6->dwFileAttributes & 4) != 0);
          if ( String1 )
          {
            v25 = -1;
            do
              ++v25;
            while ( String1[v25] );
            if ( v25 )
            {
              if ( _wcsicmp(String1, L"NTFS") )
              {
                if ( (a7 & 0x100) != 0 || (a7 & 0x800) != 0 )
                {
                  if ( a6->ftCreationTime.dwLowDateTime )
                  {
                    if ( a6->ftCreationTime.dwHighDateTime )
                    {
                      WBEMTime::WBEMTime((WBEMTime *)&v36, &a6->ftCreationTime);
                      DMTFNonNtfs = WBEMTime::GetDMTFNonNtfs((WBEMTime *)&v36);
                      v27 = DMTFNonNtfs;
                      if ( DMTFNonNtfs )
                      {
                        if ( SysStringLen(DMTFNonNtfs) )
                        {
                          CInstance::SetWCHARSplat(a2, L"CreationDate", v27);
                          CInstance::SetWCHARSplat(a2, L"InstallDate", v27);
                          SysFreeString(v27);
                        }
                      }
                    }
                  }
                }
                if ( (a7 & 0x200) != 0 )
                {
                  if ( a6->ftLastAccessTime.dwLowDateTime )
                  {
                    if ( a6->ftLastAccessTime.dwHighDateTime )
                    {
                      WBEMTime::WBEMTime((WBEMTime *)&v36, &a6->ftLastAccessTime);
                      v28 = WBEMTime::GetDMTFNonNtfs((WBEMTime *)&v36);
                      v29 = v28;
                      if ( v28 )
                      {
                        if ( SysStringLen(v28) )
                        {
                          CInstance::SetWCHARSplat(a2, L"LastAccessed", v29);
                          SysFreeString(v29);
                        }
                      }
                    }
                  }
                }
                if ( (a7 & 0x400) != 0 )
                {
                  if ( a6->ftLastWriteTime.dwLowDateTime )
                  {
                    if ( a6->ftLastWriteTime.dwHighDateTime )
                    {
                      WBEMTime::WBEMTime((WBEMTime *)&v36, &a6->ftLastWriteTime);
                      v30 = WBEMTime::GetDMTFNonNtfs((WBEMTime *)&v36);
                      v31 = v30;
                      if ( v30 )
                      {
                        if ( SysStringLen(v30) )
                        {
                          CInstance::SetWCHARSplat(a2, L"LastModified", v31);
                          SysFreeString(v31);
                        }
                      }
                    }
                  }
                }
              }
              else
              {
                if ( ((a7 & 0x100) != 0 || (a7 & 0x800) != 0)
                  && a6->ftCreationTime.dwLowDateTime
                  && a6->ftCreationTime.dwHighDateTime )
                {
                  WBEMTime::WBEMTime((WBEMTime *)&v36, &a6->ftCreationTime);
                  CInstance::SetDateTime(a2, L"CreationDate", (const struct WBEMTime *)&v36);
                  WBEMTime::WBEMTime((WBEMTime *)&v36, &a6->ftCreationTime);
                  CInstance::SetDateTime(a2, L"InstallDate", (const struct WBEMTime *)&v36);
                }
                if ( (a7 & 0x200) != 0 && a6->ftLastAccessTime.dwLowDateTime && a6->ftLastAccessTime.dwHighDateTime )
                {
                  WBEMTime::WBEMTime((WBEMTime *)&v36, &a6->ftLastAccessTime);
                  CInstance::SetDateTime(a2, L"LastAccessed", (const struct WBEMTime *)&v36);
                }
                if ( (a7 & 0x400) != 0 && a6->ftLastWriteTime.dwLowDateTime && a6->ftLastWriteTime.dwHighDateTime )
                {
                  WBEMTime::WBEMTime((WBEMTime *)&v36, &a6->ftLastWriteTime);
                  CInstance::SetDateTime(a2, L"LastModified", (const struct WBEMTime *)&v36);
                }
              }
            }
          }
LABEL_94:
          if ( (a7 & 0x80u) != 0 )
          {
            if ( String1 )
            {
              v32 = -1;
              do
                ++v32;
              while ( String1[v32] );
              if ( v32 )
              {
                if ( _wcsicmp(String1, L"FAT") && _wcsicmp(String1, L"FAT32") )
                {
                  if ( !FileInformation )
                  {
                    v33 = (const unsigned __int16 **)CreateFileW(&FileName, 0x2000000u, 7u, 0, 3u, 0x2000000u, 0);
                    v36 = v33;
                    if ( v33 == (const unsigned __int16 **)-1LL )
                    {
                      if ( GetLastError() == 5 )
                      {
                        v34 = 0;
                        goto LABEL_107;
                      }
                    }
                    else
                    {
                      FileInformation = 0;
                      IoStatusBlock = 0;
                      if ( NtQueryInformationFile(v33, &IoStatusBlock, &FileInformation, 4u, FileAccessInformation) >= 0 )
                      {
                        v34 = FileInformation;
LABEL_107:
                        CInstance::SetDWORD(a2, L"AccessMask", v34);
                      }
                    }
                    SmartCloseHandle::~SmartCloseHandle((void **)&v36);
LABEL_111:
                    (*(void (__fastcall **)(CImplement_LogicalFile *, struct CInstance *, _QWORD))(*(_QWORD *)v39 + 144LL))(
                      v39,
                      a2,
                      a7);
LABEL_115:
                    v18 = 0;
                    goto LABEL_116;
                  }
LABEL_112:
                  if ( (a7 & 0x20) != 0 && a6 )
                  {
                    _i64tow_s(a6->nFileSizeLow + ((unsigned __int64)a6->nFileSizeHigh << 32), Buffer, 0x28u, 10);
                    CHString::CHString((CHString *)&v39, Buffer);
                    CInstance::SetWBEMINT64(a2, L"FileSize", (const struct CHString *)&v39);
                    CHString::~CHString((CHString *)&v39);
                  }
                  goto LABEL_115;
                }
                CInstance::SetDWORD(a2, L"AccessMask", 0xFFFFFFFF);
              }
            }
          }
LABEL_110:
          if ( !FileInformation )
            goto LABEL_111;
          goto LABEL_112;
        }
      }
      v19 = L"File Folder";
      goto LABEL_46;
    }
  }
  v18 = -2147217406;
LABEL_116:
  SmartCloseHandle::~SmartCloseHandle(&v44);
  CHString::~CHString((CHString *)v45);
  return v18;
}

```

## disassembly

```asm
0x180070cd0  push    rbp
0x180070cd2  push    rbx
0x180070cd3  push    rsi
0x180070cd4  push    rdi
0x180070cd5  push    r12
0x180070cd7  push    r13
0x180070cd9  push    r14
0x180070cdb  push    r15
0x180070cdd  lea     rbp, [rsp-1318h]
0x180070ce5  mov     eax, 1418h
0x180070cea  call    _alloca_probe
0x180070cef  sub     rsp, rax
0x180070cf2  mov     rax, cs:__security_cookie
0x180070cf9  xor     rax, rsp
0x180070cfc  mov     [rbp+1350h+var_50], rax
0x180070d03  mov     rsi, r9
0x180070d06  mov     r14, r8
0x180070d09  mov     rbx, rdx
0x180070d0c  mov     [rsp+1450h+var_13F8], rcx
0x180070d11  mov     rdi, [rbp+1350h+arg_28]
0x180070d18  mov     r12, [rbp+1350h+String1]
0x180070d1f  xor     r15d, r15d
0x180070d22  mov     qword ptr [rbp+1350h+String], r15
0x180070d29  lea     edx, [r15+4]; unsigned __int64
0x180070d2d  lea     r9d, [r15+3]; unsigned __int64
0x180070d31  lea     rcx, [rbp+1350h+String]; unsigned __int16 *
0x180070d38  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180070d3d  mov     r9d, 104h; unsigned __int64
0x180070d43  mov     r8, rsi; unsigned __int16 *
0x180070d46  lea     edx, [r9+1]; unsigned __int64
0x180070d4a  lea     rcx, [rbp+1350h+var_A80]; unsigned __int16 *
0x180070d51  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180070d56  lea     rcx, [rbp+1350h+String]; String
0x180070d5d  call    cs:__imp__wcslwr
0x180070d63  lea     rcx, [rbp+1350h+var_A80]; String
0x180070d6a  call    cs:__imp__wcslwr
0x180070d70  mov     [rbp+1350h+FileName], r15w
0x180070d78  xor     edx, edx; Val
0x180070d7a  mov     r8d, 40Eh; Size
0x180070d80  lea     rcx, [rbp+1350h+var_E8E]; void *
0x180070d87  call    memset_0
0x180070d8c  lea     rcx, [rbp+1350h+var_13C0]
0x180070d90  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180070d96  nop
0x180070d97  test    rdi, rdi
0x180070d9a  jnz     short loc_180070DC3
0x180070d9c  mov     r13b, 1
0x180070d9f  mov     r9, r14
0x180070da2  lea     r8, aS_6; "%s\\"
0x180070da9  mov     r15d, 410h
0x180070daf  mov     edx, r15d; unsigned __int64
0x180070db2  lea     rcx, [rbp+1350h+FileName]; unsigned __int16 *
0x180070db9  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180070dbe  jmp     loc_180070E8C
0x180070dc3  mov     r13b, r15b
0x180070dc6  lea     rdx, aName; "Name"
0x180070dcd  mov     rcx, rbx
0x180070dd0  call    cs:__imp_?IsNull@CInstance@@QEBA_NPEBG@Z; CInstance::IsNull(ushort const *)
0x180070dd6  test    al, al
0x180070dd8  jz      short loc_180070E0C
0x180070dda  lea     rax, [rdi+2Ch]
0x180070dde  mov     qword ptr [rsp+1450h+dwFlagsAndAttributes], rax
0x180070de3  mov     qword ptr [rsp+1450h+dwCreationDisposition], rsi
0x180070de8  mov     r9, r14
0x180070deb  lea     r8, aSSS_1; "%s%s%s"
0x180070df2  mov     r15d, 410h
0x180070df8  mov     edx, r15d; unsigned __int64
0x180070dfb  lea     rcx, [rbp+1350h+FileName]; unsigned __int16 *
0x180070e02  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180070e07  jmp     loc_180070E8C
0x180070e0c  lea     rcx, [rsp+1450h+var_1400]
0x180070e11  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180070e17  nop
0x180070e18  lea     r8, [rsp+1450h+var_1400]
0x180070e1d  lea     rdx, aName; "Name"
0x180070e24  mov     rcx, rbx
0x180070e27  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x180070e2d  lea     rcx, [rsp+1450h+var_1400]
0x180070e32  call    cs:__imp_?GetLength@CHString@@QEBAHXZ; CHString::GetLength(void)
0x180070e38  mov     r15d, 410h
0x180070e3e  lea     rcx, [rbp+1350h+FileName]; unsigned __int16 *
0x180070e45  test    eax, eax
0x180070e47  jnz     short loc_180070E6B
0x180070e49  lea     rax, [rdi+2Ch]
0x180070e4d  mov     qword ptr [rsp+1450h+dwFlagsAndAttributes], rax
0x180070e52  mov     qword ptr [rsp+1450h+dwCreationDisposition], rsi
0x180070e57  mov     r9, r14
0x180070e5a  lea     r8, aSSS_1; "%s%s%s"
0x180070e61  mov     edx, r15d; unsigned __int64
0x180070e64  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180070e69  jmp     short loc_180070E81
0x180070e6b  mov     r9d, 103h; unsigned __int64
0x180070e71  mov     r8, [rsp+1450h+var_1400]; unsigned __int16 *
0x180070e76  mov     edx, 208h; unsigned __int64
0x180070e7b  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180070e80  nop
0x180070e81  lea     rcx, [rsp+1450h+var_1400]
0x180070e86  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180070e8c  lea     r8, [rbp+1350h+FileName]
0x180070e93  lea     rdx, aName; "Name"
0x180070e9a  mov     rcx, rbx
0x180070e9d  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180070ea3  xor     esi, esi
0x180070ea5  test    rdi, rdi
0x180070ea8  jz      short loc_180070EAE
0x180070eaa  mov     eax, [rdi]
0x180070eac  jmp     short loc_180070EB0
0x180070eae  mov     eax, esi
0x180070eb0  bts     eax, 19h
0x180070eb4  mov     [rsp+1450h+hTemplateFile], rsi; hTemplateFile
0x180070eb9  mov     [rsp+1450h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180070ebd  mov     [rsp+1450h+dwCreationDisposition], 3; dwCreationDisposition
0x180070ec5  xor     r9d, r9d; lpSecurityAttributes
0x180070ec8  xor     edx, edx; dwDesiredAccess
0x180070eca  lea     r8d, [r9+7]; dwShareMode
0x180070ece  lea     rcx, [rbp+1350h+FileName]; lpFileName
0x180070ed5  call    cs:__imp_CreateFileW
0x180070edb  mov     [rbp+1350h+var_13C8], rax
0x180070edf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180070ee3  jnz     loc_1800710EE
0x180070ee9  call    cs:__imp_GetLastError
0x180070eef  cmp     eax, 2
0x180070ef2  jz      loc_180071104
0x180070ef8  mov     [rsp+1450h+FileInformation], 1
0x180070f00  mov     rcx, [rsp+1450h+var_13F8]; this
0x180070f05  call    ?GetAllProps@CImplement_LogicalFile@@IEAA_NXZ; CImplement_LogicalFile::GetAllProps(void)
0x180070f0a  mov     esi, [rbp+1350h+arg_30]
0x180070f10  xor     ecx, ecx
0x180070f12  test    al, al
0x180070f14  jz      loc_18007186D
0x180070f1a  test    r12, r12
0x180070f1d  jz      short loc_180070F45
0x180070f1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180070f23  inc     rax
0x180070f26  cmp     [r12+rax*2], cx
0x180070f2b  jnz     short loc_180070F23
0x180070f2d  test    rax, rax
0x180070f30  jz      short loc_180070F45
0x180070f32  mov     r8, r12
0x180070f35  lea     rdx, aFsname; "FSName"
0x180070f3c  mov     rcx, rbx
0x180070f3f  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180070f45  mov     r8b, 1
0x180070f48  lea     rdx, aReadable; "Readable"
0x180070f4f  mov     rcx, rbx
0x180070f52  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180070f58  lea     r8, [rbp+1350h+String]
0x180070f5f  lea     rdx, aDrive; "Drive"
0x180070f66  mov     rcx, rbx
0x180070f69  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x180070f6f  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x180070f76  lea     rdx, aCscreationclas; "CSCreationClassName"
0x180070f7d  mov     rcx, rbx
0x180070f80  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180070f86  mov     r8, cs:__imp_?s_strComputerName@Provider@@0VCHString@@A; CHString Provider::s_strComputerName
0x180070f8d  lea     rdx, aCsname; "CSName"
0x180070f94  mov     rcx, rbx
0x180070f97  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180070f9d  lea     r8, aCimLogicalfile; "CIM_LogicalFile"
0x180070fa4  lea     rdx, aCreationclassn; "CreationClassName"
0x180070fab  mov     rcx, rbx
0x180070fae  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180070fb4  lea     r8, aOk; "OK"
0x180070fbb  lea     rdx, aStatus; "Status"
0x180070fc2  mov     rcx, rbx
0x180070fc5  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180070fcb  lea     r8, aWin32Filesyste; "Win32_FileSystem"
0x180070fd2  lea     rdx, aFscreationclas; "FSCreationClassName"
0x180070fd9  mov     rcx, rbx
0x180070fdc  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180070fe2  xor     eax, eax
0x180070fe4  test    r13b, r13b
0x180070fe7  jnz     loc_1800716A6
0x180070fed  mov     r13d, eax
0x180070ff0  lea     rcx, [rdi+234h]
0x180070ff7  cmp     [rcx], ax
0x180070ffa  jnz     short loc_180071000
0x180070ffc  lea     rcx, [rdi+2Ch]; String
0x180071000  call    cs:__imp__wcslwr
0x180071006  mov     qword ptr [rsp+1450h+dwFlagsAndAttributes], rax
0x18007100b  lea     rax, [rbp+1350h+var_A80]
0x180071012  mov     qword ptr [rsp+1450h+dwCreationDisposition], rax
0x180071017  lea     r9, [rbp+1350h+String]
0x18007101e  lea     r8, aSSS_1; "%s%s%s"
0x180071025  mov     rdx, r15; unsigned __int64
0x180071028  lea     rcx, [rbp+1350h+var_460]; unsigned __int16 *
0x18007102f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180071034  lea     r8, [rbp+1350h+var_460]
0x18007103b  lea     rdx, aEightdotthreef; "EightDotThreeFileName"
0x180071042  mov     rcx, rbx
0x180071045  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x18007104b  test    byte ptr [rdi], 10h
0x18007104e  jnz     short loc_180071062
0x180071050  mov     edx, 2Eh ; '.'; Ch
0x180071055  lea     rcx, [rdi+2Ch]; Str
0x180071059  call    cs:__imp_wcsrchr
0x18007105f  mov     r13, rax
0x180071062  mov     r8d, [rdi]
0x180071065  shr     r8d, 5
0x180071069  and     r8b, 1
0x18007106d  lea     rdx, aArchive; "Archive"
0x180071074  mov     rcx, rbx
0x180071077  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18007107d  mov     r14d, esi
0x180071080  and     r14d, 4
0x180071084  lea     rdx, aExtension; "Extension"
0x18007108b  mov     rcx, rbx
0x18007108e  test    r13, r13
0x180071091  jz      loc_1800712A5
0x180071097  lea     r8, [r13+2]
0x18007109b  call    cs:__imp_?SetWCHARSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetWCHARSplat(ushort const *,ushort const *)
0x1800710a1  test    r14d, r14d
0x1800710a4  jz      loc_1800712E4
0x1800710aa  test    byte ptr [rdi], 10h
0x1800710ad  jnz     loc_1800712C8
0x1800710b3  lea     rcx, [rbp+1350h+var_1150]
0x1800710ba  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x1800710c0  nop
0x1800710c1  lea     rcx, [rsp+1450h+var_1400]
0x1800710c6  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800710cc  nop
0x1800710cd  lea     rdx, [r13+2]; unsigned __int16 *
0x1800710d1  lea     rcx, [rsp+1450h+var_1410]; this
0x1800710d6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800710db  nop
0x1800710dc  mov     rax, [rsp+1450h+var_1410]
0x1800710e1  xor     r13d, r13d
0x1800710e4  test    rax, rax
0x1800710e7  jz      short loc_18007110E
0x1800710e9  mov     rdx, [rax]
0x1800710ec  jmp     short loc_180071111
0x1800710ee  mov     [rsp+1450h+FileInformation], esi
0x1800710f2  mov     rcx, rax; hFile
0x1800710f5  call    cs:__imp_GetFileType
0x1800710fb  cmp     eax, 1
0x1800710fe  jz      loc_180070F00
0x180071104  mov     ebx, 80041002h
0x180071109  jmp     loc_1800718F9
0x18007110e  mov     rdx, r13
0x180071111  lea     rcx, [rsp+1450h+IoStatusBlock]
0x180071116  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x18007111c  nop
0x18007111d  lea     rcx, [rsp+1450h+var_13E0]
0x180071122  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180071128  nop
0x180071129  lea     rcx, [rsp+1450h+var_13F0]
0x18007112e  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180071134  nop
0x180071135  lea     r9, aFile; "File"
0x18007113c  mov     r8, qword ptr [rsp+1450h+IoStatusBlock]
0x180071141  lea     rdx, aSS_2; "%s %s"
0x180071148  lea     rcx, [rsp+1450h+var_13F0]
0x18007114d  call    cs:__imp_?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x180071153  mov     r9, qword ptr [rsp+1450h+IoStatusBlock]
0x180071158  lea     r8, aSoftwareClasse_6; "Software\\Classes\\"
0x18007115f  lea     rdx, aSS; "%s.%s"
0x180071166  lea     rcx, [rsp+1450h+var_1400]
0x18007116b  call    cs:__imp_?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x180071171  mov     r14d, 20019h
0x180071177  mov     r9d, r14d
0x18007117a  mov     r8, [rsp+1450h+var_1400]
0x18007117f  mov     rdx, 0FFFFFFFF80000002h
0x180071186  lea     rcx, [rbp+1350h+var_1150]
0x18007118d  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180071193  test    eax, eax
0x180071195  jnz     loc_180071245
0x18007119b  lea     r8, [rsp+1450h+var_13E0]
0x1800711a0  xor     edx, edx
0x1800711a2  lea     rcx, [rbp+1350h+var_1150]
0x1800711a9  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800711af  test    eax, eax
0x1800711b1  jnz     loc_180071245
0x1800711b7  lea     rcx, [rbp+1350h+var_13B0]
0x1800711bb  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x1800711c1  nop
0x1800711c2  mov     r9, [rsp+1450h+var_13E0]
0x1800711c7  lea     r8, aSoftwareClasse_6; "Software\\Classes\\"
0x1800711ce  lea     rdx, aSS_1; "%s%s"
0x1800711d5  lea     rcx, [rsp+1450h+var_1400]
0x1800711da  call    cs:__imp_?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x1800711e0  mov     r9d, r14d
0x1800711e3  mov     r8, [rsp+1450h+var_1400]
0x1800711e8  mov     rdx, 0FFFFFFFF80000002h
0x1800711ef  lea     rcx, [rbp+1350h+var_13B0]
0x1800711f3  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x1800711f9  test    eax, eax
0x1800711fb  jnz     short loc_18007123B
0x1800711fd  lea     rcx, [rsp+1450h+var_13E8]
0x180071202  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180071208  nop
0x180071209  lea     r8, [rsp+1450h+var_13E8]
0x18007120e  xor     edx, edx
0x180071210  lea     rcx, [rbp+1350h+var_13B0]
0x180071214  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x18007121a  test    eax, eax
0x18007121c  jnz     short loc_18007122F
0x18007121e  lea     rdx, [rsp+1450h+var_13E8]
0x180071223  lea     rcx, [rsp+1450h+var_13F0]
0x180071228  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x18007122e  nop
  ... truncated ...
```
