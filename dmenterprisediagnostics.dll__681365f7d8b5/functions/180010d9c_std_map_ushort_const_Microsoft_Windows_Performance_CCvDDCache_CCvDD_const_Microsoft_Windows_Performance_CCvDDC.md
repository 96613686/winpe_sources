# std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<ushort const *,>(ushort const * &&)

- ea: `0x180010d9c`
- end: `0x180010e8b`
- name: `??$_Try_emplace@PEBG$$V@?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@_N@1@$$QEAPEBG@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800122cc`

## callees

- `0x18000183c`
- `0x18000fdb8`
- `0x180010714`
- `0x1800107cc`
- `0x180010d9c`
- `0x180011ce8`
- `0x1800186f4`
- `0x1800188c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<unsigned short const *,>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rdx
  __int128 v12; // [rsp+20h] [rbp-48h] BYREF
  __int128 v13; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+40h] [rbp-28h]
  __int64 v15; // [rsp+88h] [rbp+20h] BYREF

  std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Find_lower_bound<unsigned short const *>(
    a1,
    &v13);
  v6 = v14;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Lower_bound_duplicate<unsigned short const *>(
                          v7,
                          v14,
                          a3) )
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Throw_tree_length_error();
    v8 = *a1;
    *(_QWORD *)&v12 = a1;
    v9 = operator new(0x30u);
    v15 = a3;
    ____0__QEAPEBG__Z__V___pair_QEBGPEBUCCvDD_CCvDDCache_Performance_Windows_Microsoft___std__QEAA_Upiecewise_construct_t_1_V__tuple___QEAPEBG_1_V__tuple___V_1__Z(
      v9 + 4,
      v10,
      &v15);
    *v9 = v8;
    v9[1] = v8;
    v9[2] = v8;
    *((_WORD *)v9 + 12) = 0;
    *((_QWORD *)&v12 + 1) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>(&v12);
    v12 = v13;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                      a1,
                      &v12,
                      v9);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x180010d9c  mov     [rsp+arg_0], rbx
0x180010da1  mov     [rsp+arg_8], rbp
0x180010da6  push    rsi
0x180010da7  push    rdi
0x180010da8  push    r14
0x180010daa  sub     rsp, 50h
0x180010dae  mov     rbp, r8
0x180010db1  mov     rsi, rdx
0x180010db4  mov     r14, rcx
0x180010db7  lea     rdx, [rsp+68h+var_38]
0x180010dbc  call    ??$_Find_lower_bound@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Find_lower_bound<ushort const *>(ushort const * const &)
0x180010dc1  mov     r8, rbp
0x180010dc4  mov     rbx, [rsp+68h+var_28]
0x180010dc9  mov     rdx, rbx
0x180010dcc  call    ??$_Lower_bound_duplicate@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Lower_bound_duplicate<ushort const *>(std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> * const,ushort const * const &)
0x180010dd1  test    al, al
0x180010dd3  jz      short loc_180010DE1
0x180010dd5  mov     [rsi], rbx
0x180010dd8  mov     byte ptr [rsi+8], 0
0x180010ddc  jmp     loc_180010E74
0x180010de1  mov     rax, 555555555555555h
0x180010deb  cmp     [r14+8], rax
0x180010def  jnz     short loc_180010DF7
0x180010df1  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x180010df7  mov     rbx, [r14]
0x180010dfa  mov     qword ptr [rsp+68h+var_48], r14
0x180010dff  mov     qword ptr [rsp+68h+var_48+8], 0
0x180010e08  mov     ecx, 30h ; '0'; Size
0x180010e0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010e12  mov     rdi, rax
0x180010e15  mov     [rsp+68h+arg_18], rbp
0x180010e1d  lea     rcx, [rax+20h]
0x180010e21  lea     r8, [rsp+68h+arg_18]
0x180010e29  call    ??$?0$$QEAPEBG$$Z$$V@?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@QEAA@Upiecewise_construct_t@1@V?$tuple@$$QEAPEBG@1@V?$tuple@$$V@1@@Z
0x180010e2e  mov     [rdi], rbx
0x180010e31  mov     [rdi+8], rbx
0x180010e35  mov     [rdi+10h], rbx
0x180010e39  mov     word ptr [rdi+18h], 0
0x180010e3f  mov     qword ptr [rsp+68h+var_48+8], 0
0x180010e48  lea     rcx, [rsp+68h+var_48]
0x180010e4d  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>(void)
0x180010e52  movups  xmm0, [rsp+68h+var_38]
0x180010e57  movdqu  [rsp+68h+var_48], xmm0
0x180010e5d  mov     r8, rdi
0x180010e60  lea     rdx, [rsp+68h+var_48]
0x180010e65  mov     rcx, r14
0x180010e68  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x180010e6d  mov     [rsi], rax
0x180010e70  mov     byte ptr [rsi+8], 1
0x180010e74  mov     rax, rsi
0x180010e77  mov     rbx, [rsp+68h+arg_0]
0x180010e7c  mov     rbp, [rsp+68h+arg_8]
0x180010e81  add     rsp, 50h
0x180010e85  pop     r14
0x180010e87  pop     rdi
0x180010e88  pop     rsi
0x180010e89  retn
```
