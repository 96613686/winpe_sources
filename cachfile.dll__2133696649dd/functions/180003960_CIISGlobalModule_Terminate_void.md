# CIISGlobalModule::Terminate(void)

- ea: `0x180003960`
- end: `0x180003a1f`
- name: `?Terminate@CIISGlobalModule@@UEAAXXZ`
- size: `191`
- prototype: `void __fastcall(CIISGlobalModule *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180002920`
- `0x180003208`
- `0x180003960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800039ce`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800039ce`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800039b9`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1800039b9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000399c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000399c`
- `iisutil!DestroyRefTraceLog` at `0x1800039e0`
- `iisutil!DestroyRefTraceLog` at `0x1800039e0`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x18000397d`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x18000397d`

## pseudocode

```c
void __fastcall CIISGlobalModule::Terminate(CIISGlobalModule *this)
{
  char *v2; // rbx
  void *v3; // rdx
  void *v4; // rcx
  unsigned int v5; // edx

  if ( g_pFileCache )
  {
    TREE_HASH_TABLE::Clear((TREE_HASH_TABLE *)g_pFileCache);
    v2 = (char *)g_pFileCache;
    v3 = (void *)*((_QWORD *)g_pFileCache + 17);
    if ( v3 )
    {
      DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)v2 + 17) = 0;
    }
    v4 = (void *)*((_QWORD *)v2 + 16);
    if ( v4 )
    {
      HeapDestroy(v4);
      *((_QWORD *)v2 + 16) = 0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 72));
    if ( g_pTraceLog )
    {
      DestroyRefTraceLog();
      g_pTraceLog = 0;
    }
    if ( g_pFileCache )
      FILE_CACHE::`scalar deleting destructor'((FILE_CACHE *)g_pFileCache, v5);
    g_pFileCache = 0;
  }
  operator delete(this);
}

```

## disassembly

```asm
0x180003960  mov     [rsp+arg_0], rbx
0x180003965  push    rdi
0x180003966  sub     rsp, 20h
0x18000396a  mov     rdi, rcx
0x18000396d  mov     rcx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x180003974  test    rcx, rcx
0x180003977  jz      loc_180003A0D
0x18000397d  call    cs:__imp_?Clear@TREE_HASH_TABLE@@QEAAXXZ; TREE_HASH_TABLE::Clear(void)
0x180003983  mov     rbx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x18000398a  mov     rdx, [rbx+88h]; Timer
0x180003991  test    rdx, rdx
0x180003994  jz      short loc_1800039AD
0x180003996  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000399a  xor     ecx, ecx; TimerQueue
0x18000399c  call    cs:__imp_DeleteTimerQueueTimer
0x1800039a2  mov     qword ptr [rbx+88h], 0
0x1800039ad  mov     rcx, [rbx+80h]; hHeap
0x1800039b4  test    rcx, rcx
0x1800039b7  jz      short loc_1800039CA
0x1800039b9  call    cs:__imp_HeapDestroy
0x1800039bf  mov     qword ptr [rbx+80h], 0
0x1800039ca  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800039ce  call    cs:__imp_DeleteCriticalSection
0x1800039d4  mov     rcx, cs:?g_pTraceLog@@3PEAU_TRACE_LOG@@EA; _TRACE_LOG * g_pTraceLog
0x1800039db  test    rcx, rcx
0x1800039de  jz      short loc_1800039F1
0x1800039e0  call    cs:__imp_DestroyRefTraceLog
0x1800039e6  mov     cs:?g_pTraceLog@@3PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * g_pTraceLog
0x1800039f1  mov     rcx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; this
0x1800039f8  test    rcx, rcx
0x1800039fb  jz      short loc_180003A02
0x1800039fd  call    ??_GFILE_CACHE@@QEAAPEAXI@Z; FILE_CACHE::`scalar deleting destructor'(uint)
0x180003a02  mov     cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA, 0; FILE_CACHE * g_pFileCache
0x180003a0d  mov     rcx, rdi; Block
0x180003a10  mov     rbx, [rsp+28h+arg_0]
0x180003a15  add     rsp, 20h
0x180003a19  pop     rdi
0x180003a1a  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
