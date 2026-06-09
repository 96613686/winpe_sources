# PublicNlm::Log(INetworkConnection *,ulong)

- ea: `0x18003e780`
- end: `0x18003ea12`
- name: `?Log@PublicNlm@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUINetworkConnection@@K@Z`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callers

- `0x18000f424`

## callees

- `0x18000f0ec`
- `0x18000f388`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x1800114c4`
- `0x180011614`
- `0x1800120d0`
- `0x18002a928`
- `0x180034dac`
- `0x1800384d0`
- `0x18003a37c`
- `0x18003e780`
- `0x18003ec6c`
- `0x180043010`

## string_xrefs

- `0x18003e7d7`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18003e80e`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18003e845`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x18003e87c`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PublicNlm::Log(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // r14
  const wchar_t *v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  int v20; // [rsp+20h] [rbp-B9h]
  _BYTE v21[32]; // [rsp+48h] [rbp-91h] BYREF
  _BYTE v22[32]; // [rsp+68h] [rbp-71h] BYREF
  _BYTE v23[32]; // [rsp+88h] [rbp-51h] BYREF
  __int64 v24; // [rsp+A8h] [rbp-31h] BYREF
  enum NLM_DOMAIN_TYPE v25; // [rsp+B0h] [rbp-29h] BYREF
  int v26; // [rsp+B4h] [rbp-25h] BYREF
  __int128 v27; // [rsp+B8h] [rbp-21h] BYREF
  __int128 v28; // [rsp+C8h] [rbp-11h] BYREF
  _BYTE v29[32]; // [rsp+D8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v24 = a2;
  v28 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a3 + 96LL))(a3, &v28);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v7,
      v20);
  v27 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a3 + 88LL))(a3, &v27);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v8,
      v20);
  v26 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 80LL))(a3, &v26);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v9,
      v20);
  v25 = NLM_DOMAIN_TYPE_NON_DOMAIN_NETWORK;
  v10 = (*(__int64 (__fastcall **)(__int64, enum NLM_DOMAIN_TYPE *))(*(_QWORD *)a3 + 104LL))(a3, &v25);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v10,
      v20);
  std::wstring::wstring((__int64)v29);
  v24 = 0;
  v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a3)(
          a3,
          &GUID_00e676ed_5a35_4738_92eb_8581738d0f0a,
          &v24);
  if ( v11 < 0 )
  {
    v12 = wil::str_printf<std::wstring>(
            (__int64)v21,
            (__int64)L"  ! <INetworkConnection2::QueryInterface(INetworkConnenction2) failed (0x%x)>",
            (unsigned int)v11);
    std::wstring::operator=((__int64)v29, v12);
    std::wstring::_Tidy_deallocate((__int64)v21);
  }
  if ( v24 )
  {
    std::wstring::push_back(v29);
    LogINetworkConnection2(v21, v24, a4);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)v21);
  }
  v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v14 = ToString(&v25);
  ToString(v23, &v26);
  v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v22, &v27);
  v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v21, &v28);
  v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>(
    a2,
    (__int64)L"\n"
              " >>>>>> INetworkConnection Enumerated Interface [%u] <<<<<< \n"
              "    AdapterId (Interface GUID): %ws\n"
              "    ConnectionId: %ws\n"
              "    NLM Connectivity: %ws\n"
              "    NLM Domain Type: %ws\n"
              "%ws",
    a4,
    v17,
    v16,
    v15,
    v14,
    v13);
  std::wstring::_Tidy_deallocate((__int64)v21);
  std::wstring::_Tidy_deallocate((__int64)v22);
  std::wstring::_Tidy_deallocate((__int64)v23);
  v18 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  std::wstring::_Tidy_deallocate((__int64)v29);
  return a2;
}

```

## disassembly

```asm
0x18003e780  push    rbp
0x18003e782  push    rbx
0x18003e783  push    rsi
0x18003e784  push    rdi
0x18003e785  push    r12
0x18003e787  push    r14
0x18003e789  push    r15
0x18003e78b  lea     rbp, [rsp-27h]
0x18003e790  sub     rsp, 100h
0x18003e797  mov     rax, cs:__security_cookie
0x18003e79e  xor     rax, rsp
0x18003e7a1  mov     [rbp+57h+var_38], rax
0x18003e7a5  mov     r12d, r9d
0x18003e7a8  mov     rbx, r8
0x18003e7ab  mov     r15, rdx
0x18003e7ae  mov     [rbp+57h+var_88], rdx
0x18003e7b2  xorps   xmm0, xmm0
0x18003e7b5  movups  [rbp+57h+var_68], xmm0
0x18003e7b9  mov     rax, [r8]
0x18003e7bc  lea     rdx, [rbp+57h+var_68]
0x18003e7c0  mov     rcx, r8
0x18003e7c3  mov     rax, [rax+60h]
0x18003e7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7cc  mov     rcx, [rbp+5Fh]; this
0x18003e7d0  test    eax, eax
0x18003e7d2  jns     short loc_18003E7E9
0x18003e7d4  mov     r9d, eax; char *
0x18003e7d7  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18003e7de  mov     edx, 138h; void *
0x18003e7e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e7e9  xorps   xmm0, xmm0
0x18003e7ec  movups  [rbp+57h+var_78], xmm0
0x18003e7f0  mov     rax, [rbx]
0x18003e7f3  lea     rdx, [rbp+57h+var_78]
0x18003e7f7  mov     rcx, rbx
0x18003e7fa  mov     rax, [rax+58h]
0x18003e7fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e803  mov     rcx, [rbp+5Fh]; this
0x18003e807  test    eax, eax
0x18003e809  jns     short loc_18003E820
0x18003e80b  mov     r9d, eax; char *
0x18003e80e  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18003e815  mov     edx, 13Bh; void *
0x18003e81a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e820  mov     [rbp+57h+var_7C], 0
0x18003e827  mov     rax, [rbx]
0x18003e82a  lea     rdx, [rbp+57h+var_7C]
0x18003e82e  mov     rcx, rbx
0x18003e831  mov     rax, [rax+50h]
0x18003e835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e83a  mov     rcx, [rbp+5Fh]; this
0x18003e83e  test    eax, eax
0x18003e840  jns     short loc_18003E857
0x18003e842  mov     r9d, eax; char *
0x18003e845  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18003e84c  mov     edx, 13Eh; void *
0x18003e851  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e857  mov     [rbp+57h+var_80], 0
0x18003e85e  mov     rax, [rbx]
0x18003e861  lea     rdx, [rbp+57h+var_80]
0x18003e865  mov     rcx, rbx
0x18003e868  mov     rax, [rax+68h]
0x18003e86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e871  mov     rcx, [rbp+5Fh]; this
0x18003e875  test    eax, eax
0x18003e877  jns     short loc_18003E88E
0x18003e879  mov     r9d, eax; char *
0x18003e87c  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18003e883  mov     edx, 141h; void *
0x18003e888  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e88e  lea     rcx, [rbp+57h+var_58]
0x18003e892  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003e897  nop
0x18003e898  mov     [rbp+57h+var_88], 0
0x18003e8a0  mov     rax, [rbx]
0x18003e8a3  lea     r8, [rbp+57h+var_88]
0x18003e8a7  lea     rdx, _GUID_00e676ed_5a35_4738_92eb_8581738d0f0a
0x18003e8ae  mov     rcx, rbx
0x18003e8b1  mov     rax, [rax]
0x18003e8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8b9  test    eax, eax
0x18003e8bb  jns     short loc_18003E8E7
0x18003e8bd  mov     r8d, eax
0x18003e8c0  lea     rdx, aInetworkconnec_6; "  ! <INetworkConnection2::QueryInterfac"...
0x18003e8c7  lea     rcx, [rsp+130h+var_E8]
0x18003e8cc  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003e8d1  mov     rdx, rax
0x18003e8d4  lea     rcx, [rbp+57h+var_58]
0x18003e8d8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003e8dd  lea     rcx, [rsp+130h+var_E8]
0x18003e8e2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e8e7  cmp     [rbp+57h+var_88], 0
0x18003e8ec  jz      short loc_18003E920
0x18003e8ee  lea     rcx, [rbp+57h+var_58]
0x18003e8f2  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x18003e8f7  mov     r8d, r12d
0x18003e8fa  mov     rdx, [rbp+57h+var_88]
0x18003e8fe  lea     rcx, [rsp+130h+var_E8]
0x18003e903  call    LogINetworkConnection2
0x18003e908  nop
0x18003e909  mov     rdx, rax
0x18003e90c  lea     rcx, [rbp+57h+var_58]
0x18003e910  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003e915  nop
0x18003e916  lea     rcx, [rsp+130h+var_E8]
0x18003e91b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e920  lea     rcx, [rbp+57h+var_58]
0x18003e924  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003e929  mov     r14, rax
0x18003e92c  lea     rcx, [rbp+57h+var_80]; enum NLM_DOMAIN_TYPE *
0x18003e930  call    ?ToString@@YAPEB_WAEBW4NLM_DOMAIN_TYPE@@@Z; ToString(NLM_DOMAIN_TYPE const &)
0x18003e935  mov     rsi, rax
0x18003e938  lea     rdx, [rbp+57h+var_7C]
0x18003e93c  lea     rcx, [rbp+57h+var_A8]
0x18003e940  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4NLM_CONNECTIVITY@@@Z; ToString(NLM_CONNECTIVITY const &)
0x18003e945  nop
0x18003e946  mov     rcx, rax
0x18003e949  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003e94e  mov     rdi, rax
0x18003e951  lea     rdx, [rbp+57h+var_78]
0x18003e955  lea     rcx, [rbp+57h+var_C8]
0x18003e959  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x18003e95e  nop
0x18003e95f  mov     rcx, rax
0x18003e962  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003e967  mov     rbx, rax
0x18003e96a  lea     rdx, [rbp+57h+var_68]
0x18003e96e  lea     rcx, [rsp+130h+var_E8]
0x18003e973  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x18003e978  nop
0x18003e979  mov     rcx, rax
0x18003e97c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003e981  mov     [rsp+130h+var_F8], r14
0x18003e986  mov     [rsp+130h+var_100], rsi
0x18003e98b  mov     [rsp+130h+var_108], rdi
0x18003e990  mov     [rsp+130h+var_110], rbx
0x18003e995  mov     r9, rax
0x18003e998  mov     r8d, r12d
0x18003e99b  lea     rdx, aInetworkconnec; "\n >>>>>> INetworkConnection Enumerated"...
0x18003e9a2  mov     rcx, r15
0x18003e9a5  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003e9aa  nop
0x18003e9ab  lea     rcx, [rsp+130h+var_E8]
0x18003e9b0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e9b5  nop
0x18003e9b6  lea     rcx, [rbp+57h+var_C8]
0x18003e9ba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e9bf  nop
0x18003e9c0  lea     rcx, [rbp+57h+var_A8]
0x18003e9c4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e9c9  nop
0x18003e9ca  mov     rcx, [rbp+57h+var_88]
0x18003e9ce  test    rcx, rcx
0x18003e9d1  jz      short loc_18003E9E8
0x18003e9d3  mov     [rbp+57h+var_88], 0
0x18003e9db  mov     rdx, [rcx]
0x18003e9de  mov     rax, [rdx+10h]
0x18003e9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9e7  nop
0x18003e9e8  lea     rcx, [rbp+57h+var_58]
0x18003e9ec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e9f1  mov     rax, r15
0x18003e9f4  mov     rcx, [rbp+57h+var_38]
0x18003e9f8  xor     rcx, rsp; StackCookie
0x18003e9fb  call    __security_check_cookie
0x18003ea00  add     rsp, 100h
0x18003ea07  pop     r15
0x18003ea09  pop     r14
0x18003ea0b  pop     r12
0x18003ea0d  pop     rdi
0x18003ea0e  pop     rsi
0x18003ea0f  pop     rbx
0x18003ea10  pop     rbp
0x18003ea11  retn
```
