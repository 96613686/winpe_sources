# CbsRegDeleteKeyWithBackupRestore(void *,HKEY__ *,wchar_t const *,ulong)

- ea: `0x18005857c`
- end: `0x180058b90`
- name: `?CbsRegDeleteKeyWithBackupRestore@@YAJPEAXPEAUHKEY__@@PEB_WK@Z`
- size: `1556`
- prototype: `int(void *, HKEY, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b0528`

## callees

- `0x180010cc0`
- `0x1800150c0`
- `0x18003330c`
- `0x18004a680`
- `0x18004dd18`
- `0x18004f454`
- `0x180058308`
- `0x1800584fc`
- `0x18005857c`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1801077f4`
- `0x18010ffe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058937`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800585f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800585f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800585dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800585dd`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800589e0`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800589e0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180058923`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180058923`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180058887`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180058887`

## string_xrefs

- `0x18005877d`: `Failed to create DACL.`
- `0x180058818`: `Failed to open key with WRITE_DAC access.`
- `0x180058628`: `Failed to get process token to set privileges into.`
- `0x1800586d8`: `Failed to get sid for current token.`
- `0x180058a12`: `Failed to set key security to gain delete access to registry key.`
- `0x180058b12`: `Failed to delete key with backup/restore privileges.`
- `0x1800588b6`: `Failed initializing security descriptor`
- `0x180058956`: `Failed setting security descriptor dacl`

## pseudocode

```c
__int64 __fastcall CbsRegDeleteKeyWithBackupRestore(void *a1, HKEY a2, const wchar_t *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // ebx
  int v9; // edx
  unsigned int v10; // eax
  int UserSidFromToken; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // r9d
  int v15; // edx
  int Dacl; // eax
  int v17; // edx
  struct _ACL *v18; // rdi
  HKEY *InitPointer; // rax
  int KeyWithBackupRestore; // eax
  int v21; // edx
  int v22; // ebx
  int v23; // edx
  unsigned int v24; // eax
  __int64 v25; // rdx
  int v26; // edx
  unsigned int v27; // eax
  int v28; // edx
  int v30; // eax
  int v31; // edx
  unsigned int v32; // [rsp+20h] [rbp-49h]
  PACL pDacl; // [rsp+30h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-31h] BYREF
  PACL v35; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v36[2]; // [rsp+48h] [rbp-21h] BYREF
  PACL v37; // [rsp+50h] [rbp-19h]
  __int64 v38; // [rsp+58h] [rbp-11h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v40; // [rsp+70h] [rbp+7h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v42; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  TokenHandle = 0;
  v5 = CbsRegDeleteKeyW(a2, a3);
  v6 = v5;
  if ( v5 == 5 )
  {
    v38 = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20028u, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to get process token to set privileges into.");
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        else
          v10 = LastError;
        v40 = v10;
        LOBYTE(v9) = 1;
        pDacl = (PACL)&v40;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v9,
          3,
          (unsigned int)": {0}",
          (__int64)&pDacl);
      }
      if ( LastError )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x64,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)(unsigned int)LastError,
               v32);
LABEL_49:
        Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v38);
        return v6;
      }
LABEL_39:
      v6 = 0;
      goto LABEL_49;
    }
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&v38, TokenHandle);
    pDacl = 0;
    UserSidFromToken = GetUserSidFromToken(TokenHandle, &pDacl);
    v6 = UserSidFromToken;
    if ( UserSidFromToken < 0 )
    {
      v40 = UserSidFromToken;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get sid for current token.");
        pDacl = (PACL)&v40;
        LOBYTE(v15) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v15,
          3,
          (unsigned int)": {}",
          (__int64)&pDacl);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
        (const char *)v6,
        v32);
      goto LABEL_49;
    }
    v35 = pDacl;
    v37 = pDacl;
    v36[0] = 4;
    v36[1] = 983103;
    pDacl = 0;
    Dacl = AclCreateDacl(v13, v12, (unsigned int)v36, v14, (__int64)&pDacl);
    v6 = Dacl;
    if ( Dacl < 0 )
    {
      v40 = Dacl;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create DACL.");
        pDacl = (PACL)&v40;
        LOBYTE(v17) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v17,
          3,
          (unsigned int)": {}",
          (__int64)&pDacl);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
        (const char *)v6,
        v32);
      goto LABEL_48;
    }
    v18 = pDacl;
    hKey = 0;
    InitPointer = (HKEY *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&hKey);
    KeyWithBackupRestore = CbsRegCreateKeyWithBackupRestore(a2, a3, 0, InitPointer);
    v6 = KeyWithBackupRestore;
    if ( KeyWithBackupRestore < 0 )
    {
      v40 = KeyWithBackupRestore;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open key with WRITE_DAC access.");
        *(_QWORD *)v36 = &v40;
        LOBYTE(v21) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v21,
          3,
          (unsigned int)": {}",
          (__int64)v36);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
        (const char *)v6,
        v32);
      goto LABEL_47;
    }
    v42 = 0;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      v22 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed initializing security descriptor");
        if ( v22 > 0 )
          v24 = (unsigned __int16)v22 | 0x80070000;
        else
          v24 = v22;
        v40 = v24;
        LOBYTE(v23) = 1;
        *(_QWORD *)v36 = &v40;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v23,
          3,
          (unsigned int)": {0}",
          (__int64)v36);
      }
      if ( v22 )
      {
        v25 = 128;
LABEL_46:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v25,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)(unsigned int)v22,
               v32);
LABEL_47:
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
        CbsRegDeleteKeyWithBackupRestore_::_5_::DaclGuard::_DaclGuard(&pDacl);
LABEL_48:
        Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v35);
        goto LABEL_49;
      }
      goto LABEL_38;
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v18, 0) )
    {
      v22 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed setting security descriptor dacl");
        if ( v22 > 0 )
          v27 = (unsigned __int16)v22 | 0x80070000;
        else
          v27 = v22;
        v40 = v27;
        LOBYTE(v26) = 1;
        *(_QWORD *)v36 = &v40;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          3,
          (unsigned int)": {0}",
          (__int64)v36);
      }
      if ( v22 )
      {
        v25 = 132;
        goto LABEL_46;
      }
LABEL_38:
      Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
      CbsRegDeleteKeyWithBackupRestore_::_5_::DaclGuard::_DaclGuard(&pDacl);
      Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v35);
      goto LABEL_39;
    }
    v22 = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
    if ( v22 < 0 )
      __fastfail(7u);
    if ( v22 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to set key security to gain delete access to registry key.");
        v40 = (unsigned __int16)v22 | 0x80070000;
        LOBYTE(v28) = 1;
        *(_QWORD *)v36 = &v40;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v28,
          3,
          (unsigned int)": {0}",
          (__int64)v36);
      }
      v25 = 136;
      goto LABEL_46;
    }
    Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
    v30 = CbsRegDeleteKeyW(a2, a3);
    v6 = v30;
    if ( v30 > 0 )
      v6 = (unsigned __int16)v30 | 0x80070000;
    Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
    CbsRegDeleteKeyWithBackupRestore_::_5_::DaclGuard::_DaclGuard(&pDacl);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v35);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v38);
  }
  else if ( v5 > 0 )
  {
    v6 = (unsigned __int16)v5 | 0x80070000;
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    v40 = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to delete key with backup/restore privileges.");
      *(_QWORD *)v36 = &v40;
      LOBYTE(v31) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v31,
        3,
        (unsigned int)": {}",
        (__int64)v36);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
      (const char *)v6,
      v32);
    return v6;
  }
  return 0;
}

```

## disassembly

```asm
0x18005857c  mov     [rsp-8+arg_0], rbx
0x180058581  mov     [rsp-8+arg_18], rsi
0x180058586  push    rbp
0x180058587  push    rdi
0x180058588  push    r14
0x18005858a  lea     rbp, [rsp-47h]
0x18005858f  sub     rsp, 0B0h
0x180058596  mov     rax, cs:__security_cookie
0x18005859d  xor     rax, rsp
0x1800585a0  mov     [rbp+57h+var_20], rax
0x1800585a4  mov     rsi, rdx
0x1800585a7  mov     [rbp+57h+TokenHandle], 0
0x1800585af  mov     rcx, rsi; hKey
0x1800585b2  mov     rdx, r8; lpSubKey
0x1800585b5  mov     r14, r8
0x1800585b8  call    ?CbsRegDeleteKeyW@@YAKPEAUHKEY__@@PEB_W@Z; CbsRegDeleteKeyW(HKEY__ *,wchar_t const *)
0x1800585bd  mov     ebx, eax
0x1800585bf  cmp     eax, 5
0x1800585c2  jnz     loc_180058AED
0x1800585c8  mov     rcx, [rbp+57h+TokenHandle]
0x1800585cc  mov     [rbp+57h+var_68], 0
0x1800585d4  test    rcx, rcx
0x1800585d7  jnz     loc_1800586AD
0x1800585dd  call    cs:__imp_GetCurrentProcess
0x1800585e4  nop     dword ptr [rax+rax+00h]
0x1800585e9  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800585ed  mov     edx, 20028h; DesiredAccess
0x1800585f2  mov     rcx, rax; ProcessHandle
0x1800585f5  call    cs:__imp_OpenProcessToken
0x1800585fc  nop     dword ptr [rax+rax+00h]
0x180058601  test    eax, eax
0x180058603  jnz     loc_18005869C
0x180058609  call    cs:__imp_GetLastError
0x180058610  nop     dword ptr [rax+rax+00h]
0x180058615  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005861c  mov     ebx, eax
0x18005861e  test    rcx, rcx
0x180058621  jz      short loc_180058675
0x180058623  mov     edi, 3
0x180058628  lea     r9, aFailedToGetPro_60; "Failed to get process token to set priv"...
0x18005862f  mov     r8d, edi
0x180058632  xor     edx, edx
0x180058634  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180058639  test    ebx, ebx
0x18005863b  jg      short loc_180058641
0x18005863d  mov     eax, ebx
0x18005863f  jmp     short loc_180058649
0x180058641  movzx   eax, bx
0x180058644  or      eax, 80070000h
0x180058649  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180058650  lea     r9, a0; ": {0}"
0x180058657  mov     [rbp+57h+var_50], eax
0x18005865a  mov     r8d, edi
0x18005865d  lea     rax, [rbp+57h+var_50]
0x180058661  mov     dl, 1
0x180058663  mov     [rbp+57h+pDacl], rax
0x180058667  lea     rax, [rbp+57h+pDacl]
0x18005866b  mov     qword ptr [rsp+0C0h+var_A0], rax; unsigned int
0x180058670  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180058675  test    ebx, ebx
0x180058677  jz      loc_1800589CC
0x18005867d  mov     rcx, [rbp+5Fh]; this
0x180058681  lea     r8, aOnecoreBaseCbs_80; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x180058688  mov     r9d, ebx; char *
0x18005868b  mov     edx, 64h ; 'd'; void *
0x180058690  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180058695  mov     ebx, eax
0x180058697  jmp     loc_180058A94
0x18005869c  mov     rdx, [rbp+57h+TokenHandle]
0x1800586a0  lea     rcx, [rbp+57h+var_68]
0x1800586a4  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800586a9  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800586ad  lea     rdx, [rbp+57h+pDacl]
0x1800586b1  mov     [rbp+57h+pDacl], 0
0x1800586b9  call    GetUserSidFromToken
0x1800586be  mov     ebx, eax
0x1800586c0  test    eax, eax
0x1800586c2  jns     short loc_18005872F
0x1800586c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800586cb  mov     [rbp+57h+var_50], eax
0x1800586ce  test    rcx, rcx
0x1800586d1  jz      short loc_180058712
0x1800586d3  mov     edi, 3
0x1800586d8  lea     r9, aFailedToGetSid_1; "Failed to get sid for current token."
0x1800586df  mov     r8d, edi
0x1800586e2  xor     edx, edx
0x1800586e4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800586e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800586f0  lea     rax, [rbp+57h+var_50]
0x1800586f4  mov     [rbp+57h+pDacl], rax
0x1800586f8  lea     r9, asc_1802EE7AC; ": {}"
0x1800586ff  lea     rax, [rbp+57h+pDacl]
0x180058703  mov     r8d, edi
0x180058706  mov     dl, 1
0x180058708  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18005870d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180058712  mov     rcx, [rbp+5Fh]; this
0x180058716  lea     r8, aOnecoreBaseCbs_80; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x18005871d  mov     r9d, ebx; char *
0x180058720  mov     edx, 69h ; 'i'; void *
0x180058725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005872a  jmp     loc_180058A94
0x18005872f  mov     rax, [rbp+57h+pDacl]
0x180058733  lea     r8, [rbp+57h+var_78]
0x180058737  mov     [rbp+57h+var_80], rax
0x18005873b  mov     [rbp+57h+var_70], rax
0x18005873f  lea     rax, [rbp+57h+pDacl]
0x180058743  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180058748  mov     [rbp+57h+var_78], 4
0x18005874f  mov     [rbp+57h+var_78+4], 0F003Fh
0x180058756  mov     [rbp+57h+pDacl], 0
0x18005875e  call    AclCreateDacl
0x180058763  mov     ebx, eax
0x180058765  test    eax, eax
0x180058767  jns     short loc_1800587D4
0x180058769  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180058770  mov     [rbp+57h+var_50], eax
0x180058773  test    rcx, rcx
0x180058776  jz      short loc_1800587B7
0x180058778  mov     edi, 3
0x18005877d  lea     r9, aFailedToCreate_108; "Failed to create DACL."
0x180058784  mov     r8d, edi
0x180058787  xor     edx, edx
0x180058789  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18005878e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180058795  lea     rax, [rbp+57h+var_50]
0x180058799  mov     [rbp+57h+pDacl], rax
0x18005879d  lea     r9, asc_1802EE7AC; ": {}"
0x1800587a4  lea     rax, [rbp+57h+pDacl]
0x1800587a8  mov     r8d, edi
0x1800587ab  mov     dl, 1
0x1800587ad  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800587b2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800587b7  mov     rcx, [rbp+5Fh]; this
0x1800587bb  lea     r8, aOnecoreBaseCbs_80; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1800587c2  mov     r9d, ebx; char *
0x1800587c5  mov     edx, 73h ; 's'; void *
0x1800587ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800587cf  jmp     loc_180058A8B
0x1800587d4  mov     rdi, [rbp+57h+pDacl]
0x1800587d8  lea     rcx, [rbp+57h+hKey]
0x1800587dc  mov     [rbp+57h+pDacl], rdi
0x1800587e0  mov     [rbp+57h+hKey], 0
0x1800587e8  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1800587ed  mov     r9, rax; HKEY *
0x1800587f0  xor     r8d, r8d; unsigned int
0x1800587f3  mov     rdx, r14; wchar_t *
0x1800587f6  mov     rcx, rsi; hKey
0x1800587f9  call    ?CbsRegCreateKeyWithBackupRestore@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; CbsRegCreateKeyWithBackupRestore(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1800587fe  mov     ebx, eax
0x180058800  test    eax, eax
0x180058802  jns     short loc_18005886F
0x180058804  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005880b  mov     [rbp+57h+var_50], eax
0x18005880e  test    rcx, rcx
0x180058811  jz      short loc_180058852
0x180058813  mov     edi, 3
0x180058818  lea     r9, aFailedToOpenKe_0; "Failed to open key with WRITE_DAC acces"...
0x18005881f  mov     r8d, edi
0x180058822  xor     edx, edx
0x180058824  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180058829  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180058830  lea     rax, [rbp+57h+var_50]
0x180058834  mov     qword ptr [rbp+57h+var_78], rax
0x180058838  lea     r9, asc_1802EE7AC; ": {}"
0x18005883f  lea     rax, [rbp+57h+var_78]
0x180058843  mov     r8d, edi
0x180058846  mov     dl, 1
0x180058848  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18005884d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180058852  mov     rcx, [rbp+5Fh]; this
0x180058856  lea     r8, aOnecoreBaseCbs_80; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x18005885d  mov     r9d, ebx; char *
0x180058860  mov     edx, 7Bh ; '{'; void *
0x180058865  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005886a  jmp     loc_180058A79
0x18005886f  xor     eax, eax
0x180058871  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180058875  xorps   xmm0, xmm0
0x180058878  mov     [rbp+57h+var_28], rax
0x18005887c  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180058880  lea     edx, [rax+1]; dwRevision
0x180058883  movups  [rbp+57h+var_38], xmm0
0x180058887  call    cs:__imp_InitializeSecurityDescriptor
0x18005888e  nop     dword ptr [rax+rax+00h]
0x180058893  test    eax, eax
0x180058895  jnz     short loc_180058915
0x180058897  call    cs:__imp_GetLastError
0x18005889e  nop     dword ptr [rax+rax+00h]
0x1800588a3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800588aa  mov     ebx, eax
0x1800588ac  test    rcx, rcx
0x1800588af  jz      short loc_180058903
0x1800588b1  mov     edi, 3
0x1800588b6  lea     r9, aFailedInitiali_9; "Failed initializing security descriptor"
0x1800588bd  mov     r8d, edi
0x1800588c0  xor     edx, edx
0x1800588c2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800588c7  test    ebx, ebx
0x1800588c9  jg      short loc_1800588CF
0x1800588cb  mov     eax, ebx
0x1800588cd  jmp     short loc_1800588D7
0x1800588cf  movzx   eax, bx
0x1800588d2  or      eax, 80070000h
0x1800588d7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800588de  lea     r9, a0; ": {0}"
0x1800588e5  mov     [rbp+57h+var_50], eax
0x1800588e8  mov     r8d, edi
0x1800588eb  lea     rax, [rbp+57h+var_50]
0x1800588ef  mov     dl, 1
0x1800588f1  mov     qword ptr [rbp+57h+var_78], rax
0x1800588f5  lea     rax, [rbp+57h+var_78]
0x1800588f9  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800588fe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180058903  test    ebx, ebx
0x180058905  jz      loc_1800589B1
0x18005890b  mov     edx, 80h
0x180058910  jmp     loc_180058A64
0x180058915  xor     r9d, r9d; bDaclDefaulted
0x180058918  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18005891c  mov     r8, rdi; pDacl
0x18005891f  lea     edx, [r9+1]; bDaclPresent
0x180058923  call    cs:__imp_SetSecurityDescriptorDacl
0x18005892a  nop     dword ptr [rax+rax+00h]
0x18005892f  test    eax, eax
0x180058931  jnz     loc_1800589D3
0x180058937  call    cs:__imp_GetLastError
0x18005893e  nop     dword ptr [rax+rax+00h]
0x180058943  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005894a  mov     ebx, eax
0x18005894c  test    rcx, rcx
0x18005894f  jz      short loc_1800589A3
0x180058951  mov     edi, 3
0x180058956  lea     r9, aFailedSettingS_2; "Failed setting security descriptor dacl"
0x18005895d  mov     r8d, edi
0x180058960  xor     edx, edx
0x180058962  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180058967  test    ebx, ebx
0x180058969  jg      short loc_18005896F
0x18005896b  mov     eax, ebx
0x18005896d  jmp     short loc_180058977
0x18005896f  movzx   eax, bx
0x180058972  or      eax, 80070000h
0x180058977  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18005897e  lea     r9, a0; ": {0}"
0x180058985  mov     [rbp+57h+var_50], eax
0x180058988  mov     r8d, edi
0x18005898b  lea     rax, [rbp+57h+var_50]
0x18005898f  mov     dl, 1
0x180058991  mov     qword ptr [rbp+57h+var_78], rax
0x180058995  lea     rax, [rbp+57h+var_78]
0x180058999  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18005899e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800589a3  test    ebx, ebx
0x1800589a5  jz      short loc_1800589B1
0x1800589a7  mov     edx, 84h
0x1800589ac  jmp     loc_180058A64
0x1800589b1  lea     rcx, [rbp+57h+hKey]
0x1800589b5  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x1800589ba  lea     rcx, [rbp+57h+pDacl]
0x1800589be  call    _CbsRegDeleteKeyWithBackupRestore____5___DaclGuard___DaclGuard
0x1800589c3  lea     rcx, [rbp+57h+var_80]
0x1800589c7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x1800589cc  xor     ebx, ebx
0x1800589ce  jmp     loc_180058A94
0x1800589d3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800589d7  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800589db  mov     edx, 4; SecurityInformation
0x1800589e0  call    cs:__imp_RegSetKeySecurity
0x1800589e7  nop     dword ptr [rax+rax+00h]
0x1800589ec  mov     ebx, eax
0x1800589ee  test    eax, eax
0x1800589f0  jns     short loc_1800589F9
0x1800589f2  mov     ecx, 7
0x1800589f7  int     29h; Win8: RtlFailFast(ecx)
0x1800589f9  test    ebx, ebx
0x1800589fb  jz      loc_180058AA4
0x180058a01  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180058a08  test    rcx, rcx
0x180058a0b  jz      short loc_180058A5F
0x180058a0d  mov     edi, 3
0x180058a12  lea     r9, aFailedToSetKey; "Failed to set key security to gain dele"...
0x180058a19  mov     r8d, edi
0x180058a1c  xor     edx, edx
0x180058a1e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180058a23  test    ebx, ebx
0x180058a25  jg      short loc_180058A2B
0x180058a27  mov     eax, ebx
0x180058a29  jmp     short loc_180058A33
0x180058a2b  movzx   eax, bx
0x180058a2e  or      eax, 80070000h
0x180058a33  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180058a3a  lea     r9, a0; ": {0}"
0x180058a41  mov     [rbp+57h+var_50], eax
0x180058a44  mov     r8d, edi
0x180058a47  lea     rax, [rbp+57h+var_50]
0x180058a4b  mov     dl, 1
0x180058a4d  mov     qword ptr [rbp+57h+var_78], rax
0x180058a51  lea     rax, [rbp+57h+var_78]
0x180058a55  mov     qword ptr [rsp+0C0h+var_A0], rax; unsigned int
  ... truncated ...
```
