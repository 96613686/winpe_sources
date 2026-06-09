# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(void)

- ea: `0x180022488`
- end: `0x1800224b4`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002201c`

## callees

- `0x18000c6e4`
- `0x180011ce8`
- `0x180022488`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)(v2 + 40) - 24LL));
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>(a1);
}

```

## disassembly

```asm
0x180022488  push    rbx
0x18002248a  sub     rsp, 20h
0x18002248e  mov     rbx, rcx
0x180022491  mov     rcx, [rcx+8]
0x180022495  test    rcx, rcx
0x180022498  jz      short loc_1800224A7
0x18002249a  mov     rcx, [rcx+28h]
0x18002249e  sub     rcx, 18h; this
0x1800224a2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800224a7  mov     rcx, rbx
0x1800224aa  add     rsp, 20h
0x1800224ae  pop     rbx
0x1800224af  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>(void)
```
