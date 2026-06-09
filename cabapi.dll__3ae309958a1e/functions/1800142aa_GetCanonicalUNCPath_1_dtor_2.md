# _GetCanonicalUNCPath_::_1_::dtor$2

- ea: `0x1800142aa`
- end: `0x1800142b6`
- name: `_GetCanonicalUNCPath_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall GetCanonicalUNCPath_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 144));
}

```

## disassembly

```asm
0x1800142aa  lea     rcx, [rdx+90h]
0x1800142b1  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
