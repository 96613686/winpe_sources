# _std::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void_______::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void________std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY____::_1_::dtor$0

- ea: `0x180011e6b`
- end: `0x180011e77`
- name: `_std::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void_______::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void________std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY____::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f9cc`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void_______::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void________std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,CLockTable::CSP_LOCK_ENTRY>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,CLockTable::CSP_LOCK_ENTRY>,void *>>>(*(_QWORD *)(a2 + 80));
}

```

## disassembly

```asm
0x180011e6b  mov     rcx, [rdx+50h]
0x180011e72  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,CLockTable::CSP_LOCK_ENTRY>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,CLockTable::CSP_LOCK_ENTRY>,void *>>>(void)
```
