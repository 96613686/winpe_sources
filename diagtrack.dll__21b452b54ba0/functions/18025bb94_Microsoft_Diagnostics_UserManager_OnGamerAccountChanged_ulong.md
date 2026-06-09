# Microsoft::Diagnostics::UserManager::OnGamerAccountChanged(ulong)

- ea: `0x18025bb94`
- end: `0x18025be89`
- name: `?OnGamerAccountChanged@UserManager@Diagnostics@Microsoft@@AEAAJK@Z`
- size: `757`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UserManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18025afa0`

## callees

- `0x180004b24`
- `0x180024558`
- `0x18002abec`
- `0x18002afd8`
- `0x18002df00`
- `0x180049bec`
- `0x180053ff4`
- `0x1800561a4`
- `0x180064e34`
- `0x180064e8c`
- `0x180081924`
- `0x1800bc658`
- `0x1800e86c0`
- `0x1800e9a00`
- `0x1800fc72c`
- `0x18010022c`
- `0x18010024c`
- `0x180129fe0`
- `0x180139730`
- `0x18013cca4`
- `0x180142fcc`
- `0x1801c2d0c`
- `0x1801dd8c8`
- `0x18020aac0`
- `0x18025bb94`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18025bdbe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18025bdbe`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18025bcd7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18025bcd7`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x18025bbc6`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x18025bbc6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18025bcac`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18025bcac`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18025bc80`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18025bc80`

## string_xrefs

- `0x18025be45`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x18025be77`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Diagnostics::UserManager::OnGamerAccountChanged(
        Microsoft::Diagnostics::UserManager *this,
        unsigned int a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  Microsoft::Diagnostics::TelemetryAssert *TelemetryAssert; // rax
  struct Microsoft::Diagnostics::UserManager::SessionInformation *Session; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // r15
  CONTEXT *v11; // rsi
  __int64 v12; // r8
  int v13; // eax
  unsigned int v14; // edi
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  _QWORD *v18; // rax
  const char *v19; // r9
  struct Microsoft::Diagnostics::AsimovEventSerializer *AsimovEventSerializer; // rax
  int v22; // [rsp+20h] [rbp-79h]
  HANDLE hToken; // [rsp+48h] [rbp-51h] BYREF
  wchar_t *v24; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v25; // [rsp+58h] [rbp-41h] BYREF
  __int64 v26; // [rsp+60h] [rbp-39h] BYREF
  _QWORD *v27; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v28[16]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v29[16]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v30[16]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v31[4]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  if ( (unsigned int)XblaIsConsole() )
  {
    if ( (unsigned int)dword_1804543B0 > 2 )
    {
      v24 = (wchar_t *)"OnGamerAccountChanged";
      hToken = "!XblaIsConsole()";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v4,
        (unsigned int)&dword_1803E621C,
        v5,
        v6,
        (__int64)&hToken,
        (__int64)&v24);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      TelemetryAssert = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::TelemetryAssert::Assert(TelemetryAssert);
    }
  }
  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v29, (char *)this + 8);
  Session = Microsoft::Diagnostics::UserManager::GetSession(this, a2);
  v9 = (_QWORD *)*((_QWORD *)Session + 1);
  v10 = (_QWORD *)*((_QWORD *)Session + 2);
  if ( v9 == v10 )
  {
LABEL_20:
    if ( _InterlockedCompareExchange64((_QWORD *)&xmmword_1804631C0 + 1, 0, 0) )
    {
      AsimovEventSerializer = Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::AsimovSharedPartAState::UpdateXblExtensionData((struct Microsoft::Diagnostics::AsimovEventSerializer *)((char *)AsimovEventSerializer + 8));
    }
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v29);
    return 0;
  }
  else
  {
    v11 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
    while ( 1 )
    {
      hToken = 0;
      RtlCaptureContext(v11);
      LOBYTE(v12) = 2;
      Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(v28, 240000, v12, v11);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hToken,
        0);
      v13 = UMgrQueryUserToken(*v9, &hToken);
      v14 = v13;
      if ( v13 < 0 )
        break;
      Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)v28);
      if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && ImpersonateLoggedOnUser(hToken) )
      {
        std::wstring::wstring(v31);
        v24 = 0;
        if ( (int)XblAuthConfig::GetGamerAccountXuidForImpersonatedUser(&v24) >= 0 )
          std::wstring::assign(v31, v24);
        std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v30, (char *)this + 88);
        std::wstring::operator=(v9 + 5, v31);
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 2048) )
        {
          v18 = v31;
          if ( v31[3] > 7u )
            v18 = (_QWORD *)v31[0];
          v27 = v18;
          v26 = *v9;
          v25 = a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(
            v15,
            (unsigned int)byte_1803E61CB,
            v16,
            v17,
            (__int64)&v25,
            (__int64)&v26,
            (__int64)&v27);
        }
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v30);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v24);
        std::wstring::_Tidy_deallocate(v31);
        if ( !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x409,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
            v19);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      v9 += 14;
      if ( v9 == v10 )
        goto LABEL_20;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      (const char *)(unsigned int)v13,
      v22);
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)v28);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v29);
    return v14;
  }
}

```

## disassembly

```asm
0x18025bb94  mov     [rsp-8+arg_10], rbx
0x18025bb99  mov     [rsp-8+arg_18], rsi
0x18025bb9e  push    rbp
0x18025bb9f  push    rdi
0x18025bba0  push    r12
0x18025bba2  push    r14
0x18025bba4  push    r15
0x18025bba6  lea     rbp, [rsp-37h]
0x18025bbab  sub     rsp, 0D0h
0x18025bbb2  mov     rax, cs:__security_cookie
0x18025bbb9  xor     rax, rsp
0x18025bbbc  mov     [rbp+57h+var_30], rax
0x18025bbc0  mov     r12d, edx
0x18025bbc3  mov     r14, rcx
0x18025bbc6  call    cs:__imp_XblaIsConsole
0x18025bbcc  test    eax, eax
0x18025bbce  jz      short loc_18025BC33
0x18025bbd0  mov     eax, cs:dword_1804543B0
0x18025bbd6  cmp     eax, 2
0x18025bbd9  jbe     short loc_18025BC0F
0x18025bbdb  lea     rax, aOngameraccount; "OnGamerAccountChanged"
0x18025bbe2  mov     [rbp+57h+var_A0], rax
0x18025bbe6  lea     rax, aXblaisconsole_0; "!XblaIsConsole()"
0x18025bbed  mov     [rbp+57h+hToken], rax
0x18025bbf1  lea     rax, [rbp+57h+var_A0]
0x18025bbf5  mov     [rsp+0F0h+var_C8], rax
0x18025bbfa  lea     rax, [rbp+57h+hToken]
0x18025bbfe  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x18025bc03  lea     rdx, dword_1803E621C
0x18025bc0a  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18025bc0f  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18025bc16  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x18025bc1b  test    al, al
0x18025bc1d  jz      short loc_18025BC33
0x18025bc1f  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18025bc26  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x18025bc2b  mov     rcx, rax; this
0x18025bc2e  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x18025bc33  lea     rdx, [r14+8]
0x18025bc37  lea     rcx, [rbp+57h+var_70]
0x18025bc3b  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x18025bc40  nop
0x18025bc41  mov     edx, r12d; unsigned int
0x18025bc44  mov     rcx, r14; this
0x18025bc47  call    ?GetSession@UserManager@Diagnostics@Microsoft@@AEAAAEAUSessionInformation@123@K@Z; Microsoft::Diagnostics::UserManager::GetSession(ulong)
0x18025bc4c  mov     rbx, [rax+8]
0x18025bc50  mov     r15, [rax+10h]
0x18025bc54  cmp     rbx, r15
0x18025bc57  jz      loc_18025BDE6
0x18025bc5d  mov     ecx, cs:_tls_index
0x18025bc63  mov     rax, gs:58h
0x18025bc6c  mov     esi, 40h ; '@'
0x18025bc71  add     rsi, [rax+rcx*8]
0x18025bc75  mov     [rbp+57h+hToken], 0
0x18025bc7d  mov     rcx, rsi; ContextRecord
0x18025bc80  call    cs:__imp_RtlCaptureContext
0x18025bc86  mov     r9, rsi
0x18025bc89  mov     r8b, 2
0x18025bc8c  mov     edx, 3A980h
0x18025bc91  lea     rcx, [rbp+57h+var_80]
0x18025bc95  call    ??0ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@KVExternalHangBucket@EnumDetails@23@AEBU_CONTEXT@@@Z; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(ulong,Microsoft::Diagnostics::EnumDetails::ExternalHangBucket,_CONTEXT const &)
0x18025bc9a  xor     edx, edx
0x18025bc9c  lea     rcx, [rbp+57h+hToken]
0x18025bca0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18025bca5  lea     rdx, [rbp+57h+hToken]
0x18025bca9  mov     rcx, [rbx]
0x18025bcac  call    cs:__imp_UMgrQueryUserToken
0x18025bcb2  mov     edi, eax
0x18025bcb4  test    eax, eax
0x18025bcb6  js      loc_18025BE3E
0x18025bcbc  lea     rcx, [rbp+57h+var_80]; this
0x18025bcc0  call    ??1ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor(void)
0x18025bcc5  mov     rcx, [rbp+57h+hToken]; hToken
0x18025bcc9  lea     rax, [rcx-1]
0x18025bccd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18025bcd1  ja      loc_18025BDD0
0x18025bcd7  call    cs:__imp_ImpersonateLoggedOnUser
0x18025bcdd  test    eax, eax
0x18025bcdf  jz      loc_18025BDD0
0x18025bce5  mov     [rbp+57h+var_AF], 1
0x18025bce9  lea     rdx, Src
0x18025bcf0  lea     rcx, [rbp+57h+var_50]
0x18025bcf4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18025bcf9  nop
0x18025bcfa  mov     [rbp+57h+var_A0], 0
0x18025bd02  lea     rcx, [rbp+57h+var_A0]; wchar_t **
0x18025bd06  call    ?GetGamerAccountXuidForImpersonatedUser@XblAuthConfig@@SAJPEAPEA_W@Z; XblAuthConfig::GetGamerAccountXuidForImpersonatedUser(wchar_t * *)
0x18025bd0b  test    eax, eax
0x18025bd0d  js      short loc_18025BD1C
0x18025bd0f  mov     rdx, [rbp+57h+var_A0]
0x18025bd13  lea     rcx, [rbp+57h+var_50]
0x18025bd17  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18025bd1c  lea     rdx, [r14+58h]
0x18025bd20  lea     rcx, [rbp+57h+var_60]
0x18025bd24  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x18025bd29  nop
0x18025bd2a  lea     rcx, [rbx+28h]
0x18025bd2e  lea     rdx, [rbp+57h+var_50]
0x18025bd32  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18025bd37  mov     eax, cs:dword_1804543B0
0x18025bd3d  cmp     eax, 4
0x18025bd40  jbe     short loc_18025BD9C
0x18025bd42  mov     edx, 800h
0x18025bd47  lea     rcx, dword_1804543B0
0x18025bd4e  call    _tlgKeywordOn
0x18025bd53  test    al, al
0x18025bd55  jz      short loc_18025BD9C
0x18025bd57  lea     rax, [rbp+57h+var_50]
0x18025bd5b  cmp     [rbp+57h+var_38], 7
0x18025bd60  cmova   rax, [rbp+57h+var_50]
0x18025bd65  mov     [rbp+57h+var_88], rax
0x18025bd69  mov     rax, [rbx]
0x18025bd6c  mov     [rbp+57h+var_90], rax
0x18025bd70  mov     [rbp+57h+var_98], r12d
0x18025bd74  lea     rax, [rbp+57h+var_88]
0x18025bd78  mov     [rsp+0F0h+var_C0], rax
0x18025bd7d  lea     rax, [rbp+57h+var_90]
0x18025bd81  mov     [rsp+0F0h+var_C8], rax
0x18025bd86  lea     rax, [rbp+57h+var_98]
0x18025bd8a  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18025bd8f  lea     rdx, byte_1803E61CB
0x18025bd96  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &)
0x18025bd9b  nop
0x18025bd9c  lea     rcx, [rbp+57h+var_60]
0x18025bda0  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18025bda5  nop
0x18025bda6  lea     rcx, [rbp+57h+var_A0]
0x18025bdaa  call    ??1?$unique_storage@U?$resource_policy@PEA_W$$A6AXPEAX@Z$1?CloseHeapPointer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18025bdaf  nop
0x18025bdb0  lea     rcx, [rbp+57h+var_50]
0x18025bdb4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18025bdb9  nop
0x18025bdba  mov     [rbp+57h+var_AF], 0
0x18025bdbe  call    cs:__imp_RevertToSelf
0x18025bdc4  mov     rcx, [rbp+5Fh]; this
0x18025bdc8  test    eax, eax
0x18025bdca  jz      loc_18025BE77
0x18025bdd0  lea     rcx, [rbp+57h+hToken]
0x18025bdd4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18025bdd9  add     rbx, 70h ; 'p'
0x18025bddd  cmp     rbx, r15
0x18025bde0  jnz     loc_18025BC75
0x18025bde6  xor     edx, edx
0x18025bde8  xor     eax, eax
0x18025bdea  lock cmpxchg qword ptr cs:xmmword_1804631C0+8, rdx
0x18025bdf3  jz      short loc_18025BE0B
0x18025bdf5  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18025bdfc  call    ?GetAsimovEventSerializer@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAsimovEventSerializer@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer(void)
0x18025be01  lea     rcx, [rax+8]; this
0x18025be05  call    ?UpdateXblExtensionData@AsimovSharedPartAState@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::AsimovSharedPartAState::UpdateXblExtensionData(void)
0x18025be0a  nop
0x18025be0b  lea     rcx, [rbp+57h+var_70]
0x18025be0f  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18025be14  xor     eax, eax
0x18025be16  mov     rcx, [rbp+57h+var_30]
0x18025be1a  xor     rcx, rsp; StackCookie
0x18025be1d  call    __security_check_cookie
0x18025be22  lea     r11, [rsp+0F0h+var_20]
0x18025be2a  mov     rbx, [r11+40h]
0x18025be2e  mov     rsi, [r11+48h]
0x18025be32  mov     rsp, r11
0x18025be35  pop     r15
0x18025be37  pop     r14
0x18025be39  pop     r12
0x18025be3b  pop     rdi
0x18025be3c  pop     rbp
0x18025be3d  retn
0x18025be3e  mov     rcx, [rbp+5Fh]; this
0x18025be42  mov     r9d, edi; char *
0x18025be45  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x18025be4c  mov     edx, 3FEh; void *
0x18025be51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025be56  lea     rcx, [rbp+57h+var_80]; this
0x18025be5a  call    ??1ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor(void)
0x18025be5f  nop
0x18025be60  lea     rcx, [rbp+57h+hToken]
0x18025be64  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18025be69  nop
0x18025be6a  lea     rcx, [rbp+57h+var_70]
0x18025be6e  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18025be73  mov     eax, edi
0x18025be75  jmp     short loc_18025BE16
0x18025be77  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x18025be7e  mov     edx, 409h; void *
0x18025be83  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
