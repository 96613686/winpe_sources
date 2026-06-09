# GetNonTiToken(void * *)

- ea: `0x18009564c`
- end: `0x18009591b`
- name: `?GetNonTiToken@@YAJPEAPEAX@Z`
- size: `719`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `7`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009d188`
- `0x1800f3190`
- `0x1800fd374`
- `0x1801707f8`
- `0x180178b84`
- `0x1801dba50`
- `0x1801dc03c`

## callees

- `0x180010cc0`
- `0x18009564c`
- `0x180095924`
- `0x180095e34`
- `0x180096e44`
- `0x180098538`
- `0x180099548`
- `0x1800eb920`
- `0x1800fdf20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800956b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800956b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095855`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800956a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800956a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009568f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009568f`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180095845`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180095845`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180095743`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180095743`

## string_xrefs

- `0x180095874`: `Failed to create restricted token.`
- `0x1800956d6`: `Failed to open process token.`
- `0x180095776`: `Failed to convert string SID to SID`

## pseudocode

```c
__int64 __fastcall GetNonTiToken(void **a1)
{
  void **v2; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // edi
  int v5; // edx
  unsigned int v6; // eax
  __int64 v7; // rdx
  PSID *InitPointer; // rax
  int v9; // edx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  void *v12; // rdx
  void **NewTokenHandle; // rax
  int v14; // edx
  unsigned int v15; // eax
  void *v16; // rdx
  unsigned int DeletePrivilegeCount; // [rsp+20h] [rbp-39h]
  unsigned int v19; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v20[2]; // [rsp+58h] [rbp-1h] BYREF
  struct _SID_AND_ATTRIBUTES SidsToDisable; // [rsp+60h] [rbp+7h] BYREF
  Windows::Detail *v22; // [rsp+70h] [rbp+17h] BYREF
  void *v23; // [rsp+78h] [rbp+1Fh] BYREF
  HANDLE ExistingTokenHandle; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  ExistingTokenHandle = 0;
  v22 = 0;
  SidsToDisable = 0;
  v23 = 0;
  v2 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&ExistingTokenHandle);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xBu, v2) )
  {
    InitPointer = (PSID *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v22);
    if ( ConvertStringSidToSidW(L"S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464", InitPointer) )
    {
      SidsToDisable.Sid = v22;
      *(_QWORD *)&SidsToDisable.Attributes = 0;
      NewTokenHandle = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v23);
      if ( CreateRestrictedToken(ExistingTokenHandle, 1u, 1u, &SidsToDisable, 0, 0, 0, 0, NewTokenHandle) )
      {
        *a1 = v23;
        v23 = 0;
        goto LABEL_28;
      }
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create restricted token.");
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        else
          v15 = LastError;
        v19 = v15;
        LOBYTE(v14) = 1;
        *(_QWORD *)v20 = &v19;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v14,
          3,
          (unsigned int)": {0}",
          (__int64)v20);
      }
      if ( !LastError )
        goto LABEL_28;
      v7 = 1717;
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to convert string SID to SID");
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        else
          v10 = LastError;
        v19 = v10;
        LOBYTE(v9) = 1;
        *(_QWORD *)v20 = &v19;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v9,
          3,
          (unsigned int)": {0}",
          (__int64)v20);
      }
      if ( !LastError )
        goto LABEL_28;
      v7 = 1701;
    }
LABEL_17:
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v7,
            (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
            (const char *)(unsigned int)LastError,
            DeletePrivilegeCount);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    if ( v22 )
    {
      Windows::Detail::CloseWithRtlFreeSid(v22, v12);
      v22 = 0;
    }
    goto LABEL_31;
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open process token.");
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    else
      v6 = LastError;
    v19 = v6;
    LOBYTE(v5) = 1;
    *(_QWORD *)v20 = &v19;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v5,
      3,
      (unsigned int)": {0}",
      (__int64)v20);
  }
  if ( LastError )
  {
    v7 = 1698;
    goto LABEL_17;
  }
LABEL_28:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
  if ( v22 )
  {
    Windows::Detail::CloseWithRtlFreeSid(v22, v16);
    v22 = 0;
  }
  v11 = 0;
LABEL_31:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
  return v11;
}

```

## disassembly

```asm
0x18009564c  push    rbp
0x18009564e  push    rbx
0x18009564f  push    rsi
0x180095650  push    rdi
0x180095651  lea     rbp, [rsp-3Fh]
0x180095656  sub     rsp, 98h
0x18009565d  mov     rax, cs:__security_cookie
0x180095664  xor     rax, rsp
0x180095667  mov     [rbp+57h+var_28], rax
0x18009566b  xor     esi, esi
0x18009566d  mov     rdi, rcx
0x180095670  xorps   xmm0, xmm0
0x180095673  mov     [rbp+57h+ExistingTokenHandle], rsi
0x180095677  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x18009567b  mov     [rbp+57h+var_40], rsi
0x18009567f  movups  xmmword ptr [rbp+57h+SidsToDisable.Sid], xmm0
0x180095683  mov     [rbp+57h+var_38], rsi
0x180095687  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18009568c  mov     rbx, rax
0x18009568f  call    cs:__imp_GetCurrentProcess
0x180095696  nop     dword ptr [rax+rax+00h]
0x18009569b  mov     r8, rbx; TokenHandle
0x18009569e  lea     edx, [rsi+0Bh]; DesiredAccess
0x1800956a1  mov     rcx, rax; ProcessHandle
0x1800956a4  call    cs:__imp_OpenProcessToken
0x1800956ab  nop     dword ptr [rax+rax+00h]
0x1800956b0  test    eax, eax
0x1800956b2  jnz     short loc_180095730
0x1800956b4  call    cs:__imp_GetLastError
0x1800956bb  nop     dword ptr [rax+rax+00h]
0x1800956c0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800956c7  mov     edi, eax
0x1800956c9  test    rcx, rcx
0x1800956cc  jz      short loc_18009571E
0x1800956ce  lea     ebx, [rsi+3]
0x1800956d1  xor     edx, edx
0x1800956d3  mov     r8d, ebx
0x1800956d6  lea     r9, aFailedToOpenPr; "Failed to open process token."
0x1800956dd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800956e2  test    edi, edi
0x1800956e4  jg      short loc_1800956EA
0x1800956e6  mov     eax, edi
0x1800956e8  jmp     short loc_1800956F2
0x1800956ea  movzx   eax, di
0x1800956ed  or      eax, 80070000h
0x1800956f2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800956f9  lea     r9, a0; ": {0}"
0x180095700  mov     [rbp+57h+var_60], eax
0x180095703  mov     r8d, ebx
0x180095706  lea     rax, [rbp+57h+var_60]
0x18009570a  mov     dl, 1
0x18009570c  mov     qword ptr [rbp+57h+var_58], rax
0x180095710  lea     rax, [rbp+57h+var_58]
0x180095714  mov     qword ptr [rsp+0B0h+DeletePrivilegeCount], rax
0x180095719  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009571e  test    edi, edi
0x180095720  jz      loc_1800958DA
0x180095726  mov     edx, 6A2h
0x18009572b  jmp     loc_1800957D0
0x180095730  lea     rcx, [rbp+57h+var_40]
0x180095734  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x180095739  mov     rdx, rax; Sid
0x18009573c  lea     rcx, StringSid; "S-1-5-80-956008885-3418522649-183103804"...
0x180095743  call    cs:__imp_ConvertStringSidToSidW
0x18009574a  nop     dword ptr [rax+rax+00h]
0x18009574f  test    eax, eax
0x180095751  jnz     loc_180095809
0x180095757  call    cs:__imp_GetLastError
0x18009575e  nop     dword ptr [rax+rax+00h]
0x180095763  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009576a  mov     edi, eax
0x18009576c  test    rcx, rcx
0x18009576f  jz      short loc_1800957C3
0x180095771  mov     ebx, 3
0x180095776  lea     r9, aFailedToConver_27; "Failed to convert string SID to SID"
0x18009577d  mov     r8d, ebx
0x180095780  xor     edx, edx
0x180095782  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180095787  test    edi, edi
0x180095789  jg      short loc_18009578F
0x18009578b  mov     eax, edi
0x18009578d  jmp     short loc_180095797
0x18009578f  movzx   eax, di
0x180095792  or      eax, 80070000h
0x180095797  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009579e  lea     r9, a0; ": {0}"
0x1800957a5  mov     [rbp+57h+var_60], eax
0x1800957a8  mov     r8d, ebx
0x1800957ab  lea     rax, [rbp+57h+var_60]
0x1800957af  mov     dl, 1
0x1800957b1  mov     qword ptr [rbp+57h+var_58], rax
0x1800957b5  lea     rax, [rbp+57h+var_58]
0x1800957b9  mov     qword ptr [rsp+0B0h+DeletePrivilegeCount], rax; unsigned int
0x1800957be  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800957c3  test    edi, edi
0x1800957c5  jz      loc_1800958DA
0x1800957cb  mov     edx, 6A5h; void *
0x1800957d0  mov     rcx, [rbp+5Fh]; this
0x1800957d4  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800957db  mov     r9d, edi; char *
0x1800957de  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800957e3  lea     rcx, [rbp+57h+var_38]
0x1800957e7  mov     ebx, eax
0x1800957e9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800957ee  mov     rcx, [rbp+57h+var_40]; this
0x1800957f2  test    rcx, rcx
0x1800957f5  jz      loc_1800958F7
0x1800957fb  call    ?CloseWithRtlFreeSid@Detail@Windows@@YAXPEAX@Z; Windows::Detail::CloseWithRtlFreeSid(void *)
0x180095800  mov     [rbp+57h+var_40], rsi
0x180095804  jmp     loc_1800958F7
0x180095809  mov     rax, [rbp+57h+var_40]
0x18009580d  lea     rcx, [rbp+57h+var_38]
0x180095811  mov     [rbp+57h+SidsToDisable.Sid], rax
0x180095815  mov     qword ptr [rbp+57h+SidsToDisable.Attributes], rsi
0x180095819  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18009581e  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x180095822  lea     r9, [rbp+57h+SidsToDisable]; SidsToDisable
0x180095826  mov     [rsp+0B0h+NewTokenHandle], rax; NewTokenHandle
0x18009582b  mov     edx, 1; Flags
0x180095830  mov     [rsp+0B0h+SidsToRestrict], rsi; SidsToRestrict
0x180095835  mov     r8d, edx; DisableSidCount
0x180095838  mov     [rsp+0B0h+RestrictedSidCount], esi; RestrictedSidCount
0x18009583c  mov     [rsp+0B0h+PrivilegesToDelete], rsi; PrivilegesToDelete
0x180095841  mov     [rsp+0B0h+DeletePrivilegeCount], esi; DeletePrivilegeCount
0x180095845  call    cs:__imp_CreateRestrictedToken
0x18009584c  nop     dword ptr [rax+rax+00h]
0x180095851  test    eax, eax
0x180095853  jnz     short loc_1800958CF
0x180095855  call    cs:__imp_GetLastError
0x18009585c  nop     dword ptr [rax+rax+00h]
0x180095861  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180095868  mov     edi, eax
0x18009586a  test    rcx, rcx
0x18009586d  jz      short loc_1800958C1
0x18009586f  mov     ebx, 3
0x180095874  lea     r9, aFailedToCreate_95; "Failed to create restricted token."
0x18009587b  mov     r8d, ebx
0x18009587e  xor     edx, edx
0x180095880  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180095885  test    edi, edi
0x180095887  jg      short loc_18009588D
0x180095889  mov     eax, edi
0x18009588b  jmp     short loc_180095895
0x18009588d  movzx   eax, di
0x180095890  or      eax, 80070000h
0x180095895  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009589c  lea     r9, a0; ": {0}"
0x1800958a3  mov     [rbp+57h+var_60], eax
0x1800958a6  mov     r8d, ebx
0x1800958a9  lea     rax, [rbp+57h+var_60]
0x1800958ad  mov     dl, 1
0x1800958af  mov     qword ptr [rbp+57h+var_58], rax
0x1800958b3  lea     rax, [rbp+57h+var_58]
0x1800958b7  mov     qword ptr [rsp+0B0h+DeletePrivilegeCount], rax
0x1800958bc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800958c1  test    edi, edi
0x1800958c3  jz      short loc_1800958DA
0x1800958c5  mov     edx, 6B5h
0x1800958ca  jmp     loc_1800957D0
0x1800958cf  mov     rax, [rbp+57h+var_38]
0x1800958d3  mov     [rdi], rax
0x1800958d6  mov     [rbp+57h+var_38], rsi
0x1800958da  lea     rcx, [rbp+57h+var_38]
0x1800958de  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800958e3  mov     rcx, [rbp+57h+var_40]; this
0x1800958e7  test    rcx, rcx
0x1800958ea  jz      short loc_1800958F5
0x1800958ec  call    ?CloseWithRtlFreeSid@Detail@Windows@@YAXPEAX@Z; Windows::Detail::CloseWithRtlFreeSid(void *)
0x1800958f1  mov     [rbp+57h+var_40], rsi
0x1800958f5  mov     ebx, esi
0x1800958f7  lea     rcx, [rbp+57h+ExistingTokenHandle]
0x1800958fb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180095900  mov     eax, ebx
0x180095902  mov     rcx, [rbp+57h+var_28]
0x180095906  xor     rcx, rsp; StackCookie
0x180095909  call    __security_check_cookie
0x18009590e  add     rsp, 98h
0x180095915  pop     rdi
0x180095916  pop     rsi
0x180095917  pop     rbx
0x180095918  pop     rbp
0x180095919  retn
```
