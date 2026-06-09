# shared::GetUserAccountProperty(Windows::Security::Credentials::IWebAccount *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18009fecc`
- end: `0x1800a02b4`
- name: `?GetUserAccountProperty@shared@@YA?AV?$tuple@_NV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAUIWebAccount@Credentials@Security@Windows@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z`
- size: `1000`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18009a0c4`
- `0x18020e348`
- `0x18020e678`

## callees

- `0x180009b48`
- `0x18000aec4`
- `0x18000b724`
- `0x18000d02c`
- `0x18000d098`
- `0x18001ce80`
- `0x180030190`
- `0x1800624cc`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18009fecc`
- `0x1800a11bc`
- `0x18011d5d0`
- `0x18011d808`
- `0x18011d8c4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a0231`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a0231`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a02ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a02ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a001a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a011b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a01ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a001a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a011b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a01ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0090`

## string_xrefs

- `0x1800a025a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18009ff0d`: `.\tokenbrokerhelpers.cpp`
- `0x18009ff70`: `.\tokenbrokerhelpers.cpp`
- `0x18009ffd0`: `.\tokenbrokerhelpers.cpp`
- `0x1800a021b`: `.\tokenbrokerhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall shared::GetUserAccountProperty(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3)
{
  __int64 v6; // rax
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD **); // rbx
  int v12; // eax
  __int64 v13; // rax
  _QWORD *v14; // rbx
  __int64 v15; // rdi
  const WCHAR *v16; // rdx
  unsigned __int64 v17; // r9
  int v18; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v20; // rax
  __m128i v21; // xmm6
  _QWORD *v22; // rcx
  __int64 v23; // rcx
  __m128i si128; // xmm1
  int v26; // ecx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  HSTRING string; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD *v32; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B8h] BYREF
  __int64 CurrentThreadId; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+68h] [rbp-A0h] BYREF
  const char *v37; // [rsp+A0h] [rbp-68h] BYREF
  int v38[6]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 hstringHeader; // [rsp+C0h] [rbp-48h] BYREF
  __m128i hstringHeader_16; // [rsp+D0h] [rbp-38h]
  PCWSTR sourceString[2]; // [rsp+E0h] [rbp-28h] BYREF
  __m128i v42; // [rsp+F0h] [rbp-18h]

  CurrentThreadId = a1;
  if ( !a2 )
  {
    v37 = ".\\tokenbrokerhelpers.cpp";
    v38[0] = 39;
    v6 = cdp::MakeException<std::invalid_argument,>(&hstringHeader, 0, "Expected web account.");
    cdp::CdpThrow<std::invalid_argument>(&v37, v6);
  }
  v33 = 0;
  v7 = **a2;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  v8 = v7(a2, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v33);
  if ( v8 < 0 )
  {
    v37 = ".\\tokenbrokerhelpers.cpp";
    v38[0] = 42;
    v9 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v37, (unsigned int)v8);
    cdp::CdpThrow<cdp::hresult_exception>(&v37, v9);
  }
  v32 = 0;
  v10 = v33;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v33 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  v12 = v11(v10, &v32);
  if ( v12 < 0 )
  {
    v37 = ".\\tokenbrokerhelpers.cpp";
    v38[0] = 45;
    v13 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v37, (unsigned int)v12);
    cdp::CdpThrow<cdp::hresult_exception>(&v37, v13);
  }
  cdp::ToWstring(sourceString, a3);
  string = 0;
  v14 = v32;
  v15 = *v32;
  WindowsDeleteString(0);
  string = 0;
  v16 = (const WCHAR *)sourceString;
  if ( v42.m128i_i64[1] > 7uLL )
    v16 = sourceString[0];
  hstringHeader_16.m128i_i64[1] = 0;
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  if ( v17 > 0xFFFFFFFF || (int)v17 + 1 < (unsigned int)v17 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x1800A02B3LL);
  }
  Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)&hstringHeader, v16, v17 + 1, v17);
  v18 = (*(__int64 (__fastcall **)(_QWORD *, __int64, HSTRING *))(v15 + 48))(
          v14,
          hstringHeader_16.m128i_i64[1],
          &string);
  if ( v18 < 0 )
  {
    if ( v18 != -2147483637 )
    {
      v37 = ".\\tokenbrokerhelpers.cpp";
      v38[0] = 60;
      LODWORD(v34) = v18;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v26,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v34,
        (unsigned int)&v37,
        (__int64)v38,
        (__int64)&CurrentThreadId);
      v27 = cdp::ExceptionStackFromSourceLocationInfo(&hstringHeader, &v37);
      v30 = cdp::ErrorCodeToString((unsigned int)v18, v28, v29, v27);
      ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v18, v30);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    hstringHeader = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    hstringHeader_16 = si128;
    LOBYTE(hstringHeader) = 0;
    *(_OWORD *)a1 = hstringHeader;
    *(__m128i *)(a1 + 16) = si128;
    *(_BYTE *)(a1 + 32) = 0;
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&hstringHeader);
    WindowsDeleteString(string);
    string = 0;
    std::wstring::_Tidy_deallocate(sourceString);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v33);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(&hstringHeader, StringRawBuffer);
    v20 = cdp::ToUtf8(&v37, &hstringHeader);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)v20;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v20 + 16);
    *(_QWORD *)(v20 + 16) = 0;
    *(_QWORD *)(v20 + 24) = 15;
    *(_BYTE *)v20 = 0;
    *(_BYTE *)(a1 + 32) = 1;
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v37);
    if ( hstringHeader_16.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(hstringHeader, 2 * hstringHeader_16.m128i_i64[1] + 2);
    v21 = _mm_load_si128((const __m128i *)&_xmm);
    hstringHeader_16 = v21;
    LOWORD(hstringHeader) = 0;
    WindowsDeleteString(string);
    string = 0;
    if ( v42.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(sourceString[0], 2 * v42.m128i_i64[1] + 2);
    v42 = v21;
    LOWORD(sourceString[0]) = 0;
    v22 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
    }
    v23 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18009fecc  mov     rax, rsp
0x18009fecf  mov     [rax+20h], rbx
0x18009fed3  push    rbp
0x18009fed4  push    rsi
0x18009fed5  push    rdi
0x18009fed6  push    r14
0x18009fed8  push    r15
0x18009feda  lea     rbp, [rax-38h]
0x18009fede  sub     rsp, 110h
0x18009fee5  movaps  xmmword ptr [rax-38h], xmm6
0x18009fee9  mov     rax, cs:__security_cookie
0x18009fef0  xor     rax, rsp
0x18009fef3  mov     [rbp+30h+var_38], rax
0x18009fef7  mov     r14, r8
0x18009fefa  mov     rdi, rdx
0x18009fefd  mov     rsi, rcx
0x18009ff00  mov     [rsp+130h+var_E0], rcx
0x18009ff05  xor     r15d, r15d
0x18009ff08  test    rdx, rdx
0x18009ff0b  jnz     short loc_18009FF3D
0x18009ff0d  lea     rax, aTokenbrokerhel; ".\\tokenbrokerhelpers.cpp"
0x18009ff14  mov     [rbp+30h+var_98], rax
0x18009ff18  mov     [rbp+30h+var_90], 27h ; '''
0x18009ff1f  lea     r8, aExpectedWebAcc; "Expected web account."
0x18009ff26  lea     rcx, [rbp+30h+hstringHeader]
0x18009ff2a  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x18009ff2f  nop
0x18009ff30  mov     rdx, rax
0x18009ff33  lea     rcx, [rbp+30h+var_98]
0x18009ff37  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x18009ff3d  mov     [rsp+130h+var_F0], r15
0x18009ff42  mov     rax, [rdx]
0x18009ff45  mov     rbx, [rax]
0x18009ff48  lea     rcx, [rsp+130h+var_F0]
0x18009ff4d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009ff52  lea     r8, [rsp+130h+var_F0]
0x18009ff57  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x18009ff5e  mov     rcx, rdi
0x18009ff61  mov     rax, rbx
0x18009ff64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ff69  mov     r8d, eax
0x18009ff6c  test    eax, eax
0x18009ff6e  jns     short loc_18009FF9E
0x18009ff70  lea     rax, aTokenbrokerhel; ".\\tokenbrokerhelpers.cpp"
0x18009ff77  mov     [rbp+30h+var_98], rax
0x18009ff7b  mov     [rbp+30h+var_90], 2Ah ; '*'
0x18009ff82  lea     rdx, [rbp+30h+var_98]
0x18009ff86  lea     rcx, [rsp+130h+pExceptionObject]
0x18009ff8b  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009ff90  nop
0x18009ff91  mov     rdx, rax
0x18009ff94  lea     rcx, [rbp+30h+var_98]
0x18009ff98  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009ff9e  mov     [rsp+130h+var_F8], r15
0x18009ffa3  mov     rdi, [rsp+130h+var_F0]
0x18009ffa8  mov     rax, [rdi]
0x18009ffab  mov     rbx, [rax+38h]
0x18009ffaf  lea     rcx, [rsp+130h+var_F8]
0x18009ffb4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009ffb9  lea     rdx, [rsp+130h+var_F8]
0x18009ffbe  mov     rcx, rdi
0x18009ffc1  mov     rax, rbx
0x18009ffc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ffc9  mov     r8d, eax
0x18009ffcc  test    eax, eax
0x18009ffce  jns     short loc_18009FFFE
0x18009ffd0  lea     rax, aTokenbrokerhel; ".\\tokenbrokerhelpers.cpp"
0x18009ffd7  mov     [rbp+30h+var_98], rax
0x18009ffdb  mov     [rbp+30h+var_90], 2Dh ; '-'
0x18009ffe2  lea     rdx, [rbp+30h+var_98]
0x18009ffe6  lea     rcx, [rsp+130h+pExceptionObject]
0x18009ffeb  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009fff0  nop
0x18009fff1  mov     rdx, rax
0x18009fff4  lea     rcx, [rbp+30h+var_98]
0x18009fff8  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009fffe  mov     rdx, r14
0x1800a0001  lea     rcx, [rbp+30h+sourceString]
0x1800a0005  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1800a000a  nop
0x1800a000b  mov     [rsp+130h+string], r15
0x1800a0010  mov     rbx, [rsp+130h+var_F8]
0x1800a0015  mov     rdi, [rbx]
0x1800a0018  xor     ecx, ecx; string
0x1800a001a  call    cs:__imp_WindowsDeleteString
0x1800a0020  mov     [rsp+130h+string], r15
0x1800a0025  lea     rdx, [rbp+30h+sourceString]
0x1800a0029  cmp     [rbp+30h+var_40], 7
0x1800a002e  cmova   rdx, [rbp+30h+sourceString]; sourceString
0x1800a0033  mov     [rbp+30h+var_60], r15
0x1800a0037  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800a003b  inc     r9; unsigned int
0x1800a003e  cmp     [rdx+r9*2], r15w
0x1800a0043  jnz     short loc_1800A003B
0x1800a0045  mov     eax, 0FFFFFFFFh
0x1800a004a  cmp     r9, rax
0x1800a004d  ja      loc_1800A029E
0x1800a0053  lea     r8d, [r9+1]; unsigned int
0x1800a0057  cmp     r8d, r9d
0x1800a005a  jb      loc_1800A029E
0x1800a0060  lea     rcx, [rbp+30h+hstringHeader]; hstringHeader
0x1800a0064  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a0069  nop
0x1800a006a  lea     r8, [rsp+130h+string]
0x1800a006f  mov     rdx, [rbp+30h+var_60]
0x1800a0073  mov     rcx, rbx
0x1800a0076  mov     rax, [rdi+30h]
0x1800a007a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a007f  mov     ebx, eax
0x1800a0081  test    eax, eax
0x1800a0083  js      loc_1800A01AE
0x1800a0089  xor     edx, edx; length
0x1800a008b  mov     rcx, [rsp+130h+string]; string
0x1800a0090  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a0096  mov     rdx, rax
0x1800a0099  lea     rcx, [rbp+30h+hstringHeader]
0x1800a009d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a00a2  nop
0x1800a00a3  lea     rdx, [rbp+30h+hstringHeader]
0x1800a00a7  lea     rcx, [rbp+30h+var_98]
0x1800a00ab  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x1800a00b0  xorps   xmm0, xmm0
0x1800a00b3  movups  xmmword ptr [rsi], xmm0
0x1800a00b6  mov     [rsi+10h], r15
0x1800a00ba  mov     [rsi+18h], r15
0x1800a00be  movups  xmm0, xmmword ptr [rax]
0x1800a00c1  movups  xmmword ptr [rsi], xmm0
0x1800a00c4  movups  xmm1, xmmword ptr [rax+10h]
0x1800a00c8  movups  xmmword ptr [rsi+10h], xmm1
0x1800a00cc  mov     [rax+10h], r15
0x1800a00d0  mov     qword ptr [rax+18h], 0Fh
0x1800a00d8  mov     [rax], r15b
0x1800a00db  mov     byte ptr [rsi+20h], 1
0x1800a00df  lea     rcx, [rbp+30h+var_98]; void *
0x1800a00e3  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a00e8  nop
0x1800a00e9  mov     rdx, [rbp+30h+var_60]
0x1800a00ed  cmp     rdx, 7
0x1800a00f1  jbe     short loc_1800A0104
0x1800a00f3  lea     rdx, ds:2[rdx*2]
0x1800a00fb  mov     rcx, qword ptr [rbp+30h+hstringHeader.Reserved]
0x1800a00ff  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a0104  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800a010c  movdqu  xmmword ptr [rbp-38h], xmm6
0x1800a0111  mov     word ptr [rbp+30h+hstringHeader.Reserved], r15w
0x1800a0116  mov     rcx, [rsp+130h+string]; string
0x1800a011b  call    cs:__imp_WindowsDeleteString
0x1800a0121  mov     [rsp+130h+string], r15
0x1800a0126  mov     rdx, [rbp+30h+var_40]
0x1800a012a  cmp     rdx, 7
0x1800a012e  jbe     short loc_1800A0141
0x1800a0130  lea     rdx, ds:2[rdx*2]
0x1800a0138  mov     rcx, [rbp+30h+sourceString]
0x1800a013c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a0141  movdqu  xmmword ptr [rbp-18h], xmm6
0x1800a0146  mov     word ptr [rbp+30h+sourceString], r15w
0x1800a014b  mov     rcx, [rsp+130h+var_F8]
0x1800a0150  test    rcx, rcx
0x1800a0153  jz      short loc_1800A0167
0x1800a0155  mov     [rsp+130h+var_F8], r15
0x1800a015a  mov     rax, [rcx]
0x1800a015d  mov     rax, [rax+10h]
0x1800a0161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0166  nop
0x1800a0167  mov     rcx, [rsp+130h+var_F0]
0x1800a016c  test    rcx, rcx
0x1800a016f  jz      short loc_1800A0183
0x1800a0171  mov     [rsp+130h+var_F0], r15
0x1800a0176  mov     rdx, [rcx]
0x1800a0179  mov     rax, [rdx+10h]
0x1800a017d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0182  nop
0x1800a0183  mov     rax, rsi
0x1800a0186  mov     rcx, [rbp+30h+var_38]
0x1800a018a  xor     rcx, rsp; StackCookie
0x1800a018d  call    __security_check_cookie
0x1800a0192  lea     r11, [rsp+130h+var_20]
0x1800a019a  mov     rbx, [r11+48h]
0x1800a019e  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a01a3  mov     rsp, r11
0x1800a01a6  pop     r15
0x1800a01a8  pop     r14
0x1800a01aa  pop     rdi
0x1800a01ab  pop     rsi
0x1800a01ac  pop     rbp
0x1800a01ad  retn
0x1800a01ae  cmp     ebx, 8000000Bh
0x1800a01b4  jnz     short loc_1800A021B
0x1800a01b6  xorps   xmm0, xmm0
0x1800a01b9  movups  xmmword ptr [rbp+30h+hstringHeader.Reserved], xmm0
0x1800a01bd  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800a01c5  movdqu  xmmword ptr [rbp-38h], xmm1
0x1800a01ca  mov     byte ptr [rbp+30h+hstringHeader.Reserved], r15b
0x1800a01ce  movups  xmm0, xmmword ptr [rbp+30h+hstringHeader.Reserved]
0x1800a01d2  movups  xmmword ptr [rsi], xmm0
0x1800a01d5  movups  xmmword ptr [rsi+10h], xmm1
0x1800a01d9  mov     [rsi+20h], r15b
0x1800a01dd  lea     rcx, [rbp+30h+hstringHeader]; void *
0x1800a01e1  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a01e6  nop
0x1800a01e7  mov     rcx, [rsp+130h+string]; string
0x1800a01ec  call    cs:__imp_WindowsDeleteString
0x1800a01f2  mov     [rsp+130h+string], r15
0x1800a01f7  lea     rcx, [rbp+30h+sourceString]
0x1800a01fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a0200  nop
0x1800a0201  lea     rcx, [rsp+130h+var_F8]
0x1800a0206  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a020b  nop
0x1800a020c  lea     rcx, [rsp+130h+var_F0]
0x1800a0211  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a0216  jmp     loc_1800A0183
0x1800a021b  lea     rax, aTokenbrokerhel; ".\\tokenbrokerhelpers.cpp"
0x1800a0222  mov     [rbp+30h+var_98], rax
0x1800a0226  mov     [rbp+30h+var_90], 3Ch ; '<'
0x1800a022d  mov     dword ptr [rsp+130h+var_E8], ebx
0x1800a0231  call    cs:__imp_GetCurrentThreadId
0x1800a0237  mov     eax, eax
0x1800a0239  mov     [rsp+130h+var_E0], rax
0x1800a023e  lea     rax, [rsp+130h+var_E0]
0x1800a0243  mov     [rsp+130h+var_108], rax
0x1800a0248  lea     rax, [rbp+30h+var_90]
0x1800a024c  mov     [rsp+130h+var_110], rax
0x1800a0251  lea     r9, [rbp+30h+var_98]
0x1800a0255  lea     r8, [rsp+130h+var_E8]
0x1800a025a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800a0261  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800a0266  lea     rdx, [rbp+30h+var_98]
0x1800a026a  lea     rcx, [rbp+30h+hstringHeader]
0x1800a026e  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800a0273  mov     r9, rax
0x1800a0276  mov     ecx, ebx
0x1800a0278  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800a027d  mov     r8, rax
0x1800a0280  mov     edx, ebx
0x1800a0282  lea     rcx, [rsp+130h+pExceptionObject]
0x1800a0287  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800a028c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800a0293  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x1800a0298  call    _CxxThrowException_0
0x1800a029e  xor     r9d, r9d; lpArguments
0x1800a02a1  xor     r8d, r8d; nNumberOfArguments
0x1800a02a4  lea     edx, [r9+1]; dwExceptionFlags
0x1800a02a8  mov     ecx, 80070216h; dwExceptionCode
0x1800a02ad  call    cs:__imp_RaiseException
```
