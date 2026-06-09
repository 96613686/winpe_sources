# _ExecuteCommands::Execute_::_1_::dtor$5

- ea: `0x14000aaf3`
- end: `0x14000aaff`
- name: `_ExecuteCommands::Execute_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140008370`

## pseudocode

```c
void __fastcall ExecuteCommands::Execute_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  RegistryConfig::~RegistryConfig((void **)(a2 + 368));
}

```

## disassembly

```asm
0x14000aaf3  lea     rcx, [rdx+170h]; this
0x14000aafa  jmp     ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
```
