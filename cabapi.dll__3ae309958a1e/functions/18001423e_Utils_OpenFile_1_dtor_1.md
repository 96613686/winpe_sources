# _Utils::OpenFile_::_1_::dtor$1

- ea: `0x18001423e`
- end: `0x18001424a`
- name: `_Utils::OpenFile_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall Utils::OpenFile_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 88));
}

```

## disassembly

```asm
0x18001423e  lea     rcx, [rdx+58h]
0x180014245  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
