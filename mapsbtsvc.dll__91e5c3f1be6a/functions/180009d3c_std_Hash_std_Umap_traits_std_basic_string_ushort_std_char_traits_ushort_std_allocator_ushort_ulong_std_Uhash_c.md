# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Erase<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180009d3c`
- end: `0x180009ddf`
- name: `??$_Erase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@AEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `163`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000dd10`

## callees

- `0x180009d3c`
- `0x180009f40`
- `0x18000a060`
- `0x18000b880`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Erase<std::wstring>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // r11
  _QWORD *v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  _BYTE v11[24]; // [rsp+20h] [rbp-18h] BYREF

  v3 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a2);
  v5 = *(_QWORD **)(std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
                      a1,
                      v11,
                      v4,
                      v3)
                  + 8);
  if ( !v5 )
    return 0;
  v6 = a1[3];
  v7 = 2 * (v3 & a1[6]);
  if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6]) + 8) == v5 )
  {
    if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6])) == v5 )
    {
      v8 = a1[1];
      *(_QWORD *)(v6 + 16 * (v3 & a1[6])) = v8;
    }
    else
    {
      v8 = v5[1];
    }
    *(_QWORD *)(v6 + 8 * v7 + 8) = v8;
  }
  else if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6])) == v5 )
  {
    *(_QWORD *)(v6 + 16 * (v3 & a1[6])) = *v5;
  }
  v9 = *v5;
  --a1[2];
  *(_QWORD *)v5[1] = v9;
  *(_QWORD *)(v9 + 8) = v5[1];
  std::_List_node<std::pair<std::wstring const,unsigned long>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,unsigned long>,void *>>>();
  return 1;
}

```

## disassembly

```asm
0x180009d3c  mov     [rsp+arg_0], rbx
0x180009d41  push    rdi
0x180009d42  sub     rsp, 30h
0x180009d46  mov     rbx, rcx
0x180009d49  mov     r11, rdx
0x180009d4c  mov     rcx, rdx
0x180009d4f  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180009d54  mov     r9, rax
0x180009d57  lea     rdx, [rsp+38h+var_18]
0x180009d5c  mov     r8, r11
0x180009d5f  mov     rcx, rbx
0x180009d62  mov     rdi, rax
0x180009d65  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180009d6a  mov     rdx, [rax+8]
0x180009d6e  test    rdx, rdx
0x180009d71  jz      short loc_180009DD2
0x180009d73  mov     rcx, [rbx+30h]
0x180009d77  mov     r8, [rbx+18h]
0x180009d7b  and     rcx, rdi
0x180009d7e  add     rcx, rcx
0x180009d81  cmp     [r8+rcx*8+8], rdx
0x180009d86  jnz     short loc_180009DA3
0x180009d88  cmp     [r8+rcx*8], rdx
0x180009d8c  jnz     short loc_180009D98
0x180009d8e  mov     rax, [rbx+8]
0x180009d92  mov     [r8+rcx*8], rax
0x180009d96  jmp     short loc_180009D9C
0x180009d98  mov     rax, [rdx+8]
0x180009d9c  mov     [r8+rcx*8+8], rax
0x180009da1  jmp     short loc_180009DB0
0x180009da3  cmp     [r8+rcx*8], rdx
0x180009da7  jnz     short loc_180009DB0
0x180009da9  mov     rax, [rdx]
0x180009dac  mov     [r8+rcx*8], rax
0x180009db0  mov     rcx, [rdx]
0x180009db3  dec     qword ptr [rbx+10h]
0x180009db7  mov     rax, [rdx+8]
0x180009dbb  mov     [rax], rcx
0x180009dbe  mov     rax, [rdx+8]
0x180009dc2  mov     [rcx+8], rax
0x180009dc6  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,ulong>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,ulong>,void *>> &,std::_List_node<std::pair<std::wstring const,ulong>,void *> *)
0x180009dcb  mov     eax, 1
0x180009dd0  jmp     short loc_180009DD4
0x180009dd2  xor     eax, eax
0x180009dd4  mov     rbx, [rsp+38h+arg_0]
0x180009dd9  add     rsp, 30h
0x180009ddd  pop     rdi
0x180009dde  retn
```
