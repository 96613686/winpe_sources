# KerbInitializeScavenger

- ea: `0x1800dcbac`
- end: `0x1800dcc91`
- name: `KerbInitializeScavenger`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x1800802c0`

## callees

- `0x1800dcbac`

## import_xrefs

- `ntdll!RtlDeleteTimerQueue` at `0x1800dcc4e`
- `ntdll!RtlDeleteTimerQueue` at `0x1800dcc4e`
- `ntdll!NtClose` at `0x1800dcc6b`
- `ntdll!NtClose` at `0x1800dcc6b`
- `ntdll!NtCreateEvent` at `0x1800dcc1f`
- `ntdll!NtCreateEvent` at `0x1800dcc1f`
- `ntdll!RtlCreateTimerQueue` at `0x1800dcc32`
- `ntdll!RtlCreateTimerQueue` at `0x1800dcc32`
- `ntdll!RtlDeleteCriticalSection` at `0x1800dcc83`
- `ntdll!RtlDeleteCriticalSection` at `0x1800dcc83`
- `ntdll!RtlInitializeCriticalSection` at `0x1800dcbb9`
- `ntdll!RtlInitializeCriticalSection` at `0x1800dcbb9`

## pseudocode

```c
NTSTATUS KerbInitializeScavenger()
{
  NTSTATUS result; // eax
  NTSTATUS Event; // ebx

  result = RtlInitializeCriticalSection(&ScavengerLock);
  if ( result >= 0 )
  {
    ScavengerTaskQueueSize = 0;
    qword_180148AC8 = (__int64)&ScavengerTaskQueue;
    ScavengerTaskQueue = (struct SCAVENGER_TASK *)&ScavengerTaskQueue;
    ScavengerDeadPoolSize = 0;
    qword_180148AE0 = (__int64)&ScavengerDeadPool;
    ScavengerDeadPool = (struct SCAVENGER_TASK *)&ScavengerDeadPool;
    Event = NtCreateEvent(&ScavengerTimerShutdownEvent, 0x100003u, 0, SynchronizationEvent, 0);
    if ( Event >= 0 )
    {
      Event = RtlCreateTimerQueue(&ScavengerTimerQueue);
      if ( Event >= 0 )
        return 0;
    }
    if ( ScavengerTimerQueue )
    {
      RtlDeleteTimerQueue(ScavengerTimerQueue);
      ScavengerTimerQueue = 0;
    }
    if ( ScavengerTimerShutdownEvent )
    {
      NtClose(ScavengerTimerShutdownEvent);
      ScavengerTimerShutdownEvent = 0;
    }
    RtlDeleteCriticalSection(&ScavengerLock);
    return Event;
  }
  return result;
}

```

## disassembly

```asm
0x1800dcbac  push    rbx
0x1800dcbae  sub     rsp, 30h
0x1800dcbb2  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800dcbb9  call    cs:__imp_RtlInitializeCriticalSection
0x1800dcbbf  test    eax, eax
0x1800dcbc1  js      loc_1800DCC8B
0x1800dcbc7  lea     rax, ?ScavengerTaskQueue@@3U_LIST_ENTRY@@A; _LIST_ENTRY ScavengerTaskQueue
0x1800dcbce  mov     cs:?ScavengerTaskQueueSize@@3KA, 0; ulong ScavengerTaskQueueSize
0x1800dcbd8  mov     cs:qword_180148AC8, rax
0x1800dcbdf  lea     rcx, ?ScavengerTimerShutdownEvent@@3PEAXEA; EventHandle
0x1800dcbe6  mov     cs:?ScavengerTaskQueue@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ScavengerTaskQueue
0x1800dcbed  mov     r9d, 1; EventType
0x1800dcbf3  lea     rax, ?ScavengerDeadPool@@3U_LIST_ENTRY@@A; _LIST_ENTRY ScavengerDeadPool
0x1800dcbfa  mov     cs:?ScavengerDeadPoolSize@@3KA, 0; ulong ScavengerDeadPoolSize
0x1800dcc04  xor     r8d, r8d; ObjectAttributes
0x1800dcc07  mov     cs:qword_180148AE0, rax
0x1800dcc0e  mov     edx, 100003h; DesiredAccess
0x1800dcc13  mov     cs:?ScavengerDeadPool@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ScavengerDeadPool
0x1800dcc1a  mov     [rsp+38h+InitialState], 0; InitialState
0x1800dcc1f  call    cs:__imp_NtCreateEvent
0x1800dcc25  mov     ebx, eax
0x1800dcc27  test    eax, eax
0x1800dcc29  js      short loc_1800DCC42
0x1800dcc2b  lea     rcx, ?ScavengerTimerQueue@@3PEAXEA; TimerQueue
0x1800dcc32  call    cs:__imp_RtlCreateTimerQueue
0x1800dcc38  mov     ebx, eax
0x1800dcc3a  test    eax, eax
0x1800dcc3c  js      short loc_1800DCC42
0x1800dcc3e  xor     ebx, ebx
0x1800dcc40  jmp     short loc_1800DCC89
0x1800dcc42  mov     rcx, cs:?ScavengerTimerQueue@@3PEAXEA; TimerQueue
0x1800dcc49  test    rcx, rcx
0x1800dcc4c  jz      short loc_1800DCC5F
0x1800dcc4e  call    cs:__imp_RtlDeleteTimerQueue
0x1800dcc54  mov     cs:?ScavengerTimerQueue@@3PEAXEA, 0; void * ScavengerTimerQueue
0x1800dcc5f  mov     rcx, cs:?ScavengerTimerShutdownEvent@@3PEAXEA; Handle
0x1800dcc66  test    rcx, rcx
0x1800dcc69  jz      short loc_1800DCC7C
0x1800dcc6b  call    cs:__imp_NtClose
0x1800dcc71  mov     cs:?ScavengerTimerShutdownEvent@@3PEAXEA, 0; void * ScavengerTimerShutdownEvent
0x1800dcc7c  lea     rcx, ?ScavengerLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800dcc83  call    cs:__imp_RtlDeleteCriticalSection
0x1800dcc89  mov     eax, ebx
0x1800dcc8b  add     rsp, 30h
0x1800dcc8f  pop     rbx
0x1800dcc90  retn
```
