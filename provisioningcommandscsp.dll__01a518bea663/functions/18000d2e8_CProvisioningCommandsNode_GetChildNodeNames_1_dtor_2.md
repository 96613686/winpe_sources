# _CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor$2

- ea: `0x18000d2e8`
- end: `0x18000d2f4`
- name: `_CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CommandSet::~CommandSet((CommandSet *)(a2 + 96));
}

```

## disassembly

```asm
0x18000d2e8  lea     rcx, [rdx+60h]; this
0x18000d2ef  jmp     ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
```
