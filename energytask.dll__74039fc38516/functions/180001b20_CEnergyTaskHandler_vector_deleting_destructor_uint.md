# CEnergyTaskHandler::`vector deleting destructor'(uint)

- ea: `0x180001b20`
- end: `0x180001b4f`
- name: `??_ECEnergyTaskHandler@@UEAAPEAXI@Z`
- size: `47`
- prototype: `CEnergyTaskHandler *__fastcall(CEnergyTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180001a44`
- `0x180001b20`

## pseudocode

```c
CEnergyTaskHandler *__fastcall CEnergyTaskHandler::`vector deleting destructor'(CEnergyTaskHandler *this, char a2)
{
  CEnergyTaskHandler::~CEnergyTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001b20  mov     [rsp+arg_0], rbx
0x180001b25  push    rdi
0x180001b26  sub     rsp, 20h
0x180001b2a  mov     ebx, edx
0x180001b2c  mov     rdi, rcx
0x180001b2f  call    ??1CEnergyTaskHandler@@UEAA@XZ; CEnergyTaskHandler::~CEnergyTaskHandler(void)
0x180001b34  test    bl, 1
0x180001b37  jz      short loc_180001B41
0x180001b39  mov     rcx, rdi; Block
0x180001b3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001b41  mov     rbx, [rsp+28h+arg_0]
0x180001b46  mov     rax, rdi
0x180001b49  add     rsp, 20h
0x180001b4d  pop     rdi
0x180001b4e  retn
```
