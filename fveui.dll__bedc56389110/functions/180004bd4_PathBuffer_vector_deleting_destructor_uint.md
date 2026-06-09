# PathBuffer::`vector deleting destructor'(uint)

- ea: `0x180004bd4`
- end: `0x180004c0e`
- name: `??_EPathBuffer@@QEAAPEAXI@Z`
- size: `58`
- prototype: `_QWORD *__fastcall(PathBuffer *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007360`
- `0x180012be8`

## callees

- `0x18000204c`
- `0x18000211c`

## pseudocode

```c
_QWORD *__fastcall PathBuffer::`vector deleting destructor'(PathBuffer *this)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)((char *)this - 8);
  `eh vector destructor iterator'(this, 8u, *((_QWORD *)this - 1), (void (*)(void *))PathBuffer::~PathBuffer);
  operator delete[](v1, 8LL * *v1 + 8);
  return v1;
}

```

## disassembly

```asm
0x180004bd4  push    rbx
0x180004bd6  sub     rsp, 20h
0x180004bda  lea     rbx, [rcx-8]
0x180004bde  lea     r9, ??1PathBuffer@@QEAA@XZ; void (*)(void *)
0x180004be5  mov     r8, [rbx]; unsigned __int64
0x180004be8  mov     edx, 8; unsigned __int64
0x180004bed  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180004bf2  mov     rdx, [rbx]
0x180004bf5  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x180004bfd  mov     rcx, rbx; void *
0x180004c00  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x180004c05  mov     rax, rbx
0x180004c08  add     rsp, 20h
0x180004c0c  pop     rbx
0x180004c0d  retn
```
