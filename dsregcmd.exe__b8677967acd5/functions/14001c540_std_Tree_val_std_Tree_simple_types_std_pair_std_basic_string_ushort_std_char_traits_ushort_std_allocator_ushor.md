# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,JsonValue const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,JsonValue const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,JsonValue const *>,void *>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,JsonValue const *>,void *> *)

- ea: `0x14001c540`
- end: `0x14001c593`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@1@@Z`
- size: `83`
- prototype: `void __fastcall(__int64, __int64, char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x14001c540`
- `0x14001c884`

## callees

- `0x1400028ac`
- `0x1400032ec`
- `0x14001c540`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,JsonValue const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,JsonValue const *>,void *>>>(
        __int64 a1,
        __int64 a2,
        char *a3)
{
  char *v3; // rdi
  char *v6; // rbx

  v3 = a3;
  while ( !v3[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,JsonValue const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,JsonValue const *>,void *>>>(
      a1,
      a2,
      *((_QWORD *)v3 + 2));
    v6 = v3;
    v3 = *(char **)v3;
    std::wstring::~wstring(v6 + 32);
    operator delete(v6);
  }
}

```

## disassembly

```asm
0x14001c540  push    rbx
0x14001c542  push    rbp
0x14001c543  push    rsi
0x14001c544  push    rdi
0x14001c545  sub     rsp, 28h
0x14001c549  cmp     byte ptr [r8+19h], 0
0x14001c54e  mov     rdi, r8
0x14001c551  mov     rsi, rdx
0x14001c554  mov     rbp, rcx
0x14001c557  jnz     short loc_14001C58A
0x14001c559  mov     r8, [rdi+10h]
0x14001c55d  mov     rdx, rsi
0x14001c560  mov     rcx, rbp
0x14001c563  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,JsonValue const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,JsonValue const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,JsonValue const *>,void *>> &,std::_Tree_node<std::pair<std::wstring const,JsonValue const *>,void *> *)
0x14001c568  mov     rbx, rdi
0x14001c56b  mov     rdi, [rdi]
0x14001c56e  lea     rcx, [rbx+20h]
0x14001c572  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001c577  mov     edx, 48h ; 'H'
0x14001c57c  mov     rcx, rbx; Block
0x14001c57f  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14001c584  cmp     byte ptr [rdi+19h], 0
0x14001c588  jz      short loc_14001C559
0x14001c58a  add     rsp, 28h
0x14001c58e  pop     rdi
0x14001c58f  pop     rsi
0x14001c590  pop     rbp
0x14001c591  pop     rbx
0x14001c592  retn
```
