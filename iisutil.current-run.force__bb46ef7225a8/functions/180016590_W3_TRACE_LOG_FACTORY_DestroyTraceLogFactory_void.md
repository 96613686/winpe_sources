# W3_TRACE_LOG_FACTORY::DestroyTraceLogFactory(void)

- ea: `0x180016590`
- end: `0x180016601`
- name: `?DestroyTraceLogFactory@W3_TRACE_LOG_FACTORY@@QEAAXXZ`
- size: `113`
- prototype: `void __fastcall(W3_TRACE_LOG_FACTORY *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800164a0`

## callees

- `0x180002b60`
- `0x180016590`
- `0x180018438`
- `0x18002a050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800165de`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800165de`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x1800165a8`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x1800165a8`

## pseudocode

```c
void __fastcall W3_TRACE_LOG_FACTORY::DestroyTraceLogFactory(W3_TRACE_LOG_FACTORY *this)
{
  void *v1; // rdx
  bool v3; // zf

  v1 = (void *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    DeleteTimerQueueTimer(0, v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *((_DWORD *)this + 28) )
    W3_TRACE_LOG_FACTORY::TimerCallback(this, 1u);
  v3 = *((_DWORD *)this + 28) == 0;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 4) = 0;
  if ( !v3 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    *((_DWORD *)this + 28) = 0;
  }
  BUFFER::~BUFFER((W3_TRACE_LOG_FACTORY *)((char *)this + 24));
  operator delete(this);
}

```

## disassembly

```asm
0x180016590  push    rbx
0x180016592  sub     rsp, 20h
0x180016596  mov     rdx, [rcx+8]; Timer
0x18001659a  mov     rbx, rcx
0x18001659d  test    rdx, rdx
0x1800165a0  jz      short loc_1800165B6
0x1800165a2  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800165a6  xor     ecx, ecx; TimerQueue
0x1800165a8  call    cs:__imp_DeleteTimerQueueTimer
0x1800165ae  mov     qword ptr [rbx+8], 0
0x1800165b6  cmp     dword ptr [rbx+70h], 0
0x1800165ba  jz      short loc_1800165C6
0x1800165bc  mov     dl, 1; BOOLEAN
0x1800165be  mov     rcx, rbx; PVOID
0x1800165c1  call    ?TimerCallback@W3_TRACE_LOG_FACTORY@@CAXPEAXE@Z; W3_TRACE_LOG_FACTORY::TimerCallback(void *,uchar)
0x1800165c6  cmp     dword ptr [rbx+70h], 0
0x1800165ca  mov     qword ptr [rbx], 0
0x1800165d1  mov     dword ptr [rbx+10h], 0
0x1800165d8  jz      short loc_1800165EB
0x1800165da  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800165de  call    cs:__imp_DeleteCriticalSection
0x1800165e4  mov     dword ptr [rbx+70h], 0
0x1800165eb  lea     rcx, [rbx+18h]; this
0x1800165ef  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800165f4  mov     rcx, rbx; Block
0x1800165f7  add     rsp, 20h
0x1800165fb  pop     rbx
0x1800165fc  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
