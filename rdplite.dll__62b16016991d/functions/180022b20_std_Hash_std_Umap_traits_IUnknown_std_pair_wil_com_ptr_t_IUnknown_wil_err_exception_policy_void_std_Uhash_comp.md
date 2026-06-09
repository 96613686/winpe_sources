# std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180022b20`
- end: `0x180022c92`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f8ac`

## callees

- `0x180008be0`
- `0x18000d118`
- `0x18001effc`
- `0x180020aa8`
- `0x180022b20`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  __int64 v6; // rdi
  unsigned __int64 *v7; // rcx
  unsigned __int64 v8; // r8
  __int64 i; // r10
  unsigned __int64 appended; // rax
  unsigned __int64 **v11; // rdx
  unsigned __int64 v12; // r10
  __int64 v13; // r11
  __int64 v14; // r9
  unsigned __int64 *v15; // rax
  unsigned __int64 v16; // rdi
  _QWORD *v17; // rdx
  unsigned __int64 *v18; // rax
  unsigned __int64 **v19; // rdi
  _QWORD *v20; // rdx
  unsigned __int64 *v21; // rax
  _QWORD *v22; // rdx
  unsigned __int64 *v23; // rax
  __int64 v25; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(v25) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = a1[1];
  LODWORD(v25) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  for ( i = *(_QWORD *)a1[1]; i != v4; i = v13 )
  {
    appended = std::_Fnv1a_append_bytes((unsigned __int64)v7, (const unsigned __int8 *const)(i + 16), v8);
    v14 = a1[3];
    v8 = 2 * (a1[6] & appended);
    if ( *(_QWORD *)(v14 + 16 * (a1[6] & appended)) == v4 )
    {
      *(_QWORD *)(v14 + 16 * (a1[6] & appended)) = v12;
LABEL_7:
      *(_QWORD *)(v14 + 8 * v8 + 8) = v12;
      continue;
    }
    v15 = *(unsigned __int64 **)(v14 + 16 * (a1[6] & appended) + 8);
    v7 = *v11;
    if ( *v11 == (unsigned __int64 *)v15[2] )
    {
      v16 = *v15;
      if ( *v15 != v12 )
      {
        v17 = *(_QWORD **)(v12 + 8);
        *v17 = v13;
        v7 = *(unsigned __int64 **)(v13 + 8);
        *v7 = v16;
        v18 = *(unsigned __int64 **)(v16 + 8);
        *v18 = v12;
        *(_QWORD *)(v16 + 8) = v7;
        *(_QWORD *)(v13 + 8) = v17;
        *(_QWORD *)(v12 + 8) = v18;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v19 = (unsigned __int64 **)(v15 + 1);
      if ( *(unsigned __int64 **)(v14 + 8 * v8) == v15 )
        break;
      v15 = *v19;
      if ( v7 == (unsigned __int64 *)(*v19)[2] )
      {
        v8 = *v15;
        v20 = *(_QWORD **)(v12 + 8);
        *v20 = v13;
        v7 = *(unsigned __int64 **)(v13 + 8);
        *v7 = v8;
        v21 = *(unsigned __int64 **)(v8 + 8);
        *v21 = v12;
        *(_QWORD *)(v8 + 8) = v7;
        *(_QWORD *)(v13 + 8) = v20;
        *(_QWORD *)(v12 + 8) = v21;
        goto LABEL_15;
      }
    }
    v22 = *(_QWORD **)(v12 + 8);
    *v22 = v13;
    v7 = *(unsigned __int64 **)(v13 + 8);
    *v7 = (unsigned __int64)v15;
    v23 = *v19;
    *v23 = v12;
    *v19 = v7;
    *(_QWORD *)(v13 + 8) = v22;
    *(_QWORD *)(v12 + 8) = v23;
    *(_QWORD *)(v14 + 8 * v8) = v12;
LABEL_15:
    ;
  }
  v25 = 0;
  return std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Clear_guard::~_Clear_guard(&v25);
}

```

## disassembly

```asm
0x180022b20  push    rbx
0x180022b22  push    rsi
0x180022b23  push    rdi
0x180022b24  push    r14
0x180022b26  sub     rsp, 28h
0x180022b2a  mov     rax, 0FFFFFFFFFFFFFFFh
0x180022b34  mov     dword ptr [rsp+48h+arg_8], 0
0x180022b3c  mov     rsi, rcx
0x180022b3f  mov     edi, 1
0x180022b44  bsr     rcx, rax
0x180022b48  mov     eax, edi
0x180022b4a  shl     rax, cl
0x180022b4d  cmp     rdx, rax
0x180022b50  jbe     short loc_180022B5F
0x180022b52  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180022b59  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180022b5f  mov     rbx, [rsi+8]
0x180022b63  lea     rax, [rdx-1]
0x180022b67  or      rax, rdi
0x180022b6a  mov     dword ptr [rsp+48h+arg_8], 0
0x180022b72  bsr     rcx, rax
0x180022b76  mov     r8, rbx
0x180022b79  inc     ecx
0x180022b7b  shl     rdi, cl
0x180022b7e  lea     rcx, [rsi+18h]
0x180022b82  lea     rdx, [rdi+rdi]
0x180022b86  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>)
0x180022b8b  mov     [rsi+38h], rdi
0x180022b8f  lea     rax, [rdi-1]
0x180022b93  mov     [rsi+30h], rax
0x180022b97  mov     r10, [rsi+8]
0x180022b9b  mov     r10, [r10]
0x180022b9e  mov     r11, r10
0x180022ba1  cmp     r10, rbx
0x180022ba4  jz      loc_180022C75
0x180022baa  mov     r11, [r11]
0x180022bad  lea     rdx, [r10+10h]; unsigned __int8 *
0x180022bb1  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180022bb6  mov     r9, [rsi+18h]
0x180022bba  mov     r8, rax
0x180022bbd  and     r8, [rsi+30h]
0x180022bc1  add     r8, r8
0x180022bc4  cmp     [r9+r8*8], rbx
0x180022bc8  jnz     short loc_180022BD8
0x180022bca  mov     [r9+r8*8], r10
0x180022bce  mov     [r9+r8*8+8], r10
0x180022bd3  jmp     loc_180022C6D
0x180022bd8  mov     rax, [r9+r8*8+8]
0x180022bdd  mov     rcx, [rdx]
0x180022be0  cmp     rcx, [rax+10h]
0x180022be4  jnz     short loc_180022C11
0x180022be6  mov     rdi, [rax]
0x180022be9  cmp     rdi, r10
0x180022bec  jz      short loc_180022BCE
0x180022bee  mov     rdx, [r10+8]
0x180022bf2  mov     [rdx], r11
0x180022bf5  mov     rcx, [r11+8]
0x180022bf9  mov     [rcx], rdi
0x180022bfc  mov     rax, [rdi+8]
0x180022c00  mov     [rax], r10
0x180022c03  mov     [rdi+8], rcx
0x180022c07  mov     [r11+8], rdx
0x180022c0b  mov     [r10+8], rax
0x180022c0f  jmp     short loc_180022BCE
0x180022c11  lea     rdi, [rax+8]
0x180022c15  cmp     [r9+r8*8], rax
0x180022c19  jz      short loc_180022C4A
0x180022c1b  mov     rax, [rdi]
0x180022c1e  cmp     rcx, [rax+10h]
0x180022c22  jnz     short loc_180022C11
0x180022c24  mov     r8, [rax]
0x180022c27  mov     rdx, [r10+8]
0x180022c2b  mov     [rdx], r11
0x180022c2e  mov     rcx, [r11+8]
0x180022c32  mov     [rcx], r8
0x180022c35  mov     rax, [r8+8]
0x180022c39  mov     [rax], r10
0x180022c3c  mov     [r8+8], rcx
0x180022c40  mov     [r11+8], rdx
0x180022c44  mov     [r10+8], rax
0x180022c48  jmp     short loc_180022C6D
0x180022c4a  mov     rdx, [r10+8]
0x180022c4e  mov     [rdx], r11
0x180022c51  mov     rcx, [r11+8]
0x180022c55  mov     [rcx], rax
0x180022c58  mov     rax, [rdi]
0x180022c5b  mov     [rax], r10
0x180022c5e  mov     [rdi], rcx
0x180022c61  mov     [r11+8], rdx
0x180022c65  mov     [r10+8], rax
0x180022c69  mov     [r9+r8*8], r10
0x180022c6d  mov     r10, r11
0x180022c70  jmp     loc_180022BA1
0x180022c75  lea     rcx, [rsp+48h+arg_8]
0x180022c7a  mov     [rsp+48h+arg_8], 0
0x180022c83  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180022c88  add     rsp, 28h
0x180022c8c  pop     r14
0x180022c8e  pop     rdi
0x180022c8f  pop     rsi
0x180022c90  pop     rbx
0x180022c91  retn
```
