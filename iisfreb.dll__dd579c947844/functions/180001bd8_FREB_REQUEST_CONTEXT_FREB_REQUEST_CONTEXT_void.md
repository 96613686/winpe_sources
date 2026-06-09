# FREB_REQUEST_CONTEXT::~FREB_REQUEST_CONTEXT(void)

- ea: `0x180001bd8`
- end: `0x180001cf1`
- name: `??1FREB_REQUEST_CONTEXT@@AEAA@XZ`
- size: `281`
- prototype: `void __fastcall(FREB_REQUEST_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ec0`

## callees

- `0x180001bd8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001cc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001cc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001cb5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001c96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001ca3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001c96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001ca3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c5b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c5b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c1d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001c1d`

## pseudocode

```c
void __fastcall FREB_REQUEST_CONTEXT::~FREB_REQUEST_CONTEXT(FREB_REQUEST_CONTEXT *this)
{
  bool v1; // zf
  char *v3; // rdi
  _QWORD *v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rdx
  void (__fastcall ***v7)(_QWORD); // rcx
  void *v8; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *((_QWORD *)this + 2) == 0;
  *(_QWORD *)this = &FREB_REQUEST_CONTEXT::`vftable'{for `IHttpStoredContext'};
  *((_DWORD *)this + 10) = 1718773090;
  *((_QWORD *)this + 1) = &FREB_REQUEST_CONTEXT::`vftable'{for `FREB_TIMEOUT_MONITOR_ENTRY'};
  if ( !v1 )
  {
    v3 = (char *)FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor + 8 * *((unsigned int *)this + 9);
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v3 + 4800));
    v4 = (_QWORD *)((char *)this + 16);
    v5 = *((_QWORD *)this + 2);
    if ( v5 )
    {
      if ( *(_QWORD **)(v5 + 8) != v4 || (v6 = (_QWORD *)*((_QWORD *)this + 3), (_QWORD *)*v6 != v4) )
        __fastfail(3u);
      *v6 = v5;
      *(_QWORD *)(v5 + 8) = v6;
      *v4 = 0;
    }
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v3 + 4800));
  }
  if ( *((_QWORD *)this + 9) )
    *((_QWORD *)this + 9) = 0;
  if ( *((_DWORD *)this + 16) )
  {
    v7 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 7);
    if ( v7 )
    {
      (**v7)(v7);
      *((_QWORD *)this + 7) = 0;
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  v8 = (void *)*((_QWORD *)this + 20);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    *((_QWORD *)this + 20) = 0;
  }
  *((_QWORD *)this + 1) = &FREB_TIMEOUT_MONITOR_ENTRY::`vftable';
}

```

## disassembly

```asm
0x180001bd8  mov     [rsp+arg_0], rbx
0x180001bdd  push    rdi
0x180001bde  sub     rsp, 20h
0x180001be2  cmp     qword ptr [rcx+10h], 0
0x180001be7  lea     rax, ??_7FREB_REQUEST_CONTEXT@@6BIHttpStoredContext@@@; const FREB_REQUEST_CONTEXT::`vftable'{for `IHttpStoredContext'}
0x180001bee  mov     [rcx], rax
0x180001bf1  mov     rbx, rcx
0x180001bf4  lea     rax, ??_7FREB_REQUEST_CONTEXT@@6BFREB_TIMEOUT_MONITOR_ENTRY@@@; const FREB_REQUEST_CONTEXT::`vftable'{for `FREB_TIMEOUT_MONITOR_ENTRY'}
0x180001bfb  mov     dword ptr [rcx+28h], 66726562h
0x180001c02  mov     [rcx+8], rax
0x180001c06  jz      short loc_180001C61
0x180001c08  mov     edx, [rcx+24h]
0x180001c0b  mov     rax, cs:?sm_pTimeoutMonitor@FREB_REQUEST_CONTEXT@@0PEAVFREB_TIMEOUT_MONITOR_LIST@@EA; FREB_TIMEOUT_MONITOR_LIST * FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor
0x180001c12  lea     rdi, [rax+rdx*8]
0x180001c16  lea     rcx, [rdi+12C0h]
0x180001c1d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180001c23  lea     rax, [rbx+10h]
0x180001c27  mov     rcx, [rax]
0x180001c2a  test    rcx, rcx
0x180001c2d  jz      short loc_180001C54
0x180001c2f  cmp     [rcx+8], rax
0x180001c33  jnz     loc_180001CEA
0x180001c39  mov     rdx, [rax+8]
0x180001c3d  cmp     [rdx], rax
0x180001c40  jnz     loc_180001CEA
0x180001c46  mov     [rdx], rcx
0x180001c49  mov     [rcx+8], rdx
0x180001c4d  mov     qword ptr [rax], 0
0x180001c54  lea     rcx, [rdi+12C0h]
0x180001c5b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001c61  cmp     qword ptr [rbx+48h], 0
0x180001c66  jz      short loc_180001C70
0x180001c68  mov     qword ptr [rbx+48h], 0
0x180001c70  cmp     dword ptr [rbx+40h], 0
0x180001c74  jz      short loc_180001C92
0x180001c76  mov     rcx, [rbx+38h]
0x180001c7a  test    rcx, rcx
0x180001c7d  jz      short loc_180001C92
0x180001c7f  mov     rax, [rcx]
0x180001c82  mov     rax, [rax]
0x180001c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c8a  mov     qword ptr [rbx+38h], 0
0x180001c92  lea     rcx, [rbx+70h]; lpCriticalSection
0x180001c96  call    cs:__imp_DeleteCriticalSection
0x180001c9c  lea     rcx, [rbx+110h]; lpCriticalSection
0x180001ca3  call    cs:__imp_DeleteCriticalSection
0x180001ca9  mov     rdi, [rbx+0A0h]
0x180001cb0  test    rdi, rdi
0x180001cb3  jz      short loc_180001CD4
0x180001cb5  call    cs:__imp_GetProcessHeap
0x180001cbb  mov     r8, rdi; lpMem
0x180001cbe  xor     edx, edx; dwFlags
0x180001cc0  mov     rcx, rax; hHeap
0x180001cc3  call    cs:__imp_HeapFree
0x180001cc9  mov     qword ptr [rbx+0A0h], 0
0x180001cd4  lea     rax, ??_7FREB_TIMEOUT_MONITOR_ENTRY@@6B@; const FREB_TIMEOUT_MONITOR_ENTRY::`vftable'
0x180001cdb  mov     [rbx+8], rax
0x180001cdf  mov     rbx, [rsp+28h+arg_0]
0x180001ce4  add     rsp, 20h
0x180001ce8  pop     rdi
0x180001ce9  retn
0x180001cea  mov     ecx, 3
0x180001cef  int     29h; Win8: RtlFailFast(ecx)
```
