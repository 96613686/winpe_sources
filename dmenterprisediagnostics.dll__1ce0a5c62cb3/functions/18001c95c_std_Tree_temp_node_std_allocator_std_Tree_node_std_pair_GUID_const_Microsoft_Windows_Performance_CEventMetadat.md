# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(void)

- ea: `0x18001c95c`
- end: `0x18001c984`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c358`

## callees

- `0x18001c860`
- `0x18001c95c`
- `0x18001cbb8`

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
0x18001c95c  push    rbx
0x18001c95e  sub     rsp, 20h
0x18001c962  mov     rbx, rcx
0x18001c965  mov     rcx, [rcx+8]
0x18001c969  test    rcx, rcx
0x18001c96c  jz      short loc_18001C977
0x18001c96e  add     rcx, 30h ; '0'; this
0x18001c972  call    ??1CProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState::~CProviderInfoState(void)
0x18001c977  mov     rcx, rbx
0x18001c97a  add     rsp, 20h
0x18001c97e  pop     rbx
0x18001c97f  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>,void *>>>(void)
```
