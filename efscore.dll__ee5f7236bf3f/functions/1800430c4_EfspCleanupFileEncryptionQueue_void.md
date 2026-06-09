# EfspCleanupFileEncryptionQueue(void)

- ea: `0x1800430c4`
- end: `0x1800431a9`
- name: `?EfspCleanupFileEncryptionQueue@@YAXXZ`
- size: `229`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180033ab8`

## callees

- `0x1800430c4`
- `0x180043d88`
- `0x180043dc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043103`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180043103`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043154`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043154`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800430de`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800430de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004316e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004316e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004318d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004318d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043180`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800430eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800430eb`

## pseudocode

```c
void EfspCleanupFileEncryptionQueue(void)
{
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY **p_Blink; // rbp
  struct _LIST_ENTRY *v2; // rcx
  struct _LIST_ENTRY **p_Flink; // rbx

  if ( g_hfeQueueServiceEvent )
  {
    WaitForSingleObject(g_hfeQueueServiceEvent, 0xFFFFFFFF);
    CloseHandle(g_hfeQueueServiceEvent);
    g_hfeQueueServiceEvent = 0;
  }
  AcquireSRWLockExclusive(&g_feQueueLock);
  Flink = g_feQueueList.Flink;
  while ( Flink != &g_feQueueList )
  {
    p_Blink = &Flink[-2].Blink;
    Flink = Flink->Flink;
    v2 = p_Blink[1];
    if ( v2 != (struct _LIST_ENTRY *)(p_Blink + 1) )
    {
      do
      {
        p_Flink = &v2->Flink->Flink;
        FreeFEQueueFile(&v2[-3]);
        v2 = (struct _LIST_ENTRY *)p_Flink;
      }
      while ( p_Flink != p_Blink + 1 );
    }
    FreeUserFEQueue(p_Blink);
  }
  ReleaseSRWLockExclusive(&g_feQueueLock);
  if ( g_feQueueLogonDelayTimer )
  {
    SetThreadpoolTimer(g_feQueueLogonDelayTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(g_feQueueLogonDelayTimer, 1);
    CloseThreadpoolTimer(g_feQueueLogonDelayTimer);
    g_feQueueLogonDelayTimer = 0;
  }
}

```

## disassembly

```asm
0x1800430c4  push    rbx
0x1800430c6  push    rbp
0x1800430c7  push    rsi
0x1800430c8  push    rdi
0x1800430c9  push    r14
0x1800430cb  sub     rsp, 20h
0x1800430cf  mov     rcx, cs:?g_hfeQueueServiceEvent@@3PEAXEA; hHandle
0x1800430d6  test    rcx, rcx
0x1800430d9  jz      short loc_1800430FC
0x1800430db  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800430de  call    cs:__imp_WaitForSingleObject
0x1800430e4  mov     rcx, cs:?g_hfeQueueServiceEvent@@3PEAXEA; hObject
0x1800430eb  call    cs:__imp_CloseHandle
0x1800430f1  mov     cs:?g_hfeQueueServiceEvent@@3PEAXEA, 0; void * g_hfeQueueServiceEvent
0x1800430fc  lea     rcx, ?g_feQueueLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180043103  call    cs:__imp_AcquireSRWLockExclusive
0x180043109  mov     rdi, cs:?g_feQueueList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_feQueueList
0x180043110  lea     r14, ?g_feQueueList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_feQueueList
0x180043117  jmp     short loc_180043148
0x180043119  lea     rbp, [rdi-18h]
0x18004311d  mov     rdi, [rdi]
0x180043120  lea     rsi, [rbp+8]
0x180043124  mov     rcx, [rsi]
0x180043127  cmp     rcx, rsi
0x18004312a  jz      short loc_180043140
0x18004312c  mov     rbx, [rcx]
0x18004312f  add     rcx, 0FFFFFFFFFFFFFFD0h; lpMem
0x180043133  call    FreeFEQueueFile
0x180043138  mov     rcx, rbx
0x18004313b  cmp     rbx, rsi
0x18004313e  jnz     short loc_18004312C
0x180043140  mov     rcx, rbp; lpMem
0x180043143  call    FreeUserFEQueue
0x180043148  cmp     rdi, r14
0x18004314b  jnz     short loc_180043119
0x18004314d  lea     rcx, ?g_feQueueLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180043154  call    cs:__imp_ReleaseSRWLockExclusive
0x18004315a  mov     rcx, cs:?g_feQueueLogonDelayTimer@@3PEAU_TP_TIMER@@EA; pti
0x180043161  test    rcx, rcx
0x180043164  jz      short loc_18004319E
0x180043166  xor     r9d, r9d; msWindowLength
0x180043169  xor     r8d, r8d; msPeriod
0x18004316c  xor     edx, edx; pftDueTime
0x18004316e  call    cs:__imp_SetThreadpoolTimer
0x180043174  mov     rcx, cs:?g_feQueueLogonDelayTimer@@3PEAU_TP_TIMER@@EA; pti
0x18004317b  mov     edx, 1; fCancelPendingCallbacks
0x180043180  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180043186  mov     rcx, cs:?g_feQueueLogonDelayTimer@@3PEAU_TP_TIMER@@EA; pti
0x18004318d  call    cs:__imp_CloseThreadpoolTimer
0x180043193  mov     cs:?g_feQueueLogonDelayTimer@@3PEAU_TP_TIMER@@EA, 0; _TP_TIMER * g_feQueueLogonDelayTimer
0x18004319e  add     rsp, 20h
0x1800431a2  pop     r14
0x1800431a4  pop     rdi
0x1800431a5  pop     rsi
0x1800431a6  pop     rbp
0x1800431a7  pop     rbx
0x1800431a8  retn
```
