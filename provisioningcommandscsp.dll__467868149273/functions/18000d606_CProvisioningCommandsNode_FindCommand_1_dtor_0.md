# _CProvisioningCommandsNode::FindCommand_::_1_::dtor$0

- ea: `0x18000d606`
- end: `0x18000d612`
- name: `_CProvisioningCommandsNode::FindCommand_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000aab0`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::FindCommand_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  RegistryConfig::~RegistryConfig((void **)(a2 + 96));
}

```

## disassembly

```asm
0x18000d606  lea     rcx, [rdx+60h]; this
0x18000d60d  jmp     ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
```
