# _DevhlprGetReaderImageNameInternal_::_1_::dtor$15

- ea: `0x180024760`
- end: `0x18002476c`
- name: `_DevhlprGetReaderImageNameInternal_::_1_::dtor$15`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013db8`

## pseudocode

```c
__int64 __fastcall DevhlprGetReaderImageNameInternal_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 328);
}

```

## disassembly

```asm
0x180024760  lea     rcx, [rdx+148h]
0x180024767  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
