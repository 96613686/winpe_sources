# W3_CHILD_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x1800214b0`
- end: `0x180021524`
- name: `??_GW3_CHILD_CONTEXT@@UEAAPEAXI@Z`
- size: `116`
- prototype: `void *__fastcall(W3_CHILD_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000eb20`
- `0x1800214b0`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180021509`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180021509`

## pseudocode

```c
W3_CHILD_CONTEXT *__fastcall W3_CHILD_CONTEXT::`scalar deleting destructor'(W3_CHILD_CONTEXT *this, char a2)
{
  *(_QWORD *)this = &W3_CHILD_CONTEXT::`vftable'{for `IHttpContext4'};
  *((_QWORD *)this + 1) = &W3_CHILD_CONTEXT::`vftable'{for `IHttpTraceContext'};
  *((_QWORD *)this + 2) = &W3_CHILD_CONTEXT::`vftable'{for `IMapHandlerProvider'};
  *((_QWORD *)this + 3) = &W3_CHILD_CONTEXT::`vftable'{for `IModuleAllocator'};
  *((_QWORD *)this + 4) = &W3_CHILD_CONTEXT::`vftable'{for `IAuthenticationProvider'};
  W3_CONTEXT::~W3_CONTEXT(this);
  if ( (a2 & 1) != 0 )
    ALLOC_CACHE_HANDLER::Free(W3_CHILD_CONTEXT::sm_pachCloneContexts, this);
  return this;
}

```

## disassembly

```asm
0x1800214b0  mov     [rsp+arg_0], rbx
0x1800214b5  push    rdi
0x1800214b6  sub     rsp, 20h
0x1800214ba  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIHttpContext4@@@; const W3_CHILD_CONTEXT::`vftable'{for `IHttpContext4'}
0x1800214c1  mov     ebx, edx
0x1800214c3  mov     [rcx], rax
0x1800214c6  mov     rdi, rcx
0x1800214c9  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIHttpTraceContext@@@; const W3_CHILD_CONTEXT::`vftable'{for `IHttpTraceContext'}
0x1800214d0  mov     [rcx+8], rax
0x1800214d4  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIMapHandlerProvider@@@; const W3_CHILD_CONTEXT::`vftable'{for `IMapHandlerProvider'}
0x1800214db  mov     [rcx+10h], rax
0x1800214df  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIModuleAllocator@@@; const W3_CHILD_CONTEXT::`vftable'{for `IModuleAllocator'}
0x1800214e6  mov     [rcx+18h], rax
0x1800214ea  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIAuthenticationProvider@@@; const W3_CHILD_CONTEXT::`vftable'{for `IAuthenticationProvider'}
0x1800214f1  mov     [rcx+20h], rax
0x1800214f5  call    ??1W3_CONTEXT@@QEAA@XZ; W3_CONTEXT::~W3_CONTEXT(void)
0x1800214fa  test    bl, 1
0x1800214fd  jz      short loc_180021515
0x1800214ff  mov     rcx, cs:?sm_pachCloneContexts@W3_CHILD_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_CHILD_CONTEXT::sm_pachCloneContexts
0x180021506  mov     rdx, rdi
0x180021509  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180021510  nop     dword ptr [rax+rax+00h]
0x180021515  mov     rbx, [rsp+28h+arg_0]
0x18002151a  mov     rax, rdi
0x18002151d  add     rsp, 20h
0x180021521  pop     rdi
0x180021522  retn
```
