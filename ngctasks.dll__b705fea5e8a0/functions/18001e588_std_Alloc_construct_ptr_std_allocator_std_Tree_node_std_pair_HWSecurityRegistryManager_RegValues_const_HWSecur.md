# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>(void)

- ea: `0x18001e588`
- end: `0x18001e5a4`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e63c`
- `0x18001e678`
- `0x180020c38`

## callees

- `0x1800172ec`
- `0x18001e588`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>(
        __int64 a1)
{
  _QWORD *v1; // rcx

  v1 = *(_QWORD **)(a1 + 8);
  if ( v1 )
    std::_Deallocate<16>(v1, 0x58u);
}

```

## disassembly

```asm
0x18001e588  sub     rsp, 28h
0x18001e58c  mov     rcx, [rcx+8]
0x18001e590  test    rcx, rcx
0x18001e593  jz      short loc_18001E59F
0x18001e595  mov     edx, 58h ; 'X'
0x18001e59a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e59f  add     rsp, 28h
0x18001e5a3  retn
```
