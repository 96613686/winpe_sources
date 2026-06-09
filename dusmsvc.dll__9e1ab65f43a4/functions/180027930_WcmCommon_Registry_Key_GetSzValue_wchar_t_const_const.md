# WcmCommon::Registry::Key::GetSzValue(wchar_t const * const)

- ea: `0x180027930`
- end: `0x180027a01`
- name: `?GetSzValue@Key@Registry@WcmCommon@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEB_W@Z`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027fbc`
- `0x1800282b0`

## callees

- `0x180007c90`
- `0x18000d6ec`
- `0x18001802c`
- `0x180020820`
- `0x1800257d4`
- `0x180025d94`
- `0x180027930`
- `0x18002d570`
- `0x18002d9a8`

## string_xrefs

- `0x18002798d`: `onecore\private\net\inc\wcm\wcm_registry_key.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WcmCommon::Registry::Key::GetSzValue(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  __int64 v4; // r10
  int Value; // eax
  __int64 v6; // rbx
  __int64 v7; // rax
  int v9; // [rsp+20h] [rbp-38h]
  __int128 v10; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v10 = 0;
  v11 = 0;
  std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(&v10);
  Value = WcmCommon::Registry::Key::_GetValue(v3, v4, v3, &v10);
  if ( Value < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_key.h",
      (const char *)(unsigned int)Value,
      v9);
  v6 = v10;
  if ( (_QWORD)v10 == *((_QWORD *)&v10 + 1) )
  {
    std::wstring::wstring(a2);
  }
  else
  {
    v7 = std::_Find_vectorized<wchar_t,wchar_t>(v10, v10 + 2LL * ((*((_QWORD *)&v10 + 1) - (_QWORD)v10) >> 1), 0);
    std::wstring::wstring(a2, v6, v7);
  }
  std::vector<unsigned char>::_Tidy(&v10);
  return a2;
}

```

## disassembly

```asm
0x180027930  mov     [rsp+arg_18], rbx
0x180027935  push    rdi
0x180027936  sub     rsp, 50h
0x18002793a  mov     rax, cs:__security_cookie
0x180027941  xor     rax, rsp
0x180027944  mov     [rsp+58h+var_10], rax
0x180027949  mov     r10, r8
0x18002794c  mov     rdi, rdx
0x18002794f  mov     r8, rcx
0x180027952  mov     [rsp+58h+var_30], rdx
0x180027957  xorps   xmm0, xmm0
0x18002795a  xor     eax, eax
0x18002795c  movups  [rsp+58h+var_28], xmm0
0x180027961  mov     [rsp+58h+var_18], rax
0x180027966  lea     rcx, [rsp+58h+var_28]
0x18002796b  call    ??0?$vector@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@V?$allocator@V?$vector@PEAU_NLA_DATA@@V?$allocator@PEAU_NLA_DATA@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<_NLA_DATA *>>::vector<std::vector<_NLA_DATA *>>(void)
0x180027970  nop
0x180027971  lea     r9, [rsp+58h+var_28]
0x180027976  mov     rdx, r10
0x180027979  mov     rcx, r8
0x18002797c  call    ?_GetValue@Key@Registry@WcmCommon@@AEBAJQEB_WKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; WcmCommon::Registry::Key::_GetValue(wchar_t const * const,ulong,std::vector<uchar> &)
0x180027981  mov     rcx, [rsp+58h]; this
0x180027986  test    eax, eax
0x180027988  jns     short loc_18002799F
0x18002798a  mov     r9d, eax; char *
0x18002798d  lea     r8, aOnecorePrivate_2; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x180027994  mov     edx, 183h; void *
0x180027999  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002799f  mov     rcx, qword ptr [rsp+58h+var_28+8]
0x1800279a4  mov     rbx, qword ptr [rsp+58h+var_28]
0x1800279a9  cmp     rbx, rcx
0x1800279ac  jz      short loc_1800279D3
0x1800279ae  xor     r8d, r8d
0x1800279b1  sub     rcx, rbx
0x1800279b4  shr     rcx, 1
0x1800279b7  lea     rdx, [rbx+rcx*2]
0x1800279bb  mov     rcx, rbx
0x1800279be  call    ??$_Find_vectorized@_W_W@std@@YAPEA_WQEA_W0_W@Z; std::_Find_vectorized<wchar_t,wchar_t>(wchar_t * const,wchar_t * const,wchar_t)
0x1800279c3  mov     r8, rax
0x1800279c6  mov     rdx, rbx
0x1800279c9  mov     rcx, rdi
0x1800279cc  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x1800279d1  jmp     short loc_1800279DC
0x1800279d3  mov     rcx, rdi
0x1800279d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800279db  nop
0x1800279dc  lea     rcx, [rsp+58h+var_28]
0x1800279e1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800279e6  mov     rax, rdi
0x1800279e9  mov     rcx, [rsp+58h+var_10]
0x1800279ee  xor     rcx, rsp; StackCookie
0x1800279f1  call    __security_check_cookie
0x1800279f6  mov     rbx, [rsp+58h+arg_18]
0x1800279fb  add     rsp, 50h
0x1800279ff  pop     rdi
0x180027a00  retn
```
