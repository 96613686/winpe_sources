# _Cabinet::CreateCabSelected_::_1_::dtor$2_0

- ea: `0x1800140a2`
- end: `0x1800140ae`
- name: `_Cabinet::CreateCabSelected_::_1_::dtor$2_0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall Cabinet::CreateCabSelected_::_1_::dtor_2_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 272));
}

```

## disassembly

```asm
0x1800140a2  lea     rcx, [rdx+110h]
0x1800140a9  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
