# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x140010df0`
- end: `0x14001101d`
- name: `?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `557`
- prototype: `int __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000fab8`

## callees

- `0x140010cc4`
- `0x140010df0`
- `0x140011024`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140010e30`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140010e30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // r12
  unsigned __int64 v4; // rcx
  __int64 v5; // rbx
  unsigned __int64 v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  const wchar_t **v10; // r15
  const wchar_t *v11; // r8
  _QWORD *v12; // r10
  unsigned __int64 v13; // rdx
  __int64 i; // r14
  __int64 v15; // rbp
  __int64 v16; // r14
  _QWORD *v17; // rsi
  const wchar_t *v18; // rdx
  const wchar_t *v19; // rcx
  _QWORD *v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  unsigned __int64 *v23; // r8
  const wchar_t *v24; // rdx
  size_t v25; // r8
  const wchar_t *v26; // rcx
  _QWORD *v27; // r8
  _QWORD *v28; // rdx
  _QWORD *v29; // rcx
  _QWORD *v30; // rdx
  _QWORD *v31; // rcx

  _BitScanReverse64(&v2, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v2 )
    std::_Xlength_error("invalid hash bucket count");
  v3 = qword_1400460A8;
  _BitScanReverse64(&v4, (a2 - 1) | 1);
  v5 = 1LL << ((unsigned __int8)v4 + 1);
  LODWORD(v6) = std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
                  &qword_1400460B8,
                  2 * v5,
                  qword_1400460A8);
  v7 = v5 - 1;
  qword_1400460D8 = v5;
  qword_1400460D0 = v5 - 1;
  v8 = *(_QWORD **)qword_1400460A8;
  v9 = *(_QWORD **)qword_1400460A8;
  while ( v8 != (_QWORD *)v3 )
  {
    v9 = (_QWORD *)*v9;
    v10 = (const wchar_t **)(v8 + 2);
    v11 = (const wchar_t *)(v8 + 2);
    v12 = (_QWORD *)v8[4];
    if ( v8[5] > 7u )
      v11 = *v10;
    v13 = 0;
    for ( i = 0xCBF29CE484222325uLL; v13 < 2 * (__int64)v12; i = 0x100000001B3LL * (v6 ^ i) )
      v6 = *((unsigned __int8 *)v11 + v13++);
    v15 = qword_1400460B8;
    v16 = 2 * (v7 & i);
    if ( *(_QWORD *)(qword_1400460B8 + 8 * v16) == v3 )
    {
      *(_QWORD *)(qword_1400460B8 + 8 * v16) = v8;
LABEL_11:
      *(_QWORD *)(v15 + 8 * v16 + 8) = v8;
      goto LABEL_32;
    }
    v17 = *(_QWORD **)(qword_1400460B8 + 8 * v16 + 8);
    v18 = (const wchar_t *)(v17 + 2);
    v6 = v17[4];
    if ( v17[5] > 7u )
      v18 = *(const wchar_t **)v18;
    v19 = (const wchar_t *)(v8 + 2);
    if ( v8[5] > 7u )
      v19 = *v10;
    if ( v12 == (_QWORD *)v6 )
    {
      if ( !v12 || (LODWORD(v6) = wmemcmp(v19, v18, v8[4]), !(_DWORD)v6) )
      {
        v20 = (_QWORD *)*v17;
        if ( (_QWORD *)*v17 != v8 )
        {
          v21 = (_QWORD *)v8[1];
          *v21 = v9;
          v22 = (_QWORD *)v9[1];
          *v22 = v20;
          v6 = v20[1];
          *(_QWORD *)v6 = v8;
          v20[1] = v22;
          v9[1] = v21;
          v8[1] = v6;
        }
        goto LABEL_11;
      }
    }
    while ( 1 )
    {
      v23 = v17 + 1;
      if ( *(_QWORD **)(v15 + 8 * v16) == v17 )
        break;
      v17 = (_QWORD *)*v23;
      v24 = (const wchar_t *)(*v23 + 16);
      if ( *(_QWORD *)(*v23 + 40) > 7u )
        v24 = *(const wchar_t **)v24;
      v25 = v8[4];
      if ( v8[5] <= 7u )
        v26 = (const wchar_t *)(v8 + 2);
      else
        v26 = *v10;
      if ( v25 == v17[4] && (!v25 || !wmemcmp(v26, v24, v25)) )
      {
        v27 = (_QWORD *)*v17;
        v28 = (_QWORD *)v8[1];
        *v28 = v9;
        v29 = (_QWORD *)v9[1];
        *v29 = v27;
        v6 = v27[1];
        *(_QWORD *)v6 = v8;
        v27[1] = v29;
        v9[1] = v28;
        v8[1] = v6;
        goto LABEL_32;
      }
    }
    v30 = (_QWORD *)v8[1];
    *v30 = v9;
    v6 = v9[1];
    *(_QWORD *)v6 = v17;
    v31 = (_QWORD *)*v23;
    *v31 = v8;
    *v23 = v6;
    v9[1] = v30;
    v8[1] = v31;
    *(_QWORD *)(v15 + 8 * v16) = v8;
LABEL_32:
    v7 = qword_1400460D0;
    v8 = v9;
  }
  return v6;
}

```

## disassembly

```asm
0x140010df0  mov     [rsp+arg_8], rbx
0x140010df5  mov     [rsp+arg_10], rbp
0x140010dfa  push    rsi
0x140010dfb  push    rdi
0x140010dfc  push    r12
0x140010dfe  push    r14
0x140010e00  push    r15
0x140010e02  sub     rsp, 20h
0x140010e06  mov     rax, 0FFFFFFFFFFFFFFFh
0x140010e10  mov     [rsp+48h+arg_0], 0
0x140010e18  bsr     rcx, rax
0x140010e1c  mov     eax, 1
0x140010e21  shl     rax, cl
0x140010e24  cmp     rdx, rax
0x140010e27  jbe     short loc_140010E37
0x140010e29  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x140010e30  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140010e37  mov     r12, cs:qword_1400460A8
0x140010e3e  lea     rax, [rdx-1]
0x140010e42  or      rax, 1
0x140010e46  mov     [rsp+48h+arg_0], 0
0x140010e4e  bsr     rcx, rax
0x140010e52  mov     ebx, 1
0x140010e57  mov     r8, r12
0x140010e5a  inc     ecx
0x140010e5c  shl     rbx, cl
0x140010e5f  lea     rcx, qword_1400460B8
0x140010e66  lea     rdx, [rbx+rbx]
0x140010e6a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x140010e6f  lea     rcx, [rbx-1]
0x140010e73  mov     cs:qword_1400460D8, rbx
0x140010e7a  mov     rbx, cs:qword_1400460A8
0x140010e81  mov     cs:qword_1400460D0, rcx
0x140010e88  mov     rbx, [rbx]
0x140010e8b  mov     rdi, rbx
0x140010e8e  cmp     rbx, r12
0x140010e91  jz      loc_140011006
0x140010e97  mov     rdi, [rdi]
0x140010e9a  lea     r15, [rbx+10h]
0x140010e9e  cmp     qword ptr [r15+18h], 7
0x140010ea3  mov     r8, r15
0x140010ea6  mov     r10, [r15+10h]
0x140010eaa  jbe     short loc_140010EAF
0x140010eac  mov     r8, [r15]
0x140010eaf  lea     r9, [r10+r10]
0x140010eb3  xor     edx, edx
0x140010eb5  mov     r14, 0CBF29CE484222325h
0x140010ebf  test    r9, r9
0x140010ec2  jz      short loc_140010EE2
0x140010ec4  movzx   eax, byte ptr [r8+rdx]
0x140010ec9  mov     r11, 100000001B3h
0x140010ed3  xor     r14, rax
0x140010ed6  inc     rdx
0x140010ed9  imul    r14, r11
0x140010edd  cmp     rdx, r9
0x140010ee0  jb      short loc_140010EC4
0x140010ee2  mov     rbp, cs:qword_1400460B8
0x140010ee9  and     r14, rcx
0x140010eec  add     r14, r14
0x140010eef  cmp     [rbp+r14*8+0], r12
0x140010ef4  jnz     short loc_140010F05
0x140010ef6  mov     [rbp+r14*8+0], rbx
0x140010efb  mov     [rbp+r14*8+8], rbx
0x140010f00  jmp     loc_140010FF7
0x140010f05  mov     rsi, [rbp+r14*8+8]
0x140010f0a  lea     rdx, [rsi+10h]
0x140010f0e  cmp     qword ptr [rdx+18h], 7
0x140010f13  mov     rax, [rdx+10h]
0x140010f17  jbe     short loc_140010F1C
0x140010f19  mov     rdx, [rdx]; S2
0x140010f1c  cmp     qword ptr [r15+18h], 7
0x140010f21  mov     rcx, r15
0x140010f24  jbe     short loc_140010F29
0x140010f26  mov     rcx, [r15]; S1
0x140010f29  cmp     r10, rax
0x140010f2c  jnz     short loc_140010F6A
0x140010f2e  test    r10, r10
0x140010f31  jz      short loc_140010F3F
0x140010f33  mov     r8, r10; N
0x140010f36  call    wmemcmp
0x140010f3b  test    eax, eax
0x140010f3d  jnz     short loc_140010F6A
0x140010f3f  mov     r8, [rsi]
0x140010f42  cmp     r8, rbx
0x140010f45  jz      short loc_140010EFB
0x140010f47  mov     rdx, [rbx+8]
0x140010f4b  mov     [rdx], rdi
0x140010f4e  mov     rcx, [rdi+8]
0x140010f52  mov     [rcx], r8
0x140010f55  mov     rax, [r8+8]
0x140010f59  mov     [rax], rbx
0x140010f5c  mov     [r8+8], rcx
0x140010f60  mov     [rdi+8], rdx
0x140010f64  mov     [rbx+8], rax
0x140010f68  jmp     short loc_140010EFB
0x140010f6a  lea     r8, [rsi+8]
0x140010f6e  cmp     [rbp+r14*8+0], rsi
0x140010f73  jz      short loc_140010FD3
0x140010f75  mov     rsi, [r8]
0x140010f78  cmp     qword ptr [rsi+28h], 7
0x140010f7d  lea     rdx, [rsi+10h]
0x140010f81  jbe     short loc_140010F86
0x140010f83  mov     rdx, [rdx]; S2
0x140010f86  cmp     qword ptr [r15+18h], 7
0x140010f8b  mov     r8, [r15+10h]; N
0x140010f8f  jbe     short loc_140010F96
0x140010f91  mov     rcx, [r15]
0x140010f94  jmp     short loc_140010F99
0x140010f96  mov     rcx, r15; S1
0x140010f99  cmp     r8, [rsi+20h]
0x140010f9d  jnz     short loc_140010F6A
0x140010f9f  test    r8, r8
0x140010fa2  jz      short loc_140010FAD
0x140010fa4  call    wmemcmp
0x140010fa9  test    eax, eax
0x140010fab  jnz     short loc_140010F6A
0x140010fad  mov     r8, [rsi]
0x140010fb0  mov     rdx, [rbx+8]
0x140010fb4  mov     [rdx], rdi
0x140010fb7  mov     rcx, [rdi+8]
0x140010fbb  mov     [rcx], r8
0x140010fbe  mov     rax, [r8+8]
0x140010fc2  mov     [rax], rbx
0x140010fc5  mov     [r8+8], rcx
0x140010fc9  mov     [rdi+8], rdx
0x140010fcd  mov     [rbx+8], rax
0x140010fd1  jmp     short loc_140010FF7
0x140010fd3  mov     rdx, [rbx+8]
0x140010fd7  mov     [rdx], rdi
0x140010fda  mov     rax, [rdi+8]
0x140010fde  mov     [rax], rsi
0x140010fe1  mov     rcx, [r8]
0x140010fe4  mov     [rcx], rbx
0x140010fe7  mov     [r8], rax
0x140010fea  mov     [rdi+8], rdx
0x140010fee  mov     [rbx+8], rcx
0x140010ff2  mov     [rbp+r14*8+0], rbx
0x140010ff7  mov     rcx, cs:qword_1400460D0
0x140010ffe  mov     rbx, rdi
0x140011001  jmp     loc_140010E8E
0x140011006  mov     rbx, [rsp+48h+arg_8]
0x14001100b  mov     rbp, [rsp+48h+arg_10]
0x140011010  add     rsp, 20h
0x140011014  pop     r15
0x140011016  pop     r14
0x140011018  pop     r12
0x14001101a  pop     rdi
0x14001101b  pop     rsi
0x14001101c  retn
```
