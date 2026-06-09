# CRepositoryCorruption::ReportCorruption(bool)

- ea: `0x18003b9f8`
- end: `0x18003c163`
- name: `?ReportCorruption@CRepositoryCorruption@@SAJ_N@Z`
- size: `1899`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c950`
- `0x18002fd70`

## callees

- `0x1800013a0`
- `0x18001ad80`
- `0x1800216c8`
- `0x180024ca0`
- `0x180029fbc`
- `0x18003b9f8`
- `0x18003f940`
- `0x180042564`
- `0x180044170`
- `0x180044208`
- `0x1800443df`
- `0x180044420`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003bb65`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003bb65`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003babe`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003babe`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003bc18`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003bc86`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003bc18`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003bc86`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003be64`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003be64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bcfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bcfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be6e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003bba0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003bc5e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003bba0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003bc5e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003bced`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003bced`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bcb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bcb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bd7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003bc98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003bc98`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003bd12`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18003c06d`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18003c06d`

## string_xrefs

- `0x18003bc91`: `wmisvc.dll`
- `0x18003bb99`: `%windir%\system32\wbem\repository\Corrupted.rec`
- `0x18003bc57`: `%windir%\system32\wbem\repository\SystemEvents`
- `0x18003bce6`: `wer.dll`
- `0x18003bd25`: `WerReportCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CRepositoryCorruption::ReportCorruption(char a1, __int64 a2, int a3)
{
  __int64 result; // rax
  int v5; // r8d
  signed __int32 v6; // ebx
  int v7; // ebx
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  CRepositoryPackager *v10; // rcx
  unsigned int *v11; // rdi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  HMODULE Library; // rbx
  signed int LastError; // eax
  FARPROC v16; // r12
  FARPROC v17; // r14
  FARPROC v18; // rsi
  FARPROC v19; // r13
  FARPROC v20; // rax
  int (__fastcall *v21)(void *); // r15
  signed int v22; // eax
  __int64 v23; // r9
  int v24; // r8d
  int v25; // eax
  PDWORD pdwReturnedProductType; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+28h] [rbp-D8h]
  WCHAR *v28; // [rsp+40h] [rbp-C0h] BYREF
  char v29[8]; // [rsp+48h] [rbp-B8h] BYREF
  int (__fastcall *v30)(void *); // [rsp+50h] [rbp-B0h]
  WCHAR *v31; // [rsp+58h] [rbp-A8h]
  char v32[8]; // [rsp+60h] [rbp-A0h] BYREF
  int (__fastcall *v33)(void *); // [rsp+68h] [rbp-98h]
  struct WMIRepositoryCorruptionReport *v34; // [rsp+70h] [rbp-90h]
  int v35; // [rsp+78h] [rbp-88h] BYREF
  int v36; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD v37; // [rsp+80h] [rbp-80h] BYREF
  char v38[8]; // [rsp+88h] [rbp-78h] BYREF
  BOOL (__stdcall *v39)(HMODULE); // [rsp+90h] [rbp-70h]
  HMODULE v40; // [rsp+98h] [rbp-68h]
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  int v42; // [rsp+A8h] [rbp-58h] BYREF
  int v43; // [rsp+ACh] [rbp-54h] BYREF
  char v44[8]; // [rsp+B0h] [rbp-50h] BYREF
  char v45[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall *v46)(_QWORD); // [rsp+C0h] [rbp-40h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  _OSVERSIONINFOW VersionInformation; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v49; // [rsp+1E4h] [rbp+E4h]
  unsigned __int16 v50; // [rsp+1E6h] [rbp+E6h]
  unsigned __int16 v51[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v52; // [rsp+1F4h] [rbp+F4h]
  __int128 v53; // [rsp+204h] [rbp+104h]
  __int128 v54; // [rsp+214h] [rbp+114h]
  __int64 v55; // [rsp+224h] [rbp+124h]
  WCHAR Dst[264]; // [rsp+230h] [rbp+130h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids);
  }
  v41 = 0;
  result = DLRegOpenKeyExW(-2147483646, (unsigned int)L"SOFTWARE\\Microsoft\\WBEM\\CIMOM", a3, 131103, (__int64)&v41);
  if ( !(_DWORD)result )
  {
    v45[0] = 0;
    v46 = DLRegCloseKey;
    v47 = v41;
    CInCritSec::CInCritSec((CInCritSec *)v44, (struct _RTL_CRITICAL_SECTION *)CRepositoryCorruption::m_ReportCritSec);
    if ( !CRepositoryCorruption::m_pPendingCorruptionReport )
    {
      v6 = _InterlockedCompareExchange(&CRepositoryCorruption::m_dwCorruptionType, 0, 0);
      if ( !v6 )
      {
        v7 = 0;
LABEL_27:
        CInCritSec::~CInCritSec((CInCritSec *)v44);
        goto LABEL_62;
      }
      v35 = 0;
      v36 = 0;
      v42 = 4;
      if ( (unsigned int)DLRegQueryValueExW(
                           v41,
                           (unsigned int)L"RepositoryCorruptionReported",
                           v5,
                           (unsigned int)&v35,
                           (__int64)&v36,
                           (__int64)&v42)
        || v35 != 4
        || !v36 )
      {
        if ( dword_180058AFC )
          CPageSource::Checkpoint((CPageSource *)qword_180058B00);
        v8 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(0x214u);
        v9 = v8;
        if ( !v8 )
        {
          v7 = -2147217402;
          goto LABEL_27;
        }
        memset_0(v8, 0, 0x214u);
        v29[0] = 0;
        v30 = deletePtr<unsigned short>;
        v31 = v9;
        if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\wbem\\repository\\Corrupted.rec", v9, 0x104u) >= 0x104 )
        {
          ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v29);
          v7 = -2147024774;
          goto LABEL_27;
        }
        *((_DWORD *)v9 + 130) = v6;
        *((_DWORD *)v9 + 132) = CRepositoryCorruption::m_dwImproperShutdownFlag;
        *((_DWORD *)v9 + 131) = CRepositoryCorruption::m_bCalledByStartup;
        v7 = CRepositoryPackager::PackageRepository(v10, v9, 0);
        if ( v7 < 0 )
        {
          ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v29);
          goto LABEL_27;
        }
        CRepositoryCorruption::m_pPendingCorruptionReport = (struct WMIRepositoryCorruptionReport *)v9;
        v29[0] = 1;
        ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v29);
      }
    }
    CInCritSec::~CInCritSec((CInCritSec *)v44);
    if ( a1 || (v11 = (unsigned int *)CRepositoryCorruption::m_pPendingCorruptionReport) == 0 )
    {
      v7 = 0;
      goto LABEL_62;
    }
    v32[0] = 0;
    v33 = deletePtr<unsigned short>;
    v34 = CRepositoryCorruption::m_pPendingCorruptionReport;
    CRepositoryCorruption::m_pPendingCorruptionReport = 0;
    if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\wbem\\repository\\SystemEvents", Dst, 0x104u) >= 0x104 )
    {
      ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v32);
      v7 = -2147024774;
LABEL_62:
      ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v45);
      return (unsigned int)v7;
    }
    ModuleHandleW = GetModuleHandleW(L"wmisvc.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "GetSystemEventsForShutdown");
      if ( ProcAddress )
      {
        v7 = ((__int64 (__fastcall *)(WCHAR *))ProcAddress)(Dst);
        if ( v7 < 0 )
        {
LABEL_31:
          ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v32);
          goto LABEL_62;
        }
        Library = LoadLibraryExW(L"wer.dll", 0, 0);
        if ( !Library )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_31;
        }
        v38[0] = 0;
        v39 = FreeLibrary;
        v40 = Library;
        v16 = GetProcAddress(Library, "WerReportCreate");
        v17 = GetProcAddress(Library, "WerReportAddFile");
        v18 = GetProcAddress(Library, "WerReportSetParameter");
        v19 = GetProcAddress(Library, "WerReportSubmit");
        v20 = GetProcAddress(Library, "WerReportCloseHandle");
        v21 = (int (__fastcall *)(void *))v20;
        if ( v16 && v17 && v18 && v19 && v20 )
        {
          v28 = 0;
          v7 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, WCHAR **))v16)(
                 L"WMIInconsistentRepository",
                 0,
                 0,
                 &v28);
          if ( v7 >= 0 )
          {
            v29[0] = 0;
            v30 = v21;
            v31 = v28;
            v7 = ((__int64 (__fastcall *)(WCHAR *, unsigned int *, __int64, __int64))v17)(v28, v11, 5, 1);
            if ( v7 >= 0 )
            {
              v7 = ((__int64 (__fastcall *)(WCHAR *, WCHAR *, __int64, __int64))v17)(v28, Dst, 5, 1);
              if ( v7 >= 0 )
              {
                memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
                VersionInformation.dwOSVersionInfoSize = 284;
                if ( GetVersionExW(&VersionInformation) )
                {
                  *(_DWORD *)v51 = *(_DWORD *)L"0";
                  v52 = 0;
                  v53 = 0;
                  v54 = 0;
                  v55 = 0;
                  GetWmiVersion(v51, 0x1Eu);
                  HIWORD(v55) = 0;
                  LODWORD(v27) = VersionInformation.dwBuildNumber;
                  LODWORD(pdwReturnedProductType) = VersionInformation.dwMinorVersion;
                  StringCchPrintfW(
                    Dst,
                    0x104u,
                    L"%d.%d.%d.%s",
                    VersionInformation.dwMajorVersion,
                    pdwReturnedProductType,
                    v27,
                    v51);
                  v7 = ((__int64 (__fastcall *)(WCHAR *, _QWORD, const wchar_t *, WCHAR *))v18)(v28, 0, L"Version", Dst);
                  if ( v7 >= 0 )
                  {
                    StringCchPrintfW(Dst, 0x104u, L"%d", v11[131]);
                    v7 = ((__int64 (__fastcall *)(WCHAR *, __int64, const wchar_t *, WCHAR *))v18)(
                           v28,
                           1,
                           L"Startup",
                           Dst);
                    if ( v7 >= 0 )
                    {
                      StringCchPrintfW(Dst, 0x104u, L"%d", v11[132]);
                      v7 = ((__int64 (__fastcall *)(WCHAR *, __int64, const wchar_t *, WCHAR *))v18)(
                             v28,
                             2,
                             L"ImproperShutdown",
                             Dst);
                      if ( v7 >= 0 )
                      {
                        v23 = v11[130];
                        if ( (v23 & 0x80u) != 0LL )
                          v23 = (unsigned int)(v23 - 128);
                        StringCchPrintfW(Dst, 0x104u, L"%d", v23);
                        v7 = ((__int64 (__fastcall *)(WCHAR *, __int64, const wchar_t *, WCHAR *))v18)(
                               v28,
                               3,
                               L"Corruption",
                               Dst);
                        if ( v7 >= 0 )
                        {
                          StringCchPrintfW(Dst, 0x104u, L"%d", CRepositoryCorruption::m_dwRecoverType);
                          v7 = ((__int64 (__fastcall *)(WCHAR *, __int64, const wchar_t *, WCHAR *))v18)(
                                 v28,
                                 4,
                                 L"Recover",
                                 Dst);
                          if ( v7 >= 0 )
                          {
                            v37 = 0;
                            GetProductInfo(
                              VersionInformation.dwMajorVersion,
                              VersionInformation.dwMinorVersion,
                              v49,
                              v50,
                              &v37);
                            StringCchPrintfW(Dst, 0x104u, L"%d", v37);
                            v7 = ((__int64 (__fastcall *)(WCHAR *, __int64, const wchar_t *, WCHAR *))v18)(
                                   v28,
                                   5,
                                   L"SKU",
                                   Dst);
                            if ( v7 >= 0 )
                            {
                              v7 = ((__int64 (__fastcall *)(WCHAR *, __int64, _QWORD, _QWORD))v19)(v28, 1, 0, 0);
                              if ( v7 >= 0 )
                              {
                                ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v29);
                                v43 = 1;
                                v25 = DLRegSetValueExW(
                                        v41,
                                        (unsigned int)L"RepositoryCorruptionReported",
                                        v24,
                                        4,
                                        (__int64)&v43,
                                        4);
                                v7 = v25;
                                if ( v25 > 0 )
                                  v7 = (unsigned __int16)v25 | 0x80070000;
                                goto LABEL_41;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                else
                {
                  v22 = GetLastError();
                  v7 = v22;
                  if ( v22 > 0 )
                    v7 = (unsigned __int16)v22 | 0x80070000;
                }
              }
            }
            ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v29);
          }
LABEL_41:
          ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v38);
          goto LABEL_31;
        }
        ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v38);
      }
    }
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v32);
    v7 = -2147217407;
    goto LABEL_62;
  }
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003b9f8  push    rbp
0x18003b9fa  push    rbx
0x18003b9fb  push    rsi
0x18003b9fc  push    rdi
0x18003b9fd  push    r12
0x18003b9ff  push    r13
0x18003ba01  push    r14
0x18003ba03  push    r15
0x18003ba05  lea     rbp, [rsp-358h]
0x18003ba0d  sub     rsp, 458h
0x18003ba14  mov     rax, cs:__security_cookie
0x18003ba1b  xor     rax, rsp
0x18003ba1e  mov     [rbp+390h+var_50], rax
0x18003ba25  mov     sil, cl
0x18003ba28  lea     rax, WPP_GLOBAL_Control
0x18003ba2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba36  cmp     rcx, rax
0x18003ba39  jz      short loc_18003BA5C
0x18003ba3b  test    byte ptr [rcx+1Ch], 1
0x18003ba3f  jz      short loc_18003BA5C
0x18003ba41  cmp     byte ptr [rcx+19h], 5
0x18003ba45  jb      short loc_18003BA5C
0x18003ba47  mov     edx, 55h ; 'U'
0x18003ba4c  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003ba53  mov     rcx, [rcx+10h]
0x18003ba57  call    WPP_SF_
0x18003ba5c  xor     r14d, r14d
0x18003ba5f  mov     [rbp+390h+var_3F0], r14
0x18003ba63  lea     rax, [rbp+390h+var_3F0]
0x18003ba67  mov     [rsp+490h+pdwReturnedProductType], rax
0x18003ba6c  mov     r9d, 2001Fh
0x18003ba72  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM"
0x18003ba79  mov     rcx, 0FFFFFFFF80000002h
0x18003ba80  call    DLRegOpenKeyExW
0x18003ba85  test    eax, eax
0x18003ba87  jz      short loc_18003BA9C
0x18003ba89  jle     loc_18003C140
0x18003ba8f  movzx   eax, ax
0x18003ba92  or      eax, 80070000h
0x18003ba97  jmp     loc_18003C140
0x18003ba9c  mov     rax, [rbp+390h+var_3F0]
0x18003baa0  mov     [rbp+390h+var_3D8], r14b
0x18003baa4  lea     rcx, DLRegCloseKey
0x18003baab  mov     [rbp+390h+var_3D0], rcx
0x18003baaf  mov     [rbp+390h+var_3C8], rax
0x18003bab3  lea     rdx, ?m_ReportCritSec@CRepositoryCorruption@@2VCCritSec@@A; CCritSec CRepositoryCorruption::m_ReportCritSec
0x18003baba  lea     rcx, [rbp+390h+var_3E0]
0x18003babe  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003bac4  nop
0x18003bac5  lea     r13, ??$deletePtr@G@@YAXPEBG@Z; deletePtr<ushort>(ushort const *)
0x18003bacc  mov     r15d, 104h
0x18003bad2  cmp     cs:?m_pPendingCorruptionReport@CRepositoryCorruption@@2PEAUWMIRepositoryCorruptionReport@@EA, r14; WMIRepositoryCorruptionReport * CRepositoryCorruption::m_pPendingCorruptionReport
0x18003bad9  jnz     loc_18003BC14
0x18003badf  mov     ecx, r14d
0x18003bae2  xor     eax, eax
0x18003bae4  lock cmpxchg cs:?m_dwCorruptionType@CRepositoryCorruption@@2JA, ecx; long CRepositoryCorruption::m_dwCorruptionType
0x18003baec  mov     ebx, eax
0x18003baee  jnz     short loc_18003BAF8
0x18003baf0  mov     ebx, r14d
0x18003baf3  jmp     loc_18003BC82
0x18003baf8  mov     [rsp+490h+var_418], r14d
0x18003bafd  mov     [rsp+490h+var_414], r14d
0x18003bb02  mov     [rbp+390h+var_3E8], 4
0x18003bb09  lea     rax, [rbp+390h+var_3E8]
0x18003bb0d  mov     [rsp+490h+var_468], rax
0x18003bb12  lea     rax, [rsp+490h+var_414]
0x18003bb17  mov     [rsp+490h+pdwReturnedProductType], rax
0x18003bb1c  lea     r9, [rsp+490h+var_418]
0x18003bb21  lea     rdx, aRepositorycorr; "RepositoryCorruptionReported"
0x18003bb28  mov     rcx, [rbp+390h+var_3F0]
0x18003bb2c  call    DLRegQueryValueExW
0x18003bb31  test    eax, eax
0x18003bb33  jnz     short loc_18003BB47
0x18003bb35  cmp     [rsp+490h+var_418], 4
0x18003bb3a  jnz     short loc_18003BB47
0x18003bb3c  cmp     [rsp+490h+var_414], r14d
0x18003bb41  jnz     loc_18003BC14
0x18003bb47  cmp     cs:dword_180058AFC, r14d
0x18003bb4e  jz      short loc_18003BB5C
0x18003bb50  lea     rcx, qword_180058B00; this
0x18003bb57  call    ?Checkpoint@CPageSource@@QEAAK_N@Z; CPageSource::Checkpoint(bool)
0x18003bb5c  mov     r12d, 214h
0x18003bb62  mov     ecx, r12d
0x18003bb65  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003bb6b  mov     rdi, rax
0x18003bb6e  test    rax, rax
0x18003bb71  jz      loc_18003BC7D
0x18003bb77  mov     r8d, r12d; Size
0x18003bb7a  xor     edx, edx; Val
0x18003bb7c  mov     rcx, rax; void *
0x18003bb7f  call    memset_0
0x18003bb84  mov     [rsp+490h+var_448], r14b
0x18003bb89  mov     [rsp+490h+var_440], r13
0x18003bb8e  mov     [rsp+490h+var_438], rdi
0x18003bb93  mov     r8d, r15d; nSize
0x18003bb96  mov     rdx, rdi; lpDst
0x18003bb99  lea     rcx, Src; "%windir%\\system32\\wbem\\repository\\C"...
0x18003bba0  call    cs:__imp_ExpandEnvironmentStringsW
0x18003bba6  cmp     eax, r15d
0x18003bba9  jb      short loc_18003BBBF
0x18003bbab  lea     rcx, [rsp+490h+var_448]
0x18003bbb0  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003bbb5  mov     ebx, 8007007Ah
0x18003bbba  jmp     loc_18003BC82
0x18003bbbf  mov     [rdi+208h], ebx
0x18003bbc5  mov     eax, cs:?m_dwImproperShutdownFlag@CRepositoryCorruption@@2KA; ulong CRepositoryCorruption::m_dwImproperShutdownFlag
0x18003bbcb  mov     [rdi+210h], eax
0x18003bbd1  mov     eax, cs:?m_bCalledByStartup@CRepositoryCorruption@@2JA; long CRepositoryCorruption::m_bCalledByStartup
0x18003bbd7  mov     [rdi+20Ch], eax
0x18003bbdd  xor     r8d, r8d; unsigned __int16 *
0x18003bbe0  mov     rdx, rdi; unsigned __int16 *
0x18003bbe3  call    ?PackageRepository@CRepositoryPackager@@QEAAJPEBG0@Z; CRepositoryPackager::PackageRepository(ushort const *,ushort const *)
0x18003bbe8  mov     ebx, eax
0x18003bbea  test    eax, eax
0x18003bbec  jns     short loc_18003BBFD
0x18003bbee  lea     rcx, [rsp+490h+var_448]
0x18003bbf3  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003bbf8  jmp     loc_18003BC82
0x18003bbfd  mov     cs:?m_pPendingCorruptionReport@CRepositoryCorruption@@2PEAUWMIRepositoryCorruptionReport@@EA, rdi; WMIRepositoryCorruptionReport * CRepositoryCorruption::m_pPendingCorruptionReport
0x18003bc04  mov     [rsp+490h+var_448], 1
0x18003bc09  lea     rcx, [rsp+490h+var_448]
0x18003bc0e  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003bc13  nop
0x18003bc14  lea     rcx, [rbp+390h+var_3E0]
0x18003bc18  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003bc1e  test    sil, sil
0x18003bc21  jnz     loc_18003C132
0x18003bc27  mov     rdi, cs:?m_pPendingCorruptionReport@CRepositoryCorruption@@2PEAUWMIRepositoryCorruptionReport@@EA; WMIRepositoryCorruptionReport * CRepositoryCorruption::m_pPendingCorruptionReport
0x18003bc2e  test    rdi, rdi
0x18003bc31  jz      loc_18003C132
0x18003bc37  mov     [rsp+490h+var_430], r14b
0x18003bc3c  mov     [rsp+490h+var_428], r13
0x18003bc41  mov     [rsp+490h+var_420], rdi
0x18003bc46  mov     cs:?m_pPendingCorruptionReport@CRepositoryCorruption@@2PEAUWMIRepositoryCorruptionReport@@EA, r14; WMIRepositoryCorruptionReport * CRepositoryCorruption::m_pPendingCorruptionReport
0x18003bc4d  mov     r8d, r15d; nSize
0x18003bc50  lea     rdx, [rbp+390h+Dst]; lpDst
0x18003bc57  lea     rcx, aWindirSystem32_0; "%windir%\\system32\\wbem\\repository\\S"...
0x18003bc5e  call    cs:__imp_ExpandEnvironmentStringsW
0x18003bc64  cmp     eax, r15d
0x18003bc67  jb      short loc_18003BC91
0x18003bc69  lea     rcx, [rsp+490h+var_430]
0x18003bc6e  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003bc73  mov     ebx, 8007007Ah
0x18003bc78  jmp     loc_18003C135
0x18003bc7d  mov     ebx, 80041006h
0x18003bc82  lea     rcx, [rbp+390h+var_3E0]
0x18003bc86  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003bc8c  jmp     loc_18003C135
0x18003bc91  lea     rcx, ModuleName; "wmisvc.dll"
0x18003bc98  call    cs:__imp_GetModuleHandleW
0x18003bc9e  test    rax, rax
0x18003bca1  jz      loc_18003C121
0x18003bca7  lea     rdx, aGetsystemevent; "GetSystemEventsForShutdown"
0x18003bcae  mov     rcx, rax; hModule
0x18003bcb1  call    cs:__imp_GetProcAddress
0x18003bcb7  test    rax, rax
0x18003bcba  jz      loc_18003C121
0x18003bcc0  lea     rcx, [rbp+390h+Dst]
0x18003bcc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bccc  mov     ebx, eax
0x18003bcce  test    eax, eax
0x18003bcd0  jns     short loc_18003BCE1
0x18003bcd2  lea     rcx, [rsp+490h+var_430]
0x18003bcd7  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003bcdc  jmp     loc_18003C135
0x18003bce1  xor     r8d, r8d; dwFlags
0x18003bce4  xor     edx, edx; hFile
0x18003bce6  lea     rcx, aWerDll; "wer.dll"
0x18003bced  call    cs:__imp_LoadLibraryExW
0x18003bcf3  mov     rbx, rax
0x18003bcf6  test    rax, rax
0x18003bcf9  jnz     short loc_18003BD12
0x18003bcfb  call    cs:__imp_GetLastError
0x18003bd01  mov     ebx, eax
0x18003bd03  test    eax, eax
0x18003bd05  jle     short loc_18003BCD2
0x18003bd07  movzx   ebx, ax
0x18003bd0a  or      ebx, 80070000h
0x18003bd10  jmp     short loc_18003BCD2
0x18003bd12  mov     rax, cs:__imp_FreeLibrary
0x18003bd19  mov     [rbp+390h+var_408], r14b
0x18003bd1d  mov     [rbp+390h+var_400], rax
0x18003bd21  mov     [rbp+390h+var_3F8], rbx
0x18003bd25  lea     rdx, aWerreportcreat; "WerReportCreate"
0x18003bd2c  mov     rcx, rbx; hModule
0x18003bd2f  call    cs:__imp_GetProcAddress
0x18003bd35  mov     r12, rax
0x18003bd38  lea     rdx, aWerreportaddfi; "WerReportAddFile"
0x18003bd3f  mov     rcx, rbx; hModule
0x18003bd42  call    cs:__imp_GetProcAddress
0x18003bd48  mov     r14, rax
0x18003bd4b  lea     rdx, aWerreportsetpa; "WerReportSetParameter"
0x18003bd52  mov     rcx, rbx; hModule
0x18003bd55  call    cs:__imp_GetProcAddress
0x18003bd5b  mov     rsi, rax
0x18003bd5e  lea     rdx, aWerreportsubmi; "WerReportSubmit"
0x18003bd65  mov     rcx, rbx; hModule
0x18003bd68  call    cs:__imp_GetProcAddress
0x18003bd6e  mov     r13, rax
0x18003bd71  lea     rdx, aWerreportclose; "WerReportCloseHandle"
0x18003bd78  mov     rcx, rbx; hModule
0x18003bd7b  call    cs:__imp_GetProcAddress
0x18003bd81  mov     r15, rax
0x18003bd84  test    r12, r12
0x18003bd87  jz      loc_18003C117
0x18003bd8d  test    r14, r14
0x18003bd90  jz      loc_18003C117
0x18003bd96  test    rsi, rsi
0x18003bd99  jz      loc_18003C117
0x18003bd9f  test    r13, r13
0x18003bda2  jz      loc_18003C117
0x18003bda8  test    rax, rax
0x18003bdab  jz      loc_18003C117
0x18003bdb1  mov     [rsp+490h+var_450], 0
0x18003bdba  lea     r9, [rsp+490h+var_450]
0x18003bdbf  xor     r8d, r8d
0x18003bdc2  xor     edx, edx
0x18003bdc4  lea     rcx, aWmiinconsisten; "WMIInconsistentRepository"
0x18003bdcb  mov     rax, r12
0x18003bdce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdd3  mov     ebx, eax
0x18003bdd5  test    eax, eax
0x18003bdd7  jns     short loc_18003BDE7
0x18003bdd9  lea     rcx, [rbp+390h+var_408]
0x18003bddd  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003bde2  jmp     loc_18003BCD2
0x18003bde7  mov     rcx, [rsp+490h+var_450]
0x18003bdec  mov     [rsp+490h+var_448], 0
0x18003bdf1  mov     [rsp+490h+var_440], r15
0x18003bdf6  mov     [rsp+490h+var_438], rcx
0x18003bdfb  mov     r15d, 1
0x18003be01  mov     r9d, r15d
0x18003be04  lea     r12d, [r15+4]
0x18003be08  mov     r8d, r12d
0x18003be0b  mov     rdx, rdi
0x18003be0e  mov     rax, r14
0x18003be11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be16  mov     ebx, eax
0x18003be18  test    eax, eax
0x18003be1a  jns     short loc_18003BE28
0x18003be1c  lea     rcx, [rsp+490h+var_448]
0x18003be21  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18003be26  jmp     short loc_18003BDD9
0x18003be28  mov     r9d, r15d
0x18003be2b  mov     r8d, r12d
0x18003be2e  lea     rdx, [rbp+390h+Dst]
0x18003be35  mov     rcx, [rsp+490h+var_450]
0x18003be3a  mov     rax, r14
0x18003be3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be42  mov     ebx, eax
0x18003be44  test    eax, eax
0x18003be46  js      short loc_18003BE1C
0x18003be48  xor     edx, edx; Val
0x18003be4a  mov     r8d, 118h; Size
0x18003be50  lea     rcx, [rbp+390h+VersionInformation.dwMajorVersion]; void *
0x18003be54  call    memset_0
0x18003be59  mov     [rbp+390h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18003be60  lea     rcx, [rbp+390h+VersionInformation]; lpVersionInformation
0x18003be64  call    cs:__imp_GetVersionExW
0x18003be6a  test    eax, eax
0x18003be6c  jnz     short loc_18003BE85
0x18003be6e  call    cs:__imp_GetLastError
0x18003be74  mov     ebx, eax
0x18003be76  test    eax, eax
0x18003be78  jle     short loc_18003BE1C
0x18003be7a  movzx   ebx, ax
0x18003be7d  or      ebx, 80070000h
0x18003be83  jmp     short loc_18003BE1C
0x18003be85  mov     eax, dword ptr cs:a0; "0"
0x18003be8b  mov     dword ptr [rbp+390h+var_2A0], eax
0x18003be91  xorps   xmm0, xmm0
0x18003be94  xor     eax, eax
0x18003be96  movups  [rbp+390h+var_29C], xmm0
0x18003be9d  movups  [rbp+390h+var_28C], xmm0
0x18003bea4  movups  [rbp+390h+var_27C], xmm0
0x18003beab  mov     [rbp+390h+var_26C], rax
0x18003beb2  lea     edx, [rax+1Eh]; unsigned int
0x18003beb5  lea     rcx, [rbp+390h+var_2A0]; unsigned __int16 *
0x18003bebc  call    ?GetWmiVersion@@YAJQEAGK@Z; GetWmiVersion(ushort * const,ulong)
0x18003bec1  xor     eax, eax
0x18003bec3  mov     word ptr [rbp+390h+var_26C+6], ax
0x18003beca  lea     rax, [rbp+390h+var_2A0]
0x18003bed1  mov     [rsp+490h+var_460], rax
0x18003bed6  mov     eax, [rbp+390h+VersionInformation.dwBuildNumber]
0x18003bed9  mov     dword ptr [rsp+490h+var_468], eax
0x18003bedd  mov     eax, [rbp+390h+VersionInformation.dwMinorVersion]
0x18003bee0  mov     dword ptr [rsp+490h+pdwReturnedProductType], eax
0x18003bee4  mov     r9d, [rbp+390h+VersionInformation.dwMajorVersion]
0x18003bee8  lea     r8, aDDDS; "%d.%d.%d.%s"
0x18003beef  mov     r14d, 104h
0x18003bef5  mov     edx, r14d; unsigned __int64
0x18003bef8  lea     rcx, [rbp+390h+Dst]; unsigned __int16 *
0x18003beff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bf04  lea     r9, [rbp+390h+Dst]
0x18003bf0b  lea     r8, aVersion; "Version"
0x18003bf12  xor     edx, edx
0x18003bf14  mov     rcx, [rsp+490h+var_450]
0x18003bf19  mov     rax, rsi
0x18003bf1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf21  mov     ebx, eax
  ... truncated ...
```
