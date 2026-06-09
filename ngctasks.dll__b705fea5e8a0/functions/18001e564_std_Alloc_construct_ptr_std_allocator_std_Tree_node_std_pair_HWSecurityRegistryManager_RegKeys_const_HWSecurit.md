# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>(void)

- ea: `0x18001e564`
- end: `0x18001e580`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e60c`
- `0x18001e66c`
- `0x180020c14`

## callees

- `0x1800172ec`
- `0x18001e564`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>(
        __int64 a1)
{
  _QWORD *v1; // rcx

  v1 = *(_QWORD **)(a1 + 8);
  if ( v1 )
    std::_Deallocate<16>(v1, 0xB0u);
}

```

## disassembly

```asm
0x18001e564  sub     rsp, 28h
0x18001e568  mov     rcx, [rcx+8]
0x18001e56c  test    rcx, rcx
0x18001e56f  jz      short loc_18001E57B
0x18001e571  mov     edx, 0B0h
0x18001e576  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e57b  add     rsp, 28h
0x18001e57f  retn
```
