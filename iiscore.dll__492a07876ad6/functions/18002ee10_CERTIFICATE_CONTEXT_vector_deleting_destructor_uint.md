# CERTIFICATE_CONTEXT::`vector deleting destructor'(uint)

- ea: `0x18002ee10`
- end: `0x18002ee6b`
- name: `??_ECERTIFICATE_CONTEXT@@UEAAPEAXI@Z`
- size: `91`
- prototype: `void *__fastcall(CERTIFICATE_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002ee10`

## import_xrefs

- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002ee35`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002ee35`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002ee50`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002ee50`

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
0x18002ee10  mov     [rsp+arg_0], rbx
0x18002ee15  push    rdi
0x18002ee16  sub     rsp, 20h
0x18002ee1a  lea     rax, ??_7CERTIFICATE_CONTEXT@@6B@; const CERTIFICATE_CONTEXT::`vftable'
0x18002ee21  mov     qword ptr [rcx+8], 0
0x18002ee29  mov     [rcx], rax
0x18002ee2c  mov     rdi, rcx
0x18002ee2f  add     rcx, 18h
0x18002ee33  mov     ebx, edx
0x18002ee35  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002ee3c  nop     dword ptr [rax+rax+00h]
0x18002ee41  test    bl, 1
0x18002ee44  jz      short loc_18002EE5C
0x18002ee46  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x18002ee4d  mov     rdx, rdi
0x18002ee50  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18002ee57  nop     dword ptr [rax+rax+00h]
0x18002ee5c  mov     rbx, [rsp+28h+arg_0]
0x18002ee61  mov     rax, rdi
0x18002ee64  add     rsp, 20h
0x18002ee68  pop     rdi
0x18002ee69  retn
```
