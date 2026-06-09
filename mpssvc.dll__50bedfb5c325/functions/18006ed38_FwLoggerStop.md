# FwLoggerStop

- ea: `0x18006ed38`
- end: `0x18006f1bf`
- name: `FwLoggerStop`
- size: `1159`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180042754`
- `0x180056b40`
- `0x18006d5f4`
- `0x180099290`
- `0x1800993a4`

## callees

- `0x1800087cc`
- `0x1800089bc`
- `0x18000a710`
- `0x1800192e0`
- `0x1800436d4`
- `0x180056574`
- `0x180056a14`
- `0x180061864`
- `0x18006ed38`
- `0x18007d3c8`
- `0x180098750`
- `0x1800ec010`

## import_xrefs

- `ntdll!DbgPrint` at `0x18006edd8`
- `ntdll!DbgPrint` at `0x18006ee0b`
- `ntdll!DbgPrint` at `0x18006eeb8`
- `ntdll!DbgPrint` at `0x18006f0aa`
- `ntdll!DbgPrint` at `0x18006edd8`
- `ntdll!DbgPrint` at `0x18006ee0b`
- `ntdll!DbgPrint` at `0x18006eeb8`
- `ntdll!DbgPrint` at `0x18006f0aa`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18006ef2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ef54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f15b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ef54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006efc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f15b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006f18f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006f18f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f12f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f12f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006eea1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006eea1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f110`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f110`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ed4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f010`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ed4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f010`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f0ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f0ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f0b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f0b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006effd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f1a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006effd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f1a2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18006f14b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18006f14b`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18006edf6`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18006edf6`

## string_xrefs

- `0x18006eeaf`: `FwLoggerStop: WaitForSingleObject(hThread, 45 * 1000) = %d.\n`

## pseudocode

```c
void FwLoggerStop()
{
  int v0; // r8d
  __int64 v1; // rcx
  HANDLE v2; // r14
  struct _EVENT_TRACE_PROPERTIES *TraceProperties; // rbp
  ULONG v4; // edi
  int v5; // r8d
  HANDLE v6; // rsi
  DWORD v7; // edi
  DWORD LastError; // eax
  DWORD v9; // eax
  int v10; // r8d
  __int64 v11; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE EventW; // rbx
  DWORD v14; // eax
  __int64 v15; // rcx

  EnterCriticalSection(&g_FwLock);
  v1 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, v0, (unsigned int)"FwLoggerStop", (__int64)"g_Fw");
    v1 = WPP_GLOBAL_Control;
  }
  v2 = g_hDroppedEventTimer;
  g_hDroppedEventTimer = 0;
  g_fTracingActive = 0;
  if ( g_hSession )
  {
    TraceProperties = FwpAllocateTraceProperties();
    if ( !TraceProperties )
    {
LABEL_37:
      v1 = WPP_GLOBAL_Control;
      goto LABEL_38;
    }
    DbgPrint("FwLoggerStop: Calling ControlTrace()\n");
    v4 = ControlTraceW(g_hSession, 0, TraceProperties, 1u);
    DbgPrint("FwLoggerStop: Exiting ControlTrace()\n");
    if ( v4 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 48, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, v4);
      DbgPrint("FwLoggerStop: ControlTrace() = %d.\n", v4);
      goto LABEL_36;
    }
    v6 = g_hThread;
    g_hSession = 0;
    g_ulKernelEventsLostAtShutdown = TraceProperties->EventsLost;
    if ( g_hThread )
    {
      g_hThread = 0;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, v5, (unsigned int)"FwLoggerStop", (__int64)"g_Fw");
      LeaveCriticalSection(&g_FwLock);
      v7 = WaitForSingleObject(v6, 0xAFC8u);
      DbgPrint("FwLoggerStop: WaitForSingleObject(hThread, 45 * 1000) = %d.\n", v7);
      if ( v7 == 258 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids);
        FwEnterCriticalSectionAndTrace(&g_FwFileLock, "FwLoggerStop", "g_File");
        FwEnterCriticalSectionAndTrace(&g_FwLock, "FwLoggerStop", "g_Fw");
        if ( !(unsigned int)((__int64 (__fastcall *)(HANDLE, __int64))TerminateThread)(v6, 1460)
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            45,
            WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids,
            LastError);
        }
        FwLeaveCriticalSectionAndTrace(&g_FwLock, "FwLoggerStop", "g_Fw");
        FwLeaveCriticalSectionAndTrace(&g_FwFileLock, "FwLoggerStop", "g_File");
        FwpCleanupTraceThreadResources();
      }
      else if ( v7
             && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = GetLastError();
        WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 46, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, v7, v9);
      }
      CloseHandle(v6);
      EnterCriticalSection(&g_FwLock);
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_31;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      {
LABEL_28:
        if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_BYTE *)(v11 + 28) & 1) != 0 )
          WPP_SF_(*(_QWORD *)(v11 + 16), 47, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids);
LABEL_31:
        g_ulKernelEventsLostAtShutdown = 0;
LABEL_36:
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, TraceProperties);
        goto LABEL_37;
      }
      WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, v10, (unsigned int)"FwLoggerStop", (__int64)"g_Fw");
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_28;
  }
LABEL_38:
  if ( (_UNKNOWN *)v1 != &WPP_GLOBAL_Control && (*(_BYTE *)(v1 + 28) & 4) != 0 )
    WPP_SF_ss(*(_QWORD *)(v1 + 16), 19, v0, (unsigned int)"FwLoggerStop", (__int64)"g_Fw");
  LeaveCriticalSection(&g_FwLock);
  if ( v2 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    while ( !DeleteTimerQueueTimer(g_hTimerQueue, v2, EventW) && GetLastError() != 997 )
      ;
    if ( EventW )
    {
      while ( 1 )
      {
        v14 = WaitForSingleObjectEx(EventW, 0xFFFFFFFF, 1);
        if ( !v14 )
          break;
        if ( v14 != 192 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v15);
      }
      CloseHandle(EventW);
    }
  }
  FwDeleteProfileToIntIFMapping();
}

```

## disassembly

```asm
0x18006ed38  push    rbx
0x18006ed3a  push    rbp
0x18006ed3b  push    rsi
0x18006ed3c  push    rdi
0x18006ed3d  push    r12
0x18006ed3f  push    r14
0x18006ed41  sub     rsp, 38h
0x18006ed45  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006ed4c  call    cs:__imp_EnterCriticalSection
0x18006ed53  nop     dword ptr [rax+rax+00h]
0x18006ed58  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ed5f  lea     r12, WPP_GLOBAL_Control
0x18006ed66  lea     rbx, aGFw; "g_Fw"
0x18006ed6d  cmp     rcx, r12
0x18006ed70  jz      short loc_18006ED99
0x18006ed72  test    byte ptr [rcx+1Ch], 4
0x18006ed76  jz      short loc_18006ED99
0x18006ed78  mov     rcx, [rcx+10h]
0x18006ed7c  lea     r9, aFwloggerstop; "FwLoggerStop"
0x18006ed83  mov     edx, 12h
0x18006ed88  mov     [rsp+68h+var_48], rbx
0x18006ed8d  call    WPP_SF_ss
0x18006ed92  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ed99  cmp     cs:?g_hSession@@3_KA, 0; unsigned __int64 g_hSession
0x18006eda1  mov     r14, cs:?g_hDroppedEventTimer@@3PEAXEA; void * g_hDroppedEventTimer
0x18006eda8  mov     cs:?g_hDroppedEventTimer@@3PEAXEA, 0; void * g_hDroppedEventTimer
0x18006edb3  mov     cs:?g_fTracingActive@@3EA, 0; uchar g_fTracingActive
0x18006edba  jz      loc_18006F0E4
0x18006edc0  call    ?FwpAllocateTraceProperties@@YAPEAU_EVENT_TRACE_PROPERTIES@@XZ; FwpAllocateTraceProperties(void)
0x18006edc5  mov     rbp, rax
0x18006edc8  test    rax, rax
0x18006edcb  jz      loc_18006F0DD
0x18006edd1  lea     rcx, Format; "FwLoggerStop: Calling ControlTrace()\n"
0x18006edd8  call    cs:__imp_DbgPrint
0x18006eddf  nop     dword ptr [rax+rax+00h]
0x18006ede4  mov     rcx, cs:?g_hSession@@3_KA; TraceHandle
0x18006edeb  mov     r9d, 1; ControlCode
0x18006edf1  mov     r8, rbp; Properties
0x18006edf4  xor     edx, edx; InstanceName
0x18006edf6  call    cs:__imp_ControlTraceW
0x18006edfd  nop     dword ptr [rax+rax+00h]
0x18006ee02  lea     rcx, aFwloggerstopEx; "FwLoggerStop: Exiting ControlTrace()\n"
0x18006ee09  mov     edi, eax
0x18006ee0b  call    cs:__imp_DbgPrint
0x18006ee12  nop     dword ptr [rax+rax+00h]
0x18006ee17  test    edi, edi
0x18006ee19  jnz     loc_18006F077
0x18006ee1f  mov     rsi, cs:?g_hThread@@3PEAXEA; void * g_hThread
0x18006ee26  lea     rbx, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x18006ee2d  mov     cs:?g_hSession@@3_KA, 0; unsigned __int64 g_hSession
0x18006ee38  mov     eax, [rbp+58h]
0x18006ee3b  mov     cs:?g_ulKernelEventsLostAtShutdown@@3KA, eax; ulong g_ulKernelEventsLostAtShutdown
0x18006ee41  test    rsi, rsi
0x18006ee44  jz      loc_18006F048
0x18006ee4a  mov     cs:?g_hThread@@3PEAXEA, 0; void * g_hThread
0x18006ee55  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ee5c  cmp     rcx, r12
0x18006ee5f  jz      short loc_18006EE86
0x18006ee61  test    byte ptr [rcx+1Ch], 4
0x18006ee65  jz      short loc_18006EE86
0x18006ee67  mov     rcx, [rcx+10h]
0x18006ee6b  lea     rax, aGFw; "g_Fw"
0x18006ee72  lea     edx, [rdi+13h]
0x18006ee75  mov     [rsp+68h+var_48], rax
0x18006ee7a  lea     r9, aFwloggerstop; "FwLoggerStop"
0x18006ee81  call    WPP_SF_ss
0x18006ee86  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006ee8d  call    cs:__imp_LeaveCriticalSection
0x18006ee94  nop     dword ptr [rax+rax+00h]
0x18006ee99  mov     edx, 0AFC8h; dwMilliseconds
0x18006ee9e  mov     rcx, rsi; hHandle
0x18006eea1  call    cs:__imp_WaitForSingleObject
0x18006eea8  nop     dword ptr [rax+rax+00h]
0x18006eead  mov     edx, eax
0x18006eeaf  lea     rcx, aFwloggerstopWa; "FwLoggerStop: WaitForSingleObject(hThre"...
0x18006eeb6  mov     edi, eax
0x18006eeb8  call    cs:__imp_DbgPrint
0x18006eebf  nop     dword ptr [rax+rax+00h]
0x18006eec4  cmp     edi, 102h
0x18006eeca  jnz     loc_18006EFB2
0x18006eed0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eed7  cmp     rcx, r12
0x18006eeda  jz      short loc_18006EEF3
0x18006eedc  test    byte ptr [rcx+1Ch], 1
0x18006eee0  jz      short loc_18006EEF3
0x18006eee2  mov     rcx, [rcx+10h]
0x18006eee6  mov     edx, 2Ch ; ','
0x18006eeeb  mov     r8, rbx
0x18006eeee  call    WPP_SF_
0x18006eef3  lea     r8, aGFile; "g_File"
0x18006eefa  lea     rdx, aFwloggerstop; "FwLoggerStop"
0x18006ef01  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x18006ef08  call    FwEnterCriticalSectionAndTrace
0x18006ef0d  lea     rdi, aGFw; "g_Fw"
0x18006ef14  mov     r8, rdi
0x18006ef17  lea     rdx, aFwloggerstop; "FwLoggerStop"
0x18006ef1e  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwLock
0x18006ef25  call    FwEnterCriticalSectionAndTrace
0x18006ef2a  mov     rax, cs:__imp_TerminateThread
0x18006ef31  mov     edx, 5B4h
0x18006ef36  mov     rcx, rsi
0x18006ef39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef3e  test    eax, eax
0x18006ef40  jnz     short loc_18006EF7B
0x18006ef42  mov     rax, cs:WPP_GLOBAL_Control
0x18006ef49  cmp     rax, r12
0x18006ef4c  jz      short loc_18006EF7B
0x18006ef4e  test    byte ptr [rax+1Ch], 1
0x18006ef52  jz      short loc_18006EF7B
0x18006ef54  call    cs:__imp_GetLastError
0x18006ef5b  nop     dword ptr [rax+rax+00h]
0x18006ef60  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ef67  mov     edx, 2Dh ; '-'
0x18006ef6c  mov     r9d, eax
0x18006ef6f  mov     r8, rbx
0x18006ef72  mov     rcx, [rcx+10h]
0x18006ef76  call    WPP_SF_d
0x18006ef7b  mov     r8, rdi
0x18006ef7e  lea     rdx, aFwloggerstop; "FwLoggerStop"
0x18006ef85  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwLock
0x18006ef8c  call    FwLeaveCriticalSectionAndTrace
0x18006ef91  lea     r8, aGFile; "g_File"
0x18006ef98  lea     rdx, aFwloggerstop; "FwLoggerStop"
0x18006ef9f  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x18006efa6  call    FwLeaveCriticalSectionAndTrace
0x18006efab  call    ?FwpCleanupTraceThreadResources@@YAXXZ; FwpCleanupTraceThreadResources(void)
0x18006efb0  jmp     short loc_18006EFFA
0x18006efb2  test    edi, edi
0x18006efb4  jz      short loc_18006EFF3
0x18006efb6  mov     rax, cs:WPP_GLOBAL_Control
0x18006efbd  cmp     rax, r12
0x18006efc0  jz      short loc_18006EFF3
0x18006efc2  test    byte ptr [rax+1Ch], 1
0x18006efc6  jz      short loc_18006EFF3
0x18006efc8  call    cs:__imp_GetLastError
0x18006efcf  nop     dword ptr [rax+rax+00h]
0x18006efd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006efdb  mov     edx, 2Eh ; '.'
0x18006efe0  mov     r9d, edi
0x18006efe3  mov     dword ptr [rsp+68h+var_48], eax
0x18006efe7  mov     r8, rbx
0x18006efea  mov     rcx, [rcx+10h]
0x18006efee  call    WPP_SF_dd
0x18006eff3  lea     rdi, aGFw; "g_Fw"
0x18006effa  mov     rcx, rsi; hObject
0x18006effd  call    cs:__imp_CloseHandle
0x18006f004  nop     dword ptr [rax+rax+00h]
0x18006f009  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006f010  call    cs:__imp_EnterCriticalSection
0x18006f017  nop     dword ptr [rax+rax+00h]
0x18006f01c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f023  cmp     rcx, r12
0x18006f026  jz      short loc_18006F06B
0x18006f028  test    byte ptr [rcx+1Ch], 4
0x18006f02c  jz      short loc_18006F04F
0x18006f02e  mov     rcx, [rcx+10h]
0x18006f032  lea     r9, aFwloggerstop; "FwLoggerStop"
0x18006f039  mov     edx, 12h
0x18006f03e  mov     [rsp+68h+var_48], rdi
0x18006f043  call    WPP_SF_ss
0x18006f048  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f04f  cmp     rcx, r12
0x18006f052  jz      short loc_18006F06B
0x18006f054  test    byte ptr [rcx+1Ch], 1
0x18006f058  jz      short loc_18006F06B
0x18006f05a  mov     rcx, [rcx+10h]
0x18006f05e  mov     edx, 2Fh ; '/'
0x18006f063  mov     r8, rbx
0x18006f066  call    WPP_SF_
0x18006f06b  mov     cs:?g_ulKernelEventsLostAtShutdown@@3KA, 0; ulong g_ulKernelEventsLostAtShutdown
0x18006f075  jmp     short loc_18006F0B6
0x18006f077  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f07e  cmp     rcx, r12
0x18006f081  jz      short loc_18006F0A1
0x18006f083  test    byte ptr [rcx+1Ch], 1
0x18006f087  jz      short loc_18006F0A1
0x18006f089  mov     rcx, [rcx+10h]
0x18006f08d  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x18006f094  mov     edx, 30h ; '0'
0x18006f099  mov     r9d, edi
0x18006f09c  call    WPP_SF_d
0x18006f0a1  mov     edx, edi
0x18006f0a3  lea     rcx, aFwloggerstopCo; "FwLoggerStop: ControlTrace() = %d.\n"
0x18006f0aa  call    cs:__imp_DbgPrint
0x18006f0b1  nop     dword ptr [rax+rax+00h]
0x18006f0b6  call    cs:__imp_GetProcessHeap
0x18006f0bd  nop     dword ptr [rax+rax+00h]
0x18006f0c2  mov     r8, rbp; lpMem
0x18006f0c5  xor     edx, edx; dwFlags
0x18006f0c7  mov     rcx, rax; hHeap
0x18006f0ca  call    cs:__imp_HeapFree
0x18006f0d1  nop     dword ptr [rax+rax+00h]
0x18006f0d6  lea     rbx, aGFw; "g_Fw"
0x18006f0dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f0e4  cmp     rcx, r12
0x18006f0e7  jz      short loc_18006F109
0x18006f0e9  test    byte ptr [rcx+1Ch], 4
0x18006f0ed  jz      short loc_18006F109
0x18006f0ef  mov     rcx, [rcx+10h]
0x18006f0f3  lea     r9, aFwloggerstop; "FwLoggerStop"
0x18006f0fa  mov     edx, 13h
0x18006f0ff  mov     [rsp+68h+var_48], rbx
0x18006f104  call    WPP_SF_ss
0x18006f109  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006f110  call    cs:__imp_LeaveCriticalSection
0x18006f117  nop     dword ptr [rax+rax+00h]
0x18006f11c  test    r14, r14
0x18006f11f  jz      loc_18006F1AE
0x18006f125  xor     r9d, r9d; lpName
0x18006f128  xor     r8d, r8d; bInitialState
0x18006f12b  xor     edx, edx; bManualReset
0x18006f12d  xor     ecx, ecx; lpEventAttributes
0x18006f12f  call    cs:__imp_CreateEventW
0x18006f136  nop     dword ptr [rax+rax+00h]
0x18006f13b  mov     rbx, rax
0x18006f13e  mov     rcx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x18006f145  mov     r8, rbx; CompletionEvent
0x18006f148  mov     rdx, r14; Timer
0x18006f14b  call    cs:__imp_DeleteTimerQueueTimer
0x18006f152  nop     dword ptr [rax+rax+00h]
0x18006f157  test    eax, eax
0x18006f159  jnz     short loc_18006F16E
0x18006f15b  call    cs:__imp_GetLastError
0x18006f162  nop     dword ptr [rax+rax+00h]
0x18006f167  cmp     eax, 3E5h
0x18006f16c  jnz     short loc_18006F13E
0x18006f16e  test    rbx, rbx
0x18006f171  jz      short loc_18006F1AE
0x18006f173  or      edi, 0FFFFFFFFh
0x18006f176  jmp     short loc_18006F184
0x18006f178  cmp     eax, 0C0h
0x18006f17d  jz      short loc_18006F184
0x18006f17f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwWaitStatus == WAIT_IO_COMPLETION")
0x18006f184  mov     r8d, 1; bAlertable
0x18006f18a  mov     edx, edi; dwMilliseconds
0x18006f18c  mov     rcx, rbx; hHandle
0x18006f18f  call    cs:__imp_WaitForSingleObjectEx
0x18006f196  nop     dword ptr [rax+rax+00h]
0x18006f19b  test    eax, eax
0x18006f19d  jnz     short loc_18006F178
0x18006f19f  mov     rcx, rbx; hObject
0x18006f1a2  call    cs:__imp_CloseHandle
0x18006f1a9  nop     dword ptr [rax+rax+00h]
0x18006f1ae  add     rsp, 38h
0x18006f1b2  pop     r14
0x18006f1b4  pop     r12
0x18006f1b6  pop     rdi
0x18006f1b7  pop     rsi
0x18006f1b8  pop     rbp
0x18006f1b9  pop     rbx
0x18006f1ba  jmp     ?FwDeleteProfileToIntIFMapping@@YAXXZ; FwDeleteProfileToIntIFMapping(void)
```
