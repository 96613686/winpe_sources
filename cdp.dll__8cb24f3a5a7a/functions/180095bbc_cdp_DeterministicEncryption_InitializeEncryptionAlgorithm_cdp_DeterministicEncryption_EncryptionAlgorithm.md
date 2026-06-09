# cdp::DeterministicEncryption::InitializeEncryptionAlgorithm(cdp::DeterministicEncryption::EncryptionAlgorithm)

- ea: `0x180095bbc`
- end: `0x180095fe1`
- name: `?InitializeEncryptionAlgorithm@DeterministicEncryption@cdp@@AEAAXW4EncryptionAlgorithm@12@@Z`
- size: `1061`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18003d144`
- `0x1801e1bc0`

## callees

- `0x1800113bc`
- `0x180030190`
- `0x1800874fc`
- `0x180087560`
- `0x180095bbc`
- `0x180095fe8`
- `0x18011d5d0`
- `0x1801e6c30`
- `0x1801e6ce4`
- `0x1801f6fb0`
- `0x1801f780e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095c13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095d23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095c13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180095d23`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180095c30`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180095d45`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180095c30`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180095d45`
- `bcrypt!BCryptDestroyKey` at `0x180095fcd`
- `bcrypt!BCryptDestroyKey` at `0x180095fcd`
- `bcrypt!BCryptGetProperty` at `0x180095cf9`
- `bcrypt!BCryptGetProperty` at `0x180095f7f`
- `bcrypt!BCryptGetProperty` at `0x180095cf9`
- `bcrypt!BCryptGetProperty` at `0x180095f7f`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180095cbf`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180095cbf`
- `bcrypt!BCryptSetProperty` at `0x180095c73`
- `bcrypt!BCryptSetProperty` at `0x180095f1c`
- `bcrypt!BCryptSetProperty` at `0x180095c73`
- `bcrypt!BCryptSetProperty` at `0x180095f1c`

## string_xrefs

- `0x180095d8e`: `Failed to open an algorithm provider`
- `0x180095e2a`: `Failed to open an algorithm provider`
- `0x180095e5e`: `Failed to configure algorithm`
- `0x180095f38`: `Failed to configure algorithm`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall cdp::DeterministicEncryption::InitializeEncryptionAlgorithm(__int64 a1, int a2)
{
  BCRYPT_ALG_HANDLE *v4; // rdi
  wil::details *v5; // r15
  DWORD LastError; // ebx
  void *v7; // rdx
  UCHAR *v8; // r12
  ULONG cbSecret; // ebx
  void *v10; // r15
  wil::details *v11; // rdi
  DWORD v12; // ebx
  void *v13; // rdx
  __int64 result; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const char *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  const char *v23; // [rsp+40h] [rbp-49h] BYREF
  int v24; // [rsp+48h] [rbp-41h]
  ULONG pcbResult; // [rsp+50h] [rbp-39h] BYREF
  void **v26; // [rsp+58h] [rbp-31h] BYREF
  __int128 v27; // [rsp+60h] [rbp-29h] BYREF
  const char *v28; // [rsp+70h] [rbp-19h] BYREF
  int v29; // [rsp+78h] [rbp-11h]
  _QWORD v30[7]; // [rsp+80h] [rbp-9h] BYREF

  pcbResult = 0;
  v4 = (BCRYPT_ALG_HANDLE *)(a1 + 56);
  v5 = *(wil::details **)(a1 + 56);
  if ( v5 )
  {
    LastError = GetLastError();
    wil::details::BCryptCloseAlgorithmProviderNoFlags(v5, v7);
    SetLastError(LastError);
  }
  *v4 = 0;
  if ( BCryptOpenAlgorithmProvider(v4, L"AES", 0, 0) < 0 )
  {
    v23 = ".\\deterministicencryption.cpp";
    v24 = 28;
    v15 = cdp::MakeException<cdp::HResultException<-2147220479>,>(v30, &v23, "Failed to open an algorithm provider");
    cdp::CdpThrow<cdp::HResultException<-2147220479>>(&v23, v15);
  }
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v28 = ".\\deterministicencryption.cpp";
      v29 = 51;
      cdp::detail::StringFormat(v30, "Unsupported encryption algorithm provided: %d", a2);
      v20 = (const char *)v30;
      if ( v30[3] > 0xFu )
        v20 = (const char *)v30[0];
      v26 = &std::exception::`vftable';
      v27 = 0;
      v23 = v20;
      LOBYTE(v24) = 1;
      o___std_exception_copy_0(&v23, &v27);
      v26 = &std::invalid_argument::`vftable';
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v30);
      cdp::CdpThrow<std::invalid_argument>(&v28, &v26);
    }
    if ( BCryptSetProperty(*v4, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0) < 0 )
    {
      v23 = ".\\deterministicencryption.cpp";
      v24 = 47;
      v19 = cdp::MakeException<cdp::HResultException<-2147220479>,>(v30, &v23, "Failed to configure algorithm");
      cdp::CdpThrow<cdp::HResultException<-2147220479>>(&v23, v19);
    }
  }
  else
  {
    if ( BCryptSetProperty(*v4, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0) < 0 )
    {
      v23 = ".\\deterministicencryption.cpp";
      v24 = 35;
      v21 = cdp::MakeException<cdp::HResultException<-2147220479>,>(v30, &v23, "Failed to configure algorithm");
      cdp::CdpThrow<cdp::HResultException<-2147220479>>(&v23, v21);
    }
    if ( BCryptGetProperty(*v4, L"AuthTagLength", (PUCHAR)(a1 + 72), 0xCu, &pcbResult, 0) < 0 )
    {
      v23 = ".\\deterministicencryption.cpp";
      v24 = 40;
      v22 = cdp::MakeException<cdp::HResultException<-2147220479>,>(v30, &v23, "Failed to get tag length");
      cdp::CdpThrow<cdp::HResultException<-2147220479>>(&v23, v22);
    }
  }
  v8 = *(UCHAR **)(a1 + 24);
  cbSecret = *(_DWORD *)(a1 + 32) - (_DWORD)v8;
  v10 = *(void **)(a1 + 64);
  if ( v10 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v23);
    BCryptDestroyKey(v10);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v23);
  }
  *(_QWORD *)(a1 + 64) = 0;
  if ( BCryptGenerateSymmetricKey(*v4, (BCRYPT_KEY_HANDLE *)(a1 + 64), 0, 0, v8, cbSecret, 0) < 0 )
  {
    v23 = ".\\deterministicencryption.cpp";
    v24 = 57;
    v16 = cdp::MakeException<cdp::HResultException<-2147220479>,>(v30, &v23, "Failed to generate key");
    cdp::CdpThrow<cdp::HResultException<-2147220479>>(&v23, v16);
  }
  if ( BCryptGetProperty(*v4, L"BlockLength", (PUCHAR)(a1 + 84), 4u, &pcbResult, 0) < 0 )
  {
    v23 = ".\\deterministicencryption.cpp";
    v24 = 62;
    v17 = cdp::MakeException<cdp::HResultException<-2147220479>,>(v30, &v23, "Failed to get block length");
    cdp::CdpThrow<cdp::HResultException<-2147220479>>(&v23, v17);
  }
  v11 = *(wil::details **)(a1 + 48);
  if ( v11 )
  {
    v12 = GetLastError();
    wil::details::BCryptCloseAlgorithmProviderNoFlags(v11, v13);
    SetLastError(v12);
  }
  *(_QWORD *)(a1 + 48) = 0;
  result = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(a1 + 48), L"AES-CMAC", 0, 8u) | 0x10000000u;
  if ( (int)result < 0 )
  {
    v23 = ".\\deterministicencryption.cpp";
    v24 = 65;
    v18 = cdp::MakeException<cdp::HResultException<-2147220479>,>(v30, &v23, "Failed to open an algorithm provider");
    cdp::CdpThrow<cdp::HResultException<-2147220479>>(&v23, v18);
  }
  return result;
}

```

## disassembly

```asm
0x180095bbc  mov     [rsp-8+arg_10], rbx
0x180095bc1  mov     [rsp-8+arg_18], rsi
0x180095bc6  push    rbp
0x180095bc7  push    rdi
0x180095bc8  push    r12
0x180095bca  push    r14
0x180095bcc  push    r15
0x180095bce  lea     rbp, [rsp-37h]
0x180095bd3  sub     rsp, 0C0h
0x180095bda  mov     rax, cs:__security_cookie
0x180095be1  xor     rax, rsp
0x180095be4  mov     [rbp+57h+var_28], rax
0x180095be8  mov     r14d, edx
0x180095beb  mov     rsi, rcx
0x180095bee  mov     [rbp+57h+pcbResult], 0
0x180095bf5  lea     rdi, [rcx+38h]
0x180095bf9  mov     r15, [rdi]
0x180095bfc  test    r15, r15
0x180095bff  jz      short loc_180095C19
0x180095c01  call    cs:__imp_GetLastError
0x180095c07  mov     ebx, eax
0x180095c09  mov     rcx, r15; this
0x180095c0c  call    ?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAXPEAX@Z; wil::details::BCryptCloseAlgorithmProviderNoFlags(void *)
0x180095c11  mov     ecx, ebx; dwErrCode
0x180095c13  call    cs:__imp_SetLastError
0x180095c19  mov     qword ptr [rdi], 0
0x180095c20  xor     r9d, r9d; dwFlags
0x180095c23  xor     r8d, r8d; pszImplementation
0x180095c26  lea     rdx, pszAlgId; "AES"
0x180095c2d  mov     rcx, rdi; phAlgorithm
0x180095c30  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180095c36  mov     ebx, 10000000h
0x180095c3b  or      eax, ebx
0x180095c3d  jl      loc_180095D7C
0x180095c43  test    r14d, r14d
0x180095c46  jz      loc_180095EFD
0x180095c4c  cmp     r14d, 1
0x180095c50  jnz     loc_180095E80
0x180095c56  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x180095c5e  lea     r9d, [r14+1Fh]; cbInput
0x180095c62  lea     r8, pbInput; "ChainingModeCBC"
0x180095c69  lea     rdx, aChainingmode; "ChainingMode"
0x180095c70  mov     rcx, [rdi]; hObject
0x180095c73  call    cs:__imp_BCryptSetProperty
0x180095c79  or      eax, ebx
0x180095c7b  jl      loc_180095E4C
0x180095c81  mov     r12, [rsi+18h]
0x180095c85  mov     ebx, [rsi+20h]
0x180095c88  sub     ebx, r12d
0x180095c8b  lea     r14, [rsi+40h]
0x180095c8f  mov     r15, [r14]
0x180095c92  test    r15, r15
0x180095c95  jnz     loc_180095FC1
0x180095c9b  mov     qword ptr [r14], 0
0x180095ca2  mov     [rsp+0E0h+var_B0], 0; dwFlags
0x180095caa  mov     [rsp+0E0h+cbSecret], ebx; cbSecret
0x180095cae  mov     qword ptr [rsp+0E0h+dwFlags], r12; pbSecret
0x180095cb3  xor     r9d, r9d; cbKeyObject
0x180095cb6  xor     r8d, r8d; pbKeyObject
0x180095cb9  mov     rdx, r14; phKey
0x180095cbc  mov     rcx, [rdi]; hAlgorithm
0x180095cbf  call    cs:__imp_BCryptGenerateSymmetricKey
0x180095cc5  mov     r14d, 10000000h
0x180095ccb  or      eax, r14d
0x180095cce  jl      loc_180095DB0
0x180095cd4  lea     r8, [rsi+54h]; pbOutput
0x180095cd8  mov     [rsp+0E0h+cbSecret], 0; dwFlags
0x180095ce0  lea     rax, [rbp+57h+pcbResult]
0x180095ce4  mov     qword ptr [rsp+0E0h+dwFlags], rax; pcbResult
0x180095ce9  mov     r9d, 4; cbOutput
0x180095cef  lea     rdx, aBlocklength; "BlockLength"
0x180095cf6  mov     rcx, [rdi]; hObject
0x180095cf9  call    cs:__imp_BCryptGetProperty
0x180095cff  or      eax, r14d
0x180095d02  jl      loc_180095DE4
0x180095d08  mov     rdi, [rsi+30h]
0x180095d0c  test    rdi, rdi
0x180095d0f  jz      short loc_180095D29
0x180095d11  call    cs:__imp_GetLastError
0x180095d17  mov     ebx, eax
0x180095d19  mov     rcx, rdi; this
0x180095d1c  call    ?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAXPEAX@Z; wil::details::BCryptCloseAlgorithmProviderNoFlags(void *)
0x180095d21  mov     ecx, ebx; dwErrCode
0x180095d23  call    cs:__imp_SetLastError
0x180095d29  mov     qword ptr [rsi+30h], 0
0x180095d31  mov     r9d, 8; dwFlags
0x180095d37  xor     r8d, r8d; pszImplementation
0x180095d3a  lea     rdx, aAesCmac; "AES-CMAC"
0x180095d41  lea     rcx, [rsi+30h]; phAlgorithm
0x180095d45  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180095d4b  or      eax, r14d
0x180095d4e  jl      loc_180095E18
0x180095d54  mov     rcx, [rbp+57h+var_28]
0x180095d58  xor     rcx, rsp; StackCookie
0x180095d5b  call    __security_check_cookie
0x180095d60  lea     r11, [rsp+0E0h+var_20]
0x180095d68  mov     rbx, [r11+40h]
0x180095d6c  mov     rsi, [r11+48h]
0x180095d70  mov     rsp, r11
0x180095d73  pop     r15
0x180095d75  pop     r14
0x180095d77  pop     r12
0x180095d79  pop     rdi
0x180095d7a  pop     rbp
0x180095d7b  retn
0x180095d7c  lea     rax, aDeterministice; ".\\deterministicencryption.cpp"
0x180095d83  mov     [rbp+57h+var_A0], rax
0x180095d87  mov     [rbp+57h+var_98], 1Ch
0x180095d8e  lea     r8, aFailedToOpenAn; "Failed to open an algorithm provider"
0x180095d95  lea     rdx, [rbp+57h+var_A0]
0x180095d99  lea     rcx, [rbp+57h+var_60]
0x180095d9d  call    ??$MakeException@V?$HResultException@$0?HPPLPLPP@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPLPP@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147220479>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180095da2  nop
0x180095da3  mov     rdx, rax
0x180095da6  lea     rcx, [rbp+57h+var_A0]
0x180095daa  call    ??$CdpThrow@V?$HResultException@$0?HPPLPLPP@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPLPP@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147220479>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147220479> &&)
0x180095db0  lea     rax, aDeterministice; ".\\deterministicencryption.cpp"
0x180095db7  mov     [rbp+57h+var_A0], rax
0x180095dbb  mov     [rbp+57h+var_98], 39h ; '9'
0x180095dc2  lea     r8, aFailedToGenera; "Failed to generate key"
0x180095dc9  lea     rdx, [rbp+57h+var_A0]
0x180095dcd  lea     rcx, [rbp+57h+var_60]
0x180095dd1  call    ??$MakeException@V?$HResultException@$0?HPPLPLPP@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPLPP@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147220479>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180095dd6  nop
0x180095dd7  mov     rdx, rax
0x180095dda  lea     rcx, [rbp+57h+var_A0]
0x180095dde  call    ??$CdpThrow@V?$HResultException@$0?HPPLPLPP@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPLPP@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147220479>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147220479> &&)
0x180095de4  lea     rax, aDeterministice; ".\\deterministicencryption.cpp"
0x180095deb  mov     [rbp+57h+var_A0], rax
0x180095def  mov     [rbp+57h+var_98], 3Eh ; '>'
0x180095df6  lea     r8, aFailedToGetBlo; "Failed to get block length"
0x180095dfd  lea     rdx, [rbp+57h+var_A0]
0x180095e01  lea     rcx, [rbp+57h+var_60]
0x180095e05  call    ??$MakeException@V?$HResultException@$0?HPPLPLPP@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPLPP@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147220479>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180095e0a  nop
0x180095e0b  mov     rdx, rax
0x180095e0e  lea     rcx, [rbp+57h+var_A0]
0x180095e12  call    ??$CdpThrow@V?$HResultException@$0?HPPLPLPP@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPLPP@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147220479>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147220479> &&)
0x180095e18  lea     rax, aDeterministice; ".\\deterministicencryption.cpp"
0x180095e1f  mov     [rbp+57h+var_A0], rax
0x180095e23  mov     [rbp+57h+var_98], 41h ; 'A'
0x180095e2a  lea     r8, aFailedToOpenAn; "Failed to open an algorithm provider"
0x180095e31  lea     rdx, [rbp+57h+var_A0]
0x180095e35  lea     rcx, [rbp+57h+var_60]
0x180095e39  call    ??$MakeException@V?$HResultException@$0?HPPLPLPP@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPLPP@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147220479>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180095e3e  nop
0x180095e3f  mov     rdx, rax
0x180095e42  lea     rcx, [rbp+57h+var_A0]
0x180095e46  call    ??$CdpThrow@V?$HResultException@$0?HPPLPLPP@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPLPP@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147220479>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147220479> &&)
0x180095e4c  lea     rax, aDeterministice; ".\\deterministicencryption.cpp"
0x180095e53  mov     [rbp+57h+var_A0], rax
0x180095e57  mov     [rbp+57h+var_98], 2Fh ; '/'
0x180095e5e  lea     r8, aFailedToConfig; "Failed to configure algorithm"
0x180095e65  lea     rdx, [rbp+57h+var_A0]
0x180095e69  lea     rcx, [rbp+57h+var_60]
0x180095e6d  call    ??$MakeException@V?$HResultException@$0?HPPLPLPP@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPLPP@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147220479>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180095e72  nop
0x180095e73  mov     rdx, rax
0x180095e76  lea     rcx, [rbp+57h+var_A0]
0x180095e7a  call    ??$CdpThrow@V?$HResultException@$0?HPPLPLPP@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPLPP@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147220479>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147220479> &&)
0x180095e80  lea     rax, aDeterministice; ".\\deterministicencryption.cpp"
0x180095e87  mov     [rbp+57h+var_70], rax
0x180095e8b  mov     [rbp+57h+var_68], 33h ; '3'
0x180095e92  mov     r8d, r14d
0x180095e95  lea     rdx, aUnsupportedEnc; "Unsupported encryption algorithm provid"...
0x180095e9c  lea     rcx, [rbp+57h+var_60]
0x180095ea0  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180095ea5  lea     rax, [rbp+57h+var_60]
0x180095ea9  cmp     [rbp+57h+var_48], 0Fh
0x180095eae  cmova   rax, [rbp+57h+var_60]
0x180095eb3  lea     rcx, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180095eba  mov     [rbp+57h+var_88], rcx
0x180095ebe  xorps   xmm0, xmm0
0x180095ec1  movups  [rbp+57h+var_80], xmm0
0x180095ec5  mov     [rbp+57h+var_A0], rax
0x180095ec9  mov     byte ptr [rbp+57h+var_98], 1
0x180095ecd  lea     rdx, [rbp+57h+var_80]
0x180095ed1  lea     rcx, [rbp+57h+var_A0]
0x180095ed5  call    _o___std_exception_copy_0
0x180095eda  lea     rax, ??_7invalid_argument@std@@6B@; const std::invalid_argument::`vftable'
0x180095ee1  mov     [rbp+57h+var_88], rax
0x180095ee5  lea     rcx, [rbp+57h+var_60]; void *
0x180095ee9  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180095eee  nop
0x180095eef  lea     rdx, [rbp+57h+var_88]
0x180095ef3  lea     rcx, [rbp+57h+var_70]
0x180095ef7  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x180095efd  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x180095f05  mov     r9d, 20h ; ' '; cbInput
0x180095f0b  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x180095f12  lea     rdx, aChainingmode; "ChainingMode"
0x180095f19  mov     rcx, [rdi]; hObject
0x180095f1c  call    cs:__imp_BCryptSetProperty
0x180095f22  or      eax, ebx
0x180095f24  jge     short loc_180095F5A
0x180095f26  lea     rax, aDeterministice; ".\\deterministicencryption.cpp"
0x180095f2d  mov     [rbp+57h+var_A0], rax
0x180095f31  mov     [rbp+57h+var_98], 23h ; '#'
0x180095f38  lea     r8, aFailedToConfig; "Failed to configure algorithm"
0x180095f3f  lea     rdx, [rbp+57h+var_A0]
0x180095f43  lea     rcx, [rbp+57h+var_60]
0x180095f47  call    ??$MakeException@V?$HResultException@$0?HPPLPLPP@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPLPP@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147220479>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180095f4c  nop
0x180095f4d  mov     rdx, rax
0x180095f50  lea     rcx, [rbp+57h+var_A0]
0x180095f54  call    ??$CdpThrow@V?$HResultException@$0?HPPLPLPP@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPLPP@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147220479>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147220479> &&)
0x180095f5a  lea     r8, [rsi+48h]; pbOutput
0x180095f5e  mov     [rsp+0E0h+cbSecret], 0; dwFlags
0x180095f66  lea     rax, [rbp+57h+pcbResult]
0x180095f6a  mov     qword ptr [rsp+0E0h+dwFlags], rax; pcbResult
0x180095f6f  mov     r9d, 0Ch; cbOutput
0x180095f75  lea     rdx, aAuthtaglength; "AuthTagLength"
0x180095f7c  mov     rcx, [rdi]; hObject
0x180095f7f  call    cs:__imp_BCryptGetProperty
0x180095f85  or      eax, ebx
0x180095f87  jge     loc_180095C81
0x180095f8d  lea     rax, aDeterministice; ".\\deterministicencryption.cpp"
0x180095f94  mov     [rbp+57h+var_A0], rax
0x180095f98  mov     [rbp+57h+var_98], 28h ; '('
0x180095f9f  lea     r8, aFailedToGetTag; "Failed to get tag length"
0x180095fa6  lea     rdx, [rbp+57h+var_A0]
0x180095faa  lea     rcx, [rbp+57h+var_60]
0x180095fae  call    ??$MakeException@V?$HResultException@$0?HPPLPLPP@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPLPP@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147220479>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180095fb3  nop
0x180095fb4  mov     rdx, rax
0x180095fb7  lea     rcx, [rbp+57h+var_A0]
0x180095fbb  call    ??$CdpThrow@V?$HResultException@$0?HPPLPLPP@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPLPLPP@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147220479>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147220479> &&)
0x180095fc1  lea     rcx, [rbp+57h+var_A0]; this
0x180095fc5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180095fca  mov     rcx, r15; hKey
0x180095fcd  call    cs:__imp_BCryptDestroyKey
0x180095fd3  lea     rcx, [rbp+57h+var_A0]; this
0x180095fd7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180095fdc  jmp     loc_180095C9B
```
