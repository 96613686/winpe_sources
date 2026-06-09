# CWMWriterProperties::`scalar deleting destructor'(uint)

- ea: `0x1800120f0`
- end: `0x180012124`
- name: `??_GCWMWriterProperties@@EEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CWMWriterProperties *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800120e0`

## callees

- `0x180001008`
- `0x18001208c`
- `0x1800120f0`

## pseudocode

```c
CWMWriterProperties *__fastcall CWMWriterProperties::`scalar deleting destructor'(CWMWriterProperties *this, char a2)
{
  CWMWriterProperties::~CWMWriterProperties(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800120f0  mov     [rsp+arg_0], rbx
0x1800120f5  push    rdi
0x1800120f6  sub     rsp, 20h
0x1800120fa  mov     ebx, edx
0x1800120fc  mov     rdi, rcx
0x1800120ff  call    ??1CWMWriterProperties@@EEAA@XZ; CWMWriterProperties::~CWMWriterProperties(void)
0x180012104  test    bl, 1
0x180012107  jz      short loc_180012116
0x180012109  mov     edx, 78h ; 'x'; unsigned __int64
0x18001210e  mov     rcx, rdi; void *
0x180012111  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012116  mov     rbx, [rsp+28h+arg_0]
0x18001211b  mov     rax, rdi
0x18001211e  add     rsp, 20h
0x180012122  pop     rdi
0x180012123  retn
```
