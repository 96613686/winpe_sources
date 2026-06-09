# _ServiceCallbacks::SetCurrentCallingStateForCurrentThread_::_1_::dtor$5

- ea: `0x18000cbc1`
- end: `0x18000cbcd`
- name: `_ServiceCallbacks::SetCurrentCallingStateForCurrentThread_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009480`

## pseudocode

```c
__int64 __fastcall ServiceCallbacks::SetCurrentCallingStateForCurrentThread_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,enum CallingState>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,enum CallingState>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x18000cbc1  lea     rcx, [rdx+20h]
0x18000cbc8  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBKW4CallingState@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,CallingState>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,CallingState>,void *>>>(void)
```
