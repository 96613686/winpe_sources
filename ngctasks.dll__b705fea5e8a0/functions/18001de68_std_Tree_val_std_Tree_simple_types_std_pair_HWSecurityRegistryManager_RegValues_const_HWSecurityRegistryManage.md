# std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>(std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>> &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *)

- ea: `0x18001de68`
- end: `0x18001debe`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@1@@Z`
- size: `86`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001de68`
- `0x18001e5dc`

## callees

- `0x1800172ec`
- `0x18001aaa0`
- `0x18001de68`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>(
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
    std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v7 = v3;
    v3 = (__int64 *)*v3;
    std::wstring::_Tidy_deallocate(v6 + 6);
    std::_Deallocate<16>(v7, 0x58u);
  }
}

```

## disassembly

```asm
0x18001de68  push    rbx
0x18001de6a  push    rbp
0x18001de6b  push    rsi
0x18001de6c  push    rdi
0x18001de6d  sub     rsp, 28h
0x18001de71  cmp     byte ptr [r8+19h], 0
0x18001de76  mov     rdi, r8
0x18001de79  mov     rsi, rdx
0x18001de7c  mov     rbp, rcx
0x18001de7f  jnz     short loc_18001DEB5
0x18001de81  mov     r8, [rdi+10h]
0x18001de85  mov     rdx, rsi
0x18001de88  mov     rcx, rbp
0x18001de8b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>(std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>> &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *)
0x18001de90  mov     rcx, rdi
0x18001de93  mov     rbx, rdi
0x18001de96  mov     rdi, [rdi]
0x18001de99  add     rcx, 30h ; '0'
0x18001de9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dea2  mov     edx, 58h ; 'X'
0x18001dea7  mov     rcx, rbx
0x18001deaa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001deaf  cmp     byte ptr [rdi+19h], 0
0x18001deb3  jz      short loc_18001DE81
0x18001deb5  add     rsp, 28h
0x18001deb9  pop     rdi
0x18001deba  pop     rsi
0x18001debb  pop     rbp
0x18001debc  pop     rbx
0x18001debd  retn
```
