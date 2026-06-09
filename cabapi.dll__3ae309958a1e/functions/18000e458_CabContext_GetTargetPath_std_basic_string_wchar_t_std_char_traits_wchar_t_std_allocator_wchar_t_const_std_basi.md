# CabContext::GetTargetPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *)

- ea: `0x18000e458`
- end: `0x18000e5fb`
- name: `?GetTargetPath@CabContext@@QEBAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV23@@Z`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000c8e0`

## callees

- `0x180001540`
- `0x180001f76`
- `0x180002e54`
- `0x180003648`
- `0x18000553c`
- `0x1800084b4`
- `0x18000b2c0`
- `0x18000db98`
- `0x18000e458`

## pseudocode

```c
__int64 __fastcall CabContext::GetTargetPath(_QWORD *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  _WORD *v7; // rcx
  _QWORD *v8; // r14
  _QWORD *v9; // rsi
  const wchar_t *v10; // rdx
  _QWORD *v11; // rdx
  __int128 *v12; // rdx
  unsigned __int64 v13; // r8
  __int128 *p_Src; // rdx
  __int64 v16; // [rsp+28h] [rbp-48h] BYREF
  __int64 v17; // [rsp+38h] [rbp-38h]
  __int128 Src; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v19; // [rsp+50h] [rbp-20h]
  unsigned __int64 v20; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( a3 )
  {
    *(_QWORD *)(a3 + 16) = 0;
    if ( *(_QWORD *)(a3 + 24) <= 7u )
      v7 = (_WORD *)a3;
    else
      v7 = *(_WORD **)a3;
    *v7 = 0;
    Src = 0;
    v19 = 0;
    v20 = 7;
    LOWORD(Src) = 0;
    if ( a1[3] )
    {
      v8 = a1 + 6;
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
        (__int64)(a1 + 6),
        &v16,
        a2);
      v9 = (_QWORD *)v17;
      if ( *(_BYTE *)(v17 + 25) )
        goto LABEL_18;
      v10 = (const wchar_t *)(v17 + 32);
      if ( *(_QWORD *)(v17 + 56) > 7u )
        v10 = *(const wchar_t **)v10;
      if ( *(_QWORD *)(a2 + 24) > 7u )
        a2 = *(_QWORD *)a2;
      if ( wcsicmp((const wchar_t *)a2, v10) < 0 || v9 == (_QWORD *)*v8 )
      {
LABEL_18:
        v6 = -2145877310;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabcontext.cpp",
          (const char *)0x801882C2LL,
          -2);
LABEL_29:
        std::wstring::~wstring((char **)&Src);
        return v6;
      }
      v11 = v9 + 8;
      if ( &Src != (__int128 *)(v9 + 8) )
      {
        if ( v9[11] > 7u )
          v11 = (_QWORD *)*v11;
        std::wstring::_Assign<wchar_t>((void **)&Src, v11, v9[10]);
      }
    }
    else
    {
      v12 = (__int128 *)(a1 + 8);
      if ( &Src != v12 )
      {
        v13 = *((_QWORD *)v12 + 2);
        if ( *((_QWORD *)v12 + 3) > 7u )
          v12 = *(__int128 **)v12;
        std::wstring::_Assign<wchar_t>((void **)&Src, v12, v13);
      }
      std::wstring::operator+=(&Src, L"\\");
      std::wstring::operator+=(&Src, (_QWORD *)a2);
    }
    if ( (__int128 *)a3 != &Src )
    {
      p_Src = &Src;
      if ( v20 > 7 )
        p_Src = (__int128 *)Src;
      std::wstring::_Assign<wchar_t>((void **)a3, p_Src, v19);
    }
    v6 = 0;
    goto LABEL_29;
  }
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A,
    (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\cabcontext.cpp",
    (const char *)0x80004003LL,
    -2);
  return v6;
}

```

## disassembly

```asm
0x18000e458  push    rbp
0x18000e45a  push    rbx
0x18000e45b  push    rsi
0x18000e45c  push    rdi
0x18000e45d  push    r14
0x18000e45f  mov     rbp, rsp
0x18000e462  sub     rsp, 70h
0x18000e466  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18000e46e  mov     rax, cs:__security_cookie
0x18000e475  xor     rax, rsp
0x18000e478  mov     [rbp+var_10], rax
0x18000e47c  mov     rbx, r8
0x18000e47f  mov     rdi, rdx
0x18000e482  mov     rdx, rcx
0x18000e485  test    r8, r8
0x18000e488  jnz     short loc_18000E4AC
0x18000e48a  mov     rcx, [rbp+28h]; this
0x18000e48e  mov     ebx, 80004003h
0x18000e493  mov     r9d, ebx; char *
0x18000e496  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000e49d  mov     edx, 2Ah ; '*'; void *
0x18000e4a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e4a7  jmp     loc_18000E5E2
0x18000e4ac  mov     qword ptr [r8+10h], 0
0x18000e4b4  cmp     qword ptr [r8+18h], 7
0x18000e4b9  jbe     short loc_18000E4C0
0x18000e4bb  mov     rcx, [r8]
0x18000e4be  jmp     short loc_18000E4C3
0x18000e4c0  mov     rcx, rbx
0x18000e4c3  xor     eax, eax
0x18000e4c5  mov     [rcx], ax
0x18000e4c8  xorps   xmm0, xmm0
0x18000e4cb  movups  [rbp+Src], xmm0
0x18000e4cf  mov     [rbp+var_20], rax
0x18000e4d3  mov     [rbp+var_18], 7
0x18000e4db  mov     word ptr [rbp+Src], ax
0x18000e4df  cmp     [rdx+18h], rax
0x18000e4e3  jz      loc_18000E574
0x18000e4e9  lea     r14, [rdx+30h]
0x18000e4ed  mov     r8, rdi
0x18000e4f0  lea     rdx, [rbp+var_48]
0x18000e4f4  mov     rcx, r14
0x18000e4f7  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@UWStringCaseInsensitiveCompare@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,WStringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000e4fc  mov     rsi, [rbp+var_38]
0x18000e500  cmp     byte ptr [rsi+19h], 0
0x18000e504  jnz     short loc_18000E555
0x18000e506  lea     rdx, [rsi+20h]
0x18000e50a  cmp     qword ptr [rdx+18h], 7
0x18000e50f  jbe     short loc_18000E514
0x18000e511  mov     rdx, [rdx]; String2
0x18000e514  cmp     qword ptr [rdi+18h], 7
0x18000e519  jbe     short loc_18000E51E
0x18000e51b  mov     rdi, [rdi]
0x18000e51e  mov     rcx, rdi; String1
0x18000e521  call    _wcsicmp
0x18000e526  test    eax, eax
0x18000e528  js      short loc_18000E555
0x18000e52a  cmp     rsi, [r14]
0x18000e52d  jz      short loc_18000E555
0x18000e52f  lea     rdx, [rsi+40h]
0x18000e533  lea     rax, [rbp+Src]
0x18000e537  cmp     rax, rdx
0x18000e53a  jz      short loc_18000E5B4
0x18000e53c  mov     r8, [rdx+10h]
0x18000e540  cmp     qword ptr [rdx+18h], 7
0x18000e545  jbe     short loc_18000E54A
0x18000e547  mov     rdx, [rdx]
0x18000e54a  lea     rcx, [rbp+Src]
0x18000e54e  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e553  jmp     short loc_18000E5B4
0x18000e555  mov     rcx, [rbp+28h]; this
0x18000e559  mov     ebx, 801882C2h
0x18000e55e  mov     r9d, ebx; char *
0x18000e561  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000e568  mov     edx, 32h ; '2'; void *
0x18000e56d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e572  jmp     short loc_18000E5D9
0x18000e574  add     rdx, 40h ; '@'
0x18000e578  lea     rax, [rbp+Src]
0x18000e57c  cmp     rax, rdx
0x18000e57f  jz      short loc_18000E598
0x18000e581  mov     r8, [rdx+10h]
0x18000e585  cmp     qword ptr [rdx+18h], 7
0x18000e58a  jbe     short loc_18000E58F
0x18000e58c  mov     rdx, [rdx]
0x18000e58f  lea     rcx, [rbp+Src]
0x18000e593  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e598  lea     rdx, asc_180017CF4; "\\"
0x18000e59f  lea     rcx, [rbp+Src]; Src
0x18000e5a3  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator+=(wchar_t const * const)
0x18000e5a8  mov     rdx, rdi
0x18000e5ab  lea     rcx, [rbp+Src]; Src
0x18000e5af  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x18000e5b4  lea     rax, [rbp+Src]
0x18000e5b8  cmp     rbx, rax
0x18000e5bb  jz      short loc_18000E5D7
0x18000e5bd  lea     rdx, [rbp+Src]
0x18000e5c1  cmp     [rbp+var_18], 7
0x18000e5c6  cmova   rdx, qword ptr [rbp+Src]
0x18000e5cb  mov     r8, [rbp+var_20]
0x18000e5cf  mov     rcx, rbx
0x18000e5d2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000e5d7  xor     ebx, ebx
0x18000e5d9  lea     rcx, [rbp+Src]
0x18000e5dd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e5e2  mov     eax, ebx
0x18000e5e4  mov     rcx, [rbp+var_10]
0x18000e5e8  xor     rcx, rsp; StackCookie
0x18000e5eb  call    __security_check_cookie
0x18000e5f0  add     rsp, 70h
0x18000e5f4  pop     r14
0x18000e5f6  pop     rdi
0x18000e5f7  pop     rsi
0x18000e5f8  pop     rbx
0x18000e5f9  pop     rbp
0x18000e5fa  retn
```
