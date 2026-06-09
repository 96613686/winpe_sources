# std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18000d3a8`
- end: `0x18000d531`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEAAX_K@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009e04`

## callees

- `0x180008be0`
- `0x18000a9b0`
- `0x18000d118`
- `0x18000d3a8`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  __int64 v6; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // r11
  __int64 v10; // r10
  _QWORD *v11; // rdx
  __int64 v12; // r8
  _QWORD *v13; // rdi
  _QWORD *v14; // r9
  _QWORD *v15; // r8
  _QWORD *v16; // rdx
  _QWORD *v17; // rdi
  __int64 v18; // r8
  _QWORD *v19; // r10
  _QWORD *v20; // r9
  _QWORD *v21; // r8
  _QWORD *v22; // rdx
  _QWORD *v23; // r9
  _QWORD *v24; // r8
  _QWORD *v25; // rdx
  __int64 v27; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(v27) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = a1[1];
  LODWORD(v27) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  v7 = *(_QWORD **)a1[1];
  v8 = v7;
  while ( v7 != (_QWORD *)v4 )
  {
    v9 = a1[3];
    v10 = 2LL * (a1[6] & v7[3]);
    v8 = (_QWORD *)*v8;
    if ( *(_QWORD *)(v9 + 16LL * (a1[6] & v7[3])) == v4 )
    {
      *(_QWORD *)(v9 + 16LL * (a1[6] & v7[3])) = v7;
LABEL_7:
      *(_QWORD *)(v9 + 8 * v10 + 8) = v7;
      goto LABEL_19;
    }
    v11 = *(_QWORD **)(v9 + 16LL * (a1[6] & v7[3]) + 8);
    v12 = v7[2] - v11[2];
    if ( !v12 )
      v12 = v7[3] - v11[3];
    if ( !v12 )
    {
      v13 = (_QWORD *)*v11;
      if ( (_QWORD *)*v11 != v7 )
      {
        v14 = (_QWORD *)v7[1];
        *v14 = v8;
        v15 = (_QWORD *)v8[1];
        *v15 = v13;
        v16 = (_QWORD *)v13[1];
        *v16 = v7;
        v13[1] = v15;
        v8[1] = v14;
        v7[1] = v16;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v17 = v11 + 1;
      if ( *(_QWORD **)(v9 + 16LL * (a1[6] & v7[3])) == v11 )
        break;
      v11 = (_QWORD *)*v17;
      v18 = v7[2] - *(_QWORD *)(*v17 + 16LL);
      if ( !v18 )
        v18 = v7[3] - v11[3];
      if ( !v18 )
      {
        v19 = (_QWORD *)*v11;
        v20 = (_QWORD *)v7[1];
        *v20 = v8;
        v21 = (_QWORD *)v8[1];
        *v21 = v19;
        v22 = (_QWORD *)v19[1];
        *v22 = v7;
        v19[1] = v21;
        v8[1] = v20;
        v7[1] = v22;
        goto LABEL_19;
      }
    }
    v23 = (_QWORD *)v7[1];
    *v23 = v8;
    v24 = (_QWORD *)v8[1];
    *v24 = v11;
    v25 = (_QWORD *)*v17;
    *v25 = v7;
    *v17 = v24;
    v8[1] = v23;
    v7[1] = v25;
    *(_QWORD *)(v9 + 8 * v10) = v7;
LABEL_19:
    v7 = v8;
  }
  v27 = 0;
  return std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Clear_guard::~_Clear_guard(&v27);
}

```

## disassembly

```asm
0x18000d3a8  push    rbx
0x18000d3aa  push    rsi
0x18000d3ab  push    rdi
0x18000d3ac  push    r14
0x18000d3ae  sub     rsp, 28h
0x18000d3b2  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000d3bc  mov     dword ptr [rsp+48h+arg_8], 0
0x18000d3c4  mov     rsi, rcx
0x18000d3c7  mov     edi, 1
0x18000d3cc  bsr     rcx, rax
0x18000d3d0  mov     eax, edi
0x18000d3d2  shl     rax, cl
0x18000d3d5  cmp     rdx, rax
0x18000d3d8  jbe     short loc_18000D3E7
0x18000d3da  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18000d3e1  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000d3e7  mov     rbx, [rsi+8]
0x18000d3eb  lea     rax, [rdx-1]
0x18000d3ef  or      rax, rdi
0x18000d3f2  mov     dword ptr [rsp+48h+arg_8], 0
0x18000d3fa  bsr     rcx, rax
0x18000d3fe  mov     r8, rbx
0x18000d401  inc     ecx
0x18000d403  shl     rdi, cl
0x18000d406  lea     rcx, [rsi+18h]
0x18000d40a  lea     rdx, [rdi+rdi]
0x18000d40e  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>)
0x18000d413  lea     rax, [rdi-1]
0x18000d417  mov     [rsi+38h], rdi
0x18000d41b  mov     [rsi+30h], rax
0x18000d41f  mov     rax, [rsi+8]
0x18000d423  mov     rax, [rax]
0x18000d426  mov     rcx, rax
0x18000d429  cmp     rax, rbx
0x18000d42c  jz      loc_18000D514
0x18000d432  mov     r10, [rax+18h]
0x18000d436  and     r10, [rsi+30h]
0x18000d43a  mov     r11, [rsi+18h]
0x18000d43e  add     r10, r10
0x18000d441  mov     rcx, [rcx]
0x18000d444  cmp     [r11+r10*8], rbx
0x18000d448  jnz     short loc_18000D458
0x18000d44a  mov     [r11+r10*8], rax
0x18000d44e  mov     [r11+r10*8+8], rax
0x18000d453  jmp     loc_18000D50C
0x18000d458  mov     rdx, [r11+r10*8+8]
0x18000d45d  mov     r8, [rax+10h]
0x18000d461  sub     r8, [rdx+10h]
0x18000d465  jnz     short loc_18000D46F
0x18000d467  mov     r8, [rax+18h]
0x18000d46b  sub     r8, [rdx+18h]
0x18000d46f  test    r8, r8
0x18000d472  jnz     short loc_18000D49F
0x18000d474  mov     rdi, [rdx]
0x18000d477  cmp     rdi, rax
0x18000d47a  jz      short loc_18000D44E
0x18000d47c  mov     r9, [rax+8]
0x18000d480  mov     [r9], rcx
0x18000d483  mov     r8, [rcx+8]
0x18000d487  mov     [r8], rdi
0x18000d48a  mov     rdx, [rdi+8]
0x18000d48e  mov     [rdx], rax
0x18000d491  mov     [rdi+8], r8
0x18000d495  mov     [rcx+8], r9
0x18000d499  mov     [rax+8], rdx
0x18000d49d  jmp     short loc_18000D44E
0x18000d49f  lea     rdi, [rdx+8]
0x18000d4a3  cmp     [r11+r10*8], rdx
0x18000d4a7  jz      short loc_18000D4E9
0x18000d4a9  mov     rdx, [rdi]
0x18000d4ac  mov     r8, [rax+10h]
0x18000d4b0  sub     r8, [rdx+10h]
0x18000d4b4  jnz     short loc_18000D4BE
0x18000d4b6  mov     r8, [rax+18h]
0x18000d4ba  sub     r8, [rdx+18h]
0x18000d4be  test    r8, r8
0x18000d4c1  jnz     short loc_18000D49F
0x18000d4c3  mov     r10, [rdx]
0x18000d4c6  mov     r9, [rax+8]
0x18000d4ca  mov     [r9], rcx
0x18000d4cd  mov     r8, [rcx+8]
0x18000d4d1  mov     [r8], r10
0x18000d4d4  mov     rdx, [r10+8]
0x18000d4d8  mov     [rdx], rax
0x18000d4db  mov     [r10+8], r8
0x18000d4df  mov     [rcx+8], r9
0x18000d4e3  mov     [rax+8], rdx
0x18000d4e7  jmp     short loc_18000D50C
0x18000d4e9  mov     r9, [rax+8]
0x18000d4ed  mov     [r9], rcx
0x18000d4f0  mov     r8, [rcx+8]
0x18000d4f4  mov     [r8], rdx
0x18000d4f7  mov     rdx, [rdi]
0x18000d4fa  mov     [rdx], rax
0x18000d4fd  mov     [rdi], r8
0x18000d500  mov     [rcx+8], r9
0x18000d504  mov     [rax+8], rdx
0x18000d508  mov     [r11+r10*8], rax
0x18000d50c  mov     rax, rcx
0x18000d50f  jmp     loc_18000D429
0x18000d514  lea     rcx, [rsp+48h+arg_8]
0x18000d519  mov     [rsp+48h+arg_8], 0
0x18000d522  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000d527  add     rsp, 28h
0x18000d52b  pop     r14
0x18000d52d  pop     rdi
0x18000d52e  pop     rsi
0x18000d52f  pop     rbx
0x18000d530  retn
```
