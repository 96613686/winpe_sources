# DDMInitializePerformanceCounters

- ea: `0x18001afb8`
- end: `0x18001b1a3`
- name: `DDMInitializePerformanceCounters`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b570`

## callees

- `0x18000b078`
- `0x18000b2b0`
- `0x18001afb8`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x18001afc5`
- `KERNEL32!CreateMutexW` at `0x18001afc5`
- `KERNEL32!GetLastError` at `0x18001b08c`
- `KERNEL32!GetLastError` at `0x18001b0d1`
- `KERNEL32!GetLastError` at `0x18001b08c`
- `KERNEL32!GetLastError` at `0x18001b0d1`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b111`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b132`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b153`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b174`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b195`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b111`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b132`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b153`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b174`
- `ADVAPI32!PerfSetCounterRefValue` at `0x18001b195`
- `ADVAPI32!PerfStopProvider` at `0x18001b066`
- `ADVAPI32!PerfStopProvider` at `0x18001b066`
- `ADVAPI32!PerfStartProviderEx` at `0x18001b021`
- `ADVAPI32!PerfStartProviderEx` at `0x18001b021`
- `ADVAPI32!PerfCreateInstance` at `0x18001b0bf`
- `ADVAPI32!PerfCreateInstance` at `0x18001b0bf`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x18001b04e`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x18001b04e`

## pseudocode

```c
__int64 DDMInitializePerformanceCounters()
{
  const char *v0; // rcx
  ULONG started; // ebx
  void *v2; // r9
  const char *v3; // rcx
  void *v4; // r9
  DWORD LastError; // ebx
  _PROVIDER_CONTEXT ProviderContext; // [rsp+20h] [rbp-38h] BYREF

  g_PerfmonLock = CreateMutexW(0, 0, 0);
  *(_QWORD *)&ProviderContext.ContextSize = 40;
  memset(&ProviderContext.ControlCallback, 0, 32);
  PerfmonGuids = (GUID)RASTotalExGuid;
  started = PerfStartProviderEx(&DdmCountersGuid, &ProviderContext, &DdmCounters);
  if ( started )
    goto LABEL_2;
  started = PerfSetCounterSetInfo(DdmCounters, &RASTotalExInfo, 0xC8u);
  if ( started )
  {
    v0 = (const char *)DdmCounters;
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
  if ( (unsigned int)GetAndTraceLock(v0, "InitializePerfmonCounters", 0xDEu, v2) )
  {
    LastError = PerfmonCounterInitialization;
    if ( !PerfmonCounterInitialization )
    {
      CounterSetInstanceContexts = 0;
      Instance = PerfCreateInstance(DdmCounters, &PerfmonGuids, L"_Default", 0);
      if ( !Instance )
        LastError = GetLastError();
    }
    ReleaseAndTraceLock(v3, "InitializePerfmonCounters", 0xF9u, v4);
  }
  else
  {
    LastError = GetLastError();
  }
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
0x18001afb8  push    rbx
0x18001afba  sub     rsp, 50h
0x18001afbe  xor     r8d, r8d; lpName
0x18001afc1  xor     edx, edx; bInitialOwner
0x18001afc3  xor     ecx, ecx; lpMutexAttributes
0x18001afc5  call    cs:__imp_CreateMutexW
0x18001afcb  movups  xmm0, cs:RASTotalExGuid
0x18001afd2  lea     r8, DdmCounters; Provider
0x18001afd9  mov     cs:g_PerfmonLock, rax
0x18001afe0  lea     rdx, [rsp+58h+ProviderContext]; ProviderContext
0x18001afe5  mov     qword ptr [rsp+58h+ProviderContext.ContextSize], 28h ; '('
0x18001afee  lea     rcx, DdmCountersGuid; ProviderGuid
0x18001aff5  mov     [rsp+58h+ProviderContext.ControlCallback], 0
0x18001affe  movdqu  xmmword ptr cs:?PerfmonGuids@@3PAU_GUID@@A.Data1, xmm0; _GUID near * PerfmonGuids ...
0x18001b006  mov     [rsp+58h+ProviderContext.MemAllocRoutine], 0
0x18001b00f  mov     [rsp+58h+ProviderContext.MemFreeRoutine], 0
0x18001b018  mov     [rsp+58h+ProviderContext.pMemContext], 0
0x18001b021  call    cs:__imp_PerfStartProviderEx
0x18001b027  mov     ebx, eax
0x18001b029  test    eax, eax
0x18001b02b  jz      short loc_18001B03A
0x18001b02d  mov     cs:DdmCounters, 0
0x18001b038  jmp     short loc_18001B070
0x18001b03a  mov     rcx, cs:DdmCounters; ProviderHandle
0x18001b041  lea     rdx, RASTotalExInfo; Template
0x18001b048  mov     r8d, 0C8h; TemplateSize
0x18001b04e  call    cs:__imp_PerfSetCounterSetInfo
0x18001b054  mov     ebx, eax
0x18001b056  test    eax, eax
0x18001b058  jz      short loc_18001B06E
0x18001b05a  mov     rcx, cs:DdmCounters; ProviderHandle
0x18001b061  test    rcx, rcx
0x18001b064  jz      short loc_18001B070
0x18001b066  call    cs:__imp_PerfStopProvider
0x18001b06c  jmp     short loc_18001B02D
0x18001b06e  xor     ebx, ebx
0x18001b070  mov     r8d, 0DEh; unsigned int
0x18001b076  mov     cs:?PerfmonCounterInitialization@@3KA, ebx; ulong PerfmonCounterInitialization
0x18001b07c  lea     rdx, aInitializeperf; "InitializePerfmonCounters"
0x18001b083  call    ?GetAndTraceLock@@YAHPEBD0IPEAX@Z; GetAndTraceLock(char const *,char const *,uint,void *)
0x18001b088  test    eax, eax
0x18001b08a  jnz     short loc_18001B096
0x18001b08c  call    cs:__imp_GetLastError
0x18001b092  mov     ebx, eax
0x18001b094  jmp     short loc_18001B0EB
0x18001b096  mov     ebx, cs:?PerfmonCounterInitialization@@3KA; ulong PerfmonCounterInitialization
0x18001b09c  test    ebx, ebx
0x18001b09e  jnz     short loc_18001B0D9
0x18001b0a0  mov     rcx, cs:DdmCounters; ProviderHandle
0x18001b0a7  lea     r8, Name; "_Default"
0x18001b0ae  xor     r9d, r9d; Id
0x18001b0b1  mov     cs:?CounterSetInstanceContexts@@3PAU_PERFMON_COUNTER_INSTANCE_SET_CONTEXT@@A, rbx; _PERFMON_COUNTER_INSTANCE_SET_CONTEXT near * CounterSetInstanceContexts
0x18001b0b8  lea     rdx, ?PerfmonGuids@@3PAU_GUID@@A; CounterSetGuid
0x18001b0bf  call    cs:__imp_PerfCreateInstance
0x18001b0c5  mov     cs:Instance, rax
0x18001b0cc  test    rax, rax
0x18001b0cf  jnz     short loc_18001B0D9
0x18001b0d1  call    cs:__imp_GetLastError
0x18001b0d7  mov     ebx, eax
0x18001b0d9  mov     r8d, 0F9h; unsigned int
0x18001b0df  lea     rdx, aInitializeperf; "InitializePerfmonCounters"
0x18001b0e6  call    ?ReleaseAndTraceLock@@YAXPEBD0IPEAX@Z; ReleaseAndTraceLock(char const *,char const *,uint,void *)
0x18001b0eb  test    ebx, ebx
0x18001b0ed  jz      short loc_18001B0F6
0x18001b0ef  mov     eax, ebx
0x18001b0f1  jmp     loc_18001B19D
0x18001b0f6  mov     rdx, cs:Instance; Instance
0x18001b0fd  lea     r9, gblTotalConnections; Address
0x18001b104  mov     rcx, cs:DdmCounters; Provider
0x18001b10b  mov     r8d, 1; CounterId
0x18001b111  call    cs:__imp_PerfSetCounterRefValue
0x18001b117  mov     rdx, cs:Instance; Instance
0x18001b11e  lea     r9, gblMaxActiveConnections; Address
0x18001b125  mov     rcx, cs:DdmCounters; Provider
0x18001b12c  mov     r8d, 2; CounterId
0x18001b132  call    cs:__imp_PerfSetCounterRefValue
0x18001b138  mov     rdx, cs:Instance; Instance
0x18001b13f  lea     r9, gblTotalFailedAuth; Address
0x18001b146  mov     rcx, cs:DdmCounters; Provider
0x18001b14d  mov     r8d, 3; CounterId
0x18001b153  call    cs:__imp_PerfSetCounterRefValue
0x18001b159  mov     rdx, cs:Instance; Instance
0x18001b160  lea     r9, gblTotalBytesInDisconnected; Address
0x18001b167  mov     rcx, cs:DdmCounters; Provider
0x18001b16e  mov     r8d, 4; CounterId
0x18001b174  call    cs:__imp_PerfSetCounterRefValue
0x18001b17a  mov     rdx, cs:Instance; Instance
0x18001b181  lea     r9, gblTotalBytesOutDisconnected; Address
0x18001b188  mov     rcx, cs:DdmCounters; Provider
0x18001b18f  mov     r8d, 5; CounterId
0x18001b195  call    cs:__imp_PerfSetCounterRefValue
0x18001b19b  xor     eax, eax
0x18001b19d  add     rsp, 50h
0x18001b1a1  pop     rbx
0x18001b1a2  retn
```
