# _RegistryConfig::ParseCommand_::_1_::dtor$8

- ea: `0x18000cebe`
- end: `0x18000cece`
- name: `_RegistryConfig::ParseCommand_::_1_::dtor$8`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800069c0`

## pseudocode

```c
__int64 __fastcall RegistryConfig::ParseCommand_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 80) + 32LL);
}

```

## disassembly

```asm
0x18000cebe  mov     rcx, [rdx+50h]
0x18000cec5  add     rcx, 20h ; ' '
0x18000cec9  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
