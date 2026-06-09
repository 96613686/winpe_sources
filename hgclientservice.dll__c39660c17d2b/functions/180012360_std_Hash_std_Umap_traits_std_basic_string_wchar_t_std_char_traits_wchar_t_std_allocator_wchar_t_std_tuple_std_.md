# std::_Hash<std::_Umap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::tuple<std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>>,std::_Uhash_compare<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::equal_to<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::tuple<std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180012360`
- end: `0x18001257a`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `538`
- prototype: `int __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011008`

## callees

- `0x180010d20`
- `0x180012234`
- `0x180012360`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001239e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001239e`

## pseudocode

```c
int __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  const wchar_t **v11; // r15
  const wchar_t *v12; // r8
  _QWORD *v13; // r10
  unsigned __int64 v14; // rdx
  __int64 i; // rcx
  __int64 v16; // r12
  __int64 v17; // r14
  _QWORD *v18; // rsi
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  _QWORD *v21; // r8
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  unsigned __int64 *v24; // r8
  const wchar_t *v25; // rdx
  size_t v26; // r8
  const wchar_t *v27; // rcx
  _QWORD *v28; // r8
  _QWORD *v29; // rdx
  _QWORD *v30; // rcx
  _QWORD *v31; // rdx
  _QWORD *v32; // rcx

  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>,std::vector<unsigned char>>>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v7,
    v4);
  LODWORD(v8) = v7 - 1;
  a1[7] = v7;
  a1[6] = v7 - 1;
  v9 = *(_QWORD **)a1[1];
  v10 = v9;
  while ( v9 != v4 )
  {
    v10 = (_QWORD *)*v10;
    v11 = (const wchar_t **)(v9 + 2);
    v12 = (const wchar_t *)(v9 + 2);
    v13 = (_QWORD *)v9[4];
    if ( v9[5] > 7u )
      v12 = *v11;
    v14 = 0;
    for ( i = 0xCBF29CE484222325uLL; v14 < 2 * (__int64)v13; i = 0x100000001B3LL * (v8 ^ i) )
      v8 = *((unsigned __int8 *)v12 + v14++);
    v16 = *v6;
    v17 = 2 * (i & a1[6]);
    if ( *(_QWORD **)(*v6 + 16 * (i & a1[6])) == v4 )
    {
      *(_QWORD *)(v16 + 16 * (i & a1[6])) = v9;
      *(_QWORD *)(v16 + 8 * v17 + 8) = v9;
    }
    else
    {
      v18 = *(_QWORD **)(v16 + 16 * (i & a1[6]) + 8);
      v19 = (const wchar_t *)(v18 + 2);
      v8 = v18[4];
      if ( v18[5] > 7u )
        v19 = *(const wchar_t **)v19;
      v20 = (const wchar_t *)(v9 + 2);
      if ( v9[5] > 7u )
        v20 = *v11;
      if ( v13 != (_QWORD *)v8 || v13 && (LODWORD(v8) = wmemcmp(v20, v19, v9[4]), (_DWORD)v8) )
      {
        while ( 1 )
        {
          v24 = v18 + 1;
          if ( *(_QWORD **)(v16 + 8 * v17) == v18 )
            break;
          v18 = (_QWORD *)*v24;
          v25 = (const wchar_t *)(*v24 + 16);
          if ( *(_QWORD *)(*v24 + 40) > 7u )
            v25 = *(const wchar_t **)v25;
          v26 = v9[4];
          if ( v9[5] <= 7u )
            v27 = (const wchar_t *)(v9 + 2);
          else
            v27 = *v11;
          if ( v26 == v18[4] && (!v26 || !wmemcmp(v27, v25, v26)) )
          {
            v28 = (_QWORD *)*v18;
            v29 = (_QWORD *)v9[1];
            *v29 = v10;
            v30 = (_QWORD *)v10[1];
            *v30 = v28;
            v8 = v28[1];
            *(_QWORD *)v8 = v9;
            v28[1] = v30;
            v10[1] = v29;
            v9[1] = v8;
            goto LABEL_32;
          }
        }
        v31 = (_QWORD *)v9[1];
        *v31 = v10;
        v8 = v10[1];
        *(_QWORD *)v8 = v18;
        v32 = (_QWORD *)*v24;
        *v32 = v9;
        *v24 = v8;
        v10[1] = v31;
        v9[1] = v32;
        *(_QWORD *)(v16 + 8 * v17) = v9;
      }
      else
      {
        v21 = (_QWORD *)*v18;
        if ( (_QWORD *)*v18 != v9 )
        {
          v22 = (_QWORD *)v9[1];
          *v22 = v10;
          v23 = (_QWORD *)v10[1];
          *v23 = v21;
          v8 = v21[1];
          *(_QWORD *)v8 = v9;
          v21[1] = v23;
          v10[1] = v22;
          v9[1] = v8;
        }
        *(_QWORD *)(v16 + 8 * v17 + 8) = v9;
      }
LABEL_32:
      v6 = a1 + 3;
    }
    v9 = v10;
  }
  return v8;
}

```

## disassembly

```asm
0x180012360  push    rbx
0x180012362  push    rbp
0x180012363  push    rsi
0x180012364  push    rdi
0x180012365  push    r12
0x180012367  push    r13
0x180012369  push    r14
0x18001236b  push    r15
0x18001236d  sub     rsp, 28h
0x180012371  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001237b  mov     [rsp+68h+arg_8], 0
0x180012383  mov     r13, rcx
0x180012386  bsr     rcx, rax
0x18001238a  mov     eax, 1
0x18001238f  shl     rax, cl
0x180012392  cmp     rdx, rax
0x180012395  jbe     short loc_1800123A5
0x180012397  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18001239e  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800123a5  mov     rbp, [r13+8]
0x1800123a9  lea     rax, [rdx-1]
0x1800123ad  or      rax, 1
0x1800123b1  mov     [rsp+68h+arg_8], 0
0x1800123b9  bsr     rcx, rax
0x1800123bd  mov     ebx, 1
0x1800123c2  lea     rsi, [r13+18h]
0x1800123c6  inc     ecx
0x1800123c8  mov     r8, rbp
0x1800123cb  shl     rbx, cl
0x1800123ce  mov     rcx, rsi
0x1800123d1  lea     rdx, [rbx+rbx]
0x1800123d5  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@V?$vector@EV?$allocator@E@std@@@std@@V12@V12@V12@V12@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::tuple<std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>,std::vector<uchar>>>>>>)
0x1800123da  lea     rax, [rbx-1]
0x1800123de  mov     [r13+38h], rbx
0x1800123e2  mov     [r13+30h], rax
0x1800123e6  mov     rbx, [r13+8]
0x1800123ea  mov     rbx, [rbx]
0x1800123ed  mov     rdi, rbx
0x1800123f0  cmp     rbx, rbp
0x1800123f3  jz      loc_180012569
0x1800123f9  mov     rdi, [rdi]
0x1800123fc  lea     r15, [rbx+10h]
0x180012400  cmp     qword ptr [r15+18h], 7
0x180012405  mov     r8, r15
0x180012408  mov     r10, [r15+10h]
0x18001240c  jbe     short loc_180012411
0x18001240e  mov     r8, [r15]
0x180012411  lea     r9, [r10+r10]
0x180012415  xor     edx, edx
0x180012417  mov     rcx, 0CBF29CE484222325h
0x180012421  test    r9, r9
0x180012424  jz      short loc_180012444
0x180012426  movzx   eax, byte ptr [r8+rdx]
0x18001242b  mov     r11, 100000001B3h
0x180012435  xor     rcx, rax
0x180012438  inc     rdx
0x18001243b  imul    rcx, r11
0x18001243f  cmp     rdx, r9
0x180012442  jb      short loc_180012426
0x180012444  mov     r14, [r13+30h]
0x180012448  mov     r12, [rsi]
0x18001244b  and     r14, rcx
0x18001244e  add     r14, r14
0x180012451  cmp     [r12+r14*8], rbp
0x180012455  jnz     short loc_180012465
0x180012457  mov     [r12+r14*8], rbx
0x18001245b  mov     [r12+r14*8+8], rbx
0x180012460  jmp     loc_180012561
0x180012465  mov     rsi, [r12+r14*8+8]
0x18001246a  lea     rdx, [rsi+10h]
0x18001246e  cmp     qword ptr [rdx+18h], 7
0x180012473  mov     rax, [rdx+10h]
0x180012477  jbe     short loc_18001247C
0x180012479  mov     rdx, [rdx]; S2
0x18001247c  cmp     qword ptr [r15+18h], 7
0x180012481  mov     rcx, r15
0x180012484  jbe     short loc_180012489
0x180012486  mov     rcx, [r15]; S1
0x180012489  cmp     r10, rax
0x18001248c  jnz     short loc_1800124D2
0x18001248e  test    r10, r10
0x180012491  jz      short loc_18001249F
0x180012493  mov     r8, r10; N
0x180012496  call    wmemcmp
0x18001249b  test    eax, eax
0x18001249d  jnz     short loc_1800124D2
0x18001249f  mov     r8, [rsi]
0x1800124a2  cmp     r8, rbx
0x1800124a5  jz      short loc_1800124C8
0x1800124a7  mov     rdx, [rbx+8]
0x1800124ab  mov     [rdx], rdi
0x1800124ae  mov     rcx, [rdi+8]
0x1800124b2  mov     [rcx], r8
0x1800124b5  mov     rax, [r8+8]
0x1800124b9  mov     [rax], rbx
0x1800124bc  mov     [r8+8], rcx
0x1800124c0  mov     [rdi+8], rdx
0x1800124c4  mov     [rbx+8], rax
0x1800124c8  mov     [r12+r14*8+8], rbx
0x1800124cd  jmp     loc_18001255D
0x1800124d2  lea     r8, [rsi+8]
0x1800124d6  cmp     [r12+r14*8], rsi
0x1800124da  jz      short loc_18001253A
0x1800124dc  mov     rsi, [r8]
0x1800124df  cmp     qword ptr [rsi+28h], 7
0x1800124e4  lea     rdx, [rsi+10h]
0x1800124e8  jbe     short loc_1800124ED
0x1800124ea  mov     rdx, [rdx]; S2
0x1800124ed  cmp     qword ptr [r15+18h], 7
0x1800124f2  mov     r8, [r15+10h]; N
0x1800124f6  jbe     short loc_1800124FD
0x1800124f8  mov     rcx, [r15]
0x1800124fb  jmp     short loc_180012500
0x1800124fd  mov     rcx, r15; S1
0x180012500  cmp     r8, [rsi+20h]
0x180012504  jnz     short loc_1800124D2
0x180012506  test    r8, r8
0x180012509  jz      short loc_180012514
0x18001250b  call    wmemcmp
0x180012510  test    eax, eax
0x180012512  jnz     short loc_1800124D2
0x180012514  mov     r8, [rsi]
0x180012517  mov     rdx, [rbx+8]
0x18001251b  mov     [rdx], rdi
0x18001251e  mov     rcx, [rdi+8]
0x180012522  mov     [rcx], r8
0x180012525  mov     rax, [r8+8]
0x180012529  mov     [rax], rbx
0x18001252c  mov     [r8+8], rcx
0x180012530  mov     [rdi+8], rdx
0x180012534  mov     [rbx+8], rax
0x180012538  jmp     short loc_18001255D
0x18001253a  mov     rdx, [rbx+8]
0x18001253e  mov     [rdx], rdi
0x180012541  mov     rax, [rdi+8]
0x180012545  mov     [rax], rsi
0x180012548  mov     rcx, [r8]
0x18001254b  mov     [rcx], rbx
0x18001254e  mov     [r8], rax
0x180012551  mov     [rdi+8], rdx
0x180012555  mov     [rbx+8], rcx
0x180012559  mov     [r12+r14*8], rbx
0x18001255d  lea     rsi, [r13+18h]
0x180012561  mov     rbx, rdi
0x180012564  jmp     loc_1800123F0
0x180012569  add     rsp, 28h
0x18001256d  pop     r15
0x18001256f  pop     r14
0x180012571  pop     r13
0x180012573  pop     r12
0x180012575  pop     rdi
0x180012576  pop     rsi
0x180012577  pop     rbp
0x180012578  pop     rbx
0x180012579  retn
```
