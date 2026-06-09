# shared::OneCoreAccountProvider::GetDefaultSignInAccount(void)

- ea: `0x18009cdb4`
- end: `0x18009d1cc`
- name: `?GetDefaultSignInAccount@OneCoreAccountProvider@shared@@AEAA?AV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@XZ`
- size: `1048`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1800218c4`

## callees

- `0x18000b724`
- `0x18000d098`
- `0x180010fb4`
- `0x180011058`
- `0x1800117f8`
- `0x18001ce80`
- `0x180030190`
- `0x18005ade0`
- `0x1800624cc`
- `0x18009c468`
- `0x18009c514`
- `0x18009c5b4`
- `0x18009cdb4`
- `0x18009dd54`
- `0x18009ded4`
- `0x18009e080`
- `0x1800af2a4`
- `0x1801074c4`
- `0x18011d8c4`
- `0x1801f6fb0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d0c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d0c3`

## string_xrefs

- `0x18009cee3`: `class Microsoft::WRL::ComPtr<struct Windows::Security::Credentials::IWebAccount> __cdecl shared::OneCoreAccountProvider::GetDefaultSignInAccount(void)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 *__fastcall shared::OneCoreAccountProvider::GetDefaultSignInAccount(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // ebx
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // r14d
  __int64 (__fastcall *v14)(__int64, __int64 *); // rdi
  int v15; // eax
  __int64 v16; // rax
  __int16 AccountProviderType; // r15
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v21; // rax
  const WCHAR *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v27; // [rsp+24h] [rbp-DCh]
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v30[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v31[32]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v32; // [rsp+68h] [rbp-98h] BYREF
  __m128i si128; // [rsp+78h] [rbp-88h]
  _BYTE v34[56]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v35[42]; // [rsp+C0h] [rbp-40h] BYREF

  v30[1] = a2;
  v27 = 0;
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v35,
    "GetDefaultSignInAccountActivity",
    a3);
  v35[0] = &OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity::`vftable';
  OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity::StartActivity((OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity *)v35);
  v29 = 0;
  v5 = *(_QWORD *)(a1 + 88);
  v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 232LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
  v7 = v6(v5, &v29);
  v26 = v7;
  OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity::GetDefaultSignInAccountAsync<long &,unsigned short const (&)[1]>(
    v35,
    &v26);
  if ( v7 < 0 )
  {
    *(_QWORD *)&v32 = ".\\onecoreaccountprovider.cpp";
    DWORD2(v32) = 1275;
    v8 = cdp::MakeException<cdp::hresult_exception>(v34, &v32, (unsigned int)v7);
    cdp::CdpThrow<cdp::hresult_exception>(&v32, v8);
  }
  v30[0] = 0;
  string = (HSTRING)30000;
  v32 = 0;
  si128 = 0;
  *(_QWORD *)&v32 = std::allocator<char>::allocate(&v32, 160);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy(
    (char *)v32,
    "class Microsoft::WRL::ComPtr<struct Windows::Security::Credentials::IWebAccount> __cdecl shared::OneCoreAccountProvi"
    "der::GetDefaultSignInAccount(void)");
  v9 = shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(
         v29,
         &v32,
         &string,
         v30);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v32);
  if ( v9 < 0 )
  {
    *(_QWORD *)&v32 = ".\\onecoreaccountprovider.cpp";
    DWORD2(v32) = 1279;
    v10 = cdp::MakeException<cdp::hresult_exception>(v34, &v32, (unsigned int)v9);
    cdp::CdpThrow<cdp::hresult_exception>(&v32, v10);
  }
  v11 = v30[0];
  if ( !v30[0] )
  {
    *(_QWORD *)&v32 = ".\\onecoreaccountprovider.cpp";
    DWORD2(v32) = 1280;
    v12 = cdp::MakeException<cdp::HResultException<-2147418113>,>(
            v34,
            &v32,
            "Unexpected null result from async operation");
    cdp::CdpThrow<cdp::HResultException<-2147418113>>(&v32, v12);
  }
  *a2 = 0;
  v13 = 1;
  v27 = 1;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  v15 = v14(v11, a2);
  if ( v15 < 0 )
  {
    *(_QWORD *)&v32 = ".\\onecoreaccountprovider.cpp";
    DWORD2(v32) = 1283;
    v16 = cdp::MakeException<cdp::hresult_exception>(v34, &v32, (unsigned int)v15);
    cdp::CdpThrow<cdp::hresult_exception>(&v32, v16);
  }
  if ( *a2 )
  {
    AccountProviderType = shared::OneCoreAccountProvider::GetAccountProviderType(a1);
    string = 0;
    v18 = *a2;
    v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a2 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v26 = v19(v18, &string);
    if ( v26 < 0 )
    {
      v22 = &pNodeName;
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v21 = std::wstring::wstring(v31, StringRawBuffer);
      v22 = (const WCHAR *)EncryptString(v34, v21);
      v13 = 3;
      v27 = 3;
      if ( *((_QWORD *)v22 + 3) > 7u )
        v22 = *(const WCHAR **)v22;
    }
    *(_QWORD *)&v32 = v22;
    OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity::GetDefaultSignInAccountAsync<long &,unsigned short const *>(
      v35,
      &v26,
      &v32);
    if ( (v13 & 2) != 0 )
    {
      v27 = v13 & 0xFFFFFFFD;
      std::wstring::_Tidy_deallocate(v34);
    }
    if ( AccountProviderType == 3 )
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
    WindowsDeleteString(string);
  }
  v23 = v30[0];
  if ( v30[0] )
  {
    v30[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v35[0] = &OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity::`vftable';
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v35);
  return a2;
}

```

## disassembly

```asm
0x18009cdb4  mov     [rsp-8+arg_10], rbx
0x18009cdb9  mov     [rsp-8+arg_18], rsi
0x18009cdbe  push    rbp
0x18009cdbf  push    rdi
0x18009cdc0  push    r13
0x18009cdc2  push    r14
0x18009cdc4  push    r15
0x18009cdc6  lea     rbp, [rsp-120h]
0x18009cdce  sub     rsp, 220h
0x18009cdd5  mov     rax, cs:__security_cookie
0x18009cddc  xor     rax, rsp
0x18009cddf  mov     [rbp+140h+var_30], rax
0x18009cde6  mov     rsi, rdx
0x18009cde9  mov     r15, rcx
0x18009cdec  mov     [rsp+240h+var_200], rdx
0x18009cdf1  mov     [rsp+240h+var_21C], 0
0x18009cdf9  lea     rdx, aGetdefaultsign; "GetDefaultSignInAccountActivity"
0x18009ce00  lea     rcx, [rbp+140h+var_180]
0x18009ce04  call    ??0?$ActivityBase@VOneCoreAccountTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009ce09  lea     r13, ??_7GetDefaultSignInAccountActivity@OneCoreAccountTelemetryProvider@@6B@; const OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity::`vftable'
0x18009ce10  mov     [rbp+140h+var_180], r13
0x18009ce14  lea     rcx, [rbp+140h+var_180]; this
0x18009ce18  call    ?StartActivity@GetDefaultSignInAccountActivity@OneCoreAccountTelemetryProvider@@QEAAXXZ; OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity::StartActivity(void)
0x18009ce1d  nop
0x18009ce1e  mov     [rsp+240h+var_210], 0
0x18009ce27  mov     rdi, [r15+58h]
0x18009ce2b  mov     rax, [rdi]
0x18009ce2e  mov     rbx, [rax+0E8h]
0x18009ce35  lea     rcx, [rsp+240h+var_210]
0x18009ce3a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009ce3f  lea     rdx, [rsp+240h+var_210]
0x18009ce44  mov     rcx, rdi
0x18009ce47  mov     rax, rbx
0x18009ce4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ce4f  mov     ebx, eax
0x18009ce51  mov     [rsp+240h+var_220], eax
0x18009ce55  lea     rdx, [rsp+240h+var_220]
0x18009ce5a  lea     rcx, [rbp+140h+var_180]
0x18009ce5e  call    ??$GetDefaultSignInAccountAsync@AEAJAEAY00$$CBG@GetDefaultSignInAccountActivity@OneCoreAccountTelemetryProvider@@QEAAXAEAJAEAY00$$CBG@Z; OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity::GetDefaultSignInAccountAsync<long &,ushort const (&)[1]>(long &,ushort const (&)[1])
0x18009ce63  test    ebx, ebx
0x18009ce65  jns     short loc_18009CE9B
0x18009ce67  lea     rcx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009ce6e  mov     qword ptr [rsp+240h+var_1D8], rcx
0x18009ce73  mov     dword ptr [rsp+240h+var_1D8+8], 4FBh
0x18009ce7b  mov     r8d, ebx
0x18009ce7e  lea     rdx, [rsp+240h+var_1D8]
0x18009ce83  lea     rcx, [rbp+140h+var_1B8]
0x18009ce87  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009ce8c  nop
0x18009ce8d  mov     rdx, rax
0x18009ce90  lea     rcx, [rsp+240h+var_1D8]
0x18009ce95  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009ce9b  mov     [rsp+240h+var_208], 0
0x18009cea4  mov     [rsp+240h+string], 7530h
0x18009cead  xorps   xmm0, xmm0
0x18009ceb0  movups  [rsp+240h+var_1D8], xmm0
0x18009ceb5  xorps   xmm1, xmm1
0x18009ceb8  movdqu  [rsp+240h+var_1C8], xmm1
0x18009cebe  mov     edx, 0A0h
0x18009cec3  lea     rcx, [rsp+240h+var_1D8]
0x18009cec8  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x18009cecd  mov     rcx, rax
0x18009ced0  mov     qword ptr [rsp+240h+var_1D8], rax
0x18009ced5  movdqa  xmm0, cs:__xmm@000000000000009f0000000000000096
0x18009cedd  movdqu  [rsp+240h+var_1C8], xmm0
0x18009cee3  movaps  xmm0, xmmword ptr cs:aClassMicrosoft_2; "class Microsoft::WRL::ComPtr<struct Win"...
0x18009ceea  movups  xmmword ptr [rax], xmm0
0x18009ceed  movaps  xmm1, xmmword ptr cs:aClassMicrosoft_2+10h; ":WRL::ComPtr<struct Windows::Security::"...
0x18009cef4  movups  xmmword ptr [rax+10h], xmm1
0x18009cef8  movaps  xmm0, xmmword ptr cs:aClassMicrosoft_2+20h; "uct Windows::Security::Credentials::IWe"...
0x18009ceff  movups  xmmword ptr [rax+20h], xmm0
0x18009cf03  movaps  xmm1, xmmword ptr cs:aClassMicrosoft_2+30h; "urity::Credentials::IWebAccount> __cdec"...
0x18009cf0a  movups  xmmword ptr [rax+30h], xmm1
0x18009cf0e  movaps  xmm0, xmmword ptr cs:aClassMicrosoft_2+40h; "ls::IWebAccount> __cdecl shared::OneCor"...
0x18009cf15  movups  xmmword ptr [rax+40h], xmm0
0x18009cf19  movaps  xmm1, xmmword ptr cs:aClassMicrosoft_2+50h; " __cdecl shared::OneCoreAccountProvider"...
0x18009cf20  movups  xmmword ptr [rax+50h], xmm1
0x18009cf24  movaps  xmm0, xmmword ptr cs:aClassMicrosoft_2+60h; ":OneCoreAccountProvider::GetDefaultSign"...
0x18009cf2b  movups  xmmword ptr [rax+60h], xmm0
0x18009cf2f  movaps  xmm1, xmmword ptr cs:aClassMicrosoft_2+70h; "rovider::GetDefaultSignInAccount(void)"
0x18009cf36  movups  xmmword ptr [rax+70h], xmm1
0x18009cf3a  movaps  xmm0, xmmword ptr cs:aClassMicrosoft_2+80h; "ultSignInAccount(void)"
0x18009cf41  movups  xmmword ptr [rax+80h], xmm0
0x18009cf48  mov     rax, qword ptr cs:aClassMicrosoft_2+8Eh; "nt(void)"
0x18009cf4f  mov     [rcx+8Eh], rax
0x18009cf56  mov     byte ptr [rcx+96h], 0
0x18009cf5d  lea     r9, [rsp+240h+var_208]
0x18009cf62  lea     r8, [rsp+240h+string]
0x18009cf67  lea     rdx, [rsp+240h+var_1D8]
0x18009cf6c  mov     rcx, [rsp+240h+var_210]
0x18009cf71  call    ??$CancellableBlockingWRLCall@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@3@@shared@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@5@PEAPEAUIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@3@@Z; shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,std::string const &,std::chrono::duration<__int64,std::ratio<1,1000>> const &,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult * *)
0x18009cf76  mov     ebx, eax
0x18009cf78  lea     rcx, [rsp+240h+var_1D8]; void *
0x18009cf7d  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18009cf82  test    ebx, ebx
0x18009cf84  jns     short loc_18009CFBA
0x18009cf86  lea     rcx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009cf8d  mov     qword ptr [rsp+240h+var_1D8], rcx
0x18009cf92  mov     dword ptr [rsp+240h+var_1D8+8], 4FFh
0x18009cf9a  mov     r8d, ebx
0x18009cf9d  lea     rdx, [rsp+240h+var_1D8]
0x18009cfa2  lea     rcx, [rbp+140h+var_1B8]
0x18009cfa6  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009cfab  nop
0x18009cfac  mov     rdx, rax
0x18009cfaf  lea     rcx, [rsp+240h+var_1D8]
0x18009cfb4  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009cfba  mov     rbx, [rsp+240h+var_208]
0x18009cfbf  test    rbx, rbx
0x18009cfc2  jnz     short loc_18009CFFC
0x18009cfc4  lea     rcx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009cfcb  mov     qword ptr [rsp+240h+var_1D8], rcx
0x18009cfd0  mov     dword ptr [rsp+240h+var_1D8+8], 500h
0x18009cfd8  lea     r8, aUnexpectedNull; "Unexpected null result from async opera"...
0x18009cfdf  lea     rdx, [rsp+240h+var_1D8]
0x18009cfe4  lea     rcx, [rbp+140h+var_1B8]
0x18009cfe8  call    ??$MakeException@V?$HResultException@$0?HPPPAAAB@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPAAAB@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147418113>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x18009cfed  nop
0x18009cfee  mov     rdx, rax
0x18009cff1  lea     rcx, [rsp+240h+var_1D8]
0x18009cff6  call    ??$CdpThrow@V?$HResultException@$0?HPPPAAAB@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPAAAB@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147418113>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147418113> &&)
0x18009cffc  mov     qword ptr [rsi], 0
0x18009d003  mov     r14d, 1
0x18009d009  mov     [rsp+240h+var_21C], r14d
0x18009d00e  mov     rax, [rbx]
0x18009d011  mov     rdi, [rax+30h]
0x18009d015  mov     rcx, rsi
0x18009d018  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009d01d  mov     rdx, rsi
0x18009d020  mov     rcx, rbx
0x18009d023  mov     rax, rdi
0x18009d026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d02b  test    eax, eax
0x18009d02d  jns     short loc_18009D063
0x18009d02f  lea     rcx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d036  mov     qword ptr [rsp+240h+var_1D8], rcx
0x18009d03b  mov     dword ptr [rsp+240h+var_1D8+8], 503h
0x18009d043  mov     r8d, eax
0x18009d046  lea     rdx, [rsp+240h+var_1D8]
0x18009d04b  lea     rcx, [rbp+140h+var_1B8]
0x18009d04f  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009d054  nop
0x18009d055  mov     rdx, rax
0x18009d058  lea     rcx, [rsp+240h+var_1D8]
0x18009d05d  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d063  mov     rdx, [rsi]
0x18009d066  test    rdx, rdx
0x18009d069  jz      loc_18009D147
0x18009d06f  mov     rcx, r15
0x18009d072  call    ?GetAccountProviderType@OneCoreAccountProvider@shared@@AEAA?AW4CDPAccountType@@PEAUIWebAccount@Credentials@Security@Windows@@@Z; shared::OneCoreAccountProvider::GetAccountProviderType(Windows::Security::Credentials::IWebAccount *)
0x18009d077  movzx   r15d, ax
0x18009d07b  mov     [rsp+240h+string], 0
0x18009d084  mov     rdi, [rsi]
0x18009d087  mov     rax, [rdi]
0x18009d08a  mov     rbx, [rax+38h]
0x18009d08e  xor     ecx, ecx; string
0x18009d090  call    cs:__imp_WindowsDeleteString
0x18009d096  mov     [rsp+240h+string], 0
0x18009d09f  lea     rdx, [rsp+240h+string]
0x18009d0a4  mov     rcx, rdi
0x18009d0a7  mov     rax, rbx
0x18009d0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d0af  mov     [rsp+240h+var_220], eax
0x18009d0b3  mov     ebx, 3
0x18009d0b8  test    eax, eax
0x18009d0ba  js      short loc_18009D0F5
0x18009d0bc  xor     edx, edx; length
0x18009d0be  mov     rcx, [rsp+240h+string]; string
0x18009d0c3  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d0c9  mov     rdx, rax
0x18009d0cc  lea     rcx, [rsp+240h+var_1F8]
0x18009d0d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009d0d6  mov     rdx, rax
0x18009d0d9  lea     rcx, [rbp+140h+var_1B8]
0x18009d0dd  call    ?EncryptString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; EncryptString(std::wstring)
0x18009d0e2  mov     r14d, ebx
0x18009d0e5  mov     [rsp+240h+var_21C], ebx
0x18009d0e9  cmp     qword ptr [rax+18h], 7
0x18009d0ee  jbe     short loc_18009D0FC
0x18009d0f0  mov     rax, [rax]
0x18009d0f3  jmp     short loc_18009D0FC
0x18009d0f5  lea     rax, pNodeName
0x18009d0fc  mov     qword ptr [rsp+240h+var_1D8], rax
0x18009d101  lea     r8, [rsp+240h+var_1D8]
0x18009d106  lea     rdx, [rsp+240h+var_220]
0x18009d10b  lea     rcx, [rbp+140h+var_180]
0x18009d10f  call    ??$GetDefaultSignInAccountAsync@AEAJPEBG@GetDefaultSignInAccountActivity@OneCoreAccountTelemetryProvider@@QEAAXAEAJ$$QEAPEBG@Z; OneCoreAccountTelemetryProvider::GetDefaultSignInAccountActivity::GetDefaultSignInAccountAsync<long &,ushort const *>(long &,ushort const * &&)
0x18009d114  test    r14b, 2
0x18009d118  jz      short loc_18009D12C
0x18009d11a  and     r14d, 0FFFFFFFDh
0x18009d11e  mov     [rsp+240h+var_21C], r14d
0x18009d123  lea     rcx, [rbp+140h+var_1B8]
0x18009d127  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009d12c  cmp     r15w, bx
0x18009d130  jnz     short loc_18009D13B
0x18009d132  mov     rcx, rsi
0x18009d135  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009d13a  nop
0x18009d13b  mov     rcx, [rsp+240h+string]; string
0x18009d140  call    cs:__imp_WindowsDeleteString
0x18009d146  nop
0x18009d147  mov     rcx, [rsp+240h+var_208]
0x18009d14c  test    rcx, rcx
0x18009d14f  jz      short loc_18009D167
0x18009d151  mov     [rsp+240h+var_208], 0
0x18009d15a  mov     rax, [rcx]
0x18009d15d  mov     rax, [rax+10h]
0x18009d161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d166  nop
0x18009d167  mov     rcx, [rsp+240h+var_210]
0x18009d16c  test    rcx, rcx
0x18009d16f  jz      short loc_18009D187
0x18009d171  mov     [rsp+240h+var_210], 0
0x18009d17a  mov     rdx, [rcx]
0x18009d17d  mov     rax, [rdx+10h]
0x18009d181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d186  nop
0x18009d187  mov     [rbp+140h+var_180], r13
0x18009d18b  lea     rcx, [rbp+140h+var_180]
0x18009d18f  call    ?Destroy@?$ActivityBase@VOneCoreAccountTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18009d194  lea     rcx, [rbp+140h+var_180]
0x18009d198  call    ??1?$ActivityBase@VOneCoreAccountTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18009d19d  mov     rax, rsi
0x18009d1a0  mov     rcx, [rbp+140h+var_30]
0x18009d1a7  xor     rcx, rsp; StackCookie
0x18009d1aa  call    __security_check_cookie
0x18009d1af  lea     r11, [rsp+240h+var_20]
0x18009d1b7  mov     rbx, [r11+40h]
0x18009d1bb  mov     rsi, [r11+48h]
0x18009d1bf  mov     rsp, r11
0x18009d1c2  pop     r15
0x18009d1c4  pop     r14
0x18009d1c6  pop     r13
0x18009d1c8  pop     rdi
0x18009d1c9  pop     rbp
0x18009d1ca  retn
```
