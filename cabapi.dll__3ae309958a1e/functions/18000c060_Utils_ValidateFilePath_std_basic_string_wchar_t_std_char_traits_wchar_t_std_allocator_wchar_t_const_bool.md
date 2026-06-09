# Utils::ValidateFilePath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x18000c060`
- end: `0x18000c384`
- name: `?ValidateFilePath@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z`
- size: `804`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18000c38c`
- `0x18000c8e0`

## callees

- `0x180001540`
- `0x180001fd6`
- `0x180003648`
- `0x18000553c`
- `0x180007fd0`
- `0x18000a74c`
- `0x18000a764`
- `0x18000a964`
- `0x18000aa84`
- `0x18000c060`
- `0x18000e990`
- `0x18000eaa0`
- `0x18000f5f0`
- `0x180013e04`

## pseudocode

```c
__int64 __fastcall Utils::ValidateFilePath(__int64 a1, char a2)
{
  void **v3; // r11
  __int64 not_ch; // rax
  __int64 v5; // r11
  __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  void **v9; // rcx
  unsigned __int64 v10; // rbx
  void **v11; // rcx
  void **v12; // r8
  unsigned __int64 v13; // r9
  __int64 last_not_ch_pos; // rax
  void **v15; // rcx
  __int64 v16; // rdx
  void **v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rbx
  void **v21; // rsi
  const wchar_t *v22; // rcx
  wchar_t *v23; // rbx
  void **v24; // rdi
  char *v25; // rbx
  __int64 seq_traits_avx_2_void_unsigned_short; // rax
  void **v27; // rdi
  char *v28; // rbx
  __int64 v29; // rax
  _BYTE v30[256]; // [rsp+30h] [rbp-D0h] BYREF
  void *Src[2]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v32; // [rsp+140h] [rbp+40h]
  unsigned __int64 v33; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  std::wstring::wstring((__int64)Src, a1);
  v3 = Src;
  if ( v33 > 7 )
    v3 = (void **)Src[0];
  if ( !v32 || (not_ch = std::_Find_not_ch_vectorized<wchar_t>(v3, (char *)v3 + 2 * v32), not_ch == v6) )
    v7 = -1;
  else
    v7 = (not_ch - v5) >> 1;
  v8 = v32;
  if ( v32 >= v7 )
    v8 = v7;
  v9 = Src;
  if ( v33 > 7 )
    v9 = (void **)Src[0];
  v10 = v32 - v8;
  memmove_0(v9, (char *)v9 + 2 * v8, 2 * (v32 - v8) + 2);
  v32 = v10;
  v11 = Src;
  v12 = (void **)Src[0];
  v13 = v33;
  if ( v33 > 7 )
    v11 = (void **)Src[0];
  if ( v10 )
  {
    last_not_ch_pos = std::_Find_last_not_ch_pos_vectorized<wchar_t>(v11, (char *)v11 + 2 * v10);
    v13 = v33;
    v10 = v32;
    v12 = (void **)Src[0];
  }
  else
  {
    last_not_ch_pos = -1;
  }
  if ( v10 < last_not_ch_pos + 1 )
    std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
  v32 = last_not_ch_pos + 1;
  v15 = Src;
  if ( v13 > 7 )
    v15 = v12;
  *((_WORD *)v15 + last_not_ch_pos + 1) = 0;
  if ( !v32 )
  {
    v16 = 480;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\utils.cpp",
      (const char *)0x801882DALL);
    std::wstring::~wstring((char **)Src);
    return 2149090010LL;
  }
  v18 = Src;
  if ( v33 > 7 )
    v18 = (void **)Src[0];
  if ( v32 + 5 < 0x10 )
  {
    v21 = (void **)((char *)v18 + 2 * v32);
    memset_0(v30, 0, sizeof(v30));
    v22 = L"*\"<>|";
    while ( *v22 < 0x100u )
    {
      v30[*(unsigned __int8 *)v22++] = 1;
      if ( v22 == L"" )
      {
        v23 = (wchar_t *)v18;
        if ( v18 >= v21 )
          goto LABEL_36;
        while ( *v23 >= 0x100u || !v30[*v23] )
        {
          if ( ++v23 >= (wchar_t *)v21 )
            goto LABEL_36;
        }
        goto LABEL_47;
      }
    }
    v23 = (wchar_t *)v18;
    if ( v18 >= v21 )
      goto LABEL_36;
    while ( !wmemchr(L"*\"<>|", *v23, 5u) )
    {
      if ( ++v23 >= (wchar_t *)v21 )
        goto LABEL_36;
    }
LABEL_47:
    v20 = ((char *)v23 - (char *)v18) >> 1;
  }
  else
  {
    if ( (_isa_enabled & 4) != 0 )
      v19 = anonymous_namespace_::_Find_meow_of::_First_of::_Dispatch_pos_sse_1_2_unsigned_short_0_(v18);
    else
      v19 = anonymous_namespace_::_Find_meow_of::_First_of::_Dispatch_pos_fallback_unsigned_short_0_(v18, v32);
    v20 = v19;
  }
  if ( v20 != -1 )
  {
    v16 = 482;
    goto LABEL_21;
  }
LABEL_36:
  if ( a2 )
  {
    v24 = Src;
    if ( v33 > 7 )
      v24 = (void **)Src[0];
    if ( v32 >= 3 )
    {
      v25 = (char *)v24 + 2 * v32;
      seq_traits_avx_2_void_unsigned_short = anonymous_namespace_::_Find_seq::_Search_impl__anonymous_namespace_::_Finding::_Find_traits_2_A0x8fcf2c39::_Find_seq::_Find_seq_traits_avx_2_void_unsigned_short_(
                                               v24,
                                               v25,
                                               L"..\\");
      if ( (char *)seq_traits_avx_2_void_unsigned_short != v25
        && !((seq_traits_avx_2_void_unsigned_short - (__int64)v24) >> 1) )
      {
        v16 = 486;
        goto LABEL_21;
      }
    }
    v27 = Src;
    if ( v33 > 7 )
      v27 = (void **)Src[0];
    if ( v32 >= 4 )
    {
      v28 = (char *)v27 + 2 * v32;
      v29 = anonymous_namespace_::_Find_seq::_Search_impl__anonymous_namespace_::_Finding::_Find_traits_2_A0x8fcf2c39::_Find_seq::_Find_seq_traits_avx_2_void_unsigned_short_(
              v27,
              v28,
              L"\\..\\");
      if ( (char *)v29 != v28 && (v29 - (__int64)v27) >> 1 != -1 )
      {
        v16 = 487;
        goto LABEL_21;
      }
    }
  }
  std::wstring::~wstring((char **)Src);
  return 0;
}

```

## disassembly

```asm
0x18000c060  mov     rax, rsp
0x18000c063  push    rbp
0x18000c064  push    rdi
0x18000c065  push    r12
0x18000c067  push    r14
0x18000c069  push    r15
0x18000c06b  lea     rbp, [rsp-60h]
0x18000c070  sub     rsp, 160h
0x18000c077  mov     qword ptr [rsp+180h+var_160], 0FFFFFFFFFFFFFFFEh; int
0x18000c080  mov     [rax+10h], rbx
0x18000c084  mov     [rax+18h], rsi
0x18000c088  mov     rax, cs:__security_cookie
0x18000c08f  xor     rax, rsp
0x18000c092  mov     [rbp+80h+var_30], rax
0x18000c096  mov     r14b, dl
0x18000c099  mov     rdx, rcx
0x18000c09c  lea     rcx, [rbp+80h+Src]
0x18000c0a0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c0a5  nop
0x18000c0a6  mov     rax, [rbp+80h+var_40]
0x18000c0aa  lea     r11, [rbp+80h+Src]
0x18000c0ae  cmp     [rbp+80h+var_38], 7
0x18000c0b3  cmova   r11, [rbp+80h+Src]
0x18000c0b8  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c0bc  test    rax, rax
0x18000c0bf  jz      short loc_18000C0DD
0x18000c0c1  lea     rdx, [r11+rax*2]
0x18000c0c5  mov     rcx, r11
0x18000c0c8  call    ??$_Find_not_ch_vectorized@_W@std@@YAPEB_WQEB_W0_W@Z; std::_Find_not_ch_vectorized<wchar_t>(wchar_t const * const,wchar_t const * const,wchar_t)
0x18000c0cd  mov     rcx, rax
0x18000c0d0  cmp     rax, rdx
0x18000c0d3  jz      short loc_18000C0DD
0x18000c0d5  sub     rcx, r11
0x18000c0d8  sar     rcx, 1
0x18000c0db  jmp     short loc_18000C0E0
0x18000c0dd  mov     rcx, r15
0x18000c0e0  mov     rbx, [rbp+80h+var_40]
0x18000c0e4  mov     rax, rbx
0x18000c0e7  cmp     rbx, rcx
0x18000c0ea  cmovnb  rax, rcx
0x18000c0ee  lea     rcx, [rbp+80h+Src]
0x18000c0f2  cmp     [rbp+80h+var_38], 7
0x18000c0f7  cmova   rcx, [rbp+80h+Src]; void *
0x18000c0fc  sub     rbx, rax
0x18000c0ff  lea     r8, ds:2[rbx*2]; Size
0x18000c107  lea     rdx, [rcx+rax*2]; Src
0x18000c10b  call    memmove_0
0x18000c110  mov     [rbp+80h+var_40], rbx
0x18000c114  lea     rcx, [rbp+80h+Src]
0x18000c118  mov     r8, [rbp+80h+Src]
0x18000c11c  mov     r9, [rbp+80h+var_38]
0x18000c120  cmp     r9, 7
0x18000c124  cmova   rcx, r8
0x18000c128  test    rbx, rbx
0x18000c12b  jnz     short loc_18000C132
0x18000c12d  mov     rax, r15
0x18000c130  jmp     short loc_18000C155
0x18000c132  lea     rax, [rbx-1]
0x18000c136  cmp     rax, r15
0x18000c139  cmovnb  rax, r15
0x18000c13d  inc     rax
0x18000c140  lea     rdx, [rcx+rax*2]
0x18000c144  call    ??$_Find_last_not_ch_pos_vectorized@_W@std@@YA_KQEB_W0_W@Z; std::_Find_last_not_ch_pos_vectorized<wchar_t>(wchar_t const * const,wchar_t const * const,wchar_t)
0x18000c149  mov     r9, [rbp+80h+var_38]
0x18000c14d  mov     rbx, [rbp+80h+var_40]
0x18000c151  mov     r8, [rbp+80h+Src]
0x18000c155  lea     rdx, [rax+1]
0x18000c159  cmp     rbx, rdx
0x18000c15c  jb      loc_18000C37E
0x18000c162  mov     [rbp+80h+var_40], rdx
0x18000c166  lea     rcx, [rbp+80h+Src]
0x18000c16a  cmp     r9, 7
0x18000c16e  cmova   rcx, r8
0x18000c172  xor     eax, eax
0x18000c174  mov     [rcx+rdx*2], ax
0x18000c178  cmp     [rbp+80h+var_40], rax
0x18000c17c  jnz     short loc_18000C1AF
0x18000c17e  mov     edx, 1E0h; void *
0x18000c183  mov     ebx, 801882DAh
0x18000c188  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000c18f  mov     r9d, ebx; char *
0x18000c192  mov     rcx, [rbp+88h]; this
0x18000c199  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c19e  nop
0x18000c19f  lea     rcx, [rbp+80h+Src]
0x18000c1a3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c1a8  mov     eax, ebx
0x18000c1aa  jmp     loc_18000C356
0x18000c1af  lea     rdi, [rbp+80h+Src]
0x18000c1b3  cmp     [rbp+80h+var_38], 7
0x18000c1b8  cmova   rdi, [rbp+80h+Src]
0x18000c1bd  mov     rcx, [rbp+80h+var_40]
0x18000c1c1  test    rcx, rcx
0x18000c1c4  jz      loc_18000C264
0x18000c1ca  lea     rax, [rcx+5]
0x18000c1ce  cmp     rax, 10h
0x18000c1d2  jb      short loc_18000C1FD
0x18000c1d4  mov     r9d, 5
0x18000c1da  mov     rdx, rcx
0x18000c1dd  mov     rcx, rdi; Src
0x18000c1e0  test    byte ptr cs:__isa_enabled, 4
0x18000c1e7  jz      short loc_18000C1F0
0x18000c1e9  call    _anonymous_namespace____Find_meow_of___First_of___Dispatch_pos_sse_1_2_unsigned_short_0_
0x18000c1ee  jmp     short loc_18000C1F5
0x18000c1f0  call    _anonymous_namespace____Find_meow_of___First_of___Dispatch_pos_fallback_unsigned_short_0_
0x18000c1f5  mov     rbx, rax
0x18000c1f8  jmp     loc_18000C2EA
0x18000c1fd  lea     rsi, [rdi+rcx*2]
0x18000c201  mov     r12d, 100h
0x18000c207  mov     r8d, r12d; Size
0x18000c20a  xor     edx, edx; Val
0x18000c20c  lea     rcx, [rsp+180h+var_150]; void *
0x18000c211  call    memset_0
0x18000c216  lea     rcx, Src; "*\"<>|"
0x18000c21d  cmp     [rcx], r12w
0x18000c221  jnb     loc_18000C2B7
0x18000c227  movzx   eax, byte ptr [rcx]
0x18000c22a  mov     [rsp+rax+180h+var_150], 1
0x18000c22f  add     rcx, 2
0x18000c233  lea     rax, Src+0Ah; ""
0x18000c23a  cmp     rcx, rax
0x18000c23d  jnz     short loc_18000C21D
0x18000c23f  mov     rbx, rdi
0x18000c242  cmp     rdi, rsi
0x18000c245  jnb     short loc_18000C264
0x18000c247  cmp     [rbx], r12w
0x18000c24b  jnb     short loc_18000C25B
0x18000c24d  movzx   eax, word ptr [rbx]
0x18000c250  cmp     [rsp+rax+180h+var_150], 0
0x18000c255  jnz     loc_18000C2E4
0x18000c25b  add     rbx, 2
0x18000c25f  cmp     rbx, rsi
0x18000c262  jb      short loc_18000C247
0x18000c264  test    r14b, r14b
0x18000c267  jz      loc_18000C34B
0x18000c26d  mov     rax, [rbp+80h+var_40]
0x18000c271  lea     rdi, [rbp+80h+Src]
0x18000c275  cmp     [rbp+80h+var_38], 7
0x18000c27a  cmova   rdi, [rbp+80h+Src]
0x18000c27f  mov     r9d, 3
0x18000c285  cmp     rax, r9
0x18000c288  jb      short loc_18000C2FD
0x18000c28a  lea     rbx, [rdi+rax*2]
0x18000c28e  lea     r8, asc_180018140; "..\\"
0x18000c295  mov     rdx, rbx
0x18000c298  mov     rcx, rdi
0x18000c29b  call    _anonymous_namespace____Find_seq___Search_impl__anonymous_namespace____Finding___Find_traits_2_A0x8fcf2c39___Find_seq___Find_seq_traits_avx_2_void_unsigned_short_
0x18000c2a0  cmp     rax, rbx
0x18000c2a3  jz      short loc_18000C2FD
0x18000c2a5  sub     rax, rdi
0x18000c2a8  sar     rax, 1
0x18000c2ab  jnz     short loc_18000C2FD
0x18000c2ad  mov     edx, 1E6h
0x18000c2b2  jmp     loc_18000C183
0x18000c2b7  mov     rbx, rdi
0x18000c2ba  cmp     rdi, rsi
0x18000c2bd  jnb     short loc_18000C264
0x18000c2bf  mov     r8d, 5; N
0x18000c2c5  movzx   edx, word ptr [rbx]; C
0x18000c2c8  lea     rcx, Src; "*\"<>|"
0x18000c2cf  call    wmemchr
0x18000c2d4  test    rax, rax
0x18000c2d7  jnz     short loc_18000C2E4
0x18000c2d9  add     rbx, 2
0x18000c2dd  cmp     rbx, rsi
0x18000c2e0  jb      short loc_18000C2BF
0x18000c2e2  jmp     short loc_18000C264
0x18000c2e4  sub     rbx, rdi
0x18000c2e7  sar     rbx, 1
0x18000c2ea  cmp     rbx, r15
0x18000c2ed  jz      loc_18000C264
0x18000c2f3  mov     edx, 1E2h
0x18000c2f8  jmp     loc_18000C183
0x18000c2fd  mov     rax, [rbp+80h+var_40]
0x18000c301  lea     rdi, [rbp+80h+Src]
0x18000c305  cmp     [rbp+80h+var_38], 7
0x18000c30a  cmova   rdi, [rbp+80h+Src]
0x18000c30f  cmp     rax, 4
0x18000c313  jb      short loc_18000C34B
0x18000c315  lea     rbx, [rdi+rax*2]
0x18000c319  mov     r9d, 4
0x18000c31f  lea     r8, asc_180018148; "\\..\\"
0x18000c326  mov     rdx, rbx
0x18000c329  mov     rcx, rdi
0x18000c32c  call    _anonymous_namespace____Find_seq___Search_impl__anonymous_namespace____Finding___Find_traits_2_A0x8fcf2c39___Find_seq___Find_seq_traits_avx_2_void_unsigned_short_
0x18000c331  cmp     rax, rbx
0x18000c334  jz      short loc_18000C34B
0x18000c336  sub     rax, rdi
0x18000c339  sar     rax, 1
0x18000c33c  cmp     rax, r15
0x18000c33f  jz      short loc_18000C34B
0x18000c341  mov     edx, 1E7h
0x18000c346  jmp     loc_18000C183
0x18000c34b  lea     rcx, [rbp+80h+Src]
0x18000c34f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c354  xor     eax, eax
0x18000c356  mov     rcx, [rbp+80h+var_30]
0x18000c35a  xor     rcx, rsp; StackCookie
0x18000c35d  call    __security_check_cookie
0x18000c362  lea     r11, [rsp+180h+var_20]
0x18000c36a  mov     rbx, [r11+38h]
0x18000c36e  mov     rsi, [r11+40h]
0x18000c372  mov     rsp, r11
0x18000c375  pop     r15
0x18000c377  pop     r14
0x18000c379  pop     r12
0x18000c37b  pop     rdi
0x18000c37c  pop     rbp
0x18000c37d  retn
0x18000c37e  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
