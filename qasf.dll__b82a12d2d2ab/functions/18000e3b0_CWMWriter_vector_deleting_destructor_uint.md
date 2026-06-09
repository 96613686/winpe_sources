# CWMWriter::`vector deleting destructor'(uint)

- ea: `0x18000e3b0`
- end: `0x18000e3e4`
- name: `??_ECWMWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CWMWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001008`
- `0x18000e238`
- `0x18000e3b0`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall CWMWriter::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        char a2)
{
  CWMWriter::~CWMWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e3b0  mov     [rsp+arg_0], rbx
0x18000e3b5  push    rdi
0x18000e3b6  sub     rsp, 20h
0x18000e3ba  mov     ebx, edx
0x18000e3bc  mov     rdi, rcx
0x18000e3bf  call    ??1CWMWriter@@UEAA@XZ; CWMWriter::~CWMWriter(void)
0x18000e3c4  test    bl, 1
0x18000e3c7  jz      short loc_18000E3D6
0x18000e3c9  mov     edx, 210h; unsigned __int64
0x18000e3ce  mov     rcx, rdi; void *
0x18000e3d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e3d6  mov     rbx, [rsp+28h+arg_0]
0x18000e3db  mov     rax, rdi
0x18000e3de  add     rsp, 20h
0x18000e3e2  pop     rdi
0x18000e3e3  retn
```
