# CoreResourcesLoad(wchar_t const * const,int)

- ea: `0x180064cb0`
- end: `0x180064fc5`
- name: `?CoreResourcesLoad@@YAJQEB_WH@Z`
- size: `789`
- prototype: `__int64 __fastcall(const wchar_t *const, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x1800f3f0c`

## callees

- `0x180010f54`
- `0x180011094`
- `0x180013250`
- `0x180015420`
- `0x180016d40`
- `0x18005aa38`
- `0x180064cb0`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800eb920`
- `0x1800ec920`
- `0x18010c194`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180064ee7`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180064f3b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180064ee7`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180064f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180064d7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180064d7b`

## string_xrefs

- `0x180064eb7`: `CbsMsg.dll`
- `0x180064f0c`: `CbsMsg.dll`
- `0x180064d16`: `CoreResources have already been initialized.`
- `0x180064dae`: `Failed to get windows directory for CoreResources path.`
- `0x180064f80`: `Unable to load cbsmsg DLL: {}`

## pseudocode

```c
__int64 __fastcall CoreResourcesLoad(const wchar_t *a1)
{
  int v1; // edi
  unsigned int v3; // ebx
  int v4; // edx
  __int64 v5; // rdx
  UINT SystemWindowsDirectoryW; // eax
  signed int v7; // ebx
  int v8; // edx
  unsigned int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  HMODULE Library; // rax
  DWORD LastError; // eax
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  unsigned int v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[24]; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpLibFileName; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v1 = vbOfflineStack;
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v17,
    (struct AutoMonitoredCritSec *)&vCoreResourcesLock,
    1);
  if ( vhCoreResourcesDll )
  {
    v3 = -2146498558;
    v19 = -2146498558;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "CoreResources have already been initialized.");
      *(_QWORD *)v16 = &v19;
      LOBYTE(v4) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)v16);
    }
    v5 = 12;
    goto LABEL_15;
  }
  memset_0(Buffer, 0, 0x208u);
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  if ( SystemWindowsDirectoryW )
  {
    if ( SystemWindowsDirectoryW >= 0x104 )
    {
      v3 = -2147024774;
      v5 = 17;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecore\\base\\cbs\\core\\coreresources.cpp",
        (const char *)v3,
        v15);
      goto LABEL_36;
    }
    lpLibFileName = 0;
    if ( v1 )
    {
      Library = vhCoreResourcesDll;
    }
    else
    {
      v10 = SczAllocFromSz(&lpLibFileName, Buffer);
      v3 = v10;
      if ( v10 < 0 )
      {
        v11 = 23;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\base\\cbs\\core\\coreresources.cpp",
          (const char *)(unsigned int)v10,
          v15);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
        goto LABEL_36;
      }
      v10 = SczEnsureBackslashTerminated(&lpLibFileName);
      v3 = v10;
      if ( v10 < 0 )
      {
        v11 = 25;
        goto LABEL_19;
      }
      v10 = SczAllocConcat2Sz(&lpLibFileName, L"servicing\\", L"CbsMsg.dll");
      v3 = v10;
      if ( v10 < 0 )
      {
        v11 = 27;
        goto LABEL_19;
      }
      Library = LoadLibraryExW(lpLibFileName, 0, 2u);
      vhCoreResourcesDll = Library;
    }
    if ( !Library )
    {
      v10 = SczAllocConcat2Sz(&lpLibFileName, a1, L"CbsMsg.dll");
      v3 = v10;
      if ( v10 < 0 )
      {
        v11 = 35;
        goto LABEL_19;
      }
      vhCoreResourcesDll = LoadLibraryExW(lpLibFileName, 0, 2u);
      if ( !vhCoreResourcesDll )
      {
        LastError = GetLastError();
        if ( v1 && LastError == 2 )
          LogAdapter::TraceAtLevel<>(1, "Offline servicing, localized strings will not be available");
        else
          LogAdapter::TraceAtLevelWin32<unsigned long,wchar_t *>(
            1,
            LastError,
            "Unable to load cbsmsg DLL: {}",
            &lpLibFileName);
      }
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
LABEL_35:
    v3 = 0;
    goto LABEL_36;
  }
  v7 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      LogAdapter::g_Logger,
      0,
      3,
      "Failed to get windows directory for CoreResources path.");
    if ( v7 > 0 )
      v9 = (unsigned __int16)v7 | 0x80070000;
    else
      v9 = v7;
    v19 = v9;
    LOBYTE(v8) = 1;
    *(_QWORD *)v16 = &v19;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v8,
      3,
      (unsigned int)": {0}",
      (__int64)v16);
  }
  if ( !v7 )
    goto LABEL_35;
  v3 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x10,
         (unsigned int)"onecore\\base\\cbs\\core\\coreresources.cpp",
         (const char *)(unsigned int)v7,
         v15);
LABEL_36:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v17);
  return v3;
}

```

## disassembly

```asm
0x180064cb0  push    rbp
0x180064cb2  push    rbx
0x180064cb3  push    rsi
0x180064cb4  push    rdi
0x180064cb5  lea     rbp, [rsp-188h]
0x180064cbd  sub     rsp, 288h
0x180064cc4  mov     rax, cs:__security_cookie
0x180064ccb  xor     rax, rsp
0x180064cce  mov     [rbp+1A0h+var_30], rax
0x180064cd5  mov     edi, cs:?vbOfflineStack@@3HA; int vbOfflineStack
0x180064cdb  lea     rdx, ?vCoreResourcesLock@@3UMonitoredCritSec@@A; struct AutoMonitoredCritSec *
0x180064ce2  mov     rsi, rcx
0x180064ce5  mov     r8b, 1; bool
0x180064ce8  lea     rcx, [rsp+2A0h+var_268]; this
0x180064ced  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x180064cf2  cmp     cs:?vhCoreResourcesDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * vhCoreResourcesDll
0x180064cfa  jz      short loc_180064D5D
0x180064cfc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180064d03  mov     ebx, 800F0802h
0x180064d08  mov     [rsp+2A0h+var_248], ebx
0x180064d0c  test    rcx, rcx
0x180064d0f  jz      short loc_180064D53
0x180064d11  mov     edi, 3
0x180064d16  lea     r9, aCoreresourcesH; "CoreResources have already been initial"...
0x180064d1d  mov     r8d, edi
0x180064d20  xor     edx, edx
0x180064d22  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180064d27  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180064d2e  lea     rax, [rsp+2A0h+var_248]
0x180064d33  mov     qword ptr [rsp+2A0h+var_270], rax
0x180064d38  lea     r9, asc_1802EE7AC; ": {}"
0x180064d3f  lea     rax, [rsp+2A0h+var_270]
0x180064d44  mov     r8d, edi
0x180064d47  mov     dl, 1
0x180064d49  mov     qword ptr [rsp+2A0h+var_280], rax
0x180064d4e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180064d53  mov     edx, 0Ch
0x180064d58  jmp     loc_180064E37
0x180064d5d  xor     edx, edx; Val
0x180064d5f  lea     rcx, [rsp+2A0h+Buffer]; void *
0x180064d64  mov     r8d, 208h; Size
0x180064d6a  call    memset_0
0x180064d6f  mov     ebx, 104h
0x180064d74  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180064d79  mov     edx, ebx; uSize
0x180064d7b  call    cs:__imp_GetSystemWindowsDirectoryW
0x180064d82  nop     dword ptr [rax+rax+00h]
0x180064d87  test    eax, eax
0x180064d89  jnz     loc_180064E29
0x180064d8f  call    cs:__imp_GetLastError
0x180064d96  nop     dword ptr [rax+rax+00h]
0x180064d9b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180064da2  mov     ebx, eax
0x180064da4  test    rcx, rcx
0x180064da7  jz      short loc_180064DFF
0x180064da9  mov     edi, 3
0x180064dae  lea     r9, aFailedToGetWin_8; "Failed to get windows directory for Cor"...
0x180064db5  mov     r8d, edi
0x180064db8  xor     edx, edx
0x180064dba  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180064dbf  test    ebx, ebx
0x180064dc1  jg      short loc_180064DC7
0x180064dc3  mov     eax, ebx
0x180064dc5  jmp     short loc_180064DCF
0x180064dc7  movzx   eax, bx
0x180064dca  or      eax, 80070000h
0x180064dcf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180064dd6  lea     r9, a0; ": {0}"
0x180064ddd  mov     [rsp+2A0h+var_248], eax
0x180064de1  mov     r8d, edi
0x180064de4  lea     rax, [rsp+2A0h+var_248]
0x180064de9  mov     dl, 1
0x180064deb  mov     qword ptr [rsp+2A0h+var_270], rax
0x180064df0  lea     rax, [rsp+2A0h+var_270]
0x180064df5  mov     qword ptr [rsp+2A0h+var_280], rax; unsigned int
0x180064dfa  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180064dff  test    ebx, ebx
0x180064e01  jz      loc_180064F9B
0x180064e07  mov     rcx, [rbp+1A8h]; this
0x180064e0e  lea     r8, aOnecoreBaseCbs_142; "onecore\\base\\cbs\\core\\coreresources"...
0x180064e15  mov     r9d, ebx; char *
0x180064e18  mov     edx, 10h; void *
0x180064e1d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180064e22  mov     ebx, eax
0x180064e24  jmp     loc_180064F9D
0x180064e29  cmp     eax, ebx
0x180064e2b  jb      short loc_180064E52
0x180064e2d  mov     ebx, 8007007Ah
0x180064e32  mov     edx, 11h; void *
0x180064e37  mov     rcx, [rbp+1A8h]; this
0x180064e3e  lea     r8, aOnecoreBaseCbs_142; "onecore\\base\\cbs\\core\\coreresources"...
0x180064e45  mov     r9d, ebx; char *
0x180064e48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064e4d  jmp     loc_180064F9D
0x180064e52  mov     [rsp+2A0h+lpLibFileName], 0
0x180064e5b  test    edi, edi
0x180064e5d  jnz     loc_180064EFC
0x180064e63  lea     rdx, [rsp+2A0h+Buffer]
0x180064e68  lea     rcx, [rsp+2A0h+lpLibFileName]
0x180064e6d  call    SczAllocFromSz
0x180064e72  mov     ebx, eax
0x180064e74  test    eax, eax
0x180064e76  jns     short loc_180064EA0
0x180064e78  lea     edx, [rdi+17h]; void *
0x180064e7b  mov     rcx, [rbp+1A8h]; this
0x180064e82  lea     r8, aOnecoreBaseCbs_142; "onecore\\base\\cbs\\core\\coreresources"...
0x180064e89  mov     r9d, eax; char *
0x180064e8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064e91  lea     rcx, [rsp+2A0h+lpLibFileName]
0x180064e96  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180064e9b  jmp     loc_180064F9D
0x180064ea0  lea     rcx, [rsp+2A0h+lpLibFileName]
0x180064ea5  call    SczEnsureBackslashTerminated
0x180064eaa  mov     ebx, eax
0x180064eac  test    eax, eax
0x180064eae  jns     short loc_180064EB7
0x180064eb0  mov     edx, 19h
0x180064eb5  jmp     short loc_180064E7B
0x180064eb7  lea     r8, aCbsmsgDll; "CbsMsg.dll"
0x180064ebe  lea     rdx, aServicing_1; "servicing\\"
0x180064ec5  lea     rcx, [rsp+2A0h+lpLibFileName]
0x180064eca  call    SczAllocConcat2Sz
0x180064ecf  mov     ebx, eax
0x180064ed1  test    eax, eax
0x180064ed3  jns     short loc_180064EDC
0x180064ed5  mov     edx, 1Bh
0x180064eda  jmp     short loc_180064E7B
0x180064edc  mov     rcx, [rsp+2A0h+lpLibFileName]; lpLibFileName
0x180064ee1  xor     edx, edx; hFile
0x180064ee3  lea     r8d, [rdx+2]; dwFlags
0x180064ee7  call    cs:__imp_LoadLibraryExW
0x180064eee  nop     dword ptr [rax+rax+00h]
0x180064ef3  mov     cs:?vhCoreResourcesDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhCoreResourcesDll
0x180064efa  jmp     short loc_180064F03
0x180064efc  mov     rax, cs:?vhCoreResourcesDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * vhCoreResourcesDll
0x180064f03  test    rax, rax
0x180064f06  jnz     loc_180064F91
0x180064f0c  lea     r8, aCbsmsgDll; "CbsMsg.dll"
0x180064f13  mov     rdx, rsi
0x180064f16  lea     rcx, [rsp+2A0h+lpLibFileName]
0x180064f1b  call    SczAllocConcat2Sz
0x180064f20  mov     ebx, eax
0x180064f22  test    eax, eax
0x180064f24  jns     short loc_180064F30
0x180064f26  mov     edx, 23h ; '#'
0x180064f2b  jmp     loc_180064E7B
0x180064f30  mov     rcx, [rsp+2A0h+lpLibFileName]; lpLibFileName
0x180064f35  xor     edx, edx; hFile
0x180064f37  lea     r8d, [rdx+2]; dwFlags
0x180064f3b  call    cs:__imp_LoadLibraryExW
0x180064f42  nop     dword ptr [rax+rax+00h]
0x180064f47  mov     cs:?vhCoreResourcesDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhCoreResourcesDll
0x180064f4e  test    rax, rax
0x180064f51  jnz     short loc_180064F91
0x180064f53  call    cs:__imp_GetLastError
0x180064f5a  nop     dword ptr [rax+rax+00h]
0x180064f5f  test    edi, edi
0x180064f61  jz      short loc_180064F79
0x180064f63  cmp     eax, 2
0x180064f66  jnz     short loc_180064F79
0x180064f68  lea     rdx, aOfflineServici; "Offline servicing, localized strings wi"...
0x180064f6f  lea     ecx, [rax-1]
0x180064f72  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180064f77  jmp     short loc_180064F91
0x180064f79  lea     r9, [rsp+2A0h+lpLibFileName]
0x180064f7e  mov     edx, eax
0x180064f80  lea     r8, aUnableToLoadCb; "Unable to load cbsmsg DLL: {}"
0x180064f87  mov     ecx, 1
0x180064f8c  call    ??$TraceAtLevelWin32@KPEA_W@LogAdapter@@YAXW4LogLevel@0@KQEBDAEBQEA_W@Z; LogAdapter::TraceAtLevelWin32<ulong,wchar_t *>(LogAdapter::LogLevel,ulong,char const * const,wchar_t * const &)
0x180064f91  lea     rcx, [rsp+2A0h+lpLibFileName]
0x180064f96  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180064f9b  xor     ebx, ebx
0x180064f9d  lea     rcx, [rsp+2A0h+var_268]; this
0x180064fa2  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x180064fa7  mov     eax, ebx
0x180064fa9  mov     rcx, [rbp+1A0h+var_30]
0x180064fb0  xor     rcx, rsp; StackCookie
0x180064fb3  call    __security_check_cookie
0x180064fb8  add     rsp, 288h
0x180064fbf  pop     rdi
0x180064fc0  pop     rsi
0x180064fc1  pop     rbx
0x180064fc2  pop     rbp
0x180064fc3  retn
```
