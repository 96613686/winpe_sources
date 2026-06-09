# _CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$2

- ea: `0x18000d5ac`
- end: `0x18000d5b8`
- name: `_CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a50c`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CommandSet::~CommandSet((void **)(a2 + 272));
}

```

## disassembly

```asm
0x18000d5ac  lea     rcx, [rdx+110h]; this
0x18000d5b3  jmp     ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
```
