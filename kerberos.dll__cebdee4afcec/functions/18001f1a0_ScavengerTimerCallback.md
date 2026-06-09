# ScavengerTimerCallback

- ea: `0x18001f1a0`
- end: `0x18001f36a`
- name: `ScavengerTimerCallback`
- size: `458`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180065644`

## callees

- `0x18001f1a0`
- `0x18001f370`
- `0x18001f4b0`
- `0x180067d50`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f2bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f2bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f1cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f1cd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001f30f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001f30f`
- `ntdll!RtlEnterCriticalSection` at `0x18001f228`
- `ntdll!RtlEnterCriticalSection` at `0x18001f2d6`
- `ntdll!RtlEnterCriticalSection` at `0x18001f322`
- `ntdll!RtlEnterCriticalSection` at `0x18001f228`
- `ntdll!RtlEnterCriticalSection` at `0x18001f2d6`
- `ntdll!RtlEnterCriticalSection` at `0x18001f322`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f24e`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f2a3`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f24e`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f2a3`

## pseudocode

```c
void __fastcall ScavengerTimerCallback(struct SCAVENGER_TASK *a1, char a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // rdx
  unsigned int v6; // esi
  unsigned int v7; // eax
  struct SCAVENGER_TASK *v8; // rdi
  __int64 v9; // rcx
  void *v10; // rdx
  struct SCAVENGER_TASK **v11; // rax

  if ( !_InterlockedCompareExchange((volatile signed __int32 *)a1 + 14, 1, 0) )
  {
    if ( a2 == 1 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = *((_QWORD *)a1 + 10);
      *((_DWORD *)a1 + 4) = CurrentThreadId;
      (*((void (__fastcall **)(struct SCAVENGER_TASK *, __int64))a1 + 8))(a1, v5);
      *((_DWORD *)a1 + 4) = 0;
    }
    if ( !*((_BYTE *)a1 + 21) || !a2 )
      *((_BYTE *)a1 + 20) = 1;
    if ( *((_BYTE *)a1 + 20) )
      ScavengerCancelTask(a1);
    else
      _InterlockedExchange((volatile __int32 *)a1 + 14, 0);
    if ( a2 == 1 )
    {
      v6 = 0;
      RtlEnterCriticalSection(&ScavengerLock);
LABEL_10:
      v7 = ScavengerDeadPoolSize;
      while ( 1 )
      {
        v8 = ScavengerDeadPool;
        if ( ScavengerDeadPool == (struct SCAVENGER_TASK *)&ScavengerDeadPool || v6 >= v7 )
          break;
        if ( *((struct SCAVENGER_TASK ***)ScavengerDeadPool + 1) != &ScavengerDeadPool
          || (v9 = *(_QWORD *)ScavengerDeadPool,
              *(struct SCAVENGER_TASK **)(*(_QWORD *)ScavengerDeadPool + 8LL) != ScavengerDeadPool) )
        {
LABEL_27:
          __fastfail(3u);
        }
        ScavengerDeadPool = *(struct SCAVENGER_TASK **)ScavengerDeadPool;
        *(_QWORD *)(v9 + 8) = &ScavengerDeadPool;
        ScavengerDeadPoolSize = v7 - 1;
        RtlLeaveCriticalSection(&ScavengerLock);
        if ( v8 != a1 )
        {
          v10 = (void *)*((_QWORD *)v8 + 4);
          if ( v10 )
          {
            DeleteTimerQueueTimer(ScavengerTimerQueue, v10, *((HANDLE *)v8 + 6));
            *((_QWORD *)v8 + 4) = 0;
          }
          if ( !WaitForSingleObject(*((HANDLE *)v8 + 6), 0) )
          {
            ScavengerFreeTask(v8);
            RtlEnterCriticalSection(&ScavengerLock);
            goto LABEL_10;
          }
        }
        RtlEnterCriticalSection(&ScavengerLock);
        v11 = (struct SCAVENGER_TASK **)qword_180148AE0;
        if ( *(struct SCAVENGER_TASK ***)qword_180148AE0 != &ScavengerDeadPool )
          goto LABEL_27;
        *((_QWORD *)v8 + 1) = qword_180148AE0;
        *(_QWORD *)v8 = &ScavengerDeadPool;
        *v11 = v8;
        v7 = ScavengerDeadPoolSize + 1;
        qword_180148AE0 = (__int64)v8;
        ++ScavengerDeadPoolSize;
        ++v6;
      }
      RtlLeaveCriticalSection(&ScavengerLock);
    }
    else
    {
      ScavengerPurgeDeadPool(0);
    }
  }
}

```

## disassembly

```asm
0x18001f1a0  mov     [rsp+arg_18], rbx
0x18001f1a5  push    rdi
0x18001f1a6  sub     rsp, 20h
0x18001f1aa  mov     rbx, rcx
0x18001f1ad  movzx   edi, dl
0x18001f1b0  mov     ecx, 1
0x18001f1b5  xor     eax, eax
0x18001f1b7  lock cmpxchg [rbx+38h], ecx
0x18001f1bc  jnz     loc_18001F263
0x18001f1c2  mov     [rsp+28h+arg_0], rbp
0x18001f1c7  xor     ebp, ebp
0x18001f1c9  cmp     dl, cl
0x18001f1cb  jnz     short loc_18001F1E9
0x18001f1cd  call    cs:__imp_GetCurrentThreadId
0x18001f1d3  mov     rdx, [rbx+50h]
0x18001f1d7  mov     rcx, rbx
0x18001f1da  mov     [rbx+10h], eax
0x18001f1dd  mov     rax, [rbx+40h]
0x18001f1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1e6  mov     [rbx+10h], ebp
0x18001f1e9  cmp     [rbx+15h], bpl
0x18001f1ed  jz      loc_18001F35A
0x18001f1f3  test    dil, dil
0x18001f1f6  jz      loc_18001F35A
0x18001f1fc  cmp     [rbx+14h], bpl
0x18001f200  jnz     loc_18001F2E1
0x18001f206  mov     eax, ebp
0x18001f208  xchg    eax, [rbx+38h]
0x18001f20b  cmp     dil, 1
0x18001f20f  jnz     loc_18001F2EE
0x18001f215  mov     [rsp+28h+arg_8], rsi
0x18001f21a  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001f221  mov     [rsp+28h+arg_10], r14
0x18001f226  mov     esi, ebp
0x18001f228  call    cs:__imp_RtlEnterCriticalSection
0x18001f22e  lea     r14, ?ScavengerDeadPool@@3U_LIST_ENTRY@@A; _LIST_ENTRY ScavengerDeadPool
0x18001f235  mov     eax, cs:?ScavengerDeadPoolSize@@3KA; ulong ScavengerDeadPoolSize
0x18001f23b  mov     rdi, cs:?ScavengerDeadPool@@3U_LIST_ENTRY@@A; _LIST_ENTRY ScavengerDeadPool
0x18001f242  cmp     rdi, r14
0x18001f245  jnz     short loc_18001F26E
0x18001f247  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001f24e  call    cs:__imp_RtlLeaveCriticalSection
0x18001f254  mov     rsi, [rsp+28h+arg_8]
0x18001f259  mov     r14, [rsp+28h+arg_10]
0x18001f25e  mov     rbp, [rsp+28h+arg_0]
0x18001f263  mov     rbx, [rsp+28h+arg_18]
0x18001f268  add     rsp, 20h
0x18001f26c  pop     rdi
0x18001f26d  retn
0x18001f26e  cmp     esi, eax
0x18001f270  jnb     short loc_18001F247
0x18001f272  cmp     [rdi+8], r14
0x18001f276  jnz     loc_18001F363
0x18001f27c  mov     rcx, [rdi]
0x18001f27f  cmp     [rcx+8], rdi
0x18001f283  jnz     loc_18001F363
0x18001f289  mov     cs:?ScavengerDeadPool@@3U_LIST_ENTRY@@A, rcx; _LIST_ENTRY ScavengerDeadPool
0x18001f290  dec     eax
0x18001f292  mov     [rcx+8], r14
0x18001f296  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001f29d  mov     cs:?ScavengerDeadPoolSize@@3KA, eax; ulong ScavengerDeadPoolSize
0x18001f2a3  call    cs:__imp_RtlLeaveCriticalSection
0x18001f2a9  cmp     rdi, rbx
0x18001f2ac  jz      short loc_18001F31B
0x18001f2ae  mov     rdx, [rdi+20h]; Timer
0x18001f2b2  test    rdx, rdx
0x18001f2b5  jnz     short loc_18001F304
0x18001f2b7  mov     rcx, [rdi+30h]; hHandle
0x18001f2bb  xor     edx, edx; dwMilliseconds
0x18001f2bd  call    cs:__imp_WaitForSingleObject
0x18001f2c3  test    eax, eax
0x18001f2c5  jnz     short loc_18001F31B
0x18001f2c7  mov     rcx, rdi; struct SCAVENGER_TASK *
0x18001f2ca  call    ?ScavengerFreeTask@@YAXPEAUSCAVENGER_TASK@@@Z; ScavengerFreeTask(SCAVENGER_TASK *)
0x18001f2cf  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001f2d6  call    cs:__imp_RtlEnterCriticalSection
0x18001f2dc  jmp     loc_18001F235
0x18001f2e1  mov     rcx, rbx; struct SCAVENGER_TASK *
0x18001f2e4  call    ?ScavengerCancelTask@@YAXPEAUSCAVENGER_TASK@@@Z; ScavengerCancelTask(SCAVENGER_TASK *)
0x18001f2e9  jmp     loc_18001F20B
0x18001f2ee  xor     ecx, ecx; struct SCAVENGER_TASK *
0x18001f2f0  mov     rbp, [rsp+28h+arg_0]
0x18001f2f5  mov     rbx, [rsp+28h+arg_18]
0x18001f2fa  add     rsp, 20h
0x18001f2fe  pop     rdi
0x18001f2ff  jmp     ?ScavengerPurgeDeadPool@@YAXPEAUSCAVENGER_TASK@@@Z; ScavengerPurgeDeadPool(SCAVENGER_TASK *)
0x18001f304  mov     r8, [rdi+30h]; CompletionEvent
0x18001f308  mov     rcx, cs:?ScavengerTimerQueue@@3PEAXEA; TimerQueue
0x18001f30f  call    cs:__imp_DeleteTimerQueueTimer
0x18001f315  mov     [rdi+20h], rbp
0x18001f319  jmp     short loc_18001F2B7
0x18001f31b  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001f322  call    cs:__imp_RtlEnterCriticalSection
0x18001f328  mov     rax, cs:qword_180148AE0
0x18001f32f  cmp     [rax], r14
0x18001f332  jnz     short loc_18001F363
0x18001f334  mov     [rdi+8], rax
0x18001f338  mov     [rdi], r14
0x18001f33b  mov     [rax], rdi
0x18001f33e  mov     eax, cs:?ScavengerDeadPoolSize@@3KA; ulong ScavengerDeadPoolSize
0x18001f344  inc     eax
0x18001f346  mov     cs:qword_180148AE0, rdi
0x18001f34d  mov     cs:?ScavengerDeadPoolSize@@3KA, eax; ulong ScavengerDeadPoolSize
0x18001f353  inc     esi
0x18001f355  jmp     loc_18001F23B
0x18001f35a  mov     byte ptr [rbx+14h], 1
0x18001f35e  jmp     loc_18001F1FC
0x18001f363  mov     ecx, 3
0x18001f368  int     29h; Win8: RtlFailFast(ecx)
```
