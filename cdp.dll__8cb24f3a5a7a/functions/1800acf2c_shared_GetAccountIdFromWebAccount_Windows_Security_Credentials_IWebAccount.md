# shared::GetAccountIdFromWebAccount(Windows::Security::Credentials::IWebAccount *)

- ea: `0x1800acf2c`
- end: `0x1800ad0fa`
- name: `?GetAccountIdFromWebAccount@shared@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUIWebAccount@Credentials@Security@Windows@@@Z`
- size: `462`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800accf0`
- `0x180224a60`

## callees

- `0x18000aec4`
- `0x18000d02c`
- `0x18000d098`
- `0x18001ce80`
- `0x1800624cc`
- `0x1800acf2c`
- `0x18011d5d0`
- `0x18011d808`
- `0x18011d8c4`
- `0x1801f6fb0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad0ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad0ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad05a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad05a`

## string_xrefs

- `0x1800acf5d`: `.\tokenbrokerhelpers.cpp`
- `0x1800acfc1`: `.\tokenbrokerhelpers.cpp`
- `0x1800ad027`: `.\tokenbrokerhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall shared::GetAccountIdFromWebAccount(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  __int64 v4; // rax
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  __int64 v11; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-29h] BYREF
  HSTRING string; // [rsp+28h] [rbp-21h] BYREF
  const char *v17; // [rsp+30h] [rbp-19h] BYREF
  int v18; // [rsp+38h] [rbp-11h]
  _QWORD v19[2]; // [rsp+48h] [rbp-1h] BYREF
  __m128i si128; // [rsp+58h] [rbp+Fh]

  v15 = a1;
  if ( !a2 )
  {
    v17 = ".\\tokenbrokerhelpers.cpp";
    v18 = 23;
    v4 = cdp::MakeException<std::invalid_argument,>(v19, 0, "Expected web account.");
    cdp::CdpThrow<std::invalid_argument>(&v17, v4);
  }
  v15 = 0;
  v5 = **a2;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
  v6 = v5(a2, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v15);
  if ( v6 < 0 )
  {
    v17 = ".\\tokenbrokerhelpers.cpp";
    v18 = 26;
    v7 = cdp::MakeException<cdp::hresult_exception>(v19, &v17, (unsigned int)v6);
    cdp::CdpThrow<cdp::hresult_exception>(&v17, v7);
  }
  string = 0;
  v8 = v15;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = v9(v8, &string);
  if ( v10 < 0 )
  {
    v17 = ".\\tokenbrokerhelpers.cpp";
    v18 = 30;
    v11 = cdp::MakeException<cdp::hresult_exception>(v19, &v17, (unsigned int)v10);
    cdp::CdpThrow<cdp::hresult_exception>(&v17, v11);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(v19, StringRawBuffer);
  cdp::ToUtf8(a1, v19);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v19[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19[0]) = 0;
  WindowsDeleteString(string);
  string = 0;
  v13 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return a1;
}

```

## disassembly

```asm
0x1800acf2c  mov     [rsp-8+arg_10], rbx
0x1800acf31  push    rbp
0x1800acf32  push    rsi
0x1800acf33  push    rdi
0x1800acf34  lea     rbp, [rsp-47h]
0x1800acf39  sub     rsp, 90h
0x1800acf40  mov     rax, cs:__security_cookie
0x1800acf47  xor     rax, rsp
0x1800acf4a  mov     [rbp+57h+var_20], rax
0x1800acf4e  mov     rdi, rdx
0x1800acf51  mov     rsi, rcx
0x1800acf54  mov     [rbp+57h+var_80], rcx
0x1800acf58  test    rdx, rdx
0x1800acf5b  jnz     short loc_1800ACF8D
0x1800acf5d  lea     rax, aTokenbrokerhel; ".\\tokenbrokerhelpers.cpp"
0x1800acf64  mov     [rbp+57h+var_70], rax
0x1800acf68  mov     [rbp+57h+var_68], 17h
0x1800acf6f  lea     r8, aExpectedWebAcc; "Expected web account."
0x1800acf76  lea     rcx, [rbp+57h+var_58]
0x1800acf7a  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x1800acf7f  nop
0x1800acf80  mov     rdx, rax
0x1800acf83  lea     rcx, [rbp+57h+var_70]
0x1800acf87  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x1800acf8d  mov     [rbp+57h+var_80], 0
0x1800acf95  mov     rax, [rdx]
0x1800acf98  mov     rbx, [rax]
0x1800acf9b  lea     rcx, [rbp+57h+var_80]
0x1800acf9f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800acfa4  lea     r8, [rbp+57h+var_80]
0x1800acfa8  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x1800acfaf  mov     rcx, rdi
0x1800acfb2  mov     rax, rbx
0x1800acfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acfba  mov     r8d, eax
0x1800acfbd  test    eax, eax
0x1800acfbf  jns     short loc_1800ACFEE
0x1800acfc1  lea     rax, aTokenbrokerhel; ".\\tokenbrokerhelpers.cpp"
0x1800acfc8  mov     [rbp+57h+var_70], rax
0x1800acfcc  mov     [rbp+57h+var_68], 1Ah
0x1800acfd3  lea     rdx, [rbp+57h+var_70]
0x1800acfd7  lea     rcx, [rbp+57h+var_58]
0x1800acfdb  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800acfe0  nop
0x1800acfe1  mov     rdx, rax
0x1800acfe4  lea     rcx, [rbp+57h+var_70]
0x1800acfe8  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800acfee  mov     [rbp+57h+string], 0
0x1800acff6  mov     rdi, [rbp+57h+var_80]
0x1800acffa  mov     rax, [rdi]
0x1800acffd  mov     rbx, [rax+30h]
0x1800ad001  xor     ecx, ecx; string
0x1800ad003  call    cs:__imp_WindowsDeleteString
0x1800ad009  mov     [rbp+57h+string], 0
0x1800ad011  lea     rdx, [rbp+57h+string]
0x1800ad015  mov     rcx, rdi
0x1800ad018  mov     rax, rbx
0x1800ad01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad020  mov     r8d, eax
0x1800ad023  test    eax, eax
0x1800ad025  jns     short loc_1800AD054
0x1800ad027  lea     rax, aTokenbrokerhel; ".\\tokenbrokerhelpers.cpp"
0x1800ad02e  mov     [rbp+57h+var_70], rax
0x1800ad032  mov     [rbp+57h+var_68], 1Eh
0x1800ad039  lea     rdx, [rbp+57h+var_70]
0x1800ad03d  lea     rcx, [rbp+57h+var_58]
0x1800ad041  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800ad046  nop
0x1800ad047  mov     rdx, rax
0x1800ad04a  lea     rcx, [rbp+57h+var_70]
0x1800ad04e  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800ad054  xor     edx, edx; length
0x1800ad056  mov     rcx, [rbp+57h+string]; string
0x1800ad05a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad060  mov     rdx, rax
0x1800ad063  lea     rcx, [rbp+57h+var_58]
0x1800ad067  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ad06c  nop
0x1800ad06d  lea     rdx, [rbp+57h+var_58]
0x1800ad071  mov     rcx, rsi
0x1800ad074  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x1800ad079  nop
0x1800ad07a  mov     rdx, [rbp+57h+var_40]
0x1800ad07e  cmp     rdx, 7
0x1800ad082  jbe     short loc_1800AD095
0x1800ad084  lea     rdx, ds:2[rdx*2]
0x1800ad08c  mov     rcx, [rbp+57h+var_58]
0x1800ad090  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800ad095  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800ad09d  movdqu  xmmword ptr [rbp+0Fh], xmm0
0x1800ad0a2  xor     eax, eax
0x1800ad0a4  mov     word ptr [rbp+57h+var_58], ax
0x1800ad0a8  mov     rcx, [rbp+57h+string]; string
0x1800ad0ac  call    cs:__imp_WindowsDeleteString
0x1800ad0b2  mov     [rbp+57h+string], 0
0x1800ad0ba  mov     rcx, [rbp+57h+var_80]
0x1800ad0be  test    rcx, rcx
0x1800ad0c1  jz      short loc_1800AD0D8
0x1800ad0c3  mov     [rbp+57h+var_80], 0
0x1800ad0cb  mov     rdx, [rcx]
0x1800ad0ce  mov     rax, [rdx+10h]
0x1800ad0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad0d7  nop
0x1800ad0d8  mov     rax, rsi
0x1800ad0db  mov     rcx, [rbp+57h+var_20]
0x1800ad0df  xor     rcx, rsp; StackCookie
0x1800ad0e2  call    __security_check_cookie
0x1800ad0e7  mov     rbx, [rsp+0A0h+arg_10]
0x1800ad0ef  add     rsp, 90h
0x1800ad0f6  pop     rdi
0x1800ad0f7  pop     rsi
0x1800ad0f8  pop     rbp
0x1800ad0f9  retn
```
