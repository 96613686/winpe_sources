# _DevhlprGetReaderImageNameInternal_::_1_::dtor$11

- ea: `0x180024720`
- end: `0x18002472c`
- name: `_DevhlprGetReaderImageNameInternal_::_1_::dtor$11`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013db8`

## pseudocode

```c
__int64 __fastcall DevhlprGetReaderImageNameInternal_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 296);
}

```

## disassembly

```asm
0x180024720  lea     rcx, [rdx+128h]
0x180024727  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
