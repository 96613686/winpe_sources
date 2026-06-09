# std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Try_emplace<ulong const &,>(ulong const &)

- ea: `0x180010c84`
- end: `0x180010d95`
- name: `??$_Try_emplace@AEBK$$V@?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z`
- size: `273`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800123fc`
- `0x18001266c`
- `0x180014bb0`

## callees

- `0x18000183c`
- `0x18000fdf0`
- `0x180010c84`
- `0x180011dec`
- `0x1800186f4`
- `0x1800188c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<unsigned long const &,>(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3)
{
  __int64 *v6; // r15
  __int64 *v7; // rax
  __int64 *v8; // rdx
  unsigned int v9; // ecx
  _QWORD *v10; // rbx
  __int128 v12; // [rsp+30h] [rbp-38h] BYREF
  __int128 v13; // [rsp+40h] [rbp-28h]
  unsigned int *v14; // [rsp+A0h] [rbp+38h] BYREF

  v6 = (__int64 *)*a1;
  v7 = *(__int64 **)(*a1 + 8LL);
  v13 = (unsigned __int64)v7;
  v8 = v6;
  if ( !*((_BYTE *)v7 + 25) )
  {
    v9 = *a3;
    do
    {
      *(_QWORD *)&v13 = v7;
      if ( *((_DWORD *)v7 + 8) >= v9 )
      {
        DWORD2(v13) = 1;
        v8 = v7;
      }
      else
      {
        DWORD2(v13) = 0;
        v7 += 2;
      }
      v7 = (__int64 *)*v7;
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( *((_BYTE *)v8 + 25) || *a3 < *((_DWORD *)v8 + 8) )
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Throw_tree_length_error();
    *(_QWORD *)&v12 = a1;
    v10 = operator new(0x38u);
    v14 = a3;
    ____0V__tuple_AEBK_std__V__tuple___V_1__0A___Z_S___pair___CBKV__map_PEBGPEBUCCvDD_CCvDDCache_Performance_Windows_Microsoft__UlessLPCWSTR_ci_2345_V__allocator_U__pair_QEBGPEBUCCvDD_CCvDDCache_Performance_Windows_Microsoft___std___std___std___std__AEAA_AEAV__tuple_AEBK_1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
      v10 + 4,
      &v14);
    *v10 = v6;
    v10[1] = v6;
    v10[2] = v6;
    *((_WORD *)v10 + 12) = 0;
    *((_QWORD *)&v12 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(&v12);
    v12 = v13;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                      a1,
                      &v12,
                      v10);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v8;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180010c84  push    rbp
0x180010c86  push    rbx
0x180010c87  push    rsi
0x180010c88  push    rdi
0x180010c89  push    r14
0x180010c8b  push    r15
0x180010c8d  mov     rbp, rsp
0x180010c90  sub     rsp, 68h
0x180010c94  mov     rsi, r8
0x180010c97  mov     rdi, rdx
0x180010c9a  mov     r14, rcx
0x180010c9d  mov     r15, [rcx]
0x180010ca0  mov     rax, [r15+8]
0x180010ca4  mov     qword ptr [rbp+var_28], rax
0x180010ca8  mov     qword ptr [rbp+var_28+8], 0
0x180010cb0  mov     rdx, r15
0x180010cb3  cmp     byte ptr [rax+19h], 0
0x180010cb7  jnz     short loc_180010CE5
0x180010cb9  mov     ecx, [r8]
0x180010cbc  mov     qword ptr [rbp+var_28], rax
0x180010cc0  cmp     [rax+20h], ecx
0x180010cc3  jnb     short loc_180010CD2
0x180010cc5  mov     dword ptr [rbp+var_28+8], 0
0x180010ccc  add     rax, 10h
0x180010cd0  jmp     short loc_180010CDC
0x180010cd2  mov     dword ptr [rbp+var_28+8], 1
0x180010cd9  mov     rdx, rax
0x180010cdc  mov     rax, [rax]
0x180010cdf  cmp     byte ptr [rax+19h], 0
0x180010ce3  jz      short loc_180010CBC
0x180010ce5  cmp     byte ptr [rdx+19h], 0
0x180010ce9  jnz     short loc_180010CFF
0x180010ceb  mov     eax, [rdx+20h]
0x180010cee  cmp     [r8], eax
0x180010cf1  jb      short loc_180010CFF
0x180010cf3  mov     [rdi], rdx
0x180010cf6  mov     byte ptr [rdi+8], 0
0x180010cfa  jmp     loc_180010D84
0x180010cff  mov     rax, 492492492492492h
0x180010d09  cmp     [r14+8], rax
0x180010d0d  jnz     short loc_180010D15
0x180010d0f  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x180010d15  mov     qword ptr [rbp+var_38], r14
0x180010d19  mov     qword ptr [rbp+var_38+8], 0
0x180010d21  mov     ecx, 38h ; '8'; Size
0x180010d26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010d2b  mov     rbx, rax
0x180010d2e  mov     qword ptr [rbp+var_38+8], rax
0x180010d32  mov     [rbp+arg_0], rsi
0x180010d36  lea     rcx, [rax+20h]
0x180010d3a  lea     rdx, [rbp+arg_0]
0x180010d3e  call    ??$?0V?$tuple@AEBK@std@@V?$tuple@$$V@1@$0A@$$Z$S@?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@AEAA@AEAV?$tuple@AEBK@1@AEAV?$tuple@$$V@1@U?$integer_sequence@_K$0A@@1@U?$integer_sequence@_K$S@1@@Z
0x180010d43  mov     [rbx], r15
0x180010d46  mov     [rbx+8], r15
0x180010d4a  mov     [rbx+10h], r15
0x180010d4e  mov     word ptr [rbx+18h], 0
0x180010d54  mov     qword ptr [rbp+var_38+8], 0
0x180010d5c  lea     rcx, [rbp+var_38]
0x180010d60  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(void)
0x180010d65  movups  xmm0, [rbp+var_28]
0x180010d69  movdqu  [rbp+var_38], xmm0
0x180010d6e  mov     r8, rbx
0x180010d71  lea     rdx, [rbp+var_38]
0x180010d75  mov     rcx, r14
0x180010d78  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x180010d7d  mov     [rdi], rax
0x180010d80  mov     byte ptr [rdi+8], 1
0x180010d84  mov     rax, rdi
0x180010d87  add     rsp, 68h
0x180010d8b  pop     r15
0x180010d8d  pop     r14
0x180010d8f  pop     rdi
0x180010d90  pop     rsi
0x180010d91  pop     rbx
0x180010d92  pop     rbp
0x180010d93  retn
```
