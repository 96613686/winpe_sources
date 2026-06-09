# PublicNlm::Log(INetworkCostManager *)

- ea: `0x18001101c`
- end: `0x180011363`
- name: `?Log@PublicNlm@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkCostManager@@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x180010f64`

## callees

- `0x18000f388`
- `0x180010124`
- `0x18001101c`
- `0x180011614`
- `0x1800120d0`
- `0x18002a928`
- `0x18002b654`
- `0x18003a2ac`
- `0x18003a37c`
- `0x18003ea18`
- `0x180043010`

## string_xrefs

- `0x18001108a`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x1800110ee`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall PublicNlm::Log(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // di
  int v6; // eax
  int v7; // eax
  const wchar_t *v8; // rsi
  const wchar_t *v9; // r15
  const wchar_t *v10; // r13
  const wchar_t *v11; // r12
  __int64 v12; // rbx
  __int64 v13; // rax
  char v14; // di
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+64h] [rbp-9Ch] BYREF
  const wchar_t *v18; // [rsp+68h] [rbp-98h]
  __int64 v19; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+78h] [rbp-88h]
  _BYTE v21[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v23[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v24[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v25[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v26[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v27[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v28[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v29[32]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v30; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v31; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v32; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v33; // [rsp+1D0h] [rbp+D0h]
  int v34; // [rsp+1D8h] [rbp+D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v19 = a2;
  v5 = 0;
  v34 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)a3 + 24LL))(a3, &v34, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v6,
      v16);
  v17 = v34;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)a3 + 32LL))(a3, &v30, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v7,
      v16);
  v8 = L"-1";
  if ( (_DWORD)v31 == -1 )
  {
    v9 = L"-1";
  }
  else
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v25);
    v5 = 65;
    v9 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  ToString(v29, (char *)&v31 + 4);
  v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v28, (char *)&v32 + 8);
  v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( (_DWORD)v33 == -1 )
  {
    v18 = L"-1";
  }
  else
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v24);
    v5 |= 2u;
    v18 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  if ( DWORD1(v32) == -1 )
  {
    v10 = L"-1";
  }
  else
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v23);
    v5 |= 4u;
    v10 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  if ( (_DWORD)v32 == -1 )
  {
    v11 = L"-1";
  }
  else
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v22);
    v5 |= 8u;
    v11 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  if ( HIDWORD(v31) != -1 )
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v21);
    v5 |= 0x10u;
    v8 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  ToString(v27, &v17);
  v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v26, &v30);
  v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>(
    a2,
    (__int64)L"\n"
              " >>>>>> INetworkCostManager Cost Information <<<<<<\n"
              "    InterfaceGuid: %ws\n"
              "    Cost: %ws\n"
              "    DataLimit (MB): %ws\n"
              "    InboundBandwidth (Kbps): %ws\n"
              "    OutboundBandwidth (Kbps): %ws\n"
              "    MaxTransferSize (MB): %ws\n"
              "    NextBillingCycle: %ws\n"
              "    UsageData LastSyncTime: %ws\n"
              "    UsageData Usage (MB): %ws\n",
    v13,
    v12,
    v8,
    v11,
    v10,
    v18,
    v19,
    v20,
    v9);
  v14 = v5 | 0x20;
  std::wstring::_Tidy_deallocate((__int64)v26);
  std::wstring::_Tidy_deallocate((__int64)v27);
  if ( (v14 & 0x10) != 0 )
  {
    v14 &= ~0x10u;
    std::wstring::_Tidy_deallocate((__int64)v21);
  }
  if ( (v14 & 8) != 0 )
  {
    v14 &= ~8u;
    std::wstring::_Tidy_deallocate((__int64)v22);
  }
  if ( (v14 & 4) != 0 )
  {
    v14 &= ~4u;
    std::wstring::_Tidy_deallocate((__int64)v23);
  }
  if ( (v14 & 2) != 0 )
  {
    v14 &= ~2u;
    std::wstring::_Tidy_deallocate((__int64)v24);
  }
  std::wstring::_Tidy_deallocate((__int64)v28);
  std::wstring::_Tidy_deallocate((__int64)v29);
  if ( (v14 & 1) != 0 )
    std::wstring::_Tidy_deallocate((__int64)v25);
  return a2;
}

```

## disassembly

```asm
0x18001101c  mov     [rsp-8+arg_0], rbx
0x180011021  push    rbp
0x180011022  push    rsi
0x180011023  push    rdi
0x180011024  push    r12
0x180011026  push    r13
0x180011028  push    r14
0x18001102a  push    r15
0x18001102c  lea     rbp, [rsp-0F0h]
0x180011034  sub     rsp, 1F0h
0x18001103b  mov     rax, cs:__security_cookie
0x180011042  xor     rax, rsp
0x180011045  mov     [rbp+120h+var_40], rax
0x18001104c  mov     rbx, r8
0x18001104f  mov     r14, rdx
0x180011052  mov     [rsp+220h+var_1B0], rdx
0x180011057  xor     edi, edi
0x180011059  mov     [rsp+220h+var_1C0], edi
0x18001105d  mov     [rbp+120h+var_48], edi
0x180011063  mov     rax, [r8]
0x180011066  xor     r8d, r8d
0x180011069  lea     rdx, [rbp+120h+var_48]
0x180011070  mov     rcx, rbx
0x180011073  mov     rax, [rax+18h]
0x180011077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001107c  mov     rcx, [rbp+128h]; this
0x180011083  test    eax, eax
0x180011085  jns     short loc_18001109C
0x180011087  mov     r9d, eax; char *
0x18001108a  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x180011091  mov     edx, 22Ch; void *
0x180011096  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001109c  mov     eax, [rbp+120h+var_48]
0x1800110a2  mov     [rsp+220h+var_1BC], eax
0x1800110a6  xorps   xmm0, xmm0
0x1800110a9  xor     eax, eax
0x1800110ab  movups  [rbp+120h+var_80], xmm0
0x1800110b2  movups  [rbp+120h+var_70], xmm0
0x1800110b9  movups  [rbp+120h+var_60], xmm0
0x1800110c0  mov     [rbp+120h+var_50], rax
0x1800110c7  mov     rax, [rbx]
0x1800110ca  xor     r8d, r8d
0x1800110cd  lea     rdx, [rbp+120h+var_80]
0x1800110d4  mov     rcx, rbx
0x1800110d7  mov     rax, [rax+20h]
0x1800110db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110e0  mov     rcx, [rbp+128h]; this
0x1800110e7  test    eax, eax
0x1800110e9  jns     short loc_180011100
0x1800110eb  mov     r9d, eax; char *
0x1800110ee  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x1800110f5  mov     edx, 230h; void *
0x1800110fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011100  lea     rsi, a1; "-1"
0x180011107  mov     edx, dword ptr [rbp+120h+var_70]
0x18001110d  or      ebx, 0FFFFFFFFh
0x180011110  cmp     edx, ebx
0x180011112  jnz     short loc_180011119
0x180011114  mov     r15, rsi
0x180011117  jmp     short loc_180011138
0x180011119  lea     rcx, [rbp+120h+var_120]
0x18001111d  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x180011122  nop
0x180011123  mov     edi, 41h ; 'A'
0x180011128  mov     [rsp+220h+var_1C0], edi
0x18001112c  lea     rcx, [rbp+120h+var_120]
0x180011130  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180011135  mov     r15, rax
0x180011138  lea     rdx, [rbp+120h+var_70+4]
0x18001113f  lea     rcx, [rbp+120h+var_A0]
0x180011146  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_FILETIME@@@Z; ToString(_FILETIME const &)
0x18001114b  nop
0x18001114c  mov     rcx, rax
0x18001114f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180011154  mov     [rsp+220h+var_1A8], rax
0x180011159  lea     rdx, [rbp+120h+var_60+8]
0x180011160  lea     rcx, [rbp+120h+var_C0]
0x180011164  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_FILETIME@@@Z; ToString(_FILETIME const &)
0x180011169  nop
0x18001116a  mov     rcx, rax
0x18001116d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180011172  mov     [rsp+220h+var_1B0], rax
0x180011177  mov     rdx, [rbp+120h+var_50]
0x18001117e  cmp     edx, ebx
0x180011180  jnz     short loc_180011189
0x180011182  mov     [rsp+220h+var_1B8], rsi
0x180011187  jmp     short loc_1800111AB
0x180011189  lea     rcx, [rbp+120h+var_140]
0x18001118d  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x180011192  bts     edi, 8
0x180011196  or      edi, 2
0x180011199  mov     [rsp+220h+var_1C0], edi
0x18001119d  lea     rcx, [rbp+120h+var_140]
0x1800111a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800111a6  mov     [rsp+220h+var_1B8], rax
0x1800111ab  mov     edx, dword ptr [rbp+120h+var_60+4]
0x1800111b1  cmp     edx, ebx
0x1800111b3  jnz     short loc_1800111BA
0x1800111b5  mov     r13, rsi
0x1800111b8  jmp     short loc_1800111DA
0x1800111ba  lea     rcx, [rbp+120h+var_160]
0x1800111be  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x1800111c3  bts     edi, 0Ah
0x1800111c7  or      edi, 4
0x1800111ca  mov     [rsp+220h+var_1C0], edi
0x1800111ce  lea     rcx, [rbp+120h+var_160]
0x1800111d2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800111d7  mov     r13, rax
0x1800111da  mov     edx, dword ptr [rbp+120h+var_60]
0x1800111e0  cmp     edx, ebx
0x1800111e2  jnz     short loc_1800111E9
0x1800111e4  mov     r12, rsi
0x1800111e7  jmp     short loc_180011209
0x1800111e9  lea     rcx, [rbp+120h+var_180]
0x1800111ed  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x1800111f2  bts     edi, 0Ch
0x1800111f6  or      edi, 8
0x1800111f9  mov     [rsp+220h+var_1C0], edi
0x1800111fd  lea     rcx, [rbp+120h+var_180]
0x180011201  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180011206  mov     r12, rax
0x180011209  mov     edx, dword ptr [rbp+120h+var_70+0Ch]
0x18001120f  cmp     edx, ebx
0x180011211  jz      short loc_180011233
0x180011213  lea     rcx, [rbp+120h+var_1A0]
0x180011217  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x18001121c  bts     edi, 0Eh
0x180011220  or      edi, 10h
0x180011223  mov     [rsp+220h+var_1C0], edi
0x180011227  lea     rcx, [rbp+120h+var_1A0]
0x18001122b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180011230  mov     rsi, rax
0x180011233  lea     rdx, [rsp+220h+var_1BC]
0x180011238  lea     rcx, [rbp+120h+var_E0]
0x18001123c  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4NLM_CONNECTION_COST@@@Z; ToString(NLM_CONNECTION_COST const &)
0x180011241  nop
0x180011242  mov     rcx, rax
0x180011245  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001124a  mov     rbx, rax
0x18001124d  lea     rdx, [rbp+120h+var_80]
0x180011254  lea     rcx, [rbp+120h+var_100]
0x180011258  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x18001125d  nop
0x18001125e  mov     rcx, rax
0x180011261  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180011266  mov     [rsp+220h+var_1D0], r15
0x18001126b  mov     rcx, [rsp+220h+var_1A8]
0x180011270  mov     [rsp+220h+var_1D8], rcx
0x180011275  mov     rcx, [rsp+220h+var_1B0]
0x18001127a  mov     [rsp+220h+var_1E0], rcx
0x18001127f  mov     rcx, [rsp+220h+var_1B8]
0x180011284  mov     [rsp+220h+var_1E8], rcx
0x180011289  mov     [rsp+220h+var_1F0], r13
0x18001128e  mov     [rsp+220h+var_1F8], r12
0x180011293  mov     [rsp+220h+var_200], rsi
0x180011298  mov     r9, rbx
0x18001129b  mov     r8, rax
0x18001129e  lea     rdx, aInetworkcostma; "\n >>>>>> INetworkCostManager Cost Info"...
0x1800112a5  mov     rcx, r14
0x1800112a8  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x1800112ad  or      edi, 20h
0x1800112b0  lea     rcx, [rbp+120h+var_100]
0x1800112b4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800112b9  nop
0x1800112ba  lea     rcx, [rbp+120h+var_E0]
0x1800112be  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800112c3  nop
0x1800112c4  test    dil, 10h
0x1800112c8  jz      short loc_1800112D7
0x1800112ca  and     edi, 0FFFFFFEFh
0x1800112cd  lea     rcx, [rbp+120h+var_1A0]
0x1800112d1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800112d6  nop
0x1800112d7  test    dil, 8
0x1800112db  jz      short loc_1800112EA
0x1800112dd  and     edi, 0FFFFFFF7h
0x1800112e0  lea     rcx, [rbp+120h+var_180]
0x1800112e4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800112e9  nop
0x1800112ea  test    dil, 4
0x1800112ee  jz      short loc_1800112FD
0x1800112f0  and     edi, 0FFFFFFFBh
0x1800112f3  lea     rcx, [rbp+120h+var_160]
0x1800112f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800112fc  nop
0x1800112fd  test    dil, 2
0x180011301  jz      short loc_180011310
0x180011303  and     edi, 0FFFFFFFDh
0x180011306  lea     rcx, [rbp+120h+var_140]
0x18001130a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001130f  nop
0x180011310  lea     rcx, [rbp+120h+var_C0]
0x180011314  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011319  nop
0x18001131a  lea     rcx, [rbp+120h+var_A0]
0x180011321  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011326  nop
0x180011327  test    dil, 1
0x18001132b  jz      short loc_180011336
0x18001132d  lea     rcx, [rbp+120h+var_120]
0x180011331  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011336  mov     rax, r14
0x180011339  mov     rcx, [rbp+120h+var_40]
0x180011340  xor     rcx, rsp; StackCookie
0x180011343  call    __security_check_cookie
0x180011348  mov     rbx, [rsp+220h+arg_0]
0x180011350  add     rsp, 1F0h
0x180011357  pop     r15
0x180011359  pop     r14
0x18001135b  pop     r13
0x18001135d  pop     r12
0x18001135f  pop     rdi
0x180011360  pop     rsi
0x180011361  pop     rbp
0x180011362  retn
```
