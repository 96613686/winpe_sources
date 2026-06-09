# _Cabinet::CreateCabSelected_::_1_::dtor$2

- ea: `0x18001406c`
- end: `0x180014078`
- name: `_Cabinet::CreateCabSelected_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800036b4`

## pseudocode

```c
void __fastcall Cabinet::CreateCabSelected_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(a2 + 128);
}

```

## disassembly

```asm
0x18001406c  lea     rcx, [rdx+80h]
0x180014073  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
