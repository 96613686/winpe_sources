# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Check_max_size(void)

- ea: `0x18000be30`
- end: `0x18000be57`
- name: `?_Check_max_size@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBAXXZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000983c`
- `0x18000da04`

## callees

- `0x18000be30`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000be4b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000be4b`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Check_max_size(
        __int64 a1)
{
  __int64 result; // rax

  result = 0x333333333333333LL;
  if ( *(_QWORD *)(a1 + 16) == 0x333333333333333LL )
    std::_Xlength_error("unordered_map/set too long");
  return result;
}

```

## disassembly

```asm
0x18000be30  sub     rsp, 28h
0x18000be34  mov     rax, 333333333333333h
0x18000be3e  cmp     [rcx+10h], rax
0x18000be42  jnz     short loc_18000BE52
0x18000be44  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000be4b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000be52  add     rsp, 28h
0x18000be56  retn
```
