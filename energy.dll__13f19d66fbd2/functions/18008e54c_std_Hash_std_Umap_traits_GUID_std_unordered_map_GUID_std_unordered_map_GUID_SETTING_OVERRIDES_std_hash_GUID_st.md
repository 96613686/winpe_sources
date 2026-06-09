# std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES,std::hash<_GUID>,std::equal_to<_GUID>,std::allocator<std::pair<_GUID const,_SETTING_OVERRIDES>>>,std::hash<_GUID>,std::equal_to<_GUID>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,_SETTING_OVERRIDES,std::hash<_GUID>,std::equal_to<_GUID>,std::allocator<std::pair<_GUID const,_SETTING_OVERRIDES>>>>>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES,std::hash<_GUID>,std::equal_to<_GUID>,std::allocator<std::pair<_GUID const,_SETTING_OVERRIDES>>>,std::hash<_GUID>,std::equal_to<_GUID>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,_SETTING_OVERRIDES,std::hash<_GUID>,std::equal_to<_GUID>,std::allocator<std::pair<_GUID const,_SETTING_OVERRIDES>>>>>>>>,0>>::_Try_emplace<_GUID const &,>(_GUID const &)

- ea: `0x18008e54c`
- end: `0x18008e6b5`
- name: `??$_Try_emplace@AEBU_GUID@@$$V@?$_Hash@V?$_Umap_traits@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(float *, __int64, UUID *)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18008ed10`
- `0x18008f070`
- `0x18008f5bc`

## callees

- `0x1800348e4`
- `0x18003dfdc`
- `0x18008e07c`
- `0x18008e1d4`
- `0x18008e204`
- `0x18008e54c`
- `0x18008e950`
- `0x18008f914`
- `0x18008fcf8`
- `0x180090038`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18008e5b2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18008e5b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>>,0>>::_Try_emplace<_GUID const &,>(
        float *a1,
        __int64 a2,
        UUID *a3)
{
  __int64 v6; // r15
  SIZE_T size_of; // rax
  _QWORD *v8; // r14
  __int64 v9; // rdx
  float v10; // xmm0_4
  __int64 v11; // rcx
  float v12; // xmm1_4
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v16; // [rsp+30h] [rbp-28h] BYREF
  _QWORD *v17; // [rsp+38h] [rbp-20h]
  __int128 v18; // [rsp+40h] [rbp-18h] BYREF
  UUID *v19; // [rsp+90h] [rbp+38h] BYREF

  v6 = std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>((__int64)a1, a3);
  std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>>,0>>::_Find_last<_GUID>(
    a1,
    &v18,
    a3,
    v6);
  if ( *((_QWORD *)&v18 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v18 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *((_QWORD *)a1 + 2) == 0x2AAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v16 = a1 + 2;
    size_of = std::_Get_size_of_n<96>(1);
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v17 = v8;
    v19 = a3;
    ____0V__tuple_AEBU_GUID___std__V__tuple___V_1__0A___Z_S___pair___CBU_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std___std__AEAA_AEAV__tuple_AEBU_GUID___1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
      v8 + 2,
      &v19);
    v9 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v9 < 0 )
      v10 = (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1))
          + (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1));
    else
      v10 = (float)(int)v9;
    v11 = *((_QWORD *)a1 + 7);
    if ( v11 < 0 )
    {
      v13 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v11 >> 1);
      v12 = (float)(int)v13 + (float)(int)v13;
    }
    else
    {
      v12 = (float)(int)v11;
    }
    if ( (float)(v10 / v12) > *a1 )
    {
      v14 = __Desired_grow_bucket_count____Hash_V___Umap_traits_U_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std___std___3__std__V___Uhash_compare_U_GUID__U__hash_U_GUID___std__U__equal_to_U_GUID___3__3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std__U__hash_U_GUID___3_U__equal_to_U_GUID___3_V__allocator_U__pair___CBU_GUID__V__unordered_map_U_GUID__U_SETTING_OVERRIDES__U__hash_U_GUID___std__U__equal_to_U_GUID___4_V__allocator_U__pair___CBU_GUID__U_SETTING_OVERRIDES___std___4__std___std___3__std___std___3__std___std___3__0A__std___std__IEBA_K_K_Z(a1);
      std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>>,0>>::_Forced_rehash(
        a1,
        v14);
      v18 = *(_OWORD *)std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>>,0>>::_Find_last<_GUID>(
                         a1,
                         &v18,
                         v8 + 2,
                         v6);
    }
    v17 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<_GUID,_SETTING_OVERRIDES,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,_SETTING_OVERRIDES>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      v18,
                      v8);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>,void *>>>(&v16);
  }
  return a2;
}

```

## disassembly

```asm
0x18008e54c  push    rbp
0x18008e54e  push    rbx
0x18008e54f  push    rsi
0x18008e550  push    rdi
0x18008e551  push    r14
0x18008e553  push    r15
0x18008e555  mov     rbp, rsp
0x18008e558  sub     rsp, 58h
0x18008e55c  mov     rsi, r8
0x18008e55f  mov     rbx, rdx
0x18008e562  mov     rdi, rcx
0x18008e565  mov     rdx, r8
0x18008e568  call    ??$?RU_GUID@@@?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@QEBA_KAEBU_GUID@@@Z; std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(_GUID const &)
0x18008e56d  mov     r15, rax
0x18008e570  mov     r9, rax
0x18008e573  mov     r8, rsi
0x18008e576  lea     rdx, [rbp+var_18]
0x18008e57a  mov     rcx, rdi
0x18008e57d  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x18008e582  mov     rdx, qword ptr [rbp+var_18+8]
0x18008e586  test    rdx, rdx
0x18008e589  jz      short loc_18008E597
0x18008e58b  mov     [rbx], rdx
0x18008e58e  mov     byte ptr [rbx+8], 0
0x18008e592  jmp     loc_18008E6A5
0x18008e597  lea     rax, [rdi+8]
0x18008e59b  mov     rcx, 2AAAAAAAAAAAAAAh
0x18008e5a5  cmp     [rax+8], rcx
0x18008e5a9  jnz     short loc_18008E5B9
0x18008e5ab  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18008e5b2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18008e5b9  mov     [rbp+var_28], rax
0x18008e5bd  mov     [rbp+var_20], 0
0x18008e5c5  mov     ecx, 1
0x18008e5ca  call    ??$_Get_size_of_n@$0GA@@std@@YA_K_K@Z; std::_Get_size_of_n<96>(unsigned __int64)
0x18008e5cf  mov     rcx, rax
0x18008e5d2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18008e5d7  mov     r14, rax
0x18008e5da  mov     [rbp+var_20], rax
0x18008e5de  mov     [rbp+arg_0], rsi
0x18008e5e2  lea     rcx, [rax+10h]
0x18008e5e6  lea     rdx, [rbp+arg_0]
0x18008e5ea  call    ??$?0V?$tuple@AEBU_GUID@@@std@@V?$tuple@$$V@1@$0A@$$Z$S@?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@AEAA@AEAV?$tuple@AEBU_GUID@@@1@AEAV?$tuple@$$V@1@U?$integer_sequence@_K$0A@@1@U?$integer_sequence@_K$S@1@@Z
0x18008e5ef  nop
0x18008e5f0  mov     rdx, [rdi+10h]
0x18008e5f4  add     rdx, 1
0x18008e5f8  xorps   xmm0, xmm0
0x18008e5fb  js      short loc_18008E604
0x18008e5fd  cvtsi2ss xmm0, rdx
0x18008e602  jmp     short loc_18008E61C
0x18008e604  mov     rcx, rdx
0x18008e607  shr     rcx, 1
0x18008e60a  mov     rax, rdx
0x18008e60d  and     eax, 1
0x18008e610  or      rcx, rax
0x18008e613  cvtsi2ss xmm0, rcx
0x18008e618  addss   xmm0, xmm0
0x18008e61c  mov     rcx, [rdi+38h]
0x18008e620  xorps   xmm1, xmm1
0x18008e623  test    rcx, rcx
0x18008e626  js      short loc_18008E62F
0x18008e628  cvtsi2ss xmm1, rcx
0x18008e62d  jmp     short loc_18008E644
0x18008e62f  mov     rax, rcx
0x18008e632  shr     rax, 1
0x18008e635  and     ecx, 1
0x18008e638  or      rax, rcx
0x18008e63b  cvtsi2ss xmm1, rax
0x18008e640  addss   xmm1, xmm1
0x18008e644  divss   xmm0, xmm1
0x18008e648  comiss  xmm0, dword ptr [rdi]
0x18008e64b  jbe     short loc_18008E67B
0x18008e64d  mov     rcx, rdi
0x18008e650  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@@std@@@std@@@3@$0A@@std@@@std@@IEBA_K_K@Z
0x18008e655  mov     rdx, rax
0x18008e658  mov     rcx, rdi
0x18008e65b  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>>,0>>::_Forced_rehash(unsigned __int64)
0x18008e660  lea     r8, [r14+10h]
0x18008e664  mov     r9, r15
0x18008e667  lea     rdx, [rbp+var_18]
0x18008e66b  mov     rcx, rdi
0x18008e66e  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x18008e673  movups  xmm0, xmmword ptr [rax]
0x18008e676  movdqu  [rbp+var_18], xmm0
0x18008e67b  mov     [rbp+var_20], 0
0x18008e683  mov     r9, r14
0x18008e686  mov     r8, qword ptr [rbp+var_18]
0x18008e68a  mov     rdx, r15
0x18008e68d  mov     rcx, rdi
0x18008e690  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@U_GUID@@U_SETTING_OVERRIDES@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<_GUID,_SETTING_OVERRIDES,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,_SETTING_OVERRIDES>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<_GUID const,_SETTING_OVERRIDES>,void *> * const,std::_List_node<std::pair<_GUID const,_SETTING_OVERRIDES>,void *> * const)
0x18008e695  mov     [rbx], rax
0x18008e698  mov     byte ptr [rbx+8], 1
0x18008e69c  lea     rcx, [rbp+var_28]
0x18008e6a0  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@U?$hash@U_GUID@@@3@U?$equal_to@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$unordered_map@U_GUID@@U_SETTING_OVERRIDES@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@4@V?$allocator@U?$pair@$$CBU_GUID@@U_SETTING_OVERRIDES@@@std@@@4@@std@@@std@@@3@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<_GUID const,std::unordered_map<_GUID,std::unordered_map<_GUID,_SETTING_OVERRIDES>>>,void *>>>(void)
0x18008e6a5  mov     rax, rbx
0x18008e6a8  add     rsp, 58h
0x18008e6ac  pop     r15
0x18008e6ae  pop     r14
0x18008e6b0  pop     rdi
0x18008e6b1  pop     rsi
0x18008e6b2  pop     rbx
0x18008e6b3  pop     rbp
0x18008e6b4  retn
```
