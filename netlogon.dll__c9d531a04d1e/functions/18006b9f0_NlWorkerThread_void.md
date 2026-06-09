# NlWorkerThread(void *)

- ea: `0x18006b9f0`
- end: `0x18006bc57`
- name: `?NlWorkerThread@@YAXPEAX@Z`
- size: `615`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180007278`
- `0x18000d710`
- `0x180015e84`
- `0x180015fa0`
- `0x18006b9f0`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006bb4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006bb4c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006bbff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006bbff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bb94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bb82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bb82`
- `ntdll!RtlLeaveCriticalSection` at `0x18006bac7`
- `ntdll!RtlLeaveCriticalSection` at `0x18006bbd9`
- `ntdll!RtlLeaveCriticalSection` at `0x18006bc3b`
- `ntdll!RtlLeaveCriticalSection` at `0x18006bac7`
- `ntdll!RtlLeaveCriticalSection` at `0x18006bbd9`
- `ntdll!RtlLeaveCriticalSection` at `0x18006bc3b`
- `ntdll!RtlEnterCriticalSection` at `0x18006ba29`
- `ntdll!RtlEnterCriticalSection` at `0x18006bafd`
- `ntdll!RtlEnterCriticalSection` at `0x18006ba29`
- `ntdll!RtlEnterCriticalSection` at `0x18006bafd`

## string_xrefs

- `0x18006bc16`: `%lx: worker thread exiting\n`
- `0x18006ba9d`: `onecore\ds\netapi\svcdlls\logonsrv\server\worker.cxx`
- `0x18006bb30`: `%lx: 0x%p: Ditching worker thread\n`
- `0x18006bb5e`: `%lx: worker thread handle cannot be awaited. %ld 0x%p\n`
- `0x18006bba5`: `%lx: worker thread handle cannot be closed. %ld 0x%p\n`

## pseudocode

```c
void __fastcall NlWorkerThread(PVOID Parameter)
{
  unsigned int v1; // ebp
  char *v2; // r9
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v4; // rax
  struct _LIST_ENTRY *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rsi
  DWORD v8; // eax
  void * near *v9; // rbx
  DWORD LastError; // eax
  AXB *v11; // rbx

  if ( (unsigned int)Parameter < 5 )
  {
    v1 = (unsigned int)Parameter;
    while ( 1 )
    {
      RtlEnterCriticalSection(&NlWorkerCritSect);
      Flink = NlWorkerHighQueueHead.Flink;
      if ( NlWorkerHighQueueHead.Flink == &NlWorkerHighQueueHead )
      {
        Flink = NlWorkerQueueHead.Flink;
        if ( NlWorkerQueueHead.Flink == &NlWorkerQueueHead )
        {
          NlPrintRoutine(0x10000u, L"%lx: worker thread exiting\n", v1);
          --NlNumberOfCreatedWorkerThreads;
          *((_BYTE *)&NlThreadExitted + v1) = 1;
          RtlLeaveCriticalSection(&NlWorkerCritSect);
          return;
        }
        if ( NlWorkerQueueHead.Flink->Blink != &NlWorkerQueueHead )
          goto LABEL_28;
        v4 = NlWorkerQueueHead.Flink->Flink;
        if ( NlWorkerQueueHead.Flink->Flink->Blink != NlWorkerQueueHead.Flink )
          goto LABEL_28;
        NlWorkerQueueHead.Flink = NlWorkerQueueHead.Flink->Flink;
        v4->Blink = &NlWorkerQueueHead;
      }
      else
      {
        if ( NlWorkerHighQueueHead.Flink->Blink != &NlWorkerHighQueueHead
          || (v5 = NlWorkerHighQueueHead.Flink->Flink,
              NlWorkerHighQueueHead.Flink->Flink->Blink != NlWorkerHighQueueHead.Flink) )
        {
LABEL_28:
          __fastfail(3u);
        }
        NlWorkerHighQueueHead.Flink = NlWorkerHighQueueHead.Flink->Flink;
        v5->Blink = &NlWorkerHighQueueHead;
      }
      if ( !LOBYTE(Flink[2].Flink) )
        NlAssertFailed("WorkItem->Inserted", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\worker.cxx", 109, v2);
      v6 = NlNumberOfCreatedWorkerThreads - 1;
      LOBYTE(Flink[2].Flink) = 0;
      ++*((_DWORD *)&NlWorkerThreadStats + v6);
      RtlLeaveCriticalSection(&NlWorkerCritSect);
      NlPrintRoutine(0x10000u, L"%lx: Pulling off work item 0x%p (0x%p)\n", v1, Flink, Flink[1].Flink);
      ((void (__fastcall *)(struct _LIST_ENTRY *))Flink[1].Flink)(Flink[1].Blink);
      RtlEnterCriticalSection(&NlWorkerCritSect);
      v7 = 0;
      do
      {
        if ( v1 != (_DWORD)v7 && (&NlThreadArray)[v7] && *((_BYTE *)&NlThreadExitted + v7) )
        {
          NlPrintRoutine(0x10000u, L"%lx: 0x%p: Ditching worker thread\n", (unsigned int)v7);
          v8 = WaitForSingleObject((&NlThreadArray)[v7], 0xFFFFFFFF);
          if ( v8 )
            NlPrintRoutine(
              0x100u,
              L"%lx: worker thread handle cannot be awaited. %ld 0x%p\n",
              (unsigned int)v7,
              v8,
              (&NlThreadArray)[v7]);
          if ( !CloseHandle((&NlThreadArray)[v7]) )
          {
            v9 = (&NlThreadArray)[v7];
            LastError = GetLastError();
            NlPrintRoutine(
              0x100u,
              L"%lx: worker thread handle cannot be closed. %ld 0x%p\n",
              (unsigned int)v7,
              LastError,
              v9);
          }
          (&NlThreadArray)[v7] = 0;
          *((_BYTE *)&NlThreadExitted + v7) = 0;
        }
        v7 = (unsigned int)(v7 + 1);
      }
      while ( (unsigned int)v7 < 5 );
      RtlLeaveCriticalSection(&NlWorkerCritSect);
      v11 = NlOutstandingTasks;
      SPINLOCK::Acquire((AXB *)((char *)NlOutstandingTasks + 16));
      if ( _InterlockedDecrement((volatile signed __int32 *)v11) < 0 )
        SetEvent(*((HANDLE *)v11 + 1));
      SPINLOCK::Release((AXB *)((char *)v11 + 16));
    }
  }
}

```

## disassembly

```asm
0x18006b9f0  cmp     ecx, 5
0x18006b9f3  jnb     locret_18006BC4F
0x18006b9f9  push    rbx
0x18006b9fa  push    rbp
0x18006b9fb  push    rsi
0x18006b9fc  push    rdi
0x18006b9fd  push    r12
0x18006b9ff  push    r13
0x18006ba01  push    r14
0x18006ba03  sub     rsp, 30h
0x18006ba07  mov     rbp, rcx
0x18006ba0a  lea     r12, ?NlWorkerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlWorkerCritSect
0x18006ba11  lea     r13, ?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x18006ba18  lea     r14, __ImageBase
0x18006ba1f  mov     rcx, r12; CriticalSection
0x18006ba22  lea     rdi, ?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x18006ba29  call    cs:__imp_RtlEnterCriticalSection
0x18006ba2f  mov     rbx, cs:?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x18006ba36  cmp     rbx, rdi
0x18006ba39  jnz     short loc_18006BA6F
0x18006ba3b  mov     rbx, cs:?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x18006ba42  cmp     rbx, r13
0x18006ba45  jz      loc_18006BC13
0x18006ba4b  cmp     [rbx+8], r13
0x18006ba4f  jnz     loc_18006BC50
0x18006ba55  mov     rax, [rbx]
0x18006ba58  cmp     [rax+8], rbx
0x18006ba5c  jnz     loc_18006BC50
0x18006ba62  mov     cs:?NlWorkerQueueHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlWorkerQueueHead
0x18006ba69  mov     [rax+8], r13
0x18006ba6d  jmp     short loc_18006BA91
0x18006ba6f  cmp     [rbx+8], rdi
0x18006ba73  jnz     loc_18006BC50
0x18006ba79  mov     rax, [rbx]
0x18006ba7c  cmp     [rax+8], rbx
0x18006ba80  jnz     loc_18006BC50
0x18006ba86  mov     cs:?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlWorkerHighQueueHead
0x18006ba8d  mov     [rax+8], rdi
0x18006ba91  cmp     byte ptr [rbx+20h], 0
0x18006ba95  jnz     short loc_18006BAB0
0x18006ba97  mov     r8d, 6Dh ; 'm'; unsigned int
0x18006ba9d  lea     rdx, aOnecoreDsNetap_19; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006baa4  lea     rcx, aWorkitemInsert; "WorkItem->Inserted"
0x18006baab  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006bab0  mov     eax, cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x18006bab6  mov     rcx, r12; CriticalSection
0x18006bab9  dec     eax
0x18006babb  mov     byte ptr [rbx+20h], 0
0x18006babf  inc     dword ptr rva ?NlWorkerThreadStats@@3PAKA[r14+rax*4]; ulong near * NlWorkerThreadStats ...
0x18006bac7  call    cs:__imp_RtlLeaveCriticalSection
0x18006bacd  mov     rax, [rbx+10h]
0x18006bad1  lea     rdx, aLxPullingOffWo; "%lx: Pulling off work item 0x%p (0x%p)"...
0x18006bad8  mov     r9, rbx
0x18006badb  mov     [rsp+68h+var_48], rax
0x18006bae0  mov     r8d, ebp
0x18006bae3  mov     ecx, 10000h; unsigned int
0x18006bae8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006baed  mov     rcx, [rbx+18h]
0x18006baf1  mov     rax, [rbx+10h]
0x18006baf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bafa  mov     rcx, r12; CriticalSection
0x18006bafd  call    cs:__imp_RtlEnterCriticalSection
0x18006bb03  xor     esi, esi
0x18006bb05  cmp     ebp, esi
0x18006bb07  jz      loc_18006BBCB
0x18006bb0d  mov     r9, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; void * near * NlThreadArray ...
0x18006bb15  test    r9, r9
0x18006bb18  jz      loc_18006BBCB
0x18006bb1e  cmp     byte ptr [rsi+r14+0F1960h], 0
0x18006bb27  jz      loc_18006BBCB
0x18006bb2d  mov     r8d, esi
0x18006bb30  lea     rdx, aLx0xPDitchingW; "%lx: 0x%p: Ditching worker thread\n"
0x18006bb37  mov     ecx, 10000h; unsigned int
0x18006bb3c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006bb41  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; hHandle
0x18006bb49  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006bb4c  call    cs:__imp_WaitForSingleObject
0x18006bb52  test    eax, eax
0x18006bb54  jz      short loc_18006BB7A
0x18006bb56  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; void * near * NlThreadArray ...
0x18006bb5e  lea     rdx, aLxWorkerThread_1; "%lx: worker thread handle cannot be awa"...
0x18006bb65  mov     [rsp+68h+var_48], rcx
0x18006bb6a  mov     r9d, eax
0x18006bb6d  mov     ecx, 100h; unsigned int
0x18006bb72  mov     r8d, esi
0x18006bb75  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006bb7a  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; hObject
0x18006bb82  call    cs:__imp_CloseHandle
0x18006bb88  test    eax, eax
0x18006bb8a  jnz     short loc_18006BBB6
0x18006bb8c  mov     rbx, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; void * near * NlThreadArray ...
0x18006bb94  call    cs:__imp_GetLastError
0x18006bb9a  mov     r8d, esi
0x18006bb9d  mov     [rsp+68h+var_48], rbx
0x18006bba2  mov     r9d, eax
0x18006bba5  lea     rdx, aLxWorkerThread; "%lx: worker thread handle cannot be clo"...
0x18006bbac  mov     ecx, 100h; unsigned int
0x18006bbb1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006bbb6  mov     qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8], 0; void * near * NlThreadArray ...
0x18006bbc2  mov     byte ptr [rsi+r14+0F1960h], 0
0x18006bbcb  inc     esi
0x18006bbcd  cmp     esi, 5
0x18006bbd0  jb      loc_18006BB05
0x18006bbd6  mov     rcx, r12; CriticalSection
0x18006bbd9  call    cs:__imp_RtlLeaveCriticalSection
0x18006bbdf  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x18006bbe6  lea     rcx, [rbx+10h]; this
0x18006bbea  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x18006bbef  or      eax, 0FFFFFFFFh
0x18006bbf2  lock xadd [rbx], eax
0x18006bbf6  cmp     eax, 1
0x18006bbf9  jns     short loc_18006BC05
0x18006bbfb  mov     rcx, [rbx+8]; hEvent
0x18006bbff  call    cs:__imp_SetEvent
0x18006bc05  lea     rcx, [rbx+10h]; this
0x18006bc09  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x18006bc0e  jmp     loc_18006BA1F
0x18006bc13  mov     r8d, ebp
0x18006bc16  lea     rdx, aLxWorkerThread_0; "%lx: worker thread exiting\n"
0x18006bc1d  mov     ecx, 10000h; unsigned int
0x18006bc22  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006bc27  dec     cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x18006bc2d  mov     rcx, r12; CriticalSection
0x18006bc30  mov     eax, ebp
0x18006bc32  mov     byte ptr [rax+r14+0F1960h], 1
0x18006bc3b  call    cs:__imp_RtlLeaveCriticalSection
0x18006bc41  add     rsp, 30h
0x18006bc45  pop     r14
0x18006bc47  pop     r13
0x18006bc49  pop     r12
0x18006bc4b  pop     rdi
0x18006bc4c  pop     rsi
0x18006bc4d  pop     rbp
0x18006bc4e  pop     rbx
0x18006bc4f  retn
0x18006bc50  mov     ecx, 3
0x18006bc55  int     29h; Win8: RtlFailFast(ecx)
```
