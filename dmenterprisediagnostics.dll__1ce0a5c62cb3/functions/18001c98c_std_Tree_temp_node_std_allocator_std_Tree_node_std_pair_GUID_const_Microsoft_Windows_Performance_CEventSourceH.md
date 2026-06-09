# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>(void)

- ea: `0x18001c98c`
- end: `0x18001c9b4`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c43c`

## callees

- `0x18001c884`
- `0x18001c98c`
- `0x18001ca10`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    std::vector<bool>::~vector<bool>(v2 + 48);
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>(a1);
}

```

## disassembly

```asm
0x18001c98c  push    rbx
0x18001c98e  sub     rsp, 20h
0x18001c992  mov     rbx, rcx
0x18001c995  mov     rcx, [rcx+8]
0x18001c999  test    rcx, rcx
0x18001c99c  jz      short loc_18001C9A7
0x18001c99e  add     rcx, 30h ; '0'
0x18001c9a2  call    ??1?$vector@_NV?$allocator@_N@std@@@std@@QEAA@XZ; std::vector<bool>::~vector<bool>(void)
0x18001c9a7  mov     rcx, rbx
0x18001c9aa  add     rsp, 20h
0x18001c9ae  pop     rbx
0x18001c9af  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>(void)
```
