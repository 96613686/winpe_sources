# CbsCoreLoadComponentStore

- ea: `0x180056400`
- end: `0x18005681b`
- name: `CbsCoreLoadComponentStore`
- size: `1051`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002641c`
- `0x1800adf44`
- `0x1800f8cd0`
- `0x18012e6d0`

## callees

- `0x180013250`
- `0x180013280`
- `0x180016d40`
- `0x180033d50`
- `0x180043d50`
- `0x1800442fc`
- `0x18004854c`
- `0x180056400`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ae508`
- `0x1800eb920`
- `0x1800f1eb4`
- `0x18012d748`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564fb`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800565e7`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800565e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800564b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800564e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800564b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800564e7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800565ff`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800565ff`

## string_xrefs

- `0x180056494`: `COMPONENTS`
- `0x1800565dd`: `COMPONENTS`
- `0x1800566bc`: `COMPONENTS`
- `0x18005651a`: `Failed to get SystemWindowsDirectory path`
- `0x18005646e`: `Unexpected component layer access.`
- `0x180056658`: `Failed to load the COMPONENTS hive from '{}' into registry key 'HKLM\COMPONENTS'.`
- `0x1800566e8`: `Failed to open the root regkey of HKLM\COMPONENTS.`
- `0x1800565a9`: `\System32\config\COMPONENTS`
- `0x180056613`: `Unable to load COMPONENTS hive with ERROR_SHARING_VIOLATION, retry #{}`

## pseudocode

```c
__int64 CbsCoreLoadComponentStore()
{
  int v0; // esi
  HKEY *v1; // rax
  __int64 SystemWindowsDirectoryW; // rdi
  int v3; // eax
  unsigned int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  UINT v7; // eax
  signed int LastError; // ebx
  int v9; // edx
  unsigned int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  const WCHAR *v14; // rbx
  LSTATUS KeyW; // edi
  int v16; // edx
  HKEY *v17; // rax
  int v18; // eax
  int v19; // edx
  int v20; // eax
  int v21; // edx
  unsigned int v23; // [rsp+20h] [rbp-58h]
  char v24[8]; // [rsp+30h] [rbp-48h] BYREF
  int v25[2]; // [rsp+38h] [rbp-40h] BYREF
  LPWSTR lpBuffer; // [rsp+40h] [rbp-38h] BYREF
  __int64 v27; // [rsp+48h] [rbp-30h] BYREF
  LPCWSTR lpFile; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v29[2]; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v0 = 0;
  lpFile = 0;
  lpBuffer = 0;
  v27 = 0;
  v31 = 0;
  v24[0] = 1;
  if ( vpfnTiLockProcess )
    vpfnTiLockProcess(0);
  if ( !vbComponentHiveLoaded )
  {
    if ( !CCbsStoreParameters::m_bShouldOnlineComponentHiveBeLoaded )
      LogAdapter::TraceAtLevelHr<long,>(2, 2148468736LL, "Unexpected component layer access.");
    v1 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v27);
    if ( (int)CbsRegOpenKeyWithBackupRestore(HKEY_LOCAL_MACHINE, L"COMPONENTS", 1u, v1) < 0 )
    {
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
      v3 = SczAlloc(&lpBuffer, SystemWindowsDirectoryW);
      v4 = v3;
      if ( v3 < 0 )
      {
        v5 = (unsigned int)v3;
        v6 = 48;
LABEL_38:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v6,
          (unsigned int)"onecore\\base\\cbs\\core\\cbscorestore.cpp",
          (const char *)v5,
          v23);
        goto LABEL_39;
      }
      v7 = GetSystemWindowsDirectoryW(lpBuffer, SystemWindowsDirectoryW);
      if ( !v7 )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get SystemWindowsDirectory path");
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          else
            v10 = LastError;
          v30 = v10;
          LOBYTE(v9) = 1;
          *(_QWORD *)v29 = &v30;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v9,
            3,
            (unsigned int)": {0}",
            (__int64)v29);
        }
        if ( !LastError )
        {
          v4 = 0;
          goto LABEL_39;
        }
        v11 = (unsigned int)LastError;
        v12 = 52;
LABEL_17:
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v12,
               (unsigned int)"onecore\\base\\cbs\\core\\cbscorestore.cpp",
               (const char *)v11,
               v23);
LABEL_39:
        AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v24);
        goto LABEL_49;
      }
      if ( v7 >= (unsigned int)SystemWindowsDirectoryW )
      {
        v4 = -2147024774;
        v6 = 53;
LABEL_37:
        v5 = v4;
        goto LABEL_38;
      }
      v13 = SczAllocConcat2Sz(&lpFile, lpBuffer, L"\\System32\\config\\COMPONENTS");
      v4 = v13;
      if ( v13 < 0 )
      {
        v5 = (unsigned int)v13;
        v6 = 56;
        goto LABEL_38;
      }
      if ( v31 <= 0x14 )
      {
        v14 = lpFile;
        do
        {
          KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"COMPONENTS", v14);
          if ( KeyW != 32 )
            break;
          Sleep(0x1F4u);
          ++v31;
          LogAdapter::TraceAtLevel<unsigned long>(
            1,
            "Unable to load COMPONENTS hive with ERROR_SHARING_VIOLATION, retry #{}",
            &v31);
        }
        while ( v31 <= 0x14 );
        if ( KeyW < 0 )
          __fastfail(7u);
        if ( KeyW )
        {
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v29 = v14;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to load the COMPONENTS hive from '{}' into registry key 'HKLM\\COMPONENTS'.",
              (__int64)v29);
            v30 = (unsigned __int16)KeyW | 0x80070000;
            LOBYTE(v16) = 1;
            *(_QWORD *)v25 = &v30;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v16,
              3,
              (unsigned int)": {0}",
              (__int64)v25);
          }
          v11 = (unsigned int)KeyW;
          v12 = 74;
          goto LABEL_17;
        }
      }
      v17 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v27);
      v18 = CbsRegOpenKeyWithBackupRestore(HKEY_LOCAL_MACHINE, L"COMPONENTS", 1u, v17);
      v4 = v18;
      if ( v18 < 0 )
      {
        v30 = v18;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to open the root regkey of HKLM\\COMPONENTS.");
          *(_QWORD *)v25 = &v30;
          LOBYTE(v19) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v19,
            3,
            (unsigned int)": {}",
            (__int64)v25);
        }
        v6 = 82;
        goto LABEL_37;
      }
    }
    if ( vbNeedsToCheckStoreConsistencyLater )
    {
      vbNeedsToCheckStoreConsistencyLater = 0;
      v0 = 1;
    }
    vbComponentHiveLoaded = 1;
  }
  AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v24);
  if ( v0 && (v20 = CbsCheckStoreConsistency(), v4 = v20, v20 < 0) )
  {
    v30 = v20;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "CSI store consistency check fails.");
      *(_QWORD *)v25 = &v30;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v21,
        3,
        (unsigned int)": {}",
        (__int64)v25);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscorestore.cpp",
      (const char *)v4,
      v23);
  }
  else
  {
    v4 = 0;
  }
LABEL_49:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFile);
  return v4;
}

```

## disassembly

```asm
0x180056400  push    rbp
0x180056402  push    rbx
0x180056403  push    rsi
0x180056404  push    rdi
0x180056405  push    r13
0x180056407  push    r15
0x180056409  mov     rbp, rsp
0x18005640c  sub     rsp, 78h
0x180056410  mov     rax, cs:__security_cookie
0x180056417  xor     rax, rsp
0x18005641a  mov     [rbp+var_10], rax
0x18005641e  mov     rax, cs:?vpfnTiLockProcess@@3P6AHH@ZEA; int (*vpfnTiLockProcess)(int)
0x180056425  xor     esi, esi
0x180056427  mov     [rbp+lpFile], 0
0x18005642f  mov     [rbp+lpBuffer], 0
0x180056437  mov     [rbp+var_30], 0
0x18005643f  mov     [rbp+var_14], 0
0x180056446  lea     r15d, [rsi+1]
0x18005644a  mov     [rbp+var_48], r15b
0x18005644e  test    rax, rax
0x180056451  jz      short loc_18005645A
0x180056453  xor     ecx, ecx
0x180056455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005645a  cmp     cs:?vbComponentHiveLoaded@@3HA, esi; int vbComponentHiveLoaded
0x180056460  jnz     loc_180056761
0x180056466  cmp     cs:?m_bShouldOnlineComponentHiveBeLoaded@CCbsStoreParameters@@2HA, esi; int CCbsStoreParameters::m_bShouldOnlineComponentHiveBeLoaded
0x18005646c  jnz     short loc_180056484
0x18005646e  lea     r8, aUnexpectedComp_1; "Unexpected component layer access."
0x180056475  mov     edx, 800F0800h
0x18005647a  mov     ecx, 2
0x18005647f  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180056484  lea     rcx, [rbp+var_30]
0x180056488  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18005648d  mov     r13, 0FFFFFFFF80000002h
0x180056494  lea     rdx, aComponents; "COMPONENTS"
0x18005649b  mov     rcx, r13; hKey
0x18005649e  mov     r9, rax; HKEY *
0x1800564a1  mov     r8d, r15d; unsigned int
0x1800564a4  call    ?CbsRegOpenKeyWithBackupRestore@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; CbsRegOpenKeyWithBackupRestore(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800564a9  test    eax, eax
0x1800564ab  jns     loc_180056749
0x1800564b1  xor     edx, edx; uSize
0x1800564b3  xor     ecx, ecx; lpBuffer
0x1800564b5  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800564bc  nop     dword ptr [rax+rax+00h]
0x1800564c1  mov     edx, eax
0x1800564c3  lea     rcx, [rbp+lpBuffer]
0x1800564c7  mov     edi, eax
0x1800564c9  call    SczAlloc
0x1800564ce  mov     ebx, eax
0x1800564d0  test    eax, eax
0x1800564d2  jns     short loc_1800564E1
0x1800564d4  mov     r9d, eax
0x1800564d7  mov     edx, 30h ; '0'
0x1800564dc  jmp     loc_18005672B
0x1800564e1  mov     rcx, [rbp+lpBuffer]; lpBuffer
0x1800564e5  mov     edx, edi; uSize
0x1800564e7  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800564ee  nop     dword ptr [rax+rax+00h]
0x1800564f3  test    eax, eax
0x1800564f5  jnz     loc_180056592
0x1800564fb  call    cs:__imp_GetLastError
0x180056502  nop     dword ptr [rax+rax+00h]
0x180056507  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005650e  mov     ebx, eax
0x180056510  test    rcx, rcx
0x180056513  jz      short loc_180056568
0x180056515  mov     esi, 3
0x18005651a  lea     r9, aFailedToGetSys_3; "Failed to get SystemWindowsDirectory pa"...
0x180056521  mov     r8d, esi
0x180056524  xor     edx, edx
0x180056526  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005652b  test    ebx, ebx
0x18005652d  jg      short loc_180056533
0x18005652f  mov     eax, ebx
0x180056531  jmp     short loc_18005653B
0x180056533  movzx   eax, bx
0x180056536  or      eax, 80070000h
0x18005653b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180056542  lea     r9, a0; ": {0}"
0x180056549  mov     [rbp+var_18], eax
0x18005654c  mov     r8d, esi
0x18005654f  lea     rax, [rbp+var_18]
0x180056553  mov     dl, r15b
0x180056556  mov     qword ptr [rbp+var_20], rax
0x18005655a  lea     rax, [rbp+var_20]
0x18005655e  mov     qword ptr [rsp+78h+var_58], rax; unsigned int
0x180056563  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180056568  test    ebx, ebx
0x18005656a  jz      short loc_18005658B
0x18005656c  mov     r9d, ebx; char *
0x18005656f  mov     edx, 34h ; '4'; void *
0x180056574  mov     rcx, [rbp+30h]; this
0x180056578  lea     r8, aOnecoreBaseCbs_32; "onecore\\base\\cbs\\core\\cbscorestore."...
0x18005657f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180056584  mov     ebx, eax
0x180056586  jmp     loc_18005673B
0x18005658b  xor     ebx, ebx
0x18005658d  jmp     loc_18005673B
0x180056592  cmp     eax, edi
0x180056594  jb      short loc_1800565A5
0x180056596  mov     ebx, 8007007Ah
0x18005659b  mov     edx, 35h ; '5'
0x1800565a0  jmp     loc_180056728
0x1800565a5  mov     rdx, [rbp+lpBuffer]
0x1800565a9  lea     r8, aSystem32Config; "\\System32\\config\\COMPONENTS"
0x1800565b0  lea     rcx, [rbp+lpFile]
0x1800565b4  call    SczAllocConcat2Sz
0x1800565b9  mov     ebx, eax
0x1800565bb  test    eax, eax
0x1800565bd  jns     short loc_1800565CC
0x1800565bf  mov     r9d, eax
0x1800565c2  mov     edx, 38h ; '8'
0x1800565c7  jmp     loc_18005672B
0x1800565cc  cmp     [rbp+var_14], 14h
0x1800565d0  ja      loc_1800566B0
0x1800565d6  mov     rbx, [rbp+lpFile]
0x1800565da  mov     r8, rbx; lpFile
0x1800565dd  lea     rdx, aComponents; "COMPONENTS"
0x1800565e4  mov     rcx, r13; hKey
0x1800565e7  call    cs:__imp_RegLoadKeyW
0x1800565ee  nop     dword ptr [rax+rax+00h]
0x1800565f3  mov     edi, eax
0x1800565f5  cmp     eax, 20h ; ' '
0x1800565f8  jnz     short loc_180056628
0x1800565fa  mov     ecx, 1F4h; dwMilliseconds
0x1800565ff  call    cs:__imp_Sleep
0x180056606  nop     dword ptr [rax+rax+00h]
0x18005660b  add     [rbp+var_14], r15d
0x18005660f  lea     r8, [rbp+var_14]
0x180056613  lea     rdx, aUnableToLoadCo; "Unable to load COMPONENTS hive with ERR"...
0x18005661a  mov     ecx, r15d
0x18005661d  call    ??$TraceAtLevel@K@LogAdapter@@YAXW4LogLevel@0@QEBDAEBK@Z; LogAdapter::TraceAtLevel<ulong>(LogAdapter::LogLevel,char const * const,ulong const &)
0x180056622  cmp     [rbp+var_14], 14h
0x180056626  jbe     short loc_1800565DA
0x180056628  test    edi, edi
0x18005662a  jns     short loc_180056635
0x18005662c  mov     ecx, 7
0x180056631  int     29h; Win8: RtlFailFast(ecx)
0x180056633  test    edi, edi
0x180056635  jz      short loc_1800566B0
0x180056637  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005663e  test    rcx, rcx
0x180056641  jz      short loc_1800566A3
0x180056643  lea     rax, [rbp+var_20]
0x180056647  mov     qword ptr [rbp+var_20], rbx
0x18005664b  mov     esi, 3
0x180056650  mov     qword ptr [rsp+78h+var_58], rax
0x180056655  mov     r8d, esi
0x180056658  lea     r9, aFailedToLoadTh; "Failed to load the COMPONENTS hive from"...
0x18005665f  xor     edx, edx
0x180056661  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180056666  test    edi, edi
0x180056668  jg      short loc_18005666E
0x18005666a  mov     eax, edi
0x18005666c  jmp     short loc_180056676
0x18005666e  movzx   eax, di
0x180056671  or      eax, 80070000h
0x180056676  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005667d  lea     r9, a0; ": {0}"
0x180056684  mov     [rbp+var_18], eax
0x180056687  mov     r8d, esi
0x18005668a  lea     rax, [rbp+var_18]
0x18005668e  mov     dl, r15b
0x180056691  mov     qword ptr [rbp+var_40], rax
0x180056695  lea     rax, [rbp+var_40]
0x180056699  mov     qword ptr [rsp+78h+var_58], rax
0x18005669e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800566a3  mov     r9d, edi
0x1800566a6  mov     edx, 4Ah ; 'J'
0x1800566ab  jmp     loc_180056574
0x1800566b0  lea     rcx, [rbp+var_30]
0x1800566b4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800566b9  mov     r9, rax; HKEY *
0x1800566bc  lea     rdx, aComponents; "COMPONENTS"
0x1800566c3  mov     r8d, r15d; unsigned int
0x1800566c6  mov     rcx, r13; hKey
0x1800566c9  call    ?CbsRegOpenKeyWithBackupRestore@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; CbsRegOpenKeyWithBackupRestore(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800566ce  mov     ebx, eax
0x1800566d0  test    eax, eax
0x1800566d2  jns     short loc_180056749
0x1800566d4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800566db  mov     [rbp+var_18], eax
0x1800566de  test    rcx, rcx
0x1800566e1  jz      short loc_180056723
0x1800566e3  mov     esi, 3
0x1800566e8  lea     r9, aFailedToOpenTh_2; "Failed to open the root regkey of HKLM"...
0x1800566ef  mov     r8d, esi
0x1800566f2  xor     edx, edx
0x1800566f4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800566f9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180056700  lea     rax, [rbp+var_18]
0x180056704  mov     qword ptr [rbp+var_40], rax
0x180056708  lea     r9, asc_1802EE7AC; ": {}"
0x18005670f  lea     rax, [rbp+var_40]
0x180056713  mov     r8d, esi
0x180056716  mov     dl, r15b
0x180056719  mov     qword ptr [rsp+78h+var_58], rax; int
0x18005671e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180056723  mov     edx, 52h ; 'R'; void *
0x180056728  mov     r9d, ebx; char *
0x18005672b  mov     rcx, [rbp+30h]; this
0x18005672f  lea     r8, aOnecoreBaseCbs_32; "onecore\\base\\cbs\\core\\cbscorestore."...
0x180056736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005673b  lea     rcx, [rbp+var_48]; this
0x18005673f  call    ??1AutoCsiStoreLock@@QEAA@XZ; AutoCsiStoreLock::~AutoCsiStoreLock(void)
0x180056744  jmp     loc_1800567E4
0x180056749  cmp     cs:?vbNeedsToCheckStoreConsistencyLater@@3HA, esi; int vbNeedsToCheckStoreConsistencyLater
0x18005674f  jz      short loc_18005675A
0x180056751  mov     cs:?vbNeedsToCheckStoreConsistencyLater@@3HA, esi; int vbNeedsToCheckStoreConsistencyLater
0x180056757  mov     esi, r15d
0x18005675a  mov     cs:?vbComponentHiveLoaded@@3HA, r15d; int vbComponentHiveLoaded
0x180056761  lea     rcx, [rbp+var_48]; this
0x180056765  call    ??1AutoCsiStoreLock@@QEAA@XZ; AutoCsiStoreLock::~AutoCsiStoreLock(void)
0x18005676a  test    esi, esi
0x18005676c  jz      short loc_1800567E2
0x18005676e  call    ?CbsCheckStoreConsistency@@YAJXZ; CbsCheckStoreConsistency(void)
0x180056773  mov     ebx, eax
0x180056775  test    eax, eax
0x180056777  jns     short loc_1800567E2
0x180056779  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180056780  mov     [rbp+var_18], eax
0x180056783  test    rcx, rcx
0x180056786  jz      short loc_1800567C8
0x180056788  mov     esi, 3
0x18005678d  lea     r9, aCsiStoreConsis; "CSI store consistency check fails."
0x180056794  mov     r8d, esi
0x180056797  xor     edx, edx
0x180056799  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005679e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800567a5  lea     rax, [rbp+var_18]
0x1800567a9  mov     qword ptr [rbp+var_40], rax
0x1800567ad  lea     r9, asc_1802EE7AC; ": {}"
0x1800567b4  lea     rax, [rbp+var_40]
0x1800567b8  mov     r8d, esi
0x1800567bb  mov     dl, r15b
0x1800567be  mov     qword ptr [rsp+78h+var_58], rax; int
0x1800567c3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800567c8  mov     rcx, [rbp+30h]; this
0x1800567cc  lea     r8, aOnecoreBaseCbs_32; "onecore\\base\\cbs\\core\\cbscorestore."...
0x1800567d3  mov     r9d, ebx; char *
0x1800567d6  mov     edx, 62h ; 'b'; void *
0x1800567db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800567e0  jmp     short loc_1800567E4
0x1800567e2  xor     ebx, ebx
0x1800567e4  lea     rcx, [rbp+var_30]
0x1800567e8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800567ed  lea     rcx, [rbp+lpBuffer]
0x1800567f1  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800567f6  lea     rcx, [rbp+lpFile]
0x1800567fa  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800567ff  mov     eax, ebx
0x180056801  mov     rcx, [rbp+var_10]
0x180056805  xor     rcx, rsp; StackCookie
0x180056808  call    __security_check_cookie
0x18005680d  add     rsp, 78h
0x180056811  pop     r15
0x180056813  pop     r13
0x180056815  pop     rdi
0x180056816  pop     rsi
0x180056817  pop     rbx
0x180056818  pop     rbp
0x180056819  retn
```
