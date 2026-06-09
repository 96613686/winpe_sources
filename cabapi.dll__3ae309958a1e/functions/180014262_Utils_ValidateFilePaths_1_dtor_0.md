# _Utils::ValidateFilePaths_::_1_::dtor$0

- ea: `0x180014262`
- end: `0x18001426e`
- name: `_Utils::ValidateFilePaths_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b1d4`

## pseudocode

```c
void __fastcall Utils::ValidateFilePaths_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>::~set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>((void **)(a2 + 56));
}

```

## disassembly

```asm
0x180014262  lea     rcx, [rdx+38h]
0x180014269  jmp     ??1?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>::~set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>>(void)
```
