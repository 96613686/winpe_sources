# _std::map_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t____ATL::CComPtr_IUMBusPDO__std::less_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t______std::allocator_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t____const__ATL::CComPtr_IUMBusPDO_______::insert_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t____ATL::CComPtr_IUMBusPDO____0__::_1_::dtor$2

- ea: `0x180015e1b`
- end: `0x180015e27`
- name: `_std::map_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t____ATL::CComPtr_IUMBusPDO__std::less_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t______std::allocator_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t____const__ATL::CComPtr_IUMBusPDO_______::insert_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t____ATL::CComPtr_IUMBusPDO____0__::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011500`

## pseudocode

```c
void __fastcall std::map_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t____ATL::CComPtr_IUMBusPDO__std::less_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t______std::allocator_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t____const__ATL::CComPtr_IUMBusPDO_______::insert_std::pair_std::basic_string_wchar_t_std::char_traits_wchar_t__StdAllocator_wchar_t____ATL::CComPtr_IUMBusPDO____0__::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x180015e1b  lea     rcx, [rdx+20h]
0x180015e22  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(void)
```
