# _std::map_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____unsigned___int64_WStringCaseInsensitiveCompare_std::allocator_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const__unsigned___int64_____::insert_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____unsigned___int64__0__::_1_::dtor$2

- ea: `0x18001435e`
- end: `0x18001436a`
- name: `_std::map_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____unsigned___int64_WStringCaseInsensitiveCompare_std::allocator_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const__unsigned___int64_____::insert_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____unsigned___int64__0__::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e04c`

## pseudocode

```c
__int64 __fastcall std::map_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____unsigned___int64_WStringCaseInsensitiveCompare_std::allocator_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const__unsigned___int64_____::insert_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____unsigned___int64__0__::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x18001435e  lea     rcx, [rdx+20h]
0x180014365  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned __int64>,void *>>>(void)
```
