# COMPRESSION_CONTEXT::CleanupStoredContext(void)

- ea: `0x180002740`
- end: `0x18000280f`
- name: `?CleanupStoredContext@COMPRESSION_CONTEXT@@UEAAXXZ`
- size: `207`
- prototype: `void __fastcall(COMPRESSION_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002740`
- `0x180008010`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000279b`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000279b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027db`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002803`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800027f4`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800027f4`

## pseudocode

```c
void __fastcall COMPRESSION_CONTEXT::CleanupStoredContext(COMPRESSION_CONTEXT *this)
{
  _QWORD **v1; // rbx
  _QWORD *v3; // rdx
  _QWORD *v4; // rax
  ALLOC_CACHE_HANDLER *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  if ( this )
  {
    *(_QWORD *)this = &COMPRESSION_CONTEXT::`vftable';
    v1 = (_QWORD **)((char *)this + 144);
    while ( 1 )
    {
      v3 = *v1;
      if ( *v1 == v1 )
        break;
      if ( (_QWORD **)v3[1] != v1 || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
        __fastfail(3u);
      v5 = (ALLOC_CACHE_HANDLER *)COMPRESSION_BUFFER::allocHandler;
      *v1 = v4;
      v4[1] = v1;
      ALLOC_CACHE_HANDLER::Free(v5, v3 - 500);
    }
    v6 = (void *)*((_QWORD *)this + 16);
    if ( v6 )
    {
      VirtualFree(v6, 0, 0x8000u);
      *((_QWORD *)this + 16) = 0;
    }
    v7 = (void *)*((_QWORD *)this + 15);
    if ( v7 )
    {
      CloseHandle(v7);
      *((_QWORD *)this + 15) = 0;
    }
    if ( *((_QWORD *)this + 4) )
    {
      (*(void (**)(void))(*((_QWORD *)this + 1) + 216LL))();
      *((_QWORD *)this + 4) = 0;
    }
    BUFFER::~BUFFER((COMPRESSION_CONTEXT *)((char *)this + 40));
  }
}

```

## disassembly

```asm
0x180002740  test    rcx, rcx
0x180002743  jz      locret_1800027EB
0x180002749  push    rdi
0x18000274a  sub     rsp, 20h
0x18000274e  lea     rax, ??_7COMPRESSION_CONTEXT@@6B@; const COMPRESSION_CONTEXT::`vftable'
0x180002755  mov     [rsp+28h+arg_0], rbx
0x18000275a  mov     [rcx], rax
0x18000275d  lea     rbx, [rcx+90h]
0x180002764  mov     rdi, rcx
0x180002767  mov     rdx, [rbx]
0x18000276a  cmp     rdx, rbx
0x18000276d  jz      short loc_1800027A3
0x18000276f  cmp     [rdx+8], rbx
0x180002773  jnz     loc_1800057AA
0x180002779  mov     rax, [rdx]
0x18000277c  cmp     [rax+8], rdx
0x180002780  jnz     loc_1800057AA
0x180002786  mov     rcx, cs:?allocHandler@COMPRESSION_BUFFER@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * COMPRESSION_BUFFER::allocHandler
0x18000278d  add     rdx, 0FFFFFFFFFFFFF060h
0x180002794  mov     [rbx], rax
0x180002797  mov     [rax+8], rbx
0x18000279b  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800027a1  jmp     short loc_180002767
0x1800027a3  mov     rcx, [rdi+80h]; lpAddress
0x1800027aa  xor     ebx, ebx
0x1800027ac  test    rcx, rcx
0x1800027af  jnz     short loc_1800027EC
0x1800027b1  mov     rcx, [rdi+78h]; hObject
0x1800027b5  test    rcx, rcx
0x1800027b8  jnz     short loc_180002803
0x1800027ba  mov     rcx, [rdi+20h]
0x1800027be  test    rcx, rcx
0x1800027c1  jz      short loc_1800027D7
0x1800027c3  mov     rax, [rdi+8]
0x1800027c7  mov     rax, [rax+0D8h]
0x1800027ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d3  mov     [rdi+20h], rbx
0x1800027d7  lea     rcx, [rdi+28h]
0x1800027db  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800027e1  mov     rbx, [rsp+28h+arg_0]
0x1800027e6  add     rsp, 20h
0x1800027ea  pop     rdi
0x1800027eb  retn
0x1800027ec  xor     edx, edx; dwSize
0x1800027ee  mov     r8d, 8000h; dwFreeType
0x1800027f4  call    cs:__imp_VirtualFree
0x1800027fa  mov     [rdi+80h], rbx
0x180002801  jmp     short loc_1800027B1
0x180002803  call    cs:__imp_CloseHandle
0x180002809  mov     [rdi+78h], rbx
0x18000280d  jmp     short loc_1800027BA
0x1800057aa  mov     ecx, 3
0x1800057af  int     29h; Win8: RtlFailFast(ecx)
```
