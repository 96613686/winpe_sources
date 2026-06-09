# _GetCanonicalUNCPath_::_1_::dtor$0

- ea: `0x180014286`
- end: `0x180014292`
- name: `_GetCanonicalUNCPath_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall GetCanonicalUNCPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 112));
}

```

## disassembly

```asm
0x180014286  lea     rcx, [rdx+70h]
0x18001428d  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
