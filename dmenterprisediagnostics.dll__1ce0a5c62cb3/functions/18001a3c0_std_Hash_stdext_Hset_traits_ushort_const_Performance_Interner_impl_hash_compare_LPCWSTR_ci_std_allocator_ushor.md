# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18001a3c0`
- end: `0x18001a55d`
- name: `?_Forced_rehash@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAX_K@Z`
- size: `413`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018328`

## callees

- `0x180018928`
- `0x180018a4c`
- `0x18001a288`
- `0x18001a3c0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a400`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a400`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001a48a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001a4ad`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001a48a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001a4ad`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // r12
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  _QWORD *v7; // rcx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rbp
  __int64 v12; // r14
  _QWORD *v13; // rsi
  _QWORD *v14; // r8
  _QWORD *v15; // r8
  _QWORD *v16; // rdx
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rax
  __int64 v24; // [rsp+78h] [rbp+10h] BYREF

  LODWORD(v24) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  LODWORD(v24) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  v8 = *(_QWORD **)a1[1];
  v9 = v8;
  while ( v8 != v4 )
  {
    v9 = (_QWORD *)*v9;
    v10 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()((__int64)v7, (unsigned __int16 *)v8[2]);
    v11 = a1[3];
    v12 = 2 * (v10 & a1[6]);
    if ( *(_QWORD **)(v11 + 16 * (v10 & a1[6])) == v4 )
    {
      *(_QWORD *)(v11 + 16 * (v10 & a1[6])) = v8;
LABEL_14:
      *(_QWORD *)(v11 + 8 * v12 + 8) = v8;
      goto LABEL_15;
    }
    v13 = *(_QWORD **)(v11 + 16 * (v10 & a1[6]) + 8);
    if ( (int)_o__wcsicmp(v8[2], v13[2]) >= 0 )
    {
      v20 = (_QWORD *)*v13;
      if ( (_QWORD *)*v13 != v8 )
      {
        v21 = (_QWORD *)v8[1];
        *v21 = v9;
        v7 = (_QWORD *)v9[1];
        *v7 = v20;
        v22 = (_QWORD *)v20[1];
        *v22 = v8;
        v20[1] = v7;
        v9[1] = v21;
        v8[1] = v22;
      }
      goto LABEL_14;
    }
    while ( 1 )
    {
      v14 = v13 + 1;
      if ( *(_QWORD **)(v11 + 8 * v12) == v13 )
        break;
      v13 = (_QWORD *)*v14;
      if ( (int)_o__wcsicmp(v8[2], *(_QWORD *)(*v14 + 16LL)) >= 0 )
      {
        v15 = (_QWORD *)*v13;
        v16 = (_QWORD *)v8[1];
        *v16 = v9;
        v7 = (_QWORD *)v9[1];
        *v7 = v15;
        v17 = (_QWORD *)v15[1];
        *v17 = v8;
        v15[1] = v7;
        v9[1] = v16;
        v8[1] = v17;
        goto LABEL_15;
      }
    }
    v18 = (_QWORD *)v8[1];
    *v18 = v9;
    v19 = (_QWORD *)v9[1];
    *v19 = v13;
    v7 = (_QWORD *)*v14;
    *v7 = v8;
    *v14 = v19;
    v9[1] = v18;
    v8[1] = v7;
    *(_QWORD *)(v11 + 8 * v12) = v8;
LABEL_15:
    v8 = v9;
  }
  v24 = 0;
  return std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Clear_guard::~_Clear_guard(&v24);
}

```

## disassembly

```asm
0x18001a3c0  push    rbx
0x18001a3c2  push    rbp
0x18001a3c3  push    rsi
0x18001a3c4  push    rdi
0x18001a3c5  push    r12
0x18001a3c7  push    r13
0x18001a3c9  push    r14
0x18001a3cb  push    r15
0x18001a3cd  sub     rsp, 28h
0x18001a3d1  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001a3db  mov     dword ptr [rsp+68h+arg_8], 0
0x18001a3e3  mov     r15, rcx
0x18001a3e6  mov     ebx, 1
0x18001a3eb  bsr     rcx, rax
0x18001a3ef  mov     eax, ebx
0x18001a3f1  shl     rax, cl
0x18001a3f4  cmp     rdx, rax
0x18001a3f7  jbe     short loc_18001A407
0x18001a3f9  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18001a400  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001a407  mov     r12, [r15+8]
0x18001a40b  lea     rax, [rdx-1]
0x18001a40f  or      rax, rbx
0x18001a412  mov     dword ptr [rsp+68h+arg_8], 0
0x18001a41a  bsr     rcx, rax
0x18001a41e  mov     r8, r12
0x18001a421  inc     ecx
0x18001a423  shl     rbx, cl
0x18001a426  lea     rcx, [r15+18h]
0x18001a42a  lea     rdx, [rbx+rbx]
0x18001a42e  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)
0x18001a433  lea     rax, [rbx-1]
0x18001a437  mov     [r15+38h], rbx
0x18001a43b  mov     [r15+30h], rax
0x18001a43f  mov     rbx, [r15+8]
0x18001a443  mov     rbx, [rbx]
0x18001a446  mov     rdi, rbx
0x18001a449  cmp     rbx, r12
0x18001a44c  jz      loc_18001A539
0x18001a452  mov     rdx, [rbx+10h]
0x18001a456  mov     rdi, [rdi]
0x18001a459  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x18001a45e  mov     r14, [r15+30h]
0x18001a462  mov     rbp, [r15+18h]
0x18001a466  and     r14, rax
0x18001a469  add     r14, r14
0x18001a46c  cmp     [rbp+r14*8+0], r12
0x18001a471  jnz     short loc_18001A47D
0x18001a473  mov     [rbp+r14*8+0], rbx
0x18001a478  jmp     loc_18001A52C
0x18001a47d  mov     rsi, [rbp+r14*8+8]
0x18001a482  mov     rcx, [rbx+10h]
0x18001a486  mov     rdx, [rsi+10h]
0x18001a48a  call    cs:__imp__o__wcsicmp
0x18001a490  test    eax, eax
0x18001a492  jns     short loc_18001A503
0x18001a494  mov     rax, rsi
0x18001a497  lea     r8, [rsi+8]
0x18001a49b  cmp     [rbp+r14*8+0], rax
0x18001a4a0  jz      short loc_18001A4DD
0x18001a4a2  mov     rsi, [r8]
0x18001a4a5  mov     rcx, [rbx+10h]
0x18001a4a9  mov     rdx, [rsi+10h]
0x18001a4ad  call    cs:__imp__o__wcsicmp
0x18001a4b3  test    eax, eax
0x18001a4b5  js      short loc_18001A494
0x18001a4b7  mov     r8, [rsi]
0x18001a4ba  mov     rdx, [rbx+8]
0x18001a4be  mov     [rdx], rdi
0x18001a4c1  mov     rcx, [rdi+8]
0x18001a4c5  mov     [rcx], r8
0x18001a4c8  mov     rax, [r8+8]
0x18001a4cc  mov     [rax], rbx
0x18001a4cf  mov     [r8+8], rcx
0x18001a4d3  mov     [rdi+8], rdx
0x18001a4d7  mov     [rbx+8], rax
0x18001a4db  jmp     short loc_18001A531
0x18001a4dd  mov     rdx, [rbx+8]
0x18001a4e1  mov     [rdx], rdi
0x18001a4e4  mov     rax, [rdi+8]
0x18001a4e8  mov     [rax], rsi
0x18001a4eb  mov     rcx, [r8]
0x18001a4ee  mov     [rcx], rbx
0x18001a4f1  mov     [r8], rax
0x18001a4f4  mov     [rdi+8], rdx
0x18001a4f8  mov     [rbx+8], rcx
0x18001a4fc  mov     [rbp+r14*8+0], rbx
0x18001a501  jmp     short loc_18001A531
0x18001a503  mov     r8, [rsi]
0x18001a506  cmp     r8, rbx
0x18001a509  jz      short loc_18001A52C
0x18001a50b  mov     rdx, [rbx+8]
0x18001a50f  mov     [rdx], rdi
0x18001a512  mov     rcx, [rdi+8]
0x18001a516  mov     [rcx], r8
0x18001a519  mov     rax, [r8+8]
0x18001a51d  mov     [rax], rbx
0x18001a520  mov     [r8+8], rcx
0x18001a524  mov     [rdi+8], rdx
0x18001a528  mov     [rbx+8], rax
0x18001a52c  mov     [rbp+r14*8+8], rbx
0x18001a531  mov     rbx, rdi
0x18001a534  jmp     loc_18001A449
0x18001a539  lea     rcx, [rsp+68h+arg_8]
0x18001a53e  mov     [rsp+68h+arg_8], 0
0x18001a547  call    ??1_Clear_guard@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Clear_guard::~_Clear_guard(void)
0x18001a54c  add     rsp, 28h
0x18001a550  pop     r15
0x18001a552  pop     r14
0x18001a554  pop     r13
0x18001a556  pop     r12
0x18001a558  pop     rdi
0x18001a559  pop     rsi
0x18001a55a  pop     rbp
0x18001a55b  pop     rbx
0x18001a55c  retn
```
