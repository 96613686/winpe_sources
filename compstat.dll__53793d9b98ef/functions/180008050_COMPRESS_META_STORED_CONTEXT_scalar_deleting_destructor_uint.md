# COMPRESS_META_STORED_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x180008050`
- end: `0x18000807f`
- name: `??_GCOMPRESS_META_STORED_CONTEXT@@EEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(COMPRESS_META_STORED_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800054a0`
- `0x180007fc8`
- `0x180008050`

## pseudocode

```c
COMPRESS_META_STORED_CONTEXT *__fastcall COMPRESS_META_STORED_CONTEXT::`scalar deleting destructor'(
        COMPRESS_META_STORED_CONTEXT *this,
        char a2)
{
  COMPRESS_META_STORED_CONTEXT::~COMPRESS_META_STORED_CONTEXT(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008050  mov     [rsp+arg_0], rbx
0x180008055  push    rdi
0x180008056  sub     rsp, 20h
0x18000805a  mov     ebx, edx
0x18000805c  mov     rdi, rcx
0x18000805f  call    ??1COMPRESS_META_STORED_CONTEXT@@EEAA@XZ; COMPRESS_META_STORED_CONTEXT::~COMPRESS_META_STORED_CONTEXT(void)
0x180008064  test    bl, 1
0x180008067  jz      short loc_180008071
0x180008069  mov     rcx, rdi; Block
0x18000806c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008071  mov     rbx, [rsp+28h+arg_0]
0x180008076  mov     rax, rdi
0x180008079  add     rsp, 20h
0x18000807d  pop     rdi
0x18000807e  retn
```
