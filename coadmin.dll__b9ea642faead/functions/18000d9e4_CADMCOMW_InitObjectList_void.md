# CADMCOMW::InitObjectList(void)

- ea: `0x18000d9e4`
- end: `0x18000daf3`
- name: `?InitObjectList@CADMCOMW@@SAXXZ`
- size: `271`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a0b0`

## callees

- `0x18000d9e4`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18000dad6`
- `KERNEL32!CreateThread` at `0x18000dad6`
- `KERNEL32!CreateEventA` at `0x18000da86`
- `KERNEL32!CreateEventA` at `0x18000daa2`
- `KERNEL32!CreateEventA` at `0x18000da86`
- `KERNEL32!CreateEventA` at `0x18000daa2`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000da69`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18000da69`
- `KERNEL32!GetLastError` at `0x18000dae8`
- `KERNEL32!GetLastError` at `0x18000dae8`
- `IisRTL!IISInitializeCriticalSection` at `0x18000da04`
- `IisRTL!IISInitializeCriticalSection` at `0x18000da04`
- `IisRTL!CreateRefTraceLog` at `0x18000da1b`
- `IisRTL!CreateRefTraceLog` at `0x18000da1b`

## pseudocode

```c
void CADMCOMW::InitObjectList(void)
{
  struct _TRACE_LOG *RefTraceLog; // rax

  CADMCOMW::sm_ObjectList.Blink = &CADMCOMW::sm_ObjectList;
  CADMCOMW::sm_ObjectList.Flink = &CADMCOMW::sm_ObjectList;
  IISInitializeCriticalSection(&CADMCOMW::sm_csObjectListLock);
  CADMCOMW::sm_fShutdownInProgress = 0;
  RefTraceLog = (struct _TRACE_LOG *)CreateRefTraceLog(4096, 0);
  NOTIFY_CONTEXT::s_hShutdown = 0;
  CADMCOMW::sm_pDbgRefTraceLog = RefTraceLog;
  NOTIFY_CONTEXT::s_hDataAvailable = 0;
  qword_180016ED8 = (__int64)&NOTIFY_CONTEXT::s_listEntry;
  NOTIFY_CONTEXT::s_listEntry.Flink = &NOTIFY_CONTEXT::s_listEntry;
  NOTIFY_CONTEXT::s_fInitializedCritSec = 0;
  if ( !InitializeCriticalSectionAndSpinCount(&NOTIFY_CONTEXT::s_critSec, 0x80000001)
    || (NOTIFY_CONTEXT::s_fInitializedCritSec = 1, (NOTIFY_CONTEXT::s_hShutdown = CreateEventA(0, 1, 0, 0)) == 0)
    || (NOTIFY_CONTEXT::s_hDataAvailable = CreateEventA(0, 0, 0, 0)) == 0
    || (NOTIFY_CONTEXT::s_hThread = CreateThread(
                                      0,
                                      0,
                                      NOTIFY_CONTEXT::NotifyThreadProc,
                                      0,
                                      0,
                                      &NOTIFY_CONTEXT::s_dwThreadId)) == 0 )
  {
    GetLastError();
  }
}

```

## disassembly

```asm
0x18000d9e4  sub     rsp, 38h
0x18000d9e8  lea     rax, ?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x18000d9ef  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CADMCOMW::sm_csObjectListLock
0x18000d9f6  mov     qword ptr cs:?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A+8, rax; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x18000d9fd  mov     qword ptr cs:?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A, rax; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x18000da04  call    cs:__imp_IISInitializeCriticalSection
0x18000da0a  xor     edx, edx
0x18000da0c  mov     cs:?sm_fShutdownInProgress@CADMCOMW@@2HA, 0; int CADMCOMW::sm_fShutdownInProgress
0x18000da16  mov     ecx, 1000h
0x18000da1b  call    cs:__imp_CreateRefTraceLog
0x18000da21  mov     edx, 80000001h; dwSpinCount
0x18000da26  mov     cs:?s_hShutdown@NOTIFY_CONTEXT@@0PEAXEA, 0; void * NOTIFY_CONTEXT::s_hShutdown
0x18000da31  mov     cs:?sm_pDbgRefTraceLog@CADMCOMW@@2PEAU_TRACE_LOG@@EA, rax; _TRACE_LOG * CADMCOMW::sm_pDbgRefTraceLog
0x18000da38  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000da3f  lea     rax, ?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x18000da46  mov     cs:?s_hDataAvailable@NOTIFY_CONTEXT@@0PEAXEA, 0; void * NOTIFY_CONTEXT::s_hDataAvailable
0x18000da51  mov     cs:qword_180016ED8, rax
0x18000da58  mov     cs:?s_listEntry@NOTIFY_CONTEXT@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY NOTIFY_CONTEXT::s_listEntry
0x18000da5f  mov     cs:?s_fInitializedCritSec@NOTIFY_CONTEXT@@0HA, 0; int NOTIFY_CONTEXT::s_fInitializedCritSec
0x18000da69  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000da6f  test    eax, eax
0x18000da71  jz      short loc_18000DAE8
0x18000da73  mov     edx, 1; bManualReset
0x18000da78  xor     r9d, r9d; lpName
0x18000da7b  xor     r8d, r8d; bInitialState
0x18000da7e  mov     cs:?s_fInitializedCritSec@NOTIFY_CONTEXT@@0HA, edx; int NOTIFY_CONTEXT::s_fInitializedCritSec
0x18000da84  xor     ecx, ecx; lpEventAttributes
0x18000da86  call    cs:__imp_CreateEventA
0x18000da8c  mov     cs:?s_hShutdown@NOTIFY_CONTEXT@@0PEAXEA, rax; void * NOTIFY_CONTEXT::s_hShutdown
0x18000da93  test    rax, rax
0x18000da96  jz      short loc_18000DAE8
0x18000da98  xor     r9d, r9d; lpName
0x18000da9b  xor     r8d, r8d; bInitialState
0x18000da9e  xor     edx, edx; bManualReset
0x18000daa0  xor     ecx, ecx; lpEventAttributes
0x18000daa2  call    cs:__imp_CreateEventA
0x18000daa8  mov     cs:?s_hDataAvailable@NOTIFY_CONTEXT@@0PEAXEA, rax; void * NOTIFY_CONTEXT::s_hDataAvailable
0x18000daaf  test    rax, rax
0x18000dab2  jz      short loc_18000DAE8
0x18000dab4  lea     rax, ?s_dwThreadId@NOTIFY_CONTEXT@@0KA; ulong NOTIFY_CONTEXT::s_dwThreadId
0x18000dabb  xor     r9d, r9d; lpParameter
0x18000dabe  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000dac3  lea     r8, ?NotifyThreadProc@NOTIFY_CONTEXT@@CAKPEAX@Z; lpStartAddress
0x18000daca  xor     edx, edx; dwStackSize
0x18000dacc  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000dad4  xor     ecx, ecx; lpThreadAttributes
0x18000dad6  call    cs:__imp_CreateThread
0x18000dadc  mov     cs:?s_hThread@NOTIFY_CONTEXT@@0PEAXEA, rax; void * NOTIFY_CONTEXT::s_hThread
0x18000dae3  test    rax, rax
0x18000dae6  jnz     short loc_18000DAEE
0x18000dae8  call    cs:__imp_GetLastError
0x18000daee  add     rsp, 38h
0x18000daf2  retn
```
