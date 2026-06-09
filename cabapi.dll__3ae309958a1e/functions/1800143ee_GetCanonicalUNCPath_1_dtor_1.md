# _GetCanonicalUNCPath_::_1_::dtor$1

- ea: `0x1800143ee`
- end: `0x1800143fa`
- name: `_GetCanonicalUNCPath_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall GetCanonicalUNCPath_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 208));
}

```

## disassembly

```asm
0x1800143ee  lea     rcx, [rdx+0D0h]
0x1800143f5  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
