# _CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor$1

- ea: `0x18000d9a2`
- end: `0x18000d9ae`
- name: `_CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006d20`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::GetChildNodeNames_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::list<CommandSet>::~list<CommandSet>((void ***)(a2 + 80));
}

```

## disassembly

```asm
0x18000d9a2  lea     rcx, [rdx+50h]; void *
0x18000d9a9  jmp     ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
```
