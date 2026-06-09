# std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Try_emplace<ulong const &,>(ulong const &)

- ea: `0x1800104f0`
- end: `0x180010608`
- name: `??$_Try_emplace@AEBK$$V@?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBK@Z`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011bfc`
- `0x180011e80`
- `0x180014340`

## callees

- `0x18000181c`
- `0x18000f708`
- `0x1800104f0`
- `0x18001162c`
- `0x180017cd0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010582`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010582`

## pseudocode

```c
__int64 __fastcall std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::_Try_emplace<unsigned long const &,>(
        _QWORD *a1,
        __int64 a2,
        unsigned int *a3)
{
  __int64 *v6; // r15
  __int64 *v7; // rax
  __int64 *v8; // rdx
  unsigned int v9; // ecx
  _DWORD *v10; // rbx
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
      std::_Xlength_error("map/set too long");
    *(_QWORD *)&v12 = a1;
    v10 = operator new(0x38u);
    v14 = a3;
    ____0V__tuple_AEBK_std__V__tuple___V_1__0A___Z_S___pair___CBKV__map_PEBGPEBUCCvDD_CCvDDCache_Performance_Windows_Microsoft__UlessLPCWSTR_ci_2345_V__allocator_U__pair_QEBGPEBUCCvDD_CCvDDCache_Performance_Windows_Microsoft___std___std___std___std__AEAA_AEAV__tuple_AEBK_1_AEAV__tuple___V_1_U__integer_sequence__K_0A__1_U__integer_sequence__K_S_1__Z(
      v10 + 8,
      &v14);
    *(_QWORD *)v10 = v6;
    *((_QWORD *)v10 + 1) = v6;
    *((_QWORD *)v10 + 2) = v6;
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
0x1800104f0  push    rbp
0x1800104f2  push    rbx
0x1800104f3  push    rsi
0x1800104f4  push    rdi
0x1800104f5  push    r14
0x1800104f7  push    r15
0x1800104f9  mov     rbp, rsp
0x1800104fc  sub     rsp, 68h
0x180010500  mov     rsi, r8
0x180010503  mov     rdi, rdx
0x180010506  mov     r14, rcx
0x180010509  mov     r15, [rcx]
0x18001050c  mov     rax, [r15+8]
0x180010510  mov     qword ptr [rbp+var_28], rax
0x180010514  mov     qword ptr [rbp+var_28+8], 0
0x18001051c  mov     rdx, r15
0x18001051f  cmp     byte ptr [rax+19h], 0
0x180010523  jnz     short loc_180010551
0x180010525  mov     ecx, [r8]
0x180010528  mov     qword ptr [rbp+var_28], rax
0x18001052c  cmp     [rax+20h], ecx
0x18001052f  jnb     short loc_18001053E
0x180010531  mov     dword ptr [rbp+var_28+8], 0
0x180010538  add     rax, 10h
0x18001053c  jmp     short loc_180010548
0x18001053e  mov     dword ptr [rbp+var_28+8], 1
0x180010545  mov     rdx, rax
0x180010548  mov     rax, [rax]
0x18001054b  cmp     byte ptr [rax+19h], 0
0x18001054f  jz      short loc_180010528
0x180010551  cmp     byte ptr [rdx+19h], 0
0x180010555  jnz     short loc_18001056B
0x180010557  mov     eax, [rdx+20h]
0x18001055a  cmp     [r8], eax
0x18001055d  jb      short loc_18001056B
0x18001055f  mov     [rdi], rdx
0x180010562  mov     byte ptr [rdi+8], 0
0x180010566  jmp     loc_1800105F8
0x18001056b  mov     rax, 492492492492492h
0x180010575  cmp     [r14+8], rax
0x180010579  jnz     short loc_180010589
0x18001057b  lea     rcx, aMapSetTooLong; "map/set too long"
0x180010582  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180010589  mov     qword ptr [rbp+var_38], r14
0x18001058d  mov     qword ptr [rbp+var_38+8], 0
0x180010595  mov     ecx, 38h ; '8'; Size
0x18001059a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001059f  mov     rbx, rax
0x1800105a2  mov     qword ptr [rbp+var_38+8], rax
0x1800105a6  mov     [rbp+arg_0], rsi
0x1800105aa  lea     rcx, [rax+20h]
0x1800105ae  lea     rdx, [rbp+arg_0]
0x1800105b2  call    ??$?0V?$tuple@AEBK@std@@V?$tuple@$$V@1@$0A@$$Z$S@?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@AEAA@AEAV?$tuple@AEBK@1@AEAV?$tuple@$$V@1@U?$integer_sequence@_K$0A@@1@U?$integer_sequence@_K$S@1@@Z
0x1800105b7  mov     [rbx], r15
0x1800105ba  mov     [rbx+8], r15
0x1800105be  mov     [rbx+10h], r15
0x1800105c2  mov     word ptr [rbx+18h], 0
0x1800105c8  mov     qword ptr [rbp+var_38+8], 0
0x1800105d0  lea     rcx, [rbp+var_38]
0x1800105d4  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(void)
0x1800105d9  movups  xmm0, [rbp+var_28]
0x1800105dd  movdqu  [rbp+var_38], xmm0
0x1800105e2  mov     r8, rbx
0x1800105e5  lea     rdx, [rbp+var_38]
0x1800105e9  mov     rcx, r14
0x1800105ec  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x1800105f1  mov     [rdi], rax
0x1800105f4  mov     byte ptr [rdi+8], 1
0x1800105f8  mov     rax, rdi
0x1800105fb  add     rsp, 68h
0x1800105ff  pop     r15
0x180010601  pop     r14
0x180010603  pop     rdi
0x180010604  pop     rsi
0x180010605  pop     rbx
0x180010606  pop     rbp
0x180010607  retn
```
