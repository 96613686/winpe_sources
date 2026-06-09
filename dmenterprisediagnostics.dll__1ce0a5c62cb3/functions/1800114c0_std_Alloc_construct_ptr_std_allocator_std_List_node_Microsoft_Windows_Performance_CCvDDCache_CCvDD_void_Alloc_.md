# std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)

- ea: `0x1800114c0`
- end: `0x1800114dc`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011550`
- `0x18002542f`

## callees

- `0x1800035c4`
- `0x1800114c0`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    std::_Deallocate<16>(v1, 0xA0u);
}

```

## disassembly

```asm
0x1800114c0  sub     rsp, 28h
0x1800114c4  mov     rcx, [rcx+8]
0x1800114c8  test    rcx, rcx
0x1800114cb  jz      short loc_1800114D7
0x1800114cd  mov     edx, 0A0h
0x1800114d2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800114d7  add     rsp, 28h
0x1800114db  retn
```
