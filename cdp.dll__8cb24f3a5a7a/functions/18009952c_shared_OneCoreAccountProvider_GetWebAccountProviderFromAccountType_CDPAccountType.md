# shared::OneCoreAccountProvider::GetWebAccountProviderFromAccountType(CDPAccountType)

- ea: `0x18009952c`
- end: `0x1800998bc`
- name: `?GetWebAccountProviderFromAccountType@OneCoreAccountProvider@shared@@AEAA?AV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@W4CDPAccountType@@@Z`
- size: `912`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800998c4`

## callees

- `0x180009b48`
- `0x1800113bc`
- `0x18001ce80`
- `0x180030190`
- `0x1800624cc`
- `0x18007e71c`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18009952c`
- `0x1800a5aa8`
- `0x1800a6ff8`
- `0x1800b06c0`
- `0x1800d9ff4`
- `0x180114c58`
- `0x18011d8c4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009980d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009980d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009966d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180099681`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009966d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180099681`

## string_xrefs

- `0x180099833`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18009974a`: `class Microsoft::WRL::ComPtr<struct Windows::Security::Credentials::IWebAccountProvider> __cdecl shared::OneCoreAccountProvider::GetWebAccountProviderFromAccountType(enum CDPAccountType)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall shared::OneCoreAccountProvider::GetWebAccountProviderFromAccountType(
        __int64 a1,
        _QWORD *a2,
        unsigned __int16 a3)
{
  __int64 *v5; // rsi
  __int64 v6; // r13
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r9
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // edi
  const char *v19; // rax
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v28; // [rsp+30h] [rbp-89h] BYREF
  int v29; // [rsp+38h] [rbp-81h]
  __int64 v30; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v31[2]; // [rsp+48h] [rbp-71h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+58h] [rbp-61h] BYREF
  HSTRING_HEADER v33; // [rsp+90h] [rbp-29h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-11h]
  __int128 hstringHeader; // [rsp+B0h] [rbp-9h] BYREF
  __int128 hstringHeader_16; // [rsp+C0h] [rbp+7h]

  v31[1] = a2;
  v29 = 0;
  v28 = 0;
  if ( a3 == 1 )
  {
    v5 = *(__int64 **)(a1 + 96);
    v6 = *v5;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    *((_QWORD *)&hstringHeader_16 + 1) = 0;
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( aConsumers[v8] );
    if ( v8 <= 0xFFFFFFFF && (int)v8 + 1 >= (unsigned int)v8 )
    {
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        (HSTRING_HEADER *)&hstringHeader,
        L"consumers",
        v8 + 1,
        v8);
      v34 = 0;
      do
        ++v7;
      while ( aHttpsLoginMicr[v7] );
      if ( v7 <= 0xFFFFFFFF && (int)v7 + 1 >= (unsigned int)v7 )
      {
        v9 = *((_QWORD *)&hstringHeader_16 + 1);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v33, L"https://login.microsoft.com", v7 + 1, v7);
        v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v6 + 96))(v5, v34, v9, &v28);
        if ( v10 < 0 )
        {
          v33.Reserved.Reserved1 = ".\\onecoreaccountprovider.cpp";
          *(_DWORD *)&v33.Reserved.Reserved2[8] = 1227;
          v11 = cdp::MakeException<cdp::hresult_exception,>(
                  pExceptionObject,
                  &v33,
                  (unsigned int)v10,
                  "FindAccountProviderWithAuthorityAsync failed for MSA");
          cdp::CdpThrow<cdp::hresult_exception>(&v33, v11);
        }
        goto LABEL_17;
      }
      RaiseException(0x80070216, 1u, 0, 0);
    }
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  if ( a3 == 2 )
  {
    v12 = *(_QWORD *)(a1 + 96);
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v12 + 96LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    v14 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_18037ACA0) + 24);
    v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v33, &off_180357B00);
    v16 = v13(v12, *(_QWORD *)(v15 + 24), v14, &v28);
    if ( v16 < 0 )
    {
      v33.Reserved.Reserved1 = ".\\onecoreaccountprovider.cpp";
      *(_DWORD *)&v33.Reserved.Reserved2[8] = 1233;
      v17 = cdp::MakeException<cdp::hresult_exception,>(
              pExceptionObject,
              &v33,
              (unsigned int)v16,
              "FindAccountProviderWithAuthorityAsync failed for AAD");
      cdp::CdpThrow<cdp::hresult_exception>(&v33, v17);
    }
  }
LABEL_17:
  *a2 = 0;
  v29 = 1;
  v30 = 30000;
  hstringHeader = 0;
  hstringHeader_16 = 0;
  std::string::_Construct<1,char const *>(
    &hstringHeader,
    "class Microsoft::WRL::ComPtr<struct Windows::Security::Credentials::IWebAccountProvider> __cdecl shared::OneCoreAcco"
    "untProvider::GetWebAccountProviderFromAccountType(enum CDPAccountType)",
    186);
  v18 = shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>,Windows::Security::Credentials::IWebAccountProvider>(
          v28,
          &hstringHeader,
          &v30,
          a2);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&hstringHeader);
  if ( v18 < 0 )
  {
    v19 = (const char *)EnumMapper::ToString(a3);
    cdp::detail::StringFormat(&hstringHeader, "FindAccountProviderWithAuthorityAsync failed for %s", v19);
    shared::AggregatedTelemetryLogger::Log((unsigned int)v18, &hstringHeader, ".\\onecoreaccountprovider.cpp", 1239);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&hstringHeader);
    v33.Reserved.Reserved1 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v33.Reserved.Reserved2[8] = 1240;
    v20 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v33, (unsigned int)v18);
    cdp::CdpThrow<cdp::hresult_exception>(&v33, v20);
  }
  if ( !*a2 )
  {
    v33.Reserved.Reserved1 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v33.Reserved.Reserved2[8] = 1241;
    LODWORD(v30) = -2147023692;
    v31[0] = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v21,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v30,
      (unsigned int)&v33,
      (__int64)&v33.Reserved.Reserved2[8],
      (__int64)v31);
    v22 = cdp::ExceptionStackFromSourceLocationInfo(&hstringHeader, &v33);
    v25 = cdp::ErrorCodeToString(2147943604LL, v23, v24, v22);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147943604LL, v25);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v26 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return a2;
}

```

## disassembly

```asm
0x18009952c  mov     [rsp-8+arg_18], rbx
0x180099531  push    rbp
0x180099532  push    rsi
0x180099533  push    rdi
0x180099534  push    r12
0x180099536  push    r13
0x180099538  push    r14
0x18009953a  push    r15
0x18009953c  lea     rbp, [rsp-27h]
0x180099541  sub     rsp, 0E0h
0x180099548  mov     rax, cs:__security_cookie
0x18009954f  xor     rax, rsp
0x180099552  mov     [rbp+57h+var_40], rax
0x180099556  movzx   r15d, r8w
0x18009955a  mov     r14, rdx
0x18009955d  mov     [rbp+57h+var_C0], rdx
0x180099561  xor     r12d, r12d
0x180099564  mov     [rsp+110h+var_D8], r12d
0x180099569  mov     [rsp+110h+var_E0], r12
0x18009956e  lea     ebx, [r12+1]
0x180099573  cmp     r8w, bx
0x180099577  jnz     loc_180099688
0x18009957d  mov     rsi, [rcx+60h]
0x180099581  mov     r13, [rsi]
0x180099584  lea     rcx, [rsp+110h+var_E0]
0x180099589  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009958e  mov     [rbp+57h+var_48], r12
0x180099592  mov     rdx, cs:off_180357AB8; sourceString
0x180099599  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009959d  mov     r9, rdi
0x1800995a0  inc     r9; unsigned int
0x1800995a3  cmp     [rdx+r9*2], r12w
0x1800995a8  jnz     short loc_1800995A0
0x1800995aa  mov     eax, 0FFFFFFFFh
0x1800995af  cmp     r9, rax
0x1800995b2  ja      loc_180099674
0x1800995b8  lea     r8d, [r9+1]; unsigned int
0x1800995bc  cmp     r8d, r9d
0x1800995bf  jb      loc_180099674
0x1800995c5  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800995c9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800995ce  nop
0x1800995cf  mov     [rbp+57h+var_68], r12
0x1800995d3  mov     rdx, cs:off_180357B00; sourceString
0x1800995da  inc     rdi
0x1800995dd  cmp     [rdx+rdi*2], r12w
0x1800995e2  jnz     short loc_1800995DA
0x1800995e4  mov     eax, 0FFFFFFFFh
0x1800995e9  cmp     rdi, rax
0x1800995ec  ja      short loc_180099660
0x1800995ee  lea     r8d, [rdi+1]; unsigned int
0x1800995f2  cmp     r8d, edi
0x1800995f5  jb      short loc_180099660
0x1800995f7  mov     rbx, [rbp+57h+var_48]
0x1800995fb  mov     r9d, edi; unsigned int
0x1800995fe  lea     rcx, [rbp+57h+var_80]; hstringHeader
0x180099602  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180099607  nop
0x180099608  lea     r9, [rsp+110h+var_E0]
0x18009960d  mov     r8, rbx
0x180099610  mov     rdx, [rbp+57h+var_68]
0x180099614  mov     rcx, rsi
0x180099617  mov     rax, [r13+60h]
0x18009961b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099620  nop
0x180099621  test    eax, eax
0x180099623  jns     loc_180099721
0x180099629  lea     rbx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x180099630  mov     qword ptr [rbp+57h+var_80.Reserved], rbx
0x180099634  mov     dword ptr [rbp+57h+var_80.Reserved+8], 4CBh
0x18009963b  lea     r9, aFindaccountpro; "FindAccountProviderWithAuthorityAsync f"...
0x180099642  mov     r8d, eax
0x180099645  lea     rdx, [rbp+57h+var_80]
0x180099649  lea     rcx, [rbp+57h+pExceptionObject]
0x18009964d  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x180099652  nop
0x180099653  mov     rdx, rax
0x180099656  lea     rcx, [rbp+57h+var_80]
0x18009965a  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180099660  xor     r9d, r9d; lpArguments
0x180099663  xor     r8d, r8d; nNumberOfArguments
0x180099666  mov     edx, ebx; dwExceptionFlags
0x180099668  mov     ecx, 80070216h; dwExceptionCode
0x18009966d  call    cs:__imp_RaiseException
0x180099673  nop
0x180099674  xor     r9d, r9d; lpArguments
0x180099677  xor     r8d, r8d; nNumberOfArguments
0x18009967a  mov     edx, ebx; dwExceptionFlags
0x18009967c  mov     ecx, 80070216h; dwExceptionCode
0x180099681  call    cs:__imp_RaiseException
0x180099687  int     3; Trap to Debugger
0x180099688  cmp     r15w, 2
0x18009968d  jnz     loc_180099726
0x180099693  mov     rsi, [rcx+60h]
0x180099697  mov     rax, [rsi]
0x18009969a  mov     rdi, [rax+60h]
0x18009969e  lea     rcx, [rsp+110h+var_E0]
0x1800996a3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800996a8  lea     rdx, off_18037ACA0; "organizations"
0x1800996af  lea     rcx, [rbp+57h+hstringHeader]
0x1800996b3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800996b8  nop
0x1800996b9  mov     rbx, [rax+18h]
0x1800996bd  lea     rdx, off_180357B00; "https://login.microsoft.com"
0x1800996c4  lea     rcx, [rbp+57h+var_80]
0x1800996c8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800996cd  nop
0x1800996ce  lea     r9, [rsp+110h+var_E0]
0x1800996d3  mov     r8, rbx
0x1800996d6  mov     rdx, [rax+18h]
0x1800996da  mov     rcx, rsi
0x1800996dd  mov     rax, rdi
0x1800996e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996e5  nop
0x1800996e6  test    eax, eax
0x1800996e8  jns     short loc_180099721
0x1800996ea  lea     rbx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x1800996f1  mov     qword ptr [rbp+57h+var_80.Reserved], rbx
0x1800996f5  mov     dword ptr [rbp+57h+var_80.Reserved+8], 4D1h
0x1800996fc  lea     r9, aFindaccountpro_1; "FindAccountProviderWithAuthorityAsync f"...
0x180099703  mov     r8d, eax
0x180099706  lea     rdx, [rbp+57h+var_80]
0x18009970a  lea     rcx, [rbp+57h+pExceptionObject]
0x18009970e  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x180099713  nop
0x180099714  mov     rdx, rax
0x180099717  lea     rcx, [rbp+57h+var_80]
0x18009971b  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180099721  mov     ebx, 1
0x180099726  mov     [r14], r12
0x180099729  mov     [rsp+110h+var_D8], ebx
0x18009972d  mov     [rbp+57h+var_D0], 7530h
0x180099735  xorps   xmm0, xmm0
0x180099738  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18009973c  xorps   xmm1, xmm1
0x18009973f  movdqu  xmmword ptr [rbp+7], xmm1
0x180099744  mov     r8d, 0BAh
0x18009974a  lea     rdx, aClassMicrosoft_3; "class Microsoft::WRL::ComPtr<struct Win"...
0x180099751  lea     rcx, [rbp+57h+hstringHeader]
0x180099755  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18009975a  nop
0x18009975b  mov     r9, r14
0x18009975e  lea     r8, [rbp+57h+var_D0]
0x180099762  lea     rdx, [rbp+57h+hstringHeader]
0x180099766  mov     rcx, [rsp+110h+var_E0]
0x18009976b  call    ??$CancellableBlockingWRLCall@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@UIWebAccountProvider@Credentials@Security@3@@shared@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@5@PEAPEAUIWebAccountProvider@Credentials@Security@3@@Z; shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,std::string const &,std::chrono::duration<__int64,std::ratio<1,1000>> const &,Windows::Security::Credentials::IWebAccountProvider * *)
0x180099770  mov     edi, eax
0x180099772  lea     rcx, [rbp+57h+hstringHeader]; void *
0x180099776  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18009977b  test    edi, edi
0x18009977d  jns     short loc_1800997EA
0x18009977f  movzx   ecx, r15w
0x180099783  call    ?ToString@EnumMapper@@YAPEBDW4CDPAccountType@@@Z; EnumMapper::ToString(CDPAccountType)
0x180099788  mov     r8, rax
0x18009978b  lea     rdx, aFindaccountpro_0; "FindAccountProviderWithAuthorityAsync f"...
0x180099792  lea     rcx, [rbp+57h+hstringHeader]
0x180099796  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18009979b  nop
0x18009979c  mov     r9d, 4D7h
0x1800997a2  lea     rbx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x1800997a9  mov     r8, rbx
0x1800997ac  lea     rdx, [rbp+57h+hstringHeader]
0x1800997b0  mov     ecx, edi
0x1800997b2  call    ?Log@AggregatedTelemetryLogger@shared@@SAXJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDI@Z; shared::AggregatedTelemetryLogger::Log(long,std::string const &,char const *,uint)
0x1800997b7  nop
0x1800997b8  lea     rcx, [rbp+57h+hstringHeader]; void *
0x1800997bc  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800997c1  mov     qword ptr [rbp+57h+var_80.Reserved], rbx
0x1800997c5  mov     dword ptr [rbp+57h+var_80.Reserved+8], 4D8h
0x1800997cc  mov     r8d, edi
0x1800997cf  lea     rdx, [rbp+57h+var_80]
0x1800997d3  lea     rcx, [rbp+57h+pExceptionObject]
0x1800997d7  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800997dc  nop
0x1800997dd  mov     rdx, rax
0x1800997e0  lea     rcx, [rbp+57h+var_80]
0x1800997e4  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800997ea  cmp     [r14], r12
0x1800997ed  jnz     loc_180099875
0x1800997f3  lea     rbx, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x1800997fa  mov     qword ptr [rbp+57h+var_80.Reserved], rbx
0x1800997fe  mov     dword ptr [rbp+57h+var_80.Reserved+8], 4D9h
0x180099805  mov     ebx, 800704B4h
0x18009980a  mov     dword ptr [rbp+57h+var_D0], ebx
0x18009980d  call    cs:__imp_GetCurrentThreadId
0x180099813  mov     eax, eax
0x180099815  mov     [rbp+57h+var_C8], rax
0x180099819  lea     rax, [rbp+57h+var_C8]
0x18009981d  mov     [rsp+110h+var_E8], rax
0x180099822  lea     rax, [rbp+57h+var_80.Reserved+8]
0x180099826  mov     [rsp+110h+var_F0], rax
0x18009982b  lea     r9, [rbp+57h+var_80]
0x18009982f  lea     r8, [rbp+57h+var_D0]
0x180099833  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18009983a  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18009983f  lea     rdx, [rbp+57h+var_80]
0x180099843  lea     rcx, [rbp+57h+hstringHeader]
0x180099847  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18009984c  mov     r9, rax
0x18009984f  mov     ecx, ebx
0x180099851  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180099856  mov     r8, rax
0x180099859  mov     edx, ebx
0x18009985b  lea     rcx, [rbp+57h+pExceptionObject]
0x18009985f  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180099864  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18009986b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18009986f  call    _CxxThrowException_0
0x180099875  mov     rcx, [rsp+110h+var_E0]
0x18009987a  test    rcx, rcx
0x18009987d  jz      short loc_180099891
0x18009987f  mov     [rsp+110h+var_E0], r12
0x180099884  mov     rdx, [rcx]
0x180099887  mov     rax, [rdx+10h]
0x18009988b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099890  nop
0x180099891  mov     rax, r14
0x180099894  mov     rcx, [rbp+57h+var_40]
0x180099898  xor     rcx, rsp; StackCookie
0x18009989b  call    __security_check_cookie
0x1800998a0  mov     rbx, [rsp+110h+arg_18]
0x1800998a8  add     rsp, 0E0h
0x1800998af  pop     r15
0x1800998b1  pop     r14
0x1800998b3  pop     r13
0x1800998b5  pop     r12
0x1800998b7  pop     rdi
0x1800998b8  pop     rsi
0x1800998b9  pop     rbp
0x1800998ba  retn
```
