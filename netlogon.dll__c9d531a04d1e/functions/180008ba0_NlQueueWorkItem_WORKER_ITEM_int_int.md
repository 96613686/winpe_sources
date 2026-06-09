# NlQueueWorkItem(_WORKER_ITEM *,int,int)

- ea: `0x180008ba0`
- end: `0x18000905c`
- name: `?NlQueueWorkItem@@YAHPEAU_WORKER_ITEM@@HH@Z`
- size: `1212`
- prototype: `__int64 __fastcall(struct _WORKER_ITEM *, int, int)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005d98`
- `0x180021a28`
- `0x180027870`
- `0x180064674`
- `0x180064834`
- `0x18006f490`
- `0x18007070c`

## callees

- `0x180007278`
- `0x180008ba0`
- `0x180015e84`
- `0x180015fa0`
- `0x180089a9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008cbe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008cbe`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008bff`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008bff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008c3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000903b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180089b7d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008c3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000903b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180089b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fe3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fe3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008fa8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008fa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cf4`
- `ntdll!RtlLeaveCriticalSection` at `0x18000900c`
- `ntdll!RtlLeaveCriticalSection` at `0x180089b51`
- `ntdll!RtlLeaveCriticalSection` at `0x18000900c`
- `ntdll!RtlLeaveCriticalSection` at `0x180089b51`
- `ntdll!RtlEnterCriticalSection` at `0x180008c5f`
- `ntdll!RtlEnterCriticalSection` at `0x180008c5f`

## string_xrefs

- `0x180008ca2`: `%lx: 0x%p: Ditching worker thread\n`
- `0x180008cdb`: `%lx: worker thread handle cannot be awaited. %ld 0x%p\n`
- `0x180008d17`: `%lx: worker thread handle cannot be closed. %ld 0x%p\n`
- `0x180008fc7`: `%lx: 0x%p: %lx: Starting worker thread\n`
- `0x180008fec`: `NlQueueWorkItem: Cannot create thread %ld\n`

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
        local_unwind_0(v31, &loc_180008D7E);
        return 1;
      }
      goto LABEL_31;
    }
    NlPrintRoutine(0x10000u, L"Inserting work item 0x%p (0x%p)\n", a1, *((_QWORD *)a1 + 2));
    if ( a3 )
    {
      v15 = (_QWORD *)qword_1800F1FD0;
      if ( *(struct _LIST_ENTRY **)qword_1800F1FD0 == &NlWorkerHighQueueHead )
      {
        *(_QWORD *)a1 = &NlWorkerHighQueueHead;
        *((_QWORD *)a1 + 1) = v15;
        *v15 = a1;
        qword_1800F1FD0 = (__int64)a1;
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
      v16 = (_QWORD *)qword_1800F1FE0;
      if ( *(struct _LIST_ENTRY **)qword_1800F1FE0 == &NlWorkerQueueHead )
      {
        *(_QWORD *)a1 = &NlWorkerQueueHead;
        *((_QWORD *)a1 + 1) = v16;
        *v16 = a1;
        qword_1800F1FE0 = (__int64)a1;
        goto LABEL_30;
      }
    }
LABEL_58:
    __fastfail(3u);
  }
  if ( !v13 )
  {
    local_unwind_0(v31, &loc_180008E64);
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
    local_unwind_0(v31, &loc_180008F44);
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
        local_unwind_0(v31, &loc_180008F76);
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
0x180008ba0  mov     [rsp+arg_10], r8d
0x180008ba5  mov     [rsp+arg_8], edx
0x180008ba9  push    rbx
0x180008baa  push    rdi
0x180008bab  push    r13
0x180008bad  push    r14
0x180008baf  push    r15
0x180008bb1  sub     rsp, 40h
0x180008bb5  mov     [rsp+68h+var_30], rsp
0x180008bba  mov     rdi, rcx
0x180008bbd  cmp     cs:?NlWorkerInitialized@@3EA, 0; uchar NlWorkerInitialized
0x180008bc4  jnz     short loc_180008BE6
0x180008bc6  lea     rdx, aNlqueueworkite_1; "NlQueueWorkItem when worker not initial"...
0x180008bcd  mov     ecx, 100h; unsigned int
0x180008bd2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180008bd7  xor     eax, eax
0x180008bd9  add     rsp, 40h
0x180008bdd  pop     r15
0x180008bdf  pop     r14
0x180008be1  pop     r13
0x180008be3  pop     rdi
0x180008be4  pop     rbx
0x180008be5  retn
0x180008be6  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x180008bed  lea     rcx, [rbx+10h]; this
0x180008bf1  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x180008bf6  lock inc dword ptr [rbx]
0x180008bf9  jnz     short loc_180008C05
0x180008bfb  mov     rcx, [rbx+8]; hEvent
0x180008bff  call    cs:__imp_ResetEvent
0x180008c05  lea     rcx, [rbx+10h]; this
0x180008c09  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x180008c0e  mov     rdx, cs:?NlTaskGate@@3PEAXEA; void * NlTaskGate
0x180008c15  xor     ecx, ecx
0x180008c17  xor     eax, eax
0x180008c19  lock cmpxchg [rdx], ecx
0x180008c1d  jz      short loc_180008C50
0x180008c1f  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x180008c26  lea     rcx, [rbx+10h]; this
0x180008c2a  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x180008c2f  or      eax, 0FFFFFFFFh
0x180008c32  lock xadd [rbx], eax
0x180008c36  cmp     eax, 1
0x180008c39  jns     short loc_180008C45
0x180008c3b  mov     rcx, [rbx+8]; hEvent
0x180008c3f  call    cs:__imp_SetEvent
0x180008c45  lea     rcx, [rbx+10h]; this
0x180008c49  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x180008c4e  jmp     short loc_180008BD7
0x180008c50  xor     r13d, r13d
0x180008c53  mov     [rsp+68h+var_34], r13d
0x180008c58  lea     rcx, ?NlWorkerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180008c5f  call    cs:__imp_RtlEnterCriticalSection
0x180008c65  nop
0x180008c66  xor     r14d, r14d
0x180008c69  lea     rbx, __ImageBase
0x180008c70  mov     [rsp+68h+var_38], r14d
0x180008c75  cmp     r14d, 5
0x180008c79  jnb     loc_180008D4C
0x180008c7f  mov     r9, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; void * near * NlThreadArray ...
0x180008c87  test    r9, r9
0x180008c8a  jz      loc_180008D44
0x180008c90  cmp     byte ptr [r14+rbx+0F1960h], 0
0x180008c99  jz      loc_180008D44
0x180008c9f  mov     r8d, r14d
0x180008ca2  lea     rdx, aLx0xPDitchingW; "%lx: 0x%p: Ditching worker thread\n"
0x180008ca9  mov     ecx, 10000h; unsigned int
0x180008cae  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180008cb3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008cb6  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; hHandle
0x180008cbe  call    cs:__imp_WaitForSingleObject
0x180008cc4  test    eax, eax
0x180008cc6  jz      short loc_180008CEC
0x180008cc8  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; void * near * NlThreadArray ...
0x180008cd0  mov     qword ptr [rsp+68h+dwCreationFlags], rcx
0x180008cd5  mov     r9d, eax
0x180008cd8  mov     r8d, r14d
0x180008cdb  lea     rdx, aLxWorkerThread_1; "%lx: worker thread handle cannot be awa"...
0x180008ce2  mov     ecx, 100h; unsigned int
0x180008ce7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180008cec  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; hObject
0x180008cf4  call    cs:__imp_CloseHandle
0x180008cfa  test    eax, eax
0x180008cfc  jnz     short loc_180008D2F
0x180008cfe  mov     rbx, qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8]; void * near * NlThreadArray ...
0x180008d06  call    cs:__imp_GetLastError
0x180008d0c  mov     qword ptr [rsp+68h+dwCreationFlags], rbx
0x180008d11  mov     r9d, eax
0x180008d14  mov     r8d, r14d
0x180008d17  lea     rdx, aLxWorkerThread; "%lx: worker thread handle cannot be clo"...
0x180008d1e  mov     ecx, 100h; unsigned int
0x180008d23  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180008d28  lea     rbx, __ImageBase
0x180008d2f  mov     qword ptr rva ?NlThreadArray@@3PAPEAXA[rbx+r14*8], 0; void * near * NlThreadArray ...
0x180008d3b  mov     byte ptr [r14+rbx+0F1960h], 0
0x180008d44  inc     r14d
0x180008d47  jmp     loc_180008C70
0x180008d4c  mov     al, [rdi+20h]
0x180008d4f  cmp     [rsp+68h+arg_8], 0
0x180008d54  jz      loc_180008E4E
0x180008d5a  test    al, al
0x180008d5c  jz      short loc_180008D88
0x180008d5e  mov     eax, cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x180008d64  test    eax, eax
0x180008d66  jz      loc_180008E11
0x180008d6c  lea     rdx, loc_180008D7E
0x180008d73  mov     rcx, [rsp+68h+var_30]
0x180008d78  call    _local_unwind_0
0x180008d7d  nop
0x180008d7e  mov     eax, 1
0x180008d83  jmp     loc_180008BD9
0x180008d88  mov     r9, [rdi+10h]
0x180008d8c  mov     r8, rdi
0x180008d8f  lea     rdx, aInsertingWorkI; "Inserting work item 0x%p (0x%p)\n"
0x180008d96  mov     ecx, 10000h; unsigned int
0x180008d9b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180008da0  cmp     [rsp+68h+arg_10], 0
0x180008da8  jz      short loc_180008DD4
0x180008daa  mov     rcx, cs:qword_1800F1FD0
0x180008db1  lea     rax, ?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x180008db8  cmp     [rcx], rax
0x180008dbb  jnz     loc_180009054
0x180008dc1  mov     [rdi], rax
0x180008dc4  mov     [rdi+8], rcx
0x180008dc8  mov     [rcx], rdi
0x180008dcb  mov     cs:qword_1800F1FD0, rdi
0x180008dd2  jmp     short loc_180008DFC
0x180008dd4  mov     rcx, cs:qword_1800F1FE0
0x180008ddb  lea     rax, ?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x180008de2  cmp     [rcx], rax
0x180008de5  jnz     loc_180009054
0x180008deb  mov     [rdi], rax
0x180008dee  mov     [rdi+8], rcx
0x180008df2  mov     [rcx], rdi
0x180008df5  mov     cs:qword_1800F1FE0, rdi
0x180008dfc  mov     byte ptr [rdi+20h], 1
0x180008e00  mov     r13d, 1
0x180008e06  mov     [rsp+68h+var_34], r13d
0x180008e0b  mov     eax, cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x180008e11  cmp     eax, 5
0x180008e14  jnb     loc_180009005
0x180008e1a  xor     ebx, ebx
0x180008e1c  lea     r14, __ImageBase
0x180008e23  mov     [rsp+68h+var_38], ebx
0x180008e27  mov     r9d, ebx; lpParameter
0x180008e2a  lea     rdi, ds:0[rbx*8]
0x180008e32  cmp     ebx, 5
0x180008e35  jnb     loc_180008F53
0x180008e3b  cmp     qword ptr [rdi+r14+0F1970h], 0
0x180008e44  jz      loc_180008F4E
0x180008e4a  inc     ebx
0x180008e4c  jmp     short loc_180008E23
0x180008e4e  test    al, al
0x180008e50  jnz     short loc_180008E6E
0x180008e52  lea     rdx, loc_180008E64
0x180008e59  mov     rcx, [rsp+68h+var_30]
0x180008e5e  call    _local_unwind_0
0x180008e63  nop
0x180008e64  mov     eax, 1
0x180008e69  jmp     loc_180008BD9
0x180008e6e  lea     rax, aLow; "low"
0x180008e75  lea     r8, aHigh; "high"
0x180008e7c  mov     r15d, [rsp+68h+arg_10]
0x180008e84  test    r15d, r15d
0x180008e87  cmovz   r8, rax
0x180008e8b  mov     rax, [rdi+10h]
0x180008e8f  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x180008e94  mov     r9, rdi
0x180008e97  lea     rdx, aBoostingHsPrio; "Boosting %hs priority work item 0x%p (0"...
0x180008e9e  mov     ecx, 10000h; unsigned int
0x180008ea3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180008ea8  mov     rcx, [rdi]
0x180008eab  cmp     [rcx+8], rdi
0x180008eaf  jnz     loc_180009054
0x180008eb5  mov     rax, [rdi+8]
0x180008eb9  cmp     [rax], rdi
0x180008ebc  jnz     loc_180009054
0x180008ec2  mov     [rax], rcx
0x180008ec5  mov     [rcx+8], rax
0x180008ec9  test    r15d, r15d
0x180008ecc  jz      short loc_180008EFA
0x180008ece  mov     rcx, cs:?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x180008ed5  lea     rax, ?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x180008edc  cmp     [rcx+8], rax
0x180008ee0  jnz     loc_180009054
0x180008ee6  mov     [rdi], rcx
0x180008ee9  mov     [rdi+8], rax
0x180008eed  mov     [rcx+8], rdi
0x180008ef1  mov     cs:?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY NlWorkerHighQueueHead
0x180008ef8  jmp     short loc_180008F24
0x180008efa  mov     rcx, cs:?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x180008f01  lea     rax, ?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x180008f08  cmp     [rcx+8], rax
0x180008f0c  jnz     loc_180009054
0x180008f12  mov     [rdi], rcx
0x180008f15  mov     [rdi+8], rax
0x180008f19  mov     [rcx+8], rdi
0x180008f1d  mov     cs:?NlWorkerQueueHead@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY NlWorkerQueueHead
0x180008f24  mov     eax, cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x180008f2a  test    eax, eax
0x180008f2c  jz      loc_180008E11
0x180008f32  lea     rdx, loc_180008F44
0x180008f39  mov     rcx, [rsp+68h+var_30]
0x180008f3e  call    _local_unwind_0
0x180008f43  nop
0x180008f44  mov     eax, 1
0x180008f49  jmp     loc_180008BD9
0x180008f4e  cmp     ebx, 5
0x180008f51  jb      short loc_180008F7D
0x180008f53  lea     rdx, aNlqueueworkite_2; "NlQueueWorkItem: Internal Error\n"
0x180008f5a  mov     ecx, 100h; unsigned int
0x180008f5f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180008f64  lea     rdx, loc_180008F76
0x180008f6b  mov     rcx, [rsp+68h+var_30]
0x180008f70  call    _local_unwind_0
0x180008f75  nop
0x180008f76  xor     eax, eax
0x180008f78  jmp     loc_180008BD9
0x180008f7d  mov     [rsp+68h+ThreadId], 0
0x180008f88  lea     rax, [rsp+68h+ThreadId]
0x180008f90  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180008f95  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x180008f9d  lea     r8, ?NlWorkerThread@@YAXPEAX@Z; lpStartAddress
0x180008fa4  xor     edx, edx; dwStackSize
0x180008fa6  xor     ecx, ecx; lpThreadAttributes
0x180008fa8  call    cs:__imp_CreateThread
0x180008fae  mov     [rdi+r14+0F1970h], rax
0x180008fb6  mov     edx, [rsp+68h+ThreadId]
0x180008fbd  mov     [rsp+68h+dwCreationFlags], edx
0x180008fc1  mov     r9, rax
0x180008fc4  mov     r8d, ebx
0x180008fc7  lea     rdx, aLx0xPLxStartin; "%lx: 0x%p: %lx: Starting worker thread"...
0x180008fce  mov     ecx, 10000h; unsigned int
0x180008fd3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180008fd8  cmp     qword ptr [rdi+r14+0F1970h], 0
0x180008fe1  jnz     short loc_180008FFF
0x180008fe3  call    cs:__imp_GetLastError
0x180008fe9  mov     r8d, eax
0x180008fec  lea     rdx, aNlqueueworkite_0; "NlQueueWorkItem: Cannot create thread %"...
0x180008ff3  mov     ecx, 100h; unsigned int
0x180008ff8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180008ffd  jmp     short loc_180009005
0x180008fff  inc     cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x180009005  lea     rcx, ?NlWorkerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18000900c  call    cs:__imp_RtlLeaveCriticalSection
0x180009012  test    r13d, r13d
0x180009015  jnz     loc_180008D7E
0x18000901b  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x180009022  lea     rcx, [rbx+10h]; this
0x180009026  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x18000902b  or      eax, 0FFFFFFFFh
0x18000902e  lock xadd [rbx], eax
0x180009032  cmp     eax, 1
0x180009035  jns     short loc_180009041
0x180009037  mov     rcx, [rbx+8]; hEvent
0x18000903b  call    cs:__imp_SetEvent
0x180009041  lea     rcx, [rbx+10h]; this
0x180009045  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x18000904a  mov     eax, 1
0x18000904f  jmp     loc_180008BD9
0x180009054  mov     ecx, 3
0x180009059  int     29h; Win8: RtlFailFast(ecx)
0x180089b40  push    rbx
0x180089b42  push    rbp
0x180089b43  sub     rsp, 38h
0x180089b47  mov     rbp, rdx
0x180089b4a  lea     rcx, ?NlWorkerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180089b51  call    cs:__imp_RtlLeaveCriticalSection
0x180089b57  cmp     dword ptr [rbp+34h], 0
0x180089b5b  jnz     short loc_180089B8E
0x180089b5d  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x180089b64  lea     rcx, [rbx+10h]; this
0x180089b68  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x180089b6d  or      eax, 0FFFFFFFFh
0x180089b70  lock xadd [rbx], eax
0x180089b74  sub     eax, 1
0x180089b77  jns     short loc_180089B84
0x180089b79  mov     rcx, [rbx+8]; hEvent
0x180089b7d  call    cs:__imp_SetEvent
0x180089b83  nop
0x180089b84  lea     rcx, [rbx+10h]; this
0x180089b88  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x180089b8d  nop
0x180089b8e  add     rsp, 38h
0x180089b92  pop     rbp
0x180089b93  pop     rbx
0x180089b94  retn
```
