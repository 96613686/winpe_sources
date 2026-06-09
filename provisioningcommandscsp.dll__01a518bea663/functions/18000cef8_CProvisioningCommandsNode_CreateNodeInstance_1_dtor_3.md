# _CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$3

- ea: `0x18000cef8`
- end: `0x18000cf04`
- name: `_CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a550`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  RegistryConfig::~RegistryConfig((void **)(a2 + 272));
}

```

## disassembly

```asm
0x18000cef8  lea     rcx, [rdx+110h]; this
0x18000ceff  jmp     ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
```
