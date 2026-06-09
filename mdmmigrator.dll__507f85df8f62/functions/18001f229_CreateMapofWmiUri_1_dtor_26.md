# _CreateMapofWmiUri_::_1_::dtor$26

- ea: `0x18001f229`
- end: `0x18001f235`
- name: `_CreateMapofWmiUri_::_1_::dtor$26`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008160`

## pseudocode

```c
__int64 __fastcall CreateMapofWmiUri_::_1_::dtor_26(__int64 a1, __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(a2 + 32);
}

```

## disassembly

```asm
0x18001f229  lea     rcx, [rdx+20h]
0x18001f230  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(void)
```
