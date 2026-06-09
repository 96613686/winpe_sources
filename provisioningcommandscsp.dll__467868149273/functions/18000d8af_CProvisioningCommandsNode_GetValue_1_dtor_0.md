# _CProvisioningCommandsNode::GetValue_::_1_::dtor$0

- ea: `0x18000d8af`
- end: `0x18000d8bb`
- name: `_CProvisioningCommandsNode::GetValue_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a554`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::GetValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Command::~Command((void **)(a2 + 80));
}

```

## disassembly

```asm
0x18000d8af  lea     rcx, [rdx+50h]; this
0x18000d8b6  jmp     ??1Command@@QEAA@XZ; Command::~Command(void)
```
