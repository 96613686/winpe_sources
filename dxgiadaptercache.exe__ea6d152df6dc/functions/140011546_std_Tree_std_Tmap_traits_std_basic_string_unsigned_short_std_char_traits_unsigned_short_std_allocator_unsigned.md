# _std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____CachedAdapterInformation_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CachedAdapterInformation____0___::emplace_unsigned_short_(&)[40]_CachedAdapterInformation__::_1_::dtor$0

- ea: `0x140011546`
- end: `0x140011552`
- name: `_std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____CachedAdapterInformation_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CachedAdapterInformation____0___::emplace_unsigned_short_(&)[40]_CachedAdapterInformation__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400062d8`

## pseudocode

```c
void __fastcall std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____CachedAdapterInformation_std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__CachedAdapterInformation____0___::emplace_unsigned_short_____40__CachedAdapterInformation__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x140011546  lea     rcx, [rdx+20h]
0x14001154d  jmp     ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>(void)
```
