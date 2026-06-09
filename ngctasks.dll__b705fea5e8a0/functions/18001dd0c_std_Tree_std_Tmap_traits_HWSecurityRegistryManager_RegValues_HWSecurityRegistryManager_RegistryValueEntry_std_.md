# std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Emplace_hint<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry> const &>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * const,std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry> const &)

- ea: `0x18001dd0c`
- end: `0x18001de04`
- name: `??$_Emplace_hint@AEBU?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@1@QEAU21@AEBU?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@1@@Z`
- size: `248`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003f10`

## callees

- `0x180017174`
- `0x18001dbfc`
- `0x18001dd0c`
- `0x18001e0b4`
- `0x18001e36c`
- `0x18001e63c`
- `0x18001e6f8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001dd61`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001dd61`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Emplace_hint<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry> const &>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rax
  __int128 *v5; // rsi
  __int64 v6; // rbx
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int128 *v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+28h] [rbp-20h]
  __int64 v12; // [rsp+80h] [rbp+38h] BYREF

  v12 = a1;
  v4 = std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_hint<enum HWSecurityRegistryManager::RegValues>(
         a1,
         &v10,
         a2,
         a3);
  v5 = *(__int128 **)v4;
  v6 = *(_QWORD *)(v4 + 8);
  if ( *(_BYTE *)(v4 + 16) )
    return *(_QWORD *)v4;
  if ( *((_QWORD *)&HWSecurityRegistryManager::m_RegValueTable + 1) == 0x2E8BA2E8BA2E8BALL )
    std::_Xlength_error("map/set too long");
  v12 = HWSecurityRegistryManager::m_RegValueTable;
  v10 = &HWSecurityRegistryManager::m_RegValueTable;
  v11 = 0;
  v8 = std::_Allocate<16,std::_Default_allocate_traits>(88);
  v11 = v8;
  std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>::construct<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry> const &>(
    v9,
    v8 + 32,
    a3);
  std::_Construct_in_place<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *,std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &>(
    (__int64 *)v8,
    &v12);
  std::_Construct_in_place<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *,std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &>(
    (__int64 *)(v8 + 8),
    &v12);
  std::_Construct_in_place<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *,std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &>(
    (__int64 *)(v8 + 16),
    &v12);
  *(_WORD *)(v8 + 24) = 0;
  v11 = 0;
  std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>(&v10);
  v10 = v5;
  v11 = v6;
  return std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Insert_node(
           &HWSecurityRegistryManager::m_RegValueTable,
           &v10,
           v8);
}

```

## disassembly

```asm
0x18001dd0c  mov     [rsp-30h+arg_0], rcx
0x18001dd11  push    rbp
0x18001dd12  push    rbx
0x18001dd13  push    rsi
0x18001dd14  push    rdi
0x18001dd15  push    r14
0x18001dd17  push    r15
0x18001dd19  mov     rbp, rsp
0x18001dd1c  sub     rsp, 48h
0x18001dd20  mov     r14, r8
0x18001dd23  mov     r9, r8
0x18001dd26  mov     r8, rdx
0x18001dd29  lea     rdx, [rbp+var_28]
0x18001dd2d  call    ??$_Find_hint@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_hint<HWSecurityRegistryManager::RegValues>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * const,HWSecurityRegistryManager::RegValues const &)
0x18001dd32  mov     rsi, [rax]
0x18001dd35  mov     rbx, [rax+8]
0x18001dd39  cmp     byte ptr [rax+10h], 0
0x18001dd3d  jz      short loc_18001DD47
0x18001dd3f  mov     rax, rsi
0x18001dd42  jmp     loc_18001DDF7
0x18001dd47  mov     rax, 2E8BA2E8BA2E8BAh
0x18001dd51  cmp     qword ptr cs:?m_RegValueTable@HWSecurityRegistryManager@@0V?$map@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@@std@@A+8, rax; std::map<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry> HWSecurityRegistryManager::m_RegValueTable
0x18001dd58  jnz     short loc_18001DD68
0x18001dd5a  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001dd61  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001dd68  mov     rax, qword ptr cs:?m_RegValueTable@HWSecurityRegistryManager@@0V?$map@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@@std@@A; std::map<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry> HWSecurityRegistryManager::m_RegValueTable
0x18001dd6f  mov     [rbp+arg_0], rax
0x18001dd73  lea     r15, ?m_RegValueTable@HWSecurityRegistryManager@@0V?$map@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@@std@@A; std::map<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry> HWSecurityRegistryManager::m_RegValueTable
0x18001dd7a  mov     [rbp+var_28], r15
0x18001dd7e  mov     [rbp+var_20], 0
0x18001dd86  mov     ecx, 58h ; 'X'
0x18001dd8b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001dd90  mov     rdi, rax
0x18001dd93  mov     [rbp+var_20], rax
0x18001dd97  lea     rdx, [rax+20h]
0x18001dd9b  mov     r8, r14
0x18001dd9e  call    ??$construct@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@1@AEBU31@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>::construct<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry> const &>(std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>> &,std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry> * const,std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry> const &)
0x18001dda3  lea     rdx, [rbp+arg_0]
0x18001dda7  mov     rcx, rdi
0x18001ddaa  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &)
0x18001ddaf  lea     rcx, [rdi+8]
0x18001ddb3  lea     rdx, [rbp+arg_0]
0x18001ddb7  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &)
0x18001ddbc  lea     rcx, [rdi+10h]
0x18001ddc0  lea     rdx, [rbp+arg_0]
0x18001ddc4  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &)
0x18001ddc9  mov     word ptr [rdi+18h], 0
0x18001ddcf  mov     [rbp+var_20], 0
0x18001ddd7  lea     rcx, [rbp+var_28]
0x18001dddb  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *>>>(void)
0x18001dde0  mov     [rbp+var_28], rsi
0x18001dde4  mov     [rbp+var_20], rbx
0x18001dde8  mov     r8, rdi
0x18001ddeb  lea     rdx, [rbp+var_28]
0x18001ddef  mov     rcx, r15
0x18001ddf2  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *>,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * const)
0x18001ddf7  add     rsp, 48h
0x18001ddfb  pop     r15
0x18001ddfd  pop     r14
0x18001ddff  pop     rdi
0x18001de00  pop     rsi
0x18001de01  pop     rbx
0x18001de02  pop     rbp
0x18001de03  retn
```
