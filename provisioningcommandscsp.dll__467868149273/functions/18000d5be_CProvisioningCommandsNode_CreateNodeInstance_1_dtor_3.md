# _CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$3

- ea: `0x18000d5be`
- end: `0x18000d5ca`
- name: `_CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000aab0`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  RegistryConfig::~RegistryConfig((void **)(a2 + 272));
}

```

## disassembly

```asm
0x18000d5be  lea     rcx, [rdx+110h]; this
0x18000d5c5  jmp     ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
```
