# _Utils::ValidateFilePath_::_1_::dtor$0

- ea: `0x180014250`
- end: `0x18001425c`
- name: `_Utils::ValidateFilePath_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall Utils::ValidateFilePath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 304));
}

```

## disassembly

```asm
0x180014250  lea     rcx, [rdx+130h]
0x180014257  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
