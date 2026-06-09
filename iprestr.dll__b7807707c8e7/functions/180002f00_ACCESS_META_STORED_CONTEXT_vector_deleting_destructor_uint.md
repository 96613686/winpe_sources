# ACCESS_META_STORED_CONTEXT::`vector deleting destructor'(uint)

- ea: `0x180002f00`
- end: `0x180002f2f`
- name: `??_EACCESS_META_STORED_CONTEXT@@EEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(ACCESS_META_STORED_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800010c8`
- `0x180002e78`
- `0x180002f00`

## pseudocode

```c
ACCESS_META_STORED_CONTEXT *__fastcall ACCESS_META_STORED_CONTEXT::`vector deleting destructor'(
        ACCESS_META_STORED_CONTEXT *this,
        char a2)
{
  ACCESS_META_STORED_CONTEXT::~ACCESS_META_STORED_CONTEXT(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002f00  mov     [rsp+arg_0], rbx
0x180002f05  push    rdi
0x180002f06  sub     rsp, 20h
0x180002f0a  mov     ebx, edx
0x180002f0c  mov     rdi, rcx
0x180002f0f  call    ??1ACCESS_META_STORED_CONTEXT@@EEAA@XZ; ACCESS_META_STORED_CONTEXT::~ACCESS_META_STORED_CONTEXT(void)
0x180002f14  test    bl, 1
0x180002f17  jz      short loc_180002F21
0x180002f19  mov     rcx, rdi; Block
0x180002f1c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f21  mov     rbx, [rsp+28h+arg_0]
0x180002f26  mov     rax, rdi
0x180002f29  add     rsp, 20h
0x180002f2d  pop     rdi
0x180002f2e  retn
```
