# CProvisioningCommandsCSP::`vector deleting destructor'(uint)

- ea: `0x180006160`
- end: `0x180006190`
- name: `??_ECProvisioningCommandsCSP@@MEAAPEAXI@Z`
- size: `48`
- prototype: `CProvisioningCommandsCSP *__fastcall(CProvisioningCommandsCSP *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006130`
- `0x180006160`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000617c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000617c`

## pseudocode

```c
CProvisioningCommandsCSP *__fastcall CProvisioningCommandsCSP::`vector deleting destructor'(
        CProvisioningCommandsCSP *this,
        char a2)
{
  CProvisioningCommandsCSP::~CProvisioningCommandsCSP(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006160  mov     [rsp+arg_0], rbx
0x180006165  push    rdi
0x180006166  sub     rsp, 20h
0x18000616a  mov     ebx, edx
0x18000616c  mov     rdi, rcx
0x18000616f  call    ??1CProvisioningCommandsCSP@@MEAA@XZ; CProvisioningCommandsCSP::~CProvisioningCommandsCSP(void)
0x180006174  test    bl, 1
0x180006177  jz      short loc_180006182
0x180006179  mov     rcx, rdi
0x18000617c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006182  mov     rbx, [rsp+28h+arg_0]
0x180006187  mov     rax, rdi
0x18000618a  add     rsp, 20h
0x18000618e  pop     rdi
0x18000618f  retn
```
