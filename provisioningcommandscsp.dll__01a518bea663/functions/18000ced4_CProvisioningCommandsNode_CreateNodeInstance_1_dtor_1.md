# _CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$1

- ea: `0x18000ced4`
- end: `0x18000cee0`
- name: `_CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a550`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  RegistryConfig::~RegistryConfig((void **)(a2 + 112));
}

```

## disassembly

```asm
0x18000ced4  lea     rcx, [rdx+70h]; this
0x18000cedb  jmp     ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
```
