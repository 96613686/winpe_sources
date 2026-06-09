# std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *>,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * const)

- ea: `0x18001e6f8`
- end: `0x18001e821`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `297`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dc0c`
- `0x18001dd0c`

## callees

- `0x18001e6f8`
- `0x18001e828`
- `0x18001e878`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Insert_node(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r9
  _QWORD *v4; // r11
  _QWORD *v6; // rax
  __int64 v7; // rax
  __int64 i; // r10
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax

  ++*(_QWORD *)(a1 + 8);
  v3 = a3;
  v4 = *(_QWORD **)a1;
  v6 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v6 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v6 = a3;
      if ( v6 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v6[2] = a3;
      if ( v6 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v7 = *(_QWORD *)(a3 + 8);
    for ( i = a3; ; v7 = *(_QWORD *)(i + 8) )
    {
      if ( *(_BYTE *)(v7 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return v3;
      }
      v9 = *(_QWORD *)(i + 8);
      v10 = *(__int64 **)(v9 + 8);
      v11 = *v10;
      if ( v9 == *v10 )
      {
        v11 = v10[2];
        if ( !*(_BYTE *)(v11 + 24) )
          goto LABEL_15;
        if ( i == *(_QWORD *)(v9 + 16) )
          std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Lrotate(
            a1,
            v9);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>>::_Rrotate(a1);
      }
      else
      {
        if ( !*(_BYTE *)(v11 + 24) )
        {
LABEL_15:
          *(_BYTE *)(v9 + 24) = 1;
          *(_BYTE *)(v11 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
          i = *(_QWORD *)(*(_QWORD *)(i + 8) + 8LL);
          continue;
        }
        if ( i == *(_QWORD *)v9 )
          std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>>::_Rrotate(a1);
        *(_BYTE *)(*(_QWORD *)(i + 8) + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(i + 8) + 8LL) + 24LL) = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Lrotate(
          a1,
          *(_QWORD *)(*(_QWORD *)(i + 8) + 8LL));
      }
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return v3;
}

```

## disassembly

```asm
0x18001e6f8  push    rbx
0x18001e6fa  sub     rsp, 20h
0x18001e6fe  inc     qword ptr [rcx+8]
0x18001e702  mov     r9, r8
0x18001e705  mov     r11, [rcx]
0x18001e708  mov     rbx, rcx
0x18001e70b  mov     rax, [rdx]
0x18001e70e  mov     [r8+8], rax
0x18001e712  cmp     rax, r11
0x18001e715  jnz     short loc_18001E72C
0x18001e717  mov     [r11], r8
0x18001e71a  mov     [r11+8], r8
0x18001e71e  mov     [r11+10h], r8
0x18001e722  mov     byte ptr [r8+18h], 1
0x18001e727  jmp     loc_18001E818
0x18001e72c  cmp     dword ptr [rdx+8], 0
0x18001e730  jnz     short loc_18001E742
0x18001e732  mov     [rax+10h], r9
0x18001e736  cmp     rax, [r11+10h]
0x18001e73a  jnz     short loc_18001E74D
0x18001e73c  mov     [r11+10h], r9
0x18001e740  jmp     short loc_18001E74D
0x18001e742  mov     [rax], r9
0x18001e745  cmp     rax, [r11]
0x18001e748  jnz     short loc_18001E74D
0x18001e74a  mov     [r11], r9
0x18001e74d  mov     rax, [r8+8]
0x18001e751  mov     r10, r9
0x18001e754  jmp     loc_18001E806
0x18001e759  mov     rdx, [r10+8]
0x18001e75d  mov     rcx, [rdx+8]
0x18001e761  mov     rax, [rcx]
0x18001e764  cmp     rdx, rax
0x18001e767  jnz     short loc_18001E7AA
0x18001e769  mov     rax, [rcx+10h]
0x18001e76d  cmp     byte ptr [rax+18h], 0
0x18001e771  jz      short loc_18001E7B0
0x18001e773  cmp     r10, [rdx+10h]
0x18001e777  jnz     short loc_18001E784
0x18001e779  mov     rcx, rbx
0x18001e77c  mov     r10, rdx
0x18001e77f  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Lrotate(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *)
0x18001e784  mov     rax, [r10+8]
0x18001e788  mov     byte ptr [rax+18h], 1
0x18001e78c  mov     rax, [r10+8]
0x18001e790  mov     rcx, [rax+8]
0x18001e794  mov     byte ptr [rcx+18h], 0
0x18001e798  mov     rcx, rbx
0x18001e79b  mov     rdx, [r10+8]
0x18001e79f  mov     rdx, [rdx+8]
0x18001e7a3  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>>::_Rrotate(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *> *)
0x18001e7a8  jmp     short loc_18001E802
0x18001e7aa  cmp     byte ptr [rax+18h], 0
0x18001e7ae  jnz     short loc_18001E7CE
0x18001e7b0  mov     byte ptr [rdx+18h], 1
0x18001e7b4  mov     byte ptr [rax+18h], 1
0x18001e7b8  mov     rax, [r10+8]
0x18001e7bc  mov     rcx, [rax+8]
0x18001e7c0  mov     byte ptr [rcx+18h], 0
0x18001e7c4  mov     rax, [r10+8]
0x18001e7c8  mov     r10, [rax+8]
0x18001e7cc  jmp     short loc_18001E802
0x18001e7ce  cmp     r10, [rdx]
0x18001e7d1  jnz     short loc_18001E7DE
0x18001e7d3  mov     rcx, rbx
0x18001e7d6  mov     r10, rdx
0x18001e7d9  call    ?_Rrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>>::_Rrotate(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *> *)
0x18001e7de  mov     rax, [r10+8]
0x18001e7e2  mov     byte ptr [rax+18h], 1
0x18001e7e6  mov     rax, [r10+8]
0x18001e7ea  mov     rcx, [rax+8]
0x18001e7ee  mov     byte ptr [rcx+18h], 0
0x18001e7f2  mov     rcx, rbx
0x18001e7f5  mov     rdx, [r10+8]
0x18001e7f9  mov     rdx, [rdx+8]
0x18001e7fd  call    ?_Lrotate@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Lrotate(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *)
0x18001e802  mov     rax, [r10+8]
0x18001e806  cmp     byte ptr [rax+18h], 0
0x18001e80a  jz      loc_18001E759
0x18001e810  mov     rax, [r11+8]
0x18001e814  mov     byte ptr [rax+18h], 1
0x18001e818  mov     rax, r9
0x18001e81b  add     rsp, 20h
0x18001e81f  pop     rbx
0x18001e820  retn
```
