# CProvisioningCommandsNode::~CProvisioningCommandsNode(void)

- ea: `0x180006d9c`
- end: `0x180006dbd`
- name: `??1CProvisioningCommandsNode@@MEAA@XZ`
- size: `33`
- prototype: `void __fastcall(CProvisioningCommandsNode *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006df0`

## callees

- `0x180009d1c`

## pseudocode

```c
void __fastcall CProvisioningCommandsNode::~CProvisioningCommandsNode(CProvisioningCommandsNode *this)
{
  *(_QWORD *)this = &CProvisioningCommandsNode::`vftable'{for `ICSPNode'};
  *((_QWORD *)this + 1) = &CProvisioningCommandsNode::`vftable'{for `ICSPNodeTransactioning'};
  _InterlockedDecrement(&dword_180014AB8);
  CCSPNodeImpl::~CCSPNodeImpl(this);
}

```

## disassembly

```asm
0x180006d9c  lea     rax, ??_7CProvisioningCommandsNode@@6BICSPNode@@@; const CProvisioningCommandsNode::`vftable'{for `ICSPNode'}
0x180006da3  mov     [rcx], rax
0x180006da6  lea     rax, ??_7CProvisioningCommandsNode@@6BICSPNodeTransactioning@@@; const CProvisioningCommandsNode::`vftable'{for `ICSPNodeTransactioning'}
0x180006dad  mov     [rcx+8], rax
0x180006db1  lock dec cs:dword_180014AB8
0x180006db8  jmp     ??1CCSPNodeImpl@@UEAA@XZ; CCSPNodeImpl::~CCSPNodeImpl(void)
```
