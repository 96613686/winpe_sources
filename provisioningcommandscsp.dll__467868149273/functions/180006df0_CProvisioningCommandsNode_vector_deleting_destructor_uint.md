# CProvisioningCommandsNode::`vector deleting destructor'(uint)

- ea: `0x180006df0`
- end: `0x180006e27`
- name: `??_ECProvisioningCommandsNode@@MEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(CProvisioningCommandsNode *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006d9c`
- `0x180006df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006e0c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006e0c`

## pseudocode

```c
CProvisioningCommandsNode *__fastcall CProvisioningCommandsNode::`vector deleting destructor'(
        CProvisioningCommandsNode *this,
        char a2)
{
  CProvisioningCommandsNode::~CProvisioningCommandsNode(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006df0  mov     [rsp+arg_0], rbx
0x180006df5  push    rdi
0x180006df6  sub     rsp, 20h
0x180006dfa  mov     ebx, edx
0x180006dfc  mov     rdi, rcx
0x180006dff  call    ??1CProvisioningCommandsNode@@MEAA@XZ; CProvisioningCommandsNode::~CProvisioningCommandsNode(void)
0x180006e04  test    bl, 1
0x180006e07  jz      short loc_180006E18
0x180006e09  mov     rcx, rdi
0x180006e0c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006e13  nop     dword ptr [rax+rax+00h]
0x180006e18  mov     rbx, [rsp+28h+arg_0]
0x180006e1d  mov     rax, rdi
0x180006e20  add     rsp, 20h
0x180006e24  pop     rdi
0x180006e25  retn
```
