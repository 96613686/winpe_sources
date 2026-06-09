# _Cabinet::CreateCabSelected_::_1_::dtor$8

- ea: `0x18001410e`
- end: `0x18001411a`
- name: `_Cabinet::CreateCabSelected_::_1_::dtor$8`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall Cabinet::CreateCabSelected_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 416));
}

```

## disassembly

```asm
0x18001410e  lea     rcx, [rdx+1A0h]
0x180014115  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
