# _RegistryConfig::ParseCommand_::_1_::dtor$0

- ea: `0x18000d85e`
- end: `0x18000d86a`
- name: `_RegistryConfig::ParseCommand_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006ce0`

## pseudocode

```c
__int64 __fastcall RegistryConfig::ParseCommand_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 144);
}

```

## disassembly

```asm
0x18000d85e  lea     rcx, [rdx+90h]
0x18000d865  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
