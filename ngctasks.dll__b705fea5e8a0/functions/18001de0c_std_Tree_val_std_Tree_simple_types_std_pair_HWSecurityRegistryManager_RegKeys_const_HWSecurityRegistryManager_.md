# std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>(std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>> &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *> *)

- ea: `0x18001de0c`
- end: `0x18001de62`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@1@@Z`
- size: `86`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001de0c`
- `0x18001e5ac`

## callees

- `0x1800172ec`
- `0x18001de0c`
- `0x18001e6b0`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rdi
  __int64 *v6; // rcx
  _QWORD *v7; // rbx

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v7 = v3;
    v3 = (__int64 *)*v3;
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)(v6 + 5));
    std::_Deallocate<16>(v7, 0xB0u);
  }
}

```

## disassembly

```asm
0x18001de0c  push    rbx
0x18001de0e  push    rbp
0x18001de0f  push    rsi
0x18001de10  push    rdi
0x18001de11  sub     rsp, 28h
0x18001de15  cmp     byte ptr [r8+19h], 0
0x18001de1a  mov     rdi, r8
0x18001de1d  mov     rsi, rdx
0x18001de20  mov     rbp, rcx
0x18001de23  jnz     short loc_18001DE59
0x18001de25  mov     r8, [rdi+10h]
0x18001de29  mov     rdx, rsi
0x18001de2c  mov     rcx, rbp
0x18001de2f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>(std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>> &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *> *)
0x18001de34  mov     rcx, rdi
0x18001de37  mov     rbx, rdi
0x18001de3a  mov     rdi, [rdi]
0x18001de3d  add     rcx, 28h ; '('; this
0x18001de41  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x18001de46  mov     edx, 0B0h
0x18001de4b  mov     rcx, rbx
0x18001de4e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001de53  cmp     byte ptr [rdi+19h], 0
0x18001de57  jz      short loc_18001DE25
0x18001de59  add     rsp, 28h
0x18001de5d  pop     rdi
0x18001de5e  pop     rsi
0x18001de5f  pop     rbp
0x18001de60  pop     rbx
0x18001de61  retn
```
