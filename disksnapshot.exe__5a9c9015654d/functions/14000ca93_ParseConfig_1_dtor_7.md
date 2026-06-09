# _ParseConfig_::_1_::dtor$7

- ea: `0x14000ca93`
- end: `0x14000ca9f`
- name: `_ParseConfig_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140002fb8`

## pseudocode

```c
__int64 __fastcall ParseConfig_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 232));
}

```

## disassembly

```asm
0x14000ca93  lea     rcx, [rdx+0E8h]
0x14000ca9a  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
