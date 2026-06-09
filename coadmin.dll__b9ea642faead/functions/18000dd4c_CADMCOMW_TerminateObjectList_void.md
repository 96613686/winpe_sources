# CADMCOMW::TerminateObjectList(void)

- ea: `0x18000dd4c`
- end: `0x18000de2c`
- name: `?TerminateObjectList@CADMCOMW@@SAXXZ`
- size: `224`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a0b0`
- `0x18000a6c0`

## callees

- `0x18000dd4c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000dd87`
- `KERNEL32!CloseHandle` at `0x18000dda4`
- `KERNEL32!CloseHandle` at `0x18000ddc1`
- `KERNEL32!CloseHandle` at `0x18000dd87`
- `KERNEL32!CloseHandle` at `0x18000dda4`
- `KERNEL32!CloseHandle` at `0x18000ddc1`
- `KERNEL32!SignalObjectAndWait` at `0x18000dd72`
- `KERNEL32!SignalObjectAndWait` at `0x18000dd72`
- `KERNEL32!DeleteCriticalSection` at `0x18000dde2`
- `KERNEL32!DeleteCriticalSection` at `0x18000de04`
- `KERNEL32!DeleteCriticalSection` at `0x18000dde2`
- `KERNEL32!DeleteCriticalSection` at `0x18000de04`
- `IisRTL!DestroyRefTraceLog` at `0x18000de16`
- `IisRTL!DestroyRefTraceLog` at `0x18000de16`

## pseudocode

```c
void CADMCOMW::TerminateObjectList(void)
{
  HANDLE v0; // rax

  v0 = NOTIFY_CONTEXT::s_hThread;
  if ( NOTIFY_CONTEXT::s_hThread )
  {
    if ( NOTIFY_CONTEXT::s_hShutdown )
    {
      SignalObjectAndWait(NOTIFY_CONTEXT::s_hShutdown, NOTIFY_CONTEXT::s_hThread, 0xFFFFFFFF, 0);
      v0 = NOTIFY_CONTEXT::s_hThread;
    }
    if ( v0 )
    {
      CloseHandle(v0);
      NOTIFY_CONTEXT::s_hThread = 0;
    }
  }
  if ( NOTIFY_CONTEXT::s_hDataAvailable )
  {
    CloseHandle(NOTIFY_CONTEXT::s_hDataAvailable);
    NOTIFY_CONTEXT::s_hDataAvailable = 0;
  }
  if ( NOTIFY_CONTEXT::s_hShutdown )
  {
    CloseHandle(NOTIFY_CONTEXT::s_hShutdown);
    NOTIFY_CONTEXT::s_hShutdown = 0;
  }
  if ( NOTIFY_CONTEXT::s_fInitializedCritSec )
  {
    DeleteCriticalSection(&NOTIFY_CONTEXT::s_critSec);
    NOTIFY_CONTEXT::s_fInitializedCritSec = 0;
  }
  CADMCOMW::sm_ObjectList = 0;
  DeleteCriticalSection(&CADMCOMW::sm_csObjectListLock);
  if ( CADMCOMW::sm_pDbgRefTraceLog )
  {
    DestroyRefTraceLog();
    CADMCOMW::sm_pDbgRefTraceLog = 0;
  }
}

```

## disassembly

```asm
0x18000dd4c  sub     rsp, 28h
0x18000dd50  mov     rax, cs:?s_hThread@NOTIFY_CONTEXT@@0PEAXEA; void * NOTIFY_CONTEXT::s_hThread
0x18000dd57  test    rax, rax
0x18000dd5a  jz      short loc_18000DD98
0x18000dd5c  mov     rcx, cs:?s_hShutdown@NOTIFY_CONTEXT@@0PEAXEA; hObjectToSignal
0x18000dd63  test    rcx, rcx
0x18000dd66  jz      short loc_18000DD7F
0x18000dd68  xor     r9d, r9d; bAlertable
0x18000dd6b  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000dd6f  mov     rdx, rax; hObjectToWaitOn
0x18000dd72  call    cs:__imp_SignalObjectAndWait
0x18000dd78  mov     rax, cs:?s_hThread@NOTIFY_CONTEXT@@0PEAXEA; void * NOTIFY_CONTEXT::s_hThread
0x18000dd7f  test    rax, rax
0x18000dd82  jz      short loc_18000DD98
0x18000dd84  mov     rcx, rax; hObject
0x18000dd87  call    cs:__imp_CloseHandle
0x18000dd8d  mov     cs:?s_hThread@NOTIFY_CONTEXT@@0PEAXEA, 0; void * NOTIFY_CONTEXT::s_hThread
0x18000dd98  mov     rcx, cs:?s_hDataAvailable@NOTIFY_CONTEXT@@0PEAXEA; hObject
0x18000dd9f  test    rcx, rcx
0x18000dda2  jz      short loc_18000DDB5
0x18000dda4  call    cs:__imp_CloseHandle
0x18000ddaa  mov     cs:?s_hDataAvailable@NOTIFY_CONTEXT@@0PEAXEA, 0; void * NOTIFY_CONTEXT::s_hDataAvailable
0x18000ddb5  mov     rcx, cs:?s_hShutdown@NOTIFY_CONTEXT@@0PEAXEA; hObject
0x18000ddbc  test    rcx, rcx
0x18000ddbf  jz      short loc_18000DDD2
0x18000ddc1  call    cs:__imp_CloseHandle
0x18000ddc7  mov     cs:?s_hShutdown@NOTIFY_CONTEXT@@0PEAXEA, 0; void * NOTIFY_CONTEXT::s_hShutdown
0x18000ddd2  cmp     cs:?s_fInitializedCritSec@NOTIFY_CONTEXT@@0HA, 0; int NOTIFY_CONTEXT::s_fInitializedCritSec
0x18000ddd9  jz      short loc_18000DDF2
0x18000dddb  lea     rcx, ?s_critSec@NOTIFY_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dde2  call    cs:__imp_DeleteCriticalSection
0x18000dde8  mov     cs:?s_fInitializedCritSec@NOTIFY_CONTEXT@@0HA, 0; int NOTIFY_CONTEXT::s_fInitializedCritSec
0x18000ddf2  xorps   xmm0, xmm0
0x18000ddf5  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ddfc  movdqu  cs:?sm_ObjectList@CADMCOMW@@2U_LIST_ENTRY@@A, xmm0; _LIST_ENTRY CADMCOMW::sm_ObjectList
0x18000de04  call    cs:__imp_DeleteCriticalSection
0x18000de0a  mov     rcx, cs:?sm_pDbgRefTraceLog@CADMCOMW@@2PEAU_TRACE_LOG@@EA; _TRACE_LOG * CADMCOMW::sm_pDbgRefTraceLog
0x18000de11  test    rcx, rcx
0x18000de14  jz      short loc_18000DE27
0x18000de16  call    cs:__imp_DestroyRefTraceLog
0x18000de1c  mov     cs:?sm_pDbgRefTraceLog@CADMCOMW@@2PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * CADMCOMW::sm_pDbgRefTraceLog
0x18000de27  add     rsp, 28h
0x18000de2b  retn
```
