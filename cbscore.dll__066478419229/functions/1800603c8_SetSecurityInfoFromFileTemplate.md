# SetSecurityInfoFromFileTemplate

- ea: `0x1800603c8`
- end: `0x180060a18`
- name: `SetSecurityInfoFromFileTemplate`
- size: `1616`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b5fc`
- `0x1800cbe5c`

## callees

- `0x180010cc0`
- `0x18002e280`
- `0x180055fc8`
- `0x1800603c8`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006058b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800607e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800609dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006058b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800607e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800609dc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006055f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060634`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006055f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060634`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006050f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800607d0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800609cb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006050f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800607d0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800609cb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180060844`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180060844`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180060932`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180060932`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18006071f`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18006071f`

## string_xrefs

- `0x1800605b7`: `Failed to open {}`
- `0x180060681`: `Failed to open {}`
- `0x1800604e5`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x1800607a0`: `onecore\base\cbs\util\cbsacl.cpp`
- `0x1800604a7`: `No file template specified`
- `0x180060748`: `Failed to get security information for {}`
- `0x180060957`: `Failed to set security information for {}`
- `0x180060879`: `Failed to get security descriptor control for {}`

## pseudocode

```c
__int64 __fastcall SetSecurityInfoFromFileTemplate(const WCHAR *a1, const WCHAR *a2)
{
  unsigned int v2; // ebx
  int v3; // edx
  __int64 v4; // rdx
  int v5; // edx
  HANDLE FileW; // rax
  HANDLE v8; // rdi
  signed int SecurityInfo; // ebx
  int v10; // edx
  unsigned int v11; // eax
  __int64 v12; // rdx
  HANDLE v13; // rax
  HANDLE v14; // rbx
  int v15; // edx
  unsigned int v16; // eax
  PSECURITY_DESCRIPTOR *ppSecurityDescriptor; // rax
  int v18; // r15d
  int v19; // edx
  unsigned int v20; // eax
  int v21; // edx
  unsigned int v22; // eax
  unsigned int v23; // r9d
  SECURITY_INFORMATION v24; // r8d
  int v25; // edx
  unsigned int v26; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-59h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-59h]
  HANDLE handle; // [rsp+40h] [rbp-39h] BYREF
  HANDLE v30; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v31[2]; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR lpFileName; // [rsp+58h] [rbp-21h] BYREF
  PACL ppSacl; // [rsp+60h] [rbp-19h] BYREF
  PACL ppDacl; // [rsp+68h] [rbp-11h] BYREF
  PSID ppsidGroup; // [rsp+70h] [rbp-9h] BYREF
  PSID ppsidOwner; // [rsp+78h] [rbp-1h] BYREF
  const WCHAR *v37; // [rsp+80h] [rbp+7h] BYREF
  int v38; // [rsp+88h] [rbp+Fh] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+17h] BYREF
  WORD pControl[2]; // [rsp+98h] [rbp+1Fh] BYREF
  DWORD dwRevision; // [rsp+9Ch] [rbp+23h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v37 = a1;
  lpFileName = a2;
  hMem = 0;
  v30 = 0;
  handle = 0;
  ppSacl = 0;
  ppDacl = 0;
  ppsidOwner = 0;
  ppsidGroup = 0;
  pControl[0] = 0;
  dwRevision = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    v38 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file specified");
      *(_QWORD *)v31 = &v38;
      LOBYTE(v3) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)v31);
    }
    v4 = 252;
    goto LABEL_9;
  }
  if ( !a2 )
  {
    v2 = -2147024809;
    v38 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file template specified");
      *(_QWORD *)v31 = &v38;
      LOBYTE(v5) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)v31);
    }
    v4 = 253;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&handle);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v30);
    if ( hMem && LocalFree(hMem) )
      goto LABEL_11;
    return v2;
  }
  FileW = CreateFileW(a1, 0x10E0000u, 7u, 0, 4u, 0xA200000u, 0);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &v30,
    FileW);
  v8 = v30;
  if ( (((unsigned __int64)v30 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v13 = CreateFileW(lpFileName, 0x1020000u, 7u, 0, 3u, 0xA200000u, 0);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &handle,
      v13);
    v14 = handle;
    if ( (((unsigned __int64)handle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      ppSecurityDescriptor = (PSECURITY_DESCRIPTOR *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&hMem);
      v18 = 31;
      SecurityInfo = GetSecurityInfo(
                       v14,
                       SE_FILE_OBJECT,
                       0x1Fu,
                       &ppsidOwner,
                       &ppsidGroup,
                       &ppDacl,
                       &ppSacl,
                       ppSecurityDescriptor);
      if ( SecurityInfo )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to get security information for {}",
            (__int64)&lpFileName);
          if ( SecurityInfo > 0 )
            v20 = (unsigned __int16)SecurityInfo | 0x80070000;
          else
            v20 = SecurityInfo;
          v38 = v20;
          LOBYTE(v19) = 1;
          *(_QWORD *)v31 = &v38;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v19,
            3,
            (unsigned int)": {0}",
            (__int64)v31);
        }
        v12 = 283;
      }
      else
      {
        if ( !ppsidOwner )
          v18 = 30;
        if ( !ppsidGroup )
          v18 &= ~2u;
        if ( !ppSacl || !ppSacl->AceCount )
          v18 &= ~8u;
        if ( !ppDacl || !ppDacl->AceCount )
          v18 &= ~4u;
        if ( !GetSecurityDescriptorControl(hMem, pControl, &dwRevision) )
        {
          SecurityInfo = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to get security descriptor control for {}",
              (__int64)&lpFileName);
            if ( SecurityInfo > 0 )
              v22 = (unsigned __int16)SecurityInfo | 0x80070000;
            else
              v22 = SecurityInfo;
            v38 = v22;
            LOBYTE(v21) = 1;
            *(_QWORD *)v31 = &v38;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v21,
              3,
              (unsigned int)": {0}",
              (__int64)v31);
          }
          if ( SecurityInfo )
          {
            v12 = 306;
            goto LABEL_36;
          }
          goto LABEL_68;
        }
        v23 = v18 | 0x80000000;
        if ( (pControl[0] & 0x1000) == 0 )
          v23 = v18;
        v24 = v23 | 0x40000000;
        if ( (pControl[0] & 0x2000) == 0 )
          v24 = v23;
        SecurityInfo = SetSecurityInfo(v8, SE_FILE_OBJECT, v24, ppsidOwner, ppsidGroup, ppDacl, ppSacl);
        if ( !SecurityInfo )
          goto LABEL_68;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to set security information for {}",
            (__int64)&v37);
          if ( SecurityInfo > 0 )
            v26 = (unsigned __int16)SecurityInfo | 0x80070000;
          else
            v26 = SecurityInfo;
          v38 = v26;
          LOBYTE(v25) = 1;
          *(_QWORD *)v31 = &v38;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v25,
            3,
            (unsigned int)": {0}",
            (__int64)v31);
        }
        v12 = 320;
      }
LABEL_36:
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v12,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsacl.cpp",
             (const char *)(unsigned int)SecurityInfo,
             dwCreationDispositiona);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&handle);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v30);
      if ( hMem && LocalFree(hMem) )
      {
LABEL_11:
        GetLastError();
        __fastfail(7u);
      }
      return v2;
    }
    SecurityInfo = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to open {}",
        (__int64)&lpFileName);
      if ( SecurityInfo > 0 )
        v16 = (unsigned __int16)SecurityInfo | 0x80070000;
      else
        v16 = SecurityInfo;
      v38 = v16;
      LOBYTE(v15) = 1;
      *(_QWORD *)v31 = &v38;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        3,
        (unsigned int)": {0}",
        (__int64)v31);
    }
    if ( SecurityInfo )
    {
      v12 = 279;
      goto LABEL_36;
    }
  }
  else
  {
    SecurityInfo = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to open {}",
        (__int64)&v37);
      if ( SecurityInfo > 0 )
        v11 = (unsigned __int16)SecurityInfo | 0x80070000;
      else
        v11 = SecurityInfo;
      v38 = v11;
      LOBYTE(v10) = 1;
      *(_QWORD *)v31 = &v38;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {0}",
        (__int64)v31);
    }
    if ( SecurityInfo )
    {
      v12 = 266;
      goto LABEL_36;
    }
  }
LABEL_68:
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&handle);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v30);
  if ( hMem && LocalFree(hMem) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800603c8  mov     [rsp-8+arg_10], rbx
0x1800603cd  mov     [rsp-8+arg_18], rsi
0x1800603d2  push    rbp
0x1800603d3  push    rdi
0x1800603d4  push    r12
0x1800603d6  push    r14
0x1800603d8  push    r15
0x1800603da  lea     rbp, [rsp-37h]
0x1800603df  sub     rsp, 0B0h
0x1800603e6  mov     rax, cs:__security_cookie
0x1800603ed  xor     rax, rsp
0x1800603f0  mov     [rbp+57h+var_30], rax
0x1800603f4  xor     r12d, r12d
0x1800603f7  mov     [rbp+57h+var_50], rcx
0x1800603fb  mov     [rbp+57h+lpFileName], rdx
0x1800603ff  mov     [rbp+57h+hMem], r12
0x180060403  mov     [rbp+57h+var_88], r12
0x180060407  mov     [rbp+57h+handle], r12
0x18006040b  mov     [rbp+57h+ppSacl], r12
0x18006040f  mov     [rbp+57h+ppDacl], r12
0x180060413  mov     [rbp+57h+ppsidOwner], r12
0x180060417  mov     [rbp+57h+ppsidGroup], r12
0x18006041b  mov     [rbp+57h+pControl], r12w
0x180060420  mov     [rbp+57h+dwRevision], r12d
0x180060424  test    rcx, rcx
0x180060427  jnz     short loc_180060483
0x180060429  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180060430  mov     ebx, 80070057h
0x180060435  mov     [rbp+57h+var_48], ebx
0x180060438  test    rcx, rcx
0x18006043b  jz      short loc_18006047C
0x18006043d  lea     r14d, [r12+3]
0x180060442  xor     edx, edx
0x180060444  mov     r8d, r14d
0x180060447  lea     r9, aNoFileSpecifie; "No file specified"
0x18006044e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180060453  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006045a  lea     rax, [rbp+57h+var_48]
0x18006045e  mov     qword ptr [rbp+57h+var_80], rax
0x180060462  lea     r9, asc_1802EE7AC; ": {}"
0x180060469  lea     rax, [rbp+57h+var_80]
0x18006046d  mov     r8d, r14d
0x180060470  mov     dl, 1
0x180060472  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x180060477  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18006047c  mov     edx, 0FCh
0x180060481  jmp     short loc_1800604E1
0x180060483  test    rdx, rdx
0x180060486  jnz     loc_18006053A
0x18006048c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180060493  mov     ebx, 80070057h
0x180060498  mov     [rbp+57h+var_48], ebx
0x18006049b  test    rcx, rcx
0x18006049e  jz      short loc_1800604DC
0x1800604a0  lea     r14d, [rdx+3]
0x1800604a4  mov     r8d, r14d
0x1800604a7  lea     r9, aNoFileTemplate; "No file template specified"
0x1800604ae  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800604b3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800604ba  lea     rax, [rbp+57h+var_48]
0x1800604be  mov     qword ptr [rbp+57h+var_80], rax
0x1800604c2  lea     r9, asc_1802EE7AC; ": {}"
0x1800604c9  lea     rax, [rbp+57h+var_80]
0x1800604cd  mov     r8d, r14d
0x1800604d0  mov     dl, 1
0x1800604d2  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; int
0x1800604d7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800604dc  mov     edx, 0FDh; void *
0x1800604e1  mov     rcx, [rbp+5Fh]; this
0x1800604e5  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x1800604ec  mov     r9d, ebx; char *
0x1800604ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800604f4  lea     rcx, [rbp+57h+handle]
0x1800604f8  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800604fd  lea     rcx, [rbp+57h+var_88]
0x180060501  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180060506  mov     rcx, [rbp+57h+hMem]; hMem
0x18006050a  test    rcx, rcx
0x18006050d  jz      short loc_180060533
0x18006050f  call    cs:__imp_LocalFree
0x180060516  nop     dword ptr [rax+rax+00h]
0x18006051b  test    rax, rax
0x18006051e  jz      short loc_180060533
0x180060520  call    cs:__imp_GetLastError
0x180060527  nop     dword ptr [rax+rax+00h]
0x18006052c  mov     ecx, 7; lpFileName
0x180060531  int     29h; Win8: RtlFailFast(ecx)
0x180060533  mov     eax, ebx
0x180060535  jmp     loc_1800609EF
0x18006053a  xor     r9d, r9d; lpSecurityAttributes
0x18006053d  mov     [rsp+0D0h+hTemplateFile], r12; hTemplateFile
0x180060542  mov     ebx, 0A200000h
0x180060547  mov     edx, 10E0000h; dwDesiredAccess
0x18006054c  mov     [rsp+0D0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180060550  mov     [rsp+0D0h+dwCreationDisposition], 4; dwCreationDisposition
0x180060558  lea     esi, [r9+7]
0x18006055c  mov     r8d, esi; dwShareMode
0x18006055f  call    cs:__imp_CreateFileW
0x180060566  nop     dword ptr [rax+rax+00h]
0x18006056b  mov     rdx, rax
0x18006056e  lea     rcx, [rbp+57h+var_88]
0x180060572  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x180060577  mov     rdi, [rbp+57h+var_88]
0x18006057b  lea     rax, [rdi+1]
0x18006057f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180060585  jnz     loc_180060611
0x18006058b  call    cs:__imp_GetLastError
0x180060592  nop     dword ptr [rax+rax+00h]
0x180060597  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006059e  mov     ebx, eax
0x1800605a0  test    rcx, rcx
0x1800605a3  jz      short loc_1800605FF
0x1800605a5  lea     rax, [rbp+57h+var_50]
0x1800605a9  xor     edx, edx
0x1800605ab  lea     r14d, [rsi-4]
0x1800605af  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800605b4  mov     r8d, r14d
0x1800605b7  lea     r9, aFailedToOpen; "Failed to open {}"
0x1800605be  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800605c3  test    ebx, ebx
0x1800605c5  jg      short loc_1800605CB
0x1800605c7  mov     eax, ebx
0x1800605c9  jmp     short loc_1800605D3
0x1800605cb  movzx   eax, bx
0x1800605ce  or      eax, 80070000h
0x1800605d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800605da  lea     r9, a0; ": {0}"
0x1800605e1  mov     [rbp+57h+var_48], eax
0x1800605e4  mov     r8d, r14d
0x1800605e7  lea     rax, [rbp+57h+var_48]
0x1800605eb  mov     dl, 1
0x1800605ed  mov     qword ptr [rbp+57h+var_80], rax
0x1800605f1  lea     rax, [rbp+57h+var_80]
0x1800605f5  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800605fa  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800605ff  test    ebx, ebx
0x180060601  jz      loc_1800609B0
0x180060607  mov     edx, 10Ah
0x18006060c  jmp     loc_18006079C
0x180060611  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180060615  mov     r14d, 3
0x18006061b  mov     [rsp+0D0h+hTemplateFile], r12; hTemplateFile
0x180060620  xor     r9d, r9d; lpSecurityAttributes
0x180060623  mov     [rsp+0D0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180060627  mov     r8d, esi; dwShareMode
0x18006062a  mov     edx, 1020000h; dwDesiredAccess
0x18006062f  mov     [rsp+0D0h+dwCreationDisposition], r14d; dwCreationDisposition
0x180060634  call    cs:__imp_CreateFileW
0x18006063b  nop     dword ptr [rax+rax+00h]
0x180060640  mov     rdx, rax
0x180060643  lea     rcx, [rbp+57h+handle]
0x180060647  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x18006064c  mov     rbx, [rbp+57h+handle]
0x180060650  lea     rax, [rbx+1]
0x180060654  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006065a  jnz     loc_1800606E2
0x180060660  call    cs:__imp_GetLastError
0x180060667  nop     dword ptr [rax+rax+00h]
0x18006066c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180060673  mov     ebx, eax
0x180060675  test    rcx, rcx
0x180060678  jz      short loc_1800606D0
0x18006067a  lea     rax, [rbp+57h+lpFileName]
0x18006067e  mov     r8d, r14d
0x180060681  lea     r9, aFailedToOpen; "Failed to open {}"
0x180060688  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x18006068d  xor     edx, edx
0x18006068f  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180060694  test    ebx, ebx
0x180060696  jg      short loc_18006069C
0x180060698  mov     eax, ebx
0x18006069a  jmp     short loc_1800606A4
0x18006069c  movzx   eax, bx
0x18006069f  or      eax, 80070000h
0x1800606a4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800606ab  lea     r9, a0; ": {0}"
0x1800606b2  mov     [rbp+57h+var_48], eax
0x1800606b5  mov     r8d, r14d
0x1800606b8  lea     rax, [rbp+57h+var_48]
0x1800606bc  mov     dl, 1
0x1800606be  mov     qword ptr [rbp+57h+var_80], rax
0x1800606c2  lea     rax, [rbp+57h+var_80]
0x1800606c6  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800606cb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800606d0  test    ebx, ebx
0x1800606d2  jz      loc_1800609B0
0x1800606d8  mov     edx, 117h
0x1800606dd  jmp     loc_18006079C
0x1800606e2  lea     rcx, [rbp+57h+hMem]
0x1800606e6  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1800606eb  mov     [rsp+0D0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800606f0  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x1800606f4  lea     rax, [rbp+57h+ppSacl]
0x1800606f8  mov     r15d, 1Fh
0x1800606fe  mov     [rsp+0D0h+hTemplateFile], rax; ppSacl
0x180060703  mov     r8d, r15d; SecurityInfo
0x180060706  lea     rax, [rbp+57h+ppDacl]
0x18006070a  mov     rcx, rbx; handle
0x18006070d  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax; ppDacl
0x180060712  lea     rax, [rbp+57h+ppsidGroup]
0x180060716  lea     edx, [r15-1Eh]; ObjectType
0x18006071a  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; ppsidGroup
0x18006071f  call    cs:__imp_GetSecurityInfo
0x180060726  nop     dword ptr [rax+rax+00h]
0x18006072b  mov     ebx, eax
0x18006072d  test    eax, eax
0x18006072f  jz      loc_1800607F9
0x180060735  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006073c  test    rcx, rcx
0x18006073f  jz      short loc_180060797
0x180060741  lea     rax, [rbp+57h+lpFileName]
0x180060745  mov     r8d, r14d
0x180060748  lea     r9, aFailedToGetSec_0; "Failed to get security information for "...
0x18006074f  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x180060754  xor     edx, edx
0x180060756  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18006075b  test    ebx, ebx
0x18006075d  jg      short loc_180060763
0x18006075f  mov     eax, ebx
0x180060761  jmp     short loc_18006076B
0x180060763  movzx   eax, bx
0x180060766  or      eax, 80070000h
0x18006076b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180060772  lea     r9, a0; ": {0}"
0x180060779  mov     [rbp+57h+var_48], eax
0x18006077c  mov     r8d, r14d
0x18006077f  lea     rax, [rbp+57h+var_48]
0x180060783  mov     dl, 1
0x180060785  mov     qword ptr [rbp+57h+var_80], rax
0x180060789  lea     rax, [rbp+57h+var_80]
0x18006078d  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; unsigned int
0x180060792  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180060797  mov     edx, 11Bh; void *
0x18006079c  mov     rcx, [rbp+5Fh]; this
0x1800607a0  lea     r8, aOnecoreBaseCbs_107; "onecore\\base\\cbs\\util\\cbsacl.cpp"
0x1800607a7  mov     r9d, ebx; char *
0x1800607aa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800607af  lea     rcx, [rbp+57h+handle]
0x1800607b3  mov     ebx, eax
0x1800607b5  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800607ba  lea     rcx, [rbp+57h+var_88]
0x1800607be  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800607c3  mov     rcx, [rbp+57h+hMem]; hMem
0x1800607c7  test    rcx, rcx
0x1800607ca  jz      loc_180060533
0x1800607d0  call    cs:__imp_LocalFree
0x1800607d7  nop     dword ptr [rax+rax+00h]
0x1800607dc  test    rax, rax
0x1800607df  jz      loc_180060533
0x1800607e5  call    cs:__imp_GetLastError
0x1800607ec  nop     dword ptr [rax+rax+00h]
0x1800607f1  mov     rcx, rsi
0x1800607f4  jmp     loc_180060531
0x1800607f9  cmp     [rbp+57h+ppsidOwner], r12
0x1800607fd  mov     eax, 1Eh
0x180060802  cmovz   r15d, eax
0x180060806  cmp     [rbp+57h+ppsidGroup], r12
0x18006080a  jnz     short loc_180060810
0x18006080c  and     r15d, 0FFFFFFFDh
0x180060810  mov     rax, [rbp+57h+ppSacl]
0x180060814  test    rax, rax
0x180060817  jz      short loc_180060820
0x180060819  cmp     [rax+4], r12w
0x18006081e  jnz     short loc_180060824
0x180060820  and     r15d, 0FFFFFFF7h
0x180060824  mov     rax, [rbp+57h+ppDacl]
0x180060828  test    rax, rax
0x18006082b  jz      short loc_180060834
0x18006082d  cmp     [rax+4], r12w
0x180060832  jnz     short loc_180060838
0x180060834  and     r15d, 0FFFFFFFBh
0x180060838  mov     rcx, [rbp+57h+hMem]; pSecurityDescriptor
0x18006083c  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x180060840  lea     rdx, [rbp+57h+pControl]; pControl
0x180060844  call    cs:__imp_GetSecurityDescriptorControl
0x18006084b  nop     dword ptr [rax+rax+00h]
0x180060850  test    eax, eax
0x180060852  jnz     loc_1800608DA
0x180060858  call    cs:__imp_GetLastError
0x18006085f  nop     dword ptr [rax+rax+00h]
0x180060864  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006086b  mov     ebx, eax
0x18006086d  test    rcx, rcx
0x180060870  jz      short loc_1800608C8
0x180060872  lea     rax, [rbp+57h+lpFileName]
0x180060876  mov     r8d, r14d
0x180060879  lea     r9, aFailedToGetSec; "Failed to get security descriptor contr"...
0x180060880  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x180060885  xor     edx, edx
0x180060887  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18006088c  test    ebx, ebx
0x18006088e  jg      short loc_180060894
0x180060890  mov     eax, ebx
0x180060892  jmp     short loc_18006089C
0x180060894  movzx   eax, bx
0x180060897  or      eax, 80070000h
0x18006089c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800608a3  lea     r9, a0; ": {0}"
0x1800608aa  mov     [rbp+57h+var_48], eax
0x1800608ad  mov     r8d, r14d
  ... truncated ...
```
