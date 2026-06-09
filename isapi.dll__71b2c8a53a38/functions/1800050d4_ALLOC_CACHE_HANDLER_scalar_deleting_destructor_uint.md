# ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)

- ea: `0x1800050d4`
- end: `0x1800050f4`
- name: `??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180005c44`
- `0x18000c5e8`

## callees

- `0x180001060`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800050dd`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800050dd`

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
0x1800050d4  push    rbx
0x1800050d6  sub     rsp, 20h
0x1800050da  mov     rbx, rcx
0x1800050dd  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x1800050e3  mov     rcx, rbx; Block
0x1800050e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800050eb  mov     rax, rbx
0x1800050ee  add     rsp, 20h
0x1800050f2  pop     rbx
0x1800050f3  retn
```
