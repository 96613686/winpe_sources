# _CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$4

- ea: `0x18000d5d0`
- end: `0x18000d5dc`
- name: `_CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a554`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Command::~Command((void **)(a2 + 160));
}

```

## disassembly

```asm
0x18000d5d0  lea     rcx, [rdx+0A0h]; this
0x18000d5d7  jmp     ??1Command@@QEAA@XZ; Command::~Command(void)
```
