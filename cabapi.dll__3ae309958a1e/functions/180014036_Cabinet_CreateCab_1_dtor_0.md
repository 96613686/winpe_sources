# _Cabinet::CreateCab_::_1_::dtor$0

- ea: `0x180014036`
- end: `0x180014042`
- name: `_Cabinet::CreateCab_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800036b4`

## pseudocode

```c
void __fastcall Cabinet::CreateCab_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(a2 + 72);
}

```

## disassembly

```asm
0x180014036  lea     rcx, [rdx+48h]
0x18001403d  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
