# _WriteOutputHeaders_::_1_::dtor$1

- ea: `0x14000c641`
- end: `0x14000c64d`
- name: `_WriteOutputHeaders_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002fb8`

## pseudocode

```c
__int64 __fastcall WriteOutputHeaders_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 120));
}

```

## disassembly

```asm
0x14000c641  lea     rcx, [rdx+78h]
0x14000c648  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
