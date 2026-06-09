# _std::_Tree_std::_Tset_traits_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____WstringCaseInsensitiveCompare_std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______0___::insert_0_0__::_1_::dtor$1

- ea: `0x18001417a`
- end: `0x180014186`
- name: `_std::_Tree_std::_Tset_traits_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____WstringCaseInsensitiveCompare_std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______0___::insert_0_0__::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b140`

## pseudocode

```c
__int64 __fastcall std::_Tree_std::_Tset_traits_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____WstringCaseInsensitiveCompare_std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t______0___::insert_0_0__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::wstring,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::wstring,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x18001417a  lea     rcx, [rdx+20h]
0x180014181  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::wstring,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::wstring,void *>>>(void)
```
