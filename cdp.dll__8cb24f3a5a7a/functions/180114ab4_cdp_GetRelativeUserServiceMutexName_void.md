# cdp::GetRelativeUserServiceMutexName(void *)

- ea: `0x180114ab4`
- end: `0x180114c4f`
- name: `?GetRelativeUserServiceMutexName@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `411`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180097608`
- `0x1800f55d8`

## callees

- `0x18000d02c`
- `0x18000d098`
- `0x1800624cc`
- `0x1800f10e4`
- `0x180114ab4`
- `0x180114c58`
- `0x1801f6fb0`
- `0x1801f7974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114b18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114b7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114b18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114b7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180114c25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180114c25`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180114b0e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180114b0e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180114b74`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180114b74`

## string_xrefs

- `0x180114b2a`: `.\userservicenotificationclient.cpp`
- `0x180114b90`: `.\userservicenotificationclient.cpp`
- `0x180114bcd`: `CDPUserSvc_Ready_db7a3b24-68b7-4c2e-8335-533dd99ee0f6_`
- `0x180114ba2`: `ConvertSidToStringSid Failed`
- `0x180114b3c`: `GetTokenInformation Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
WCHAR *__fastcall cdp::GetRelativeUserServiceMutexName(WCHAR *a1, void *a2)
{
  signed int LastError; // eax
  __int64 v5; // rax
  signed int v6; // eax
  __int64 v7; // rax
  LPWSTR v8; // rbx
  __int64 v9; // rax
  LPWSTR StringSid; // [rsp+30h] [rbp-D0h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-C4h] BYREF
  _BYTE v13[64]; // [rsp+40h] [rbp-C0h] BYREF
  PSID TokenInformation[12]; // [rsp+80h] [rbp-80h] BYREF
  const char *v15; // [rsp+E0h] [rbp-20h] BYREF
  int v16; // [rsp+E8h] [rbp-18h]
  __m128i si128; // [rsp+F0h] [rbp-10h]

  StringSid = a1;
  memset_0(TokenInformation, 0, 0x58u);
  if ( !GetTokenInformation(a2, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v15 = ".\\userservicenotificationclient.cpp";
    v16 = 119;
    v5 = cdp::MakeException<cdp::hresult_exception,>(v13, &v15, (unsigned int)LastError, "GetTokenInformation Failed");
    cdp::CdpThrow<cdp::hresult_exception>(&v15, v5);
  }
  StringSid = 0;
  if ( !ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
  {
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v15 = ".\\userservicenotificationclient.cpp";
    v16 = 125;
    v7 = cdp::MakeException<cdp::hresult_exception,>(v13, &v15, (unsigned int)v6, "ConvertSidToStringSid Failed");
    cdp::CdpThrow<cdp::hresult_exception>(&v15, v7);
  }
  v8 = StringSid;
  v9 = std::wstring::wstring(&v15, L"CDPUserSvc_Ready_db7a3b24-68b7-4c2e-8335-533dd99ee0f6_");
  std::operator+<unsigned short>(a1, v9, v8);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v15, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v15) = 0;
  if ( StringSid )
    LocalFree(StringSid);
  return a1;
}

```

## disassembly

```asm
0x180114ab4  mov     [rsp-8+arg_10], rbx
0x180114ab9  mov     [rsp-8+arg_18], rdi
0x180114abe  push    rbp
0x180114abf  lea     rbp, [rsp-10h]
0x180114ac4  sub     rsp, 110h
0x180114acb  mov     rax, cs:__security_cookie
0x180114ad2  xor     rax, rsp
0x180114ad5  mov     [rbp+10h+var_10], rax
0x180114ad9  mov     rbx, rdx
0x180114adc  mov     rdi, rcx
0x180114adf  mov     [rsp+110h+StringSid], rcx
0x180114ae4  xor     edx, edx; Val
0x180114ae6  lea     r8d, [rdx+58h]; Size
0x180114aea  lea     rcx, [rbp+10h+TokenInformation]; void *
0x180114aee  call    memset_0
0x180114af3  lea     rax, [rsp+110h+var_D4]
0x180114af8  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x180114afd  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180114b03  lea     r8, [rbp+10h+TokenInformation]; TokenInformation
0x180114b07  lea     edx, [r9-57h]; TokenInformationClass
0x180114b0b  mov     rcx, rbx; TokenHandle
0x180114b0e  call    cs:__imp_GetTokenInformation
0x180114b14  test    eax, eax
0x180114b16  jnz     short loc_180114B62
0x180114b18  call    cs:__imp_GetLastError
0x180114b1e  test    eax, eax
0x180114b20  jle     short loc_180114B2A
0x180114b22  movzx   eax, ax
0x180114b25  or      eax, 80070000h
0x180114b2a  lea     rcx, aUserservicenot; ".\\userservicenotificationclient.cpp"
0x180114b31  mov     [rbp+10h+var_30], rcx
0x180114b35  mov     [rbp+10h+var_28], 77h ; 'w'
0x180114b3c  lea     r9, aGettokeninform; "GetTokenInformation Failed"
0x180114b43  mov     r8d, eax
0x180114b46  lea     rdx, [rbp+10h+var_30]
0x180114b4a  lea     rcx, [rsp+110h+var_D0]
0x180114b4f  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x180114b54  nop
0x180114b55  mov     rdx, rax
0x180114b58  lea     rcx, [rbp+10h+var_30]
0x180114b5c  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180114b62  mov     [rsp+110h+StringSid], 0
0x180114b6b  lea     rdx, [rsp+110h+StringSid]; StringSid
0x180114b70  mov     rcx, [rbp+10h+TokenInformation]; Sid
0x180114b74  call    cs:__imp_ConvertSidToStringSidW
0x180114b7a  test    eax, eax
0x180114b7c  jnz     short loc_180114BC8
0x180114b7e  call    cs:__imp_GetLastError
0x180114b84  test    eax, eax
0x180114b86  jle     short loc_180114B90
0x180114b88  movzx   eax, ax
0x180114b8b  or      eax, 80070000h
0x180114b90  lea     rcx, aUserservicenot; ".\\userservicenotificationclient.cpp"
0x180114b97  mov     [rbp+10h+var_30], rcx
0x180114b9b  mov     [rbp+10h+var_28], 7Dh ; '}'
0x180114ba2  lea     r9, aConvertsidtost_0; "ConvertSidToStringSid Failed"
0x180114ba9  mov     r8d, eax
0x180114bac  lea     rdx, [rbp+10h+var_30]
0x180114bb0  lea     rcx, [rsp+110h+var_D0]
0x180114bb5  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x180114bba  nop
0x180114bbb  mov     rdx, rax
0x180114bbe  lea     rcx, [rbp+10h+var_30]
0x180114bc2  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180114bc8  mov     rbx, [rsp+110h+StringSid]
0x180114bcd  lea     rdx, aCdpusersvcRead; "CDPUserSvc_Ready_db7a3b24-68b7-4c2e-833"...
0x180114bd4  lea     rcx, [rbp+10h+var_30]
0x180114bd8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180114bdd  nop
0x180114bde  mov     r8, rbx
0x180114be1  mov     rdx, rax
0x180114be4  mov     rcx, rdi
0x180114be7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180114bec  nop
0x180114bed  mov     rdx, [rbp+10h+var_18]
0x180114bf1  cmp     rdx, 7
0x180114bf5  jbe     short loc_180114C08
0x180114bf7  lea     rdx, ds:2[rdx*2]
0x180114bff  mov     rcx, [rbp+10h+var_30]
0x180114c03  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180114c08  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180114c10  movdqu  xmmword ptr [rbp-10h], xmm0
0x180114c15  xor     ecx, ecx
0x180114c17  mov     word ptr [rbp+10h+var_30], cx
0x180114c1b  mov     rcx, [rsp+110h+StringSid]; hMem
0x180114c20  test    rcx, rcx
0x180114c23  jz      short loc_180114C2B
0x180114c25  call    cs:__imp_LocalFree
0x180114c2b  mov     rax, rdi
0x180114c2e  mov     rcx, [rbp+10h+var_10]
0x180114c32  xor     rcx, rsp; StackCookie
0x180114c35  call    __security_check_cookie
0x180114c3a  lea     r11, [rsp+110h+var_s0]
0x180114c42  mov     rbx, [r11+20h]
0x180114c46  mov     rdi, [r11+28h]
0x180114c4a  mov     rsp, r11
0x180114c4d  pop     rbp
0x180114c4e  retn
```
