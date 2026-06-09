# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(void)

- ea: `0x18001d438`
- end: `0x18001d460`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ce3c`

## callees

- `0x18001d33c`
- `0x18001d438`
- `0x18001d6ac`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState::~CProviderInfoState((Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState *)(v2 + 48));
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(a1);
}

```

## disassembly

```asm
0x18001d438  push    rbx
0x18001d43a  sub     rsp, 20h
0x18001d43e  mov     rbx, rcx
0x18001d441  mov     rcx, [rcx+8]
0x18001d445  test    rcx, rcx
0x18001d448  jz      short loc_18001D453
0x18001d44a  add     rcx, 30h ; '0'; this
0x18001d44e  call    ??1CProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState::~CProviderInfoState(void)
0x18001d453  mov     rcx, rbx
0x18001d456  add     rsp, 20h
0x18001d45a  pop     rbx
0x18001d45b  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(void)
```
