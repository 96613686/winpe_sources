# _std::_Tree_std::_Tset_traits_unsigned_long_std::less_unsigned_long__std::allocator_unsigned_long__1___::_Copy_nodes_0__::_1_::dtor$0

- ea: `0x180011e8f`
- end: `0x180011e9b`
- name: `_std::_Tree_std::_Tset_traits_unsigned_long_std::less_unsigned_long__std::allocator_unsigned_long__1___::_Copy_nodes_0__::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f9f0`

## pseudocode

```c
__int64 __fastcall std::_Tree_std::_Tset_traits_unsigned_long_std::less_unsigned_long__std::allocator_unsigned_long__1___::_Copy_nodes_0__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<unsigned long,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<unsigned long,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x180011e8f  lea     rcx, [rdx+20h]
0x180011e96  jmp     ??1?$_Erase_tree_and_orphan_guard@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAA@XZ; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<ulong,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<ulong,void *>>>(void)
```
