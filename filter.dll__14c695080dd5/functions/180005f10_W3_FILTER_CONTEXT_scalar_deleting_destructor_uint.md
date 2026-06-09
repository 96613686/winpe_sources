# W3_FILTER_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x180005f10`
- end: `0x180005f50`
- name: `??_GW3_FILTER_CONTEXT@@EEAAPEAXI@Z`
- size: `64`
- prototype: `void *__fastcall(W3_FILTER_CONTEXT *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005f10`
- `0x180005f60`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180005f48`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180005f48`

## pseudocode

```c
W3_FILTER_CONTEXT *__fastcall W3_FILTER_CONTEXT::`scalar deleting destructor'(W3_FILTER_CONTEXT *this, char a2)
{
  W3_FILTER_CONTEXT::~W3_FILTER_CONTEXT(this);
  if ( (a2 & 1) != 0 && !*((_DWORD *)this + 4) )
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)W3_FILTER_CONTEXT::sm_pachFilterContexts, this);
  return this;
}

```

## disassembly

```asm
0x180005f10  mov     [rsp+arg_0], rbx
0x180005f15  push    rdi
0x180005f16  sub     rsp, 20h
0x180005f1a  mov     edi, edx
0x180005f1c  mov     rbx, rcx
0x180005f1f  call    ??1W3_FILTER_CONTEXT@@EEAA@XZ; W3_FILTER_CONTEXT::~W3_FILTER_CONTEXT(void)
0x180005f24  test    dil, 1
0x180005f28  jz      short loc_180005F30
0x180005f2a  cmp     dword ptr [rbx+10h], 0
0x180005f2e  jz      short loc_180005F3E
0x180005f30  mov     rax, rbx
0x180005f33  mov     rbx, [rsp+28h+arg_0]
0x180005f38  add     rsp, 20h
0x180005f3c  pop     rdi
0x180005f3d  retn
0x180005f3e  mov     rcx, cs:?sm_pachFilterContexts@W3_FILTER_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_FILTER_CONTEXT::sm_pachFilterContexts
0x180005f45  mov     rdx, rbx
0x180005f48  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180005f4e  jmp     short loc_180005F30
```
