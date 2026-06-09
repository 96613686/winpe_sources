# CERTIFICATE_CONTEXT::`vector deleting destructor'(uint)

- ea: `0x18002c610`
- end: `0x18002c65e`
- name: `??_ECERTIFICATE_CONTEXT@@UEAAPEAXI@Z`
- size: `78`
- prototype: `void *__fastcall(CERTIFICATE_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c610`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002c635`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002c635`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002c64a`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002c64a`

## pseudocode

```c
CERTIFICATE_CONTEXT *__fastcall CERTIFICATE_CONTEXT::`vector deleting destructor'(CERTIFICATE_CONTEXT *this, char a2)
{
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &CERTIFICATE_CONTEXT::`vftable';
  BUFFER::~BUFFER((CERTIFICATE_CONTEXT *)((char *)this + 24));
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free(CERTIFICATE_CONTEXT::sm_pachCertContexts, this);
  return this;
}

```

## disassembly

```asm
0x18002c610  mov     [rsp+arg_0], rbx
0x18002c615  push    rdi
0x18002c616  sub     rsp, 20h
0x18002c61a  lea     rax, ??_7CERTIFICATE_CONTEXT@@6B@; const CERTIFICATE_CONTEXT::`vftable'
0x18002c621  mov     qword ptr [rcx+8], 0
0x18002c629  mov     [rcx], rax
0x18002c62c  mov     rdi, rcx
0x18002c62f  add     rcx, 18h
0x18002c633  mov     ebx, edx
0x18002c635  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002c63b  test    bl, 1
0x18002c63e  jz      short loc_18002C650
0x18002c640  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x18002c647  mov     rdx, rdi
0x18002c64a  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18002c650  mov     rbx, [rsp+28h+arg_0]
0x18002c655  mov     rax, rdi
0x18002c658  add     rsp, 20h
0x18002c65c  pop     rdi
0x18002c65d  retn
```
