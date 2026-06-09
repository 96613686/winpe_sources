# GarbageCollectionNeeded(int,ulong)

- ea: `0x18002f928`
- end: `0x18002fa62`
- name: `?GarbageCollectionNeeded@@YAHHK@Z`
- size: `314`
- prototype: `__int64 __fastcall(int, unsigned int)`
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002f070`
- `0x18004bb90`
- `0x1800527e8`
- `0x180054318`
- `0x180073554`
- `0x180085070`
- `0x180093e74`
- `0x180096930`
- `0x1800bc6e8`

## callees

- `0x180021e70`
- `0x18002f928`
- `0x18005de08`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18002f951`
- `ntdll!RtlDllShutdownInProgress` at `0x18002f951`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002f9e5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002f9e5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002f94b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002f94b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fa36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fa36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002fa00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002fa00`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18002f999`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18002f999`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f9d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f9d8`

## pseudocode

```c
__int64 __fastcall GarbageCollectionNeeded(int a1, DWORD a2)
{
  RPC_THREAD_POOL_TIMER *v4; // rax
  unsigned int v5; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rbx
  _FILETIME pftDueTime; // [rsp+40h] [rbp+18h] BYREF

  pftDueTime = 0;
  RtlAcquireSRWLockExclusive(&gGarbageCollectionTimerLock);
  if ( RtlDllShutdownInProgress() )
    goto LABEL_12;
  v4 = gGarbageCollectionTimer;
  if ( !gGarbageCollectionTimer )
  {
    if ( !(unsigned int)RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary() )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(PerformGarbageCollection, 0, RPC_THREAD_POOL::CallbackEnvironment);
      if ( ThreadpoolTimer )
      {
        v4 = (RPC_THREAD_POOL_TIMER *)AllocWrapper(8u);
        if ( v4 )
        {
          *(_QWORD *)v4 = ThreadpoolTimer;
          gGarbageCollectionTimer = v4;
          goto LABEL_3;
        }
        CloseThreadpoolTimer(ThreadpoolTimer);
      }
    }
LABEL_12:
    v5 = 0;
    goto LABEL_10;
  }
LABEL_3:
  v5 = 1;
  if ( a1 )
  {
    GarbageCollectionRequested = 1;
  }
  else
  {
    _InterlockedAdd(&PeriodicGarbageCollectItems, 1u);
    v4 = gGarbageCollectionTimer;
  }
  if ( !gGarbageCollectionPeriod || gGarbageCollectionPeriod >= a2 )
    gGarbageCollectionPeriod = a2;
  if ( !IsThreadpoolTimerSet(*(PTP_TIMER *)v4) )
  {
    pftDueTime = (_FILETIME)-(__int64)(10000 * gGarbageCollectionPeriod);
    SetThreadpoolTimer(
      *(PTP_TIMER *)gGarbageCollectionTimer,
      &pftDueTime,
      gGarbageCollectionPeriod,
      gGarbageCollectionPeriod >> 1);
  }
LABEL_10:
  RtlReleaseSRWLockExclusive(&gGarbageCollectionTimerLock);
  return v5;
}

```

## disassembly

```asm
0x18002f928  mov     [rsp+arg_0], rbx
0x18002f92d  mov     [rsp+arg_8], rsi
0x18002f932  push    rdi
0x18002f933  sub     rsp, 20h
0x18002f937  mov     esi, ecx
0x18002f939  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x18002f942  lea     rcx, ?gGarbageCollectionTimerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gGarbageCollectionTimerLock
0x18002f949  mov     edi, edx
0x18002f94b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002f951  call    cs:__imp_RtlDllShutdownInProgress
0x18002f957  test    al, al
0x18002f959  jnz     loc_18002FA06
0x18002f95f  mov     rax, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x18002f966  test    rax, rax
0x18002f969  jz      loc_18002FA1D
0x18002f96f  mov     ebx, 1
0x18002f974  test    esi, esi
0x18002f976  jz      loc_18002FA0A
0x18002f97c  mov     cs:?GarbageCollectionRequested@@3JA, ebx; long GarbageCollectionRequested
0x18002f982  mov     ecx, cs:?gGarbageCollectionPeriod@@3KA; ulong gGarbageCollectionPeriod
0x18002f988  test    ecx, ecx
0x18002f98a  jz      short loc_18002F990
0x18002f98c  cmp     ecx, edi
0x18002f98e  jb      short loc_18002F996
0x18002f990  mov     cs:?gGarbageCollectionPeriod@@3KA, edi; ulong gGarbageCollectionPeriod
0x18002f996  mov     rcx, [rax]; pti
0x18002f999  call    cs:__imp_IsThreadpoolTimerSet
0x18002f99f  test    eax, eax
0x18002f9a1  jnz     short loc_18002F9DE
0x18002f9a3  mov     r8d, cs:?gGarbageCollectionPeriod@@3KA; msPeriod
0x18002f9aa  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18002f9af  imul    eax, r8d, 2710h
0x18002f9b6  mov     r9d, r8d
0x18002f9b9  shr     r9d, 1; msWindowLength
0x18002f9bc  neg     rax
0x18002f9bf  mov     rcx, rax
0x18002f9c2  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18002f9c6  shr     rcx, 20h
0x18002f9ca  mov     [rsp+28h+pftDueTime.dwHighDateTime], ecx
0x18002f9ce  mov     rcx, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x18002f9d5  mov     rcx, [rcx]; pti
0x18002f9d8  call    cs:__imp_SetThreadpoolTimer
0x18002f9de  lea     rcx, ?gGarbageCollectionTimerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gGarbageCollectionTimerLock
0x18002f9e5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002f9eb  mov     rsi, [rsp+28h+arg_8]
0x18002f9f0  mov     eax, ebx
0x18002f9f2  mov     rbx, [rsp+28h+arg_0]
0x18002f9f7  add     rsp, 20h
0x18002f9fb  pop     rdi
0x18002f9fc  retn
0x18002f9fd  mov     rcx, rbx; pti
0x18002fa00  call    cs:__imp_CloseThreadpoolTimer
0x18002fa06  xor     ebx, ebx
0x18002fa08  jmp     short loc_18002F9DE
0x18002fa0a  lock add cs:?PeriodicGarbageCollectItems@@3JA, ebx; long PeriodicGarbageCollectItems
0x18002fa11  mov     rax, cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x18002fa18  jmp     loc_18002F982
0x18002fa1d  call    ?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ; RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
0x18002fa22  test    eax, eax
0x18002fa24  jnz     short loc_18002FA06
0x18002fa26  mov     r8, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; pcbe
0x18002fa2d  lea     rcx, ?PerformGarbageCollection@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002fa34  xor     edx, edx; pv
0x18002fa36  call    cs:__imp_CreateThreadpoolTimer
0x18002fa3c  mov     rbx, rax
0x18002fa3f  test    rax, rax
0x18002fa42  jz      short loc_18002FA06
0x18002fa44  mov     ecx, 8; dwBytes
0x18002fa49  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18002fa4e  test    rax, rax
0x18002fa51  jz      short loc_18002F9FD
0x18002fa53  mov     [rax], rbx
0x18002fa56  mov     cs:?gGarbageCollectionTimer@@3PEAVRPC_THREAD_POOL_TIMER@@EA, rax; RPC_THREAD_POOL_TIMER * gGarbageCollectionTimer
0x18002fa5d  jmp     loc_18002F96F
```
