# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(void)

- ea: `0x180021748`
- end: `0x180021774`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021320`

## callees

- `0x18000c120`
- `0x18001152c`
- `0x180021748`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)(v2 + 40) - 24LL));
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>(a1);
}

```

## disassembly

```asm
0x180021748  push    rbx
0x18002174a  sub     rsp, 20h
0x18002174e  mov     rbx, rcx
0x180021751  mov     rcx, [rcx+8]
0x180021755  test    rcx, rcx
0x180021758  jz      short loc_180021767
0x18002175a  mov     rcx, [rcx+28h]
0x18002175e  sub     rcx, 18h; this
0x180021762  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021767  mov     rcx, rbx
0x18002176a  add     rsp, 20h
0x18002176e  pop     rbx
0x18002176f  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>(void)
```
