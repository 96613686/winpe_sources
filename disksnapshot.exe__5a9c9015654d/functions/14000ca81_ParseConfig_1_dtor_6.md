# _ParseConfig_::_1_::dtor$6

- ea: `0x14000ca81`
- end: `0x14000ca8d`
- name: `_ParseConfig_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140002fb8`

## pseudocode

```c
__int64 __fastcall ParseConfig_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 168));
}

```

## disassembly

```asm
0x14000ca81  lea     rcx, [rdx+0A8h]
0x14000ca88  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
