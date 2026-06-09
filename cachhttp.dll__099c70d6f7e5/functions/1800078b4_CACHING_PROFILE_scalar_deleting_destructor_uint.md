# CACHING_PROFILE::`scalar deleting destructor'(uint)

- ea: `0x1800078b4`
- end: `0x1800078d3`
- name: `??_GCACHING_PROFILE@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(CACHING_PROFILE *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800058ac`
- `0x180007918`

## callees

- `0x180005a4c`
- `0x180007880`

## pseudocode

```c
CACHING_PROFILE *__fastcall CACHING_PROFILE::`scalar deleting destructor'(CACHING_PROFILE *this)
{
  CACHING_PROFILE::~CACHING_PROFILE(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800078b4  push    rbx
0x1800078b6  sub     rsp, 20h
0x1800078ba  mov     rbx, rcx
0x1800078bd  call    ??1CACHING_PROFILE@@QEAA@XZ; CACHING_PROFILE::~CACHING_PROFILE(void)
0x1800078c2  mov     rcx, rbx; Block
0x1800078c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800078ca  mov     rax, rbx
0x1800078cd  add     rsp, 20h
0x1800078d1  pop     rbx
0x1800078d2  retn
```
