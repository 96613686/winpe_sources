# COMPRESS_META_STORED_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x180001890`
- end: `0x1800018c0`
- name: `??_GCOMPRESS_META_STORED_CONTEXT@@EEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(COMPRESS_META_STORED_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001890`
- `0x1800018d0`
- `0x180004250`

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
0x180001890  mov     [rsp+arg_0], rbx
0x180001895  push    rdi
0x180001896  sub     rsp, 20h
0x18000189a  mov     edi, edx
0x18000189c  mov     rbx, rcx
0x18000189f  call    ??1COMPRESS_META_STORED_CONTEXT@@EEAA@XZ; COMPRESS_META_STORED_CONTEXT::~COMPRESS_META_STORED_CONTEXT(void)
0x1800018a4  test    dil, 1
0x1800018a8  jz      short loc_1800018B2
0x1800018aa  mov     rcx, rbx; Block
0x1800018ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800018b2  mov     rax, rbx
0x1800018b5  mov     rbx, [rsp+28h+arg_0]
0x1800018ba  add     rsp, 20h
0x1800018be  pop     rdi
0x1800018bf  retn
```
