# LPA::Lpd::DownloadInstance::InitializeHttpClient(void)

- ea: `0x1800b089c`
- end: `0x1800b0e2f`
- name: `?InitializeHttpClient@DownloadInstance@Lpd@LPA@@AEAAJXZ`
- size: `1427`
- prototype: `__int64 __fastcall(LPA::Lpd::DownloadInstance *__hidden this)`
- caller_count: `2`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800af458`
- `0x1800b81b8`

## callees

- `0x18000df90`
- `0x18000e46c`
- `0x18000ebf4`
- `0x1800115e0`
- `0x180013640`
- `0x1800141d0`
- `0x1800356e0`
- `0x18005fe70`
- `0x180063668`
- `0x180071320`
- `0x180071650`
- `0x180097224`
- `0x1800999f0`
- `0x1800a639c`
- `0x1800a692c`
- `0x1800a696c`
- `0x1800a69a0`
- `0x1800a6a2c`
- `0x1800a6a94`
- `0x1800a7fa0`
- `0x1800a7fbc`
- `0x1800a8a18`
- `0x1800a8c48`
- `0x1800a8c7c`
- `0x1800a8e1c`
- `0x1800a8f9c`
- `0x1800a8fd8`
- `0x1800ab810`
- `0x1800b089c`
- `0x1800c1c10`
- `0x1800c4050`
- `0x1800d97c8`
- `0x1800f1cd0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b0d3b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b0d4e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b0d61`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b0d3b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b0d4e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b0d61`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800b0ba4`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800b0ba4`
- `MobileNetworking!PersistentRegPathGetDWORD` at `0x1800b0b1a`
- `MobileNetworking!PersistentRegPathGetDWORD` at `0x1800b0b1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall LPA::Lpd::DownloadInstance::InitializeHttpClient(LPA::Lpd::DownloadInstance *this)
{
  LPA::Lpd::DownloadInstance *v1; // rsi
  __int64 v2; // rax
  int v3; // edi
  __int64 v4; // rax
  __int64 v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  const struct web::uri *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rdx
  LPA::Lpd::DownloadInstance *v16; // rbx
  _QWORD *v17; // rax
  int v18; // r8d
  int v19; // r9d
  int v20; // [rsp+50h] [rbp-758h] BYREF
  int v21; // [rsp+58h] [rbp-750h] BYREF
  web::http::client::http_client *v22; // [rsp+60h] [rbp-748h] BYREF
  LPA::Lpd::DownloadInstance *v23; // [rsp+68h] [rbp-740h]
  __int64 v24; // [rsp+70h] [rbp-738h] BYREF
  __int64 v25; // [rsp+78h] [rbp-730h] BYREF
  _QWORD *v26; // [rsp+80h] [rbp-728h] BYREF
  const char *v27; // [rsp+88h] [rbp-720h] BYREF
  const std::exception *v28; // [rsp+90h] [rbp-718h] BYREF
  _BYTE v29[304]; // [rsp+98h] [rbp-710h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+1C8h] [rbp-5E0h] BYREF
  LPA::Lpd *v31; // [rsp+1E8h] [rbp-5C0h] BYREF
  std::_Ref_count_base *v32; // [rsp+1F0h] [rbp-5B8h]
  __int128 v33; // [rsp+208h] [rbp-5A0h] BYREF
  __int64 v34; // [rsp+218h] [rbp-590h]
  __int64 v35; // [rsp+220h] [rbp-588h]
  _BYTE v36[40]; // [rsp+228h] [rbp-580h] BYREF
  _DWORD v37[54]; // [rsp+250h] [rbp-558h] BYREF
  __int128 v38; // [rsp+328h] [rbp-480h]
  _BYTE v39[240]; // [rsp+340h] [rbp-468h] BYREF
  _BYTE v40[208]; // [rsp+430h] [rbp-378h] BYREF
  _BYTE v41[416]; // [rsp+500h] [rbp-2A8h] BYREF
  __int64 v42; // [rsp+6A0h] [rbp-108h]
  char v43; // [rsp+6B1h] [rbp-F7h]
  __int64 v44; // [rsp+750h] [rbp-58h] BYREF
  __int64 v45; // [rsp+758h] [rbp-50h]
  int v46; // [rsp+768h] [rbp-40h]

  v1 = this;
  v23 = this;
  web::http::client::http_client_config::http_client_config((web::http::client::http_client_config *)v41);
  web::details::uri_components::uri_components((web::details::uri_components *)v40);
  v33 = 0;
  v34 = 0;
  v35 = 7;
  LOWORD(v33) = 0;
  v2 = std::_String_val<std::_Simple_types<char>>::_Myptr((char *)v1 + 240);
  v3 = LPA::Util::ConvertUtf8ToUtf16(v2, &v33);
  v42 = 60000000;
  v43 = 0;
  v46 |= 0x100u;
  if ( *(_OWORD *)&GUID_NULL != *((_OWORD *)v1 + 63) )
  {
    memset_0(v37, 0, 0xE8u);
    v37[0] = 65538;
    v37[53] = 1;
    v38 = *((_OWORD *)v1 + 63);
    if ( v44 != v45 )
      v45 = v44;
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(&v44, v37, 232);
  }
  if ( v3 >= 0 )
  {
    if ( !(unsigned __int8)web::uri::validate(&v33) )
      v3 = -2147024809;
    if ( v3 >= 0 )
    {
      v4 = web::uri::uri(v39, &v33);
      web::details::uri_components::uri_components(
        (web::details::uri_components *)v37,
        (const struct web::details::uri_components *)(v4 + 32));
      web::details::uri_components::operator=(v40, v37);
      web::details::uri_components::~uri_components((web::details::uri_components *)v37);
      web::uri::~uri((web::uri *)v39);
      if ( !(unsigned __int8)std::wstring::_Equal(v40, L"https") )
      {
        std::operator+<unsigned short>(&pProxyConfig, L"https://", &v33);
        if ( (unsigned __int8)web::uri::validate(&pProxyConfig) )
        {
          v5 = web::uri::uri(v39, &pProxyConfig);
          web::details::uri_components::uri_components(
            (web::details::uri_components *)v37,
            (const struct web::details::uri_components *)(v5 + 32));
          web::details::uri_components::operator=(v40, v37);
          web::details::uri_components::~uri_components((web::details::uri_components *)v37);
          web::uri::~uri((web::uri *)v39);
        }
        else
        {
          v3 = -2147024809;
        }
        std::wstring::_Tidy_deallocate(&pProxyConfig);
      }
    }
  }
  v21 = 0;
  if ( !(unsigned int)PersistentRegPathGetDWORD(38, 0, L"ProxySettingsPerUser", &v21) && !v21 )
  {
    *((_BYTE *)v1 + 1040) = 1;
    goto LABEL_37;
  }
  v24 = -1;
  v6 = (_QWORD *)*((_QWORD *)v1 + 16);
  if ( v6 && *v6 )
  {
    try
    {
      v7 = wil::impersonate_token(&v20, **((_QWORD **)v1 + 16));
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::operator=(
        &v24,
        v7);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v20);
    }
    catch ( const std::exception *v28 )
    {
      v20 = -2147418113;
      if ( (unsigned int)CallbackContext <= 3 )
      {
        v16 = v23;
      }
      else
      {
        v31 = (LPA::Lpd *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v28 + 8LL))(v28);
        LOWORD(v32) = 1024;
        v16 = v23;
        v17 = (_QWORD *)*((_QWORD *)v23 + 16);
        v25 = *v17;
        v26 = v17;
        v27 = "LPA::Lpd::DownloadInstance::InitializeHttpClient";
        v22 = (web::http::client::http_client *)"LpaServiceLpd";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>>(
          v25,
          (unsigned int)&unk_18012FE10,
          v18,
          v19,
          (__int64)&v22,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v31);
      }
      std::weak_ptr<LPA::Lpd::DownloadInstance>::lock((char *)v16 + 32, &v31);
      if ( v31 )
        LPA::Lpd::InvalidateClientToken(v31);
      if ( v32 )
        std::_Ref_count_base::_Decref(v32);
      v3 = v20;
      v1 = v23;
    }
  }
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
  {
    if ( pProxyConfig.fAutoDetect || pProxyConfig.lpszAutoConfigUrl )
    {
      *((_BYTE *)v1 + 1041) = 1;
    }
    else
    {
      if ( !pProxyConfig.lpszProxy )
      {
LABEL_34:
        if ( pProxyConfig.lpszProxyBypass )
          GlobalFree(pProxyConfig.lpszProxyBypass);
        goto LABEL_36;
      }
      *((_BYTE *)v1 + 1042) = 1;
      web::uri::uri((web::uri *)v37);
      std::wstring::wstring(v36, pProxyConfig.lpszProxy);
      if ( !wcsncmp_0(pProxyConfig.lpszProxy, L"http", 4u) )
      {
        v9 = web::uri::uri(v39, v36);
        web::uri::operator=(v37, v9);
        web::uri::~uri((web::uri *)v39);
      }
      else
      {
        std::operator+<unsigned short>(&v31, L"http://", v36);
        if ( (unsigned __int8)web::uri::validate(&v31) )
        {
          v8 = web::uri::uri(v39, &v31);
          web::uri::operator=(v37, v8);
          web::uri::~uri((web::uri *)v39);
        }
        std::wstring::_Tidy_deallocate(&v31);
      }
      try
      {
        v10 = web::uri::uri((web::uri *)v39, (const struct web::uri *)v37);
        v11 = web::web_proxy::web_proxy(v29, v10);
        web::http::client::http_client_config::set_proxy(v41, v11);
      }
      catch ( web::uri_exception )
      {
        v20 = -2147024809;
        v1 = v23;
        v3 = -2147024809;
      }
      catch ( std::exception )
      {
        v20 = -2147418113;
        v1 = v23;
        v3 = -2147418113;
      }
      std::wstring::_Tidy_deallocate(v36);
      web::uri::~uri((web::uri *)v37);
    }
    if ( pProxyConfig.lpszProxy )
      GlobalFree(pProxyConfig.lpszProxy);
    if ( pProxyConfig.lpszAutoConfigUrl )
      GlobalFree(pProxyConfig.lpszAutoConfigUrl);
    goto LABEL_34;
  }
LABEL_36:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v24);
LABEL_37:
  if ( v3 >= 0 )
  {
    try
    {
      v12 = (const struct web::uri *)web::uri_builder::to_uri(v40, v39);
      v22 = (web::http::client::http_client *)operator new(0x10u);
      v13 = web::http::client::http_client::http_client(
              v22,
              v12,
              (const struct web::http::client::http_client_config *)v41);
      v22 = 0;
      v14 = *((_QWORD *)v1 + 12);
      *((_QWORD *)v1 + 12) = v13;
      if ( v14 )
        std::default_delete<web::http::client::http_client>::operator()();
      std::unique_ptr<web::http::client::http_client>::~unique_ptr<web::http::client::http_client>(&v22);
      web::uri::~uri((web::uri *)v39);
    }
    catch ( web::uri_exception )
    {
      v20 = -2147024809;
      v3 = -2147024809;
    }
    catch ( std::exception )
    {
      v20 = -2147418113;
      v3 = -2147418113;
    }
  }
  std::wstring::_Tidy_deallocate(&v33);
  web::details::uri_components::~uri_components((web::details::uri_components *)v40);
  web::http::client::http_client_config::~http_client_config((web::http::client::http_client_config *)v41);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800b089c  push    rbx
0x1800b089e  push    rsi
0x1800b089f  push    rdi
0x1800b08a0  push    r14
0x1800b08a2  sub     rsp, 788h
0x1800b08a9  mov     rax, cs:__security_cookie
0x1800b08b0  xor     rax, rsp
0x1800b08b3  mov     [rsp+7A8h+var_38], rax
0x1800b08bb  mov     rsi, rcx
0x1800b08be  mov     [rsp+7A8h+var_740], rcx
0x1800b08c3  xor     ebx, ebx
0x1800b08c5  lea     rcx, [rsp+7A8h+var_2A8]; this
0x1800b08cd  call    ??0http_client_config@client@http@web@@QEAA@XZ; web::http::client::http_client_config::http_client_config(void)
0x1800b08d2  nop
0x1800b08d3  lea     rcx, [rsp+7A8h+var_378]; this
0x1800b08db  call    ??0uri_components@details@web@@QEAA@XZ; web::details::uri_components::uri_components(void)
0x1800b08e0  nop
0x1800b08e1  xorps   xmm0, xmm0
0x1800b08e4  movups  [rsp+7A8h+var_5A0], xmm0
0x1800b08ec  mov     [rsp+7A8h+var_590], rbx
0x1800b08f4  mov     [rsp+7A8h+var_588], 7
0x1800b0900  mov     word ptr [rsp+7A8h+var_5A0], bx
0x1800b0908  lea     rcx, [rsi+0F0h]
0x1800b090f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800b0914  lea     rdx, [rsp+7A8h+var_5A0]
0x1800b091c  mov     rcx, rax
0x1800b091f  call    ?ConvertUtf8ToUtf16@Util@LPA@@YAJPEBDAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@4@@Z; LPA::Util::ConvertUtf8ToUtf16(char const *,std::wstring &,std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>> *)
0x1800b0924  mov     edi, eax
0x1800b0926  mov     [rsp+7A8h+var_108], 3938700h
0x1800b0932  mov     [rsp+7A8h+var_F7], bl
0x1800b0939  bts     [rsp+7A8h+var_40], 8
0x1800b0942  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x1800b0949  cmp     rcx, [rsi+3F0h]
0x1800b0950  jnz     short loc_1800B0962
0x1800b0952  mov     rcx, qword ptr cs:GUID_NULL.Data4
0x1800b0959  cmp     rcx, [rsi+3F8h]
0x1800b0960  jz      short loc_1800B09D2
0x1800b0962  mov     r14d, 0E8h
0x1800b0968  mov     r8d, r14d; Size
0x1800b096b  xor     edx, edx; Val
0x1800b096d  lea     rcx, [rsp+7A8h+var_558]; void *
0x1800b0975  call    memset_0
0x1800b097a  mov     [rsp+7A8h+var_558], 10002h
0x1800b0985  mov     [rsp+7A8h+var_484], 1
0x1800b0990  movups  xmm0, xmmword ptr [rsi+3F0h]
0x1800b0997  movdqu  [rsp+7A8h+var_480], xmm0
0x1800b09a0  mov     rax, [rsp+7A8h+var_58]
0x1800b09a8  cmp     rax, [rsp+7A8h+var_50]
0x1800b09b0  jz      short loc_1800B09BA
0x1800b09b2  mov     [rsp+7A8h+var_50], rax
0x1800b09ba  mov     r8, r14
0x1800b09bd  lea     rdx, [rsp+7A8h+var_558]
0x1800b09c5  lea     rcx, [rsp+7A8h+var_58]
0x1800b09cd  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x1800b09d2  test    edi, edi
0x1800b09d4  js      loc_1800B0B05
0x1800b09da  lea     rcx, [rsp+7A8h+var_5A0]
0x1800b09e2  call    ?validate@uri@web@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::validate(std::wstring const &)
0x1800b09e7  mov     r14d, 80070057h
0x1800b09ed  test    al, al
0x1800b09ef  cmovz   edi, r14d
0x1800b09f3  test    edi, edi
0x1800b09f5  js      loc_1800B0B05
0x1800b09fb  lea     rdx, [rsp+7A8h+var_5A0]
0x1800b0a03  lea     rcx, [rsp+7A8h+var_468]
0x1800b0a0b  call    ??0uri@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::uri(std::wstring const &)
0x1800b0a10  nop
0x1800b0a11  lea     rdx, [rax+20h]; struct web::details::uri_components *
0x1800b0a15  lea     rcx, [rsp+7A8h+var_558]; this
0x1800b0a1d  call    ??0uri_components@details@web@@QEAA@AEBU012@@Z; web::details::uri_components::uri_components(web::details::uri_components const &)
0x1800b0a22  lea     rdx, [rsp+7A8h+var_558]
0x1800b0a2a  lea     rcx, [rsp+7A8h+var_378]
0x1800b0a32  call    ??4uri_components@details@web@@QEAAAEAU012@$$QEAU012@@Z; web::details::uri_components::operator=(web::details::uri_components &&)
0x1800b0a37  lea     rcx, [rsp+7A8h+var_558]; this
0x1800b0a3f  call    ??1uri_components@details@web@@QEAA@XZ; web::details::uri_components::~uri_components(void)
0x1800b0a44  nop
0x1800b0a45  lea     rcx, [rsp+7A8h+var_468]; this
0x1800b0a4d  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x1800b0a52  lea     rdx, aHttps_0; "https"
0x1800b0a59  lea     rcx, [rsp+7A8h+var_378]
0x1800b0a61  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x1800b0a66  test    al, al
0x1800b0a68  jnz     loc_1800B0B05
0x1800b0a6e  lea     r8, [rsp+7A8h+var_5A0]
0x1800b0a76  lea     rdx, aHttps; "https://"
0x1800b0a7d  lea     rcx, [rsp+7A8h+pProxyConfig]
0x1800b0a85  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800b0a8a  nop
0x1800b0a8b  lea     rcx, [rsp+7A8h+pProxyConfig]
0x1800b0a93  call    ?validate@uri@web@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::validate(std::wstring const &)
0x1800b0a98  test    al, al
0x1800b0a9a  jz      short loc_1800B0AF5
0x1800b0a9c  lea     rdx, [rsp+7A8h+pProxyConfig]
0x1800b0aa4  lea     rcx, [rsp+7A8h+var_468]
0x1800b0aac  call    ??0uri@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::uri(std::wstring const &)
0x1800b0ab1  nop
0x1800b0ab2  lea     rdx, [rax+20h]; struct web::details::uri_components *
0x1800b0ab6  lea     rcx, [rsp+7A8h+var_558]; this
0x1800b0abe  call    ??0uri_components@details@web@@QEAA@AEBU012@@Z; web::details::uri_components::uri_components(web::details::uri_components const &)
0x1800b0ac3  lea     rdx, [rsp+7A8h+var_558]
0x1800b0acb  lea     rcx, [rsp+7A8h+var_378]
0x1800b0ad3  call    ??4uri_components@details@web@@QEAAAEAU012@$$QEAU012@@Z; web::details::uri_components::operator=(web::details::uri_components &&)
0x1800b0ad8  lea     rcx, [rsp+7A8h+var_558]; this
0x1800b0ae0  call    ??1uri_components@details@web@@QEAA@XZ; web::details::uri_components::~uri_components(void)
0x1800b0ae5  nop
0x1800b0ae6  lea     rcx, [rsp+7A8h+var_468]; this
0x1800b0aee  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x1800b0af3  jmp     short loc_1800B0AF8
0x1800b0af5  mov     edi, r14d
0x1800b0af8  lea     rcx, [rsp+7A8h+pProxyConfig]
0x1800b0b00  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b0b05  mov     [rsp+7A8h+var_750], ebx
0x1800b0b09  lea     r9, [rsp+7A8h+var_750]
0x1800b0b0e  lea     r8, aProxysettingsp; "ProxySettingsPerUser"
0x1800b0b15  xor     edx, edx
0x1800b0b17  lea     ecx, [rdx+26h]
0x1800b0b1a  call    cs:__imp_PersistentRegPathGetDWORD
0x1800b0b20  test    eax, eax
0x1800b0b22  jnz     short loc_1800B0B36
0x1800b0b24  cmp     [rsp+7A8h+var_750], ebx
0x1800b0b28  jnz     short loc_1800B0B36
0x1800b0b2a  mov     byte ptr [rsi+410h], 1
0x1800b0b31  jmp     loc_1800B0D72
0x1800b0b36  mov     [rsp+7A8h+var_738], 0FFFFFFFFFFFFFFFFh
0x1800b0b3f  mov     rax, [rsi+80h]
0x1800b0b46  test    rax, rax
0x1800b0b49  jz      short loc_1800B0B89
0x1800b0b4b  cmp     [rax], rbx
0x1800b0b4e  jz      short loc_1800B0B89
0x1800b0b50  mov     rdx, [rsi+80h]
0x1800b0b57  mov     rdx, [rdx]
0x1800b0b5a  lea     rcx, [rsp+7A8h+var_758]
0x1800b0b5f  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1800b0b64  mov     rdx, rax
0x1800b0b67  lea     rcx, [rsp+7A8h+var_738]
0x1800b0b6c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &&)
0x1800b0b71  lea     rcx, [rsp+7A8h+var_758]
0x1800b0b76  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800b0b7b  nop
0x1800b0b7c  jmp     short loc_1800B0B89
0x1800b0b7e  xor     ebx, ebx
0x1800b0b80  mov     edi, [rsp+7A8h+var_758]
0x1800b0b84  mov     rsi, [rsp+7A8h+var_740]
0x1800b0b89  xorps   xmm0, xmm0
0x1800b0b8c  movups  xmmword ptr [rsp+7A8h+pProxyConfig.fAutoDetect], xmm0
0x1800b0b94  movups  xmmword ptr [rsp+7A8h+pProxyConfig.lpszProxy], xmm0
0x1800b0b9c  lea     rcx, [rsp+7A8h+pProxyConfig]; pProxyConfig
0x1800b0ba4  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800b0baa  test    eax, eax
0x1800b0bac  jz      loc_1800B0D68
0x1800b0bb2  cmp     [rsp+7A8h+pProxyConfig.fAutoDetect], ebx
0x1800b0bb9  jnz     loc_1800B0D27
0x1800b0bbf  cmp     [rsp+7A8h+pProxyConfig.lpszAutoConfigUrl], rbx
0x1800b0bc7  jnz     loc_1800B0D27
0x1800b0bcd  cmp     [rsp+7A8h+pProxyConfig.lpszProxy], rbx
0x1800b0bd5  jz      loc_1800B0D54
0x1800b0bdb  mov     byte ptr [rsi+412h], 1
0x1800b0be2  lea     rcx, [rsp+7A8h+var_558]; this
0x1800b0bea  call    ??0uri@web@@QEAA@XZ; web::uri::uri(void)
0x1800b0bef  nop
0x1800b0bf0  mov     rdx, [rsp+7A8h+pProxyConfig.lpszProxy]
0x1800b0bf8  lea     rcx, [rsp+7A8h+var_580]
0x1800b0c00  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b0c05  nop
0x1800b0c06  mov     r8d, 4; MaxCount
0x1800b0c0c  lea     rdx, aHttp_0; "http"
0x1800b0c13  mov     rcx, [rsp+7A8h+pProxyConfig.lpszProxy]; String1
0x1800b0c1b  call    wcsncmp_0
0x1800b0c20  test    eax, eax
0x1800b0c22  jz      short loc_1800B0C94
0x1800b0c24  lea     r8, [rsp+7A8h+var_580]
0x1800b0c2c  lea     rdx, aHttp; "http://"
0x1800b0c33  lea     rcx, [rsp+7A8h+var_5C0]
0x1800b0c3b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800b0c40  nop
0x1800b0c41  lea     rcx, [rsp+7A8h+var_5C0]
0x1800b0c49  call    ?validate@uri@web@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::validate(std::wstring const &)
0x1800b0c4e  test    al, al
0x1800b0c50  jz      short loc_1800B0C85
0x1800b0c52  lea     rdx, [rsp+7A8h+var_5C0]
0x1800b0c5a  lea     rcx, [rsp+7A8h+var_468]
0x1800b0c62  call    ??0uri@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::uri(std::wstring const &)
0x1800b0c67  mov     rdx, rax
0x1800b0c6a  lea     rcx, [rsp+7A8h+var_558]
0x1800b0c72  call    ??4uri@web@@QEAAAEAV01@$$QEAV01@@Z; web::uri::operator=(web::uri &&)
0x1800b0c77  lea     rcx, [rsp+7A8h+var_468]; this
0x1800b0c7f  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x1800b0c84  nop
0x1800b0c85  lea     rcx, [rsp+7A8h+var_5C0]
0x1800b0c8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b0c92  jmp     short loc_1800B0CC7
0x1800b0c94  lea     rdx, [rsp+7A8h+var_580]
0x1800b0c9c  lea     rcx, [rsp+7A8h+var_468]
0x1800b0ca4  call    ??0uri@web@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::uri::uri(std::wstring const &)
0x1800b0ca9  mov     rdx, rax
0x1800b0cac  lea     rcx, [rsp+7A8h+var_558]
0x1800b0cb4  call    ??4uri@web@@QEAAAEAV01@$$QEAV01@@Z; web::uri::operator=(web::uri &&)
0x1800b0cb9  lea     rcx, [rsp+7A8h+var_468]; this
0x1800b0cc1  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x1800b0cc6  nop
0x1800b0cc7  lea     rdx, [rsp+7A8h+var_558]; struct web::uri *
0x1800b0ccf  lea     rcx, [rsp+7A8h+var_468]; this
0x1800b0cd7  call    ??0uri@web@@QEAA@AEBV01@@Z; web::uri::uri(web::uri const &)
0x1800b0cdc  mov     rdx, rax
0x1800b0cdf  lea     rcx, [rsp+7A8h+var_710]
0x1800b0ce7  call    ??0web_proxy@web@@QEAA@Vuri@1@@Z; web::web_proxy::web_proxy(web::uri)
0x1800b0cec  mov     rdx, rax
0x1800b0cef  lea     rcx, [rsp+7A8h+var_2A8]
0x1800b0cf7  call    ?set_proxy@http_client_config@client@http@web@@QEAAXVweb_proxy@4@@Z; web::http::client::http_client_config::set_proxy(web::web_proxy)
0x1800b0cfc  nop
0x1800b0cfd  jmp     short loc_1800B0D0A
0x1800b0cff  mov     rsi, [rsp+7A8h+var_740]
0x1800b0d04  mov     edi, [rsp+7A8h+var_758]
0x1800b0d08  xor     ebx, ebx
0x1800b0d0a  lea     rcx, [rsp+7A8h+var_580]
0x1800b0d12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b0d17  nop
0x1800b0d18  lea     rcx, [rsp+7A8h+var_558]; this
0x1800b0d20  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x1800b0d25  jmp     short loc_1800B0D2E
0x1800b0d27  mov     byte ptr [rsi+411h], 1
0x1800b0d2e  mov     rcx, [rsp+7A8h+pProxyConfig.lpszProxy]; hMem
0x1800b0d36  test    rcx, rcx
0x1800b0d39  jz      short loc_1800B0D41
0x1800b0d3b  call    cs:__imp_GlobalFree
0x1800b0d41  mov     rcx, [rsp+7A8h+pProxyConfig.lpszAutoConfigUrl]; hMem
0x1800b0d49  test    rcx, rcx
0x1800b0d4c  jz      short loc_1800B0D54
0x1800b0d4e  call    cs:__imp_GlobalFree
0x1800b0d54  mov     rcx, [rsp+7A8h+pProxyConfig.lpszProxyBypass]; hMem
0x1800b0d5c  test    rcx, rcx
0x1800b0d5f  jz      short loc_1800B0D68
0x1800b0d61  call    cs:__imp_GlobalFree
0x1800b0d67  nop
0x1800b0d68  lea     rcx, [rsp+7A8h+var_738]
0x1800b0d6d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800b0d72  test    edi, edi
0x1800b0d74  js      short loc_1800B0DE7
0x1800b0d76  lea     rdx, [rsp+7A8h+var_468]
0x1800b0d7e  lea     rcx, [rsp+7A8h+var_378]
0x1800b0d86  call    ?to_uri@uri_builder@web@@QEBA?AVuri@2@XZ; web::uri_builder::to_uri(void)
0x1800b0d8b  mov     r14, rax
0x1800b0d8e  mov     ecx, 10h; Size
0x1800b0d93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b0d98  mov     [rsp+7A8h+var_748], rax
0x1800b0d9d  lea     r8, [rsp+7A8h+var_2A8]; struct web::http::client::http_client_config *
0x1800b0da5  mov     rdx, r14; struct web::uri *
0x1800b0da8  mov     rcx, rax; this
0x1800b0dab  call    ??0http_client@client@http@web@@QEAA@AEBVuri@3@AEBVhttp_client_config@123@@Z; web::http::client::http_client::http_client(web::uri const &,web::http::client::http_client_config const &)
0x1800b0db0  nop
0x1800b0db1  mov     [rsp+7A8h+var_748], rbx
0x1800b0db6  mov     rdx, [rsi+60h]
0x1800b0dba  mov     [rsi+60h], rax
0x1800b0dbe  test    rdx, rdx
0x1800b0dc1  jz      short loc_1800B0DC8
0x1800b0dc3  call    ??R?$default_delete@Vhttp_client@client@http@web@@@std@@QEBAXPEAVhttp_client@client@http@web@@@Z; std::default_delete<web::http::client::http_client>::operator()(web::http::client::http_client *)
0x1800b0dc8  lea     rcx, [rsp+7A8h+var_748]
0x1800b0dcd  call    ??1?$unique_ptr@Vhttp_client@client@http@web@@U?$default_delete@Vhttp_client@client@http@web@@@std@@@std@@QEAA@XZ; std::unique_ptr<web::http::client::http_client>::~unique_ptr<web::http::client::http_client>(void)
0x1800b0dd2  nop
0x1800b0dd3  lea     rcx, [rsp+7A8h+var_468]; this
0x1800b0ddb  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x1800b0de0  nop
0x1800b0de1  jmp     short loc_1800B0DE7
0x1800b0de3  mov     edi, [rsp+7A8h+var_758]
0x1800b0de7  lea     rcx, [rsp+7A8h+var_5A0]
0x1800b0def  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b0df4  nop
0x1800b0df5  lea     rcx, [rsp+7A8h+var_378]; this
0x1800b0dfd  call    ??1uri_components@details@web@@QEAA@XZ; web::details::uri_components::~uri_components(void)
0x1800b0e02  nop
0x1800b0e03  lea     rcx, [rsp+7A8h+var_2A8]; this
0x1800b0e0b  call    ??1http_client_config@client@http@web@@UEAA@XZ; web::http::client::http_client_config::~http_client_config(void)
0x1800b0e10  mov     eax, edi
0x1800b0e12  mov     rcx, [rsp+7A8h+var_38]
0x1800b0e1a  xor     rcx, rsp; StackCookie
0x1800b0e1d  call    __security_check_cookie
0x1800b0e22  add     rsp, 788h
0x1800b0e29  pop     r14
0x1800b0e2b  pop     rdi
0x1800b0e2c  pop     rsi
0x1800b0e2d  pop     rbx
0x1800b0e2e  retn
```
