# std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<ushort const *,>(ushort const * &&)

- ea: `0x180010610`
- end: `0x180010706`
- name: `??$_Try_emplace@PEBG$$V@?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@_N@1@$$QEAPEBG@Z`
- size: `246`
- prototype: `__int64 __fastcall(__int64 *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011bfc`
- `0x180011e80`

## callees

- `0x18000181c`
- `0x18000f6d0`
- `0x18000ff88`
- `0x180010038`
- `0x180010610`
- `0x18001152c`
- `0x180017cd0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001066c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001066c`

## pseudocode

```c
__int64 __fastcall std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Try_emplace<unsigned short const *,>(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rdx
  __int128 v12; // [rsp+20h] [rbp-48h] BYREF
  __int128 v13; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+40h] [rbp-28h]
  _QWORD *v15; // [rsp+88h] [rbp+20h] BYREF

  std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Find_lower_bound<unsigned short const *>(
    (__int64)a1,
    &v13,
    a3);
  v6 = v14;
  if ( std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Lower_bound_duplicate<unsigned short const *>(
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
      std::_Xlength_error("map/set too long");
    v8 = *a1;
    *(_QWORD *)&v12 = a1;
    v9 = operator new(0x30u);
    v15 = a3;
    ____0__QEAPEBG__Z__V___pair_QEBGPEBUCCvDD_CCvDDCache_Performance_Windows_Microsoft___std__QEAA_Upiecewise_construct_t_1_V__tuple___QEAPEBG_1_V__tuple___V_1__Z(
      (__int64)(v9 + 4),
      v10,
      (__int64)&v15);
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
0x180010610  mov     [rsp+arg_0], rbx
0x180010615  mov     [rsp+arg_8], rbp
0x18001061a  push    rsi
0x18001061b  push    rdi
0x18001061c  push    r14
0x18001061e  sub     rsp, 50h
0x180010622  mov     rbp, r8
0x180010625  mov     rsi, rdx
0x180010628  mov     r14, rcx
0x18001062b  lea     rdx, [rsp+68h+var_38]
0x180010630  call    ??$_Find_lower_bound@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Find_lower_bound<ushort const *>(ushort const * const &)
0x180010635  mov     r8, rbp
0x180010638  mov     rbx, [rsp+68h+var_28]
0x18001063d  mov     rdx, rbx
0x180010640  call    ??$_Lower_bound_duplicate@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Lower_bound_duplicate<ushort const *>(std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> * const,ushort const * const &)
0x180010645  test    al, al
0x180010647  jz      short loc_180010655
0x180010649  mov     [rsi], rbx
0x18001064c  mov     byte ptr [rsi+8], 0
0x180010650  jmp     loc_1800106F0
0x180010655  mov     rax, 555555555555555h
0x18001065f  cmp     [r14+8], rax
0x180010663  jnz     short loc_180010673
0x180010665  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001066c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180010673  mov     rbx, [r14]
0x180010676  mov     qword ptr [rsp+68h+var_48], r14
0x18001067b  mov     qword ptr [rsp+68h+var_48+8], 0
0x180010684  mov     ecx, 30h ; '0'; Size
0x180010689  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001068e  mov     rdi, rax
0x180010691  mov     [rsp+68h+arg_18], rbp
0x180010699  lea     rcx, [rax+20h]
0x18001069d  lea     r8, [rsp+68h+arg_18]
0x1800106a5  call    ??$?0$$QEAPEBG$$Z$$V@?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@QEAA@Upiecewise_construct_t@1@V?$tuple@$$QEAPEBG@1@V?$tuple@$$V@1@@Z
0x1800106aa  mov     [rdi], rbx
0x1800106ad  mov     [rdi+8], rbx
0x1800106b1  mov     [rdi+10h], rbx
0x1800106b5  mov     word ptr [rdi+18h], 0
0x1800106bb  mov     qword ptr [rsp+68h+var_48+8], 0
0x1800106c4  lea     rcx, [rsp+68h+var_48]
0x1800106c9  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>(void)
0x1800106ce  movups  xmm0, [rsp+68h+var_38]
0x1800106d3  movdqu  [rsp+68h+var_48], xmm0
0x1800106d9  mov     r8, rdi
0x1800106dc  lea     rdx, [rsp+68h+var_48]
0x1800106e1  mov     rcx, r14
0x1800106e4  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x1800106e9  mov     [rsi], rax
0x1800106ec  mov     byte ptr [rsi+8], 1
0x1800106f0  mov     rax, rsi
0x1800106f3  mov     rbx, [rsp+68h+arg_0]
0x1800106f8  mov     rbp, [rsp+68h+arg_8]
0x1800106fd  add     rsp, 50h
0x180010701  pop     r14
0x180010703  pop     rdi
0x180010704  pop     rsi
0x180010705  retn
```
