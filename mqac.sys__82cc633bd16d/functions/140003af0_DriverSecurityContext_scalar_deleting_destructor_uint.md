# DriverSecurityContext::`scalar deleting destructor'(uint)

- ea: `0x140003af0`
- end: `0x140003b10`
- name: `??_GDriverSecurityContext@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(DriverSecurityContext *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003ad0`
- `0x14000e9a8`

## callees

- `0x1400010a4`
- `0x140003aa0`

## pseudocode

```c
DriverSecurityContext *__fastcall DriverSecurityContext::`scalar deleting destructor'(DriverSecurityContext *this)
{
  CACSecurityContext::~CACSecurityContext(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140003af0  push    rbx
0x140003af2  sub     rsp, 20h
0x140003af6  mov     rbx, rcx
0x140003af9  call    ??1CACSecurityContext@@QEAA@XZ; CACSecurityContext::~CACSecurityContext(void)
0x140003afe  mov     rcx, rbx; void *
0x140003b01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003b06  mov     rax, rbx
0x140003b09  add     rsp, 20h
0x140003b0d  pop     rbx
0x140003b0e  retn
```
