# _RegistryConfig::ParseCommand_::_1_::dtor$1

- ea: `0x14000ad57`
- end: `0x14000ad63`
- name: `_RegistryConfig::ParseCommand_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007c34`

## pseudocode

```c
__int64 __fastcall RegistryConfig::ParseCommand_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 112);
}

```

## disassembly

```asm
0x14000ad57  lea     rcx, [rdx+70h]
0x14000ad5e  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
