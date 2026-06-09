# TurboContainerLoad(wchar_t const * const,HINSTANCE__ * *)

- ea: `0x1800b32cc`
- end: `0x1800b3684`
- name: `?TurboContainerLoad@@YAJQEB_WPEAPEAUHINSTANCE__@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(const wchar_t *const, HINSTANCE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f3f0c`

## callees

- `0x180013250`
- `0x1800150c0`
- `0x180016d40`
- `0x180034954`
- `0x180049ec0`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800b32cc`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b3462`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b3501`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b35a0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b3462`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b3501`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800b35a0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800b3398`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800b3398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b33bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b347a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b35b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b33bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b347a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b35b8`

## string_xrefs

- `0x1800b35d4`: `Failed to get proc address for GetIMultiSourceUpdateContainer`
- `0x1800b3535`: `Failed to get proc address for GetIPsfUpdateContainer`
- `0x1800b3496`: `Failed to get proc address for GetIUpdateContainer`
- `0x1800b33dd`: `Failed to load TurboContainer DLL: {}`
- `0x1800b3312`: `No core dll path specified`
- `0x1800b34f7`: `GetIPsfUpdateContainer`
- `0x1800b3596`: `GetIMultiSourceUpdateContainer`
- `0x1800b335b`: `turbocontainer.dll`
- `0x1800b3458`: `GetIUpdateContainer`

## pseudocode

```c
__int64 __fastcall TurboContainerLoad(const wchar_t *a1, HINSTANCE *a2)
{
  unsigned int v2; // ebx
  int v3; // edx
  __int64 v4; // r9
  __int64 v5; // rdx
  int v6; // eax
  HMODULE Library; // rax
  HMODULE v8; // rbx
  signed int LastError; // ebx
  int v10; // edx
  unsigned int v11; // eax
  __int64 v12; // rdx
  int v13; // edx
  unsigned int v14; // eax
  int v15; // edx
  unsigned int v16; // eax
  int v17; // edx
  unsigned int v18; // eax
  unsigned int v20; // [rsp+20h] [rbp-40h]
  unsigned int v21[2]; // [rsp+30h] [rbp-30h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-28h] BYREF
  int v23; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpLibFileName; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  lpLibFileName = 0;
  hModule = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    v23 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No core dll path specified");
      *(_QWORD *)v21 = &v23;
      LOBYTE(v3) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)v21);
    }
    v4 = 2147942487LL;
    v5 = 13;
    goto LABEL_7;
  }
  v6 = SczAllocConcat2Sz(&lpLibFileName, a1, L"turbocontainer.dll");
  v2 = v6;
  if ( v6 >= 0 )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 8u);
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hModule, Library);
    v8 = hModule;
    if ( hModule )
    {
      vpfnGetIUpdateContainer = (__int64)GetProcAddress(hModule, "GetIUpdateContainer");
      if ( vpfnGetIUpdateContainer )
      {
        vpfnGetIPsfUpdateContainer = (__int64)GetProcAddress(v8, "GetIPsfUpdateContainer");
        if ( vpfnGetIPsfUpdateContainer )
        {
          vpfnGetIMultiSourceUpdateContainer = (__int64)GetProcAddress(v8, "GetIMultiSourceUpdateContainer");
          if ( vpfnGetIMultiSourceUpdateContainer )
          {
            hModule = 0;
            vhTurboContainerDll = v8;
            CBSWdsLog(0x4000000, 0, 0, "TurboContainer load Successful");
          }
          else
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to get proc address for GetIMultiSourceUpdateContainer");
              if ( LastError > 0 )
                v18 = (unsigned __int16)LastError | 0x80070000;
              else
                v18 = LastError;
              v23 = v18;
              LOBYTE(v17) = 1;
              *(_QWORD *)v21 = &v23;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v17,
                3,
                (unsigned int)": {0}",
                (__int64)v21);
            }
            if ( LastError )
            {
              v12 = 34;
              goto LABEL_16;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to get proc address for GetIPsfUpdateContainer");
            if ( LastError > 0 )
              v16 = (unsigned __int16)LastError | 0x80070000;
            else
              v16 = LastError;
            v23 = v16;
            LOBYTE(v15) = 1;
            *(_QWORD *)v21 = &v23;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v15,
              3,
              (unsigned int)": {0}",
              (__int64)v21);
          }
          if ( LastError )
          {
            v12 = 31;
            goto LABEL_16;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to get proc address for GetIUpdateContainer");
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
          else
            v14 = LastError;
          v23 = v14;
          LOBYTE(v13) = 1;
          *(_QWORD *)v21 = &v23;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v13,
            3,
            (unsigned int)": {0}",
            (__int64)v21);
        }
        if ( LastError )
        {
          v12 = 28;
          goto LABEL_16;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to load TurboContainer DLL: {}",
          (__int64)&lpLibFileName);
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        else
          v11 = LastError;
        v23 = v11;
        LOBYTE(v10) = 1;
        *(_QWORD *)v21 = &v23;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v10,
          3,
          (unsigned int)": {0}",
          (__int64)v21);
      }
      if ( LastError )
      {
        v12 = 25;
LABEL_16:
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v12,
               (unsigned int)"onecore\\base\\cbs\\core\\cbsturbocontainerwrapper.cpp",
               (const char *)(unsigned int)LastError,
               v20);
        goto LABEL_43;
      }
    }
    v2 = 0;
    goto LABEL_43;
  }
  v4 = (unsigned int)v6;
  v5 = 19;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsturbocontainerwrapper.cpp",
    (const char *)v4,
    v20);
LABEL_43:
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  return v2;
}

```

## disassembly

```asm
0x1800b32cc  mov     [rsp-8+arg_8], rbx
0x1800b32d1  push    rbp
0x1800b32d2  mov     rbp, rsp
0x1800b32d5  sub     rsp, 60h
0x1800b32d9  mov     rax, cs:__security_cookie
0x1800b32e0  xor     rax, rsp
0x1800b32e3  mov     [rbp+var_10], rax
0x1800b32e7  mov     [rbp+lpLibFileName], 0
0x1800b32ef  mov     [rbp+hModule], 0
0x1800b32f7  test    rcx, rcx
0x1800b32fa  jnz     short loc_1800B3358
0x1800b32fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b3303  mov     ebx, 80070057h
0x1800b3308  mov     [rbp+var_20], ebx
0x1800b330b  test    rcx, rcx
0x1800b330e  jz      short loc_1800B334E
0x1800b3310  xor     edx, edx
0x1800b3312  lea     r9, aNoCoreDllPathS; "No core dll path specified"
0x1800b3319  lea     r8d, [rdx+3]
0x1800b331d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b3322  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b3329  lea     rax, [rbp+var_20]
0x1800b332d  mov     qword ptr [rbp+var_30], rax
0x1800b3331  lea     r9, asc_1802EE7AC; ": {}"
0x1800b3338  lea     rax, [rbp+var_30]
0x1800b333c  mov     r8d, 3
0x1800b3342  mov     dl, 1
0x1800b3344  mov     qword ptr [rsp+60h+var_40], rax
0x1800b3349  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b334e  mov     r9d, ebx
0x1800b3351  mov     edx, 0Dh
0x1800b3356  jmp     short loc_1800B3379
0x1800b3358  mov     rdx, rcx
0x1800b335b  lea     r8, aTurbocontainer_4; "turbocontainer.dll"
0x1800b3362  lea     rcx, [rbp+lpLibFileName]
0x1800b3366  call    SczAllocConcat2Sz
0x1800b336b  mov     ebx, eax
0x1800b336d  test    eax, eax
0x1800b336f  jns     short loc_1800B338E
0x1800b3371  mov     r9d, eax; char *
0x1800b3374  mov     edx, 13h; void *
0x1800b3379  mov     rcx, [rbp+8]; this
0x1800b337d  lea     r8, aOnecoreBaseCbs_95; "onecore\\base\\cbs\\core\\cbsturboconta"...
0x1800b3384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3389  jmp     loc_1800B3658
0x1800b338e  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800b3392  xor     edx, edx; hFile
0x1800b3394  lea     r8d, [rdx+8]; dwFlags
0x1800b3398  call    cs:__imp_LoadLibraryExW
0x1800b339f  nop     dword ptr [rax+rax+00h]
0x1800b33a4  mov     rdx, rax
0x1800b33a7  lea     rcx, [rbp+hModule]
0x1800b33ab  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800b33b0  mov     rbx, [rbp+hModule]
0x1800b33b4  test    rbx, rbx
0x1800b33b7  jnz     loc_1800B3458
0x1800b33bd  call    cs:__imp_GetLastError
0x1800b33c4  nop     dword ptr [rax+rax+00h]
0x1800b33c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b33d0  mov     ebx, eax
0x1800b33d2  test    rcx, rcx
0x1800b33d5  jz      short loc_1800B3431
0x1800b33d7  xor     edx, edx
0x1800b33d9  lea     rax, [rbp+lpLibFileName]
0x1800b33dd  lea     r9, aFailedToLoadTu; "Failed to load TurboContainer DLL: {}"
0x1800b33e4  mov     qword ptr [rsp+60h+var_40], rax
0x1800b33e9  lea     r8d, [rdx+3]
0x1800b33ed  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b33f2  test    ebx, ebx
0x1800b33f4  jg      short loc_1800B33FA
0x1800b33f6  mov     eax, ebx
0x1800b33f8  jmp     short loc_1800B3402
0x1800b33fa  movzx   eax, bx
0x1800b33fd  or      eax, 80070000h
0x1800b3402  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b3409  lea     r9, a0; ": {0}"
0x1800b3410  mov     [rbp+var_20], eax
0x1800b3413  mov     r8d, 3
0x1800b3419  lea     rax, [rbp+var_20]
0x1800b341d  mov     dl, 1
0x1800b341f  mov     qword ptr [rbp+var_30], rax
0x1800b3423  lea     rax, [rbp+var_30]
0x1800b3427  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x1800b342c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b3431  test    ebx, ebx
0x1800b3433  jz      loc_1800B3656
0x1800b3439  mov     edx, 19h; void *
0x1800b343e  mov     rcx, [rbp+8]; this
0x1800b3442  lea     r8, aOnecoreBaseCbs_95; "onecore\\base\\cbs\\core\\cbsturboconta"...
0x1800b3449  mov     r9d, ebx; char *
0x1800b344c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b3451  mov     ebx, eax
0x1800b3453  jmp     loc_1800B3658
0x1800b3458  lea     rdx, aGetiupdatecont; "GetIUpdateContainer"
0x1800b345f  mov     rcx, rbx; hModule
0x1800b3462  call    cs:__imp_GetProcAddress
0x1800b3469  nop     dword ptr [rax+rax+00h]
0x1800b346e  mov     cs:?vpfnGetIUpdateContainer@@3P6AJQEB_WPEAPEAVIUpdateContainer@@@_EEA, rax
0x1800b3475  test    rax, rax
0x1800b3478  jnz     short loc_1800B34F7
0x1800b347a  call    cs:__imp_GetLastError
0x1800b3481  nop     dword ptr [rax+rax+00h]
0x1800b3486  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b348d  mov     ebx, eax
0x1800b348f  test    rcx, rcx
0x1800b3492  jz      short loc_1800B34E5
0x1800b3494  xor     edx, edx
0x1800b3496  lea     r9, aFailedToGetPro_3; "Failed to get proc address for GetIUpda"...
0x1800b349d  lea     r8d, [rdx+3]
0x1800b34a1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b34a6  test    ebx, ebx
0x1800b34a8  jg      short loc_1800B34AE
0x1800b34aa  mov     eax, ebx
0x1800b34ac  jmp     short loc_1800B34B6
0x1800b34ae  movzx   eax, bx
0x1800b34b1  or      eax, 80070000h
0x1800b34b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b34bd  lea     r9, a0; ": {0}"
0x1800b34c4  mov     [rbp+var_20], eax
0x1800b34c7  mov     r8d, 3
0x1800b34cd  lea     rax, [rbp+var_20]
0x1800b34d1  mov     dl, 1
0x1800b34d3  mov     qword ptr [rbp+var_30], rax
0x1800b34d7  lea     rax, [rbp+var_30]
0x1800b34db  mov     qword ptr [rsp+60h+var_40], rax
0x1800b34e0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b34e5  test    ebx, ebx
0x1800b34e7  jz      loc_1800B3656
0x1800b34ed  mov     edx, 1Ch
0x1800b34f2  jmp     loc_1800B343E
0x1800b34f7  lea     rdx, aGetipsfupdatec; "GetIPsfUpdateContainer"
0x1800b34fe  mov     rcx, rbx; hModule
0x1800b3501  call    cs:__imp_GetProcAddress
0x1800b3508  nop     dword ptr [rax+rax+00h]
0x1800b350d  mov     cs:?vpfnGetIPsfUpdateContainer@@3P6AJQEB_WPEAPEAVIPsfUpdateContainer@@@_EEA, rax
0x1800b3514  test    rax, rax
0x1800b3517  jnz     short loc_1800B3596
0x1800b3519  call    cs:__imp_GetLastError
0x1800b3520  nop     dword ptr [rax+rax+00h]
0x1800b3525  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b352c  mov     ebx, eax
0x1800b352e  test    rcx, rcx
0x1800b3531  jz      short loc_1800B3584
0x1800b3533  xor     edx, edx
0x1800b3535  lea     r9, aFailedToGetPro_57; "Failed to get proc address for GetIPsfU"...
0x1800b353c  lea     r8d, [rdx+3]
0x1800b3540  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b3545  test    ebx, ebx
0x1800b3547  jg      short loc_1800B354D
0x1800b3549  mov     eax, ebx
0x1800b354b  jmp     short loc_1800B3555
0x1800b354d  movzx   eax, bx
0x1800b3550  or      eax, 80070000h
0x1800b3555  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b355c  lea     r9, a0; ": {0}"
0x1800b3563  mov     [rbp+var_20], eax
0x1800b3566  mov     r8d, 3
0x1800b356c  lea     rax, [rbp+var_20]
0x1800b3570  mov     dl, 1
0x1800b3572  mov     qword ptr [rbp+var_30], rax
0x1800b3576  lea     rax, [rbp+var_30]
0x1800b357a  mov     qword ptr [rsp+60h+var_40], rax
0x1800b357f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b3584  test    ebx, ebx
0x1800b3586  jz      loc_1800B3656
0x1800b358c  mov     edx, 1Fh
0x1800b3591  jmp     loc_1800B343E
0x1800b3596  lea     rdx, aGetimultisourc; "GetIMultiSourceUpdateContainer"
0x1800b359d  mov     rcx, rbx; hModule
0x1800b35a0  call    cs:__imp_GetProcAddress
0x1800b35a7  nop     dword ptr [rax+rax+00h]
0x1800b35ac  mov     cs:?vpfnGetIMultiSourceUpdateContainer@@3P6AJPEAPEAVIMultiSourceUpdateContainer@@@_EEA, rax
0x1800b35b3  test    rax, rax
0x1800b35b6  jnz     short loc_1800B3631
0x1800b35b8  call    cs:__imp_GetLastError
0x1800b35bf  nop     dword ptr [rax+rax+00h]
0x1800b35c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b35cb  mov     ebx, eax
0x1800b35cd  test    rcx, rcx
0x1800b35d0  jz      short loc_1800B3623
0x1800b35d2  xor     edx, edx
0x1800b35d4  lea     r9, aFailedToGetPro_33; "Failed to get proc address for GetIMult"...
0x1800b35db  lea     r8d, [rdx+3]
0x1800b35df  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800b35e4  test    ebx, ebx
0x1800b35e6  jg      short loc_1800B35EC
0x1800b35e8  mov     eax, ebx
0x1800b35ea  jmp     short loc_1800B35F4
0x1800b35ec  movzx   eax, bx
0x1800b35ef  or      eax, 80070000h
0x1800b35f4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b35fb  lea     r9, a0; ": {0}"
0x1800b3602  mov     [rbp+var_20], eax
0x1800b3605  mov     r8d, 3
0x1800b360b  lea     rax, [rbp+var_20]
0x1800b360f  mov     dl, 1
0x1800b3611  mov     qword ptr [rbp+var_30], rax
0x1800b3615  lea     rax, [rbp+var_30]
0x1800b3619  mov     qword ptr [rsp+60h+var_40], rax
0x1800b361e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b3623  test    ebx, ebx
0x1800b3625  jz      short loc_1800B3656
0x1800b3627  mov     edx, 22h ; '"'
0x1800b362c  jmp     loc_1800B343E
0x1800b3631  lea     r9, aTurbocontainer_0; "TurboContainer load Successful"
0x1800b3638  mov     [rbp+hModule], 0
0x1800b3640  xor     r8d, r8d
0x1800b3643  mov     cs:?vhTurboContainerDll@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * vhTurboContainerDll
0x1800b364a  xor     edx, edx
0x1800b364c  mov     ecx, 4000000h
0x1800b3651  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1800b3656  xor     ebx, ebx
0x1800b3658  lea     rcx, [rbp+hModule]
0x1800b365c  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800b3661  lea     rcx, [rbp+lpLibFileName]
0x1800b3665  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b366a  mov     eax, ebx
0x1800b366c  mov     rcx, [rbp+var_10]
0x1800b3670  xor     rcx, rsp; StackCookie
0x1800b3673  call    __security_check_cookie
0x1800b3678  mov     rbx, [rsp+60h+arg_8]
0x1800b367d  add     rsp, 60h
0x1800b3681  pop     rbp
0x1800b3682  retn
```
