# SSI_REQUEST::CleanupStoredContext(void)

- ea: `0x180003480`
- end: `0x1800034a8`
- name: `?CleanupStoredContext@SSI_REQUEST@@UEAAXXZ`
- size: `40`
- prototype: `void __fastcall(SSI_REQUEST *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800033c8`
- `0x180003480`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000349c`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000349c`

## pseudocode

```c
void __fastcall SSI_REQUEST::CleanupStoredContext(SSI_REQUEST *this)
{
  if ( this )
  {
    SSI_REQUEST::~SSI_REQUEST(this);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)SSI_REQUEST::sm_pachSsiRequests, this);
  }
}

```

## disassembly

```asm
0x180003480  test    rcx, rcx
0x180003483  jz      short locret_1800034A7
0x180003485  push    rbx
0x180003486  sub     rsp, 20h
0x18000348a  mov     rbx, rcx
0x18000348d  call    ??1SSI_REQUEST@@QEAA@XZ; SSI_REQUEST::~SSI_REQUEST(void)
0x180003492  mov     rcx, cs:?sm_pachSsiRequests@SSI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSI_REQUEST::sm_pachSsiRequests
0x180003499  mov     rdx, rbx
0x18000349c  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800034a2  add     rsp, 20h
0x1800034a6  pop     rbx
0x1800034a7  retn
```
