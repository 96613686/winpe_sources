# NlWorkerThread(void *)

- ea: `0x180070ac0`
- end: `0x180070d5e`
- name: `?NlWorkerThread@@YAXPEAX@Z`
- size: `670`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x1800167c4`
- `0x180016900`
- `0x180070ac0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070c2e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070c2e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180070cf9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180070cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070c82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070c6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070c6a`
- `ntdll!RtlLeaveCriticalSection` at `0x180070b9d`
- `ntdll!RtlLeaveCriticalSection` at `0x180070ccd`
- `ntdll!RtlLeaveCriticalSection` at `0x180070d3b`
- `ntdll!RtlLeaveCriticalSection` at `0x180070b9d`
- `ntdll!RtlLeaveCriticalSection` at `0x180070ccd`
- `ntdll!RtlLeaveCriticalSection` at `0x180070d3b`
- `ntdll!RtlEnterCriticalSection` at `0x180070af9`
- `ntdll!RtlEnterCriticalSection` at `0x180070bd9`
- `ntdll!RtlEnterCriticalSection` at `0x180070af9`
- `ntdll!RtlEnterCriticalSection` at `0x180070bd9`

## string_xrefs

- `0x180070d16`: `%lx: worker thread exiting\n`
- `0x180070b73`: `onecore\ds\netapi\svcdlls\logonsrv\server\worker.cxx`
- `0x180070c12`: `%lx: 0x%p: Ditching worker thread\n`
- `0x180070c46`: `%lx: worker thread handle cannot be awaited. %ld 0x%p\n`
- `0x180070c99`: `%lx: worker thread handle cannot be closed. %ld 0x%p\n`

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
        NlAssertFailed("WorkItem->Inserted", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\worker.cxx", 0x6Du, v2);
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
0x180070ac0  cmp     ecx, 5
0x180070ac3  jnb     locret_180070D55
0x180070ac9  push    rbx
0x180070aca  push    rbp
0x180070acb  push    rsi
0x180070acc  push    rdi
0x180070acd  push    r12
0x180070acf  push    r13
0x180070ad1  push    r14
0x180070ad3  sub     rsp, 30h
0x180070ad7  mov     rbp, rcx
0x180070ada  lea     r12, ?NlWorkerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlWorkerCritSect
0x180070ae1  lea     r13, ?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x180070ae8  lea     r14, __ImageBase
0x180070aef  mov     rcx, r12; CriticalSection
0x180070af2  lea     rdi, ?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x180070af9  call    cs:__imp_RtlEnterCriticalSection
0x180070b00  nop     dword ptr [rax+rax+00h]
0x180070b05  mov     rbx, cs:?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerHighQueueHead
0x180070b0c  cmp     rbx, rdi
0x180070b0f  jnz     short loc_180070B45
0x180070b11  mov     rbx, cs:?NlWorkerQueueHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlWorkerQueueHead
0x180070b18  cmp     rbx, r13
0x180070b1b  jz      loc_180070D13
0x180070b21  cmp     [rbx+8], r13
0x180070b25  jnz     loc_180070D57
0x180070b2b  mov     rax, [rbx]
0x180070b2e  cmp     [rax+8], rbx
0x180070b32  jnz     loc_180070D57
0x180070b38  mov     cs:?NlWorkerQueueHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlWorkerQueueHead
0x180070b3f  mov     [rax+8], r13
0x180070b43  jmp     short loc_180070B67
0x180070b45  cmp     [rbx+8], rdi
0x180070b49  jnz     loc_180070D57
0x180070b4f  mov     rax, [rbx]
0x180070b52  cmp     [rax+8], rbx
0x180070b56  jnz     loc_180070D57
0x180070b5c  mov     cs:?NlWorkerHighQueueHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlWorkerHighQueueHead
0x180070b63  mov     [rax+8], rdi
0x180070b67  cmp     byte ptr [rbx+20h], 0
0x180070b6b  jnz     short loc_180070B86
0x180070b6d  mov     r8d, 6Dh ; 'm'; unsigned int
0x180070b73  lea     rdx, aOnecoreDsNetap_19; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180070b7a  lea     rcx, aWorkitemInsert; "WorkItem->Inserted"
0x180070b81  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180070b86  mov     eax, cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x180070b8c  mov     rcx, r12; CriticalSection
0x180070b8f  dec     eax
0x180070b91  mov     byte ptr [rbx+20h], 0
0x180070b95  inc     dword ptr rva ?NlWorkerThreadStats@@3PAKA[r14+rax*4]; ulong near * NlWorkerThreadStats ...
0x180070b9d  call    cs:__imp_RtlLeaveCriticalSection
0x180070ba4  nop     dword ptr [rax+rax+00h]
0x180070ba9  mov     rax, [rbx+10h]
0x180070bad  lea     rdx, aLxPullingOffWo; "%lx: Pulling off work item 0x%p (0x%p)"...
0x180070bb4  mov     r9, rbx
0x180070bb7  mov     [rsp+68h+var_48], rax
0x180070bbc  mov     r8d, ebp
0x180070bbf  mov     ecx, 10000h; unsigned int
0x180070bc4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180070bc9  mov     rcx, [rbx+18h]
0x180070bcd  mov     rax, [rbx+10h]
0x180070bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070bd6  mov     rcx, r12; CriticalSection
0x180070bd9  call    cs:__imp_RtlEnterCriticalSection
0x180070be0  nop     dword ptr [rax+rax+00h]
0x180070be5  xor     esi, esi
0x180070be7  cmp     ebp, esi
0x180070be9  jz      loc_180070CBF
0x180070bef  mov     r9, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; void * near * NlThreadArray ...
0x180070bf7  test    r9, r9
0x180070bfa  jz      loc_180070CBF
0x180070c00  cmp     byte ptr [rsi+r14+0F8960h], 0
0x180070c09  jz      loc_180070CBF
0x180070c0f  mov     r8d, esi
0x180070c12  lea     rdx, aLx0xPDitchingW; "%lx: 0x%p: Ditching worker thread\n"
0x180070c19  mov     ecx, 10000h; unsigned int
0x180070c1e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180070c23  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; hHandle
0x180070c2b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180070c2e  call    cs:__imp_WaitForSingleObject
0x180070c35  nop     dword ptr [rax+rax+00h]
0x180070c3a  test    eax, eax
0x180070c3c  jz      short loc_180070C62
0x180070c3e  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; void * near * NlThreadArray ...
0x180070c46  lea     rdx, aLxWorkerThread_1; "%lx: worker thread handle cannot be awa"...
0x180070c4d  mov     [rsp+68h+var_48], rcx
0x180070c52  mov     r9d, eax
0x180070c55  mov     ecx, 100h; unsigned int
0x180070c5a  mov     r8d, esi
0x180070c5d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180070c62  mov     rcx, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; hObject
0x180070c6a  call    cs:__imp_CloseHandle
0x180070c71  nop     dword ptr [rax+rax+00h]
0x180070c76  test    eax, eax
0x180070c78  jnz     short loc_180070CAA
0x180070c7a  mov     rbx, qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8]; void * near * NlThreadArray ...
0x180070c82  call    cs:__imp_GetLastError
0x180070c89  nop     dword ptr [rax+rax+00h]
0x180070c8e  mov     r8d, esi
0x180070c91  mov     [rsp+68h+var_48], rbx
0x180070c96  mov     r9d, eax
0x180070c99  lea     rdx, aLxWorkerThread; "%lx: worker thread handle cannot be clo"...
0x180070ca0  mov     ecx, 100h; unsigned int
0x180070ca5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180070caa  mov     qword ptr rva ?NlThreadArray@@3PAPEAXA[r14+rsi*8], 0; void * near * NlThreadArray ...
0x180070cb6  mov     byte ptr [rsi+r14+0F8960h], 0
0x180070cbf  inc     esi
0x180070cc1  cmp     esi, 5
0x180070cc4  jb      loc_180070BE7
0x180070cca  mov     rcx, r12; CriticalSection
0x180070ccd  call    cs:__imp_RtlLeaveCriticalSection
0x180070cd4  nop     dword ptr [rax+rax+00h]
0x180070cd9  mov     rbx, cs:?NlOutstandingTasks@@3PEAXEA; void * NlOutstandingTasks
0x180070ce0  lea     rcx, [rbx+10h]; this
0x180070ce4  call    ?Acquire@SPINLOCK@@QEAAXXZ; SPINLOCK::Acquire(void)
0x180070ce9  or      eax, 0FFFFFFFFh
0x180070cec  lock xadd [rbx], eax
0x180070cf0  cmp     eax, 1
0x180070cf3  jns     short loc_180070D05
0x180070cf5  mov     rcx, [rbx+8]; hEvent
0x180070cf9  call    cs:__imp_SetEvent
0x180070d00  nop     dword ptr [rax+rax+00h]
0x180070d05  lea     rcx, [rbx+10h]; this
0x180070d09  call    ?Release@SPINLOCK@@QEAAXXZ; SPINLOCK::Release(void)
0x180070d0e  jmp     loc_180070AEF
0x180070d13  mov     r8d, ebp
0x180070d16  lea     rdx, aLxWorkerThread_0; "%lx: worker thread exiting\n"
0x180070d1d  mov     ecx, 10000h; unsigned int
0x180070d22  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180070d27  dec     cs:?NlNumberOfCreatedWorkerThreads@@3KA; ulong NlNumberOfCreatedWorkerThreads
0x180070d2d  mov     rcx, r12; CriticalSection
0x180070d30  mov     eax, ebp
0x180070d32  mov     byte ptr [rax+r14+0F8960h], 1
0x180070d3b  call    cs:__imp_RtlLeaveCriticalSection
0x180070d42  nop     dword ptr [rax+rax+00h]
0x180070d47  add     rsp, 30h
0x180070d4b  pop     r14
0x180070d4d  pop     r13
0x180070d4f  pop     r12
0x180070d51  pop     rdi
0x180070d52  pop     rsi
0x180070d53  pop     rbp
0x180070d54  pop     rbx
0x180070d55  retn
0x180070d57  mov     ecx, 3
0x180070d5c  int     29h; Win8: RtlFailFast(ecx)
```
