# std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Emplace_hint<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *> * const,std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &)

- ea: `0x18001dc0c`
- end: `0x18001dd04`
- name: `??$_Emplace_hint@AEBU?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@1@QEAU21@AEBU?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@1@@Z`
- size: `248`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800031b0`

## callees

- `0x180017174`
- `0x18001dbfc`
- `0x18001dc0c`
- `0x18001dec4`
- `0x18001e354`
- `0x18001e60c`
- `0x18001e6f8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001dc61`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001dc61`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Emplace_hint<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &>(
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
  v4 = std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_hint<enum HWSecurityRegistryManager::RegKeys>(
         a1,
         &v10,
         a2,
         a3);
  v5 = *(__int128 **)v4;
  v6 = *(_QWORD *)(v4 + 8);
  if ( *(_BYTE *)(v4 + 16) )
    return *(_QWORD *)v4;
  if ( *((_QWORD *)&HWSecurityRegistryManager::m_RegKeyTable + 1) == 0x1745D1745D1745DLL )
    std::_Xlength_error("map/set too long");
  v12 = HWSecurityRegistryManager::m_RegKeyTable;
  v10 = &HWSecurityRegistryManager::m_RegKeyTable;
  v11 = 0;
  v8 = std::_Allocate<16,std::_Default_allocate_traits>(176);
  v11 = v8;
  std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>::construct<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &>(
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
  std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>(&v10);
  v10 = v5;
  v11 = v6;
  return std::_Tree_val<std::_Tree_simple_types<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Insert_node(
           &HWSecurityRegistryManager::m_RegKeyTable,
           &v10,
           v8);
}

```

## disassembly

```asm
0x18001dc0c  mov     [rsp-30h+arg_0], rcx
0x18001dc11  push    rbp
0x18001dc12  push    rbx
0x18001dc13  push    rsi
0x18001dc14  push    rdi
0x18001dc15  push    r14
0x18001dc17  push    r15
0x18001dc19  mov     rbp, rsp
0x18001dc1c  sub     rsp, 48h
0x18001dc20  mov     r14, r8
0x18001dc23  mov     r9, r8
0x18001dc26  mov     r8, rdx
0x18001dc29  lea     rdx, [rbp+var_28]
0x18001dc2d  call    ??$_Find_hint@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_hint<HWSecurityRegistryManager::RegKeys>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *> * const,HWSecurityRegistryManager::RegKeys const &)
0x18001dc32  mov     rsi, [rax]
0x18001dc35  mov     rbx, [rax+8]
0x18001dc39  cmp     byte ptr [rax+10h], 0
0x18001dc3d  jz      short loc_18001DC47
0x18001dc3f  mov     rax, rsi
0x18001dc42  jmp     loc_18001DCF7
0x18001dc47  mov     rax, 1745D1745D1745Dh
0x18001dc51  cmp     qword ptr cs:?m_RegKeyTable@HWSecurityRegistryManager@@0V?$map@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@@std@@A+8, rax; std::map<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry> HWSecurityRegistryManager::m_RegKeyTable
0x18001dc58  jnz     short loc_18001DC68
0x18001dc5a  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001dc61  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001dc68  mov     rax, qword ptr cs:?m_RegKeyTable@HWSecurityRegistryManager@@0V?$map@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@@std@@A; std::map<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry> HWSecurityRegistryManager::m_RegKeyTable
0x18001dc6f  mov     [rbp+arg_0], rax
0x18001dc73  lea     r15, ?m_RegKeyTable@HWSecurityRegistryManager@@0V?$map@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@@std@@A; std::map<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry> HWSecurityRegistryManager::m_RegKeyTable
0x18001dc7a  mov     [rbp+var_28], r15
0x18001dc7e  mov     [rbp+var_20], 0
0x18001dc86  mov     ecx, 0B0h
0x18001dc8b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001dc90  mov     rdi, rax
0x18001dc93  mov     [rbp+var_20], rax
0x18001dc97  lea     rdx, [rax+20h]
0x18001dc9b  mov     r8, r14
0x18001dc9e  call    ??$construct@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@1@AEBU31@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>::construct<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &>(std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>> &,std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> * const,std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &)
0x18001dca3  lea     rdx, [rbp+arg_0]
0x18001dca7  mov     rcx, rdi
0x18001dcaa  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &)
0x18001dcaf  lea     rcx, [rdi+8]
0x18001dcb3  lea     rdx, [rbp+arg_0]
0x18001dcb7  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &)
0x18001dcbc  lea     rcx, [rdi+10h]
0x18001dcc0  lea     rdx, [rbp+arg_0]
0x18001dcc4  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &>(std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * &)
0x18001dcc9  mov     word ptr [rdi+18h], 0
0x18001dccf  mov     [rbp+var_20], 0
0x18001dcd7  lea     rcx, [rbp+var_28]
0x18001dcdb  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>,void *>>>(void)
0x18001dce0  mov     [rbp+var_28], rsi
0x18001dce4  mov     [rbp+var_20], rbx
0x18001dce8  mov     r8, rdi
0x18001dceb  lea     rdx, [rbp+var_28]
0x18001dcef  mov     rcx, r15
0x18001dcf2  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> *>,std::_Tree_node<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>,void *> * const)
0x18001dcf7  add     rsp, 48h
0x18001dcfb  pop     r15
0x18001dcfd  pop     r14
0x18001dcff  pop     rdi
0x18001dd00  pop     rsi
0x18001dd01  pop     rbx
0x18001dd02  pop     rbp
0x18001dd03  retn
```
