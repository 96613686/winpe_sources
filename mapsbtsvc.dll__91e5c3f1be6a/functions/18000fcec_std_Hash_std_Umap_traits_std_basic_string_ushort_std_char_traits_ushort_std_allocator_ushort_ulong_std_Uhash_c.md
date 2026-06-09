# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Check_max_size(void)

- ea: `0x18000fcec`
- end: `0x18000fd13`
- name: `?_Check_max_size@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBAXXZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a460`
- `0x18000a9b8`
- `0x18000aab8`

## callees

- `0x18000fcec`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fd07`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fd07`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Check_max_size(
        __int64 a1)
{
  __int64 result; // rax

  result = 0x492492492492492LL;
  if ( *(_QWORD *)(a1 + 16) == 0x492492492492492LL )
    std::_Xlength_error("unordered_map/set too long");
  return result;
}

```

## disassembly

```asm
0x18000fcec  sub     rsp, 28h
0x18000fcf0  mov     rax, 492492492492492h
0x18000fcfa  cmp     [rcx+10h], rax
0x18000fcfe  jnz     short loc_18000FD0E
0x18000fd00  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000fd07  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000fd0e  add     rsp, 28h
0x18000fd12  retn
```
