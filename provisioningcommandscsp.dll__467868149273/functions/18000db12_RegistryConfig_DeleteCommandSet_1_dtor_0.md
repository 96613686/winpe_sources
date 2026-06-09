# _RegistryConfig::DeleteCommandSet_::_1_::dtor$0

- ea: `0x18000db12`
- end: `0x18000db1e`
- name: `_RegistryConfig::DeleteCommandSet_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006ce0`

## pseudocode

```c
__int64 __fastcall RegistryConfig::DeleteCommandSet_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 88);
}

```

## disassembly

```asm
0x18000db12  lea     rcx, [rdx+58h]
0x18000db19  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
