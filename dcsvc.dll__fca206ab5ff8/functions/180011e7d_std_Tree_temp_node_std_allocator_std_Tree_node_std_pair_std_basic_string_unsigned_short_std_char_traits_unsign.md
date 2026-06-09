# _std::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void_______::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void________std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY____::_1_::dtor$2

- ea: `0x180011e7d`
- end: `0x180011e89`
- name: `_std::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void_______::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void________std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY____::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000fb28`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void_______::_Tree_temp_node_std::allocator_std::_Tree_node_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY__void________std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CLockTable::CSP_LOCK_ENTRY____::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(*(char ***)(a2 + 88));
}

```

## disassembly

```asm
0x180011e7d  mov     rcx, [rdx+58h]
0x180011e84  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
