# CLR_HOSTING_BASE::`scalar deleting destructor'(uint)

- ea: `0x180003ab0`
- end: `0x180003adf`
- name: `??_GCLR_HOSTING_BASE@@MEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CLR_HOSTING_BASE *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180003a18`
- `0x180003ab0`

## pseudocode

```c
CLR_HOSTING_BASE *__fastcall CLR_HOSTING_BASE::`scalar deleting destructor'(CLR_HOSTING_BASE *this, char a2)
{
  CLR_HOSTING_BASE::~CLR_HOSTING_BASE(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003ab0  mov     [rsp+arg_0], rbx
0x180003ab5  push    rdi
0x180003ab6  sub     rsp, 20h
0x180003aba  mov     ebx, edx
0x180003abc  mov     rdi, rcx
0x180003abf  call    ??1CLR_HOSTING_BASE@@MEAA@XZ; CLR_HOSTING_BASE::~CLR_HOSTING_BASE(void)
0x180003ac4  test    bl, 1
0x180003ac7  jz      short loc_180003AD1
0x180003ac9  mov     rcx, rdi; Block
0x180003acc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003ad1  mov     rbx, [rsp+28h+arg_0]
0x180003ad6  mov     rax, rdi
0x180003ad9  add     rsp, 20h
0x180003add  pop     rdi
0x180003ade  retn
```
