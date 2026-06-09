# CProvisioningCommandsCSP::`vector deleting destructor'(uint)

- ea: `0x180006450`
- end: `0x180006487`
- name: `??_ECProvisioningCommandsCSP@@MEAAPEAXI@Z`
- size: `55`
- prototype: `void *__fastcall(CProvisioningCommandsCSP *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006420`
- `0x180006450`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000646c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000646c`

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
0x180006450  mov     [rsp+arg_0], rbx
0x180006455  push    rdi
0x180006456  sub     rsp, 20h
0x18000645a  mov     ebx, edx
0x18000645c  mov     rdi, rcx
0x18000645f  call    ??1CProvisioningCommandsCSP@@MEAA@XZ; CProvisioningCommandsCSP::~CProvisioningCommandsCSP(void)
0x180006464  test    bl, 1
0x180006467  jz      short loc_180006478
0x180006469  mov     rcx, rdi
0x18000646c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006473  nop     dword ptr [rax+rax+00h]
0x180006478  mov     rbx, [rsp+28h+arg_0]
0x18000647d  mov     rax, rdi
0x180006480  add     rsp, 20h
0x180006484  pop     rdi
0x180006485  retn
```
