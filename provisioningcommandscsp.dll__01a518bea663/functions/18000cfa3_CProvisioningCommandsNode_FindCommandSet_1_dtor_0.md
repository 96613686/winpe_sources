# _CProvisioningCommandsNode::FindCommandSet_::_1_::dtor$0

- ea: `0x18000cfa3`
- end: `0x18000cfaf`
- name: `_CProvisioningCommandsNode::FindCommandSet_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a550`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::FindCommandSet_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  RegistryConfig::~RegistryConfig((void **)(a2 + 56));
}

```

## disassembly

```asm
0x18000cfa3  lea     rcx, [rdx+38h]; this
0x18000cfaa  jmp     ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
```
