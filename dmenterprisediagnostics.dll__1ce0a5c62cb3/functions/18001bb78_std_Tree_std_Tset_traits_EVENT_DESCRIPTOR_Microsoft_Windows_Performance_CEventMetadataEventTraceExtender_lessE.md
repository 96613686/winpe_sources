# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Emplace<_EVENT_DESCRIPTOR const &>(_EVENT_DESCRIPTOR const &)

- ea: `0x18001bb78`
- end: `0x18001bc53`
- name: `??$_Emplace@AEBU_EVENT_DESCRIPTOR@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U_EVENT_DESCRIPTOR@@PEAX@std@@_N@1@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64 *, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c62c`

## callees

- `0x18000181c`
- `0x18001152c`
- `0x180017cd0`
- `0x18001bb78`
- `0x18001bf4c`
- `0x18001c0c8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001bbd1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001bbd1`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Emplace<_EVENT_DESCRIPTOR const &>(
        __int64 *a1,
        __int64 a2,
        _OWORD *a3)
{
  __int64 lower; // rax
  __int128 v7; // xmm6
  __int64 v8; // rcx
  __int64 v9; // rbx
  _OWORD *v10; // rdi
  _OWORD v12[2]; // [rsp+20h] [rbp-58h] BYREF

  lower = std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Find_lower_bound<_EVENT_DESCRIPTOR>(
            a1,
            v12);
  v7 = *(_OWORD *)lower;
  if ( (unsigned __int8)std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Lower_bound_duplicate<_EVENT_DESCRIPTOR>(
                          *(_QWORD *)(lower + 16),
                          *(_QWORD *)(lower + 16)) )
  {
    *(_QWORD *)a2 = v8;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v9 = *a1;
    v12[0] = (unsigned __int64)a1;
    v10 = operator new(0x30u);
    v10[2] = *a3;
    *(_QWORD *)v10 = v9;
    *((_QWORD *)v10 + 1) = v9;
    *((_QWORD *)v10 + 2) = v9;
    *((_WORD *)v10 + 12) = 0;
    *((_QWORD *)&v12[0] + 1) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>(v12);
    v12[0] = v7;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                      a1,
                      v12,
                      v10);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x18001bb78  push    rbx
0x18001bb7a  push    rbp
0x18001bb7b  push    rsi
0x18001bb7c  push    rdi
0x18001bb7d  push    r14
0x18001bb7f  sub     rsp, 50h
0x18001bb83  movaps  [rsp+78h+var_38], xmm6
0x18001bb88  mov     rbp, r8
0x18001bb8b  mov     rsi, rdx
0x18001bb8e  mov     r14, rcx
0x18001bb91  lea     rdx, [rsp+78h+var_58]
0x18001bb96  call    ??$_Find_lower_bound@U_EVENT_DESCRIPTOR@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U_EVENT_DESCRIPTOR@@PEAX@std@@@1@AEBU_EVENT_DESCRIPTOR@@@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Find_lower_bound<_EVENT_DESCRIPTOR>(_EVENT_DESCRIPTOR const &)
0x18001bb9b  movups  xmm6, xmmword ptr [rax]
0x18001bb9e  mov     rcx, [rax+10h]
0x18001bba2  mov     rdx, rcx
0x18001bba5  call    ??$_Lower_bound_duplicate@U_EVENT_DESCRIPTOR@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U_EVENT_DESCRIPTOR@@PEAX@1@AEBU_EVENT_DESCRIPTOR@@@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Lower_bound_duplicate<_EVENT_DESCRIPTOR>(std::_Tree_node<_EVENT_DESCRIPTOR,void *> * const,_EVENT_DESCRIPTOR const &)
0x18001bbaa  test    al, al
0x18001bbac  jz      short loc_18001BBBA
0x18001bbae  mov     [rsi], rcx
0x18001bbb1  mov     byte ptr [rsi+8], 0
0x18001bbb5  jmp     loc_18001BC40
0x18001bbba  mov     rax, 555555555555555h
0x18001bbc4  cmp     [r14+8], rax
0x18001bbc8  jnz     short loc_18001BBD8
0x18001bbca  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001bbd1  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001bbd8  mov     rbx, [r14]
0x18001bbdb  mov     qword ptr [rsp+78h+var_58], r14
0x18001bbe0  mov     qword ptr [rsp+78h+var_58+8], 0
0x18001bbe9  mov     ecx, 30h ; '0'; Size
0x18001bbee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bbf3  mov     rdi, rax
0x18001bbf6  movups  xmm0, xmmword ptr [rbp+0]
0x18001bbfa  movdqu  xmmword ptr [rax+20h], xmm0
0x18001bbff  mov     [rax], rbx
0x18001bc02  mov     [rax+8], rbx
0x18001bc06  mov     [rax+10h], rbx
0x18001bc0a  mov     word ptr [rax+18h], 0
0x18001bc10  mov     qword ptr [rsp+78h+var_58+8], 0
0x18001bc19  lea     rcx, [rsp+78h+var_58]
0x18001bc1e  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>(void)
0x18001bc23  movdqu  [rsp+78h+var_58], xmm6
0x18001bc29  mov     r8, rdi
0x18001bc2c  lea     rdx, [rsp+78h+var_58]
0x18001bc31  mov     rcx, r14
0x18001bc34  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18001bc39  mov     [rsi], rax
0x18001bc3c  mov     byte ptr [rsi+8], 1
0x18001bc40  mov     rax, rsi
0x18001bc43  movaps  xmm6, [rsp+78h+var_38]
0x18001bc48  add     rsp, 50h
0x18001bc4c  pop     r14
0x18001bc4e  pop     rdi
0x18001bc4f  pop     rsi
0x18001bc50  pop     rbp
0x18001bc51  pop     rbx
0x18001bc52  retn
```
