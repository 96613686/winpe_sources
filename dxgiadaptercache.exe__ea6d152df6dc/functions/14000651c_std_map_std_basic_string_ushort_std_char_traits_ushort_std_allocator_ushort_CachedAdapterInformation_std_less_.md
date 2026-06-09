# std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CachedAdapterInformation,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>>::~map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CachedAdapterInformation,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>>(void)

- ea: `0x14000651c`
- end: `0x140006521`
- name: `??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400115b8`

## callees

- `0x14000625c`

## pseudocode

```c
// attributes: thunk
void __fastcall std::map<std::wstring,CachedAdapterInformation>::~map<std::wstring,CachedAdapterInformation>(void **a1)
{
  std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>(a1);
}

```

## disassembly

```asm
0x14000651c  jmp     ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>(void)
```
