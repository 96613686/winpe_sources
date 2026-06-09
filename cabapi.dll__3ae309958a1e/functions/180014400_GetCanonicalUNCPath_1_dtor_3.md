# _GetCanonicalUNCPath_::_1_::dtor$3

- ea: `0x180014400`
- end: `0x18001440c`
- name: `_GetCanonicalUNCPath_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall GetCanonicalUNCPath_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 240));
}

```

## disassembly

```asm
0x180014400  lea     rcx, [rdx+0F0h]
0x180014407  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
