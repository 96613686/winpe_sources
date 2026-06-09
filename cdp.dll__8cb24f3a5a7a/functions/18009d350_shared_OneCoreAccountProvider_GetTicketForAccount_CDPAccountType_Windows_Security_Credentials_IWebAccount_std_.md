# shared::OneCoreAccountProvider::GetTicketForAccount(CDPAccountType,Windows::Security::Credentials::IWebAccount *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,CDPStrongAuthenticationRequirement,HWND__ *)

- ea: `0x18009d350`
- end: `0x18009db19`
- name: `?GetTicketForAccount@OneCoreAccountProvider@shared@@AEAA?AV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_NV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@@std@@W4CDPAccountType@@PEAUIWebAccount@Credentials@Security@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@2W4CDPStrongAuthenticationRequirement@@PEAUHWND__@@@Z`
- size: `1993`
- prototype: ``
- caller_count: `4`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x180140dc4`
- `0x180162df8`
- `0x180163810`
- `0x18020e348`

## callees

- `0x18000aec4`
- `0x18000d02c`
- `0x18000d070`
- `0x18000d350`
- `0x18001ce80`
- `0x180030190`
- `0x1800624cc`
- `0x18008dbc0`
- `0x180091258`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18009d350`
- `0x18009dd54`
- `0x18009ded4`
- `0x18009e080`
- `0x18009e140`
- `0x18009e1ec`
- `0x180114c58`
- `0x18011d8c4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x1801fcb4e`
- `0x18020bc00`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d77b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009d77b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18009d946`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18009d946`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d85f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009da77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009d85f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009da77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d90a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d90a`

## string_xrefs

- `0x18009d7a4`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18009d51f`: `{"text":"Token result: WebTokenRequestStatus_ProviderError."}`
- `0x18009d573`: `WebTokenRequest failed due to provider error`
- `0x18009d617`: `WebTokenRequest failed due to provider error`
- `0x18009d6b8`: `{"text":"Token result: WebTokenRequestStatus_UserCancel."}`
- `0x18009d50e`: `{"text":"Token result: WebTokenRequestStatus_UserInteractionRequired."}`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
char *__fastcall shared::OneCoreAccountProvider::GetTicketForAccount(
        __int64 a1,
        char *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        unsigned int a7,
        __int64 a8)
{
  __int16 v9; // r12
  char *TokenResultForAccount; // rbx
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int128 *); // rbx
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // r8
  bool v26; // sf
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  int v36; // ecx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, _QWORD, __int64 *); // rbx
  int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, HSTRING *); // rbx
  int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rax
  PCWSTR StringRawBuffer; // rax
  PCWSTR v52; // r14
  unsigned __int64 v53; // rbx
  __int64 v54; // rsi
  size_t v55; // rbx
  __int64 size_of; // rax
  char *v57; // rdi
  size_t v58; // rbx
  __int64 v59; // rbx
  char *v60; // rdi
  __int64 v61; // rdx
  __int64 v62; // r8
  char *v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  char *v68; // [rsp+40h] [rbp-C0h] BYREF
  int v69; // [rsp+48h] [rbp-B8h] BYREF
  char v70[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v71; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v72; // [rsp+58h] [rbp-A8h]
  __int64 v73; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v74; // [rsp+68h] [rbp-98h] BYREF
  int v75; // [rsp+70h] [rbp-90h] BYREF
  int v76; // [rsp+74h] [rbp-8Ch] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  char *v78; // [rsp+80h] [rbp-80h] BYREF
  char v79; // [rsp+90h] [rbp-70h] BYREF
  __int128 v80; // [rsp+98h] [rbp-68h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-58h]
  _BYTE pExceptionObject[56]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v83[42]; // [rsp+F0h] [rbp-10h] BYREF

  v9 = a3;
  v68 = a2;
  v78 = a2;
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v83,
    "GetTicketForAccountActivity",
    a3);
  v83[0] = &OneCoreAccountTelemetryProvider::GetTicketForAccountActivity::`vftable';
  OneCoreAccountTelemetryProvider::GetTicketForAccountActivity::StartActivity((OneCoreAccountTelemetryProvider::GetTicketForAccountActivity *)v83);
  v72 = 0;
  TokenResultForAccount = shared::OneCoreAccountProvider::GetTokenResultForAccount(
                            a1,
                            (char *)&v80,
                            v9,
                            a4,
                            a5,
                            a6,
                            a7,
                            a8);
  v12 = (__int64 *)(TokenResultForAccount + 8);
  v13 = 0;
  if ( &v79 != TokenResultForAccount + 8 )
  {
    v13 = *v12;
    *v12 = 0;
  }
  v14 = v72;
  v72 = v13;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v70[0] = *TokenResultForAccount;
  v15 = *((_QWORD *)&v80 + 1);
  if ( *((_QWORD *)&v80 + 1) )
  {
    *((_QWORD *)&v80 + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v72 + 56LL))(v72, &v75);
  if ( v16 < 0 )
  {
    v68 = ".\\onecoreaccountprovider.cpp";
    v69 = 1811;
    v17 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v68, (unsigned int)v16);
    cdp::CdpThrow<cdp::hresult_exception>(&v68, v17);
  }
  OneCoreAccountTelemetryProvider::GetTicketForAccountActivity::WebTokenResponseStatus<enum Windows::Security::Authentication::Web::Core::WebTokenRequestStatus &,bool &>(
    v83,
    &v75,
    v70);
  if ( v75 )
  {
    switch ( v75 )
    {
      case 1:
        Log<>(4, "{\"text\":\"Token result: WebTokenRequestStatus_UserCancel.\"}");
        v68 = ".\\onecoreaccountprovider.cpp";
        v69 = 1822;
        v33 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v68, 2147943623LL);
        cdp::CdpThrow<cdp::hresult_exception>(&v68, v33);
      case 3:
        Log<>(4, "{\"text\":\"Token result: WebTokenRequestStatus_UserInteractionRequired.\"}");
        break;
      case 5:
        break;
      default:
        v68 = ".\\onecoreaccountprovider.cpp";
        v69 = 1840;
        v18 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v68, 2147942952LL);
        cdp::CdpThrow<cdp::hresult_exception>(&v68, v18);
    }
    Log<>(4, "{\"text\":\"Token result: WebTokenRequestStatus_ProviderError.\"}");
    *(_QWORD *)&v80 = 0;
    v19 = v72;
    v20 = *(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v72 + 64LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v80);
    v21 = v20(v19, &v80);
    if ( v21 < 0 )
    {
      v68 = ".\\onecoreaccountprovider.cpp";
      v69 = 1832;
      v22 = cdp::MakeException<cdp::hresult_exception,>(
              pExceptionObject,
              &v68,
              (unsigned int)v21,
              "WebTokenRequest failed due to provider error");
      cdp::CdpThrow<cdp::hresult_exception>(&v68, v22);
    }
    v71 = 0;
    v23 = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD))(*(_QWORD *)v80 + 48LL))(v80, &v71, (unsigned int)v21);
    if ( v23 < 0 )
    {
      v68 = ".\\onecoreaccountprovider.cpp";
      v69 = 1834;
      v24 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v68, (unsigned int)v23);
      cdp::CdpThrow<cdp::hresult_exception>(&v68, v24);
    }
    v25 = (unsigned int)v71;
    v26 = v71 < 0;
    if ( v71 > 0 )
    {
      v25 = (unsigned __int16)v71 | 0x80070000;
      v26 = 1;
    }
    if ( v26 )
    {
      v68 = ".\\onecoreaccountprovider.cpp";
      v69 = 1835;
      v27 = cdp::MakeException<cdp::hresult_exception,>(
              pExceptionObject,
              &v68,
              v25,
              "WebTokenRequest failed due to provider error");
      cdp::CdpThrow<cdp::hresult_exception>(&v68, v27);
    }
    v28 = v80;
    if ( (_QWORD)v80 )
    {
      *(_QWORD *)&v80 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
  }
  v74 = 0;
  v29 = v72;
  v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v72 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
  v31 = v30(v29, &v74);
  if ( v31 < 0 )
  {
    v68 = ".\\onecoreaccountprovider.cpp";
    v69 = 1846;
    v32 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v68, (unsigned int)v31);
    cdp::CdpThrow<cdp::hresult_exception>(&v68, v32);
  }
  v76 = 0;
  v34 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v74 + 56LL))(v74, &v76, (unsigned int)v31);
  if ( v34 < 0 )
  {
    v68 = ".\\onecoreaccountprovider.cpp";
    v69 = 1849;
    v35 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v68, (unsigned int)v34);
    cdp::CdpThrow<cdp::hresult_exception>(&v68, v35);
  }
  if ( v76 != 1 )
  {
    v68 = ".\\onecoreaccountprovider.cpp";
    v69 = 1852;
    v71 = -2147418113;
    *(_QWORD *)&v80 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v36,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v71,
      (unsigned int)&v68,
      (__int64)&v69,
      (__int64)&v80);
    v37 = cdp::ExceptionStackFromSourceLocationInfo(&v80, &v68);
    v40 = cdp::ErrorCodeToString(2147549183LL, v38, v39, v37);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147549183LL, v40);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v73 = 0;
  v41 = v74;
  v42 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v74 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v73);
  v43 = v42(v41, 0, &v73);
  if ( v43 < 0 )
  {
    v68 = ".\\onecoreaccountprovider.cpp";
    v69 = 1855;
    v44 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v68, (unsigned int)v43);
    cdp::CdpThrow<cdp::hresult_exception>(&v68, v44);
  }
  string = 0;
  v45 = v73;
  v46 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v73 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v47 = v46(v45, &string);
  if ( v47 < 0 )
  {
    v68 = ".\\onecoreaccountprovider.cpp";
    v69 = 1858;
    v48 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v68, (unsigned int)v47);
    cdp::CdpThrow<cdp::hresult_exception>(&v68, v48);
  }
  v78 = 0;
  v49 = (*(__int64 (__fastcall **)(__int64, char **, _QWORD))(*(_QWORD *)v73 + 64LL))(v73, &v78, (unsigned int)v47);
  if ( v49 < 0 )
  {
    v68 = ".\\onecoreaccountprovider.cpp";
    v69 = 1861;
    v50 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v68, (unsigned int)v49);
    cdp::CdpThrow<cdp::hresult_exception>(&v68, v50);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v52 = StringRawBuffer;
  v80 = 0;
  si128 = 0;
  v53 = -1;
  do
    ++v53;
  while ( StringRawBuffer[v53] );
  v54 = 0x7FFFFFFFFFFFFFFELL;
  if ( v53 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v53 > 7 )
  {
    if ( (v53 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v54 = v53 | 7;
      if ( (v53 | 7) < 0xA )
        v54 = 10;
    }
    size_of = std::_Get_size_of_n<2>(v54 + 1);
    v57 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    *(_QWORD *)&v80 = v57;
    si128.m128i_i64[0] = v53;
    si128.m128i_i64[1] = v54;
    v58 = 2 * v53;
    memcpy_0(v57, v52, v58);
    *(_WORD *)&v57[v58] = 0;
  }
  else
  {
    si128.m128i_i64[0] = v53;
    si128.m128i_i64[1] = 7;
    v55 = 2 * v53;
    memcpy_0(&v80, StringRawBuffer, v55);
    *(_WORD *)((char *)&v80 + v55) = 0;
  }
  v59 = cdp::ToUtf8(pExceptionObject, &v80);
  v60 = v68;
  *(_QWORD *)v68 = v78;
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>::InternalAddRef(
    v60,
    v61,
    v62);
  v60[8] = v70[0];
  *((_OWORD *)v60 + 1) = 0;
  *((_QWORD *)v60 + 4) = 0;
  *((_QWORD *)v60 + 5) = 0;
  *((_OWORD *)v60 + 1) = *(_OWORD *)v59;
  *((_OWORD *)v60 + 2) = *(_OWORD *)(v59 + 16);
  *(_QWORD *)(v59 + 16) = 0;
  *(_QWORD *)(v59 + 24) = 15;
  *(_BYTE *)v59 = 0;
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(pExceptionObject);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v80, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v80) = 0;
  v63 = v78;
  if ( v78 )
  {
    v78 = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v63 + 16LL))(v63);
  }
  WindowsDeleteString(string);
  string = 0;
  v64 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  }
  v65 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  }
  v66 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  }
  v83[0] = &OneCoreAccountTelemetryProvider::GetTicketForAccountActivity::`vftable';
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v83);
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v83);
  return v60;
}

```

## disassembly

```asm
0x18009d350  push    rbp
0x18009d352  push    rbx
0x18009d353  push    rsi
0x18009d354  push    rdi
0x18009d355  push    r12
0x18009d357  push    r13
0x18009d359  push    r14
0x18009d35b  push    r15
0x18009d35d  lea     rbp, [rsp-158h]
0x18009d365  sub     rsp, 258h
0x18009d36c  mov     rax, cs:__security_cookie
0x18009d373  xor     rax, rsp
0x18009d376  mov     [rbp+190h+var_50], rax
0x18009d37d  mov     r13, r9
0x18009d380  movzx   r12d, r8w
0x18009d384  mov     [rsp+290h+var_250], rdx
0x18009d389  mov     r15, rcx
0x18009d38c  mov     [rbp+190h+var_210], rdx
0x18009d390  mov     r14, [rbp+190h+arg_20]
0x18009d397  mov     rsi, [rbp+190h+arg_28]
0x18009d39e  mov     edi, [rbp+190h+arg_30]
0x18009d3a4  mov     rbx, [rbp+190h+arg_38]
0x18009d3ab  lea     rdx, aGetticketforac; "GetTicketForAccountActivity"
0x18009d3b2  lea     rcx, [rbp+190h+var_1A0]
0x18009d3b6  call    ??0?$ActivityBase@VOneCoreAccountTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009d3bb  lea     rax, ??_7GetTicketForAccountActivity@OneCoreAccountTelemetryProvider@@6B@; const OneCoreAccountTelemetryProvider::GetTicketForAccountActivity::`vftable'
0x18009d3c2  mov     [rbp+190h+var_1A0], rax
0x18009d3c6  lea     rcx, [rbp+190h+var_1A0]; this
0x18009d3ca  call    ?StartActivity@GetTicketForAccountActivity@OneCoreAccountTelemetryProvider@@QEAAXXZ; OneCoreAccountTelemetryProvider::GetTicketForAccountActivity::StartActivity(void)
0x18009d3cf  nop
0x18009d3d0  mov     [rsp+290h+var_238], 0
0x18009d3d9  mov     [rsp+290h+var_258], rbx
0x18009d3de  mov     [rsp+290h+var_260], edi
0x18009d3e2  mov     [rsp+290h+var_268], rsi
0x18009d3e7  mov     [rsp+290h+var_270], r14
0x18009d3ec  mov     r9, r13
0x18009d3ef  movzx   r8d, r12w
0x18009d3f3  lea     rdx, [rbp+190h+var_1F8]
0x18009d3f7  mov     rcx, r15
0x18009d3fa  call    ?GetTokenResultForAccount@OneCoreAccountProvider@shared@@AEAA?AV?$tuple@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@_N@std@@W4CDPAccountType@@PEAUIWebAccount@Credentials@Security@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@2W4CDPStrongAuthenticationRequirement@@PEAUHWND__@@@Z; shared::OneCoreAccountProvider::GetTokenResultForAccount(CDPAccountType,Windows::Security::Credentials::IWebAccount *,std::wstring const &,std::wstring const &,CDPStrongAuthenticationRequirement,HWND__ *)
0x18009d3ff  mov     rbx, rax
0x18009d402  lea     rcx, [rax+8]
0x18009d406  xor     r15d, r15d
0x18009d409  mov     eax, r15d
0x18009d40c  lea     rdx, [rbp+190h+var_200]
0x18009d410  cmp     rdx, rcx
0x18009d413  jz      short loc_18009D41B
0x18009d415  mov     rax, [rcx]
0x18009d418  mov     [rcx], r15
0x18009d41b  mov     rcx, [rsp+290h+var_238]
0x18009d420  mov     [rsp+290h+var_238], rax
0x18009d425  test    rcx, rcx
0x18009d428  jz      short loc_18009D437
0x18009d42a  mov     rax, [rcx]
0x18009d42d  mov     rax, [rax+10h]
0x18009d431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d436  nop
0x18009d437  mov     al, [rbx]
0x18009d439  mov     [rsp+290h+var_240], al
0x18009d43d  mov     rcx, qword ptr [rbp+190h+var_1F8+8]
0x18009d441  test    rcx, rcx
0x18009d444  jz      short loc_18009D457
0x18009d446  mov     qword ptr [rbp+190h+var_1F8+8], r15
0x18009d44a  mov     rax, [rcx]
0x18009d44d  mov     rax, [rax+10h]
0x18009d451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d456  nop
0x18009d457  mov     rcx, [rsp+290h+var_238]
0x18009d45c  mov     rax, [rcx]
0x18009d45f  lea     rdx, [rsp+290h+var_220]
0x18009d464  mov     rax, [rax+38h]
0x18009d468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d46d  mov     r8d, eax
0x18009d470  test    eax, eax
0x18009d472  jns     short loc_18009D4A5
0x18009d474  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d47b  mov     [rsp+290h+var_250], rax
0x18009d480  mov     [rsp+290h+var_248], 713h
0x18009d488  lea     rdx, [rsp+290h+var_250]
0x18009d48d  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d491  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009d496  nop
0x18009d497  mov     rdx, rax
0x18009d49a  lea     rcx, [rsp+290h+var_250]
0x18009d49f  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d4a5  lea     r8, [rsp+290h+var_240]
0x18009d4aa  lea     rdx, [rsp+290h+var_220]
0x18009d4af  lea     rcx, [rbp+190h+var_1A0]
0x18009d4b3  call    ??$WebTokenResponseStatus@AEAW4WebTokenRequestStatus@Core@Web@Authentication@Security@Windows@@AEA_N@GetTicketForAccountActivity@OneCoreAccountTelemetryProvider@@QEAAXAEAW4WebTokenRequestStatus@Core@Web@Authentication@Security@Windows@@AEA_N@Z; OneCoreAccountTelemetryProvider::GetTicketForAccountActivity::WebTokenResponseStatus<Windows::Security::Authentication::Web::Core::WebTokenRequestStatus &,bool &>(Windows::Security::Authentication::Web::Core::WebTokenRequestStatus &,bool &)
0x18009d4b8  mov     ecx, [rsp+290h+var_220]
0x18009d4bc  test    ecx, ecx
0x18009d4be  jz      loc_18009D655
0x18009d4c4  sub     ecx, 1
0x18009d4c7  jz      loc_18009D6B8
0x18009d4cd  sub     ecx, 2
0x18009d4d0  jz      short loc_18009D50E
0x18009d4d2  cmp     ecx, 2
0x18009d4d5  jz      short loc_18009D51F
0x18009d4d7  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d4de  mov     [rsp+290h+var_250], rax
0x18009d4e3  mov     [rsp+290h+var_248], 730h
0x18009d4eb  mov     r8d, 80070228h
0x18009d4f1  lea     rdx, [rsp+290h+var_250]
0x18009d4f6  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d4fa  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009d4ff  nop
0x18009d500  mov     rdx, rax
0x18009d503  lea     rcx, [rsp+290h+var_250]
0x18009d508  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d50e  lea     rdx, aTextTokenResul; "{\"text\":\"Token result: WebTokenReque"...
0x18009d515  mov     ecx, 4
0x18009d51a  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18009d51f  lea     rdx, aTextTokenResul_0; "{\"text\":\"Token result: WebTokenReque"...
0x18009d526  mov     ecx, 4
0x18009d52b  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18009d530  mov     qword ptr [rbp+190h+var_1F8], r15
0x18009d534  mov     rdi, [rsp+290h+var_238]
0x18009d539  mov     rax, [rdi]
0x18009d53c  mov     rbx, [rax+40h]
0x18009d540  lea     rcx, [rbp+190h+var_1F8]
0x18009d544  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009d549  lea     rdx, [rbp+190h+var_1F8]
0x18009d54d  mov     rcx, rdi
0x18009d550  mov     rax, rbx
0x18009d553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d558  mov     r8d, eax
0x18009d55b  test    eax, eax
0x18009d55d  jns     short loc_18009D597
0x18009d55f  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d566  mov     [rsp+290h+var_250], rax
0x18009d56b  mov     [rsp+290h+var_248], 728h
0x18009d573  lea     r9, aWebtokenreques; "WebTokenRequest failed due to provider "...
0x18009d57a  lea     rdx, [rsp+290h+var_250]
0x18009d57f  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d583  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x18009d588  nop
0x18009d589  mov     rdx, rax
0x18009d58c  lea     rcx, [rsp+290h+var_250]
0x18009d591  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d597  mov     [rsp+290h+var_23C], r15d
0x18009d59c  mov     rcx, qword ptr [rbp+190h+var_1F8]
0x18009d5a0  mov     rax, [rcx]
0x18009d5a3  lea     rdx, [rsp+290h+var_23C]
0x18009d5a8  mov     rax, [rax+30h]
0x18009d5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d5b1  mov     r8d, eax
0x18009d5b4  test    eax, eax
0x18009d5b6  jns     short loc_18009D5E9
0x18009d5b8  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d5bf  mov     [rsp+290h+var_250], rax
0x18009d5c4  mov     [rsp+290h+var_248], 72Ah
0x18009d5cc  lea     rdx, [rsp+290h+var_250]
0x18009d5d1  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d5d5  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009d5da  nop
0x18009d5db  mov     rdx, rax
0x18009d5de  lea     rcx, [rsp+290h+var_250]
0x18009d5e3  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d5e9  mov     r8d, [rsp+290h+var_23C]
0x18009d5ee  test    r8d, r8d
0x18009d5f1  jle     short loc_18009D601
0x18009d5f3  movzx   r8d, r8w
0x18009d5f7  or      r8d, 80070000h
0x18009d5fe  test    r8d, r8d
0x18009d601  jns     short loc_18009D63B
0x18009d603  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d60a  mov     [rsp+290h+var_250], rax
0x18009d60f  mov     [rsp+290h+var_248], 72Bh
0x18009d617  lea     r9, aWebtokenreques; "WebTokenRequest failed due to provider "...
0x18009d61e  lea     rdx, [rsp+290h+var_250]
0x18009d623  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d627  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x18009d62c  nop
0x18009d62d  mov     rdx, rax
0x18009d630  lea     rcx, [rsp+290h+var_250]
0x18009d635  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d63b  mov     rcx, qword ptr [rbp+190h+var_1F8]
0x18009d63f  test    rcx, rcx
0x18009d642  jz      short loc_18009D655
0x18009d644  mov     qword ptr [rbp+190h+var_1F8], r15
0x18009d648  mov     rax, [rcx]
0x18009d64b  mov     rax, [rax+10h]
0x18009d64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d654  nop
0x18009d655  mov     [rsp+290h+var_228], r15
0x18009d65a  mov     rdi, [rsp+290h+var_238]
0x18009d65f  mov     rax, [rdi]
0x18009d662  mov     rbx, [rax+30h]
0x18009d666  lea     rcx, [rsp+290h+var_228]
0x18009d66b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009d670  lea     rdx, [rsp+290h+var_228]
0x18009d675  mov     rcx, rdi
0x18009d678  mov     rax, rbx
0x18009d67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d680  mov     r8d, eax
0x18009d683  test    eax, eax
0x18009d685  jns     short loc_18009D700
0x18009d687  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d68e  mov     [rsp+290h+var_250], rax
0x18009d693  mov     [rsp+290h+var_248], 736h
0x18009d69b  lea     rdx, [rsp+290h+var_250]
0x18009d6a0  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d6a4  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009d6a9  nop
0x18009d6aa  mov     rdx, rax
0x18009d6ad  lea     rcx, [rsp+290h+var_250]
0x18009d6b2  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d6b8  lea     rdx, aTextTokenResul_1; "{\"text\":\"Token result: WebTokenReque"...
0x18009d6bf  mov     ecx, 4
0x18009d6c4  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18009d6c9  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d6d0  mov     [rsp+290h+var_250], rax
0x18009d6d5  mov     [rsp+290h+var_248], 71Eh
0x18009d6dd  mov     r8d, 800704C7h
0x18009d6e3  lea     rdx, [rsp+290h+var_250]
0x18009d6e8  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d6ec  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009d6f1  nop
0x18009d6f2  mov     rdx, rax
0x18009d6f5  lea     rcx, [rsp+290h+var_250]
0x18009d6fa  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d700  mov     [rsp+290h+var_21C], r15d
0x18009d705  mov     rcx, [rsp+290h+var_228]
0x18009d70a  mov     rax, [rcx]
0x18009d70d  lea     rdx, [rsp+290h+var_21C]
0x18009d712  mov     rax, [rax+38h]
0x18009d716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d71b  mov     r8d, eax
0x18009d71e  test    eax, eax
0x18009d720  jns     short loc_18009D753
0x18009d722  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d729  mov     [rsp+290h+var_250], rax
0x18009d72e  mov     [rsp+290h+var_248], 739h
0x18009d736  lea     rdx, [rsp+290h+var_250]
0x18009d73b  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d73f  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009d744  nop
0x18009d745  mov     rdx, rax
0x18009d748  lea     rcx, [rsp+290h+var_250]
0x18009d74d  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d753  cmp     [rsp+290h+var_21C], 1
0x18009d758  jz      loc_18009D7E7
0x18009d75e  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d765  mov     [rsp+290h+var_250], rax
0x18009d76a  mov     [rsp+290h+var_248], 73Ch
0x18009d772  mov     ebx, 8000FFFFh
0x18009d777  mov     [rsp+290h+var_23C], ebx
0x18009d77b  call    cs:__imp_GetCurrentThreadId
0x18009d781  mov     eax, eax
0x18009d783  mov     qword ptr [rbp+190h+var_1F8], rax
0x18009d787  lea     rax, [rbp+190h+var_1F8]
0x18009d78b  mov     [rsp+290h+var_268], rax
0x18009d790  lea     rax, [rsp+290h+var_248]
0x18009d795  mov     [rsp+290h+var_270], rax
0x18009d79a  lea     r9, [rsp+290h+var_250]
0x18009d79f  lea     r8, [rsp+290h+var_23C]
0x18009d7a4  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18009d7ab  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18009d7b0  lea     rdx, [rsp+290h+var_250]
0x18009d7b5  lea     rcx, [rbp+190h+var_1F8]
0x18009d7b9  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18009d7be  mov     r9, rax
0x18009d7c1  mov     ecx, ebx
0x18009d7c3  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18009d7c8  mov     r8, rax
0x18009d7cb  mov     edx, ebx
0x18009d7cd  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d7d1  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18009d7d6  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18009d7dd  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x18009d7e1  call    _CxxThrowException_0
0x18009d7e7  mov     [rsp+290h+var_230], r15
0x18009d7ec  mov     rdi, [rsp+290h+var_228]
0x18009d7f1  mov     rax, [rdi]
0x18009d7f4  mov     rbx, [rax+30h]
0x18009d7f8  lea     rcx, [rsp+290h+var_230]
0x18009d7fd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009d802  lea     r8, [rsp+290h+var_230]
0x18009d807  xor     edx, edx
0x18009d809  mov     rcx, rdi
0x18009d80c  mov     rax, rbx
0x18009d80f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d814  mov     r8d, eax
0x18009d817  test    eax, eax
0x18009d819  jns     short loc_18009D84C
0x18009d81b  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009d822  mov     [rsp+290h+var_250], rax
0x18009d827  mov     [rsp+290h+var_248], 73Fh
0x18009d82f  lea     rdx, [rsp+290h+var_250]
0x18009d834  lea     rcx, [rbp+190h+pExceptionObject]
0x18009d838  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009d83d  nop
0x18009d83e  mov     rdx, rax
0x18009d841  lea     rcx, [rsp+290h+var_250]
0x18009d846  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009d84c  mov     [rsp+290h+string], r15
0x18009d851  mov     rdi, [rsp+290h+var_230]
0x18009d856  mov     rax, [rdi]
0x18009d859  mov     rbx, [rax+30h]
0x18009d85d  xor     ecx, ecx; string
  ... truncated ...
```
