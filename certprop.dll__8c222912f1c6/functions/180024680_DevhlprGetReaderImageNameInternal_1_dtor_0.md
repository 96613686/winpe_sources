# _DevhlprGetReaderImageNameInternal_::_1_::dtor$0

- ea: `0x180024680`
- end: `0x18002468c`
- name: `_DevhlprGetReaderImageNameInternal_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013db8`

## pseudocode

```c
__int64 __fastcall DevhlprGetReaderImageNameInternal_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 288));
}

```

## disassembly

```asm
0x180024680  mov     rcx, [rdx+120h]
0x180024687  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
