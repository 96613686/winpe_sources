# PolicyFileParser::parseFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ESIMPM::_ESIM_POLICY_CONFIG *)

- ea: `0x1400393ec`
- end: `0x140039987`
- name: `?parseFile@PolicyFileParser@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_ESIM_POLICY_CONFIG@ESIMPM@@@Z`
- size: `1435`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x14002595c`

## callees

- `0x140002f60`
- `0x1400064d0`
- `0x140006530`
- `0x140006a30`
- `0x140007590`
- `0x140007630`
- `0x14000bc60`
- `0x14000dd20`
- `0x140013df8`
- `0x140014700`
- `0x140036518`
- `0x140037268`
- `0x140038e24`
- `0x140038f3c`
- `0x1400393ec`
- `0x140039990`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PolicyFileParser::parseFile(_QWORD *a1, __int64 a2)
{
  _QWORD *v3; // rdi
  _QWORD *v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  const struct web::json::value *v11; // rax
  const struct web::json::value *v12; // rax
  __int128 *v13; // r14
  __int64 v14; // rax
  _QWORD *v15; // rax
  const struct web::json::value *v16; // rax
  __int128 *v17; // r14
  web::json::value *v18; // rax
  int v19; // r15d
  __int64 v20; // r15
  __int128 *v21; // rdx
  unsigned int i; // r13d
  _BYTE v24[8]; // [rsp+20h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+28h] [rbp-D0h] BYREF
  __int128 *v26; // [rsp+30h] [rbp-C8h] BYREF
  __int128 *v27; // [rsp+38h] [rbp-C0h]
  int v28; // [rsp+44h] [rbp-B4h]
  __int64 v29; // [rsp+48h] [rbp-B0h] BYREF
  _QWORD *v30; // [rsp+50h] [rbp-A8h]
  __int128 v31; // [rsp+58h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+68h] [rbp-90h]
  __int128 v33; // [rsp+78h] [rbp-80h] BYREF
  __int128 v34; // [rsp+88h] [rbp-70h]
  __int128 v35; // [rsp+98h] [rbp-60h] BYREF
  __int128 v36; // [rsp+A8h] [rbp-50h]
  int v37; // [rsp+B8h] [rbp-40h]
  int v38; // [rsp+BCh] [rbp-3Ch]

  v3 = a1;
  v30 = a1;
  v28 = 0;
  if ( !a2 )
  {
LABEL_27:
    std::wstring::_Tidy_deallocate(v3);
    return 87;
  }
  web::json::value::value((web::json::value *)&v25);
  v31 = 0;
  v32 = 0u;
  if ( v3[3] <= 7u )
    v4 = v3;
  else
    v4 = (_QWORD *)*v3;
  try
  {
    std::wstring::_Construct<2,unsigned short const *>(&v31, v4);
    PolicyFileParser::parseJsonFile(&v31, &v25);
    v5 = web::json::value::value((web::json::value *)v24, (const struct web::json::value *)&v25);
    *(_DWORD *)a2 = (unsigned __int8)PolicyFileParser::getEnabled(v5);
    v26 = &v31;
    v31 = 0;
    v32 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(&v31, L"maxRescanIntervalInSeconds");
    v6 = web::json::value::value((web::json::value *)v24, (const struct web::json::value *)&v25);
    *(_DWORD *)(a2 + 4) = PolicyFileParser::getIntegerWithDefault(v6, &v31, 0);
    v27 = &v31;
    v31 = 0;
    v32 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(&v31, L"preferredProfileWakeConnectionTimerInSeconds");
    v7 = web::json::value::value((web::json::value *)v24, (const struct web::json::value *)&v25);
    *(_DWORD *)(a2 + 8) = PolicyFileParser::getIntegerWithDefault(v7, &v31, 200);
    v27 = &v31;
    v31 = 0;
    v32 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(&v31, L"profileRegistrationTimerInSeconds");
    v8 = web::json::value::value((web::json::value *)v24, (const struct web::json::value *)&v25);
    *(_DWORD *)(a2 + 12) = PolicyFileParser::getIntegerWithDefault(v8, &v31, 60);
    v27 = &v31;
    v31 = 0;
    v32 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(&v31, L"networkDiscoveryOption");
    v9 = web::json::value::value((web::json::value *)v24, (const struct web::json::value *)&v25);
    *(_DWORD *)(a2 + 16) = PolicyFileParser::getIntegerWithDefault(v9, &v31, 0);
    v27 = &v31;
    v31 = 0;
    v32 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(&v31, L"screenOffDurationToTriggerNetworkDiscoveryInMinutes");
    v10 = web::json::value::value((web::json::value *)v24, (const struct web::json::value *)&v25);
    *(_DWORD *)(a2 + 20) = PolicyFileParser::getIntegerWithDefault(v10, &v31, 10);
    v31 = 0;
    v32 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v31, L"policies");
    v11 = (const struct web::json::value *)web::json::value::at(&v25, &v31);
    web::json::value::value((web::json::value *)&v29, v11);
    std::wstring::_Tidy_deallocate(&v31);
    for ( i = 0; i < (unsigned __int64)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 184LL))(v29); ++i )
    {
      v12 = (const struct web::json::value *)web::json::value::operator[](&v29, i);
      v13 = (__int128 *)web::json::value::value((web::json::value *)v24, v12);
      v27 = v13;
      v33 = 0;
      v34 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v33, L"profileId");
      v14 = web::json::value::at(v13, &v33);
      v15 = (_QWORD *)web::json::value::as_string(v14);
      v35 = 0;
      v36 = 0;
      if ( v15[3] > 7u )
        v15 = (_QWORD *)*v15;
      std::wstring::_Construct<2,unsigned short const *>(&v35, v15);
      std::wstring::_Tidy_deallocate(&v33);
      if ( *(_QWORD *)v13 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v13 + 192LL))(*(_QWORD *)v13, 1);
      v16 = (const struct web::json::value *)web::json::value::operator[](&v29, i);
      v17 = (__int128 *)web::json::value::value((web::json::value *)&v26, v16);
      v27 = v17;
      v33 = 0;
      v34 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v33, L"priority");
      v18 = (web::json::value *)web::json::value::at(v17, &v33);
      v19 = web::json::value::as_integer(v18);
      std::wstring::_Tidy_deallocate(&v33);
      if ( *(_QWORD *)v17 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v17 + 192LL))(*(_QWORD *)v17, 1);
      v37 = v19;
      v38 = 0;
      v20 = *(_QWORD *)(a2 + 32);
      if ( v20 == *(_QWORD *)(a2 + 40) )
      {
        std::vector<ESIMPM::_ESIM_POLICY>::_Emplace_reallocate<ESIMPM::_ESIM_POLICY const &>(
          a2 + 24,
          *(_QWORD *)(a2 + 32),
          &v35);
      }
      else
      {
        *(_OWORD *)v20 = 0;
        *(_QWORD *)(v20 + 16) = 0;
        *(_QWORD *)(v20 + 24) = 0;
        v21 = &v35;
        if ( *((_QWORD *)&v36 + 1) > 7u )
          v21 = (__int128 *)v35;
        std::wstring::_Construct<2,unsigned short const *>(v20, v21);
        *(_DWORD *)(v20 + 32) = v37;
        *(_QWORD *)(a2 + 32) += 40LL;
      }
      v28 |= 1u;
      std::wstring::_Tidy_deallocate(&v35);
    }
    if ( v29 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 192LL))(v29, 1);
  }
  catch ( ... )
  {
    if ( v25 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 192LL))(v25, 1);
    v3 = v30;
    goto LABEL_27;
  }
  std::_Sort_unchecked_ESIMPM::_ESIM_POLICY____PolicyFileParser::parseFile_::_2_::_lambda_1___();
  if ( v25 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 192LL))(v25, 1);
  std::wstring::_Tidy_deallocate(v3);
  return 0;
}

```

## disassembly

```asm
0x1400393ec  mov     [rsp+arg_10], rbx
0x1400393f1  push    rdi
0x1400393f2  push    r12
0x1400393f4  push    r13
0x1400393f6  push    r14
0x1400393f8  push    r15
0x1400393fa  sub     rsp, 0D0h
0x140039401  mov     rax, cs:__security_cookie
0x140039408  xor     rax, rsp
0x14003940b  mov     [rsp+0F8h+var_38], rax
0x140039413  mov     r12, rdx
0x140039416  mov     rdi, rcx
0x140039419  mov     [rsp+0F8h+var_A8], rcx
0x14003941e  xor     ebx, ebx
0x140039420  mov     [rsp+0F8h+var_B4], ebx
0x140039424  test    rdx, rdx
0x140039427  jz      loc_140039951
0x14003942d  lea     rcx, [rsp+0F8h+var_D0]; this
0x140039432  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x140039437  nop
0x140039438  xorps   xmm0, xmm0
0x14003943b  movups  [rsp+0F8h+var_A0], xmm0
0x140039440  mov     qword ptr [rsp+0F8h+var_90], rbx
0x140039445  mov     qword ptr [rsp+0F8h+var_90+8], rbx
0x14003944a  cmp     qword ptr [rdi+18h], 7
0x14003944f  jbe     short loc_140039456
0x140039451  mov     rdx, [rdi]
0x140039454  jmp     short loc_140039459
0x140039456  mov     rdx, rdi
0x140039459  mov     r8, [rdi+10h]
0x14003945d  lea     rcx, [rsp+0F8h+var_A0]
0x140039462  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140039467  lea     rdx, [rsp+0F8h+var_D0]
0x14003946c  lea     rcx, [rsp+0F8h+var_A0]
0x140039471  call    ?parseJsonFile@PolicyFileParser@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVvalue@json@web@@@Z; PolicyFileParser::parseJsonFile(std::wstring,web::json::value &)
0x140039476  lea     rdx, [rsp+0F8h+var_D0]; struct web::json::value *
0x14003947b  lea     rcx, [rsp+0F8h+var_D8]; this
0x140039480  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140039485  mov     rcx, rax
0x140039488  call    ?getEnabled@PolicyFileParser@@YA_NVvalue@json@web@@@Z; PolicyFileParser::getEnabled(web::json::value)
0x14003948d  movzx   eax, al
0x140039490  mov     [r12], eax
0x140039494  lea     rax, [rsp+0F8h+var_A0]
0x140039499  mov     [rsp+0F8h+var_C8], rax
0x14003949e  xorps   xmm0, xmm0
0x1400394a1  movups  [rsp+0F8h+var_A0], xmm0
0x1400394a6  mov     qword ptr [rsp+0F8h+var_90], rbx
0x1400394ab  mov     qword ptr [rsp+0F8h+var_90+8], rbx
0x1400394b0  mov     r8d, 1Ah
0x1400394b6  lea     rdx, aMaxrescaninter; "maxRescanIntervalInSeconds"
0x1400394bd  lea     rcx, [rsp+0F8h+var_A0]
0x1400394c2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400394c7  nop
0x1400394c8  lea     rdx, [rsp+0F8h+var_D0]; struct web::json::value *
0x1400394cd  lea     rcx, [rsp+0F8h+var_D8]; this
0x1400394d2  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x1400394d7  nop
0x1400394d8  xor     r8d, r8d
0x1400394db  lea     rdx, [rsp+0F8h+var_A0]
0x1400394e0  mov     rcx, rax
0x1400394e3  call    ?getIntegerWithDefault@PolicyFileParser@@YAIVvalue@json@web@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; PolicyFileParser::getIntegerWithDefault(web::json::value,std::wstring,uint)
0x1400394e8  mov     [r12+4], eax
0x1400394ed  lea     rax, [rsp+0F8h+var_A0]
0x1400394f2  mov     [rsp+0F8h+var_C0], rax
0x1400394f7  xorps   xmm0, xmm0
0x1400394fa  movups  [rsp+0F8h+var_A0], xmm0
0x1400394ff  mov     qword ptr [rsp+0F8h+var_90], rbx
0x140039504  mov     qword ptr [rsp+0F8h+var_90+8], rbx
0x140039509  mov     r8d, 2Ch ; ','
0x14003950f  lea     rdx, aPreferredprofi; "preferredProfileWakeConnectionTimerInSe"...
0x140039516  lea     rcx, [rsp+0F8h+var_A0]
0x14003951b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140039520  nop
0x140039521  lea     rdx, [rsp+0F8h+var_D0]; struct web::json::value *
0x140039526  lea     rcx, [rsp+0F8h+var_D8]; this
0x14003952b  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140039530  nop
0x140039531  mov     r8d, 0C8h
0x140039537  lea     rdx, [rsp+0F8h+var_A0]
0x14003953c  mov     rcx, rax
0x14003953f  call    ?getIntegerWithDefault@PolicyFileParser@@YAIVvalue@json@web@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; PolicyFileParser::getIntegerWithDefault(web::json::value,std::wstring,uint)
0x140039544  mov     [r12+8], eax
0x140039549  lea     rax, [rsp+0F8h+var_A0]
0x14003954e  mov     [rsp+0F8h+var_C0], rax
0x140039553  xorps   xmm0, xmm0
0x140039556  movups  [rsp+0F8h+var_A0], xmm0
0x14003955b  mov     qword ptr [rsp+0F8h+var_90], rbx
0x140039560  mov     qword ptr [rsp+0F8h+var_90+8], rbx
0x140039565  mov     r8d, 21h ; '!'
0x14003956b  lea     rdx, aProfileregistr; "profileRegistrationTimerInSeconds"
0x140039572  lea     rcx, [rsp+0F8h+var_A0]
0x140039577  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003957c  nop
0x14003957d  lea     rdx, [rsp+0F8h+var_D0]; struct web::json::value *
0x140039582  lea     rcx, [rsp+0F8h+var_D8]; this
0x140039587  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003958c  nop
0x14003958d  mov     r8d, 3Ch ; '<'
0x140039593  lea     rdx, [rsp+0F8h+var_A0]
0x140039598  mov     rcx, rax
0x14003959b  call    ?getIntegerWithDefault@PolicyFileParser@@YAIVvalue@json@web@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; PolicyFileParser::getIntegerWithDefault(web::json::value,std::wstring,uint)
0x1400395a0  mov     [r12+0Ch], eax
0x1400395a5  lea     rax, [rsp+0F8h+var_A0]
0x1400395aa  mov     [rsp+0F8h+var_C0], rax
0x1400395af  xorps   xmm0, xmm0
0x1400395b2  movups  [rsp+0F8h+var_A0], xmm0
0x1400395b7  mov     qword ptr [rsp+0F8h+var_90], rbx
0x1400395bc  mov     qword ptr [rsp+0F8h+var_90+8], rbx
0x1400395c1  mov     r8d, 16h
0x1400395c7  lea     rdx, aNetworkdiscove; "networkDiscoveryOption"
0x1400395ce  lea     rcx, [rsp+0F8h+var_A0]
0x1400395d3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400395d8  nop
0x1400395d9  lea     rdx, [rsp+0F8h+var_D0]; struct web::json::value *
0x1400395de  lea     rcx, [rsp+0F8h+var_D8]; this
0x1400395e3  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x1400395e8  nop
0x1400395e9  xor     r8d, r8d
0x1400395ec  lea     rdx, [rsp+0F8h+var_A0]
0x1400395f1  mov     rcx, rax
0x1400395f4  call    ?getIntegerWithDefault@PolicyFileParser@@YAIVvalue@json@web@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; PolicyFileParser::getIntegerWithDefault(web::json::value,std::wstring,uint)
0x1400395f9  mov     [r12+10h], eax
0x1400395fe  lea     rax, [rsp+0F8h+var_A0]
0x140039603  mov     [rsp+0F8h+var_C0], rax
0x140039608  xorps   xmm0, xmm0
0x14003960b  movups  [rsp+0F8h+var_A0], xmm0
0x140039610  mov     qword ptr [rsp+0F8h+var_90], rbx
0x140039615  mov     qword ptr [rsp+0F8h+var_90+8], rbx
0x14003961a  mov     r8d, 33h ; '3'
0x140039620  lea     rdx, aScreenoffdurat; "screenOffDurationToTriggerNetworkDiscov"...
0x140039627  lea     rcx, [rsp+0F8h+var_A0]
0x14003962c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140039631  nop
0x140039632  lea     rdx, [rsp+0F8h+var_D0]; struct web::json::value *
0x140039637  lea     rcx, [rsp+0F8h+var_D8]; this
0x14003963c  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x140039641  nop
0x140039642  mov     r8d, 0Ah
0x140039648  lea     rdx, [rsp+0F8h+var_A0]
0x14003964d  mov     rcx, rax
0x140039650  call    ?getIntegerWithDefault@PolicyFileParser@@YAIVvalue@json@web@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; PolicyFileParser::getIntegerWithDefault(web::json::value,std::wstring,uint)
0x140039655  mov     [r12+14h], eax
0x14003965a  xorps   xmm0, xmm0
0x14003965d  movups  [rsp+0F8h+var_A0], xmm0
0x140039662  xorps   xmm1, xmm1
0x140039665  movdqu  [rsp+0F8h+var_90], xmm1
0x14003966b  mov     r8d, 8
0x140039671  lea     rdx, aPolicies; "policies"
0x140039678  lea     rcx, [rsp+0F8h+var_A0]
0x14003967d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140039682  nop
0x140039683  lea     rdx, [rsp+0F8h+var_A0]
0x140039688  lea     rcx, [rsp+0F8h+var_D0]
0x14003968d  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x140039692  mov     rdx, rax; struct web::json::value *
0x140039695  lea     rcx, [rsp+0F8h+var_B0]; this
0x14003969a  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x14003969f  nop
0x1400396a0  lea     rcx, [rsp+0F8h+var_A0]
0x1400396a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400396aa  mov     r13d, ebx
0x1400396ad  mov     rcx, [rsp+0F8h+var_B0]
0x1400396b2  mov     rax, [rcx]
0x1400396b5  mov     rax, [rax+0B8h]
0x1400396bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400396c1  mov     r15d, r13d
0x1400396c4  cmp     r15, rax
0x1400396c7  jnb     loc_1400398B7
0x1400396cd  mov     edx, r15d
0x1400396d0  lea     rcx, [rsp+0F8h+var_B0]
0x1400396d5  call    ??Avalue@json@web@@QEAAAEAV012@_K@Z; web::json::value::operator[](unsigned __int64)
0x1400396da  mov     rdx, rax; struct web::json::value *
0x1400396dd  lea     rcx, [rsp+0F8h+var_D8]; this
0x1400396e2  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x1400396e7  mov     r14, rax
0x1400396ea  mov     [rsp+0F8h+var_C0], rax
0x1400396ef  xorps   xmm0, xmm0
0x1400396f2  movups  [rsp+0F8h+var_80], xmm0
0x1400396f7  xorps   xmm1, xmm1
0x1400396fa  movdqu  [rsp+0F8h+var_70], xmm1
0x140039703  mov     r8d, 9
0x140039709  lea     rdx, aProfileid; "profileId"
0x140039710  lea     rcx, [rsp+0F8h+var_80]
0x140039715  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003971a  nop
0x14003971b  lea     rdx, [rsp+0F8h+var_80]
0x140039720  mov     rcx, r14
0x140039723  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x140039728  mov     rcx, rax
0x14003972b  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x140039730  xorps   xmm0, xmm0
0x140039733  movups  [rsp+0F8h+var_60], xmm0
0x14003973b  xorps   xmm1, xmm1
0x14003973e  movdqu  [rsp+0F8h+var_50], xmm1
0x140039747  mov     r8, [rax+10h]
0x14003974b  cmp     qword ptr [rax+18h], 7
0x140039750  jbe     short loc_140039755
0x140039752  mov     rax, [rax]
0x140039755  mov     rdx, rax
0x140039758  lea     rcx, [rsp+0F8h+var_60]
0x140039760  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140039765  nop
0x140039766  lea     rcx, [rsp+0F8h+var_80]
0x14003976b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140039770  nop
0x140039771  mov     rcx, [r14]
0x140039774  test    rcx, rcx
0x140039777  jz      short loc_14003978E
0x140039779  mov     rax, [rcx]
0x14003977c  mov     edx, 1
0x140039781  mov     rax, [rax+0C0h]
0x140039788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003978d  nop
0x14003978e  mov     rdx, r15
0x140039791  lea     rcx, [rsp+0F8h+var_B0]
0x140039796  call    ??Avalue@json@web@@QEAAAEAV012@_K@Z; web::json::value::operator[](unsigned __int64)
0x14003979b  mov     rdx, rax; struct web::json::value *
0x14003979e  lea     rcx, [rsp+0F8h+var_C8]; this
0x1400397a3  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x1400397a8  mov     r14, rax
0x1400397ab  mov     [rsp+0F8h+var_C0], rax
0x1400397b0  xorps   xmm0, xmm0
0x1400397b3  movups  [rsp+0F8h+var_80], xmm0
0x1400397b8  xorps   xmm1, xmm1
0x1400397bb  movdqu  [rsp+0F8h+var_70], xmm1
0x1400397c4  mov     r8d, 8
0x1400397ca  lea     rdx, aPriority; "priority"
0x1400397d1  lea     rcx, [rsp+0F8h+var_80]
0x1400397d6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400397db  nop
0x1400397dc  lea     rdx, [rsp+0F8h+var_80]
0x1400397e1  mov     rcx, r14
0x1400397e4  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1400397e9  mov     rcx, rax; this
0x1400397ec  call    ?as_integer@value@json@web@@QEBAHXZ; web::json::value::as_integer(void)
0x1400397f1  mov     r15d, eax
0x1400397f4  lea     rcx, [rsp+0F8h+var_80]
0x1400397f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400397fe  nop
0x1400397ff  mov     r8, [r14]
0x140039802  test    r8, r8
0x140039805  jz      short loc_14003981E
0x140039807  mov     rcx, [r8]
0x14003980a  mov     rax, [rcx+0C0h]
0x140039811  mov     edx, 1
0x140039816  mov     rcx, r8
0x140039819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003981e  mov     [rsp+0F8h+var_40], r15d
0x140039826  xor     eax, eax
0x140039828  mov     [rsp+0F8h+var_3C], eax
0x14003982f  mov     r15, [r12+20h]
0x140039834  cmp     r15, [r12+28h]
0x140039839  jz      short loc_140039887
0x14003983b  xorps   xmm0, xmm0
0x14003983e  movups  xmmword ptr [r15], xmm0
0x140039842  mov     [r15+10h], rbx
0x140039846  mov     [r15+18h], rbx
0x14003984a  lea     rdx, [rsp+0F8h+var_60]
0x140039852  cmp     qword ptr [rsp+0F8h+var_50+8], 7
0x14003985b  cmova   rdx, qword ptr [rsp+0F8h+var_60]
0x140039864  mov     r8, qword ptr [rsp+0F8h+var_50]
0x14003986c  mov     rcx, r15
0x14003986f  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140039874  mov     eax, [rsp+0F8h+var_40]
0x14003987b  mov     [r15+20h], eax
0x14003987f  add     qword ptr [r12+20h], 28h ; '('
0x140039885  jmp     short loc_14003989D
0x140039887  lea     r8, [rsp+0F8h+var_60]
0x14003988f  mov     rdx, r15
0x140039892  lea     rcx, [r12+18h]
0x140039897  call    ??$_Emplace_reallocate@AEBU_ESIM_POLICY@ESIMPM@@@?$vector@U_ESIM_POLICY@ESIMPM@@V?$allocator@U_ESIM_POLICY@ESIMPM@@@std@@@std@@AEAAPEAU_ESIM_POLICY@ESIMPM@@QEAU23@AEBU23@@Z; std::vector<ESIMPM::_ESIM_POLICY>::_Emplace_reallocate<ESIMPM::_ESIM_POLICY const &>(ESIMPM::_ESIM_POLICY * const,ESIMPM::_ESIM_POLICY const &)
0x14003989c  nop
0x14003989d  or      [rsp+0F8h+var_B4], 1
0x1400398a2  lea     rcx, [rsp+0F8h+var_60]
0x1400398aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400398af  inc     r13d
0x1400398b2  jmp     loc_1400396AD
0x1400398b7  mov     rcx, [rsp+0F8h+var_B0]
0x1400398bc  test    rcx, rcx
0x1400398bf  jz      short loc_1400398D6
0x1400398c1  mov     rax, [rcx]
0x1400398c4  mov     edx, 1
0x1400398c9  mov     rax, [rax+0C0h]
0x1400398d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400398d5  nop
0x1400398d6  mov     rdx, [r12+20h]
0x1400398db  mov     rcx, [r12+18h]
0x1400398e0  mov     r8, rdx
0x1400398e3  sub     r8, rcx
0x1400398e6  sar     r8, 3
0x1400398ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400398f4  imul    r8, rax
0x1400398f8  mov     r9b, [rsp+0F8h+var_B8]
0x1400398fd  call    std___Sort_unchecked_ESIMPM___ESIM_POLICY____PolicyFileParser__parseFile____2____lambda_1___
0x140039902  nop
0x140039903  mov     rcx, [rsp+0F8h+var_D0]
0x140039908  test    rcx, rcx
0x14003990b  jz      short loc_140039922
0x14003990d  mov     rax, [rcx]
0x140039910  mov     edx, 1
  ... truncated ...
```
