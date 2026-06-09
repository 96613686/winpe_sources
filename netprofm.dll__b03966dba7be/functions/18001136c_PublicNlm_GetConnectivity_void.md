# PublicNlm::GetConnectivity(void)

- ea: `0x18001136c`
- end: `0x1800114bb`
- name: `?GetConnectivity@PublicNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x180010124`
- `0x18001136c`
- `0x1800114c4`
- `0x180011614`
- `0x1800120d0`
- `0x18002a928`
- `0x180043010`

## string_xrefs

- `0x1800113be`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x1800113f3`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`
- `0x180011428`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PublicNlm::GetConnectivity(_QWORD *a1, __int64 a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  const wchar_t *v7; // rdi
  const wchar_t *v8; // rbx
  __int64 v9; // rax
  int v11; // [rsp+20h] [rbp-50h]
  _BYTE v12[32]; // [rsp+38h] [rbp-38h] BYREF
  _WORD v13[2]; // [rsp+58h] [rbp-18h] BYREF
  __int16 v14; // [rsp+5Ch] [rbp-14h] BYREF
  _DWORD v15[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v15[1] = HIDWORD(a2);
  v15[0] = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)*a1 + 104LL))(*a1, v15);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v4,
      v11);
  v14 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int16 *))(*(_QWORD *)*a1 + 96LL))(*a1, &v14);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v5,
      v11);
  v13[0] = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _WORD *))(*(_QWORD *)*a1 + 88LL))(*a1, v13);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v6,
      v11);
  v7 = L"True";
  v8 = L"True";
  if ( !v13[0] )
    v8 = L"False";
  if ( !v14 )
    v7 = L"False";
  ToString(v12, v15);
  v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>(
    a2,
    (__int64)L"\n"
              " >>>>>> NLM Connectivity <<<<<<\n"
              "  > Connectivity: %ws\n"
              "  > IsConnected: %ws\n"
              "  > IsConnectedToInternet: %ws\n",
    v9,
    v7,
    v8);
  std::wstring::_Tidy_deallocate((__int64)v12);
  return a2;
}

```

## disassembly

```asm
0x18001136c  mov     [rsp-18h+arg_10], rbx
0x180011371  mov     [rsp-18h+arg_18], rsi
0x180011376  push    rbp
0x180011377  push    rdi
0x180011378  push    r14
0x18001137a  mov     rbp, rsp
0x18001137d  sub     rsp, 70h
0x180011381  mov     rax, cs:__security_cookie
0x180011388  xor     rax, rsp
0x18001138b  mov     [rbp+var_8], rax
0x18001138f  mov     rsi, rdx
0x180011392  mov     rbx, rcx
0x180011395  mov     [rbp+var_10], rdx
0x180011399  xor     r14d, r14d
0x18001139c  mov     dword ptr [rbp+var_10], r14d
0x1800113a0  mov     rcx, [rcx]
0x1800113a3  mov     rax, [rcx]
0x1800113a6  lea     rdx, [rbp+var_10]
0x1800113aa  mov     rax, [rax+68h]
0x1800113ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b3  mov     rcx, [rbp+18h]; this
0x1800113b7  test    eax, eax
0x1800113b9  jns     short loc_1800113D0
0x1800113bb  mov     r9d, eax; char *
0x1800113be  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x1800113c5  mov     edx, 0BBh; void *
0x1800113ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800113d0  mov     [rbp+var_14], r14w
0x1800113d5  mov     rcx, [rbx]
0x1800113d8  mov     rax, [rcx]
0x1800113db  lea     rdx, [rbp+var_14]
0x1800113df  mov     rax, [rax+60h]
0x1800113e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113e8  mov     rcx, [rbp+18h]; this
0x1800113ec  test    eax, eax
0x1800113ee  jns     short loc_180011405
0x1800113f0  mov     r9d, eax; char *
0x1800113f3  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x1800113fa  mov     edx, 0BEh; void *
0x1800113ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011405  mov     [rbp+var_18], r14w
0x18001140a  mov     rcx, [rbx]
0x18001140d  mov     rax, [rcx]
0x180011410  lea     rdx, [rbp+var_18]
0x180011414  mov     rax, [rax+58h]
0x180011418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001141d  mov     rcx, [rbp+18h]; this
0x180011421  test    eax, eax
0x180011423  jns     short loc_18001143A
0x180011425  mov     r9d, eax; char *
0x180011428  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18001142f  mov     edx, 0C1h; void *
0x180011434  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001143a  lea     rdi, aTrue_1; "True"
0x180011441  mov     rbx, rdi
0x180011444  lea     rax, aFalse_1; "False"
0x18001144b  cmp     [rbp+var_18], r14w
0x180011450  cmovz   rbx, rax
0x180011454  cmp     [rbp+var_14], r14w
0x180011459  cmovz   rdi, rax
0x18001145d  lea     rdx, [rbp+var_10]
0x180011461  lea     rcx, [rbp+var_38]
0x180011465  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4NLM_CONNECTIVITY@@@Z; ToString(NLM_CONNECTIVITY const &)
0x18001146a  nop
0x18001146b  mov     rcx, rax
0x18001146e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180011473  mov     qword ptr [rsp+70h+var_50], rbx
0x180011478  mov     r9, rdi
0x18001147b  mov     r8, rax
0x18001147e  lea     rdx, aNlmConnectivit; "\n >>>>>> NLM Connectivity <<<<<<\n  > "...
0x180011485  mov     rcx, rsi
0x180011488  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18001148d  nop
0x18001148e  lea     rcx, [rbp+var_38]
0x180011492  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011497  mov     rax, rsi
0x18001149a  mov     rcx, [rbp+var_8]
0x18001149e  xor     rcx, rsp; StackCookie
0x1800114a1  call    __security_check_cookie
0x1800114a6  lea     r11, [rsp+70h+var_s0]
0x1800114ab  mov     rbx, [r11+30h]
0x1800114af  mov     rsi, [r11+38h]
0x1800114b3  mov     rsp, r11
0x1800114b6  pop     r14
0x1800114b8  pop     rdi
0x1800114b9  pop     rbp
0x1800114ba  retn
```
