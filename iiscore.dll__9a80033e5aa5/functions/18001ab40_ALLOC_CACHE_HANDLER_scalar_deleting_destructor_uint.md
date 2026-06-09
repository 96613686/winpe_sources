# ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)

- ea: `0x18001ab40`
- end: `0x18001ab60`
- name: `??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18001e718`
- `0x18001e7f0`
- `0x18002ce0c`

## callees

- `0x180019598`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001ab49`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001ab49`

## pseudocode

```c
ALLOC_CACHE_HANDLER *__fastcall ALLOC_CACHE_HANDLER::`scalar deleting destructor'(ALLOC_CACHE_HANDLER *this)
{
  ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001ab40  push    rbx
0x18001ab42  sub     rsp, 20h
0x18001ab46  mov     rbx, rcx
0x18001ab49  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18001ab4f  mov     rcx, rbx; Block
0x18001ab52  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ab57  mov     rax, rbx
0x18001ab5a  add     rsp, 20h
0x18001ab5e  pop     rbx
0x18001ab5f  retn
```
