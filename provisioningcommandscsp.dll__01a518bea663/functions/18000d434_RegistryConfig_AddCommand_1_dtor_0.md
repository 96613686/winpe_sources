# _RegistryConfig::AddCommand_::_1_::dtor$0

- ea: `0x18000d434`
- end: `0x18000d440`
- name: `_RegistryConfig::AddCommand_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800069c0`

## pseudocode

```c
__int64 __fastcall RegistryConfig::AddCommand_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 136);
}

```

## disassembly

```asm
0x18000d434  lea     rcx, [rdx+88h]
0x18000d43b  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
