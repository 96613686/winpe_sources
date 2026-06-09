# _DevhlprGetReaderImageNameInternal_::_1_::dtor$2

- ea: `0x1800246c0`
- end: `0x1800246cc`
- name: `_DevhlprGetReaderImageNameInternal_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013db8`

## pseudocode

```c
__int64 __fastcall DevhlprGetReaderImageNameInternal_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 272));
}

```

## disassembly

```asm
0x1800246c0  mov     rcx, [rdx+110h]
0x1800246c7  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
