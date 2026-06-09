# std::_Alloc_construct_ptr<std::allocator<std::_List_node<PIXEventsThreadInfo,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<PIXEventsThreadInfo,void *>>>(void)

- ea: `0x180011a94`
- end: `0x180011ab0`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@UPIXEventsThreadInfo@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011934`
- `0x180013fc4`

## callees

- `0x180006e2c`
- `0x180011a94`

## pseudocode

```c
__int64 __fastcall std::_Alloc_construct_ptr<std::allocator<std::_List_node<PIXEventsThreadInfo,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<PIXEventsThreadInfo,void *>>>(
        __int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
    return std::_Deallocate<16>(v1, 40);
  return result;
}

```

## disassembly

```asm
0x180011a94  sub     rsp, 28h
0x180011a98  mov     rcx, [rcx+8]
0x180011a9c  test    rcx, rcx
0x180011a9f  jz      short loc_180011AAB
0x180011aa1  mov     edx, 28h ; '('
0x180011aa6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011aab  add     rsp, 28h
0x180011aaf  retn
```
