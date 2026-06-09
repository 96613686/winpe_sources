# shared::OneCoreAccountProvider::OneCoreAccountProvider(void)

- ea: `0x1800af9bc`
- end: `0x1800affca`
- name: `??0OneCoreAccountProvider@shared@@QEAA@XZ`
- size: `1550`
- prototype: `__int64 __fastcall(shared::OneCoreAccountProvider *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18020b2e0`

## callees

- `0x18000d350`
- `0x180010fb4`
- `0x180011058`
- `0x180013da0`
- `0x18001ce80`
- `0x180030190`
- `0x18003e358`
- `0x1800573e8`
- `0x1800624cc`
- `0x1800af9bc`
- `0x1800b0098`
- `0x1800b01c4`
- `0x18011d8c4`
- `0x180129e4c`
- `0x18016bd08`
- `0x18017b6d0`
- `0x1801f6fb0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800afda1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800afe2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800afda1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800afe2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800afd8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800afe15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800afd8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800afe15`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800afdc1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800afe4b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800afdc1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800afe4b`

## string_xrefs

- `0x1800afe0e`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x1800afd84`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
shared::OneCoreAccountProvider *__fastcall shared::OneCoreAccountProvider::OneCoreAccountProvider(
        shared::OneCoreAccountProvider *this)
{
  __int64 v2; // rax
  int v3; // eax
  __int64 v4; // rcx
  const WCHAR *v5; // r8
  __int64 v6; // rdx
  WCHAR *v7; // rax
  WCHAR v8; // r9
  WCHAR *v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  const WCHAR *v12; // r8
  __int64 v13; // rdx
  WCHAR *v14; // rax
  WCHAR v15; // r9
  WCHAR *v16; // rcx
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  std::_Ref_count_base *v20; // rcx
  __m128i si128; // xmm6
  __int64 v22; // r8
  __int64 *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rdx
  std::_Ref_count_base *v26; // rcx
  HRESULT StringReference; // eax
  __int64 v28; // rbx
  int ActivationFactory; // eax
  __int64 v30; // rax
  HRESULT v31; // eax
  __int64 v32; // rbx
  int v33; // eax
  __int64 v34; // rax
  shared::WebAccountCache *v35; // rbx
  std::_Ref_count_base *v36; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // [rsp+30h] [rbp-91h] BYREF
  std::_Ref_count_base *v43; // [rsp+38h] [rbp-89h]
  shared::OneCoreAccountProvider *v44; // [rsp+40h] [rbp-81h]
  _BYTE v45[56]; // [rsp+48h] [rbp-79h] BYREF
  shared::WebAccountCache *hstringHeader[2]; // [rsp+80h] [rbp-41h] BYREF
  _OWORD hstringHeader_16[3]; // [rsp+90h] [rbp-31h] BYREF

  v44 = this;
  *(_QWORD *)this = &cdp::unknown<ICDPAccountProvider,IWebAccountBackedAccountProvider,IAccountProviderInternal>::`vftable'{for `ICDPAccountProvider'};
  *((_QWORD *)this + 1) = &cdp::unknown<ICDPAccountProvider,IWebAccountBackedAccountProvider,IAccountProviderInternal>::`vftable'{for `IWebAccountBackedAccountProvider'};
  *((_QWORD *)this + 2) = &cdp::unknown<ICDPAccountProvider,IWebAccountBackedAccountProvider,IAccountProviderInternal>::`vftable'{for `IAccountProviderInternal'};
  *((_DWORD *)this + 6) = 1;
  std::make_shared<cdp::detail::weak_ref_control_block,>((char *)this + 32);
  *(_QWORD *)this = &shared::OneCoreAccountProvider::`vftable'{for `ICDPAccountProvider'};
  *((_QWORD *)this + 1) = &shared::OneCoreAccountProvider::`vftable'{for `IWebAccountBackedAccountProvider'};
  *((_QWORD *)this + 2) = &shared::OneCoreAccountProvider::`vftable'{for `IAccountProviderInternal'};
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *(_OWORD *)((char *)this + 184) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 50) = -1;
  *((_DWORD *)this + 32) = 2;
  *(_QWORD *)((char *)this + 204) = 0;
  *(_QWORD *)((char *)this + 212) = 0;
  *(_QWORD *)((char *)this + 220) = 0;
  *(_QWORD *)((char *)this + 228) = 0;
  *((_BYTE *)this + 236) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *(_OWORD *)((char *)this + 312) = 0;
  *(_OWORD *)((char *)this + 328) = 0;
  *(_OWORD *)((char *)this + 344) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 90) = -1;
  *((_DWORD *)this + 72) = 2;
  *((_DWORD *)this + 91) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  v2 = std::_Allocate<16,std::_Default_allocate_traits>(88);
  *(_QWORD *)v2 = v2;
  *(_QWORD *)(v2 + 8) = v2;
  *(_QWORD *)(v2 + 16) = v2;
  *(_WORD *)(v2 + 24) = 257;
  *((_QWORD *)this + 46) = v2;
  std::map<std::string,CDP_DATE_TIME>::map<std::string,CDP_DATE_TIME>((char *)this + 384);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
         (char *)this + 240,
         9);
  if ( v3 < 0 )
  {
    hstringHeader[0] = (shared::WebAccountCache *)".\\onecoreaccountprovider.cpp";
    LODWORD(hstringHeader[1]) = 75;
    v41 = cdp::MakeException<cdp::hresult_exception>(v45, hstringHeader, (unsigned int)v3);
    cdp::CdpThrow<cdp::hresult_exception>(hstringHeader, v41);
  }
  v4 = 9;
  v5 = L"consumers";
  v6 = 10;
  v7 = (WCHAR *)*((_QWORD *)this + 30);
  do
  {
    if ( !v4 )
      break;
    v8 = *v5;
    if ( !*v5 )
      break;
    ++v5;
    *v7++ = v8;
    --v4;
    --v6;
  }
  while ( v6 );
  v9 = v7 - 1;
  if ( v6 )
    v9 = v7;
  *v9 = 0;
  *((_QWORD *)this + 31) = 9;
  v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
          (char *)this + 264,
          13);
  if ( v10 < 0 )
  {
    hstringHeader[0] = (shared::WebAccountCache *)".\\onecoreaccountprovider.cpp";
    LODWORD(hstringHeader[1]) = 76;
    v40 = cdp::MakeException<cdp::hresult_exception>(v45, hstringHeader, (unsigned int)v10);
    cdp::CdpThrow<cdp::hresult_exception>(hstringHeader, v40);
  }
  v11 = 13;
  v12 = L"organizations";
  v13 = 14;
  v14 = (WCHAR *)*((_QWORD *)this + 33);
  do
  {
    if ( !v11 )
      break;
    v15 = *v12;
    if ( !*v12 )
      break;
    ++v12;
    *v14++ = v15;
    --v11;
    --v13;
  }
  while ( v13 );
  v16 = v14 - 1;
  if ( v13 )
    v16 = v14;
  *v16 = 0;
  *((_QWORD *)this + 34) = 13;
  shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::ISharedPALFactory>(&v42, v13, v12);
  v17 = (__int64 *)(*(__int64 (__fastcall **)(__int64, shared::WebAccountCache **))(*(_QWORD *)v42 + 80LL))(
                     v42,
                     hstringHeader);
  v18 = *v17;
  v19 = v17[1];
  *v17 = 0;
  v17[1] = 0;
  *((_QWORD *)this + 7) = v18;
  v20 = (std::_Ref_count_base *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v19;
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  if ( hstringHeader[1] )
    std::_Ref_count_base::_Decref(hstringHeader[1]);
  if ( !*((_QWORD *)this + 7) )
  {
    hstringHeader[0] = (shared::WebAccountCache *)".\\onecoreaccountprovider.cpp";
    LODWORD(hstringHeader[1]) = 81;
    v39 = cdp::MakeException<cdp::HResultException<-2147418113>,>(
            v45,
            hstringHeader,
            "Failed to get WorkItemDispatcher");
    cdp::CdpThrow<cdp::HResultException<-2147418113>>(hstringHeader, v39);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  hstringHeader_16[0] = si128;
  strcpy((char *)hstringHeader, "CDP_AccProvider");
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(hstringHeader);
  LOBYTE(v22) = 100;
  v23 = (__int64 *)(*(__int64 (__fastcall **)(__int64, shared::WebAccountCache **, __int64))(*(_QWORD *)v42 + 88LL))(
                     v42,
                     hstringHeader,
                     v22);
  v24 = *v23;
  v25 = v23[1];
  *v23 = 0;
  v23[1] = 0;
  *((_QWORD *)this + 9) = v24;
  v26 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = v25;
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  if ( hstringHeader[1] )
  {
    std::_Ref_count_base::_Decref(hstringHeader[1]);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  if ( !*((_QWORD *)this + 9) )
  {
    hstringHeader[0] = (shared::WebAccountCache *)".\\onecoreaccountprovider.cpp";
    LODWORD(hstringHeader[1]) = 85;
    v38 = cdp::MakeException<cdp::HResultException<-2147418113>,>(
            v45,
            hstringHeader,
            "Failed to get WorkItemDispatcher");
    cdp::CdpThrow<cdp::HResultException<-2147418113>>(hstringHeader, v38);
  }
  hstringHeader_16[0] = si128;
  strcpy((char *)hstringHeader, "CDP_AccProvidTk");
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(hstringHeader);
  *((_QWORD *)&hstringHeader_16[0] + 1) = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
                      0x40u,
                      (HSTRING_HEADER *)hstringHeader,
                      (HSTRING *)hstringHeader_16 + 1);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  v28 = *((_QWORD *)&hstringHeader_16[0] + 1);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 88);
  ActivationFactory = RoGetActivationFactory(v28, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, (char *)this + 88);
  if ( ActivationFactory < 0 )
  {
    hstringHeader[0] = (shared::WebAccountCache *)".\\onecoreaccountprovider.cpp";
    LODWORD(hstringHeader[1]) = 89;
    v30 = cdp::MakeException<cdp::hresult_exception>(v45, hstringHeader, (unsigned int)ActivationFactory);
    cdp::CdpThrow<cdp::hresult_exception>(hstringHeader, v30);
  }
  *((_QWORD *)&hstringHeader_16[0] + 1) = 0;
  v31 = WindowsCreateStringReference(
          L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
          0x45u,
          (HSTRING_HEADER *)hstringHeader,
          (HSTRING *)hstringHeader_16 + 1);
  if ( v31 < 0 )
  {
    RaiseException(v31, 1u, 0, 0);
    __debugbreak();
  }
  v32 = *((_QWORD *)&hstringHeader_16[0] + 1);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 96);
  v33 = RoGetActivationFactory(v32, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, (char *)this + 96);
  if ( v33 < 0 )
  {
    hstringHeader[0] = (shared::WebAccountCache *)".\\onecoreaccountprovider.cpp";
    LODWORD(hstringHeader[1]) = 92;
    v34 = cdp::MakeException<cdp::hresult_exception>(v45, hstringHeader, (unsigned int)v33);
    cdp::CdpThrow<cdp::hresult_exception>(hstringHeader, v34);
  }
  std::make_shared<shared::WebAccountCache,>(hstringHeader);
  v35 = hstringHeader[0];
  shared::WebAccountCache::Initialize(hstringHeader[0]);
  *((_QWORD *)this + 14) = v35;
  v36 = (std::_Ref_count_base *)*((_QWORD *)this + 15);
  *((shared::WebAccountCache **)this + 15) = hstringHeader[1];
  if ( v36 )
    std::_Ref_count_base::_Decref(v36);
  shared::OneCoreAccountProvider::SubscribeToTokenBrokerEvents(this);
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  return this;
}

```

## disassembly

```asm
0x1800af9bc  mov     rax, rsp
0x1800af9bf  push    rbp
0x1800af9c0  push    rbx
0x1800af9c1  push    rsi
0x1800af9c2  push    rdi
0x1800af9c3  push    r12
0x1800af9c5  push    r13
0x1800af9c7  push    r14
0x1800af9c9  push    r15
0x1800af9cb  lea     rbp, [rax-5Fh]
0x1800af9cf  sub     rsp, 0D8h
0x1800af9d6  movaps  xmmword ptr [rax-58h], xmm6
0x1800af9da  mov     rax, cs:__security_cookie
0x1800af9e1  xor     rax, rsp
0x1800af9e4  mov     qword ptr [rbp+57h+var_58], rax
0x1800af9e8  mov     rdi, rcx
0x1800af9eb  mov     [rsp+110h+var_D8], rcx
0x1800af9f0  xor     ebx, ebx
0x1800af9f2  mov     r14d, ebx
0x1800af9f5  mov     dword ptr [rsp+110h+var_F0], ebx
0x1800af9f9  lea     rax, ??_7?$unknown@VICDPAccountProvider@@VIWebAccountBackedAccountProvider@@VIAccountProviderInternal@@@cdp@@6BICDPAccountProvider@@@; const cdp::unknown<ICDPAccountProvider,IWebAccountBackedAccountProvider,IAccountProviderInternal>::`vftable'{for `ICDPAccountProvider'}
0x1800afa00  mov     [rcx], rax
0x1800afa03  lea     rax, ??_7?$unknown@VICDPAccountProvider@@VIWebAccountBackedAccountProvider@@VIAccountProviderInternal@@@cdp@@6BIWebAccountBackedAccountProvider@@@; const cdp::unknown<ICDPAccountProvider,IWebAccountBackedAccountProvider,IAccountProviderInternal>::`vftable'{for `IWebAccountBackedAccountProvider'}
0x1800afa0a  mov     [rcx+8], rax
0x1800afa0e  lea     rax, ??_7?$unknown@VICDPAccountProvider@@VIWebAccountBackedAccountProvider@@VIAccountProviderInternal@@@cdp@@6BIAccountProviderInternal@@@; const cdp::unknown<ICDPAccountProvider,IWebAccountBackedAccountProvider,IAccountProviderInternal>::`vftable'{for `IAccountProviderInternal'}
0x1800afa15  mov     [rcx+10h], rax
0x1800afa19  mov     dword ptr [rcx+18h], 1
0x1800afa20  add     rcx, 20h ; ' '
0x1800afa24  call    ??$make_shared@Uweak_ref_control_block@detail@cdp@@$$V@std@@YA?AV?$shared_ptr@Uweak_ref_control_block@detail@cdp@@@0@XZ; std::make_shared<cdp::detail::weak_ref_control_block,>(void)
0x1800afa29  nop
0x1800afa2a  lea     rax, ??_7OneCoreAccountProvider@shared@@6BICDPAccountProvider@@@; const shared::OneCoreAccountProvider::`vftable'{for `ICDPAccountProvider'}
0x1800afa31  mov     [rdi], rax
0x1800afa34  lea     rax, ??_7OneCoreAccountProvider@shared@@6BIWebAccountBackedAccountProvider@@@; const shared::OneCoreAccountProvider::`vftable'{for `IWebAccountBackedAccountProvider'}
0x1800afa3b  mov     [rdi+8], rax
0x1800afa3f  lea     rax, ??_7OneCoreAccountProvider@shared@@6BIAccountProviderInternal@@@; const shared::OneCoreAccountProvider::`vftable'{for `IAccountProviderInternal'}
0x1800afa46  mov     [rdi+10h], rax
0x1800afa4a  mov     [rdi+30h], ebx
0x1800afa4d  mov     [rdi+38h], rbx
0x1800afa51  mov     [rdi+40h], rbx
0x1800afa55  mov     [rdi+48h], rbx
0x1800afa59  mov     [rdi+50h], rbx
0x1800afa5d  lea     r13, [rdi+58h]
0x1800afa61  mov     [r13+0], rbx
0x1800afa65  lea     r12, [rdi+60h]
0x1800afa69  mov     [r12], rbx
0x1800afa6d  mov     [rdi+68h], rbx
0x1800afa71  mov     [rdi+70h], rbx
0x1800afa75  mov     [rdi+78h], rbx
0x1800afa79  xorps   xmm0, xmm0
0x1800afa7c  movups  xmmword ptr [rdi+98h], xmm0
0x1800afa83  movups  xmmword ptr [rdi+0A8h], xmm0
0x1800afa8a  movups  xmmword ptr [rdi+0B8h], xmm0
0x1800afa91  mov     [rdi+88h], rbx
0x1800afa98  mov     [rdi+90h], rbx
0x1800afa9f  or      eax, 0FFFFFFFFh
0x1800afaa2  mov     [rdi+0C8h], eax
0x1800afaa8  mov     dword ptr [rdi+80h], 2
0x1800afab2  mov     [rdi+0CCh], rbx
0x1800afab9  mov     [rdi+0D4h], rbx
0x1800afac0  mov     [rdi+0DCh], rbx
0x1800afac7  mov     [rdi+0E4h], rbx
0x1800aface  mov     [rdi+0ECh], bl
0x1800afad4  lea     r15, [rdi+0F0h]
0x1800afadb  mov     [r15], rbx
0x1800afade  mov     [r15+8], rbx
0x1800afae2  mov     [r15+10h], rbx
0x1800afae6  lea     rsi, [rdi+108h]
0x1800afaed  mov     [rsi], rbx
0x1800afaf0  mov     [rsi+8], rbx
0x1800afaf4  mov     [rsi+10h], rbx
0x1800afaf8  movups  xmmword ptr [rdi+138h], xmm0
0x1800afaff  movups  xmmword ptr [rdi+148h], xmm0
0x1800afb06  movups  xmmword ptr [rdi+158h], xmm0
0x1800afb0d  mov     [rdi+128h], rbx
0x1800afb14  mov     [rdi+130h], rbx
0x1800afb1b  mov     [rdi+168h], eax
0x1800afb21  mov     dword ptr [rdi+120h], 2
0x1800afb2b  mov     [rdi+16Ch], ebx
0x1800afb31  lea     rbx, [rdi+170h]
0x1800afb38  mov     qword ptr [rbx], 0
0x1800afb3f  mov     qword ptr [rbx+8], 0
0x1800afb47  lea     ecx, [rax+59h]
0x1800afb4a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800afb4f  mov     [rax], rax
0x1800afb52  mov     [rax+8], rax
0x1800afb56  mov     [rax+10h], rax
0x1800afb5a  mov     word ptr [rax+18h], 101h
0x1800afb60  mov     [rbx], rax
0x1800afb63  lea     rcx, [rdi+180h]
0x1800afb6a  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UCDP_DATE_TIME@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UCDP_DATE_TIME@@@std@@@2@@std@@QEAA@XZ; std::map<std::string,CDP_DATE_TIME>::map<std::string,CDP_DATE_TIME>(void)
0x1800afb6f  nop
0x1800afb70  mov     edx, 9
0x1800afb75  mov     rcx, r15
0x1800afb78  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800afb7d  xor     ebx, ebx
0x1800afb7f  test    eax, eax
0x1800afb81  js      loc_1800AFF9A
0x1800afb87  lea     r10d, [rbx+9]
0x1800afb8b  mov     ecx, r10d
0x1800afb8e  lea     r8, aConsumers; "consumers"
0x1800afb95  lea     edx, [rbx+0Ah]
0x1800afb98  mov     rax, [r15]
0x1800afb9b  test    rcx, rcx
0x1800afb9e  jz      short loc_1800AFBBF
0x1800afba0  movzx   r9d, word ptr [r8]
0x1800afba4  test    r9w, r9w
0x1800afba8  jz      short loc_1800AFBBF
0x1800afbaa  add     r8, 2
0x1800afbae  mov     [rax], r9w
0x1800afbb2  add     rax, 2
0x1800afbb6  dec     rcx
0x1800afbb9  sub     rdx, 1
0x1800afbbd  jnz     short loc_1800AFB9B
0x1800afbbf  lea     rcx, [rax-2]
0x1800afbc3  test    rdx, rdx
0x1800afbc6  cmovnz  rcx, rax
0x1800afbca  mov     [rcx], bx
0x1800afbcd  mov     [r15+8], r10
0x1800afbd1  mov     r15d, 0Dh
0x1800afbd7  mov     edx, r15d
0x1800afbda  mov     rcx, rsi
0x1800afbdd  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800afbe2  test    eax, eax
0x1800afbe4  js      loc_1800AFF6A
0x1800afbea  mov     ecx, r15d
0x1800afbed  lea     r8, aOrganizations; "organizations"
0x1800afbf4  lea     edx, [r15+1]
0x1800afbf8  mov     rax, [rsi]
0x1800afbfb  test    rcx, rcx
0x1800afbfe  jz      short loc_1800AFC1F
0x1800afc00  movzx   r9d, word ptr [r8]
0x1800afc04  test    r9w, r9w
0x1800afc08  jz      short loc_1800AFC1F
0x1800afc0a  add     r8, 2
0x1800afc0e  mov     [rax], r9w
0x1800afc12  add     rax, 2
0x1800afc16  dec     rcx
0x1800afc19  sub     rdx, 1
0x1800afc1d  jnz     short loc_1800AFBFB
0x1800afc1f  lea     rcx, [rax-2]
0x1800afc23  test    rdx, rdx
0x1800afc26  cmovnz  rcx, rax
0x1800afc2a  mov     [rcx], bx
0x1800afc2d  mov     [rsi+8], r15
0x1800afc31  lea     rcx, [rsp+110h+var_E8]
0x1800afc36  call    ??$GetInstanceThrowIfNull@VISharedPALFactory@shared@@@SharedInstanceManager@shared@@SA?AV?$shared_ptr@VISharedPALFactory@shared@@@std@@H@Z; shared::SharedInstanceManager::GetInstanceThrowIfNull<shared::ISharedPALFactory>(int)
0x1800afc3b  nop
0x1800afc3c  mov     rcx, [rsp+110h+var_E8]
0x1800afc41  mov     rax, [rcx]
0x1800afc44  lea     rdx, [rbp+57h+hstringHeader]
0x1800afc48  mov     rax, [rax+50h]
0x1800afc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afc51  mov     rcx, rax
0x1800afc54  mov     rax, [rax]
0x1800afc57  mov     rdx, [rcx+8]
0x1800afc5b  mov     [rcx], rbx
0x1800afc5e  mov     [rcx+8], rbx
0x1800afc62  mov     [rdi+38h], rax
0x1800afc66  mov     rcx, [rdi+40h]; this
0x1800afc6a  mov     [rdi+40h], rdx
0x1800afc6e  test    rcx, rcx
0x1800afc71  jz      short loc_1800AFC78
0x1800afc73  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800afc78  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+8]; this
0x1800afc7c  test    rcx, rcx
0x1800afc7f  jz      short loc_1800AFC86
0x1800afc81  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800afc86  cmp     [rdi+38h], rbx
0x1800afc8a  jz      loc_1800AFF36
0x1800afc90  xorps   xmm0, xmm0
0x1800afc93  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1800afc97  movdqa  xmm6, cs:__xmm@000000000000000f000000000000000f
0x1800afc9f  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved+10h], xmm6
0x1800afca4  mov     rsi, 506363415F504443h
0x1800afcae  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rsi
0x1800afcb2  mov     eax, cs:dword_1803A5FD8
0x1800afcb8  mov     dword ptr [rbp+57h+hstringHeader.Reserved+8], eax
0x1800afcbb  movzx   eax, cs:word_1803A5FDC
0x1800afcc2  mov     word ptr [rbp+57h+hstringHeader.Reserved+0Ch], ax
0x1800afcc6  mov     al, cs:byte_1803A5FDE
0x1800afccc  mov     byte ptr [rbp+57h+hstringHeader.Reserved+0Eh], al
0x1800afccf  mov     byte ptr [rbp+57h+hstringHeader.Reserved+0Fh], bl
0x1800afcd2  lea     rcx, [rbp+57h+hstringHeader]; void *
0x1800afcd6  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800afcdb  mov     rcx, [rsp+110h+var_E8]
0x1800afce0  mov     rax, [rcx]
0x1800afce3  mov     r8b, 64h ; 'd'
0x1800afce6  lea     rdx, [rbp+57h+hstringHeader]
0x1800afcea  mov     rax, [rax+58h]
0x1800afcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afcf3  mov     rcx, rax
0x1800afcf6  mov     rax, [rax]
0x1800afcf9  mov     rdx, [rcx+8]
0x1800afcfd  mov     [rcx], rbx
0x1800afd00  mov     [rcx+8], rbx
0x1800afd04  mov     [rdi+48h], rax
0x1800afd08  mov     rcx, [rdi+50h]; this
0x1800afd0c  mov     [rdi+50h], rdx
0x1800afd10  test    rcx, rcx
0x1800afd13  jz      short loc_1800AFD1A
0x1800afd15  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800afd1a  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+8]; this
0x1800afd1e  test    rcx, rcx
0x1800afd21  jz      short loc_1800AFD30
0x1800afd23  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800afd28  movdqa  xmm6, cs:__xmm@000000000000000f000000000000000f
0x1800afd30  cmp     [rdi+48h], rbx
0x1800afd34  jz      loc_1800AFF02
0x1800afd3a  xorps   xmm0, xmm0
0x1800afd3d  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1800afd41  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved+10h], xmm6
0x1800afd46  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rsi
0x1800afd4a  mov     eax, cs:dword_1803A5FC8
0x1800afd50  mov     dword ptr [rbp+57h+hstringHeader.Reserved+8], eax
0x1800afd53  movzx   eax, cs:word_1803A5FCC
0x1800afd5a  mov     word ptr [rbp+57h+hstringHeader.Reserved+0Ch], ax
0x1800afd5e  mov     al, cs:byte_1803A5FCE
0x1800afd64  mov     byte ptr [rbp+57h+hstringHeader.Reserved+0Eh], al
0x1800afd67  mov     byte ptr [rbp+57h+hstringHeader.Reserved+0Fh], bl
0x1800afd6a  lea     rcx, [rbp+57h+hstringHeader]; void *
0x1800afd6e  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800afd73  mov     [rbp+57h+string], rbx
0x1800afd77  lea     r9, [rbp+57h+string]; string
0x1800afd7b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800afd7f  mov     edx, 40h ; '@'; length
0x1800afd84  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x1800afd8b  call    cs:__imp_WindowsCreateStringReference
0x1800afd91  test    eax, eax
0x1800afd93  jns     short loc_1800AFDA8
0x1800afd95  xor     r9d, r9d; lpArguments
0x1800afd98  xor     r8d, r8d; nNumberOfArguments
0x1800afd9b  lea     edx, [r9+1]; dwExceptionFlags
0x1800afd9f  mov     ecx, eax; dwExceptionCode
0x1800afda1  call    cs:__imp_RaiseException
0x1800afda7  int     3; Trap to Debugger
0x1800afda8  mov     rbx, [rbp+57h+string]
0x1800afdac  mov     rcx, r13
0x1800afdaf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800afdb4  mov     r8, r13
0x1800afdb7  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x1800afdbe  mov     rcx, rbx
0x1800afdc1  call    cs:__imp_RoGetActivationFactory
0x1800afdc7  xor     esi, esi
0x1800afdc9  test    eax, eax
0x1800afdcb  jns     short loc_1800AFDFD
0x1800afdcd  lea     rcx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x1800afdd4  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rcx
0x1800afdd8  mov     dword ptr [rbp+57h+hstringHeader.Reserved+8], 59h ; 'Y'
0x1800afddf  mov     r8d, eax
0x1800afde2  lea     rdx, [rbp+57h+hstringHeader]
0x1800afde6  lea     rcx, [rbp+57h+var_D0]
0x1800afdea  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800afdef  nop
0x1800afdf0  mov     rdx, rax
0x1800afdf3  lea     rcx, [rbp+57h+hstringHeader]
0x1800afdf7  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800afdfd  mov     [rbp+57h+string], rsi
0x1800afe01  lea     r9, [rbp+57h+string]; string
0x1800afe05  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800afe09  mov     edx, 45h ; 'E'; length
0x1800afe0e  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800afe15  call    cs:__imp_WindowsCreateStringReference
0x1800afe1b  test    eax, eax
0x1800afe1d  jns     short loc_1800AFE32
0x1800afe1f  xor     r9d, r9d; lpArguments
0x1800afe22  xor     r8d, r8d; nNumberOfArguments
0x1800afe25  lea     edx, [r9+1]; dwExceptionFlags
0x1800afe29  mov     ecx, eax; dwExceptionCode
0x1800afe2b  call    cs:__imp_RaiseException
0x1800afe31  int     3; Trap to Debugger
0x1800afe32  mov     rbx, [rbp+57h+string]
0x1800afe36  mov     rcx, r12
0x1800afe39  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800afe3e  mov     r8, r12
0x1800afe41  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x1800afe48  mov     rcx, rbx
0x1800afe4b  call    cs:__imp_RoGetActivationFactory
0x1800afe51  test    eax, eax
0x1800afe53  jns     short loc_1800AFE85
0x1800afe55  lea     rcx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x1800afe5c  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rcx
0x1800afe60  mov     dword ptr [rbp+57h+hstringHeader.Reserved+8], 5Ch ; '\'
0x1800afe67  mov     r8d, eax
0x1800afe6a  lea     rdx, [rbp+57h+hstringHeader]
0x1800afe6e  lea     rcx, [rbp+57h+var_D0]
0x1800afe72  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800afe77  nop
0x1800afe78  mov     rdx, rax
0x1800afe7b  lea     rcx, [rbp+57h+hstringHeader]
0x1800afe7f  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800afe85  lea     rcx, [rbp+57h+hstringHeader]
0x1800afe89  call    ??$make_shared@VWebAccountCache@shared@@$$V@std@@YA?AV?$shared_ptr@VWebAccountCache@shared@@@0@XZ; std::make_shared<shared::WebAccountCache,>(void)
0x1800afe8e  or      r14d, 7
0x1800afe92  mov     dword ptr [rsp+110h+var_F0], r14d
0x1800afe97  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1800afe9b  mov     rcx, rbx; this
0x1800afe9e  call    ?Initialize@WebAccountCache@shared@@QEAAXXZ; shared::WebAccountCache::Initialize(void)
0x1800afea3  mov     [rdi+70h], rbx
0x1800afea7  mov     rcx, [rdi+78h]; this
0x1800afeab  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+8]
  ... truncated ...
```
