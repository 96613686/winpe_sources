# ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)

- ea: `0x18001c238`
- end: `0x18001c25f`
- name: `??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z`
- size: `39`
- prototype: `void *__fastcall(ALLOC_CACHE_HANDLER *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800201dc`
- `0x1800202bc`
- `0x18002f794`

## callees

- `0x18001ab70`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001c241`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18001c241`

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
0x18001c238  push    rbx
0x18001c23a  sub     rsp, 20h
0x18001c23e  mov     rbx, rcx
0x18001c241  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18001c248  nop     dword ptr [rax+rax+00h]
0x18001c24d  mov     rcx, rbx; Block
0x18001c250  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c255  mov     rax, rbx
0x18001c258  add     rsp, 20h
0x18001c25c  pop     rbx
0x18001c25d  retn
```
