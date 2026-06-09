# Microsoft::Diagnostics::UtcApiManager::ExtractReport(void *,ulong,wchar_t const *,wchar_t const *)

- ea: `0x1801c29c0`
- end: `0x1801c2cc8`
- name: `?ExtractReport@UtcApiManager@Diagnostics@Microsoft@@UEAAJPEAXKPEB_W1@Z`
- size: `776`
- prototype: `int(Microsoft::Diagnostics::UtcApiManager *__hidden this, void *, unsigned int, const wchar_t *, const wchar_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180064e8c`
- `0x1800bc658`
- `0x18013b270`
- `0x1801c29c0`
- `0x1801c2d0c`
- `0x1801c2d28`
- `0x18029324c`
- `0x180298c8c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2a69`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2aea`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2b85`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2c0f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2c61`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2a69`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2aea`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2b85`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2c0f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c2c61`
- `ext-ms-win-wer-reporting-l1-1-1!WerStoreOpen` at `0x1801c2aac`
- `ext-ms-win-wer-reporting-l1-1-1!WerStoreOpen` at `0x1801c2aac`
- `wer!WerpLoadReport` at `0x1801c2b3d`
- `wer!WerpLoadReport` at `0x1801c2b3d`
- `wer!WerpExtractReportFiles` at `0x1801c2bc7`
- `wer!WerpExtractReportFiles` at `0x1801c2bc7`

## string_xrefs

- `0x1801c29e9`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2a49`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2a78`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2ac0`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2af9`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2b51`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2b94`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2bdb`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2c1e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2c70`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801c2c9d`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::ExtractReport(
        Microsoft::Diagnostics::UtcApiManager *this,
        void *a2,
        REPORT_STORE_TYPES a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  int ApiSession; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  int v12; // eax
  unsigned int v13; // ebx
  const char *v14; // r9
  HRESULT v15; // eax
  const char *v16; // r9
  int Report; // eax
  const char *v18; // r9
  int ReportFiles; // eax
  const char *v20; // r9
  const char *v21; // r9
  int v22; // [rsp+20h] [rbp-48h]
  __int64 v23; // [rsp+30h] [rbp-38h] BYREF
  PVOID phReportStore; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-28h] BYREF
  char v26; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    ApiSession = Microsoft::Diagnostics::UtcApiManager::ValidateDiagnosticDataQueryApiSession(this, a2);
    v9 = ApiSession;
    if ( ApiSession < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14DD,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)ApiSession,
        v22);
      return v9;
    }
    if ( a4 && a5 )
    {
      v23 = 0;
      v25[1] = &v23;
      v26 = 1;
      v12 = Microsoft::Diagnostics::UtcApiManager::ImpersonateIfNonAdmin(v8, &v23);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14F6,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)(unsigned int)v12,
          v22);
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x14F2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            v14);
LABEL_22:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
        return v13;
      }
      phReportStore = 0;
      v15 = WerStoreOpen(a3, &phReportStore);
      v13 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14F9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)(unsigned int)v15,
          v22);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportStore);
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x14F2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            v16);
        goto LABEL_22;
      }
      v25[0] = 0;
      Report = WerpLoadReport(phReportStore, a4, v25, 0);
      v13 = Report;
      if ( Report < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14FC,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)(unsigned int)Report,
          0);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v25);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportStore);
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x14F2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            v18);
        goto LABEL_22;
      }
      ReportFiles = WerpExtractReportFiles(v25[0], a5, 0);
      v13 = ReportFiles;
      if ( ReportFiles < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14FD,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)(unsigned int)ReportFiles,
          0);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v25);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportStore);
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x14F2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            v20);
        goto LABEL_22;
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v25);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phReportStore);
      if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x14F2,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          v21);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14E1,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)0x80070057LL,
        v22);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1501,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1801c29c0  mov     [rsp+arg_0], rbx
0x1801c29c5  mov     [rsp+arg_8], rsi
0x1801c29ca  push    r14
0x1801c29cc  sub     rsp, 60h
0x1801c29d0  mov     rsi, r9
0x1801c29d3  mov     r14d, r8d
0x1801c29d6  call    ?ValidateDiagnosticDataQueryApiSession@UtcApiManager@Diagnostics@Microsoft@@AEAAJQEAX@Z; Microsoft::Diagnostics::UtcApiManager::ValidateDiagnosticDataQueryApiSession(void * const)
0x1801c29db  mov     ebx, eax
0x1801c29dd  test    eax, eax
0x1801c29df  jns     short loc_1801C2A01
0x1801c29e1  mov     rcx, [rsp+68h]; this
0x1801c29e6  mov     r9d, eax; char *
0x1801c29e9  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c29f0  mov     edx, 14DDh; void *
0x1801c29f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c29fa  mov     eax, ebx
0x1801c29fc  jmp     loc_1801C2CB6
0x1801c2a01  test    rsi, rsi
0x1801c2a04  jz      loc_1801C2C90
0x1801c2a0a  cmp     [rsp+68h+arg_20], 0
0x1801c2a13  jz      loc_1801C2C90
0x1801c2a19  mov     [rsp+68h+var_38], 0
0x1801c2a22  lea     rax, [rsp+68h+var_38]
0x1801c2a27  mov     [rsp+68h+var_20], rax
0x1801c2a2c  mov     [rsp+68h+var_18], 1
0x1801c2a31  lea     rdx, [rsp+68h+var_38]
0x1801c2a36  call    ?ImpersonateIfNonAdmin@UtcApiManager@Diagnostics@Microsoft@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Diagnostics::UtcApiManager::ImpersonateIfNonAdmin(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1801c2a3b  mov     ebx, eax
0x1801c2a3d  test    eax, eax
0x1801c2a3f  jns     short loc_1801C2A9B
0x1801c2a41  mov     rcx, [rsp+68h]; this
0x1801c2a46  mov     r9d, eax; char *
0x1801c2a49  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2a50  mov     edx, 14F6h; void *
0x1801c2a55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c2a5a  nop
0x1801c2a5b  mov     rcx, [rsp+68h+var_38]
0x1801c2a60  dec     rcx
0x1801c2a63  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801c2a67  ja      short loc_1801C2A8A
0x1801c2a69  call    cs:__imp_RevertToSelf
0x1801c2a6f  mov     rcx, [rsp+68h]; this
0x1801c2a74  test    eax, eax
0x1801c2a76  jnz     short loc_1801C2A8A
0x1801c2a78  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2a7f  mov     edx, 14F2h; void *
0x1801c2a84  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1801c2a8a  lea     rcx, [rsp+68h+var_38]
0x1801c2a8f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2a94  mov     eax, ebx
0x1801c2a96  jmp     loc_1801C2CB6
0x1801c2a9b  mov     [rsp+68h+phReportStore], 0
0x1801c2aa4  lea     rdx, [rsp+68h+phReportStore]; phReportStore
0x1801c2aa9  mov     ecx, r14d; repStoreType
0x1801c2aac  call    cs:__imp_WerStoreOpen
0x1801c2ab2  mov     ebx, eax
0x1801c2ab4  test    eax, eax
0x1801c2ab6  jns     short loc_1801C2B1C
0x1801c2ab8  mov     rcx, [rsp+68h]; this
0x1801c2abd  mov     r9d, eax; char *
0x1801c2ac0  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2ac7  mov     edx, 14F9h; void *
0x1801c2acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c2ad1  lea     rcx, [rsp+68h+phReportStore]
0x1801c2ad6  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?WerStoreClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c2adb  nop
0x1801c2adc  mov     rcx, [rsp+68h+var_38]
0x1801c2ae1  dec     rcx
0x1801c2ae4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801c2ae8  ja      short loc_1801C2B0B
0x1801c2aea  call    cs:__imp_RevertToSelf
0x1801c2af0  mov     rcx, [rsp+68h]; this
0x1801c2af5  test    eax, eax
0x1801c2af7  jnz     short loc_1801C2B0B
0x1801c2af9  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2b00  mov     edx, 14F2h; void *
0x1801c2b05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1801c2b0b  lea     rcx, [rsp+68h+var_38]
0x1801c2b10  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2b15  mov     eax, ebx
0x1801c2b17  jmp     loc_1801C2CB6
0x1801c2b1c  mov     [rsp+68h+var_28], 0
0x1801c2b25  mov     [rsp+68h+var_48], 0; int
0x1801c2b2d  xor     r9d, r9d
0x1801c2b30  lea     r8, [rsp+68h+var_28]
0x1801c2b35  mov     rdx, rsi
0x1801c2b38  mov     rcx, [rsp+68h+phReportStore]
0x1801c2b3d  call    cs:__imp_WerpLoadReport
0x1801c2b43  mov     ebx, eax
0x1801c2b45  test    eax, eax
0x1801c2b47  jns     short loc_1801C2BB7
0x1801c2b49  mov     rcx, [rsp+68h]; this
0x1801c2b4e  mov     r9d, eax; char *
0x1801c2b51  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2b58  mov     edx, 14FCh; void *
0x1801c2b5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c2b62  lea     rcx, [rsp+68h+var_28]
0x1801c2b67  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c2b6c  lea     rcx, [rsp+68h+phReportStore]
0x1801c2b71  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?WerStoreClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c2b76  nop
0x1801c2b77  mov     rax, [rsp+68h+var_38]
0x1801c2b7c  dec     rax
0x1801c2b7f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801c2b83  ja      short loc_1801C2BA6
0x1801c2b85  call    cs:__imp_RevertToSelf
0x1801c2b8b  mov     rcx, [rsp+68h]; this
0x1801c2b90  test    eax, eax
0x1801c2b92  jnz     short loc_1801C2BA6
0x1801c2b94  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2b9b  mov     edx, 14F2h; void *
0x1801c2ba0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1801c2ba6  lea     rcx, [rsp+68h+var_38]
0x1801c2bab  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2bb0  mov     eax, ebx
0x1801c2bb2  jmp     loc_1801C2CB6
0x1801c2bb7  xor     r8d, r8d
0x1801c2bba  mov     rdx, [rsp+68h+arg_20]
0x1801c2bc2  mov     rcx, [rsp+68h+var_28]
0x1801c2bc7  call    cs:__imp_WerpExtractReportFiles
0x1801c2bcd  mov     ebx, eax
0x1801c2bcf  test    eax, eax
0x1801c2bd1  jns     short loc_1801C2C3E
0x1801c2bd3  mov     rcx, [rsp+68h]; this
0x1801c2bd8  mov     r9d, eax; char *
0x1801c2bdb  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2be2  mov     edx, 14FDh; void *
0x1801c2be7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c2bec  lea     rcx, [rsp+68h+var_28]
0x1801c2bf1  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c2bf6  lea     rcx, [rsp+68h+phReportStore]
0x1801c2bfb  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?WerStoreClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c2c00  nop
0x1801c2c01  mov     rax, [rsp+68h+var_38]
0x1801c2c06  dec     rax
0x1801c2c09  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801c2c0d  ja      short loc_1801C2C30
0x1801c2c0f  call    cs:__imp_RevertToSelf
0x1801c2c15  mov     rcx, [rsp+68h]; this
0x1801c2c1a  test    eax, eax
0x1801c2c1c  jnz     short loc_1801C2C30
0x1801c2c1e  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2c25  mov     edx, 14F2h; void *
0x1801c2c2a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1801c2c30  lea     rcx, [rsp+68h+var_38]
0x1801c2c35  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2c3a  mov     eax, ebx
0x1801c2c3c  jmp     short loc_1801C2CB6
0x1801c2c3e  lea     rcx, [rsp+68h+var_28]
0x1801c2c43  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&WerReportCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c2c48  lea     rcx, [rsp+68h+phReportStore]
0x1801c2c4d  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?WerStoreClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&WerStoreClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c2c52  nop
0x1801c2c53  mov     rax, [rsp+68h+var_38]
0x1801c2c58  dec     rax
0x1801c2c5b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801c2c5f  ja      short loc_1801C2C82
0x1801c2c61  call    cs:__imp_RevertToSelf
0x1801c2c67  mov     rcx, [rsp+68h]; this
0x1801c2c6c  test    eax, eax
0x1801c2c6e  jnz     short loc_1801C2C82
0x1801c2c70  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2c77  mov     edx, 14F2h; void *
0x1801c2c7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1801c2c82  lea     rcx, [rsp+68h+var_38]
0x1801c2c87  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c2c8c  xor     eax, eax
0x1801c2c8e  jmp     short loc_1801C2CB6
0x1801c2c90  mov     rcx, [rsp+68h]; this
0x1801c2c95  mov     ebx, 80070057h
0x1801c2c9a  mov     r9d, ebx; char *
0x1801c2c9d  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x1801c2ca4  mov     edx, 14E1h; void *
0x1801c2ca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c2cae  mov     eax, ebx
0x1801c2cb0  jmp     short loc_1801C2CB6
0x1801c2cb2  mov     eax, dword ptr [rsp+68h+var_38]
0x1801c2cb6  mov     rbx, [rsp+68h+arg_0]
0x1801c2cbb  mov     rsi, [rsp+68h+arg_8]
0x1801c2cc0  add     rsp, 60h
0x1801c2cc4  pop     r14
0x1801c2cc6  retn
```
