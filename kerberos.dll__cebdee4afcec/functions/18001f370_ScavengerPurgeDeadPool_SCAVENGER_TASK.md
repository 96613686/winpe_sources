# ScavengerPurgeDeadPool(SCAVENGER_TASK *)

- ea: `0x18001f370`
- end: `0x18001f4a7`
- name: `?ScavengerPurgeDeadPool@@YAXPEAUSCAVENGER_TASK@@@Z`
- size: `311`
- prototype: `void __fastcall(struct SCAVENGER_TASK *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001f1a0`
- `0x1800dcc98`

## callees

- `0x18001f370`
- `0x18001f4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f401`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f401`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001f485`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001f485`
- `ntdll!RtlEnterCriticalSection` at `0x18001f387`
- `ntdll!RtlEnterCriticalSection` at `0x18001f421`
- `ntdll!RtlEnterCriticalSection` at `0x18001f387`
- `ntdll!RtlEnterCriticalSection` at `0x18001f421`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f3e3`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f3e3`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f473`

## pseudocode

```c
void __fastcall ScavengerPurgeDeadPool(struct SCAVENGER_TASK *a1)
{
  unsigned int v2; // esi
  unsigned int v3; // eax
  struct SCAVENGER_TASK *v4; // rbx
  __int64 v5; // rcx
  void *v6; // rdx
  char v7; // di
  struct SCAVENGER_TASK **v8; // rax

  v2 = 0;
  RtlEnterCriticalSection(&ScavengerLock);
LABEL_2:
  v3 = ScavengerDeadPoolSize;
  while ( 1 )
  {
    v4 = ScavengerDeadPool;
    if ( ScavengerDeadPool == (struct SCAVENGER_TASK *)&ScavengerDeadPool || v2 >= v3 )
      break;
    if ( *((struct SCAVENGER_TASK ***)ScavengerDeadPool + 1) != &ScavengerDeadPool
      || (v5 = *(_QWORD *)ScavengerDeadPool,
          *(struct SCAVENGER_TASK **)(*(_QWORD *)ScavengerDeadPool + 8LL) != ScavengerDeadPool) )
    {
LABEL_17:
      __fastfail(3u);
    }
    ScavengerDeadPool = *(struct SCAVENGER_TASK **)ScavengerDeadPool;
    *(_QWORD *)(v5 + 8) = &ScavengerDeadPool;
    ScavengerDeadPoolSize = v3 - 1;
    RtlLeaveCriticalSection(&ScavengerLock);
    if ( v4 == a1 )
      goto LABEL_16;
    v6 = (void *)*((_QWORD *)v4 + 4);
    if ( v6 )
    {
      DeleteTimerQueueTimer(ScavengerTimerQueue, v6, *((HANDLE *)v4 + 6));
      *((_QWORD *)v4 + 4) = 0;
    }
    if ( WaitForSingleObject(*((HANDLE *)v4 + 6), 0) )
    {
LABEL_16:
      v7 = 1;
    }
    else
    {
      v7 = 0;
      ScavengerFreeTask(v4);
    }
    RtlEnterCriticalSection(&ScavengerLock);
    if ( !v7 )
      goto LABEL_2;
    v8 = (struct SCAVENGER_TASK **)qword_180148AE0;
    if ( *(struct SCAVENGER_TASK ***)qword_180148AE0 != &ScavengerDeadPool )
      goto LABEL_17;
    *((_QWORD *)v4 + 1) = qword_180148AE0;
    *(_QWORD *)v4 = &ScavengerDeadPool;
    *v8 = v4;
    v3 = ScavengerDeadPoolSize + 1;
    qword_180148AE0 = (__int64)v4;
    ++ScavengerDeadPoolSize;
    ++v2;
  }
  RtlLeaveCriticalSection(&ScavengerLock);
}

```

## disassembly

```asm
0x18001f370  push    rbx
0x18001f372  push    rbp
0x18001f373  push    rsi
0x18001f374  push    rdi
0x18001f375  push    r14
0x18001f377  sub     rsp, 20h
0x18001f37b  mov     rbp, rcx
0x18001f37e  xor     esi, esi
0x18001f380  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001f387  call    cs:__imp_RtlEnterCriticalSection
0x18001f38d  lea     r14, ?ScavengerDeadPool@@3U_LIST_ENTRY@@A; _LIST_ENTRY ScavengerDeadPool
0x18001f394  mov     eax, cs:?ScavengerDeadPoolSize@@3KA; ulong ScavengerDeadPoolSize
0x18001f39a  mov     rbx, cs:?ScavengerDeadPool@@3U_LIST_ENTRY@@A; _LIST_ENTRY ScavengerDeadPool
0x18001f3a1  cmp     rbx, r14
0x18001f3a4  jz      loc_18001F462
0x18001f3aa  cmp     esi, eax
0x18001f3ac  jnb     loc_18001F462
0x18001f3b2  cmp     [rbx+8], r14
0x18001f3b6  jnz     loc_18001F4A0
0x18001f3bc  mov     rcx, [rbx]
0x18001f3bf  cmp     [rcx+8], rbx
0x18001f3c3  jnz     loc_18001F4A0
0x18001f3c9  mov     cs:?ScavengerDeadPool@@3U_LIST_ENTRY@@A, rcx; _LIST_ENTRY ScavengerDeadPool
0x18001f3d0  dec     eax
0x18001f3d2  mov     [rcx+8], r14
0x18001f3d6  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001f3dd  mov     cs:?ScavengerDeadPoolSize@@3KA, eax; ulong ScavengerDeadPoolSize
0x18001f3e3  call    cs:__imp_RtlLeaveCriticalSection
0x18001f3e9  cmp     rbx, rbp
0x18001f3ec  jz      loc_18001F498
0x18001f3f2  mov     rdx, [rbx+20h]; Timer
0x18001f3f6  test    rdx, rdx
0x18001f3f9  jnz     short loc_18001F47A
0x18001f3fb  mov     rcx, [rbx+30h]; hHandle
0x18001f3ff  xor     edx, edx; dwMilliseconds
0x18001f401  call    cs:__imp_WaitForSingleObject
0x18001f407  test    eax, eax
0x18001f409  jnz     loc_18001F498
0x18001f40f  xor     dil, dil
0x18001f412  mov     rcx, rbx; struct SCAVENGER_TASK *
0x18001f415  call    ?ScavengerFreeTask@@YAXPEAUSCAVENGER_TASK@@@Z; ScavengerFreeTask(SCAVENGER_TASK *)
0x18001f41a  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001f421  call    cs:__imp_RtlEnterCriticalSection
0x18001f427  test    dil, dil
0x18001f42a  jz      loc_18001F394
0x18001f430  mov     rax, cs:qword_180148AE0
0x18001f437  cmp     [rax], r14
0x18001f43a  jnz     short loc_18001F4A0
0x18001f43c  mov     [rbx+8], rax
0x18001f440  mov     [rbx], r14
0x18001f443  mov     [rax], rbx
0x18001f446  mov     eax, cs:?ScavengerDeadPoolSize@@3KA; ulong ScavengerDeadPoolSize
0x18001f44c  inc     eax
0x18001f44e  mov     cs:qword_180148AE0, rbx
0x18001f455  mov     cs:?ScavengerDeadPoolSize@@3KA, eax; ulong ScavengerDeadPoolSize
0x18001f45b  inc     esi
0x18001f45d  jmp     loc_18001F39A
0x18001f462  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ScavengerLock
0x18001f469  add     rsp, 20h
0x18001f46d  pop     r14
0x18001f46f  pop     rdi
0x18001f470  pop     rsi
0x18001f471  pop     rbp
0x18001f472  pop     rbx
0x18001f473  jmp     cs:__imp_RtlLeaveCriticalSection
0x18001f47a  mov     r8, [rbx+30h]; CompletionEvent
0x18001f47e  mov     rcx, cs:?ScavengerTimerQueue@@3PEAXEA; TimerQueue
0x18001f485  call    cs:__imp_DeleteTimerQueueTimer
0x18001f48b  mov     qword ptr [rbx+20h], 0
0x18001f493  jmp     loc_18001F3FB
0x18001f498  mov     dil, 1
0x18001f49b  jmp     loc_18001F41A
0x18001f4a0  mov     ecx, 3
0x18001f4a5  int     29h; Win8: RtlFailFast(ecx)
```
