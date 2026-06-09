# TOKEN_ENTRY::`scalar deleting destructor'(uint)

- ea: `0x180010b10`
- end: `0x180010b3f`
- name: `??_GTOKEN_ENTRY@@EEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001060`
- `0x180010a80`
- `0x180010b10`

## pseudocode

```c
TOKEN_ENTRY *__fastcall TOKEN_ENTRY::`scalar deleting destructor'(TOKEN_ENTRY *this, char a2)
{
  TOKEN_ENTRY::~TOKEN_ENTRY(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180010b10  mov     [rsp+arg_0], rbx
0x180010b15  push    rdi
0x180010b16  sub     rsp, 20h
0x180010b1a  mov     ebx, edx
0x180010b1c  mov     rdi, rcx
0x180010b1f  call    ??1TOKEN_ENTRY@@EEAA@XZ; TOKEN_ENTRY::~TOKEN_ENTRY(void)
0x180010b24  test    bl, 1
0x180010b27  jz      short loc_180010B31
0x180010b29  mov     rcx, rdi; Block
0x180010b2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010b31  mov     rbx, [rsp+28h+arg_0]
0x180010b36  mov     rax, rdi
0x180010b39  add     rsp, 20h
0x180010b3d  pop     rdi
0x180010b3e  retn
```
