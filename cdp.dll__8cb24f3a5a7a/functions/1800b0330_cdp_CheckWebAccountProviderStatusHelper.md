# cdp::CheckWebAccountProviderStatusHelper

- ea: `0x1800b0330`
- end: `0x1800b06b8`
- name: `cdp::CheckWebAccountProviderStatusHelper`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18018e38c`

## callees

- `0x1800113bc`
- `0x1800117f8`
- `0x18001ce80`
- `0x180030190`
- `0x1800a5aa8`
- `0x1800a6ff8`
- `0x1800b0330`
- `0x1800b06c0`
- `0x1800d9ff4`
- `0x18012d5cc`
- `0x1801f6fb0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b0396`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b0396`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b0380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b0380`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b03b8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b03b8`

## string_xrefs

- `0x1800b0379`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x1800b03d5`: `.\userserviceinitializer.cpp`
- `0x1800b0471`: `.\userserviceinitializer.cpp`
- `0x1800b05bc`: `.\userserviceinitializer.cpp`
- `0x1800b0603`: `.\userserviceinitializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall cdp::CheckWebAccountProviderStatusHelper(unsigned __int16 a1)
{
  HRESULT StringReference; // eax
  __int64 v3; // rbx
  int ActivationFactory; // eax
  int v5; // ecx
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v8; // rbx
  __int64 v9; // rax
  int v10; // eax
  int v11; // ecx
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  int v16; // ebx
  const char *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // ebx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // [rsp+30h] [rbp-29h] BYREF
  __int64 v24; // [rsp+38h] [rbp-21h] BYREF
  __int64 v25; // [rsp+40h] [rbp-19h] BYREF
  __int64 v26; // [rsp+48h] [rbp-11h] BYREF
  __int64 v27; // [rsp+50h] [rbp-9h] BYREF
  __int128 hstringHeader; // [rsp+58h] [rbp-1h] BYREF
  __m128i hstringHeader_16; // [rsp+68h] [rbp+Fh] BYREF
  _BYTE v30[32]; // [rsp+78h] [rbp+1Fh] BYREF

  v26 = 0;
  hstringHeader_16.m128i_i64[1] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
                      0x45u,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16.m128i_i64[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  v3 = hstringHeader_16.m128i_i64[1];
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v26);
  if ( ActivationFactory < 0 )
  {
    v23 = ActivationFactory;
    LODWORD(v24) = 790;
    Log<long &,char const (&)[36],int>(
      v5,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v23,
      (unsigned int)".\\userserviceinitializer.cpp",
      (__int64)&v24);
LABEL_18:
    v19 = v23;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
    return v19;
  }
  v25 = 0;
  if ( a1 == 1 )
  {
    v6 = v26;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v26 + 96LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    v8 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_18037AEB0) + 24);
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v30, &off_18037AEB8);
    v10 = v7(v6, *(_QWORD *)(v9 + 24), v8, &v25);
    if ( v10 < 0 )
    {
      LODWORD(v24) = 796;
LABEL_8:
      v23 = v10;
      Log<long &,char const (&)[36],int>(
        v11,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
        (unsigned int)&v23,
        (unsigned int)".\\userserviceinitializer.cpp",
        (__int64)&v24);
LABEL_17:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
      goto LABEL_18;
    }
  }
  else if ( a1 == 2 )
  {
    v12 = v26;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v26 + 96LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    v14 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v30, off_18037AEA8) + 24);
    v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &off_18037AEB8);
    v10 = v13(v12, *(_QWORD *)(v15 + 24), v14, &v25);
    if ( v10 < 0 )
    {
      LODWORD(v24) = 801;
      goto LABEL_8;
    }
  }
  v27 = 0;
  v24 = 10000;
  hstringHeader = 0;
  hstringHeader_16 = 0;
  *(_QWORD *)&hstringHeader = std::allocator<char>::allocate(&hstringHeader, 96);
  hstringHeader_16 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)hstringHeader, "long __cdecl cdp::CheckWebAccountProviderStatusHelper(enum CDPAccountType) noexcept");
  v16 = shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>,Windows::Security::Credentials::IWebAccountProvider>(
          v25,
          &hstringHeader,
          &v24,
          &v27);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&hstringHeader);
  if ( v16 < 0 )
  {
    v17 = (const char *)EnumMapper::ToString(a1);
    cdp::detail::StringFormat(&hstringHeader, "FindAccountProviderWithAuthorityAsync failed for %s", v17);
    shared::AggregatedTelemetryLogger::Log((unsigned int)v16, &hstringHeader, ".\\userserviceinitializer.cpp", 807);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&hstringHeader);
    v23 = v16;
    LODWORD(v24) = 808;
LABEL_16:
    Log<long &,char const (&)[36],int>(
      v18,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v23,
      (unsigned int)".\\userserviceinitializer.cpp",
      (__int64)&v24);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
    goto LABEL_17;
  }
  v18 = v27;
  if ( !v27 )
  {
    v23 = -2147023692;
    LODWORD(v24) = 809;
    goto LABEL_16;
  }
  v27 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v21 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b0330  mov     [rsp-8+arg_8], rbx
0x1800b0335  mov     [rsp-8+arg_10], rsi
0x1800b033a  push    rbp
0x1800b033b  push    rdi
0x1800b033c  push    r14
0x1800b033e  lea     rbp, [rsp-47h]
0x1800b0343  sub     rsp, 0A0h
0x1800b034a  mov     rax, cs:__security_cookie
0x1800b0351  xor     rax, rsp
0x1800b0354  mov     [rbp+57h+var_18], rax
0x1800b0358  movzx   r14d, cx
0x1800b035c  mov     [rbp+57h+var_68], 0
0x1800b0364  mov     [rbp+57h+string], 0
0x1800b036c  lea     r9, [rbp+57h+string]; string
0x1800b0370  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800b0374  mov     edx, 45h ; 'E'; length
0x1800b0379  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800b0380  call    cs:__imp_WindowsCreateStringReference
0x1800b0386  test    eax, eax
0x1800b0388  jns     short loc_1800B039D
0x1800b038a  xor     r9d, r9d; lpArguments
0x1800b038d  xor     r8d, r8d; nNumberOfArguments
0x1800b0390  lea     edx, [r9+1]; dwExceptionFlags
0x1800b0394  mov     ecx, eax; dwExceptionCode
0x1800b0396  call    cs:__imp_RaiseException
0x1800b039c  int     3; Trap to Debugger
0x1800b039d  mov     rbx, [rbp+57h+string]
0x1800b03a1  lea     rcx, [rbp+57h+var_68]
0x1800b03a5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b03aa  lea     r8, [rbp+57h+var_68]
0x1800b03ae  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x1800b03b5  mov     rcx, rbx
0x1800b03b8  call    cs:__imp_RoGetActivationFactory
0x1800b03be  test    eax, eax
0x1800b03c0  jns     short loc_1800B03F1
0x1800b03c2  mov     [rbp+57h+var_80], eax
0x1800b03c5  mov     dword ptr [rbp+57h+var_78], 316h
0x1800b03cc  lea     rax, [rbp+57h+var_78]
0x1800b03d0  mov     [rsp+0B0h+var_90], rax
0x1800b03d5  lea     r9, aUserserviceini; ".\\userserviceinitializer.cpp"
0x1800b03dc  lea     r8, [rbp+57h+var_80]
0x1800b03e0  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800b03e7  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800b03ec  jmp     loc_1800B062C
0x1800b03f1  mov     [rbp+57h+var_70], 0
0x1800b03f9  mov     ecx, 1
0x1800b03fe  cmp     r14w, cx
0x1800b0402  jnz     loc_1800B048D
0x1800b0408  mov     rsi, [rbp+57h+var_68]
0x1800b040c  mov     rax, [rsi]
0x1800b040f  mov     rdi, [rax+60h]
0x1800b0413  lea     rcx, [rbp+57h+var_70]
0x1800b0417  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b041c  lea     rdx, off_18037AEB0; "consumers"
0x1800b0423  lea     rcx, [rbp+57h+hstringHeader]
0x1800b0427  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b042c  mov     rbx, [rax+18h]
0x1800b0430  lea     rdx, off_18037AEB8; "https://login.microsoft.com"
0x1800b0437  lea     rcx, [rbp+57h+var_38]
0x1800b043b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b0440  lea     r9, [rbp+57h+var_70]
0x1800b0444  mov     r8, rbx
0x1800b0447  mov     rdx, [rax+18h]
0x1800b044b  mov     rcx, rsi
0x1800b044e  mov     rax, rdi
0x1800b0451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0456  test    eax, eax
0x1800b0458  jns     loc_1800B04F2
0x1800b045e  mov     dword ptr [rbp+57h+var_78], 31Ch
0x1800b0465  mov     [rbp+57h+var_80], eax
0x1800b0468  lea     rax, [rbp+57h+var_78]
0x1800b046c  mov     [rsp+0B0h+var_90], rax
0x1800b0471  lea     r9, aUserserviceini; ".\\userserviceinitializer.cpp"
0x1800b0478  lea     r8, [rbp+57h+var_80]
0x1800b047c  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800b0483  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800b0488  jmp     loc_1800B0623
0x1800b048d  cmp     r14w, 2
0x1800b0492  jnz     short loc_1800B04F2
0x1800b0494  mov     rsi, [rbp+57h+var_68]
0x1800b0498  mov     rax, [rsi]
0x1800b049b  mov     rdi, [rax+60h]
0x1800b049f  lea     rcx, [rbp+57h+var_70]
0x1800b04a3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b04a8  lea     rdx, off_18037AEA8; "organizations"
0x1800b04af  lea     rcx, [rbp+57h+var_38]
0x1800b04b3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b04b8  mov     rbx, [rax+18h]
0x1800b04bc  lea     rdx, off_18037AEB8; "https://login.microsoft.com"
0x1800b04c3  lea     rcx, [rbp+57h+hstringHeader]
0x1800b04c7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b04cc  lea     r9, [rbp+57h+var_70]
0x1800b04d0  mov     r8, rbx
0x1800b04d3  mov     rdx, [rax+18h]
0x1800b04d7  mov     rcx, rsi
0x1800b04da  mov     rax, rdi
0x1800b04dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b04e2  test    eax, eax
0x1800b04e4  jns     short loc_1800B04F2
0x1800b04e6  mov     dword ptr [rbp+57h+var_78], 321h
0x1800b04ed  jmp     loc_1800B0465
0x1800b04f2  mov     [rbp+57h+var_60], 0
0x1800b04fa  mov     [rbp+57h+var_78], 2710h
0x1800b0502  xorps   xmm0, xmm0
0x1800b0505  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1800b0509  xorps   xmm1, xmm1
0x1800b050c  movdqu  xmmword ptr [rbp+0Fh], xmm1
0x1800b0511  mov     edx, 60h ; '`'
0x1800b0516  lea     rcx, [rbp+57h+hstringHeader]
0x1800b051a  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x1800b051f  mov     rdx, rax
0x1800b0522  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800b0526  movdqa  xmm0, cs:__xmm@000000000000005f0000000000000053
0x1800b052e  movdqu  xmmword ptr [rbp+0Fh], xmm0
0x1800b0533  movaps  xmm0, xmmword ptr cs:aLongCdeclCdpCh; "long __cdecl cdp::CheckWebAccountProvid"...
0x1800b053a  movups  xmmword ptr [rax], xmm0
0x1800b053d  movaps  xmm1, xmmword ptr cs:aLongCdeclCdpCh+10h; "::CheckWebAccountProviderStatusHelper(e"...
0x1800b0544  movups  xmmword ptr [rax+10h], xmm1
0x1800b0548  movaps  xmm0, xmmword ptr cs:aLongCdeclCdpCh+20h; "tProviderStatusHelper(enum CDPAccountTy"...
0x1800b054f  movups  xmmword ptr [rax+20h], xmm0
0x1800b0553  movaps  xmm1, xmmword ptr cs:aLongCdeclCdpCh+30h; "elper(enum CDPAccountType) noexcept"
0x1800b055a  movups  xmmword ptr [rax+30h], xmm1
0x1800b055e  movaps  xmm0, xmmword ptr cs:aLongCdeclCdpCh+40h; "countType) noexcept"
0x1800b0565  movups  xmmword ptr [rax+40h], xmm0
0x1800b0569  mov     eax, dword ptr cs:aLongCdeclCdpCh+4Fh; "cept"
0x1800b056f  mov     [rdx+4Fh], eax
0x1800b0572  mov     byte ptr [rdx+53h], 0
0x1800b0576  lea     r9, [rbp+57h+var_60]
0x1800b057a  lea     r8, [rbp+57h+var_78]
0x1800b057e  lea     rdx, [rbp+57h+hstringHeader]
0x1800b0582  mov     rcx, [rbp+57h+var_70]
0x1800b0586  call    ??$CancellableBlockingWRLCall@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@UIWebAccountProvider@Credentials@Security@3@@shared@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@5@PEAPEAUIWebAccountProvider@Credentials@Security@3@@Z; shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,std::string const &,std::chrono::duration<__int64,std::ratio<1,1000>> const &,Windows::Security::Credentials::IWebAccountProvider * *)
0x1800b058b  mov     ebx, eax
0x1800b058d  lea     rcx, [rbp+57h+hstringHeader]; void *
0x1800b0591  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800b0596  test    ebx, ebx
0x1800b0598  jns     short loc_1800B05E3
0x1800b059a  movzx   ecx, r14w
0x1800b059e  call    ?ToString@EnumMapper@@YAPEBDW4CDPAccountType@@@Z; EnumMapper::ToString(CDPAccountType)
0x1800b05a3  mov     r8, rax
0x1800b05a6  lea     rdx, aFindaccountpro_0; "FindAccountProviderWithAuthorityAsync f"...
0x1800b05ad  lea     rcx, [rbp+57h+hstringHeader]
0x1800b05b1  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x1800b05b6  mov     r9d, 327h
0x1800b05bc  lea     r8, aUserserviceini; ".\\userserviceinitializer.cpp"
0x1800b05c3  lea     rdx, [rbp+57h+hstringHeader]
0x1800b05c7  mov     ecx, ebx
0x1800b05c9  call    ?Log@AggregatedTelemetryLogger@shared@@SAXJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDI@Z; shared::AggregatedTelemetryLogger::Log(long,std::string const &,char const *,uint)
0x1800b05ce  lea     rcx, [rbp+57h+hstringHeader]; void *
0x1800b05d2  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800b05d7  mov     [rbp+57h+var_80], ebx
0x1800b05da  mov     dword ptr [rbp+57h+var_78], 328h
0x1800b05e1  jmp     short loc_1800B05FA
0x1800b05e3  mov     rcx, [rbp+57h+var_60]
0x1800b05e7  test    rcx, rcx
0x1800b05ea  jnz     short loc_1800B063C
0x1800b05ec  mov     [rbp+57h+var_80], 800704B4h
0x1800b05f3  mov     dword ptr [rbp+57h+var_78], 329h
0x1800b05fa  lea     rax, [rbp+57h+var_78]
0x1800b05fe  mov     [rsp+0B0h+var_90], rax
0x1800b0603  lea     r9, aUserserviceini; ".\\userserviceinitializer.cpp"
0x1800b060a  lea     r8, [rbp+57h+var_80]
0x1800b060e  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800b0615  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800b061a  lea     rcx, [rbp+57h+var_60]
0x1800b061e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b0623  lea     rcx, [rbp+57h+var_70]
0x1800b0627  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b062c  mov     ebx, [rbp+57h+var_80]
0x1800b062f  lea     rcx, [rbp+57h+var_68]
0x1800b0633  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b0638  mov     eax, ebx
0x1800b063a  jmp     short loc_1800B0694
0x1800b063c  test    rcx, rcx
0x1800b063f  jz      short loc_1800B0656
0x1800b0641  mov     [rbp+57h+var_60], 0
0x1800b0649  mov     rax, [rcx]
0x1800b064c  mov     rax, [rax+10h]
0x1800b0650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0655  nop
0x1800b0656  mov     rcx, [rbp+57h+var_70]
0x1800b065a  test    rcx, rcx
0x1800b065d  jz      short loc_1800B0674
0x1800b065f  mov     [rbp+57h+var_70], 0
0x1800b0667  mov     rax, [rcx]
0x1800b066a  mov     rax, [rax+10h]
0x1800b066e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0673  nop
0x1800b0674  mov     rcx, [rbp+57h+var_68]
0x1800b0678  test    rcx, rcx
0x1800b067b  jz      short loc_1800B0692
0x1800b067d  mov     [rbp+57h+var_68], 0
0x1800b0685  mov     rax, [rcx]
0x1800b0688  mov     rax, [rax+10h]
0x1800b068c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0691  nop
0x1800b0692  xor     eax, eax
0x1800b0694  mov     rcx, [rbp+57h+var_18]
0x1800b0698  xor     rcx, rsp; StackCookie
0x1800b069b  call    __security_check_cookie
0x1800b06a0  lea     r11, [rsp+0B0h+var_10]
0x1800b06a8  mov     rbx, [r11+28h]
0x1800b06ac  mov     rsi, [r11+30h]
0x1800b06b0  mov     rsp, r11
0x1800b06b3  pop     r14
0x1800b06b5  pop     rdi
0x1800b06b6  pop     rbp
0x1800b06b7  retn
```
