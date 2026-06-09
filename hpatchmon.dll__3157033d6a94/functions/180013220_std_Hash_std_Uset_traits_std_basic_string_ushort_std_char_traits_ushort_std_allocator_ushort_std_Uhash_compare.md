# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180013220`
- end: `0x180013464`
- name: `?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `580`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011d60`

## callees

- `0x1800122c4`
- `0x1800130f4`
- `0x180013220`
- `0x180013dc4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013264`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013264`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // r12
  unsigned __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rcx
  _QWORD *v7; // rbx
  _QWORD *v8; // rdi
  const wchar_t **v9; // r15
  const wchar_t *v10; // r8
  __int64 v11; // r10
  unsigned __int64 v12; // rdx
  __int64 i; // r14
  __int64 v14; // rax
  __int64 v15; // rbp
  __int64 v16; // r14
  _QWORD *v17; // rsi
  const wchar_t *v18; // rdx
  const wchar_t *v19; // rcx
  _QWORD *v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // r8
  const wchar_t *v25; // rdx
  size_t v26; // r8
  const wchar_t *v27; // rcx
  _QWORD *v28; // r8
  _QWORD *v29; // rdx
  _QWORD *v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v32; // rdx
  _QWORD *v33; // rax
  _QWORD *v34; // rcx
  unsigned __int64 *v35; // [rsp+50h] [rbp+8h] BYREF

  HIDWORD(v35) = HIDWORD(a1);
  LODWORD(v35) = 0;
  _BitScanReverse64(&v2, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v2 )
    std::_Xlength_error("invalid hash bucket count");
  v3 = qword_180022EC8;
  LODWORD(v35) = 0;
  _BitScanReverse64(&v4, (a2 - 1) | 1);
  v5 = 1LL << ((unsigned __int8)v4 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    (__int64)&qword_180022ED8,
    2 * v5,
    qword_180022EC8);
  v6 = v5 - 1;
  qword_180022EF8 = v5;
  qword_180022EF0 = v5 - 1;
  v7 = *(_QWORD **)qword_180022EC8;
  v8 = *(_QWORD **)qword_180022EC8;
  while ( v7 != (_QWORD *)v3 )
  {
    v8 = (_QWORD *)*v8;
    v9 = (const wchar_t **)(v7 + 2);
    v10 = (const wchar_t *)(v7 + 2);
    v11 = v7[4];
    if ( v7[5] > 7u )
      v10 = *v9;
    v12 = 0;
    for ( i = 0xCBF29CE484222325uLL; v12 < 2 * v11; i = 0x100000001B3LL * (v14 ^ i) )
      v14 = *((unsigned __int8 *)v10 + v12++);
    v15 = qword_180022ED8;
    v16 = 2 * (v6 & i);
    if ( *(_QWORD *)(qword_180022ED8 + 8 * v16) == v3 )
    {
      *(_QWORD *)(qword_180022ED8 + 8 * v16) = v7;
LABEL_11:
      *(_QWORD *)(v15 + 8 * v16 + 8) = v7;
      goto LABEL_32;
    }
    v17 = *(_QWORD **)(qword_180022ED8 + 8 * v16 + 8);
    v18 = (const wchar_t *)(v17 + 2);
    if ( v17[5] > 7u )
      v18 = *(const wchar_t **)v18;
    v19 = (const wchar_t *)(v7 + 2);
    if ( v7[5] > 7u )
      v19 = *v9;
    if ( v11 == v17[4] && (!v11 || !wmemcmp(v19, v18, v7[4])) )
    {
      v20 = (_QWORD *)*v17;
      if ( (_QWORD *)*v17 != v7 )
      {
        v21 = (_QWORD *)v7[1];
        *v21 = v8;
        v22 = (_QWORD *)v8[1];
        *v22 = v20;
        v23 = (_QWORD *)v20[1];
        *v23 = v7;
        v20[1] = v22;
        v8[1] = v21;
        v7[1] = v23;
      }
      goto LABEL_11;
    }
    while ( 1 )
    {
      v24 = v17 + 1;
      if ( *(_QWORD **)(v15 + 8 * v16) == v17 )
        break;
      v17 = (_QWORD *)*v24;
      v25 = (const wchar_t *)(*v24 + 16LL);
      if ( *(_QWORD *)(*v24 + 40LL) > 7u )
        v25 = *(const wchar_t **)v25;
      v26 = v7[4];
      if ( v7[5] <= 7u )
        v27 = (const wchar_t *)(v7 + 2);
      else
        v27 = *v9;
      if ( v26 == v17[4] && (!v26 || !wmemcmp(v27, v25, v26)) )
      {
        v28 = (_QWORD *)*v17;
        v29 = (_QWORD *)v7[1];
        *v29 = v8;
        v30 = (_QWORD *)v8[1];
        *v30 = v28;
        v31 = (_QWORD *)v28[1];
        *v31 = v7;
        v28[1] = v30;
        v8[1] = v29;
        v7[1] = v31;
        goto LABEL_32;
      }
    }
    v32 = (_QWORD *)v7[1];
    *v32 = v8;
    v33 = (_QWORD *)v8[1];
    *v33 = v17;
    v34 = (_QWORD *)*v24;
    *v34 = v7;
    *v24 = v33;
    v8[1] = v32;
    v7[1] = v34;
    *(_QWORD *)(v15 + 8 * v16) = v7;
LABEL_32:
    v6 = qword_180022EF0;
    v7 = v8;
  }
  v35 = 0;
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(&v35);
}

```

## disassembly

```asm
0x180013220  mov     rax, rsp
0x180013223  mov     [rax+10h], rbx
0x180013227  mov     [rax+18h], rbp
0x18001322b  mov     [rax+8], rcx
0x18001322f  push    rsi
0x180013230  push    rdi
0x180013231  push    r12
0x180013233  push    r14
0x180013235  push    r15
0x180013237  sub     rsp, 20h
0x18001323b  mov     dword ptr [rax+8], 0
0x180013242  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001324c  bsr     rcx, rax
0x180013250  mov     eax, 1
0x180013255  shl     rax, cl
0x180013258  cmp     rdx, rax
0x18001325b  jbe     short loc_18001326B
0x18001325d  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180013264  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001326b  mov     r12, cs:qword_180022EC8
0x180013272  lea     rax, [rdx-1]
0x180013276  or      rax, 1
0x18001327a  mov     dword ptr [rsp+48h+arg_0], 0
0x180013282  bsr     rcx, rax
0x180013286  mov     ebx, 1
0x18001328b  mov     r8, r12
0x18001328e  inc     ecx
0x180013290  shl     rbx, cl
0x180013293  lea     rcx, qword_180022ED8
0x18001329a  lea     rdx, [rbx+rbx]
0x18001329e  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x1800132a3  lea     rcx, [rbx-1]
0x1800132a7  mov     cs:qword_180022EF8, rbx
0x1800132ae  mov     rbx, cs:qword_180022EC8
0x1800132b5  mov     cs:qword_180022EF0, rcx
0x1800132bc  mov     rbx, [rbx]
0x1800132bf  mov     rdi, rbx
0x1800132c2  cmp     rbx, r12
0x1800132c5  jz      loc_18001343A
0x1800132cb  mov     rdi, [rdi]
0x1800132ce  lea     r15, [rbx+10h]
0x1800132d2  cmp     qword ptr [r15+18h], 7
0x1800132d7  mov     r8, r15
0x1800132da  mov     r10, [r15+10h]
0x1800132de  jbe     short loc_1800132E3
0x1800132e0  mov     r8, [r15]
0x1800132e3  lea     r9, [r10+r10]
0x1800132e7  xor     edx, edx
0x1800132e9  mov     r14, 0CBF29CE484222325h
0x1800132f3  test    r9, r9
0x1800132f6  jz      short loc_180013316
0x1800132f8  movzx   eax, byte ptr [r8+rdx]
0x1800132fd  mov     r11, 100000001B3h
0x180013307  xor     r14, rax
0x18001330a  inc     rdx
0x18001330d  imul    r14, r11
0x180013311  cmp     rdx, r9
0x180013314  jb      short loc_1800132F8
0x180013316  mov     rbp, cs:qword_180022ED8
0x18001331d  and     r14, rcx
0x180013320  add     r14, r14
0x180013323  cmp     [rbp+r14*8+0], r12
0x180013328  jnz     short loc_180013339
0x18001332a  mov     [rbp+r14*8+0], rbx
0x18001332f  mov     [rbp+r14*8+8], rbx
0x180013334  jmp     loc_18001342B
0x180013339  mov     rsi, [rbp+r14*8+8]
0x18001333e  lea     rdx, [rsi+10h]
0x180013342  cmp     qword ptr [rdx+18h], 7
0x180013347  mov     rax, [rdx+10h]
0x18001334b  jbe     short loc_180013350
0x18001334d  mov     rdx, [rdx]; S2
0x180013350  cmp     qword ptr [r15+18h], 7
0x180013355  mov     rcx, r15
0x180013358  jbe     short loc_18001335D
0x18001335a  mov     rcx, [r15]; S1
0x18001335d  cmp     r10, rax
0x180013360  jnz     short loc_18001339E
0x180013362  test    r10, r10
0x180013365  jz      short loc_180013373
0x180013367  mov     r8, r10; N
0x18001336a  call    wmemcmp
0x18001336f  test    eax, eax
0x180013371  jnz     short loc_18001339E
0x180013373  mov     r8, [rsi]
0x180013376  cmp     r8, rbx
0x180013379  jz      short loc_18001332F
0x18001337b  mov     rdx, [rbx+8]
0x18001337f  mov     [rdx], rdi
0x180013382  mov     rcx, [rdi+8]
0x180013386  mov     [rcx], r8
0x180013389  mov     rax, [r8+8]
0x18001338d  mov     [rax], rbx
0x180013390  mov     [r8+8], rcx
0x180013394  mov     [rdi+8], rdx
0x180013398  mov     [rbx+8], rax
0x18001339c  jmp     short loc_18001332F
0x18001339e  lea     r8, [rsi+8]
0x1800133a2  cmp     [rbp+r14*8+0], rsi
0x1800133a7  jz      short loc_180013407
0x1800133a9  mov     rsi, [r8]
0x1800133ac  cmp     qword ptr [rsi+28h], 7
0x1800133b1  lea     rdx, [rsi+10h]
0x1800133b5  jbe     short loc_1800133BA
0x1800133b7  mov     rdx, [rdx]; S2
0x1800133ba  cmp     qword ptr [r15+18h], 7
0x1800133bf  mov     r8, [r15+10h]; N
0x1800133c3  jbe     short loc_1800133CA
0x1800133c5  mov     rcx, [r15]
0x1800133c8  jmp     short loc_1800133CD
0x1800133ca  mov     rcx, r15; S1
0x1800133cd  cmp     r8, [rsi+20h]
0x1800133d1  jnz     short loc_18001339E
0x1800133d3  test    r8, r8
0x1800133d6  jz      short loc_1800133E1
0x1800133d8  call    wmemcmp
0x1800133dd  test    eax, eax
0x1800133df  jnz     short loc_18001339E
0x1800133e1  mov     r8, [rsi]
0x1800133e4  mov     rdx, [rbx+8]
0x1800133e8  mov     [rdx], rdi
0x1800133eb  mov     rcx, [rdi+8]
0x1800133ef  mov     [rcx], r8
0x1800133f2  mov     rax, [r8+8]
0x1800133f6  mov     [rax], rbx
0x1800133f9  mov     [r8+8], rcx
0x1800133fd  mov     [rdi+8], rdx
0x180013401  mov     [rbx+8], rax
0x180013405  jmp     short loc_18001342B
0x180013407  mov     rdx, [rbx+8]
0x18001340b  mov     [rdx], rdi
0x18001340e  mov     rax, [rdi+8]
0x180013412  mov     [rax], rsi
0x180013415  mov     rcx, [r8]
0x180013418  mov     [rcx], rbx
0x18001341b  mov     [r8], rax
0x18001341e  mov     [rdi+8], rdx
0x180013422  mov     [rbx+8], rcx
0x180013426  mov     [rbp+r14*8+0], rbx
0x18001342b  mov     rcx, cs:qword_180022EF0
0x180013432  mov     rbx, rdi
0x180013435  jmp     loc_1800132C2
0x18001343a  lea     rcx, [rsp+48h+arg_0]
0x18001343f  mov     [rsp+48h+arg_0], 0
0x180013448  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(void)
0x18001344d  mov     rbx, [rsp+48h+arg_8]
0x180013452  mov     rbp, [rsp+48h+arg_10]
0x180013457  add     rsp, 20h
0x18001345b  pop     r15
0x18001345d  pop     r14
0x18001345f  pop     r12
0x180013461  pop     rdi
0x180013462  pop     rsi
0x180013463  retn
```
