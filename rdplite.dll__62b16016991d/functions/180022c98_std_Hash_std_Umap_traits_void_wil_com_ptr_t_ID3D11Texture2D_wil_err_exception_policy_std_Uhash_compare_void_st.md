# std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180022c98`
- end: `0x180022e0a`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@IEAAX_K@Z`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f55c`
- `0x18001f704`

## callees

- `0x180008be0`
- `0x18000d118`
- `0x18001effc`
- `0x180020b28`
- `0x180022c98`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Forced_rehash(
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
  return std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>>>,0>>::_Clear_guard::~_Clear_guard(&v25);
}

```

## disassembly

```asm
0x180022c98  push    rbx
0x180022c9a  push    rsi
0x180022c9b  push    rdi
0x180022c9c  push    r14
0x180022c9e  sub     rsp, 28h
0x180022ca2  mov     rax, 0FFFFFFFFFFFFFFFh
0x180022cac  mov     dword ptr [rsp+48h+arg_8], 0
0x180022cb4  mov     rsi, rcx
0x180022cb7  mov     edi, 1
0x180022cbc  bsr     rcx, rax
0x180022cc0  mov     eax, edi
0x180022cc2  shl     rax, cl
0x180022cc5  cmp     rdx, rax
0x180022cc8  jbe     short loc_180022CD7
0x180022cca  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180022cd1  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180022cd7  mov     rbx, [rsi+8]
0x180022cdb  lea     rax, [rdx-1]
0x180022cdf  or      rax, rdi
0x180022ce2  mov     dword ptr [rsp+48h+arg_8], 0
0x180022cea  bsr     rcx, rax
0x180022cee  mov     r8, rbx
0x180022cf1  inc     ecx
0x180022cf3  shl     rdi, cl
0x180022cf6  lea     rcx, [rsi+18h]
0x180022cfa  lea     rdx, [rdi+rdi]
0x180022cfe  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>)
0x180022d03  mov     [rsi+38h], rdi
0x180022d07  lea     rax, [rdi-1]
0x180022d0b  mov     [rsi+30h], rax
0x180022d0f  mov     r10, [rsi+8]
0x180022d13  mov     r10, [r10]
0x180022d16  mov     r11, r10
0x180022d19  cmp     r10, rbx
0x180022d1c  jz      loc_180022DED
0x180022d22  mov     r11, [r11]
0x180022d25  lea     rdx, [r10+10h]; unsigned __int8 *
0x180022d29  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180022d2e  mov     r9, [rsi+18h]
0x180022d32  mov     r8, rax
0x180022d35  and     r8, [rsi+30h]
0x180022d39  add     r8, r8
0x180022d3c  cmp     [r9+r8*8], rbx
0x180022d40  jnz     short loc_180022D50
0x180022d42  mov     [r9+r8*8], r10
0x180022d46  mov     [r9+r8*8+8], r10
0x180022d4b  jmp     loc_180022DE5
0x180022d50  mov     rax, [r9+r8*8+8]
0x180022d55  mov     rcx, [rdx]
0x180022d58  cmp     rcx, [rax+10h]
0x180022d5c  jnz     short loc_180022D89
0x180022d5e  mov     rdi, [rax]
0x180022d61  cmp     rdi, r10
0x180022d64  jz      short loc_180022D46
0x180022d66  mov     rdx, [r10+8]
0x180022d6a  mov     [rdx], r11
0x180022d6d  mov     rcx, [r11+8]
0x180022d71  mov     [rcx], rdi
0x180022d74  mov     rax, [rdi+8]
0x180022d78  mov     [rax], r10
0x180022d7b  mov     [rdi+8], rcx
0x180022d7f  mov     [r11+8], rdx
0x180022d83  mov     [r10+8], rax
0x180022d87  jmp     short loc_180022D46
0x180022d89  lea     rdi, [rax+8]
0x180022d8d  cmp     [r9+r8*8], rax
0x180022d91  jz      short loc_180022DC2
0x180022d93  mov     rax, [rdi]
0x180022d96  cmp     rcx, [rax+10h]
0x180022d9a  jnz     short loc_180022D89
0x180022d9c  mov     r8, [rax]
0x180022d9f  mov     rdx, [r10+8]
0x180022da3  mov     [rdx], r11
0x180022da6  mov     rcx, [r11+8]
0x180022daa  mov     [rcx], r8
0x180022dad  mov     rax, [r8+8]
0x180022db1  mov     [rax], r10
0x180022db4  mov     [r8+8], rcx
0x180022db8  mov     [r11+8], rdx
0x180022dbc  mov     [r10+8], rax
0x180022dc0  jmp     short loc_180022DE5
0x180022dc2  mov     rdx, [r10+8]
0x180022dc6  mov     [rdx], r11
0x180022dc9  mov     rcx, [r11+8]
0x180022dcd  mov     [rcx], rax
0x180022dd0  mov     rax, [rdi]
0x180022dd3  mov     [rax], r10
0x180022dd6  mov     [rdi], rcx
0x180022dd9  mov     [r11+8], rdx
0x180022ddd  mov     [r10+8], rax
0x180022de1  mov     [r9+r8*8], r10
0x180022de5  mov     r10, r11
0x180022de8  jmp     loc_180022D19
0x180022ded  lea     rcx, [rsp+48h+arg_8]
0x180022df2  mov     [rsp+48h+arg_8], 0
0x180022dfb  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAXV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180022e00  add     rsp, 28h
0x180022e04  pop     r14
0x180022e06  pop     rdi
0x180022e07  pop     rsi
0x180022e08  pop     rbx
0x180022e09  retn
```
