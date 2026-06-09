# NlQueueWorkItem(_WORKER_ITEM *,int,int)

- ea: `0x1800090c0`
- end: `0x1800095bc`
- name: `?NlQueueWorkItem@@YAHPEAU_WORKER_ITEM@@HH@Z`
- size: `1276`
- prototype: `__int64 __fastcall(struct _WORKER_ITEM *, int, int)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005f84`
- `0x180022a8c`
- `0x180028c70`
- `0x1800690ac`
- `0x180069290`
- `0x1800747cc`
- `0x180075b60`

## callees

- `0x180007518`
- `0x1800090c0`
- `0x1800167c4`
- `0x180016900`
- `0x1800901ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800091f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800091f4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009120`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009120`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009166`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009595`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800902d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009166`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009595`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800902d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009531`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800094f0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800094f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009230`
- `ntdll!RtlLeaveCriticalSection` at `0x180009560`
- `ntdll!RtlLeaveCriticalSection` at `0x1800902a1`
- `ntdll!RtlLeaveCriticalSection` at `0x180009560`
- `ntdll!RtlLeaveCriticalSection` at `0x1800902a1`
- `ntdll!RtlEnterCriticalSection` at `0x18000918f`
- `ntdll!RtlEnterCriticalSection` at `0x18000918f`

## string_xrefs

- `0x1800091d8`: `%lx: 0x%p: Ditching worker thread\n`
- `0x180009217`: `%lx: worker thread handle cannot be awaited. %ld 0x%p\n`
- `0x18000925f`: `%lx: worker thread handle cannot be closed. %ld 0x%p\n`
- `0x180009515`: `%lx: 0x%p: %lx: Starting worker thread\n`
- `0x180009540`: `NlQueueWorkItem: Cannot create thread %ld\n`

## pseudocode

```c
__int64 __fastcall NlQueueWorkItem(struct _WORKER_ITEM *a1, int a2, int a3)
{
  AXB *v5; // rbx
  AXB *v6; // rbx
  int v7; // r13d
  __int64 v8; // r8
  __int64 i; // r14
  DWORD v10; // eax
  void * near *v11; // rbx
  DWORD LastError; // eax
  char v13; // al
  unsigned int v14; // eax
  _QWORD *v15; // rcx
  _QWORD *v16; // rcx
  __int64 j; // rbx
  __int64 v18; // rdi
  const char *v19; // r8
  __int64 v20; // rcx
  struct _WORKER_ITEM **v21; // rax
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v23; // rcx
  void **v24; // rax
  DWORD v25; // eax
  AXB *v26; // rbx
  __int64 v27; // [rsp+0h] [rbp-68h] BYREF
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-48h]
  int v29; // [rsp+30h] [rbp-38h]
  int v30; // [rsp+34h] [rbp-34h]
  __int64 *v31; // [rsp+38h] [rbp-30h]
  DWORD ThreadId; // [rsp+88h] [rbp+20h] BYREF

  v31 = &v27;
  if ( !NlWorkerInitialized )
  {
    NlPrintRoutine(0x100u, L"NlQueueWorkItem when worker not initialized\n");
    return 0;
  }
  v5 = NlOutstandingTasks;
  SPINLOCK::Acquire((AXB *)((char *)NlOutstandingTasks + 16));
  if ( !_InterlockedIncrement((volatile signed __int32 *)v5) )
    ResetEvent(*((HANDLE *)v5 + 1));
  SPINLOCK::Release((AXB *)((char *)v5 + 16));
  if ( _InterlockedCompareExchange((volatile signed __int32 *)NlTaskGate, 0, 0) )
  {
    v6 = NlOutstandingTasks;
    SPINLOCK::Acquire((AXB *)((char *)NlOutstandingTasks + 16));
    if ( _InterlockedDecrement((volatile signed __int32 *)v6) < 0 )
      SetEvent(*((HANDLE *)v6 + 1));
    SPINLOCK::Release((AXB *)((char *)v6 + 16));
    return 0;
  }
  v7 = 0;
  v30 = 0;
  RtlEnterCriticalSection(&NlWorkerCritSect);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v29 = i;
    if ( (unsigned int)i >= 5 )
      break;
    if ( (&NlThreadArray)[i] && *((_BYTE *)&NlThreadExitted + i) )
    {
      NlPrintRoutine(0x10000u, L"%lx: 0x%p: Ditching worker thread\n", (unsigned int)i);
      v10 = WaitForSingleObject((&NlThreadArray)[i], 0xFFFFFFFF);
      if ( v10 )
        NlPrintRoutine(
          0x100u,
          L"%lx: worker thread handle cannot be awaited. %ld 0x%p\n",
          (unsigned int)i,
          v10,
          (&NlThreadArray)[i]);
      if ( !CloseHandle((&NlThreadArray)[i]) )
      {
        v11 = (&NlThreadArray)[i];
        LastError = GetLastError();
        NlPrintRoutine(
          0x100u,
          L"%lx: worker thread handle cannot be closed. %ld 0x%p\n",
          (unsigned int)i,
          LastError,
          v11);
      }
      (&NlThreadArray)[i] = 0;
      *((_BYTE *)&NlThreadExitted + i) = 0;
    }
  }
  v13 = *((_BYTE *)a1 + 32);
  if ( a2 )
  {
    if ( v13 )
    {
      v14 = NlNumberOfCreatedWorkerThreads;
      if ( NlNumberOfCreatedWorkerThreads )
      {
        local_unwind_0(v31, &loc_1800092C6);
        return 1;
      }
      goto LABEL_31;
    }
    NlPrintRoutine(0x10000u, L"Inserting work item 0x%p (0x%p)\n", a1, *((_QWORD *)a1 + 2));
    if ( a3 )
    {
      v15 = (_QWORD *)qword_1800F8F90;
      if ( *(struct _LIST_ENTRY **)qword_1800F8F90 == &NlWorkerHighQueueHead )
      {
        *(_QWORD *)a1 = &NlWorkerHighQueueHead;
        *((_QWORD *)a1 + 1) = v15;
        *v15 = a1;
        qword_1800F8F90 = (__int64)a1;
LABEL_30:
        *((_BYTE *)a1 + 32) = 1;
        v7 = 1;
        v30 = 1;
        v14 = NlNumberOfCreatedWorkerThreads;
        goto LABEL_31;
      }
    }
    else
    {
      v16 = (_QWORD *)qword_1800F8FA0;
      if ( *(struct _LIST_ENTRY **)qword_1800F8FA0 == &NlWorkerQueueHead )
      {
        *(_QWORD *)a1 = &NlWorkerQueueHead;
        *((_QWORD *)a1 + 1) = v16;
        *v16 = a1;
        qword_1800F8FA0 = (__int64)a1;
        goto LABEL_30;
      }
    }
LABEL_58:
    __fastfail(3u);
  }
  if ( !v13 )
  {
    local_unwind_0(v31, &loc_1800093AC);
    return 1;
  }
  v19 = "high";
  if ( !a3 )
    v19 = "low";
  NlPrintRoutine(0x10000u, L"Boosting %hs priority work item 0x%p (0x%p)\n", v19, a1, *((_QWORD *)a1 + 2));
  v20 = *(_QWORD *)a1;
  if ( *(struct _WORKER_ITEM **)(*(_QWORD *)a1 + 8LL) != a1 )
    goto LABEL_58;
  v21 = (struct _WORKER_ITEM **)*((_QWORD *)a1 + 1);
  if ( *v21 != a1 )
    goto LABEL_58;
  *v21 = (struct _WORKER_ITEM *)v20;
  *(_QWORD *)(v20 + 8) = v21;
  if ( a3 )
  {
    Flink = NlWorkerHighQueueHead.Flink;
    if ( NlWorkerHighQueueHead.Flink->Blink != &NlWorkerHighQueueHead )
      goto LABEL_58;
    *(_QWORD *)a1 = NlWorkerHighQueueHead.Flink;
    *((_QWORD *)a1 + 1) = &NlWorkerHighQueueHead;
    Flink->Blink = (struct _LIST_ENTRY *)a1;
    NlWorkerHighQueueHead.Flink = (struct _LIST_ENTRY *)a1;
  }
  else
  {
    v23 = NlWorkerQueueHead.Flink;
    if ( NlWorkerQueueHead.Flink->Blink != &NlWorkerQueueHead )
      goto LABEL_58;
    *(_QWORD *)a1 = NlWorkerQueueHead.Flink;
    *((_QWORD *)a1 + 1) = &NlWorkerQueueHead;
    v23->Blink = (struct _LIST_ENTRY *)a1;
    NlWorkerQueueHead.Flink = (struct _LIST_ENTRY *)a1;
  }
  v14 = NlNumberOfCreatedWorkerThreads;
  if ( NlNumberOfCreatedWorkerThreads )
  {
    local_unwind_0(v31, &loc_18000948C);
    return 1;
  }
LABEL_31:
  if ( v14 < 5 )
  {
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      v29 = j;
      v18 = j;
      if ( (unsigned int)j >= 5 )
      {
        NlPrintRoutine(0x100u, L"NlQueueWorkItem: Internal Error\n", v8, (unsigned int)j);
        local_unwind_0(v31, &loc_1800094BE);
        return 0;
      }
      if ( !(&NlThreadArray)[v18] )
        break;
    }
    ThreadId = 0;
    v24 = (void **)CreateThread(0, 0, NlWorkerThread, (LPVOID)(unsigned int)j, 0, &ThreadId);
    (&NlThreadArray)[v18] = v24;
    dwCreationFlags[0] = ThreadId;
    NlPrintRoutine(
      0x10000u,
      L"%lx: 0x%p: %lx: Starting worker thread\n",
      (unsigned int)j,
      v24,
      *(_QWORD *)dwCreationFlags);
    if ( (&NlThreadArray)[v18] )
    {
      ++NlNumberOfCreatedWorkerThreads;
    }
    else
    {
      v25 = GetLastError();
      NlPrintRoutine(0x100u, L"NlQueueWorkItem: Cannot create thread %ld\n", v25);
    }
  }
  RtlLeaveCriticalSection(&NlWorkerCritSect);
  if ( v7 )
    return 1;
  v26 = NlOutstandingTasks;
  SPINLOCK::Acquire((AXB *)((char *)NlOutstandingTasks + 16));
  if ( _InterlockedDecrement((volatile signed __int32 *)v26) < 0 )
    SetEvent(*((HANDLE *)v26 + 1));
  SPINLOCK::Release((AXB *)((char *)v26 + 16));
  return 1;
}

```

## disassembly

```asm
0x1800090c0  mov     [rsp+arg_10], r8d
0x1800090c5  mov     [rsp+arg_8], edx
0x1800090c9  push    rbx
0x1800090ca  push    rdi
0x1800090cb  push    r13
0x1800090cd  push    r14
0x1800090cf  push    r15
0x1800090d1  sub     rsp, 40h
0x1800090d5  mov     [rsp+68h+var_30], rsp
0x1800090da  mov     rdi, rcx
0x1800090dd  cmp     cs:?NlWorkerInitialized@@3EA, 0; uchar NlWorkerInitialized
0x1800090e4  jnz     short loc_180009107
0x1800090e6  lea     rdx, aNlqueueworkite_1; "NlQueueWorkItem when worker not initial"...
0x1800090ed  mov     ecx, 100h; unsigned int
0x1800090f2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800090f7  xor     eax, eax
0x1800090f9  add     rsp, 40h
0x1800090fd  pop     r15
0x1800090ff  pop     r14
0x180009101  pop     r13
0x180009103  pop     rdi
0x180009104  pop     rbx
0x180009105  retn
0x180009107  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x18000910e  lea     rcx, [rbx+10h]; this
0x180009112  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x180009117  lock inc dword ptr [rbx]
0x18000911a  jnz     short loc_18000912C
0x18000911c  mov     rcx, [rbx+8]; hEvent
0x180009120  call    cs:__imp_ResetEvent
0x180009127  nop     dword ptr [rax+rax+00h]
0x18000912c  lea     rcx, [rbx+10h]; this
0x180009130  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x180009135  mov     rdx, cs:?NlTaskGate@@3PEAXEA; void * NlTaskGate
0x18000913c  xor     ecx, ecx
0x18000913e  xor     eax, eax
0x180009140  lock cmpxchg [rdx], ecx
0x180009144  jz      short loc_180009180
0x180009146  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x18000914d  lea     rcx, [rbx+10h]; this
0x180009151  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x180009156  or      eax, 0FFFFFFFFh
0x180009159  lock xadd [rbx], eax
0x18000915d  cmp     eax, 1
0x180009160  jns     short loc_180009172
0x180009162  mov     rcx, [rbx+8]; hEvent
0x180009166  call    cs:__imp_SetEvent
0x18000916d  nop     dword ptr [rax+rax+00h]
0x180009172  lea     rcx, [rbx+10h]; this
0x180009176  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x18000917b  jmp     loc_1800090F7
0x180009180  xor     r13d, r13d
0x180009183  mov     [rsp+68h+var_34], r13d
0x180009188  lea     rcx, ?NlWorkerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000918f  call    cs:__imp_RtlEnterCriticalSection
0x180009196  nop     dword ptr [rax+rax+00h]
0x18000919b  nop
0x18000919c  xor     r14d, r14d
0x18000919f  lea     rbx, __ImageBase
0x1800091a6  mov     [rsp+68h+var_38], r14d
0x1800091ab  cmp     r14d, 5
0x1800091af  jnb     loc_180009294
0x1800091b5  mov     r9, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; void * near * NlThreadArray ...
0x1800091bd  test    r9, r9
0x1800091c0  jz      loc_18000928C
0x1800091c6  cmp     byte ptr [r14+rbx+0F8960h], 0
0x1800091cf  jz      loc_18000928C
0x1800091d5  mov     r8d, r14d
0x1800091d8  lea     rdx, aLx0xPDitchingW; "%lx: 0x%p: Ditching worker thread\n"
0x1800091df  mov     ecx, 10000h; unsigned int
0x1800091e4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800091e9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800091ec  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; hHandle
0x1800091f4  call    cs:__imp_WaitForSingleObject
0x1800091fb  nop     dword ptr [rax+rax+00h]
0x180009200  test    eax, eax
0x180009202  jz      short loc_180009228
0x180009204  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; void * near * NlThreadArray ...
0x18000920c  mov     qword ptr [rsp+68h+dwCreationFlags], rcx
0x180009211  mov     r9d, eax
0x180009214  mov     r8d, r14d
0x180009217  lea     rdx, aLxWorkerThread_1; "%lx: worker thread handle cannot be awa"...
0x18000921e  mov     ecx, 100h; unsigned int
0x180009223  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180009228  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; hObject
0x180009230  call    cs:__imp_CloseHandle
0x180009237  nop     dword ptr [rax+rax+00h]
0x18000923c  test    eax, eax
0x18000923e  jnz     short loc_180009277
0x180009240  mov     rbx, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; void * near * NlThreadArray ...
0x180009248  call    cs:__imp_GetLastError
0x18000924f  nop     dword ptr [rax+rax+00h]
0x180009254  mov     qword ptr [rsp+68h+dwCreationFlags], rbx
0x180009259  mov     r9d, eax
0x18000925c  mov     r8d, r14d
0x18000925f  lea     rdx, aLxWorkerThread; "%lx: worker thread handle cannot be clo"...
0x180009266  mov     ecx, 100h; unsigned int
0x18000926b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180009270  lea     rbx, __ImageBase
0x180009277  mov     qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8], 0; void * near * NlThreadArray ...
0x180009283  mov     byte ptr [r14+rbx+0F8960h], 0
0x18000928c  inc     r14d
0x18000928f  jmp     loc_1800091A6
0x180009294  mov     al, [rdi+20h]
0x180009297  cmp     [rsp+68h+arg_8], 0
0x18000929c  jz      loc_180009396
0x1800092a2  test    al, al
0x1800092a4  jz      short loc_1800092D0
0x1800092a6  mov     eax, cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x1800092ac  test    eax, eax
0x1800092ae  jz      loc_180009359
0x1800092b4  lea     rdx, loc_1800092C6
0x1800092bb  mov     rcx, [rsp+68h+var_30]
0x1800092c0  call    _local_unwind_0
0x1800092c5  nop
0x1800092c6  mov     eax, 1
0x1800092cb  jmp     loc_1800090F9
0x1800092d0  mov     r9, [rdi+10h]
0x1800092d4  mov     r8, rdi
0x1800092d7  lea     rdx, aInsertingWorkI; "Inserting work item 0x%p (0x%p)\n"
0x1800092de  mov     ecx, 10000h; unsigned int
0x1800092e3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800092e8  cmp     [rsp+68h+arg_10], 0
0x1800092f0  jz      short loc_18000931C
0x1800092f2  mov     rcx, cs:qword_1800F8F90
0x1800092f9  lea     rax, ?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x180009300  cmp     [rcx], rax
0x180009303  jnz     loc_1800095B4
0x180009309  mov     [rdi], rax
0x18000930c  mov     [rdi+8], rcx
0x180009310  mov     [rcx], rdi
0x180009313  mov     cs:qword_1800F8F90, rdi
0x18000931a  jmp     short loc_180009344
0x18000931c  mov     rcx, cs:qword_1800F8FA0
0x180009323  lea     rax, ?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x18000932a  cmp     [rcx], rax
0x18000932d  jnz     loc_1800095B4
0x180009333  mov     [rdi], rax
0x180009336  mov     [rdi+8], rcx
0x18000933a  mov     [rcx], rdi
0x18000933d  mov     cs:qword_1800F8FA0, rdi
0x180009344  mov     byte ptr [rdi+20h], 1
0x180009348  mov     r13d, 1
0x18000934e  mov     [rsp+68h+var_34], r13d
0x180009353  mov     eax, cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x180009359  cmp     eax, 5
0x18000935c  jnb     loc_180009559
0x180009362  xor     ebx, ebx
0x180009364  lea     r14, __ImageBase
0x18000936b  mov     [rsp+68h+var_38], ebx
0x18000936f  mov     r9d, ebx; lpParameter
0x180009372  lea     rdi, ds:0[rbx*8]
0x18000937a  cmp     ebx, 5
0x18000937d  jnb     loc_18000949B
0x180009383  cmp     qword ptr [rdi+r14+0F8968h], 0
0x18000938c  jz      loc_180009496
0x180009392  inc     ebx
0x180009394  jmp     short loc_18000936B
0x180009396  test    al, al
0x180009398  jnz     short loc_1800093B6
0x18000939a  lea     rdx, loc_1800093AC
0x1800093a1  mov     rcx, [rsp+68h+var_30]
0x1800093a6  call    _local_unwind_0
0x1800093ab  nop
0x1800093ac  mov     eax, 1
0x1800093b1  jmp     loc_1800090F9
0x1800093b6  lea     rax, aLow; "low"
0x1800093bd  lea     r8, aHigh; "high"
0x1800093c4  mov     r15d, [rsp+68h+arg_10]
0x1800093cc  test    r15d, r15d
0x1800093cf  cmovz   r8, rax
0x1800093d3  mov     rax, [rdi+10h]
0x1800093d7  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x1800093dc  mov     r9, rdi
0x1800093df  lea     rdx, aBoostingHsPrio; "Boosting %hs priority work item 0x%p (0"...
0x1800093e6  mov     ecx, 10000h; unsigned int
0x1800093eb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800093f0  mov     rcx, [rdi]
0x1800093f3  cmp     [rcx+8], rdi
0x1800093f7  jnz     loc_1800095B4
0x1800093fd  mov     rax, [rdi+8]
0x180009401  cmp     [rax], rdi
0x180009404  jnz     loc_1800095B4
0x18000940a  mov     [rax], rcx
0x18000940d  mov     [rcx+8], rax
0x180009411  test    r15d, r15d
0x180009414  jz      short loc_180009442
0x180009416  mov     rcx, cs:?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x18000941d  lea     rax, ?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x180009424  cmp     [rcx+8], rax
0x180009428  jnz     loc_1800095B4
0x18000942e  mov     [rdi], rcx
0x180009431  mov     [rdi+8], rax
0x180009435  mov     [rcx+8], rdi
0x180009439  mov     cs:?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY NlWorkerHighQueueHead
0x180009440  jmp     short loc_18000946C
0x180009442  mov     rcx, cs:?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x180009449  lea     rax, ?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x180009450  cmp     [rcx+8], rax
0x180009454  jnz     loc_1800095B4
0x18000945a  mov     [rdi], rcx
0x18000945d  mov     [rdi+8], rax
0x180009461  mov     [rcx+8], rdi
0x180009465  mov     cs:?NlWorkerQueueHead@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY NlWorkerQueueHead
0x18000946c  mov     eax, cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x180009472  test    eax, eax
0x180009474  jz      loc_180009359
0x18000947a  lea     rdx, loc_18000948C
0x180009481  mov     rcx, [rsp+68h+var_30]
0x180009486  call    _local_unwind_0
0x18000948b  nop
0x18000948c  mov     eax, 1
0x180009491  jmp     loc_1800090F9
0x180009496  cmp     ebx, 5
0x180009499  jb      short loc_1800094C5
0x18000949b  lea     rdx, aNlqueueworkite_2; "NlQueueWorkItem: Internal Error\n"
0x1800094a2  mov     ecx, 100h; unsigned int
0x1800094a7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800094ac  lea     rdx, loc_1800094BE
0x1800094b3  mov     rcx, [rsp+68h+var_30]
0x1800094b8  call    _local_unwind_0
0x1800094bd  nop
0x1800094be  xor     eax, eax
0x1800094c0  jmp     loc_1800090F9
0x1800094c5  mov     [rsp+68h+ThreadId], 0
0x1800094d0  lea     rax, [rsp+68h+ThreadId]
0x1800094d8  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x1800094dd  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800094e5  lea     r8, ?NlWorkerThread@@YAXPEAX@Z; lpStartAddress
0x1800094ec  xor     edx, edx; dwStackSize
0x1800094ee  xor     ecx, ecx; lpThreadAttributes
0x1800094f0  call    cs:__imp_CreateThread
0x1800094f7  nop     dword ptr [rax+rax+00h]
0x1800094fc  mov     [rdi+r14+0F8968h], rax
0x180009504  mov     edx, [rsp+68h+ThreadId]
0x18000950b  mov     [rsp+68h+dwCreationFlags], edx
0x18000950f  mov     r9, rax
0x180009512  mov     r8d, ebx
0x180009515  lea     rdx, aLx0xPLxStartin; "%lx: 0x%p: %lx: Starting worker thread"...
0x18000951c  mov     ecx, 10000h; unsigned int
0x180009521  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180009526  cmp     qword ptr [rdi+r14+0F8968h], 0
0x18000952f  jnz     short loc_180009553
0x180009531  call    cs:__imp_GetLastError
0x180009538  nop     dword ptr [rax+rax+00h]
0x18000953d  mov     r8d, eax
0x180009540  lea     rdx, aNlqueueworkite_0; "NlQueueWorkItem: Cannot create thread %"...
0x180009547  mov     ecx, 100h; unsigned int
0x18000954c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180009551  jmp     short loc_180009559
0x180009553  inc     cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x180009559  lea     rcx, ?NlWorkerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180009560  call    cs:__imp_RtlLeaveCriticalSection
0x180009567  nop     dword ptr [rax+rax+00h]
0x18000956c  test    r13d, r13d
0x18000956f  jnz     loc_1800092C6
0x180009575  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x18000957c  lea     rcx, [rbx+10h]; this
0x180009580  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x180009585  or      eax, 0FFFFFFFFh
0x180009588  lock xadd [rbx], eax
0x18000958c  cmp     eax, 1
0x18000958f  jns     short loc_1800095A1
0x180009591  mov     rcx, [rbx+8]; hEvent
0x180009595  call    cs:__imp_SetEvent
0x18000959c  nop     dword ptr [rax+rax+00h]
0x1800095a1  lea     rcx, [rbx+10h]; this
0x1800095a5  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x1800095aa  mov     eax, 1
0x1800095af  jmp     loc_1800090F9
0x1800095b4  mov     ecx, 3
0x1800095b9  int     29h; Win8: RtlFailFast(ecx)
0x180090290  push    rbx
0x180090292  push    rbp
0x180090293  sub     rsp, 38h
0x180090297  mov     rbp, rdx
0x18009029a  lea     rcx, ?NlWorkerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800902a1  call    cs:__imp_RtlLeaveCriticalSection
0x1800902a8  nop     dword ptr [rax+rax+00h]
0x1800902ad  cmp     dword ptr [rbp+34h], 0
0x1800902b1  jnz     short loc_1800902EA
0x1800902b3  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x1800902ba  lea     rcx, [rbx+10h]; this
0x1800902be  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x1800902c3  or      eax, 0FFFFFFFFh
0x1800902c6  lock xadd [rbx], eax
0x1800902ca  sub     eax, 1
0x1800902cd  jns     short loc_1800902E0
0x1800902cf  mov     rcx, [rbx+8]; hEvent
0x1800902d3  call    cs:__imp_SetEvent
0x1800902da  nop     dword ptr [rax+rax+00h]
0x1800902df  nop
0x1800902e0  lea     rcx, [rbx+10h]; this
0x1800902e4  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x1800902e9  nop
0x1800902ea  add     rsp, 38h
0x1800902ee  pop     rbp
0x1800902ef  pop     rbx
0x1800902f0  retn
```
