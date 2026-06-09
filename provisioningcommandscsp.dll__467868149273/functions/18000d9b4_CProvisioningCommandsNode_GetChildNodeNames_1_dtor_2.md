# _CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor$2

- ea: `0x18000d9b4`
- end: `0x18000d9c0`
- name: `_CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a50c`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CommandSet::~CommandSet((void **)(a2 + 96));
}

```

## disassembly

```asm
0x18000d9b4  lea     rcx, [rdx+60h]; this
0x18000d9bb  jmp     ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
```
