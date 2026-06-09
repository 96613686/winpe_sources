# _CProvisioningCommandsNode::GetValue_::_1_::dtor$0

- ea: `0x18000d1e3`
- end: `0x18000d1ef`
- name: `_CProvisioningCommandsNode::GetValue_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a050`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::GetValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Command::~Command((void **)(a2 + 80));
}

```

## disassembly

```asm
0x18000d1e3  lea     rcx, [rdx+50h]; this
0x18000d1ea  jmp     ??1Command@@QEAA@XZ; Command::~Command(void)
```
