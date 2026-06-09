# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Emplace<_EVENT_DESCRIPTOR const &>(_EVENT_DESCRIPTOR const &)

- ea: `0x18001c664`
- end: `0x18001c735`
- name: `??$_Emplace@AEBU_EVENT_DESCRIPTOR@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U_EVENT_DESCRIPTOR@@PEAX@std@@_N@1@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001d108`

## callees

- `0x18000183c`
- `0x180011ce8`
- `0x1800186f4`
- `0x1800188c8`
- `0x18001c664`
- `0x18001ca2c`
- `0x18001cba8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      std::_Throw_tree_length_error();
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
0x18001c664  push    rbx
0x18001c666  push    rbp
0x18001c667  push    rsi
0x18001c668  push    rdi
0x18001c669  push    r14
0x18001c66b  sub     rsp, 50h
0x18001c66f  movaps  [rsp+78h+var_38], xmm6
0x18001c674  mov     rbp, r8
0x18001c677  mov     rsi, rdx
0x18001c67a  mov     r14, rcx
0x18001c67d  lea     rdx, [rsp+78h+var_58]
0x18001c682  call    ??$_Find_lower_bound@U_EVENT_DESCRIPTOR@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U_EVENT_DESCRIPTOR@@PEAX@std@@@1@AEBU_EVENT_DESCRIPTOR@@@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Find_lower_bound<_EVENT_DESCRIPTOR>(_EVENT_DESCRIPTOR const &)
0x18001c687  movups  xmm6, xmmword ptr [rax]
0x18001c68a  mov     rcx, [rax+10h]
0x18001c68e  mov     rdx, rcx
0x18001c691  call    ??$_Lower_bound_duplicate@U_EVENT_DESCRIPTOR@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U_EVENT_DESCRIPTOR@@PEAX@1@AEBU_EVENT_DESCRIPTOR@@@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Lower_bound_duplicate<_EVENT_DESCRIPTOR>(std::_Tree_node<_EVENT_DESCRIPTOR,void *> * const,_EVENT_DESCRIPTOR const &)
0x18001c696  test    al, al
0x18001c698  jz      short loc_18001C6A3
0x18001c69a  mov     [rsi], rcx
0x18001c69d  mov     byte ptr [rsi+8], 0
0x18001c6a1  jmp     short loc_18001C721
0x18001c6a3  mov     rax, 555555555555555h
0x18001c6ad  cmp     [r14+8], rax
0x18001c6b1  jnz     short loc_18001C6B9
0x18001c6b3  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x18001c6b9  mov     rbx, [r14]
0x18001c6bc  mov     qword ptr [rsp+78h+var_58], r14
0x18001c6c1  mov     qword ptr [rsp+78h+var_58+8], 0
0x18001c6ca  mov     ecx, 30h ; '0'; Size
0x18001c6cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c6d4  mov     rdi, rax
0x18001c6d7  movups  xmm0, xmmword ptr [rbp+0]
0x18001c6db  movdqu  xmmword ptr [rax+20h], xmm0
0x18001c6e0  mov     [rax], rbx
0x18001c6e3  mov     [rax+8], rbx
0x18001c6e7  mov     [rax+10h], rbx
0x18001c6eb  mov     word ptr [rax+18h], 0
0x18001c6f1  mov     qword ptr [rsp+78h+var_58+8], 0
0x18001c6fa  lea     rcx, [rsp+78h+var_58]
0x18001c6ff  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>(void)
0x18001c704  movdqu  [rsp+78h+var_58], xmm6
0x18001c70a  mov     r8, rdi
0x18001c70d  lea     rdx, [rsp+78h+var_58]
0x18001c712  mov     rcx, r14
0x18001c715  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18001c71a  mov     [rsi], rax
0x18001c71d  mov     byte ptr [rsi+8], 1
0x18001c721  mov     rax, rsi
0x18001c724  movaps  xmm6, [rsp+78h+var_38]
0x18001c729  add     rsp, 50h
0x18001c72d  pop     r14
0x18001c72f  pop     rdi
0x18001c730  pop     rsi
0x18001c731  pop     rbp
0x18001c732  pop     rbx
0x18001c733  retn
```
