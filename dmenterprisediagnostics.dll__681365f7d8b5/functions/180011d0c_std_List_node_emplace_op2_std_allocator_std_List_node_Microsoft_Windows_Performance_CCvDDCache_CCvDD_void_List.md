# std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)

- ea: `0x180011d0c`
- end: `0x180011d34`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800102a8`

## callees

- `0x180011c7c`
- `0x180011d0c`
- `0x180011eec`

## pseudocode

```c
__int64 __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((void **)(v2 + 16));
  return std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(a1);
}

```

## disassembly

```asm
0x180011d0c  push    rbx
0x180011d0e  sub     rsp, 20h
0x180011d12  mov     rbx, rcx
0x180011d15  mov     rcx, [rcx+8]
0x180011d19  test    rcx, rcx
0x180011d1c  jz      short loc_180011D27
0x180011d1e  add     rcx, 10h; this
0x180011d22  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x180011d27  mov     rcx, rbx
0x180011d2a  add     rsp, 20h
0x180011d2e  pop     rbx
0x180011d2f  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)
```
