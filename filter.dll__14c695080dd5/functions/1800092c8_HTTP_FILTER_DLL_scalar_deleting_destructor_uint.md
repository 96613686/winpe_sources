# HTTP_FILTER_DLL::`scalar deleting destructor'(uint)

- ea: `0x1800092c8`
- end: `0x1800092e7`
- name: `??_GHTTP_FILTER_DLL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(HTTP_FILTER_DLL *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800092fc`

## callees

- `0x1800088fc`
- `0x180009258`

## pseudocode

```c
HTTP_FILTER_DLL *__fastcall HTTP_FILTER_DLL::`scalar deleting destructor'(HTTP_FILTER_DLL *this)
{
  HTTP_FILTER_DLL::~HTTP_FILTER_DLL(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800092c8  push    rbx
0x1800092ca  sub     rsp, 20h
0x1800092ce  mov     rbx, rcx
0x1800092d1  call    ??1HTTP_FILTER_DLL@@QEAA@XZ; HTTP_FILTER_DLL::~HTTP_FILTER_DLL(void)
0x1800092d6  mov     rcx, rbx; Block
0x1800092d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800092de  mov     rax, rbx
0x1800092e1  add     rsp, 20h
0x1800092e5  pop     rbx
0x1800092e6  retn
```
