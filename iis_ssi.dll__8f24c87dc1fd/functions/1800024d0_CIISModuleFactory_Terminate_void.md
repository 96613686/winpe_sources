# CIISModuleFactory::Terminate(void)

- ea: `0x1800024d0`
- end: `0x180002564`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `148`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180001048`
- `0x1800024d0`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800024ec`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180002514`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x1800024ec`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180002514`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180002534`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180002534`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  void *v1; // rbx
  void *v3; // rbx

  v1 = SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles;
  if ( SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles);
    operator delete(v1);
    SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles = 0;
  }
  v3 = SSI_REQUEST::sm_pachSsiRequests;
  if ( SSI_REQUEST::sm_pachSsiRequests )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)SSI_REQUEST::sm_pachSsiRequests);
    operator delete(v3);
    SSI_REQUEST::sm_pachSsiRequests = 0;
  }
  g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x1800024d0  mov     [rsp+arg_0], rbx
0x1800024d5  push    rdi
0x1800024d6  sub     rsp, 20h
0x1800024da  mov     rbx, cs:?sm_pachSsiIncludeFiles@SSI_INCLUDE_FILE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles
0x1800024e1  mov     rdi, rcx
0x1800024e4  test    rbx, rbx
0x1800024e7  jz      short loc_180002505
0x1800024e9  mov     rcx, rbx
0x1800024ec  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x1800024f2  mov     rcx, rbx; Block
0x1800024f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800024fa  mov     cs:?sm_pachSsiIncludeFiles@SSI_INCLUDE_FILE@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * SSI_INCLUDE_FILE::sm_pachSsiIncludeFiles
0x180002505  mov     rbx, cs:?sm_pachSsiRequests@SSI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSI_REQUEST::sm_pachSsiRequests
0x18000250c  test    rbx, rbx
0x18000250f  jz      short loc_18000252D
0x180002511  mov     rcx, rbx
0x180002514  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18000251a  mov     rcx, rbx; Block
0x18000251d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002522  mov     cs:?sm_pachSsiRequests@SSI_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * SSI_REQUEST::sm_pachSsiRequests
0x18000252d  mov     rcx, cs:g_pDebug
0x180002534  call    cs:__imp_PuDeleteDebugPrintsObject
0x18000253a  mov     cs:g_pDebug, rax
0x180002541  test    rdi, rdi
0x180002544  jz      short loc_180002559
0x180002546  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x18000254d  mov     rcx, rdi; Block
0x180002550  mov     [rdi+8], rax
0x180002554  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002559  mov     rbx, [rsp+28h+arg_0]
0x18000255e  add     rsp, 20h
0x180002562  pop     rdi
0x180002563  retn
```
