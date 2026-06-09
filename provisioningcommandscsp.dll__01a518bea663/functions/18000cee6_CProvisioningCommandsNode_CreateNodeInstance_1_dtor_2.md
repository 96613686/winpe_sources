# _CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$2

- ea: `0x18000cee6`
- end: `0x18000cef2`
- name: `_CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CommandSet::~CommandSet((CommandSet *)(a2 + 272));
}

```

## disassembly

```asm
0x18000cee6  lea     rcx, [rdx+110h]; this
0x18000ceed  jmp     ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
```
