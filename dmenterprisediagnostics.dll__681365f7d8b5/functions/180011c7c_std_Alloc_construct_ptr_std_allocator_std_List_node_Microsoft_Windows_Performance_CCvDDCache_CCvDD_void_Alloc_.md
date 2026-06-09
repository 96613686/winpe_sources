# std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)

- ea: `0x180011c7c`
- end: `0x180011c99`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011d0c`
- `0x180025ca6`

## callees

- `0x180003618`
- `0x180011c7c`

## pseudocode

```c
__int64 __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(
        __int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
    return std::_Deallocate<16>(v1, 160);
  return result;
}

```

## disassembly

```asm
0x180011c7c  sub     rsp, 28h
0x180011c80  mov     rcx, [rcx+8]
0x180011c84  test    rcx, rcx
0x180011c87  jz      short loc_180011C93
0x180011c89  mov     edx, 0A0h
0x180011c8e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011c93  add     rsp, 28h
0x180011c97  retn
```
