# W3_TRACE_LOG_FACTORY::DestroyTraceLogFactory(void)

- ea: `0x1800171b0`
- end: `0x18001722d`
- name: `?DestroyTraceLogFactory@W3_TRACE_LOG_FACTORY@@QEAAXXZ`
- size: `125`
- prototype: `void __fastcall(W3_TRACE_LOG_FACTORY *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800170b0`

## callees

- `0x1800034f0`
- `0x1800171b0`
- `0x180019270`
- `0x18002bed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017204`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017204`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x1800171c8`
- `api-ms-win-core-threadpool-l1-1-0!DeleteTimerQueueTimer` at `0x1800171c8`

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
0x1800171b0  push    rbx
0x1800171b2  sub     rsp, 20h
0x1800171b6  mov     rdx, [rcx+8]; Timer
0x1800171ba  mov     rbx, rcx
0x1800171bd  test    rdx, rdx
0x1800171c0  jz      short loc_1800171DC
0x1800171c2  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800171c6  xor     ecx, ecx; TimerQueue
0x1800171c8  call    cs:__imp_DeleteTimerQueueTimer
0x1800171cf  nop     dword ptr [rax+rax+00h]
0x1800171d4  mov     qword ptr [rbx+8], 0
0x1800171dc  cmp     dword ptr [rbx+70h], 0
0x1800171e0  jz      short loc_1800171EC
0x1800171e2  mov     dl, 1; BOOLEAN
0x1800171e4  mov     rcx, rbx; PVOID
0x1800171e7  call    ?TimerCallback@W3_TRACE_LOG_FACTORY@@CAXPEAXE@Z; W3_TRACE_LOG_FACTORY::TimerCallback(void *,uchar)
0x1800171ec  cmp     dword ptr [rbx+70h], 0
0x1800171f0  mov     qword ptr [rbx], 0
0x1800171f7  mov     dword ptr [rbx+10h], 0
0x1800171fe  jz      short loc_180017217
0x180017200  lea     rcx, [rbx+48h]; lpCriticalSection
0x180017204  call    cs:__imp_DeleteCriticalSection
0x18001720b  nop     dword ptr [rax+rax+00h]
0x180017210  mov     dword ptr [rbx+70h], 0
0x180017217  lea     rcx, [rbx+18h]; this
0x18001721b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180017220  mov     rcx, rbx; Block
0x180017223  add     rsp, 20h
0x180017227  pop     rbx
0x180017228  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
