# _std::_Hash_std::_Uset_traits_long_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_long__0___::emplace_long_const_&__::_1_::dtor$0

- ea: `0x180014398`
- end: `0x1800143a4`
- name: `_std::_Hash_std::_Uset_traits_long_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_long__0___::emplace_long_const_&__::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011fc8`

## pseudocode

```c
__int64 __fastcall std::_Hash_std::_Uset_traits_long_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_long__0___::emplace_long_const____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_List_node<long,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<long,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x180014398  lea     rcx, [rdx+20h]
0x18001439f  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@JPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<long,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<long,void *>>>(void)
```
