# shared::OneCoreAccountProvider::GetWebAccountFromTokenBroker(std::shared_ptr<ICDPAccount> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800998c4`
- end: `0x180099f0b`
- name: `?GetWebAccountFromTokenBroker@OneCoreAccountProvider@shared@@AEAA?AV?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@AEBV?$shared_ptr@VICDPAccount@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `1607`
- prototype: ``
- caller_count: `3`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x18009fa94`
- `0x180161bc8`
- `0x180163810`

## callees

- `0x180009770`
- `0x180009b48`
- `0x180009b94`
- `0x18000acdc`
- `0x18000d02c`
- `0x18000d098`
- `0x180010ee0`
- `0x18001ce80`
- `0x180030190`
- `0x18005ade0`
- `0x1800624cc`
- `0x18007e71c`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180098b50`
- `0x180099438`
- `0x18009952c`
- `0x1800998c4`
- `0x18009a450`
- `0x18009dd54`
- `0x18009ded4`
- `0x18009e080`
- `0x18011d5d0`
- `0x18011d808`
- `0x18011d8c4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099b74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099b74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180099c96`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180099eee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180099f04`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180099c96`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180099eee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180099f04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099c10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099e2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099c10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099c3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099e2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099e3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099dd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099dd6`

## string_xrefs

- `0x180099b9d`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18009990f`: `GetWebAccountFromTokenBrokerActivity`
- `0x180099ae5`: `class Microsoft::WRL::ComPtr<struct Windows::Security::Credentials::IWebAccount> __cdecl shared::OneCoreAccountProvider::GetWebAccountFromTokenBroker(const class std::shared_ptr<class ICDPAccount> &,const class std::basic_string<unsigned short,struct std::char_traits<unsigned short>,class std::allocator<unsigned short> > &)`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 *__fastcall shared::OneCoreAccountProvider::GetWebAccountFromTokenBroker(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3,
        const WCHAR *a4)
{
  __int64 v8; // rdx
  unsigned __int16 v9; // r15
  __int64 v10; // rax
  __int64 v11; // rax
  _BYTE *v12; // r8
  __int64 *v13; // r15
  __int64 v14; // r13
  const WCHAR *v15; // rdx
  unsigned __int64 v16; // rdi
  int v17; // eax
  __int64 v18; // rax
  int v19; // ebx
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  const WCHAR *v26; // rcx
  __int64 v27; // rdi
  void (__fastcall *v28)(__int64, HSTRING *); // rbx
  __int64 v29; // rdi
  void (__fastcall *v30)(__int64, HSTRING *); // rbx
  PCWSTR *v31; // rax
  __int64 *v32; // r15
  __int64 v33; // r13
  const WCHAR *v34; // rdx
  unsigned __int64 v35; // rdi
  unsigned __int64 v36; // r9
  const WCHAR *v37; // rdx
  __int64 v38; // rbx
  int v39; // eax
  __int64 v40; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v42; // rax
  _QWORD *v43; // rax
  __int64 v44; // rcx
  const WCHAR *v46; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+38h] [rbp-C8h] BYREF
  int v48; // [rsp+40h] [rbp-C0h]
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v50; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR *CurrentThreadId; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v53[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER v55; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-38h]
  _BYTE hstringHeader[32]; // [rsp+D0h] [rbp-30h] BYREF
  PCWSTR sourceString[2]; // [rsp+F0h] [rbp-10h] BYREF
  __m128i si128; // [rsp+100h] [rbp+0h]
  _BYTE v60[128]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v61[42]; // [rsp+190h] [rbp+90h] BYREF

  v53[1] = a2;
  v48 = 0;
  LODWORD(v47) = 0;
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v61,
    "GetWebAccountFromTokenBrokerActivity",
    a3);
  v61[0] = &OneCoreAccountTelemetryProvider::GetWebAccountFromTokenBrokerActivity::`vftable';
  OneCoreAccountTelemetryProvider::GetWebAccountFromTokenBrokerActivity::StartActivity((OneCoreAccountTelemetryProvider::GetWebAccountFromTokenBrokerActivity *)v61);
  v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 24LL))(*a3);
  if ( (unsigned __int16)(v9 - 1) > 1u )
  {
    v55.Reserved.Reserved1 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v55.Reserved.Reserved2[8] = 1426;
    v10 = cdp::MakeException<std::invalid_argument,>(
            hstringHeader,
            v8,
            "WebAccount only available for MSA and AAD types");
    cdp::CdpThrow<std::invalid_argument>(&v55, v10);
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 32LL))(*a3);
  std::string::string(hstringHeader, v11);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v60);
  v12 = hstringHeader;
  if ( *(_QWORD *)&hstringHeader[24] > 0xFu )
    v12 = *(_BYTE **)hstringHeader;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v60,
    sourceString,
    v12,
    &v12[*(_QWORD *)&hstringHeader[16]]);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v60);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(hstringHeader);
  shared::OneCoreAccountProvider::GetWebAccountProviderFromAccountType(a1, &v51, v9);
  *a2 = 0;
  v48 = 15;
  if ( !*((_QWORD *)a4 + 2) )
  {
    v46 = 0;
    v13 = *(__int64 **)(a1 + 96);
    v14 = *v13;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    v15 = (const WCHAR *)sourceString;
    if ( si128.m128i_i64[1] > 7uLL )
      v15 = sourceString[0];
    *(_QWORD *)&hstringHeader[24] = 0;
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    a1 = 0xFFFFFFFFLL;
    if ( v16 <= 0xFFFFFFFF && (int)v16 + 1 >= (unsigned int)v16 )
    {
      Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)hstringHeader, v15, v16 + 1, v16);
      v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, const WCHAR **))(v14 + 80))(
              v13,
              v51,
              *(_QWORD *)&hstringHeader[24],
              &v46);
      if ( v17 < 0 )
      {
        v55.Reserved.Reserved1 = ".\\onecoreaccountprovider.cpp";
        *(_DWORD *)&v55.Reserved.Reserved2[8] = 1437;
        v18 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v55, (unsigned int)v17);
        cdp::CdpThrow<cdp::hresult_exception>(&v55, v18);
      }
      v47 = 30000;
      memset(hstringHeader, 0, sizeof(hstringHeader));
      std::string::_Construct<1,char const *>(
        hstringHeader,
        "class Microsoft::WRL::ComPtr<struct Windows::Security::Credentials::IWebAccount> __cdecl shared::OneCoreAccountP"
        "rovider::GetWebAccountFromTokenBroker(const class std::shared_ptr<class ICDPAccount> &,const class std::basic_st"
        "ring<unsigned short,struct std::char_traits<unsigned short>,class std::allocator<unsigned short> > &)",
        325);
      v19 = shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>,Windows::Security::Credentials::IWebAccount>(
              v46,
              hstringHeader,
              &v47,
              a2);
      LODWORD(v47) = v19;
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(hstringHeader);
      if ( v19 < 0 )
      {
        v55.Reserved.Reserved1 = ".\\onecoreaccountprovider.cpp";
        *(_DWORD *)&v55.Reserved.Reserved2[8] = 1440;
        v20 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v55, (unsigned int)v19);
        cdp::CdpThrow<cdp::hresult_exception>(&v55, v20);
      }
      if ( !*a2 )
      {
        v55.Reserved.Reserved1 = ".\\onecoreaccountprovider.cpp";
        *(_DWORD *)&v55.Reserved.Reserved2[8] = 1441;
        LODWORD(v47) = -2147023579;
        CurrentThreadId = (PCWSTR *)GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v21,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v47,
          (unsigned int)&v55,
          (__int64)&v55.Reserved.Reserved2[8],
          (__int64)&CurrentThreadId);
        v22 = cdp::ExceptionStackFromSourceLocationInfo(hstringHeader, &v55);
        v25 = cdp::ErrorCodeToString(2147943717LL, v23, v24, v22);
        ConnectedDevices::Exception::Exception(pExceptionObject, 2147943717LL, v25);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      v26 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v26 + 16LL))(v26);
      }
      goto LABEL_20;
    }
    RaiseException(0x80070216, 1u, 0, 0);
  }
  v32 = *(__int64 **)(a1 + 88);
  v33 = *v32;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  v34 = (const WCHAR *)sourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v34 = sourceString[0];
  *(_QWORD *)&hstringHeader[24] = 0;
  v35 = -1;
  v36 = -1;
  do
    ++v36;
  while ( v34[v36] );
  if ( v36 > 0xFFFFFFFF || (int)v36 + 1 < (unsigned int)v36 )
  {
LABEL_52:
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180099F0ALL);
  }
  Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)hstringHeader, v34, v36 + 1, v36);
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v37 = a4;
  else
    v37 = *(const WCHAR **)a4;
  v56 = 0;
  do
    ++v35;
  while ( v37[v35] );
  if ( v35 > 0xFFFFFFFF || (int)v35 + 1 < (unsigned int)v35 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_52;
  }
  v38 = *(_QWORD *)&hstringHeader[24];
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v55, v37, v35 + 1, v35);
  v39 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int64 *))(v33 + 88))(v32, v51, v56, v38, a2);
  if ( v39 < 0 )
  {
    v55.Reserved.Reserved1 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v55.Reserved.Reserved2[8] = 1448;
    v40 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v55, (unsigned int)v39);
    cdp::CdpThrow<cdp::hresult_exception>(&v55, v40);
  }
LABEL_20:
  v50 = 0;
  v27 = v51;
  v28 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 56LL);
  WindowsDeleteString(0);
  v50 = 0;
  v28(v27, &v50);
  string = 0;
  v29 = *a2;
  v30 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a2 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v30(v29, &string);
  v31 = sourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v31 = (PCWSTR *)sourceString[0];
  CurrentThreadId = v31;
  if ( *((_QWORD *)a4 + 2) )
  {
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
  }
  else
  {
    a4 = &pNodeName;
  }
  v46 = a4;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v42 = std::wstring::wstring(pExceptionObject, StringRawBuffer);
  v43 = (_QWORD *)EncryptString(hstringHeader, v42);
  if ( v43[3] > 7u )
    v43 = (_QWORD *)*v43;
  v53[0] = v43;
  v55.Reserved.Reserved1 = (PVOID)WindowsGetStringRawBuffer(v50, 0);
  OneCoreAccountTelemetryProvider::GetWebAccountFromTokenBrokerActivity::FindAccountForProvider<long &,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
    (unsigned int)v61,
    (unsigned int)&v47,
    (unsigned int)&v55,
    (unsigned int)v53,
    (__int64)&v46,
    (__int64)&CurrentThreadId);
  if ( *(_QWORD *)&hstringHeader[24] > 7u )
    std::_Deallocate<16>(*(_QWORD *)hstringHeader, 2LL * *(_QWORD *)&hstringHeader[24] + 2);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v50);
  v50 = 0;
  v44 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(sourceString[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(sourceString[0]) = 0;
  v61[0] = &OneCoreAccountTelemetryProvider::GetWebAccountFromTokenBrokerActivity::`vftable';
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v61);
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v61);
  return a2;
}

```

## disassembly

```asm
0x1800998c4  push    rbp
0x1800998c6  push    rbx
0x1800998c7  push    rsi
0x1800998c8  push    rdi
0x1800998c9  push    r12
0x1800998cb  push    r13
0x1800998cd  push    r14
0x1800998cf  push    r15
0x1800998d1  lea     rbp, [rsp-1F8h]
0x1800998d9  sub     rsp, 2F8h
0x1800998e0  mov     rax, cs:__security_cookie
0x1800998e7  xor     rax, rsp
0x1800998ea  mov     [rbp+230h+var_50], rax
0x1800998f1  mov     rsi, r9
0x1800998f4  mov     rdi, r8
0x1800998f7  mov     r14, rdx
0x1800998fa  mov     rbx, rcx
0x1800998fd  mov     [rsp+330h+var_2C0], rdx
0x180099902  xor     r12d, r12d
0x180099905  mov     [rsp+330h+var_2F0], r12d
0x18009990a  mov     dword ptr [rsp+330h+var_2F8], r12d
0x18009990f  lea     rdx, aGetwebaccountf; "GetWebAccountFromTokenBrokerActivity"
0x180099916  lea     rcx, [rbp+230h+var_1A0]
0x18009991d  call    ??0?$ActivityBase@VOneCoreAccountTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180099922  lea     rax, ??_7GetWebAccountFromTokenBrokerActivity@OneCoreAccountTelemetryProvider@@6B@; const OneCoreAccountTelemetryProvider::GetWebAccountFromTokenBrokerActivity::`vftable'
0x180099929  mov     [rbp+230h+var_1A0], rax
0x180099930  lea     rcx, [rbp+230h+var_1A0]; this
0x180099937  call    ?StartActivity@GetWebAccountFromTokenBrokerActivity@OneCoreAccountTelemetryProvider@@QEAAXXZ; OneCoreAccountTelemetryProvider::GetWebAccountFromTokenBrokerActivity::StartActivity(void)
0x18009993c  nop
0x18009993d  mov     rcx, [rdi]
0x180099940  mov     rax, [rcx]
0x180099943  mov     rax, [rax+18h]
0x180099947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009994c  movzx   r15d, ax
0x180099950  movzx   ecx, ax
0x180099953  lea     eax, [r12+1]
0x180099958  sub     cx, ax
0x18009995b  cmp     cx, ax
0x18009995e  jbe     short loc_180099990
0x180099960  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x180099967  mov     qword ptr [rbp+230h+var_280.Reserved], rax
0x18009996b  mov     dword ptr [rbp+230h+var_280.Reserved+8], 592h
0x180099972  lea     r8, aWebaccountOnly; "WebAccount only available for MSA and A"...
0x180099979  lea     rcx, [rbp+230h+hstringHeader]
0x18009997d  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180099982  nop
0x180099983  mov     rdx, rax
0x180099986  lea     rcx, [rbp+230h+var_280]
0x18009998a  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x180099990  mov     rcx, [rdi]
0x180099993  mov     rax, [rcx]
0x180099996  mov     rax, [rax+20h]
0x18009999a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009999f  mov     rdx, rax
0x1800999a2  lea     rcx, [rbp+230h+hstringHeader]
0x1800999a6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800999ab  nop
0x1800999ac  lea     rcx, [rbp+230h+var_220]
0x1800999b0  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800999b5  nop
0x1800999b6  lea     r8, [rbp+230h+hstringHeader]
0x1800999ba  cmp     qword ptr [rbp+230h+hstringHeader+18h], 0Fh
0x1800999bf  cmova   r8, qword ptr [rbp+230h+hstringHeader]
0x1800999c4  mov     r9, qword ptr [rbp+230h+hstringHeader+10h]
0x1800999c8  add     r9, r8
0x1800999cb  lea     rdx, [rbp+230h+sourceString]
0x1800999cf  lea     rcx, [rbp+230h+var_220]
0x1800999d3  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x1800999d8  nop
0x1800999d9  lea     rcx, [rbp+230h+var_220]
0x1800999dd  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800999e2  mov     [rsp+330h+var_2F0], 0Eh
0x1800999ea  lea     rcx, [rbp+230h+hstringHeader]; void *
0x1800999ee  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800999f3  movzx   r8d, r15w
0x1800999f7  lea     rdx, [rsp+330h+var_2D8]
0x1800999fc  mov     rcx, rbx
0x1800999ff  call    ?GetWebAccountProviderFromAccountType@OneCoreAccountProvider@shared@@AEAA?AV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@W4CDPAccountType@@@Z; shared::OneCoreAccountProvider::GetWebAccountProviderFromAccountType(CDPAccountType)
0x180099a04  nop
0x180099a05  mov     [r14], r12
0x180099a08  mov     [rsp+330h+var_2F0], 0Fh
0x180099a10  cmp     [rsi+10h], r12
0x180099a14  jnz     loc_180099C9D
0x180099a1a  mov     [rsp+330h+var_300], r12
0x180099a1f  mov     r15, [rbx+60h]
0x180099a23  mov     r13, [r15]
0x180099a26  lea     rcx, [rsp+330h+var_300]
0x180099a2b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180099a30  lea     rdx, [rbp+230h+sourceString]
0x180099a34  cmp     [rbp+230h+var_228], 7
0x180099a39  cmova   rdx, [rbp+230h+sourceString]; sourceString
0x180099a3e  mov     qword ptr [rbp+230h+hstringHeader+18h], r12
0x180099a42  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180099a46  inc     rdi
0x180099a49  cmp     [rdx+rdi*2], r12w
0x180099a4e  jnz     short loc_180099A46
0x180099a50  mov     ebx, 0FFFFFFFFh
0x180099a55  cmp     rdi, rbx
0x180099a58  ja      loc_180099C87
0x180099a5e  lea     r8d, [rdi+1]; unsigned int
0x180099a62  cmp     r8d, edi
0x180099a65  jb      loc_180099C87
0x180099a6b  mov     r9d, edi; unsigned int
0x180099a6e  lea     rcx, [rbp+230h+hstringHeader]; hstringHeader
0x180099a72  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180099a77  nop
0x180099a78  lea     r9, [rsp+330h+var_300]
0x180099a7d  mov     r8, qword ptr [rbp+230h+hstringHeader+18h]
0x180099a81  mov     rdx, [rsp+330h+var_2D8]
0x180099a86  mov     rcx, r15
0x180099a89  mov     rax, [r13+50h]
0x180099a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099a92  mov     r8d, eax
0x180099a95  test    eax, eax
0x180099a97  jns     short loc_180099AC7
0x180099a99  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x180099aa0  mov     qword ptr [rbp+230h+var_280.Reserved], rax
0x180099aa4  mov     dword ptr [rbp+230h+var_280.Reserved+8], 59Dh
0x180099aab  lea     rdx, [rbp+230h+var_280]
0x180099aaf  lea     rcx, [rsp+330h+pExceptionObject]
0x180099ab4  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x180099ab9  nop
0x180099aba  mov     rdx, rax
0x180099abd  lea     rcx, [rbp+230h+var_280]
0x180099ac1  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180099ac7  mov     [rsp+330h+var_2F8], 7530h
0x180099ad0  xorps   xmm0, xmm0
0x180099ad3  movups  xmmword ptr [rbp+230h+hstringHeader], xmm0
0x180099ad7  xorps   xmm1, xmm1
0x180099ada  movdqu  xmmword ptr [rbp+230h+hstringHeader+10h], xmm1
0x180099adf  mov     r8d, 145h
0x180099ae5  lea     rdx, aClassMicrosoft_1; "class Microsoft::WRL::ComPtr<struct Win"...
0x180099aec  lea     rcx, [rbp+230h+hstringHeader]
0x180099af0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180099af5  nop
0x180099af6  mov     r9, r14
0x180099af9  lea     r8, [rsp+330h+var_2F8]
0x180099afe  lea     rdx, [rbp+230h+hstringHeader]
0x180099b02  mov     rcx, [rsp+330h+var_300]
0x180099b07  call    ??$CancellableBlockingWRLCall@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@UIWebAccount@Credentials@Security@3@@shared@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@5@PEAPEAUIWebAccount@Credentials@Security@3@@Z; shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>,Windows::Security::Credentials::IWebAccount>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,std::string const &,std::chrono::duration<__int64,std::ratio<1,1000>> const &,Windows::Security::Credentials::IWebAccount * *)
0x180099b0c  mov     ebx, eax
0x180099b0e  mov     dword ptr [rsp+330h+var_2F8], eax
0x180099b12  lea     rcx, [rbp+230h+hstringHeader]; void *
0x180099b16  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180099b1b  test    ebx, ebx
0x180099b1d  jns     short loc_180099B50
0x180099b1f  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x180099b26  mov     qword ptr [rbp+230h+var_280.Reserved], rax
0x180099b2a  mov     dword ptr [rbp+230h+var_280.Reserved+8], 5A0h
0x180099b31  mov     r8d, ebx
0x180099b34  lea     rdx, [rbp+230h+var_280]
0x180099b38  lea     rcx, [rsp+330h+pExceptionObject]
0x180099b3d  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x180099b42  nop
0x180099b43  mov     rdx, rax
0x180099b46  lea     rcx, [rbp+230h+var_280]
0x180099b4a  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180099b50  cmp     [r14], r12
0x180099b53  jnz     loc_180099BE1
0x180099b59  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x180099b60  mov     qword ptr [rbp+230h+var_280.Reserved], rax
0x180099b64  mov     dword ptr [rbp+230h+var_280.Reserved+8], 5A1h
0x180099b6b  mov     ebx, 80070525h
0x180099b70  mov     dword ptr [rsp+330h+var_2F8], ebx
0x180099b74  call    cs:__imp_GetCurrentThreadId
0x180099b7a  mov     eax, eax
0x180099b7c  mov     [rsp+330h+var_2D0], rax
0x180099b81  lea     rax, [rsp+330h+var_2D0]
0x180099b86  mov     [rsp+330h+var_308], rax
0x180099b8b  lea     rax, [rbp+230h+var_280.Reserved+8]
0x180099b8f  mov     [rsp+330h+var_310], rax
0x180099b94  lea     r9, [rbp+230h+var_280]
0x180099b98  lea     r8, [rsp+330h+var_2F8]
0x180099b9d  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180099ba4  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180099ba9  lea     rdx, [rbp+230h+var_280]
0x180099bad  lea     rcx, [rbp+230h+hstringHeader]
0x180099bb1  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180099bb6  mov     r9, rax
0x180099bb9  mov     ecx, ebx
0x180099bbb  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180099bc0  mov     r8, rax
0x180099bc3  mov     edx, ebx
0x180099bc5  lea     rcx, [rsp+330h+pExceptionObject]
0x180099bca  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180099bcf  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180099bd6  lea     rcx, [rsp+330h+pExceptionObject]; pExceptionObject
0x180099bdb  call    _CxxThrowException_0
0x180099be1  mov     rcx, [rsp+330h+var_300]
0x180099be6  test    rcx, rcx
0x180099be9  jz      short loc_180099BFD
0x180099beb  mov     [rsp+330h+var_300], r12
0x180099bf0  mov     rax, [rcx]
0x180099bf3  mov     rax, [rax+10h]
0x180099bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099bfc  nop
0x180099bfd  mov     [rsp+330h+var_2E0], r12
0x180099c02  mov     rdi, [rsp+330h+var_2D8]
0x180099c07  mov     rax, [rdi]
0x180099c0a  mov     rbx, [rax+38h]
0x180099c0e  xor     ecx, ecx; string
0x180099c10  call    cs:__imp_WindowsDeleteString
0x180099c16  mov     [rsp+330h+var_2E0], r12
0x180099c1b  lea     rdx, [rsp+330h+var_2E0]
0x180099c20  mov     rcx, rdi
0x180099c23  mov     rax, rbx
0x180099c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c2b  mov     [rsp+330h+string], r12
0x180099c30  mov     rdi, [r14]
0x180099c33  mov     rax, [rdi]
0x180099c36  mov     rbx, [rax+38h]
0x180099c3a  xor     ecx, ecx; string
0x180099c3c  call    cs:__imp_WindowsDeleteString
0x180099c42  mov     [rsp+330h+string], r12
0x180099c47  lea     rdx, [rsp+330h+string]
0x180099c4c  mov     rcx, rdi
0x180099c4f  mov     rax, rbx
0x180099c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c57  lea     rax, [rbp+230h+sourceString]
0x180099c5b  cmp     [rbp+230h+var_228], 7
0x180099c60  cmova   rax, [rbp+230h+sourceString]
0x180099c65  mov     [rsp+330h+var_2D0], rax
0x180099c6a  cmp     [rsi+10h], r12
0x180099c6e  jz      loc_180099D8E
0x180099c74  cmp     qword ptr [rsi+18h], 7
0x180099c79  jbe     loc_180099D95
0x180099c7f  mov     rsi, [rsi]
0x180099c82  jmp     loc_180099D95
0x180099c87  xor     r9d, r9d; lpArguments
0x180099c8a  xor     r8d, r8d; nNumberOfArguments
0x180099c8d  lea     edx, [r9+1]; dwExceptionFlags
0x180099c91  mov     ecx, 80070216h; dwExceptionCode
0x180099c96  call    cs:__imp_RaiseException
0x180099c9c  nop
0x180099c9d  mov     r15, [rbx+58h]
0x180099ca1  mov     r13, [r15]
0x180099ca4  mov     rcx, r14
0x180099ca7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180099cac  lea     rdx, [rbp+230h+sourceString]
0x180099cb0  cmp     [rbp+230h+var_228], 7
0x180099cb5  cmova   rdx, [rbp+230h+sourceString]; sourceString
0x180099cba  mov     qword ptr [rbp+230h+hstringHeader+18h], r12
0x180099cbe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180099cc2  mov     r9, rdi
0x180099cc5  inc     r9; unsigned int
0x180099cc8  cmp     [rdx+r9*2], r12w
0x180099ccd  jnz     short loc_180099CC5
0x180099ccf  mov     ebx, 0FFFFFFFFh
0x180099cd4  cmp     r9, rbx
0x180099cd7  ja      loc_180099EF5
0x180099cdd  lea     r8d, [r9+1]; unsigned int
0x180099ce1  cmp     r8d, r9d
0x180099ce4  jb      loc_180099EF5
0x180099cea  lea     rcx, [rbp+230h+hstringHeader]; hstringHeader
0x180099cee  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180099cf3  nop
0x180099cf4  cmp     qword ptr [rsi+18h], 7
0x180099cf9  jbe     short loc_180099D00
0x180099cfb  mov     rdx, [rsi]
0x180099cfe  jmp     short loc_180099D03
0x180099d00  mov     rdx, rsi; sourceString
0x180099d03  mov     [rbp+230h+var_268], r12
0x180099d07  inc     rdi
0x180099d0a  cmp     [rdx+rdi*2], r12w
0x180099d0f  jnz     short loc_180099D07
0x180099d11  cmp     rdi, rbx
0x180099d14  ja      loc_180099EDF
0x180099d1a  lea     r8d, [rdi+1]; unsigned int
0x180099d1e  cmp     r8d, edi
0x180099d21  jb      loc_180099EDF
0x180099d27  mov     rbx, qword ptr [rbp+230h+hstringHeader+18h]
0x180099d2b  mov     r9d, edi; unsigned int
0x180099d2e  lea     rcx, [rbp+230h+var_280]; hstringHeader
0x180099d32  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180099d37  nop
0x180099d38  mov     [rsp+330h+var_310], r14
0x180099d3d  mov     r9, rbx
0x180099d40  mov     r8, [rbp+230h+var_268]
0x180099d44  mov     rdx, [rsp+330h+var_2D8]
0x180099d49  mov     rcx, r15
0x180099d4c  mov     rax, [r13+58h]
0x180099d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099d55  mov     r8d, eax
0x180099d58  test    eax, eax
0x180099d5a  jns     loc_180099BFD
0x180099d60  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x180099d67  mov     qword ptr [rbp+230h+var_280.Reserved], rax
0x180099d6b  mov     dword ptr [rbp+230h+var_280.Reserved+8], 5A8h
0x180099d72  lea     rdx, [rbp+230h+var_280]
0x180099d76  lea     rcx, [rsp+330h+pExceptionObject]
0x180099d7b  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x180099d80  nop
0x180099d81  mov     rdx, rax
0x180099d84  lea     rcx, [rbp+230h+var_280]
0x180099d88  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180099d8e  lea     rsi, pNodeName
0x180099d95  mov     [rsp+330h+var_300], rsi
0x180099d9a  xor     edx, edx; length
0x180099d9c  mov     rcx, [rsp+330h+string]; string
0x180099da1  call    cs:__imp_WindowsGetStringRawBuffer
  ... truncated ...
```
