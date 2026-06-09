# DDMInitializePerformanceCounters

- ea: `0x18001b924`
- end: `0x18001bb4f`
- name: `DDMInitializePerformanceCounters`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bf40`

## callees

- `0x18000b358`
- `0x18000b594`
- `0x18001b924`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x18001b931`
- `KERNEL32!CreateMutexW` at `0x18001b931`
- `KERNEL32!GetLastError` at `0x18001ba07`
- `KERNEL32!GetLastError` at `0x18001ba58`
- `KERNEL32!GetLastError` at `0x18001ba07`
- `KERNEL32!GetLastError` at `0x18001ba58`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001ba9e`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001bac5`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001baec`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001bb13`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001bb3a`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001ba9e`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001bac5`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001baec`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001bb13`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001bb3a`
- `ADVAPI32!PerfStopProvider` at `0x18001b9d9`
- `ADVAPI32!PerfStopProvider` at `0x18001b9d9`
- `ADVAPI32!PerfStartProviderEx` at `0x18001b98b`
- `ADVAPI32!PerfStartProviderEx` at `0x18001b98b`
- `ADVAPI32!PerfCreateInstance` at `0x18001ba40`
- `ADVAPI32!PerfCreateInstance` at `0x18001ba40`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x18001b9bb`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x18001b9bb`

## pseudocode

```c
__int64 DDMInitializePerformanceCounters()
{
  HANDLE MutexW; // rax
  const char *v1; // rcx
  ULONG started; // ebx
  void *v3; // r9
  DWORD LastError; // ebx
  const char *v5; // rcx
  void *v6; // r9
  DWORD v7; // eax
  _PROVIDER_CONTEXT ProviderContext; // [rsp+20h] [rbp-38h] BYREF

  MutexW = CreateMutexW(0, 0, 0);
  memset(&ProviderContext.Reserved, 0, 36);
  PerfmonGuids = (GUID)RASTotalExGuid;
  g_PerfmonLock = MutexW;
  ProviderContext.ContextSize = 40;
  started = PerfStartProviderEx(&DdmCountersGuid, &ProviderContext, &DdmCounters);
  if ( started )
    goto LABEL_2;
  started = PerfSetCounterSetInfo(DdmCounters, &RASTotalExInfo, 0xC8u);
  if ( started )
  {
    v1 = (const char *)DdmCounters;
    if ( DdmCounters )
    {
      PerfStopProvider(DdmCounters);
LABEL_2:
      DdmCounters = 0;
    }
  }
  else
  {
    started = 0;
  }
  PerfmonCounterInitialization = started;
  LastError = 0;
  if ( !(unsigned int)GetAndTraceLock(v1, "InitializePerfmonCounters", 0xDEu, v3) )
  {
    LastError = GetLastError();
    goto LABEL_14;
  }
  v7 = PerfmonCounterInitialization;
  if ( PerfmonCounterInitialization )
    goto LABEL_12;
  CounterSetInstanceContexts = 0;
  Instance = PerfCreateInstance(DdmCounters, &PerfmonGuids, L"_Default", 0);
  if ( !Instance )
  {
    v7 = GetLastError();
LABEL_12:
    LastError = v7;
  }
  ReleaseAndTraceLock(v5, "InitializePerfmonCounters", 0xF9u, v6);
LABEL_14:
  if ( LastError )
    return LastError;
  PerfSetCounterRefValue(DdmCounters, Instance, 1u, &gblTotalConnections);
  PerfSetCounterRefValue(DdmCounters, Instance, 2u, &gblMaxActiveConnections);
  PerfSetCounterRefValue(DdmCounters, Instance, 3u, &gblTotalFailedAuth);
  PerfSetCounterRefValue(DdmCounters, Instance, 4u, &gblTotalBytesInDisconnected);
  PerfSetCounterRefValue(DdmCounters, Instance, 5u, &gblTotalBytesOutDisconnected);
  return 0;
}

```

## disassembly

```asm
0x18001b924  push    rbx
0x18001b926  sub     rsp, 50h
0x18001b92a  xor     r8d, r8d; lpName
0x18001b92d  xor     edx, edx; bInitialOwner
0x18001b92f  xor     ecx, ecx; lpMutexAttributes
0x18001b931  call    cs:__imp_CreateMutexW
0x18001b938  nop     dword ptr [rax+rax+00h]
0x18001b93d  movups  xmm0, cs:RASTotalExGuid
0x18001b944  and     [rsp+58h+ProviderContext.Reserved], 0
0x18001b949  lea     r8, DdmCounters; Provider
0x18001b950  and     [rsp+58h+ProviderContext.ControlCallback], 0
0x18001b956  lea     rdx, [rsp+58h+ProviderContext]; ProviderContext
0x18001b95b  and     [rsp+58h+ProviderContext.MemAllocRoutine], 0
0x18001b961  lea     rcx, DdmCountersGuid; ProviderGuid
0x18001b968  and     [rsp+58h+ProviderContext.MemFreeRoutine], 0
0x18001b96e  and     [rsp+58h+ProviderContext.pMemContext], 0
0x18001b974  movdqu  xmmword ptr cs:?PerfmonGuids@@3PAU_GUID@@A.Data1, xmm0; _GUID near * PerfmonGuids ...
0x18001b97c  mov     cs:g_PerfmonLock, rax
0x18001b983  mov     [rsp+58h+ProviderContext.ContextSize], 28h ; '('
0x18001b98b  call    cs:__imp_PerfStartProviderEx
0x18001b992  nop     dword ptr [rax+rax+00h]
0x18001b997  mov     ebx, eax
0x18001b999  test    eax, eax
0x18001b99b  jz      short loc_18001B9A7
0x18001b99d  and     cs:DdmCounters, 0
0x18001b9a5  jmp     short loc_18001B9E9
0x18001b9a7  mov     rcx, cs:DdmCounters; ProviderHandle
0x18001b9ae  lea     rdx, RASTotalExInfo; Template
0x18001b9b5  mov     r8d, 0C8h; TemplateSize
0x18001b9bb  call    cs:__imp_PerfSetCounterSetInfo
0x18001b9c2  nop     dword ptr [rax+rax+00h]
0x18001b9c7  mov     ebx, eax
0x18001b9c9  test    eax, eax
0x18001b9cb  jz      short loc_18001B9E7
0x18001b9cd  mov     rcx, cs:DdmCounters; ProviderHandle
0x18001b9d4  test    rcx, rcx
0x18001b9d7  jz      short loc_18001B9E9
0x18001b9d9  call    cs:__imp_PerfStopProvider
0x18001b9e0  nop     dword ptr [rax+rax+00h]
0x18001b9e5  jmp     short loc_18001B99D
0x18001b9e7  xor     ebx, ebx
0x18001b9e9  mov     cs:?PerfmonCounterInitialization@@3KA, ebx; ulong PerfmonCounterInitialization
0x18001b9ef  lea     rdx, aInitializeperf; "InitializePerfmonCounters"
0x18001b9f6  mov     r8d, 0DEh; unsigned int
0x18001b9fc  xor     ebx, ebx
0x18001b9fe  call    ?GetAndTraceLock@@YAHPEBD0IPEAX@Z; GetAndTraceLock(char const *,char const *,uint,void *)
0x18001ba03  test    eax, eax
0x18001ba05  jnz     short loc_18001BA17
0x18001ba07  call    cs:__imp_GetLastError
0x18001ba0e  nop     dword ptr [rax+rax+00h]
0x18001ba13  mov     ebx, eax
0x18001ba15  jmp     short loc_18001BA78
0x18001ba17  mov     eax, cs:?PerfmonCounterInitialization@@3KA; ulong PerfmonCounterInitialization
0x18001ba1d  test    eax, eax
0x18001ba1f  jnz     short loc_18001BA64
0x18001ba21  mov     rcx, cs:DdmCounters; ProviderHandle
0x18001ba28  lea     r8, Name; "_Default"
0x18001ba2f  and     cs:?CounterSetInstanceContexts@@3PAU_PERFMON_COUNTER_INSTANCE_SET_CONTEXT@@A, rbx; _PERFMON_COUNTER_INSTANCE_SET_CONTEXT near * CounterSetInstanceContexts
0x18001ba36  lea     rdx, ?PerfmonGuids@@3PAU_GUID@@A; CounterSetGuid
0x18001ba3d  xor     r9d, r9d; Id
0x18001ba40  call    cs:__imp_PerfCreateInstance
0x18001ba47  nop     dword ptr [rax+rax+00h]
0x18001ba4c  mov     cs:Instance, rax
0x18001ba53  test    rax, rax
0x18001ba56  jnz     short loc_18001BA66
0x18001ba58  call    cs:__imp_GetLastError
0x18001ba5f  nop     dword ptr [rax+rax+00h]
0x18001ba64  mov     ebx, eax
0x18001ba66  mov     r8d, 0F9h; unsigned int
0x18001ba6c  lea     rdx, aInitializeperf; "InitializePerfmonCounters"
0x18001ba73  call    ?ReleaseAndTraceLock@@YAXPEBD0IPEAX@Z; ReleaseAndTraceLock(char const *,char const *,uint,void *)
0x18001ba78  test    ebx, ebx
0x18001ba7a  jz      short loc_18001BA83
0x18001ba7c  mov     eax, ebx
0x18001ba7e  jmp     loc_18001BB48
0x18001ba83  mov     rdx, cs:Instance; Instance
0x18001ba8a  lea     r9, gblTotalConnections; Address
0x18001ba91  mov     rcx, cs:DdmCounters; Provider
0x18001ba98  mov     r8d, 1; CounterId
0x18001ba9e  call    cs:__imp_PerfSetCounterRefValue
0x18001baa5  nop     dword ptr [rax+rax+00h]
0x18001baaa  mov     rdx, cs:Instance; Instance
0x18001bab1  lea     r9, gblMaxActiveConnections; Address
0x18001bab8  mov     rcx, cs:DdmCounters; Provider
0x18001babf  mov     r8d, 2; CounterId
0x18001bac5  call    cs:__imp_PerfSetCounterRefValue
0x18001bacc  nop     dword ptr [rax+rax+00h]
0x18001bad1  mov     rdx, cs:Instance; Instance
0x18001bad8  lea     r9, gblTotalFailedAuth; Address
0x18001badf  mov     rcx, cs:DdmCounters; Provider
0x18001bae6  mov     r8d, 3; CounterId
0x18001baec  call    cs:__imp_PerfSetCounterRefValue
0x18001baf3  nop     dword ptr [rax+rax+00h]
0x18001baf8  mov     rdx, cs:Instance; Instance
0x18001baff  lea     r9, gblTotalBytesInDisconnected; Address
0x18001bb06  mov     rcx, cs:DdmCounters; Provider
0x18001bb0d  mov     r8d, 4; CounterId
0x18001bb13  call    cs:__imp_PerfSetCounterRefValue
0x18001bb1a  nop     dword ptr [rax+rax+00h]
0x18001bb1f  mov     rdx, cs:Instance; Instance
0x18001bb26  lea     r9, gblTotalBytesOutDisconnected; Address
0x18001bb2d  mov     rcx, cs:DdmCounters; Provider
0x18001bb34  mov     r8d, 5; CounterId
0x18001bb3a  call    cs:__imp_PerfSetCounterRefValue
0x18001bb41  nop     dword ptr [rax+rax+00h]
0x18001bb46  xor     eax, eax
0x18001bb48  add     rsp, 50h
0x18001bb4c  pop     rbx
0x18001bb4d  retn
```
