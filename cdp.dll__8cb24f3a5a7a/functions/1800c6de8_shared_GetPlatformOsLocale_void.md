# shared::GetPlatformOsLocale(void)

- ea: `0x1800c6de8`
- end: `0x1800c70ae`
- name: `?GetPlatformOsLocale@shared@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `710`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18005b280`
- `0x1800c5e94`
- `0x18014f5dc`
- `0x180197fc0`

## callees

- `0x18000aec4`
- `0x18000d02c`
- `0x180010fb4`
- `0x180011058`
- `0x180030190`
- `0x1800c6de8`
- `0x1800c70b4`
- `0x18011b1bc`
- `0x1801f6fb0`
- `0x1801f7974`
- `0x1801fc5e8`
- `0x1801fca2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7040`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800c6e58`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800c701d`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800c6e58`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800c701d`

## string_xrefs

- `0x1800c6ed5`: `Unexpected return from GetSystemPreferredUILanguages(). hr = 0x%08x`
- `0x1800c7053`: `Unexpected return from GetSystemPreferredUILanguages(). hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall shared::GetPlatformOsLocale(_QWORD *a1)
{
  BOOL SystemPreferredUILanguages; // eax
  __int64 v3; // rdx
  signed int LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // rdi
  _OWORD *v7; // rdi
  const struct std::nothrow_t *v8; // rdx
  unsigned __int64 v10; // r14
  void *v11; // rsi
  signed int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // [rsp+28h] [rbp-B0h]
  __int64 pulNumLanguages; // [rsp+30h] [rbp-A8h]
  ULONG pulNumLanguagesa; // [rsp+30h] [rbp-A8h] BYREF
  int v18; // [rsp+34h] [rbp-A4h] BYREF
  __int64 pcchLanguagesBuffer; // [rsp+38h] [rbp-A0h] BYREF
  int v20; // [rsp+40h] [rbp-98h]
  const char *v21; // [rsp+48h] [rbp-90h] BYREF
  int v22; // [rsp+50h] [rbp-88h]
  _QWORD *v23; // [rsp+58h] [rbp-80h]
  __int128 v24; // [rsp+60h] [rbp-78h] BYREF
  __int64 v25; // [rsp+70h] [rbp-68h]
  unsigned __int64 v26; // [rsp+78h] [rbp-60h]
  _DWORD v27[14]; // [rsp+80h] [rbp-58h] BYREF

  v23 = a1;
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 15;
  *(_BYTE *)a1 = 0;
  v20 = 1;
  pulNumLanguagesa = 0;
  LODWORD(pcchLanguagesBuffer) = 0;
  SystemPreferredUILanguages = GetSystemPreferredUILanguages(8u, &pulNumLanguagesa, 0, (PULONG)&pcchLanguagesBuffer);
  try
  {
    if ( !SystemPreferredUILanguages )
    {
      v21 = ".\\platformshared.cpp";
      v22 = 137;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v18 = LastError;
      v5 = cdp::MakeException<cdp::HResultException<-2147418113>,long>(
             v27,
             &v21,
             "Unexpected return from GetSystemPreferredUILanguages(). hr = 0x%08x",
             (unsigned int)&v18);
      cdp::CdpThrow<cdp::HResultException<-2147418113>>(&v21, v5);
    }
    if ( !pulNumLanguagesa || !(_DWORD)pcchLanguagesBuffer )
    {
      *(_QWORD *)&v24 = ".\\platformshared.cpp";
      DWORD2(v24) = 139;
      v3 = cdp::MakeException<cdp::HResultException<-2147418113>,>(
             v27,
             &v24,
             "Number of languages and/or languages string length are invalid.");
      cdp::CdpThrow<cdp::HResultException<-2147418113>>(&v24, v3);
    }
    v6 = -1;
    v10 = saturated_mul((unsigned int)pcchLanguagesBuffer, 2u);
    v11 = operator new[](v10);
    memset_0(v11, 0, v10);
    v21 = (const char *)v11;
    v20 = 3;
    if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguagesa, (PZZWSTR)v11, (PULONG)&pcchLanguagesBuffer) )
    {
      *(_QWORD *)&v24 = ".\\platformshared.cpp";
      DWORD2(v24) = 146;
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v18 = v12;
      v13 = cdp::MakeException<cdp::HResultException<-2147418113>,long>(
              v27,
              &v24,
              "Unexpected return from GetSystemPreferredUILanguages(). hr = 0x%08x",
              (unsigned int)&v18);
      cdp::CdpThrow<cdp::HResultException<-2147418113>>(&v24, v13);
    }
    v24 = 0;
    v25 = 0;
    v26 = 0;
    do
      ++v6;
    while ( *((_WORD *)v11 + v6) );
    std::wstring::_Construct<1,unsigned short const *>(&v24, v11, v6);
    v7 = (_OWORD *)cdp::ToUtf8(v27, &v24);
    if ( a1 != (_QWORD *)v7 )
    {
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(a1);
      *(_OWORD *)a1 = *v7;
      *((_OWORD *)a1 + 1) = v7[1];
      *((_QWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 3) = 15;
      *(_BYTE *)v7 = 0;
    }
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v27);
    v8 = (const struct std::nothrow_t *)v26;
    if ( v26 > 7 )
      std::_Deallocate<16>(v24, 2 * v26 + 2);
    if ( v11 )
      operator delete(v11, v8);
  }
  catch ( ... )
  {
    pulNumLanguagesa = -2147418113;
    LODWORD(v14) = GetCurrentThreadId();
    pcchLanguagesBuffer = v14;
    v18 = 152;
    cdp::CatchAllToHR<char const (&)[21],int,unsigned __int64>(
      &pulNumLanguagesa,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Unable to g"
      "et platform OS locale\"}",
      (unsigned int)".\\platformshared.cpp",
      (const char *)&v18,
      (const char *)&pcchLanguagesBuffer,
      v15,
      pulNumLanguages);
  }
  return a1;
}

```

## disassembly

```asm
0x1800c6de8  mov     [rsp+arg_8], rbx
0x1800c6ded  mov     [rsp+arg_10], rsi
0x1800c6df2  push    rdi
0x1800c6df3  push    r14
0x1800c6df5  push    r15
0x1800c6df7  sub     rsp, 0C0h
0x1800c6dfe  mov     rax, cs:__security_cookie
0x1800c6e05  xor     rax, rsp
0x1800c6e08  mov     [rsp+0D8h+var_20], rax
0x1800c6e10  mov     rbx, rcx
0x1800c6e13  mov     [rsp+0D8h+var_80], rcx
0x1800c6e18  xor     r15d, r15d
0x1800c6e1b  mov     [rsp+0D8h+var_98], r15d
0x1800c6e20  xorps   xmm0, xmm0
0x1800c6e23  movups  xmmword ptr [rcx], xmm0
0x1800c6e26  mov     [rcx+10h], r15
0x1800c6e2a  mov     qword ptr [rcx+18h], 0Fh
0x1800c6e32  mov     [rcx], r15b
0x1800c6e35  mov     [rsp+0D8h+var_98], 1
0x1800c6e3d  mov     [rsp+0D8h+pulNumLanguages], r15d
0x1800c6e42  mov     dword ptr [rsp+0D8h+pcchLanguagesBuffer], r15d
0x1800c6e47  lea     r9, [rsp+0D8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800c6e4c  xor     r8d, r8d; pwszLanguagesBuffer
0x1800c6e4f  lea     rdx, [rsp+0D8h+pulNumLanguages]; pulNumLanguages
0x1800c6e54  lea     ecx, [r15+8]; dwFlags
0x1800c6e58  call    cs:__imp_GetSystemPreferredUILanguages
0x1800c6e5e  cmp     eax, 1
0x1800c6e61  jnz     short loc_1800C6EAA
0x1800c6e63  cmp     [rsp+0D8h+pulNumLanguages], r15d
0x1800c6e68  ja      loc_1800C7088
0x1800c6e6e  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x1800c6e75  mov     qword ptr [rsp+0D8h+var_78], rax
0x1800c6e7a  mov     dword ptr [rsp+0D8h+var_78+8], 8Bh
0x1800c6e82  lea     r8, aNumberOfLangua; "Number of languages and/or languages st"...
0x1800c6e89  lea     rdx, [rsp+0D8h+var_78]
0x1800c6e8e  lea     rcx, [rsp+0D8h+var_58]
0x1800c6e96  call    ??$MakeException@V?$HResultException@$0?HPPPAAAB@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPAAAB@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147418113>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x1800c6e9b  nop
0x1800c6e9c  mov     rdx, rax
0x1800c6e9f  lea     rcx, [rsp+0D8h+var_78]
0x1800c6ea4  call    ??$CdpThrow@V?$HResultException@$0?HPPPAAAB@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPAAAB@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147418113>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147418113> &&)
0x1800c6eaa  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x1800c6eb1  mov     [rsp+0D8h+var_90], rax
0x1800c6eb6  mov     [rsp+0D8h+var_88], 89h
0x1800c6ebe  call    cs:__imp_GetLastError
0x1800c6ec4  test    eax, eax
0x1800c6ec6  jg      loc_1800C707B
0x1800c6ecc  mov     [rsp+0D8h+var_A4], eax
0x1800c6ed0  lea     r9, [rsp+0D8h+var_A4]
0x1800c6ed5  lea     r8, aUnexpectedRetu; "Unexpected return from GetSystemPreferr"...
0x1800c6edc  lea     rdx, [rsp+0D8h+var_90]
0x1800c6ee1  lea     rcx, [rsp+0D8h+var_58]
0x1800c6ee9  call    ??$MakeException@V?$HResultException@$0?HPPPAAAB@@cdp@@J@cdp@@YA?AV?$HResultException@$0?HPPPAAAB@@0@AEBUCDPSourceLocationInfo@0@PEBD$$QEAJ@Z; cdp::MakeException<cdp::HResultException<-2147418113>,long>(cdp::CDPSourceLocationInfo const &,char const *,long &&)
0x1800c6eee  nop
0x1800c6eef  mov     rdx, rax
0x1800c6ef2  lea     rcx, [rsp+0D8h+var_90]
0x1800c6ef7  call    ??$CdpThrow@V?$HResultException@$0?HPPPAAAB@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPAAAB@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147418113>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147418113> &&)
0x1800c6efd  xorps   xmm0, xmm0
0x1800c6f00  movups  [rsp+0D8h+var_78], xmm0
0x1800c6f05  mov     [rsp+0D8h+var_68], r15
0x1800c6f0a  mov     [rsp+0D8h+var_60], r15
0x1800c6f0f  inc     rdi
0x1800c6f12  cmp     [rsi+rdi*2], r15w
0x1800c6f17  jnz     short loc_1800C6F0F
0x1800c6f19  mov     r8, rdi
0x1800c6f1c  mov     rdx, rsi
0x1800c6f1f  lea     rcx, [rsp+0D8h+var_78]
0x1800c6f24  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800c6f29  nop
0x1800c6f2a  lea     rdx, [rsp+0D8h+var_78]
0x1800c6f2f  lea     rcx, [rsp+0D8h+var_58]
0x1800c6f37  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x1800c6f3c  mov     rdi, rax
0x1800c6f3f  cmp     rbx, rax
0x1800c6f42  jz      short loc_1800C6F69
0x1800c6f44  mov     rcx, rbx; void *
0x1800c6f47  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800c6f4c  movups  xmm0, xmmword ptr [rdi]
0x1800c6f4f  movups  xmmword ptr [rbx], xmm0
0x1800c6f52  movups  xmm1, xmmword ptr [rdi+10h]
0x1800c6f56  movups  xmmword ptr [rbx+10h], xmm1
0x1800c6f5a  mov     [rdi+10h], r15
0x1800c6f5e  mov     qword ptr [rdi+18h], 0Fh
0x1800c6f66  mov     [rdi], r15b
0x1800c6f69  lea     rcx, [rsp+0D8h+var_58]; void *
0x1800c6f71  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800c6f76  nop
0x1800c6f77  mov     rdx, [rsp+0D8h+var_60]
0x1800c6f7c  cmp     rdx, 7
0x1800c6f80  jbe     short loc_1800C6F95
0x1800c6f82  lea     rdx, ds:2[rdx*2]
0x1800c6f8a  mov     rcx, qword ptr [rsp+0D8h+var_78]
0x1800c6f8f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c6f94  nop
0x1800c6f95  test    rsi, rsi
0x1800c6f98  jz      short loc_1800C6FA3
0x1800c6f9a  mov     rcx, rsi; void *
0x1800c6f9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c6fa2  nop
0x1800c6fa3  mov     rax, rbx
0x1800c6fa6  mov     rcx, [rsp+0D8h+var_20]
0x1800c6fae  xor     rcx, rsp; StackCookie
0x1800c6fb1  call    __security_check_cookie
0x1800c6fb6  lea     r11, [rsp+0D8h+var_18]
0x1800c6fbe  mov     rbx, [r11+28h]
0x1800c6fc2  mov     rsi, [r11+30h]
0x1800c6fc6  mov     rsp, r11
0x1800c6fc9  pop     r15
0x1800c6fcb  pop     r14
0x1800c6fcd  pop     rdi
0x1800c6fce  retn
0x1800c6fcf  mov     rcx, rax
0x1800c6fd2  mov     eax, 2
0x1800c6fd7  mul     rcx
0x1800c6fda  mov     r14, rax
0x1800c6fdd  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800c6fe4  cmovb   r14, rdi
0x1800c6fe8  mov     rcx, r14; unsigned __int64
0x1800c6feb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c6ff0  mov     rsi, rax
0x1800c6ff3  mov     r8, r14; Size
0x1800c6ff6  xor     edx, edx; Val
0x1800c6ff8  mov     rcx, rax; void *
0x1800c6ffb  call    memset_0
0x1800c7000  mov     [rsp+0D8h+var_90], rsi
0x1800c7005  mov     [rsp+0D8h+var_98], 3
0x1800c700d  lea     r9, [rsp+0D8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800c7012  mov     r8, rsi; pwszLanguagesBuffer
0x1800c7015  lea     rdx, [rsp+0D8h+pulNumLanguages]; pulNumLanguages
0x1800c701a  lea     ecx, [rdi+9]; dwFlags
0x1800c701d  call    cs:__imp_GetSystemPreferredUILanguages
0x1800c7023  cmp     eax, 1
0x1800c7026  jz      loc_1800C6EFD
0x1800c702c  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x1800c7033  mov     qword ptr [rsp+0D8h+var_78], rax
0x1800c7038  mov     dword ptr [rsp+0D8h+var_78+8], 92h
0x1800c7040  call    cs:__imp_GetLastError
0x1800c7046  test    eax, eax
0x1800c7048  jg      short loc_1800C7099
0x1800c704a  mov     [rsp+0D8h+var_A4], eax
0x1800c704e  lea     r9, [rsp+0D8h+var_A4]
0x1800c7053  lea     r8, aUnexpectedRetu; "Unexpected return from GetSystemPreferr"...
0x1800c705a  lea     rdx, [rsp+0D8h+var_78]
0x1800c705f  lea     rcx, [rsp+0D8h+var_58]
0x1800c7067  call    ??$MakeException@V?$HResultException@$0?HPPPAAAB@@cdp@@J@cdp@@YA?AV?$HResultException@$0?HPPPAAAB@@0@AEBUCDPSourceLocationInfo@0@PEBD$$QEAJ@Z; cdp::MakeException<cdp::HResultException<-2147418113>,long>(cdp::CDPSourceLocationInfo const &,char const *,long &&)
0x1800c706c  nop
0x1800c706d  mov     rdx, rax
0x1800c7070  lea     rcx, [rsp+0D8h+var_78]
0x1800c7075  call    ??$CdpThrow@V?$HResultException@$0?HPPPAAAB@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPAAAB@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147418113>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147418113> &&)
0x1800c707b  movzx   eax, ax
0x1800c707e  or      eax, 80070000h
0x1800c7083  jmp     loc_1800C6ECC
0x1800c7088  mov     eax, dword ptr [rsp+0D8h+pcchLanguagesBuffer]
0x1800c708c  test    eax, eax
0x1800c708e  jz      loc_1800C6E6E
0x1800c7094  jmp     loc_1800C6FCF
0x1800c7099  movzx   eax, ax
0x1800c709c  or      eax, 80070000h
0x1800c70a1  jmp     short loc_1800C704A
0x1800c70a3  mov     rbx, [rsp+0D8h+var_80]
0x1800c70a8  jmp     loc_1800C6FA3
```
