# _CProvisioningCommandsNode::Clear_::_1_::dtor$1

- ea: `0x18000d900`
- end: `0x18000d90c`
- name: `_CProvisioningCommandsNode::Clear_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000aab0`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::Clear_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  RegistryConfig::~RegistryConfig((void **)(a2 + 72));
}

```

## disassembly

```asm
0x18000d900  lea     rcx, [rdx+48h]; this
0x18000d907  jmp     ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
```
