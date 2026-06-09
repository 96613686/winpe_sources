# _CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor$0

- ea: `0x18000d2c4`
- end: `0x18000d2d0`
- name: `_CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a550`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  RegistryConfig::~RegistryConfig((void **)(a2 + 152));
}

```

## disassembly

```asm
0x18000d2c4  lea     rcx, [rdx+98h]; this
0x18000d2cb  jmp     ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
```
