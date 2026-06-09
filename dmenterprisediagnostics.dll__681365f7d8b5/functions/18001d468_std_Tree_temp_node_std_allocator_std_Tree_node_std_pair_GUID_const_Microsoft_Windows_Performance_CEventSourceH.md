# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>(void)

- ea: `0x18001d468`
- end: `0x18001d490`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cf1c`

## callees

- `0x18001d360`
- `0x18001d468`
- `0x18001d4ec`

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
0x18001d468  push    rbx
0x18001d46a  sub     rsp, 20h
0x18001d46e  mov     rbx, rcx
0x18001d471  mov     rcx, [rcx+8]
0x18001d475  test    rcx, rcx
0x18001d478  jz      short loc_18001D483
0x18001d47a  add     rcx, 30h ; '0'
0x18001d47e  call    ??1?$vector@_NV?$allocator@_N@std@@@std@@QEAA@XZ; std::vector<bool>::~vector<bool>(void)
0x18001d483  mov     rcx, rbx
0x18001d486  add     rsp, 20h
0x18001d48a  pop     rbx
0x18001d48b  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>,void *>>>(void)
```
