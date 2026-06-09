# PublicNlm::Log(INetworkConnectionCost *,ulong)

- ea: `0x180010164`
- end: `0x1800104af`
- name: `?Log@PublicNlm@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkConnectionCost@@K@Z`
- size: `843`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x18000ef20`

## callees

- `0x18000f388`
- `0x180010124`
- `0x180010164`
- `0x180011614`
- `0x1800120d0`
- `0x18002a928`
- `0x18002b654`
- `0x18003a2ac`
- `0x18003a37c`
- `0x18003ea18`
- `0x180043010`

## string_xrefs

- `0x1800101d4`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18001022b`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall PublicNlm::Log(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  char v6; // di
  int v7; // eax
  int v8; // eax
  const wchar_t *v9; // rsi
  const wchar_t *v10; // r15
  const wchar_t *v11; // r13
  const wchar_t *v12; // r12
  __int64 v13; // rbx
  __int64 v14; // rax
  char v15; // di
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v19; // [rsp+68h] [rbp-98h]
  const wchar_t *v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+80h] [rbp-80h]
  _BYTE v23[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v24[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v25[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v26[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v27[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v28[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v29[32]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v30[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v31[32]; // [rsp+188h] [rbp+88h] BYREF
  __int128 v32; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v33; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v34; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v35; // [rsp+1D8h] [rbp+D8h]
  int v36; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v19 = a4;
  v21 = a2;
  v6 = 0;
  v36 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 24LL))(a3, &v36);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20D,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v7,
      v17);
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a3 + 32LL))(a3, &v32);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v8,
      v17);
  v9 = L"-1";
  if ( (_DWORD)v33 == -1 )
  {
    v10 = L"-1";
  }
  else
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v27);
    v6 = 65;
    v10 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  ToString(v31, (char *)&v33 + 4);
  v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v30, (char *)&v34 + 8);
  v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  if ( (_DWORD)v35 == -1 )
  {
    v20 = L"-1";
  }
  else
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v26);
    v6 |= 2u;
    v20 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  if ( DWORD1(v34) == -1 )
  {
    v11 = L"-1";
  }
  else
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v25);
    v6 |= 4u;
    v11 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  if ( (_DWORD)v34 == -1 )
  {
    v12 = L"-1";
  }
  else
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v24);
    v6 |= 8u;
    v12 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  if ( HIDWORD(v33) != -1 )
  {
    std::_Integral_to_string<wchar_t,unsigned long>(v23);
    v6 |= 0x10u;
    v9 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  }
  v18 = v36;
  ToString(v29, &v18);
  v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v28, &v32);
  v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>(
    a2,
    (__int64)L"\n"
              " >>>>>> INetworkConnectionCost Enumerated Interface [%u] <<<<<<\n"
              "    InterfaceGuid: %ws\n"
              "    Cost: %ws\n"
              "    DataLimit (MB): %ws\n"
              "    InboundBandwidth (Kbps): %ws\n"
              "    OutboundBandwidth (Kbps): %ws\n"
              "    MaxTransferSize (MB): %ws\n"
              "    NextBillingCycle: %ws\n"
              "    UsageData LastSyncTime: %ws\n"
              "    UsageData Usage (MB): %ws\n",
    v19,
    v14,
    v13,
    v9,
    v12,
    v11,
    v20,
    v21,
    v22,
    v10);
  v15 = v6 | 0x20;
  std::wstring::_Tidy_deallocate((__int64)v28);
  std::wstring::_Tidy_deallocate((__int64)v29);
  if ( (v15 & 0x10) != 0 )
  {
    v15 &= ~0x10u;
    std::wstring::_Tidy_deallocate((__int64)v23);
  }
  if ( (v15 & 8) != 0 )
  {
    v15 &= ~8u;
    std::wstring::_Tidy_deallocate((__int64)v24);
  }
  if ( (v15 & 4) != 0 )
  {
    v15 &= ~4u;
    std::wstring::_Tidy_deallocate((__int64)v25);
  }
  if ( (v15 & 2) != 0 )
  {
    v15 &= ~2u;
    std::wstring::_Tidy_deallocate((__int64)v26);
  }
  std::wstring::_Tidy_deallocate((__int64)v30);
  std::wstring::_Tidy_deallocate((__int64)v31);
  if ( (v15 & 1) != 0 )
    std::wstring::_Tidy_deallocate((__int64)v27);
  return a2;
}

```

## disassembly

```asm
0x180010164  mov     [rsp-8+arg_0], rbx
0x180010169  push    rbp
0x18001016a  push    rsi
0x18001016b  push    rdi
0x18001016c  push    r12
0x18001016e  push    r13
0x180010170  push    r14
0x180010172  push    r15
0x180010174  lea     rbp, [rsp-0F0h]
0x18001017c  sub     rsp, 1F0h
0x180010183  mov     rax, cs:__security_cookie
0x18001018a  xor     rax, rsp
0x18001018d  mov     [rbp+120h+var_38], rax
0x180010194  mov     [rsp+220h+var_1B8], r9d
0x180010199  mov     rbx, r8
0x18001019c  mov     r14, rdx
0x18001019f  mov     [rsp+220h+var_1A8], rdx
0x1800101a4  xor     edi, edi
0x1800101a6  mov     [rsp+220h+var_1C0], edi
0x1800101aa  mov     [rbp+120h+var_40], edi
0x1800101b0  mov     rax, [r8]
0x1800101b3  lea     rdx, [rbp+120h+var_40]
0x1800101ba  mov     rcx, r8
0x1800101bd  mov     rax, [rax+18h]
0x1800101c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c6  mov     rcx, [rbp+128h]; this
0x1800101cd  test    eax, eax
0x1800101cf  jns     short loc_1800101E6
0x1800101d1  mov     r9d, eax; char *
0x1800101d4  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x1800101db  mov     edx, 20Dh; void *
0x1800101e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800101e6  xorps   xmm0, xmm0
0x1800101e9  xor     eax, eax
0x1800101eb  movups  [rbp+120h+var_78], xmm0
0x1800101f2  movups  [rbp+120h+var_68], xmm0
0x1800101f9  movups  [rbp+120h+var_58], xmm0
0x180010200  mov     [rbp+120h+var_48], rax
0x180010207  mov     rax, [rbx]
0x18001020a  lea     rdx, [rbp+120h+var_78]
0x180010211  mov     rcx, rbx
0x180010214  mov     rax, [rax+20h]
0x180010218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001021d  mov     rcx, [rbp+128h]; this
0x180010224  test    eax, eax
0x180010226  jns     short loc_18001023D
0x180010228  mov     r9d, eax; char *
0x18001022b  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x180010232  mov     edx, 210h; void *
0x180010237  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001023d  lea     rsi, a1; "-1"
0x180010244  mov     edx, dword ptr [rbp+120h+var_68]
0x18001024a  or      ebx, 0FFFFFFFFh
0x18001024d  cmp     edx, ebx
0x18001024f  jnz     short loc_180010256
0x180010251  mov     r15, rsi
0x180010254  jmp     short loc_180010275
0x180010256  lea     rcx, [rbp+120h+var_118]
0x18001025a  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x18001025f  nop
0x180010260  mov     edi, 41h ; 'A'
0x180010265  mov     [rsp+220h+var_1C0], edi
0x180010269  lea     rcx, [rbp+120h+var_118]
0x18001026d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180010272  mov     r15, rax
0x180010275  lea     rdx, [rbp+120h+var_68+4]
0x18001027c  lea     rcx, [rbp+120h+var_98]
0x180010283  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_FILETIME@@@Z; ToString(_FILETIME const &)
0x180010288  nop
0x180010289  mov     rcx, rax
0x18001028c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180010291  mov     [rbp+120h+var_1A0], rax
0x180010295  lea     rdx, [rbp+120h+var_58+8]
0x18001029c  lea     rcx, [rbp+120h+var_B8]
0x1800102a0  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_FILETIME@@@Z; ToString(_FILETIME const &)
0x1800102a5  nop
0x1800102a6  mov     rcx, rax
0x1800102a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800102ae  mov     [rsp+220h+var_1A8], rax
0x1800102b3  mov     rdx, [rbp+120h+var_48]
0x1800102ba  cmp     edx, ebx
0x1800102bc  jnz     short loc_1800102C5
0x1800102be  mov     [rsp+220h+var_1B0], rsi
0x1800102c3  jmp     short loc_1800102E7
0x1800102c5  lea     rcx, [rbp+120h+var_138]
0x1800102c9  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x1800102ce  bts     edi, 8
0x1800102d2  or      edi, 2
0x1800102d5  mov     [rsp+220h+var_1C0], edi
0x1800102d9  lea     rcx, [rbp+120h+var_138]
0x1800102dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800102e2  mov     [rsp+220h+var_1B0], rax
0x1800102e7  mov     edx, dword ptr [rbp+120h+var_58+4]
0x1800102ed  cmp     edx, ebx
0x1800102ef  jnz     short loc_1800102F6
0x1800102f1  mov     r13, rsi
0x1800102f4  jmp     short loc_180010316
0x1800102f6  lea     rcx, [rbp+120h+var_158]
0x1800102fa  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x1800102ff  bts     edi, 0Ah
0x180010303  or      edi, 4
0x180010306  mov     [rsp+220h+var_1C0], edi
0x18001030a  lea     rcx, [rbp+120h+var_158]
0x18001030e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180010313  mov     r13, rax
0x180010316  mov     edx, dword ptr [rbp+120h+var_58]
0x18001031c  cmp     edx, ebx
0x18001031e  jnz     short loc_180010325
0x180010320  mov     r12, rsi
0x180010323  jmp     short loc_180010345
0x180010325  lea     rcx, [rbp+120h+var_178]
0x180010329  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x18001032e  bts     edi, 0Ch
0x180010332  or      edi, 8
0x180010335  mov     [rsp+220h+var_1C0], edi
0x180010339  lea     rcx, [rbp+120h+var_178]
0x18001033d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180010342  mov     r12, rax
0x180010345  mov     edx, dword ptr [rbp+120h+var_68+0Ch]
0x18001034b  cmp     edx, ebx
0x18001034d  jz      short loc_18001036F
0x18001034f  lea     rcx, [rbp+120h+var_198]
0x180010353  call    ??$_Integral_to_string@_WK@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@K@Z; std::_Integral_to_string<wchar_t,ulong>(ulong)
0x180010358  bts     edi, 0Eh
0x18001035c  or      edi, 10h
0x18001035f  mov     [rsp+220h+var_1C0], edi
0x180010363  lea     rcx, [rbp+120h+var_198]
0x180010367  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001036c  mov     rsi, rax
0x18001036f  mov     eax, [rbp+120h+var_40]
0x180010375  mov     [rsp+220h+var_1BC], eax
0x180010379  lea     rdx, [rsp+220h+var_1BC]
0x18001037e  lea     rcx, [rbp+120h+var_D8]
0x180010382  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4NLM_CONNECTION_COST@@@Z; ToString(NLM_CONNECTION_COST const &)
0x180010387  nop
0x180010388  mov     rcx, rax
0x18001038b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180010390  mov     rbx, rax
0x180010393  lea     rdx, [rbp+120h+var_78]
0x18001039a  lea     rcx, [rbp+120h+var_F8]
0x18001039e  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x1800103a3  nop
0x1800103a4  mov     rcx, rax
0x1800103a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800103ac  mov     [rsp+220h+var_1C8], r15
0x1800103b1  mov     rcx, [rbp+120h+var_1A0]
0x1800103b5  mov     [rsp+220h+var_1D0], rcx
0x1800103ba  mov     rcx, [rsp+220h+var_1A8]
0x1800103bf  mov     [rsp+220h+var_1D8], rcx
0x1800103c4  mov     rcx, [rsp+220h+var_1B0]
0x1800103c9  mov     [rsp+220h+var_1E0], rcx
0x1800103ce  mov     [rsp+220h+var_1E8], r13
0x1800103d3  mov     [rsp+220h+var_1F0], r12
0x1800103d8  mov     [rsp+220h+var_1F8], rsi
0x1800103dd  mov     [rsp+220h+var_200], rbx
0x1800103e2  mov     r9, rax
0x1800103e5  mov     r8d, [rsp+220h+var_1B8]
0x1800103ea  lea     rdx, aInetworkconnec_3; "\n >>>>>> INetworkConnectionCost Enumer"...
0x1800103f1  mov     rcx, r14
0x1800103f4  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x1800103f9  or      edi, 20h
0x1800103fc  lea     rcx, [rbp+120h+var_F8]
0x180010400  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010405  nop
0x180010406  lea     rcx, [rbp+120h+var_D8]
0x18001040a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001040f  nop
0x180010410  test    dil, 10h
0x180010414  jz      short loc_180010423
0x180010416  and     edi, 0FFFFFFEFh
0x180010419  lea     rcx, [rbp+120h+var_198]
0x18001041d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010422  nop
0x180010423  test    dil, 8
0x180010427  jz      short loc_180010436
0x180010429  and     edi, 0FFFFFFF7h
0x18001042c  lea     rcx, [rbp+120h+var_178]
0x180010430  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010435  nop
0x180010436  test    dil, 4
0x18001043a  jz      short loc_180010449
0x18001043c  and     edi, 0FFFFFFFBh
0x18001043f  lea     rcx, [rbp+120h+var_158]
0x180010443  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010448  nop
0x180010449  test    dil, 2
0x18001044d  jz      short loc_18001045C
0x18001044f  and     edi, 0FFFFFFFDh
0x180010452  lea     rcx, [rbp+120h+var_138]
0x180010456  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001045b  nop
0x18001045c  lea     rcx, [rbp+120h+var_B8]
0x180010460  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010465  nop
0x180010466  lea     rcx, [rbp+120h+var_98]
0x18001046d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010472  nop
0x180010473  test    dil, 1
0x180010477  jz      short loc_180010482
0x180010479  lea     rcx, [rbp+120h+var_118]
0x18001047d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010482  mov     rax, r14
0x180010485  mov     rcx, [rbp+120h+var_38]
0x18001048c  xor     rcx, rsp; StackCookie
0x18001048f  call    __security_check_cookie
0x180010494  mov     rbx, [rsp+220h+arg_0]
0x18001049c  add     rsp, 1F0h
0x1800104a3  pop     r15
0x1800104a5  pop     r14
0x1800104a7  pop     r13
0x1800104a9  pop     r12
0x1800104ab  pop     rdi
0x1800104ac  pop     rsi
0x1800104ad  pop     rbp
0x1800104ae  retn
```
