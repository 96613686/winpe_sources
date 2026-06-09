# std::map<ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stringCompare,std::allocator<std::pair<ushort const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>::~map<ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stringCompare,std::allocator<std::pair<ushort const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>(void)

- ea: `0x180006454`
- end: `0x180006459`
- name: `??1?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018646`

## callees

- `0x180006308`

## pseudocode

```c
// attributes: thunk
void __fastcall std::map<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>>::~map<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>>(
        void **a1)
{
  std::_Tree<std::_Tmap_traits<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>,0>>(a1);
}

```

## disassembly

```asm
0x180006454  jmp     ??1?$_Tree@V?$_Tmap_traits@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<ushort const *,std::wstring,stringCompare,std::allocator<std::pair<ushort const * const,std::wstring>>,0>>(void)
```
