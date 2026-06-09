# shared::ActivityPolicies::IsConsentGrantedOrNotApplicable(void)

- ea: `0x1800f3c68`
- end: `0x1800f3ff7`
- name: `?IsConsentGrantedOrNotApplicable@ActivityPolicies@shared@@AEBA_NXZ`
- size: `911`
- prototype: `bool __fastcall(_Mtx_t this)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004474c`
- `0x1800b9eb8`

## callees

- `0x18000f128`
- `0x180010ee0`
- `0x1800110f8`
- `0x180030190`
- `0x18004e170`
- `0x1800a5bc8`
- `0x1800a87d8`
- `0x1800f3c68`
- `0x1800f4000`
- `0x1800fd440`
- `0x1801004fc`
- `0x18017b3f0`
- `0x180190d8c`
- `0x1801f6fb0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f3d21`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f3d5f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f3d21`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f3d5f`
- `msvcp_win!_Mtx_unlock` at `0x1800f3cc9`
- `msvcp_win!_Mtx_unlock` at `0x1800f3fc8`
- `msvcp_win!_Mtx_unlock` at `0x1800f3cc9`
- `msvcp_win!_Mtx_unlock` at `0x1800f3fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f3d0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f3d49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f3d0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f3d49`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
bool __fastcall shared::ActivityPolicies::IsConsentGrantedOrNotApplicable(__int64 **this)
{
  __int64 *v2; // rbx
  __int64 v4; // r14
  HRESULT v5; // eax
  HSTRING v6; // rsi
  HRESULT v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  const char *v10; // rsi
  const char *v11; // rax
  bool v12; // bl
  __int64 v13; // rcx
  const char *v14; // rax
  __int64 v15; // rcx
  const char *v16; // rax
  const char *v17; // rax
  const char *v18; // rax
  __int64 v19; // rax
  int v20; // ecx
  char v21; // [rsp+30h] [rbp-D0h] BYREF
  char v22; // [rsp+31h] [rbp-CFh] BYREF
  _BYTE v23[6]; // [rsp+32h] [rbp-CEh] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  const char *v25; // [rsp+40h] [rbp-C0h] BYREF
  const char *v26; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER v30; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v31; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v32[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v34[352]; // [rsp+E0h] [rbp-20h] BYREF

  v27[1] = this;
  std::_Mutex_base::lock((std::_Mutex_base *)this);
  if ( !this[23] && (int)shared::ActivityPolicies::InitializeConsentCoordinator((shared::ActivityPolicies *)this) < 0
    || (v2 = this[23]) == 0 )
  {
    _Mtx_unlock((_Mtx_t)this);
    return 0;
  }
  v24 = 0;
  v4 = *v2;
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(&v24);
  string = 0;
  v5 = WindowsCreateStringReference(L"DataSharing", 0xBu, &hstringHeader, &string);
  if ( v5 < 0 )
    RaiseException(v5, 1u, 0, 0);
  v6 = string;
  v31 = 0;
  v7 = WindowsCreateStringReference(L"WindowsAccountSyncConsent", 0x19u, &v30, &v31);
  if ( v7 < 0 )
    RaiseException(v7, 1u, 0, 0);
  if ( (*(int (__fastcall **)(__int64 *, HSTRING, HSTRING, __int64 *))(v4 + 56))(v2, v31, v6, &v24) < 0 )
  {
    v8 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_37;
  }
  if ( !v24 || (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 48LL))(v24, &v21) < 0 )
  {
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(&v24);
LABEL_37:
    v12 = 0;
    goto LABEL_38;
  }
  v10 = "true";
  v11 = "true";
  if ( !v21 )
    v11 = "false";
  v25 = v11;
  Log<std::string const &,char const *>(
    v9,
    "{\"text\":\"Consent state for stableUserId: %s - Applicable: %s\"}",
    (const char *)this + 120,
    (const char *)&v25);
  if ( v21 )
  {
    Log<std::string const &>(
      3,
      "{\"text\":\"Consent details available for stableUserId: %s\"}",
      (const char *)this + 120);
    if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v24 + 56LL))(v24, v23) >= 0 )
    {
      v14 = "true";
      if ( !v23[0] )
        v14 = "false";
      v25 = v14;
      Log<std::string const &,char const *>(
        v13,
        "{\"text\":\"Consent state for stableUserId: %s - Available: %s\"}",
        (const char *)this + 120,
        (const char *)&v25);
      if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 64LL))(v24, &v22) >= 0 )
      {
        v16 = "true";
        if ( !v22 )
          v16 = "false";
        v25 = v16;
        Log<std::string const &,char const *>(
          v15,
          "{\"text\":\"Consent state for stableUserId: %s - Accepted: %s\"}",
          (const char *)this + 120,
          (const char *)&v25);
        v12 = v23[0] && v22;
        v17 = "true";
        if ( !v22 )
          v17 = "false";
        v25 = v17;
        v18 = "true";
        if ( !v21 )
          v18 = "false";
        v26 = v18;
        if ( !v23[0] )
          v10 = "false";
        v27[0] = v10;
        cdp::StringFormat<unsigned __int64 &,unsigned __int64 &,unsigned __int64 &>(
          (unsigned int)v32,
          (unsigned int)"IsAvailable:%s|IsApplicable:%s|IsAccepted:%s",
          (unsigned int)v27,
          (unsigned int)&v26,
          (__int64)&v25);
        v19 = cdp::CorrelationVectorData::CreateOrExtendCorrelationVector(v33, 0);
        cdp::CorrelationVectorData::CorrelationVectorData(v34, v19);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v33);
        std::string::string(&hstringHeader, qword_1803986E0);
        std::string::string(&v30, "CdsActivityPolicy.ActivityBlockedByConsent");
        shared::ActivityPolicies::SendActivityPolicyTelemetry(
          v20,
          (unsigned int)&v30,
          (unsigned int)v32,
          (unsigned int)v34,
          (__int64)&hstringHeader);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v30);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&hstringHeader);
        cdp::CorrelationVectorData::~CorrelationVectorData((cdp::CorrelationVectorData *)v34);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v32);
        Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(&v24);
        goto LABEL_38;
      }
    }
    goto LABEL_36;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(&v24);
  v12 = 1;
LABEL_38:
  _Mtx_unlock((_Mtx_t)this);
  return v12;
}

```

## disassembly

```asm
0x1800f3c68  mov     [rsp-8+arg_8], rbx
0x1800f3c6d  mov     [rsp-8+arg_10], rsi
0x1800f3c72  push    rbp
0x1800f3c73  push    rdi
0x1800f3c74  push    r14
0x1800f3c76  lea     rbp, [rsp-150h]
0x1800f3c7e  sub     rsp, 250h
0x1800f3c85  mov     rax, cs:__security_cookie
0x1800f3c8c  xor     rax, rsp
0x1800f3c8f  mov     [rbp+160h+var_20], rax
0x1800f3c96  mov     rdi, rcx
0x1800f3c99  mov     [rsp+260h+var_208], rcx
0x1800f3c9e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800f3ca3  nop
0x1800f3ca4  cmp     qword ptr [rdi+0B8h], 0
0x1800f3cac  jnz     short loc_1800F3CBA
0x1800f3cae  mov     rcx, rdi; this
0x1800f3cb1  call    ?InitializeConsentCoordinator@ActivityPolicies@shared@@AEBAJXZ; shared::ActivityPolicies::InitializeConsentCoordinator(void)
0x1800f3cb6  test    eax, eax
0x1800f3cb8  js      short loc_1800F3CC6
0x1800f3cba  mov     rbx, [rdi+0B8h]
0x1800f3cc1  test    rbx, rbx
0x1800f3cc4  jnz     short loc_1800F3CD6
0x1800f3cc6  mov     rcx, rdi; _Mtx_t
0x1800f3cc9  call    cs:__imp__Mtx_unlock
0x1800f3ccf  xor     al, al
0x1800f3cd1  jmp     loc_1800F3FD0
0x1800f3cd6  mov     [rsp+260h+var_228], 0
0x1800f3cdf  mov     r14, [rbx]
0x1800f3ce2  lea     rcx, [rsp+260h+var_228]
0x1800f3ce7  call    ?InternalRelease@?$ComPtr@UIUnifiedConsentCoordinatorFactory@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(void)
0x1800f3cec  mov     [rsp+260h+string], 0
0x1800f3cf5  lea     r9, [rsp+260h+string]; string
0x1800f3cfa  lea     r8, [rsp+260h+hstringHeader]; hstringHeader
0x1800f3cff  mov     edx, 0Bh; length
0x1800f3d04  lea     rcx, sourceString; "DataSharing"
0x1800f3d0b  call    cs:__imp_WindowsCreateStringReference
0x1800f3d11  test    eax, eax
0x1800f3d13  jns     short loc_1800F3D28
0x1800f3d15  xor     r9d, r9d; lpArguments
0x1800f3d18  xor     r8d, r8d; nNumberOfArguments
0x1800f3d1b  lea     edx, [r9+1]; dwExceptionFlags
0x1800f3d1f  mov     ecx, eax; dwExceptionCode
0x1800f3d21  call    cs:__imp_RaiseException
0x1800f3d27  nop
0x1800f3d28  mov     rsi, [rsp+260h+string]
0x1800f3d2d  mov     [rbp+160h+var_1C8], 0
0x1800f3d35  lea     r9, [rbp+160h+var_1C8]; string
0x1800f3d39  lea     r8, [rbp+160h+var_1E0]; hstringHeader
0x1800f3d3d  mov     edx, 19h; length
0x1800f3d42  lea     rcx, aWindowsaccount; "WindowsAccountSyncConsent"
0x1800f3d49  call    cs:__imp_WindowsCreateStringReference
0x1800f3d4f  test    eax, eax
0x1800f3d51  jns     short loc_1800F3D66
0x1800f3d53  xor     r9d, r9d; lpArguments
0x1800f3d56  xor     r8d, r8d; nNumberOfArguments
0x1800f3d59  lea     edx, [r9+1]; dwExceptionFlags
0x1800f3d5d  mov     ecx, eax; dwExceptionCode
0x1800f3d5f  call    cs:__imp_RaiseException
0x1800f3d65  nop
0x1800f3d66  lea     r9, [rsp+260h+var_228]
0x1800f3d6b  mov     r8, rsi
0x1800f3d6e  mov     rdx, [rbp+160h+var_1C8]
0x1800f3d72  mov     rcx, rbx
0x1800f3d75  mov     rax, [r14+38h]
0x1800f3d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3d7e  nop
0x1800f3d7f  test    eax, eax
0x1800f3d81  jns     short loc_1800F3DA8
0x1800f3d83  mov     rcx, [rsp+260h+var_228]
0x1800f3d88  test    rcx, rcx
0x1800f3d8b  jz      short loc_1800F3DA3
0x1800f3d8d  mov     [rsp+260h+var_228], 0
0x1800f3d96  mov     rax, [rcx]
0x1800f3d99  mov     rax, [rax+10h]
0x1800f3d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3da2  nop
0x1800f3da3  jmp     loc_1800F3FC3
0x1800f3da8  mov     rcx, [rsp+260h+var_228]
0x1800f3dad  test    rcx, rcx
0x1800f3db0  jz      loc_1800F3FB9
0x1800f3db6  mov     rax, [rcx]
0x1800f3db9  lea     rdx, [rsp+260h+var_230]
0x1800f3dbe  mov     rax, [rax+30h]
0x1800f3dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3dc7  test    eax, eax
0x1800f3dc9  js      loc_1800F3FB9
0x1800f3dcf  lea     rsi, Str; "true"
0x1800f3dd6  mov     rax, rsi
0x1800f3dd9  lea     r14, aFalse; "false"
0x1800f3de0  cmp     [rsp+260h+var_230], 0
0x1800f3de5  cmovz   rax, r14
0x1800f3de9  mov     [rsp+260h+var_220], rax
0x1800f3dee  lea     rbx, [rdi+78h]
0x1800f3df2  lea     r9, [rsp+260h+var_220]
0x1800f3df7  mov     r8, rbx
0x1800f3dfa  lea     rdx, aTextConsentSta_1; "{\"text\":\"Consent state for stableUse"...
0x1800f3e01  call    ??$Log@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@@YAXW4CDPLogLevel@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAPEBD@Z; Log<std::string const &,char const *>(CDPLogLevel,char const *,std::string const &,char const * &&)
0x1800f3e06  cmp     [rsp+260h+var_230], 0
0x1800f3e0b  jnz     short loc_1800F3E21
0x1800f3e0d  lea     rcx, [rsp+260h+var_228]
0x1800f3e12  call    ?InternalRelease@?$ComPtr@UIUnifiedConsentCoordinatorFactory@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(void)
0x1800f3e17  mov     ebx, 1
0x1800f3e1c  jmp     loc_1800F3FC5
0x1800f3e21  mov     r8, rbx
0x1800f3e24  lea     rdx, aTextConsentDet; "{\"text\":\"Consent details available f"...
0x1800f3e2b  mov     ecx, 3
0x1800f3e30  call    ??$Log@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@@YAXW4CDPLogLevel@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Log<std::string const &>(CDPLogLevel,char const *,std::string const &)
0x1800f3e35  mov     rcx, [rsp+260h+var_228]
0x1800f3e3a  mov     rax, [rcx]
0x1800f3e3d  lea     rdx, [rsp+260h+var_22E]
0x1800f3e42  mov     rax, [rax+38h]
0x1800f3e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3e4b  test    eax, eax
0x1800f3e4d  js      loc_1800F3FB9
0x1800f3e53  mov     rax, rsi
0x1800f3e56  cmp     [rsp+260h+var_22E], 0
0x1800f3e5b  cmovz   rax, r14
0x1800f3e5f  mov     [rsp+260h+var_220], rax
0x1800f3e64  lea     r9, [rsp+260h+var_220]
0x1800f3e69  mov     r8, rbx
0x1800f3e6c  lea     rdx, aTextConsentSta_0; "{\"text\":\"Consent state for stableUse"...
0x1800f3e73  call    ??$Log@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@@YAXW4CDPLogLevel@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAPEBD@Z; Log<std::string const &,char const *>(CDPLogLevel,char const *,std::string const &,char const * &&)
0x1800f3e78  mov     rcx, [rsp+260h+var_228]
0x1800f3e7d  mov     rax, [rcx]
0x1800f3e80  lea     rdx, [rsp+260h+var_22F]
0x1800f3e85  mov     rax, [rax+40h]
0x1800f3e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3e8e  test    eax, eax
0x1800f3e90  js      loc_1800F3FB9
0x1800f3e96  mov     rax, rsi
0x1800f3e99  cmp     [rsp+260h+var_22F], 0
0x1800f3e9e  cmovz   rax, r14
0x1800f3ea2  mov     [rsp+260h+var_220], rax
0x1800f3ea7  lea     r9, [rsp+260h+var_220]
0x1800f3eac  mov     r8, rbx
0x1800f3eaf  lea     rdx, aTextConsentSta; "{\"text\":\"Consent state for stableUse"...
0x1800f3eb6  call    ??$Log@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@@YAXW4CDPLogLevel@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAPEBD@Z; Log<std::string const &,char const *>(CDPLogLevel,char const *,std::string const &,char const * &&)
0x1800f3ebb  mov     cl, [rsp+260h+var_22F]
0x1800f3ebf  mov     dl, [rsp+260h+var_22E]
0x1800f3ec3  test    dl, dl
0x1800f3ec5  jz      short loc_1800F3ED2
0x1800f3ec7  test    cl, cl
0x1800f3ec9  jz      short loc_1800F3ED2
0x1800f3ecb  mov     ebx, 1
0x1800f3ed0  jmp     short loc_1800F3ED4
0x1800f3ed2  xor     bl, bl
0x1800f3ed4  mov     rax, rsi
0x1800f3ed7  test    cl, cl
0x1800f3ed9  cmovz   rax, r14
0x1800f3edd  mov     [rsp+260h+var_220], rax
0x1800f3ee2  mov     rax, rsi
0x1800f3ee5  cmp     [rsp+260h+var_230], 0
0x1800f3eea  cmovz   rax, r14
0x1800f3eee  mov     [rsp+260h+var_218], rax
0x1800f3ef3  test    dl, dl
0x1800f3ef5  cmovz   rsi, r14
0x1800f3ef9  mov     [rsp+260h+var_210], rsi
0x1800f3efe  lea     rax, [rsp+260h+var_220]
0x1800f3f03  mov     [rsp+260h+var_240], rax
0x1800f3f08  lea     r9, [rsp+260h+var_218]
0x1800f3f0d  lea     r8, [rsp+260h+var_210]
0x1800f3f12  lea     rdx, aIsavailableSIs; "IsAvailable:%s|IsApplicable:%s|IsAccept"...
0x1800f3f19  lea     rcx, [rbp+160h+var_1C0]
0x1800f3f1d  call    ??$StringFormat@AEA_KAEA_KAEA_K@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDAEA_K11@Z; cdp::StringFormat<unsigned __int64 &,unsigned __int64 &,unsigned __int64 &>(char const *,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &)
0x1800f3f22  nop
0x1800f3f23  xor     edx, edx
0x1800f3f25  lea     rcx, [rbp+160h+var_1A0]
0x1800f3f29  call    ?CreateOrExtendCorrelationVector@CorrelationVectorData@cdp@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::CorrelationVectorData::CreateOrExtendCorrelationVector(char const *)
0x1800f3f2e  nop
0x1800f3f2f  mov     rdx, rax
0x1800f3f32  lea     rcx, [rbp+160h+var_180]
0x1800f3f36  call    ??0CorrelationVectorData@cdp@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::CorrelationVectorData::CorrelationVectorData(std::string const &)
0x1800f3f3b  nop
0x1800f3f3c  lea     rcx, [rbp+160h+var_1A0]; void *
0x1800f3f40  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800f3f45  lea     rdx, qword_1803986E0
0x1800f3f4c  lea     rcx, [rsp+260h+hstringHeader]
0x1800f3f51  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800f3f56  nop
0x1800f3f57  lea     rdx, ?CdsActivityPolicyBlockedByConsent@MetricsIdentifier@shared@@2QBDB; "CdsActivityPolicy.ActivityBlockedByCons"...
0x1800f3f5e  lea     rcx, [rbp+160h+var_1E0]
0x1800f3f62  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800f3f67  nop
0x1800f3f68  lea     rax, [rsp+260h+hstringHeader]
0x1800f3f6d  mov     [rsp+260h+var_240], rax
0x1800f3f72  lea     r9, [rbp+160h+var_180]
0x1800f3f76  lea     r8, [rbp+160h+var_1C0]
0x1800f3f7a  lea     rdx, [rbp+160h+var_1E0]
0x1800f3f7e  call    ?SendActivityPolicyTelemetry@ActivityPolicies@shared@@AEBAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0AEBUCorrelationVectorData@cdp@@0@Z; shared::ActivityPolicies::SendActivityPolicyTelemetry(std::string const &,std::string const &,cdp::CorrelationVectorData const &,std::string const &)
0x1800f3f83  nop
0x1800f3f84  lea     rcx, [rbp+160h+var_1E0]; void *
0x1800f3f88  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800f3f8d  nop
0x1800f3f8e  lea     rcx, [rsp+260h+hstringHeader]; void *
0x1800f3f93  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800f3f98  nop
0x1800f3f99  lea     rcx, [rbp+160h+var_180]; this
0x1800f3f9d  call    ??1CorrelationVectorData@cdp@@QEAA@XZ; cdp::CorrelationVectorData::~CorrelationVectorData(void)
0x1800f3fa2  nop
0x1800f3fa3  lea     rcx, [rbp+160h+var_1C0]; void *
0x1800f3fa7  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800f3fac  nop
0x1800f3fad  lea     rcx, [rsp+260h+var_228]
0x1800f3fb2  call    ?InternalRelease@?$ComPtr@UIUnifiedConsentCoordinatorFactory@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(void)
0x1800f3fb7  jmp     short loc_1800F3FC5
0x1800f3fb9  lea     rcx, [rsp+260h+var_228]
0x1800f3fbe  call    ?InternalRelease@?$ComPtr@UIUnifiedConsentCoordinatorFactory@ConsentUx@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinatorFactory>::InternalRelease(void)
0x1800f3fc3  xor     bl, bl
0x1800f3fc5  mov     rcx, rdi; _Mtx_t
0x1800f3fc8  call    cs:__imp__Mtx_unlock
0x1800f3fce  mov     al, bl
0x1800f3fd0  mov     rcx, [rbp+160h+var_20]
0x1800f3fd7  xor     rcx, rsp; StackCookie
0x1800f3fda  call    __security_check_cookie
0x1800f3fdf  lea     r11, [rsp+260h+var_10]
0x1800f3fe7  mov     rbx, [r11+28h]
0x1800f3feb  mov     rsi, [r11+30h]
0x1800f3fef  mov     rsp, r11
0x1800f3ff2  pop     r14
0x1800f3ff4  pop     rdi
0x1800f3ff5  pop     rbp
0x1800f3ff6  retn
```
