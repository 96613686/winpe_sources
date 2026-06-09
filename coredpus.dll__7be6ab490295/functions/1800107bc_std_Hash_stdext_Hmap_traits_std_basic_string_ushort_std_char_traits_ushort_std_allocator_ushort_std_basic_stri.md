# std::_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x1800107bc`
- end: `0x1800109a8`
- name: `?_Forced_rehash@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEAAX_K@Z`
- size: `492`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800060a0`
- `0x18001d604`

## callees

- `0x1800107bc`
- `0x1800109b0`
- `0x180010a68`
- `0x1800138e0`
- `0x18001d224`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800107fc`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800107fc`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  _QWORD *v11; // r12
  __int64 v12; // rax
  __int64 v13; // r15
  __int64 v14; // r14
  _QWORD *v15; // rsi
  _QWORD *v16; // r8
  _QWORD *v17; // rcx
  _QWORD *v18; // r8
  bool v19; // cc
  _QWORD *v20; // r8
  _QWORD *v21; // rcx
  _QWORD *v22; // r8
  _QWORD *v23; // rdx
  _QWORD *v24; // rax
  _QWORD *v25; // rdx
  _QWORD *v26; // rax
  _QWORD *v27; // r8
  _QWORD *v28; // rdx
  _QWORD *v29; // rax
  __int64 v31; // [rsp+78h] [rbp+10h] BYREF

  LODWORD(v31) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  LODWORD(v31) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v7,
    v4);
  a1[7] = v7;
  a1[6] = v7 - 1;
  v9 = *(_QWORD **)a1[1];
  v10 = v9;
  while ( v9 != v4 )
  {
    v10 = (_QWORD *)*v10;
    v11 = v9 + 2;
    v12 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v8, v9 + 2);
    v13 = *v6;
    v14 = 2 * (a1[6] & v12);
    if ( *(_QWORD **)(*v6 + 16 * (a1[6] & v12)) == v4 )
    {
      *(_QWORD *)(v13 + 16 * (a1[6] & v12)) = v9;
LABEL_26:
      *(_QWORD *)(v13 + 8 * v14 + 8) = v9;
      goto LABEL_27;
    }
    v15 = *(_QWORD **)(v13 + 16 * (a1[6] & v12) + 8);
    v16 = v15 + 2;
    if ( v15[5] > 7u )
      v16 = (_QWORD *)*v16;
    if ( v9[5] <= 7u )
      v17 = v9 + 2;
    else
      v17 = (_QWORD *)*v11;
    if ( (int)std::_Traits_compare<std::char_traits<unsigned short>>(v17, v9[4], v16, v15[4]) >= 0 )
    {
      v27 = (_QWORD *)*v15;
      if ( (_QWORD *)*v15 != v9 )
      {
        v28 = (_QWORD *)v9[1];
        *v28 = v10;
        v8 = (_QWORD *)v10[1];
        *v8 = v27;
        v29 = (_QWORD *)v27[1];
        *v29 = v9;
        v27[1] = v8;
        v10[1] = v28;
        v9[1] = v29;
      }
      v6 = a1 + 3;
      goto LABEL_26;
    }
    while ( 1 )
    {
      v18 = v15 + 1;
      if ( *(_QWORD **)(v13 + 8 * v14) == v15 )
        break;
      v15 = (_QWORD *)*v18;
      v19 = *(_QWORD *)(*v18 + 40LL) <= 7u;
      v20 = (_QWORD *)(*v18 + 16LL);
      if ( !v19 )
        v20 = (_QWORD *)*v20;
      if ( v9[5] <= 7u )
        v21 = v9 + 2;
      else
        v21 = (_QWORD *)*v11;
      if ( (int)std::_Traits_compare<std::char_traits<unsigned short>>(v21, v9[4], v20, v15[4]) >= 0 )
      {
        v22 = (_QWORD *)*v15;
        v23 = (_QWORD *)v9[1];
        *v23 = v10;
        v8 = (_QWORD *)v10[1];
        *v8 = v22;
        v24 = (_QWORD *)v22[1];
        *v24 = v9;
        v22[1] = v8;
        v10[1] = v23;
        v9[1] = v24;
        goto LABEL_22;
      }
    }
    v25 = (_QWORD *)v9[1];
    *v25 = v10;
    v26 = (_QWORD *)v10[1];
    *v26 = v15;
    v8 = (_QWORD *)*v18;
    *v8 = v9;
    *v18 = v26;
    v10[1] = v25;
    v9[1] = v8;
    *(_QWORD *)(v13 + 8 * v14) = v9;
LABEL_22:
    v6 = a1 + 3;
LABEL_27:
    v9 = v10;
  }
  v31 = 0;
  return std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(&v31);
}

```

## disassembly

```asm
0x1800107bc  push    rbx
0x1800107be  push    rbp
0x1800107bf  push    rsi
0x1800107c0  push    rdi
0x1800107c1  push    r12
0x1800107c3  push    r13
0x1800107c5  push    r14
0x1800107c7  push    r15
0x1800107c9  sub     rsp, 28h
0x1800107cd  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800107d7  mov     dword ptr [rsp+68h+arg_8], 0
0x1800107df  mov     r13, rcx
0x1800107e2  mov     ebx, 1
0x1800107e7  bsr     rcx, rax
0x1800107eb  mov     eax, ebx
0x1800107ed  shl     rax, cl
0x1800107f0  cmp     rdx, rax
0x1800107f3  jbe     short loc_180010809
0x1800107f5  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x1800107fc  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180010809  mov     rbp, [r13+8]
0x18001080d  lea     rax, [rdx-1]
0x180010811  or      rax, rbx
0x180010814  mov     dword ptr [rsp+68h+arg_8], 0
0x18001081c  bsr     rcx, rax
0x180010820  lea     rsi, [r13+18h]
0x180010824  mov     r8, rbp
0x180010827  inc     ecx
0x180010829  shl     rbx, cl
0x18001082c  mov     rcx, rsi
0x18001082f  lea     rdx, [rbx+rbx]
0x180010833  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>)
0x180010838  lea     rax, [rbx-1]
0x18001083c  mov     [r13+38h], rbx
0x180010840  mov     [r13+30h], rax
0x180010844  mov     rbx, [r13+8]
0x180010848  mov     rbx, [rbx]
0x18001084b  mov     rdi, rbx
0x18001084e  cmp     rbx, rbp
0x180010851  jz      loc_180010983
0x180010857  mov     rdi, [rdi]
0x18001085a  lea     r12, [rbx+10h]
0x18001085e  mov     rdx, r12
0x180010861  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x180010866  mov     r15, [rsi]
0x180010869  mov     r14, rax
0x18001086c  and     r14, [r13+30h]
0x180010870  add     r14, r14
0x180010873  cmp     [r15+r14*8], rbp
0x180010877  jnz     short loc_180010882
0x180010879  mov     [r15+r14*8], rbx
0x18001087d  jmp     loc_180010976
0x180010882  mov     rsi, [r15+r14*8+8]
0x180010887  lea     r8, [rsi+10h]
0x18001088b  cmp     qword ptr [r8+18h], 7
0x180010890  mov     r9, [r8+10h]
0x180010894  jbe     short loc_180010899
0x180010896  mov     r8, [r8]
0x180010899  cmp     qword ptr [r12+18h], 7
0x18001089f  jbe     short loc_1800108A7
0x1800108a1  mov     rcx, [r12]
0x1800108a5  jmp     short loc_1800108AA
0x1800108a7  mov     rcx, r12
0x1800108aa  mov     rdx, [r12+10h]
0x1800108af  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800108b4  test    eax, eax
0x1800108b6  jns     loc_180010949
0x1800108bc  lea     r8, [rsi+8]
0x1800108c0  cmp     [r15+r14*8], rsi
0x1800108c4  jz      short loc_180010920
0x1800108c6  mov     rsi, [r8]
0x1800108c9  cmp     qword ptr [rsi+28h], 7
0x1800108ce  lea     r8, [rsi+10h]
0x1800108d2  jbe     short loc_1800108D7
0x1800108d4  mov     r8, [r8]
0x1800108d7  cmp     qword ptr [r12+18h], 7
0x1800108dd  jbe     short loc_1800108E5
0x1800108df  mov     rcx, [r12]
0x1800108e3  jmp     short loc_1800108E8
0x1800108e5  mov     rcx, r12
0x1800108e8  mov     r9, [rsi+20h]
0x1800108ec  mov     rdx, [r12+10h]
0x1800108f1  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800108f6  test    eax, eax
0x1800108f8  js      short loc_1800108BC
0x1800108fa  mov     r8, [rsi]
0x1800108fd  mov     rdx, [rbx+8]
0x180010901  mov     [rdx], rdi
0x180010904  mov     rcx, [rdi+8]
0x180010908  mov     [rcx], r8
0x18001090b  mov     rax, [r8+8]
0x18001090f  mov     [rax], rbx
0x180010912  mov     [r8+8], rcx
0x180010916  mov     [rdi+8], rdx
0x18001091a  mov     [rbx+8], rax
0x18001091e  jmp     short loc_180010943
0x180010920  mov     rdx, [rbx+8]
0x180010924  mov     [rdx], rdi
0x180010927  mov     rax, [rdi+8]
0x18001092b  mov     [rax], rsi
0x18001092e  mov     rcx, [r8]
0x180010931  mov     [rcx], rbx
0x180010934  mov     [r8], rax
0x180010937  mov     [rdi+8], rdx
0x18001093b  mov     [rbx+8], rcx
0x18001093f  mov     [r15+r14*8], rbx
0x180010943  lea     rsi, [r13+18h]
0x180010947  jmp     short loc_18001097B
0x180010949  mov     r8, [rsi]
0x18001094c  cmp     r8, rbx
0x18001094f  jz      short loc_180010972
0x180010951  mov     rdx, [rbx+8]
0x180010955  mov     [rdx], rdi
0x180010958  mov     rcx, [rdi+8]
0x18001095c  mov     [rcx], r8
0x18001095f  mov     rax, [r8+8]
0x180010963  mov     [rax], rbx
0x180010966  mov     [r8+8], rcx
0x18001096a  mov     [rdi+8], rdx
0x18001096e  mov     [rbx+8], rax
0x180010972  lea     rsi, [r13+18h]
0x180010976  mov     [r15+r14*8+8], rbx
0x18001097b  mov     rbx, rdi
0x18001097e  jmp     loc_18001084E
0x180010983  lea     rcx, [rsp+68h+arg_8]
0x180010988  mov     [rsp+68h+arg_8], 0
0x180010991  call    ??1_Clear_guard@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180010996  add     rsp, 28h
0x18001099a  pop     r15
0x18001099c  pop     r14
0x18001099e  pop     r13
0x1800109a0  pop     r12
0x1800109a2  pop     rdi
0x1800109a3  pop     rsi
0x1800109a4  pop     rbp
0x1800109a5  pop     rbx
0x1800109a6  retn
```
