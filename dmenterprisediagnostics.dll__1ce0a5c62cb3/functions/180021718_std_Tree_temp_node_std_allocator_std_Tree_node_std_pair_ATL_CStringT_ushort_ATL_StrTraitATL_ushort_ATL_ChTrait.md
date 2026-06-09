# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(void)

- ea: `0x180021718`
- end: `0x180021740`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021238`

## callees

- `0x18001152c`
- `0x180021718`
- `0x1800217d4`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(v2 + 32);
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,void *>>>(a1);
}

```

## disassembly

```asm
0x180021718  push    rbx
0x18002171a  sub     rsp, 20h
0x18002171e  mov     rbx, rcx
0x180021721  mov     rcx, [rcx+8]
0x180021725  test    rcx, rcx
0x180021728  jz      short loc_180021733
0x18002172a  add     rcx, 20h ; ' '
0x18002172e  call    ??1?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@QEAA@XZ; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::~pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(void)
0x180021733  mov     rcx, rbx
0x180021736  add     rsp, 20h
0x18002173a  pop     rbx
0x18002173b  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *>>>(void)
```
