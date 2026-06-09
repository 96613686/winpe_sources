# std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::emplace<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob> &>(MapsBackgroundTransferJob * &&,std::shared_ptr<MapsBackgroundTransferJob> &)

- ea: `0x180003eac`
- end: `0x18000401d`
- name: `??$emplace@PEAVMapsBackgroundTransferJob@@AEAV?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAPEAVMapsBackgroundTransferJob@@AEAV?$shared_ptr@VMapsBackgroundTransferJob@@@1@@Z`
- size: `369`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180004940`

## callees

- `0x180003a00`
- `0x180003d54`
- `0x180003e94`
- `0x180003eac`
- `0x1800044f4`
- `0x180004860`
- `0x180005bf0`
- `0x180005e8c`
- `0x18000602c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003f0b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003f0b`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::emplace<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob> &>(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3,
        __int64 a4)
{
  __int64 v7; // rbp
  __int64 v8; // rcx
  _QWORD *v9; // rsi
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  float v12; // xmm0_4
  __int64 v13; // rcx
  float v14; // xmm1_4
  __int64 v15; // rax
  __int64 v16; // rcx
  _QWORD v18[2]; // [rsp+20h] [rbp-48h] BYREF
  _OWORD v19[3]; // [rsp+30h] [rbp-38h] BYREF

  v7 = std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()(a3);
  std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Find_last<MapsBackgroundTransferJob *>(
    v8,
    v19,
    a3,
    v7);
  if ( *((_QWORD *)&v19[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v19[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( qword_18001D830 == 0x666666666666666LL )
      std::_Xlength_error("unordered_map/set too long");
    v9 = std::_Allocate<16,std::_Default_allocate_traits>(0x28u);
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>::construct<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob> &>(
      v10,
      v9 + 2,
      a3,
      a4,
      &qword_18001D828,
      v9);
    v11 = qword_18001D830 + 1;
    if ( qword_18001D830 + 1 < 0 )
      v12 = (float)(int)(v11 & 1 | (v11 >> 1)) + (float)(int)(v11 & 1 | (v11 >> 1));
    else
      v12 = (float)(int)v11;
    v13 = qword_18001D858;
    if ( qword_18001D858 < 0 )
    {
      v13 = qword_18001D858 & 1;
      v14 = (float)(int)(v13 | ((unsigned __int64)qword_18001D858 >> 1))
          + (float)(int)(v13 | ((unsigned __int64)qword_18001D858 >> 1));
    }
    else
    {
      v14 = (float)(int)qword_18001D858;
    }
    if ( (float)(v12 / v14) > *(float *)&dword_18001D820 )
    {
      v15 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(&dword_18001D820);
      std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(
        &dword_18001D820,
        v15);
      v19[0] = *(_OWORD *)std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Find_last<MapsBackgroundTransferJob *>(
                            v16,
                            v19,
                            v9 + 2,
                            v7);
    }
    v18[1] = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Insert_new_node_before(
                      v13,
                      v7,
                      *(_QWORD *)&v19[0],
                      v9);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>(v18);
  }
  return a2;
}

```

## disassembly

```asm
0x180003eac  push    rbx
0x180003eae  push    rbp
0x180003eaf  push    rsi
0x180003eb0  push    rdi
0x180003eb1  push    r14
0x180003eb3  sub     rsp, 40h
0x180003eb7  mov     r14, r9
0x180003eba  mov     rdi, r8
0x180003ebd  mov     rbx, rdx
0x180003ec0  mov     rcx, r8; unsigned __int8 *
0x180003ec3  call    ??R?$_Conditionally_enabled_hash@PEAVMapsBackgroundTransferJob@@$00@std@@SA_KAEBQEAVMapsBackgroundTransferJob@@@Z; std::_Conditionally_enabled_hash<MapsBackgroundTransferJob *,1>::operator()(MapsBackgroundTransferJob * const &)
0x180003ec8  mov     rbp, rax
0x180003ecb  mov     r9, rax
0x180003ece  mov     r8, rdi
0x180003ed1  lea     rdx, [rsp+68h+var_38]
0x180003ed6  call    ??$_Find_last@PEAVMapsBackgroundTransferJob@@@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@1@AEBQEAVMapsBackgroundTransferJob@@_K@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Find_last<MapsBackgroundTransferJob *>(MapsBackgroundTransferJob * const &,unsigned __int64)
0x180003edb  mov     rdx, qword ptr [rsp+68h+var_38+8]
0x180003ee0  test    rdx, rdx
0x180003ee3  jz      short loc_180003EF1
0x180003ee5  mov     [rbx], rdx
0x180003ee8  mov     byte ptr [rbx+8], 0
0x180003eec  jmp     loc_18000400F
0x180003ef1  mov     rax, 666666666666666h
0x180003efb  cmp     cs:qword_18001D830, rax
0x180003f02  jnz     short loc_180003F12
0x180003f04  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180003f0b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180003f12  lea     rax, qword_18001D828
0x180003f19  mov     [rsp+68h+var_48], rax
0x180003f1e  mov     [rsp+68h+var_40], 0
0x180003f27  mov     ecx, 28h ; '('
0x180003f2c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180003f31  mov     rsi, rax
0x180003f34  mov     [rsp+68h+var_40], rax
0x180003f39  lea     rdx, [rax+10h]
0x180003f3d  mov     r9, r14
0x180003f40  mov     r8, rdi
0x180003f43  call    ??$construct@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAVMapsBackgroundTransferJob@@AEAV?$shared_ptr@VMapsBackgroundTransferJob@@@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@1@$$QEAPEAVMapsBackgroundTransferJob@@AEAV?$shared_ptr@VMapsBackgroundTransferJob@@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>::construct<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob> &>(std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>> &,std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>> * const,MapsBackgroundTransferJob * &&,std::shared_ptr<MapsBackgroundTransferJob> &)
0x180003f48  nop
0x180003f49  mov     rdx, cs:qword_18001D830
0x180003f50  add     rdx, 1
0x180003f54  xorps   xmm0, xmm0
0x180003f57  js      short loc_180003F60
0x180003f59  cvtsi2ss xmm0, rdx
0x180003f5e  jmp     short loc_180003F78
0x180003f60  mov     rcx, rdx
0x180003f63  shr     rcx, 1
0x180003f66  mov     rax, rdx
0x180003f69  and     eax, 1
0x180003f6c  or      rcx, rax
0x180003f6f  cvtsi2ss xmm0, rcx
0x180003f74  addss   xmm0, xmm0
0x180003f78  mov     rcx, cs:qword_18001D858
0x180003f7f  xorps   xmm1, xmm1
0x180003f82  test    rcx, rcx
0x180003f85  js      short loc_180003F8E
0x180003f87  cvtsi2ss xmm1, rcx
0x180003f8c  jmp     short loc_180003FA3
0x180003f8e  mov     rax, rcx
0x180003f91  shr     rax, 1
0x180003f94  and     ecx, 1
0x180003f97  or      rax, rcx
0x180003f9a  cvtsi2ss xmm1, rax
0x180003f9f  addss   xmm1, xmm1
0x180003fa3  divss   xmm0, xmm1
0x180003fa7  comiss  xmm0, cs:dword_18001D820
0x180003fae  jbe     short loc_180003FE5
0x180003fb0  lea     rcx, dword_18001D820
0x180003fb7  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180003fbc  mov     rdx, rax
0x180003fbf  lea     rcx, dword_18001D820
0x180003fc6  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Forced_rehash(unsigned __int64)
0x180003fcb  lea     r8, [rsi+10h]
0x180003fcf  mov     r9, rbp
0x180003fd2  lea     rdx, [rsp+68h+var_38]
0x180003fd7  call    ??$_Find_last@PEAVMapsBackgroundTransferJob@@@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@1@AEBQEAVMapsBackgroundTransferJob@@_K@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Find_last<MapsBackgroundTransferJob *>(MapsBackgroundTransferJob * const &,unsigned __int64)
0x180003fdc  movups  xmm0, xmmword ptr [rax]
0x180003fdf  movdqu  [rsp+68h+var_38], xmm0
0x180003fe5  mov     [rsp+68h+var_40], 0
0x180003fee  mov     r9, rsi
0x180003ff1  mov     r8, qword ptr [rsp+68h+var_38]
0x180003ff6  mov     rdx, rbp
0x180003ff9  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@PEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@V?$_Uhash_compare@PEAVMapsBackgroundTransferJob@@U?$hash@PEAVMapsBackgroundTransferJob@@@std@@U?$equal_to@PEAVMapsBackgroundTransferJob@@@3@@3@V?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@3@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<MapsBackgroundTransferJob *,std::shared_ptr<MapsBackgroundTransferJob>,std::_Uhash_compare<MapsBackgroundTransferJob *,std::hash<MapsBackgroundTransferJob *>,std::equal_to<MapsBackgroundTransferJob *>>,std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> * const,std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *> * const)
0x180003ffe  mov     [rbx], rax
0x180004001  mov     byte ptr [rbx+8], 1
0x180004005  lea     rcx, [rsp+68h+var_48]
0x18000400a  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>,void *>>>(void)
0x18000400f  mov     rax, rbx
0x180004012  add     rsp, 40h
0x180004016  pop     r14
0x180004018  pop     rdi
0x180004019  pop     rsi
0x18000401a  pop     rbp
0x18000401b  pop     rbx
0x18000401c  retn
```
