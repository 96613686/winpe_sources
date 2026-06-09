# _std::map_unsigned_short_const___std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____stringCompare_std::allocator_std::pair_unsigned_short_const___const_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_________::operator[]_::_1_::dtor$2

- ea: `0x18001865c`
- end: `0x180018668`
- name: `_std::map_unsigned_short_const___std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____stringCompare_std::allocator_std::pair_unsigned_short_const___const_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_________::operator[]_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800062e4`

## pseudocode

```c
__int64 __fastcall std::map_unsigned_short_const___std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____stringCompare_std::allocator_std::pair_unsigned_short_const___const_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_________::operator[]_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,std::wstring>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,std::wstring>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x18001865c  lea     rcx, [rdx+20h]
0x180018663  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ushort const * const,std::wstring>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ushort const * const,std::wstring>,void *>>>(void)
```
