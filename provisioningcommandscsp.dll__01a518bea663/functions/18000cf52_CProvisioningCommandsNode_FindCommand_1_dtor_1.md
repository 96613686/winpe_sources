# _CProvisioningCommandsNode::FindCommand_::_1_::dtor$1

- ea: `0x18000cf52`
- end: `0x18000cf5e`
- name: `_CProvisioningCommandsNode::FindCommand_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::FindCommand_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CommandSet::~CommandSet((CommandSet *)(a2 + 40));
}

```

## disassembly

```asm
0x18000cf52  lea     rcx, [rdx+28h]; this
0x18000cf59  jmp     ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
```
