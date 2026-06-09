# _std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________0___::_Copy_nodes_0__::_1_::dtor$0

- ea: `0x18001f650`
- end: `0x18001f65c`
- name: `_std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________0___::_Copy_nodes_0__::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c634`

## pseudocode

```c
__int64 __fastcall std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________0___::_Copy_nodes_0__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x18001f650  lea     rcx, [rdx+20h]
0x18001f657  jmp     ??1?$_Erase_tree_and_orphan_guard@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAA@XZ; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(void)
```
