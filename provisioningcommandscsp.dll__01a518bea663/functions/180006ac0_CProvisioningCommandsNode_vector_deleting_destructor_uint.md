# CProvisioningCommandsNode::`vector deleting destructor'(uint)

- ea: `0x180006ac0`
- end: `0x180006af0`
- name: `??_ECProvisioningCommandsNode@@MEAAPEAXI@Z`
- size: `48`
- prototype: `CProvisioningCommandsNode *__fastcall(CProvisioningCommandsNode *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006a70`
- `0x180006ac0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006adc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006adc`

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
0x180006ac0  mov     [rsp+arg_0], rbx
0x180006ac5  push    rdi
0x180006ac6  sub     rsp, 20h
0x180006aca  mov     ebx, edx
0x180006acc  mov     rdi, rcx
0x180006acf  call    ??1CProvisioningCommandsNode@@MEAA@XZ; CProvisioningCommandsNode::~CProvisioningCommandsNode(void)
0x180006ad4  test    bl, 1
0x180006ad7  jz      short loc_180006AE2
0x180006ad9  mov     rcx, rdi
0x180006adc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006ae2  mov     rbx, [rsp+28h+arg_0]
0x180006ae7  mov     rax, rdi
0x180006aea  add     rsp, 20h
0x180006aee  pop     rdi
0x180006aef  retn
```
