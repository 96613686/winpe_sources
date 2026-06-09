# std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180005e8c`
- end: `0x180006011`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z`
- size: `389`
- prototype: `unsigned __int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003eac`
- `0x180005070`
- `0x1800051b0`
- `0x180005354`
- `0x1800056d0`
- `0x180005820`

## callees

- `0x180004730`
- `0x180004860`
- `0x180005a1c`
- `0x180005e8c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005ecd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180005ecd`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  _QWORD *v7; // r11
  _QWORD *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r10
  _QWORD *v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  __int64 **v19; // r10
  __int64 v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // rdx
  __int64 **v25; // rcx
  __int64 *v26; // rax
  __int64 v28; // [rsp+48h] [rbp+10h] BYREF

  LODWORD(v28) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = a1[1];
  LODWORD(v28) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>>>::_Assign_grow(
    (__int64)(a1 + 3),
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  v7 = *(_QWORD **)a1[1];
  v8 = v7;
  while ( v7 != (_QWORD *)v4 )
  {
    v8 = (_QWORD *)*v8;
    v9 = std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()((unsigned __int8 *)v7 + 16);
    v11 = a1[3];
    v12 = 2 * (a1[6] & v9);
    if ( *(_QWORD *)(v11 + 16 * (a1[6] & v9)) == v4 )
    {
      *(_QWORD *)(v11 + 16 * (a1[6] & v9)) = v10;
LABEL_7:
      *(_QWORD *)(v11 + 8 * v12 + 8) = v10;
      goto LABEL_15;
    }
    v13 = *(__int64 **)(v11 + 16 * (a1[6] & v9) + 8);
    v14 = *(_QWORD *)(v10 + 16);
    if ( v14 == v13[2] )
    {
      v15 = *v13;
      if ( *v13 != v10 )
      {
        v16 = *(_QWORD **)(v10 + 8);
        *v16 = v8;
        v17 = (_QWORD *)v8[1];
        *v17 = v15;
        v18 = *(_QWORD **)(v15 + 8);
        *v18 = v10;
        *(_QWORD *)(v15 + 8) = v17;
        v8[1] = v16;
        *(_QWORD *)(v10 + 8) = v18;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v19 = (__int64 **)(v13 + 1);
      if ( *(__int64 **)(v11 + 8 * v12) == v13 )
        break;
      v13 = *v19;
      if ( v14 == (*v19)[2] )
      {
        v20 = *v13;
        v21 = *(_QWORD **)(v10 + 8);
        *v21 = v8;
        v22 = (_QWORD *)v8[1];
        *v22 = v20;
        v23 = *(_QWORD **)(v20 + 8);
        *v23 = v10;
        *(_QWORD *)(v20 + 8) = v22;
        v8[1] = v21;
        *(_QWORD *)(v10 + 8) = v23;
        goto LABEL_15;
      }
    }
    v24 = *(_QWORD **)(v10 + 8);
    *v24 = v8;
    v25 = (__int64 **)v8[1];
    *v25 = v13;
    v26 = *v19;
    *v26 = v10;
    *v19 = (__int64 *)v25;
    v8[1] = v24;
    *(_QWORD *)(v10 + 8) = v26;
    *(_QWORD *)(v11 + 8 * v12) = v10;
LABEL_15:
    v7 = v8;
  }
  v28 = 0;
  return std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(&v28);
}

```

## disassembly

```asm
0x180005e8c  mov     [rsp+arg_0], rbx
0x180005e91  mov     [rsp+arg_10], rbp
0x180005e96  push    rsi
0x180005e97  push    rdi
0x180005e98  push    r14
0x180005e9a  sub     rsp, 20h
0x180005e9e  mov     rax, 0FFFFFFFFFFFFFFFh
0x180005ea8  mov     dword ptr [rsp+38h+arg_8], 0
0x180005eb0  mov     rbp, rcx
0x180005eb3  mov     ebx, 1
0x180005eb8  bsr     rcx, rax
0x180005ebc  mov     eax, ebx
0x180005ebe  shl     rax, cl
0x180005ec1  cmp     rdx, rax
0x180005ec4  jbe     short loc_180005ED4
0x180005ec6  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180005ecd  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180005ed4  mov     rdi, [rbp+8]
0x180005ed8  lea     rax, [rdx-1]
0x180005edc  or      rax, rbx
0x180005edf  mov     dword ptr [rsp+38h+arg_8], 0
0x180005ee7  bsr     rcx, rax
0x180005eeb  mov     r8, rdi
0x180005eee  inc     ecx
0x180005ef0  shl     rbx, cl
0x180005ef3  lea     rcx, [rbp+18h]
0x180005ef7  lea     rdx, [rbx+rbx]
0x180005efb  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>)
0x180005f00  mov     [rbp+38h], rbx
0x180005f04  lea     rax, [rbx-1]
0x180005f08  mov     [rbp+30h], rax
0x180005f0c  mov     r11, [rbp+8]
0x180005f10  mov     r11, [r11]
0x180005f13  mov     rbx, r11
0x180005f16  cmp     r11, rdi
0x180005f19  jz      loc_180005FEB
0x180005f1f  mov     rbx, [rbx]
0x180005f22  lea     rcx, [r11+10h]; unsigned __int8 *
0x180005f26  call    ??R?$_Conditionally_enabled_hash@PEAVMapsBackgroundTransferJob@@$00@std@@SA_KAEBQEAVMapsBackgroundTransferJob@@@Z; std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()(MapsBackgroundTransferJob * const &)
0x180005f2b  mov     r9, [rbp+18h]
0x180005f2f  mov     r8, rax
0x180005f32  and     r8, [rbp+30h]
0x180005f36  add     r8, r8
0x180005f39  cmp     [r9+r8*8], rdi
0x180005f3d  jnz     short loc_180005F4D
0x180005f3f  mov     [r9+r8*8], r11
0x180005f43  mov     [r9+r8*8+8], r11
0x180005f48  jmp     loc_180005FE3
0x180005f4d  mov     rax, [r9+r8*8+8]
0x180005f52  mov     rcx, [r11+10h]
0x180005f56  cmp     rcx, [rax+10h]
0x180005f5a  jnz     short loc_180005F87
0x180005f5c  mov     r10, [rax]
0x180005f5f  cmp     r10, r11
0x180005f62  jz      short loc_180005F43
0x180005f64  mov     rdx, [r11+8]
0x180005f68  mov     [rdx], rbx
0x180005f6b  mov     rcx, [rbx+8]
0x180005f6f  mov     [rcx], r10
0x180005f72  mov     rax, [r10+8]
0x180005f76  mov     [rax], r11
0x180005f79  mov     [r10+8], rcx
0x180005f7d  mov     [rbx+8], rdx
0x180005f81  mov     [r11+8], rax
0x180005f85  jmp     short loc_180005F43
0x180005f87  lea     r10, [rax+8]
0x180005f8b  cmp     [r9+r8*8], rax
0x180005f8f  jz      short loc_180005FC0
0x180005f91  mov     rax, [r10]
0x180005f94  cmp     rcx, [rax+10h]
0x180005f98  jnz     short loc_180005F87
0x180005f9a  mov     r8, [rax]
0x180005f9d  mov     rdx, [r11+8]
0x180005fa1  mov     [rdx], rbx
0x180005fa4  mov     rcx, [rbx+8]
0x180005fa8  mov     [rcx], r8
0x180005fab  mov     rax, [r8+8]
0x180005faf  mov     [rax], r11
0x180005fb2  mov     [r8+8], rcx
0x180005fb6  mov     [rbx+8], rdx
0x180005fba  mov     [r11+8], rax
0x180005fbe  jmp     short loc_180005FE3
0x180005fc0  mov     rdx, [r11+8]
0x180005fc4  mov     [rdx], rbx
0x180005fc7  mov     rcx, [rbx+8]
0x180005fcb  mov     [rcx], rax
0x180005fce  mov     rax, [r10]
0x180005fd1  mov     [rax], r11
0x180005fd4  mov     [r10], rcx
0x180005fd7  mov     [rbx+8], rdx
0x180005fdb  mov     [r11+8], rax
0x180005fdf  mov     [r9+r8*8], r11
0x180005fe3  mov     r11, rbx
0x180005fe6  jmp     loc_180005F16
0x180005feb  lea     rcx, [rsp+38h+arg_8]
0x180005ff0  mov     [rsp+38h+arg_8], 0
0x180005ff9  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180005ffe  mov     rbx, [rsp+38h+arg_0]
0x180006003  mov     rbp, [rsp+38h+arg_10]
0x180006008  add     rsp, 20h
0x18000600c  pop     r14
0x18000600e  pop     rdi
0x18000600f  pop     rsi
0x180006010  retn
```
