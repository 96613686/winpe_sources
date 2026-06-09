# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x140032fb8`
- end: `0x1400331d6`
- name: `?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `542`
- prototype: `int __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002efb8`

## callees

- `0x140022f0c`
- `0x140032a44`
- `0x140032fb8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140032ff6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140032ff6`

## pseudocode

```c
int __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // r12
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
  __int64 v16; // rbp
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
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
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
0x140032fb8  push    rbx
0x140032fba  push    rbp
0x140032fbb  push    rsi
0x140032fbc  push    rdi
0x140032fbd  push    r12
0x140032fbf  push    r13
0x140032fc1  push    r14
0x140032fc3  push    r15
0x140032fc5  sub     rsp, 28h
0x140032fc9  mov     rax, 0FFFFFFFFFFFFFFFh
0x140032fd3  mov     [rsp+68h+arg_8], 0
0x140032fdb  mov     r13, rcx
0x140032fde  bsr     rcx, rax
0x140032fe2  mov     eax, 1
0x140032fe7  shl     rax, cl
0x140032fea  cmp     rdx, rax
0x140032fed  jbe     short loc_140032FFD
0x140032fef  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x140032ff6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140032ffd  mov     r12, [r13+8]
0x140033001  lea     rax, [rdx-1]
0x140033005  or      rax, 1
0x140033009  mov     [rsp+68h+arg_8], 0
0x140033011  bsr     rcx, rax
0x140033015  mov     ebx, 1
0x14003301a  lea     rsi, [r13+18h]
0x14003301e  inc     ecx
0x140033020  mov     r8, r12
0x140033023  shl     rbx, cl
0x140033026  mov     rcx, rsi
0x140033029  lea     rdx, [rbx+rbx]
0x14003302d  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x140033032  lea     rax, [rbx-1]
0x140033036  mov     [r13+38h], rbx
0x14003303a  mov     [r13+30h], rax
0x14003303e  mov     rbx, [r13+8]
0x140033042  mov     rbx, [rbx]
0x140033045  mov     rdi, rbx
0x140033048  cmp     rbx, r12
0x14003304b  jz      loc_1400331C5
0x140033051  mov     rdi, [rdi]
0x140033054  lea     r15, [rbx+10h]
0x140033058  cmp     qword ptr [r15+18h], 7
0x14003305d  mov     r8, r15
0x140033060  mov     r10, [r15+10h]
0x140033064  jbe     short loc_140033069
0x140033066  mov     r8, [r15]
0x140033069  lea     r9, [r10+r10]
0x14003306d  xor     edx, edx
0x14003306f  mov     rcx, 0CBF29CE484222325h
0x140033079  test    r9, r9
0x14003307c  jz      short loc_14003309C
0x14003307e  movzx   eax, byte ptr [r8+rdx]
0x140033083  mov     r11, 100000001B3h
0x14003308d  xor     rcx, rax
0x140033090  inc     rdx
0x140033093  imul    rcx, r11
0x140033097  cmp     rdx, r9
0x14003309a  jb      short loc_14003307E
0x14003309c  mov     r14, [r13+30h]
0x1400330a0  mov     rbp, [rsi]
0x1400330a3  and     r14, rcx
0x1400330a6  add     r14, r14
0x1400330a9  cmp     [rbp+r14*8+0], r12
0x1400330ae  jnz     short loc_1400330BF
0x1400330b0  mov     [rbp+r14*8+0], rbx
0x1400330b5  mov     [rbp+r14*8+8], rbx
0x1400330ba  jmp     loc_1400331BD
0x1400330bf  mov     rsi, [rbp+r14*8+8]
0x1400330c4  lea     rdx, [rsi+10h]
0x1400330c8  cmp     qword ptr [rdx+18h], 7
0x1400330cd  mov     rax, [rdx+10h]
0x1400330d1  jbe     short loc_1400330D6
0x1400330d3  mov     rdx, [rdx]; S2
0x1400330d6  cmp     qword ptr [r15+18h], 7
0x1400330db  mov     rcx, r15
0x1400330de  jbe     short loc_1400330E3
0x1400330e0  mov     rcx, [r15]; S1
0x1400330e3  cmp     r10, rax
0x1400330e6  jnz     short loc_14003312C
0x1400330e8  test    r10, r10
0x1400330eb  jz      short loc_1400330F9
0x1400330ed  mov     r8, r10; N
0x1400330f0  call    wmemcmp
0x1400330f5  test    eax, eax
0x1400330f7  jnz     short loc_14003312C
0x1400330f9  mov     r8, [rsi]
0x1400330fc  cmp     r8, rbx
0x1400330ff  jz      short loc_140033122
0x140033101  mov     rdx, [rbx+8]
0x140033105  mov     [rdx], rdi
0x140033108  mov     rcx, [rdi+8]
0x14003310c  mov     [rcx], r8
0x14003310f  mov     rax, [r8+8]
0x140033113  mov     [rax], rbx
0x140033116  mov     [r8+8], rcx
0x14003311a  mov     [rdi+8], rdx
0x14003311e  mov     [rbx+8], rax
0x140033122  mov     [rbp+r14*8+8], rbx
0x140033127  jmp     loc_1400331B9
0x14003312c  lea     r8, [rsi+8]
0x140033130  cmp     [rbp+r14*8+0], rsi
0x140033135  jz      short loc_140033195
0x140033137  mov     rsi, [r8]
0x14003313a  cmp     qword ptr [rsi+28h], 7
0x14003313f  lea     rdx, [rsi+10h]
0x140033143  jbe     short loc_140033148
0x140033145  mov     rdx, [rdx]; S2
0x140033148  cmp     qword ptr [r15+18h], 7
0x14003314d  mov     r8, [r15+10h]; N
0x140033151  jbe     short loc_140033158
0x140033153  mov     rcx, [r15]
0x140033156  jmp     short loc_14003315B
0x140033158  mov     rcx, r15; S1
0x14003315b  cmp     r8, [rsi+20h]
0x14003315f  jnz     short loc_14003312C
0x140033161  test    r8, r8
0x140033164  jz      short loc_14003316F
0x140033166  call    wmemcmp
0x14003316b  test    eax, eax
0x14003316d  jnz     short loc_14003312C
0x14003316f  mov     r8, [rsi]
0x140033172  mov     rdx, [rbx+8]
0x140033176  mov     [rdx], rdi
0x140033179  mov     rcx, [rdi+8]
0x14003317d  mov     [rcx], r8
0x140033180  mov     rax, [r8+8]
0x140033184  mov     [rax], rbx
0x140033187  mov     [r8+8], rcx
0x14003318b  mov     [rdi+8], rdx
0x14003318f  mov     [rbx+8], rax
0x140033193  jmp     short loc_1400331B9
0x140033195  mov     rdx, [rbx+8]
0x140033199  mov     [rdx], rdi
0x14003319c  mov     rax, [rdi+8]
0x1400331a0  mov     [rax], rsi
0x1400331a3  mov     rcx, [r8]
0x1400331a6  mov     [rcx], rbx
0x1400331a9  mov     [r8], rax
0x1400331ac  mov     [rdi+8], rdx
0x1400331b0  mov     [rbx+8], rcx
0x1400331b4  mov     [rbp+r14*8+0], rbx
0x1400331b9  lea     rsi, [r13+18h]
0x1400331bd  mov     rbx, rdi
0x1400331c0  jmp     loc_140033048
0x1400331c5  add     rsp, 28h
0x1400331c9  pop     r15
0x1400331cb  pop     r14
0x1400331cd  pop     r13
0x1400331cf  pop     r12
0x1400331d1  pop     rdi
0x1400331d2  pop     rsi
0x1400331d3  pop     rbp
0x1400331d4  pop     rbx
0x1400331d5  retn
```
