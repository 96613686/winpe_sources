# ESIMPM::EsimPoMgr::s_RetrieveParsePolicy(ESIMPM::_ESIM_POLICY_CONFIG &)

- ea: `0x14002595c`
- end: `0x140025dec`
- name: `?s_RetrieveParsePolicy@EsimPoMgr@ESIMPM@@SAKAEAU_ESIM_POLICY_CONFIG@2@@Z`
- size: `1168`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140024454`
- `0x140029f20`

## callees

- `0x140001308`
- `0x140002f60`
- `0x140003b64`
- `0x1400064d0`
- `0x140006530`
- `0x140008500`
- `0x14000dd20`
- `0x14000de08`
- `0x140013df8`
- `0x140014700`
- `0x1400167fc`
- `0x140020620`
- `0x14002595c`
- `0x1400384a0`
- `0x1400393ec`
- `0x140039990`
- `0x14003a898`
- `0x14003a9d8`
- `0x14003aba0`
- `0x14003adc4`
- `0x14003b25c`
- `0x14003b8bc`
- `0x14003ba84`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x140025993`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x140025993`

## string_xrefs

- `0x14002598c`: `ProgramData`
- `0x1400259e8`: `\microsoft\esimpm\policy\esimpolicies.json`
- `0x140025dac`: `Parsed file is not a JSON object`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ESIMPM::EsimPoMgr::s_RetrieveParsePolicy(__int64 **a1)
{
  __int64 v2; // r8
  __int128 *p_Src; // r9
  __int128 *v4; // rdx
  __int128 *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int128 *v13; // r9
  __int128 *v14; // rdx
  unsigned int v15; // eax
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // edi
  __int64 *v19; // rsi
  __int64 *i; // rbx
  __int64 *v21; // rdx
  _QWORD *v23; // r9
  const char *v24; // [rsp+50h] [rbp-338h] BYREF
  __int64 v25; // [rsp+58h] [rbp-330h] BYREF
  __int128 v26; // [rsp+60h] [rbp-328h] BYREF
  __int64 v27; // [rsp+70h] [rbp-318h]
  unsigned __int64 v28; // [rsp+78h] [rbp-310h]
  __int128 *v29; // [rsp+80h] [rbp-308h]
  __int128 Src; // [rsp+88h] [rbp-300h] BYREF
  __int64 v31; // [rsp+98h] [rbp-2F0h]
  unsigned __int64 v32; // [rsp+A0h] [rbp-2E8h]
  __int128 v33; // [rsp+A8h] [rbp-2E0h] BYREF
  __int128 v34; // [rsp+B8h] [rbp-2D0h]
  int v35; // [rsp+C8h] [rbp-2C0h]
  void **v36; // [rsp+D0h] [rbp-2B8h] BYREF
  __int64 v37; // [rsp+D8h] [rbp-2B0h] BYREF
  _QWORD v38[4]; // [rsp+E8h] [rbp-2A0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+108h] [rbp-280h] BYREF
  WCHAR Buffer[264]; // [rsp+140h] [rbp-248h] BYREF

  GetEnvironmentVariableW(L"ProgramData", Buffer, 0x104u);
  Src = 0;
  v31 = 0;
  v32 = 0;
  v2 = -1;
  do
    ++v2;
  while ( Buffer[v2] );
  std::wstring::_Construct<1,unsigned short const *>(&Src, Buffer);
  std::wstring::_Append<unsigned short>(&Src);
  p_Src = &Src;
  if ( v32 > 7 )
    p_Src = (__int128 *)Src;
  ESIMPM::Log::Info("ESIMPM::EsimPoMgr::s_RetrieveParsePolicy", 0, L"validate policy file (%s)", p_Src);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v4 = &Src;
  if ( v32 > 7 )
    v4 = (__int128 *)Src;
  try
  {
    std::wstring::_Construct<2,unsigned short const *>(&v26, v4);
    v29 = &v26;
    web::json::value::value((web::json::value *)&v25);
    v33 = 0;
    v34 = 0u;
    v5 = &v26;
    if ( v28 > 7 )
      v5 = (__int128 *)v26;
    std::wstring::_Construct<2,unsigned short const *>(&v33, v5);
    PolicyFileParser::parseJsonFile(&v33, &v25);
    if ( (unsigned int)web::json::value::type(&v25) != 3 )
    {
      std::wstring::wstring(&v33, L"Parsed file is not a JSON object");
      PolicyFileParser::ParsingException::ParsingException(pExceptionObject, &v33);
      throw (PolicyFileParser::ParsingException *)pExceptionObject;
    }
    v6 = web::json::value::value((web::json::value *)&v24, (const struct web::json::value *)&v25);
    PolicyFileParser::validateEnabled(v6);
    v7 = web::json::value::value((web::json::value *)&v24, (const struct web::json::value *)&v25);
    PolicyFileParser::validateMaxScanInterval(v7);
    v8 = web::json::value::value((web::json::value *)&v24, (const struct web::json::value *)&v25);
    PolicyFileParser::validatePreferredProfWakeConnectionTimer(v8);
    v9 = web::json::value::value((web::json::value *)&v24, (const struct web::json::value *)&v25);
    PolicyFileParser::validateProfileRegistrationTimer(v9);
    v10 = web::json::value::value((web::json::value *)&v24, (const struct web::json::value *)&v25);
    PolicyFileParser::validateNetworkDiscoveryOption(v10);
    v11 = web::json::value::value((web::json::value *)&v24, (const struct web::json::value *)&v25);
    PolicyFileParser::validateScreenOffDuration(v11);
    v12 = web::json::value::value((web::json::value *)&v24, (const struct web::json::value *)&v25);
    PolicyFileParser::validatePolicies(v12);
    if ( v25 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 192LL))(v25, 1);
    std::wstring::_Tidy_deallocate(&v26);
    v13 = &Src;
    if ( v32 > 7 )
      v13 = (__int128 *)Src;
    ESIMPM::Log::Info("ESIMPM::EsimPoMgr::s_RetrieveParsePolicy", 0, L"parse policy file (%s)", v13);
    v33 = 0;
    v34 = 0u;
    v14 = &Src;
    if ( v32 > 7 )
      v14 = (__int128 *)Src;
  }
  catch ( PolicyFileParser::ParsingException v36 )
  {
    v23 = v38;
    if ( v38[3] > 7u )
      v23 = (_QWORD *)v38[0];
    ESIMPM::Log::Error("ESIMPM::EsimPoMgr::s_RetrieveParsePolicy", 0, L"policy file validation failed: %ws", v23);
    std::wstring::_Tidy_deallocate(v38);
    v36 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v37);
    std::wstring::_Tidy_deallocate(&Src);
    return 1627;
  }
  std::wstring::_Construct<2,unsigned short const *>(&v26, v4);
  v29 = &v26;
  web::json::value::value((web::json::value *)&v25);
  v33 = 0;
  v34 = 0u;
  v5 = &v26;
}

```

## disassembly

```asm
0x14002595c  push    rbx
0x14002595e  push    rsi
0x14002595f  push    rdi
0x140025960  push    r14
0x140025962  sub     rsp, 368h
0x140025969  mov     rax, cs:__security_cookie
0x140025970  xor     rax, rsp
0x140025973  mov     [rsp+388h+var_38], rax
0x14002597b  mov     rbx, rcx
0x14002597e  mov     r8d, 104h; nSize
0x140025984  lea     rdx, [rsp+388h+Buffer]; lpBuffer
0x14002598c  lea     rcx, Name; "ProgramData"
0x140025993  call    cs:__imp_GetEnvironmentVariableW
0x140025999  xorps   xmm0, xmm0
0x14002599c  movups  [rsp+388h+Src], xmm0
0x1400259a4  xor     esi, esi
0x1400259a6  mov     [rsp+388h+var_2F0], rsi
0x1400259ae  mov     [rsp+388h+var_2E8], rsi
0x1400259b6  lea     rax, [rsp+388h+Buffer]
0x1400259be  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400259c2  inc     r8
0x1400259c5  cmp     [rax+r8*2], si
0x1400259ca  jnz     short loc_1400259C2
0x1400259cc  lea     rdx, [rsp+388h+Buffer]
0x1400259d4  lea     rcx, [rsp+388h+Src]
0x1400259dc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400259e1  nop
0x1400259e2  mov     r8d, 2Ah ; '*'
0x1400259e8  lea     rdx, aMicrosoftEsimp; "\\microsoft\\esimpm\\policy\\esimpolici"...
0x1400259ef  lea     rcx, [rsp+388h+Src]; Src
0x1400259f7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1400259fc  lea     r9, [rsp+388h+Src]
0x140025a04  cmp     [rsp+388h+var_2E8], 7
0x140025a0d  cmova   r9, qword ptr [rsp+388h+Src]
0x140025a16  lea     r8, aValidatePolicy; "validate policy file (%s)"
0x140025a1d  xor     edx, edx; struct _GUID *
0x140025a1f  lea     r14, aEsimpmEsimpomg_10; "ESIMPM::EsimPoMgr::s_RetrieveParsePolic"...
0x140025a26  mov     rcx, r14; char *
0x140025a29  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140025a2e  nop
0x140025a2f  xorps   xmm0, xmm0
0x140025a32  movups  [rsp+388h+var_328], xmm0
0x140025a37  mov     [rsp+388h+var_318], rsi
0x140025a3c  mov     [rsp+388h+var_310], rsi
0x140025a41  lea     rdx, [rsp+388h+Src]
0x140025a49  cmp     [rsp+388h+var_2E8], 7
0x140025a52  cmova   rdx, qword ptr [rsp+388h+Src]
0x140025a5b  mov     r8, [rsp+388h+var_2F0]
0x140025a63  lea     rcx, [rsp+388h+var_328]
0x140025a68  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140025a6d  lea     rax, [rsp+388h+var_328]
0x140025a72  mov     [rsp+388h+var_308], rax
0x140025a7a  lea     rcx, [rsp+388h+var_330]; this
0x140025a7f  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x140025a84  nop
0x140025a85  xorps   xmm0, xmm0
0x140025a88  movups  [rsp+388h+var_2E0], xmm0
0x140025a90  mov     qword ptr [rsp+388h+var_2D0], rsi
0x140025a98  mov     qword ptr [rsp+388h+var_2D0+8], rsi
0x140025aa0  lea     rdx, [rsp+388h+var_328]
0x140025aa5  cmp     [rsp+388h+var_310], 7
0x140025aab  cmova   rdx, qword ptr [rsp+388h+var_328]
0x140025ab1  mov     r8, [rsp+388h+var_318]
0x140025ab6  lea     rcx, [rsp+388h+var_2E0]
0x140025abe  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140025ac3  lea     rdx, [rsp+388h+var_330]
0x140025ac8  lea     rcx, [rsp+388h+var_2E0]
0x140025ad0  call    ?parseJsonFile@PolicyFileParser@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVvalue@json@web@@@Z; PolicyFileParser::parseJsonFile(std::wstring,web::json::value &)
0x140025ad5  lea     rcx, [rsp+388h+var_330]
0x140025ada  call    ?type@value@json@web@@QEBA?AW4value_type@123@XZ; web::json::value::type(void)
0x140025adf  cmp     eax, 3
0x140025ae2  jnz     loc_140025DAC
0x140025ae8  lea     rdx, [rsp+388h+var_330]; struct web::json::value *
0x140025aed  lea     rcx, [rsp+388h+var_338]; this
0x140025af2  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140025af7  mov     rcx, rax
0x140025afa  call    ?validateEnabled@PolicyFileParser@@YAXVvalue@json@web@@@Z; PolicyFileParser::validateEnabled(web::json::value)
0x140025aff  lea     rdx, [rsp+388h+var_330]; struct web::json::value *
0x140025b04  lea     rcx, [rsp+388h+var_338]; this
0x140025b09  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140025b0e  mov     rcx, rax
0x140025b11  call    ?validateMaxScanInterval@PolicyFileParser@@YAXVvalue@json@web@@@Z; PolicyFileParser::validateMaxScanInterval(web::json::value)
0x140025b16  lea     rdx, [rsp+388h+var_330]; struct web::json::value *
0x140025b1b  lea     rcx, [rsp+388h+var_338]; this
0x140025b20  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140025b25  mov     rcx, rax
0x140025b28  call    ?validatePreferredProfWakeConnectionTimer@PolicyFileParser@@YAXVvalue@json@web@@@Z; PolicyFileParser::validatePreferredProfWakeConnectionTimer(web::json::value)
0x140025b2d  lea     rdx, [rsp+388h+var_330]; struct web::json::value *
0x140025b32  lea     rcx, [rsp+388h+var_338]; this
0x140025b37  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140025b3c  mov     rcx, rax
0x140025b3f  call    ?validateProfileRegistrationTimer@PolicyFileParser@@YAXVvalue@json@web@@@Z; PolicyFileParser::validateProfileRegistrationTimer(web::json::value)
0x140025b44  lea     rdx, [rsp+388h+var_330]; struct web::json::value *
0x140025b49  lea     rcx, [rsp+388h+var_338]; this
0x140025b4e  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140025b53  mov     rcx, rax
0x140025b56  call    ?validateNetworkDiscoveryOption@PolicyFileParser@@YAXVvalue@json@web@@@Z; PolicyFileParser::validateNetworkDiscoveryOption(web::json::value)
0x140025b5b  lea     rdx, [rsp+388h+var_330]; struct web::json::value *
0x140025b60  lea     rcx, [rsp+388h+var_338]; this
0x140025b65  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140025b6a  mov     rcx, rax
0x140025b6d  call    ?validateScreenOffDuration@PolicyFileParser@@YAXVvalue@json@web@@@Z; PolicyFileParser::validateScreenOffDuration(web::json::value)
0x140025b72  lea     rdx, [rsp+388h+var_330]; struct web::json::value *
0x140025b77  lea     rcx, [rsp+388h+var_338]; this
0x140025b7c  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140025b81  mov     rcx, rax
0x140025b84  call    ?validatePolicies@PolicyFileParser@@YAXVvalue@json@web@@@Z; PolicyFileParser::validatePolicies(web::json::value)
0x140025b89  nop
0x140025b8a  mov     rcx, [rsp+388h+var_330]
0x140025b8f  test    rcx, rcx
0x140025b92  jz      short loc_140025BA9
0x140025b94  mov     rax, [rcx]
0x140025b97  mov     edx, 1
0x140025b9c  mov     rax, [rax+0C0h]
0x140025ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025ba8  nop
0x140025ba9  lea     rcx, [rsp+388h+var_328]
0x140025bae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140025bb3  nop
0x140025bb4  lea     r9, [rsp+388h+Src]
0x140025bbc  cmp     [rsp+388h+var_2E8], 7
0x140025bc5  cmova   r9, qword ptr [rsp+388h+Src]
0x140025bce  lea     r8, aParsePolicyFil; "parse policy file (%s)"
0x140025bd5  xor     edx, edx; struct _GUID *
0x140025bd7  mov     rcx, r14; char *
0x140025bda  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140025bdf  xorps   xmm0, xmm0
0x140025be2  movups  [rsp+388h+var_2E0], xmm0
0x140025bea  mov     qword ptr [rsp+388h+var_2D0], rsi
0x140025bf2  mov     qword ptr [rsp+388h+var_2D0+8], rsi
0x140025bfa  lea     rdx, [rsp+388h+Src]
0x140025c02  cmp     [rsp+388h+var_2E8], 7
0x140025c0b  cmova   rdx, qword ptr [rsp+388h+Src]
0x140025c14  mov     r8, [rsp+388h+var_2F0]
0x140025c1c  lea     rcx, [rsp+388h+var_2E0]
0x140025c24  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140025c29  mov     rdx, rbx
0x140025c2c  lea     rcx, [rsp+388h+var_2E0]
0x140025c34  call    ?parseFile@PolicyFileParser@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_ESIM_POLICY_CONFIG@ESIMPM@@@Z; PolicyFileParser::parseFile(std::wstring,ESIMPM::_ESIM_POLICY_CONFIG *)
0x140025c39  mov     edi, eax
0x140025c3b  test    eax, eax
0x140025c3d  jz      short loc_140025C7C
0x140025c3f  mov     ecx, cs:dword_140075078
0x140025c45  cmp     ecx, 2
0x140025c48  jbe     loc_140025D6C
0x140025c4e  mov     [rsp+388h+var_338], r14
0x140025c53  mov     dword ptr [rsp+388h+var_330], eax
0x140025c57  lea     rax, [rsp+388h+var_338]
0x140025c5c  mov     [rsp+388h+var_360], rax
0x140025c61  lea     rax, [rsp+388h+var_330]
0x140025c66  mov     [rsp+388h+var_368], rax
0x140025c6b  lea     rdx, qword_14006A558
0x140025c72  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140025c77  jmp     loc_140025D6C
0x140025c7c  mov     rax, [rbx+20h]
0x140025c80  sub     rax, [rbx+18h]
0x140025c84  sar     rax, 3
0x140025c88  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x140025c92  imul    rax, rcx
0x140025c96  mov     [rsp+388h+var_340], rax
0x140025c9b  mov     eax, [rbx+14h]
0x140025c9e  mov     [rsp+388h+var_348], eax
0x140025ca2  mov     eax, [rbx+10h]
0x140025ca5  mov     [rsp+388h+var_350], eax
0x140025ca9  mov     eax, [rbx+8]
0x140025cac  mov     [rsp+388h+var_358], eax
0x140025cb0  mov     eax, [rbx+0Ch]
0x140025cb3  mov     dword ptr [rsp+388h+var_360], eax
0x140025cb7  mov     eax, [rbx+4]
0x140025cba  mov     dword ptr [rsp+388h+var_368], eax
0x140025cbe  mov     r9d, [rbx]
0x140025cc1  lea     r8, aNewEsimPolicyF; "New eSIM policy file: enabled %d; maxRe"...
0x140025cc8  xor     edx, edx; struct _GUID *
0x140025cca  mov     rcx, r14; char *
0x140025ccd  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140025cd2  mov     rsi, [rbx+20h]
0x140025cd6  mov     rbx, [rbx+18h]
0x140025cda  jmp     loc_140025D63
0x140025cdf  xorps   xmm0, xmm0
0x140025ce2  movups  [rsp+388h+var_2E0], xmm0
0x140025cea  xorps   xmm1, xmm1
0x140025ced  movdqu  [rsp+388h+var_2D0], xmm1
0x140025cf6  cmp     qword ptr [rbx+18h], 7
0x140025cfb  jbe     short loc_140025D02
0x140025cfd  mov     rdx, [rbx]
0x140025d00  jmp     short loc_140025D05
0x140025d02  mov     rdx, rbx
0x140025d05  mov     r8, [rbx+10h]
0x140025d09  lea     rcx, [rsp+388h+var_2E0]
0x140025d11  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140025d16  mov     r9d, [rbx+20h]
0x140025d1a  mov     [rsp+388h+var_2C0], r9d
0x140025d22  lea     rax, [rsp+388h+var_2E0]
0x140025d2a  cmp     qword ptr [rsp+388h+var_2D0+8], 7
0x140025d33  cmova   rax, qword ptr [rsp+388h+var_2E0]
0x140025d3c  mov     [rsp+388h+var_368], rax
0x140025d41  lea     r8, aPolicyPriority; "Policy: priority %d plmnId %s"
0x140025d48  xor     edx, edx; struct _GUID *
0x140025d4a  mov     rcx, r14; char *
0x140025d4d  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140025d52  lea     rcx, [rsp+388h+var_2E0]
0x140025d5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140025d5f  add     rbx, 28h ; '('
0x140025d63  cmp     rbx, rsi
0x140025d66  jnz     loc_140025CDF
0x140025d6c  lea     rcx, [rsp+388h+Src]
0x140025d74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140025d79  mov     eax, edi
0x140025d7b  jmp     short loc_140025D8F
0x140025d7d  lea     rcx, [rsp+388h+Src]
0x140025d85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140025d8a  mov     eax, 65Bh
0x140025d8f  mov     rcx, [rsp+388h+var_38]
0x140025d97  xor     rcx, rsp; StackCookie
0x140025d9a  call    __security_check_cookie
0x140025d9f  add     rsp, 368h
0x140025da6  pop     r14
0x140025da8  pop     rdi
0x140025da9  pop     rsi
0x140025daa  pop     rbx
0x140025dab  retn
0x140025dac  lea     rdx, aParsedFileIsNo; "Parsed file is not a JSON object"
0x140025db3  lea     rcx, [rsp+388h+var_2E0]
0x140025dbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140025dc0  nop
0x140025dc1  lea     rdx, [rsp+388h+var_2E0]
0x140025dc9  lea     rcx, [rsp+388h+pExceptionObject]
0x140025dd1  call    ??0ParsingException@PolicyFileParser@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyFileParser::ParsingException::ParsingException(std::wstring const &)
0x140025dd6  lea     rdx, _TI2?AVParsingException@PolicyFileParser@@; pThrowInfo
0x140025ddd  lea     rcx, [rsp+388h+pExceptionObject]; pExceptionObject
0x140025de5  call    _CxxThrowException_0
```
