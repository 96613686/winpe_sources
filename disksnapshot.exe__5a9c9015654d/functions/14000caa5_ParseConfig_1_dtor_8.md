# _ParseConfig_::_1_::dtor$8

- ea: `0x14000caa5`
- end: `0x14000cab1`
- name: `_ParseConfig_::_1_::dtor$8`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140002fb8`

## pseudocode

```c
__int64 __fastcall ParseConfig_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 264));
}

```

## disassembly

```asm
0x14000caa5  lea     rcx, [rdx+108h]
0x14000caac  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
