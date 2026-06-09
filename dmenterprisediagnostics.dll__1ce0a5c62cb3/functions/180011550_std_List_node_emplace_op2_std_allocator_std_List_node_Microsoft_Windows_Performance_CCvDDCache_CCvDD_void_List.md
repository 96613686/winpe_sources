# std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)

- ea: `0x180011550`
- end: `0x180011578`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018014`

## callees

- `0x1800114c0`
- `0x180011550`
- `0x180011724`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v2 + 16));
  std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(a1);
}

```

## disassembly

```asm
0x180011550  push    rbx
0x180011552  sub     rsp, 20h
0x180011556  mov     rbx, rcx
0x180011559  mov     rcx, [rcx+8]
0x18001155d  test    rcx, rcx
0x180011560  jz      short loc_18001156B
0x180011562  add     rcx, 10h; this
0x180011566  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x18001156b  mov     rcx, rbx
0x18001156e  add     rsp, 20h
0x180011572  pop     rbx
0x180011573  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)
```
