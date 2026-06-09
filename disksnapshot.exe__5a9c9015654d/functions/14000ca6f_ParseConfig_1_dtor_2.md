# _ParseConfig_::_1_::dtor$2

- ea: `0x14000ca6f`
- end: `0x14000ca7b`
- name: `_ParseConfig_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140002fb8`

## pseudocode

```c
__int64 __fastcall ParseConfig_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 136));
}

```

## disassembly

```asm
0x14000ca6f  lea     rcx, [rdx+88h]
0x14000ca76  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
