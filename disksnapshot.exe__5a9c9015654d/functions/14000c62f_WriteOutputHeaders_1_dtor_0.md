# _WriteOutputHeaders_::_1_::dtor$0

- ea: `0x14000c62f`
- end: `0x14000c63b`
- name: `_WriteOutputHeaders_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002fb8`

## pseudocode

```c
__int64 __fastcall WriteOutputHeaders_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 152));
}

```

## disassembly

```asm
0x14000c62f  lea     rcx, [rdx+98h]
0x14000c636  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
