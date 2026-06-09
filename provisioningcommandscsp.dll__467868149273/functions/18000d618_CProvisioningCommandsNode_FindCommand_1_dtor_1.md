# _CProvisioningCommandsNode::FindCommand_::_1_::dtor$1

- ea: `0x18000d618`
- end: `0x18000d624`
- name: `_CProvisioningCommandsNode::FindCommand_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a50c`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::FindCommand_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CommandSet::~CommandSet((void **)(a2 + 40));
}

```

## disassembly

```asm
0x18000d618  lea     rcx, [rdx+28h]; this
0x18000d61f  jmp     ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
```
