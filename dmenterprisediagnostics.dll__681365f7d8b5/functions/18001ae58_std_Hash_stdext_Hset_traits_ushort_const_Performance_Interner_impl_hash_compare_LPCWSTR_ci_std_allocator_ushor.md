# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18001ae58`
- end: `0x18001affa`
- name: `?_Forced_rehash@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAX_K@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018cd8`

## callees

- `0x180019234`
- `0x180019414`
- `0x1800194a0`
- `0x18001ad20`
- `0x18001ae58`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001ae98`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001ae98`

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
  _QWORD *v15; // rdx
  _QWORD *v16; // rax
  _QWORD *v17; // r8
  _QWORD *v18; // r8
  _QWORD *v19; // rdx
  _QWORD *v20; // rax
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
    v10 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(v7, v8[2]);
    v11 = a1[3];
    v12 = 2 * (v10 & a1[6]);
    if ( *(_QWORD **)(v11 + 16 * (v10 & a1[6])) == v4 )
    {
      *(_QWORD *)(v11 + 16 * (v10 & a1[6])) = v8;
LABEL_7:
      *(_QWORD *)(v11 + 8 * v12 + 8) = v8;
      goto LABEL_15;
    }
    v13 = *(_QWORD **)(v11 + 16 * (v10 & a1[6]) + 8);
    if ( !(unsigned __int8)Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(v7, v8[2], v13[2]) )
    {
      v14 = (_QWORD *)*v13;
      if ( (_QWORD *)*v13 != v8 )
      {
        v15 = (_QWORD *)v8[1];
        *v15 = v9;
        v7 = (_QWORD *)v9[1];
        *v7 = v14;
        v16 = (_QWORD *)v14[1];
        *v16 = v8;
        v14[1] = v7;
        v9[1] = v15;
        v8[1] = v16;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v17 = v13 + 1;
      if ( *(_QWORD **)(v11 + 8 * v12) == v13 )
        break;
      v13 = (_QWORD *)*v17;
      if ( !(unsigned __int8)Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(
                               v7,
                               v8[2],
                               *(_QWORD *)(*v17 + 16LL)) )
      {
        v18 = (_QWORD *)*v13;
        v19 = (_QWORD *)v8[1];
        *v19 = v9;
        v7 = (_QWORD *)v9[1];
        *v7 = v18;
        v20 = (_QWORD *)v18[1];
        *v20 = v8;
        v18[1] = v7;
        v9[1] = v19;
        v8[1] = v20;
        goto LABEL_15;
      }
    }
    v21 = (_QWORD *)v8[1];
    *v21 = v9;
    v22 = (_QWORD *)v9[1];
    *v22 = v13;
    v7 = (_QWORD *)*v17;
    *v7 = v8;
    *v17 = v22;
    v9[1] = v21;
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
0x18001ae58  push    rbx
0x18001ae5a  push    rbp
0x18001ae5b  push    rsi
0x18001ae5c  push    rdi
0x18001ae5d  push    r12
0x18001ae5f  push    r13
0x18001ae61  push    r14
0x18001ae63  push    r15
0x18001ae65  sub     rsp, 28h
0x18001ae69  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001ae73  mov     dword ptr [rsp+68h+arg_8], 0
0x18001ae7b  mov     r15, rcx
0x18001ae7e  mov     ebx, 1
0x18001ae83  bsr     rcx, rax
0x18001ae87  mov     eax, ebx
0x18001ae89  shl     rax, cl
0x18001ae8c  cmp     rdx, rax
0x18001ae8f  jbe     short loc_18001AEA5
0x18001ae91  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18001ae98  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001aea5  mov     r12, [r15+8]
0x18001aea9  lea     rax, [rdx-1]
0x18001aead  or      rax, rbx
0x18001aeb0  mov     dword ptr [rsp+68h+arg_8], 0
0x18001aeb8  bsr     rcx, rax
0x18001aebc  mov     r8, r12
0x18001aebf  inc     ecx
0x18001aec1  shl     rbx, cl
0x18001aec4  lea     rcx, [r15+18h]
0x18001aec8  lea     rdx, [rbx+rbx]
0x18001aecc  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)
0x18001aed1  lea     rax, [rbx-1]
0x18001aed5  mov     [r15+38h], rbx
0x18001aed9  mov     [r15+30h], rax
0x18001aedd  mov     rbx, [r15+8]
0x18001aee1  mov     rbx, [rbx]
0x18001aee4  mov     rdi, rbx
0x18001aee7  cmp     rbx, r12
0x18001aeea  jz      loc_18001AFD5
0x18001aef0  mov     rdx, [rbx+10h]
0x18001aef4  mov     rdi, [rdi]
0x18001aef7  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x18001aefc  mov     r14, [r15+30h]
0x18001af00  mov     rbp, [r15+18h]
0x18001af04  and     r14, rax
0x18001af07  add     r14, r14
0x18001af0a  cmp     [rbp+r14*8+0], r12
0x18001af0f  jnz     short loc_18001AF20
0x18001af11  mov     [rbp+r14*8+0], rbx
0x18001af16  mov     [rbp+r14*8+8], rbx
0x18001af1b  jmp     loc_18001AFCD
0x18001af20  mov     rsi, [rbp+r14*8+8]
0x18001af25  mov     rdx, [rbx+10h]
0x18001af29  mov     r8, [rsi+10h]
0x18001af2d  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_NPEBG0@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *,ushort const *)
0x18001af32  test    al, al
0x18001af34  jnz     short loc_18001AF61
0x18001af36  mov     r8, [rsi]
0x18001af39  cmp     r8, rbx
0x18001af3c  jz      short loc_18001AF16
0x18001af3e  mov     rdx, [rbx+8]
0x18001af42  mov     [rdx], rdi
0x18001af45  mov     rcx, [rdi+8]
0x18001af49  mov     [rcx], r8
0x18001af4c  mov     rax, [r8+8]
0x18001af50  mov     [rax], rbx
0x18001af53  mov     [r8+8], rcx
0x18001af57  mov     [rdi+8], rdx
0x18001af5b  mov     [rbx+8], rax
0x18001af5f  jmp     short loc_18001AF16
0x18001af61  mov     rax, rsi
0x18001af64  lea     r8, [rsi+8]
0x18001af68  cmp     [rbp+r14*8+0], rax
0x18001af6d  jz      short loc_18001AFA9
0x18001af6f  mov     rsi, [r8]
0x18001af72  mov     rdx, [rbx+10h]
0x18001af76  mov     r8, [rsi+10h]
0x18001af7a  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_NPEBG0@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *,ushort const *)
0x18001af7f  test    al, al
0x18001af81  jnz     short loc_18001AF61
0x18001af83  mov     r8, [rsi]
0x18001af86  mov     rdx, [rbx+8]
0x18001af8a  mov     [rdx], rdi
0x18001af8d  mov     rcx, [rdi+8]
0x18001af91  mov     [rcx], r8
0x18001af94  mov     rax, [r8+8]
0x18001af98  mov     [rax], rbx
0x18001af9b  mov     [r8+8], rcx
0x18001af9f  mov     [rdi+8], rdx
0x18001afa3  mov     [rbx+8], rax
0x18001afa7  jmp     short loc_18001AFCD
0x18001afa9  mov     rdx, [rbx+8]
0x18001afad  mov     [rdx], rdi
0x18001afb0  mov     rax, [rdi+8]
0x18001afb4  mov     [rax], rsi
0x18001afb7  mov     rcx, [r8]
0x18001afba  mov     [rcx], rbx
0x18001afbd  mov     [r8], rax
0x18001afc0  mov     [rdi+8], rdx
0x18001afc4  mov     [rbx+8], rcx
0x18001afc8  mov     [rbp+r14*8+0], rbx
0x18001afcd  mov     rbx, rdi
0x18001afd0  jmp     loc_18001AEE7
0x18001afd5  lea     rcx, [rsp+68h+arg_8]
0x18001afda  mov     [rsp+68h+arg_8], 0
0x18001afe3  call    ??1_Clear_guard@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Clear_guard::~_Clear_guard(void)
0x18001afe8  add     rsp, 28h
0x18001afec  pop     r15
0x18001afee  pop     r14
0x18001aff0  pop     r13
0x18001aff2  pop     r12
0x18001aff4  pop     rdi
0x18001aff5  pop     rsi
0x18001aff6  pop     rbp
0x18001aff7  pop     rbx
0x18001aff8  retn
```
