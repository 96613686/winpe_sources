# FwLoggerStop

- ea: `0x18006bbe0`
- end: `0x18006bfeb`
- name: `FwLoggerStop`
- size: `1035`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180042098`
- `0x1800526d0`
- `0x18006a7e0`
- `0x180094470`
- `0x180094570`

## callees

- `0x1800091dc`
- `0x1800093b0`
- `0x18000af3c`
- `0x180017110`
- `0x180042f74`
- `0x1800520a4`
- `0x1800525a4`
- `0x18005cb88`
- `0x18006bbe0`
- `0x180079750`
- `0x1800939c4`
- `0x1800e6010`

## import_xrefs

- `ntdll!DbgPrint` at `0x18006bc7a`
- `ntdll!DbgPrint` at `0x18006bca1`
- `ntdll!DbgPrint` at `0x18006bd3c`
- `ntdll!DbgPrint` at `0x18006bf10`
- `ntdll!DbgPrint` at `0x18006bc7a`
- `ntdll!DbgPrint` at `0x18006bca1`
- `ntdll!DbgPrint` at `0x18006bd3c`
- `ntdll!DbgPrint` at `0x18006bf10`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18006bda8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bd1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bf64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bd1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006bf64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006bbf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006be7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006bbf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006be7c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006bfc7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006bfc7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006bf79`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006bf79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006bd2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006bd2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bf16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bf16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006be6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bfd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006be6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bfd4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18006bf8f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18006bf8f`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18006bc92`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18006bc92`

## string_xrefs

- `0x18006bd33`: `FwLoggerStop: WaitForSingleObject(hThread, 45 * 1000) = %d.\n`

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
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9

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
          MicrosoftTelemetryAssertTriggeredNoArgs(v16, v15, v17, v18);
      }
      CloseHandle(EventW);
    }
  }
  FwDeleteProfileToIntIFMapping();
}

```

## disassembly

```asm
0x18006bbe0  push    rbx
0x18006bbe2  push    rbp
0x18006bbe3  push    rsi
0x18006bbe4  push    rdi
0x18006bbe5  push    r12
0x18006bbe7  push    r14
0x18006bbe9  sub     rsp, 38h
0x18006bbed  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006bbf4  call    cs:__imp_EnterCriticalSection
0x18006bbfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bc01  lea     r12, WPP_GLOBAL_Control
0x18006bc08  lea     rbx, aGFw; "g_Fw"
0x18006bc0f  cmp     rcx, r12
0x18006bc12  jz      short loc_18006BC3B
0x18006bc14  test    byte ptr [rcx+1Ch], 4
0x18006bc18  jz      short loc_18006BC3B
0x18006bc1a  mov     rcx, [rcx+10h]
0x18006bc1e  lea     r9, aFwloggerstop; "FwLoggerStop"
0x18006bc25  mov     edx, 12h
0x18006bc2a  mov     [rsp+68h+var_48], rbx
0x18006bc2f  call    WPP_SF_ss
0x18006bc34  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bc3b  cmp     cs:?g_hSession@@3_KA, 0; unsigned __int64 g_hSession
0x18006bc43  mov     r14, cs:?g_hDroppedEventTimer@@3PEAXEA; void * g_hDroppedEventTimer
0x18006bc4a  mov     cs:?g_hDroppedEventTimer@@3PEAXEA, 0; void * g_hDroppedEventTimer
0x18006bc55  mov     cs:?g_fTracingActive@@3EA, 0; uchar g_fTracingActive
0x18006bc5c  jz      loc_18006BF38
0x18006bc62  call    ?FwpAllocateTraceProperties@@YAPEAU_EVENT_TRACE_PROPERTIES@@XZ; FwpAllocateTraceProperties(void)
0x18006bc67  mov     rbp, rax
0x18006bc6a  test    rax, rax
0x18006bc6d  jz      loc_18006BF31
0x18006bc73  lea     rcx, Format; "FwLoggerStop: Calling ControlTrace()\n"
0x18006bc7a  call    cs:__imp_DbgPrint
0x18006bc80  mov     rcx, cs:?g_hSession@@3_KA; TraceHandle
0x18006bc87  mov     r9d, 1; ControlCode
0x18006bc8d  mov     r8, rbp; Properties
0x18006bc90  xor     edx, edx; InstanceName
0x18006bc92  call    cs:__imp_ControlTraceW
0x18006bc98  lea     rcx, aFwloggerstopEx; "FwLoggerStop: Exiting ControlTrace()\n"
0x18006bc9f  mov     edi, eax
0x18006bca1  call    cs:__imp_DbgPrint
0x18006bca7  test    edi, edi
0x18006bca9  jnz     loc_18006BEDD
0x18006bcaf  mov     rsi, cs:?g_hThread@@3PEAXEA; void * g_hThread
0x18006bcb6  lea     rbx, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x18006bcbd  mov     cs:?g_hSession@@3_KA, 0; unsigned __int64 g_hSession
0x18006bcc8  mov     eax, [rbp+58h]
0x18006bccb  mov     cs:?g_ulKernelEventsLostAtShutdown@@3KA, eax; ulong g_ulKernelEventsLostAtShutdown
0x18006bcd1  test    rsi, rsi
0x18006bcd4  jz      loc_18006BEAE
0x18006bcda  mov     cs:?g_hThread@@3PEAXEA, 0; void * g_hThread
0x18006bce5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bcec  cmp     rcx, r12
0x18006bcef  jz      short loc_18006BD16
0x18006bcf1  test    byte ptr [rcx+1Ch], 4
0x18006bcf5  jz      short loc_18006BD16
0x18006bcf7  mov     rcx, [rcx+10h]
0x18006bcfb  lea     rax, aGFw; "g_Fw"
0x18006bd02  lea     edx, [rdi+13h]
0x18006bd05  mov     [rsp+68h+var_48], rax
0x18006bd0a  lea     r9, aFwloggerstop; "FwLoggerStop"
0x18006bd11  call    WPP_SF_ss
0x18006bd16  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006bd1d  call    cs:__imp_LeaveCriticalSection
0x18006bd23  mov     edx, 0AFC8h; dwMilliseconds
0x18006bd28  mov     rcx, rsi; hHandle
0x18006bd2b  call    cs:__imp_WaitForSingleObject
0x18006bd31  mov     edx, eax
0x18006bd33  lea     rcx, aFwloggerstopWa; "FwLoggerStop: WaitForSingleObject(hThre"...
0x18006bd3a  mov     edi, eax
0x18006bd3c  call    cs:__imp_DbgPrint
0x18006bd42  cmp     edi, 102h
0x18006bd48  jnz     loc_18006BE2A
0x18006bd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bd55  cmp     rcx, r12
0x18006bd58  jz      short loc_18006BD71
0x18006bd5a  test    byte ptr [rcx+1Ch], 1
0x18006bd5e  jz      short loc_18006BD71
0x18006bd60  mov     rcx, [rcx+10h]
0x18006bd64  mov     edx, 2Ch ; ','
0x18006bd69  mov     r8, rbx
0x18006bd6c  call    WPP_SF_
0x18006bd71  lea     r8, aGFile; "g_File"
0x18006bd78  lea     rdx, aFwloggerstop; "FwLoggerStop"
0x18006bd7f  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x18006bd86  call    FwEnterCriticalSectionAndTrace
0x18006bd8b  lea     rdi, aGFw; "g_Fw"
0x18006bd92  mov     r8, rdi
0x18006bd95  lea     rdx, aFwloggerstop; "FwLoggerStop"
0x18006bd9c  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwLock
0x18006bda3  call    FwEnterCriticalSectionAndTrace
0x18006bda8  mov     rax, cs:__imp_TerminateThread
0x18006bdaf  mov     edx, 5B4h
0x18006bdb4  mov     rcx, rsi
0x18006bdb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bdbc  test    eax, eax
0x18006bdbe  jnz     short loc_18006BDF3
0x18006bdc0  mov     rax, cs:WPP_GLOBAL_Control
0x18006bdc7  cmp     rax, r12
0x18006bdca  jz      short loc_18006BDF3
0x18006bdcc  test    byte ptr [rax+1Ch], 1
0x18006bdd0  jz      short loc_18006BDF3
0x18006bdd2  call    cs:__imp_GetLastError
0x18006bdd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bddf  mov     edx, 2Dh ; '-'
0x18006bde4  mov     r9d, eax
0x18006bde7  mov     r8, rbx
0x18006bdea  mov     rcx, [rcx+10h]
0x18006bdee  call    WPP_SF_d
0x18006bdf3  mov     r8, rdi
0x18006bdf6  lea     rdx, aFwloggerstop; "FwLoggerStop"
0x18006bdfd  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwLock
0x18006be04  call    FwLeaveCriticalSectionAndTrace
0x18006be09  lea     r8, aGFile; "g_File"
0x18006be10  lea     rdx, aFwloggerstop; "FwLoggerStop"
0x18006be17  lea     rcx, ?g_FwFileLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_FwFileLock
0x18006be1e  call    FwLeaveCriticalSectionAndTrace
0x18006be23  call    ?FwpCleanupTraceThreadResources@@YAXXZ; FwpCleanupTraceThreadResources(void)
0x18006be28  jmp     short loc_18006BE6C
0x18006be2a  test    edi, edi
0x18006be2c  jz      short loc_18006BE65
0x18006be2e  mov     rax, cs:WPP_GLOBAL_Control
0x18006be35  cmp     rax, r12
0x18006be38  jz      short loc_18006BE65
0x18006be3a  test    byte ptr [rax+1Ch], 1
0x18006be3e  jz      short loc_18006BE65
0x18006be40  call    cs:__imp_GetLastError
0x18006be46  mov     rcx, cs:WPP_GLOBAL_Control
0x18006be4d  mov     edx, 2Eh ; '.'
0x18006be52  mov     r9d, edi
0x18006be55  mov     dword ptr [rsp+68h+var_48], eax
0x18006be59  mov     r8, rbx
0x18006be5c  mov     rcx, [rcx+10h]
0x18006be60  call    WPP_SF_dd
0x18006be65  lea     rdi, aGFw; "g_Fw"
0x18006be6c  mov     rcx, rsi; hObject
0x18006be6f  call    cs:__imp_CloseHandle
0x18006be75  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006be7c  call    cs:__imp_EnterCriticalSection
0x18006be82  mov     rcx, cs:WPP_GLOBAL_Control
0x18006be89  cmp     rcx, r12
0x18006be8c  jz      short loc_18006BED1
0x18006be8e  test    byte ptr [rcx+1Ch], 4
0x18006be92  jz      short loc_18006BEB5
0x18006be94  mov     rcx, [rcx+10h]
0x18006be98  lea     r9, aFwloggerstop; "FwLoggerStop"
0x18006be9f  mov     edx, 12h
0x18006bea4  mov     [rsp+68h+var_48], rdi
0x18006bea9  call    WPP_SF_ss
0x18006beae  mov     rcx, cs:WPP_GLOBAL_Control
0x18006beb5  cmp     rcx, r12
0x18006beb8  jz      short loc_18006BED1
0x18006beba  test    byte ptr [rcx+1Ch], 1
0x18006bebe  jz      short loc_18006BED1
0x18006bec0  mov     rcx, [rcx+10h]
0x18006bec4  mov     edx, 2Fh ; '/'
0x18006bec9  mov     r8, rbx
0x18006becc  call    WPP_SF_
0x18006bed1  mov     cs:?g_ulKernelEventsLostAtShutdown@@3KA, 0; ulong g_ulKernelEventsLostAtShutdown
0x18006bedb  jmp     short loc_18006BF16
0x18006bedd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bee4  cmp     rcx, r12
0x18006bee7  jz      short loc_18006BF07
0x18006bee9  test    byte ptr [rcx+1Ch], 1
0x18006beed  jz      short loc_18006BF07
0x18006beef  mov     rcx, [rcx+10h]
0x18006bef3  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x18006befa  mov     edx, 30h ; '0'
0x18006beff  mov     r9d, edi
0x18006bf02  call    WPP_SF_d
0x18006bf07  mov     edx, edi
0x18006bf09  lea     rcx, aFwloggerstopCo; "FwLoggerStop: ControlTrace() = %d.\n"
0x18006bf10  call    cs:__imp_DbgPrint
0x18006bf16  call    cs:__imp_GetProcessHeap
0x18006bf1c  mov     r8, rbp; lpMem
0x18006bf1f  xor     edx, edx; dwFlags
0x18006bf21  mov     rcx, rax; hHeap
0x18006bf24  call    cs:__imp_HeapFree
0x18006bf2a  lea     rbx, aGFw; "g_Fw"
0x18006bf31  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bf38  cmp     rcx, r12
0x18006bf3b  jz      short loc_18006BF5D
0x18006bf3d  test    byte ptr [rcx+1Ch], 4
0x18006bf41  jz      short loc_18006BF5D
0x18006bf43  mov     rcx, [rcx+10h]
0x18006bf47  lea     r9, aFwloggerstop; "FwLoggerStop"
0x18006bf4e  mov     edx, 13h
0x18006bf53  mov     [rsp+68h+var_48], rbx
0x18006bf58  call    WPP_SF_ss
0x18006bf5d  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006bf64  call    cs:__imp_LeaveCriticalSection
0x18006bf6a  test    r14, r14
0x18006bf6d  jz      short loc_18006BFDA
0x18006bf6f  xor     r9d, r9d; lpName
0x18006bf72  xor     r8d, r8d; bInitialState
0x18006bf75  xor     edx, edx; bManualReset
0x18006bf77  xor     ecx, ecx; lpEventAttributes
0x18006bf79  call    cs:__imp_CreateEventW
0x18006bf7f  mov     rbx, rax
0x18006bf82  mov     rcx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x18006bf89  mov     r8, rbx; CompletionEvent
0x18006bf8c  mov     rdx, r14; Timer
0x18006bf8f  call    cs:__imp_DeleteTimerQueueTimer
0x18006bf95  test    eax, eax
0x18006bf97  jnz     short loc_18006BFA6
0x18006bf99  call    cs:__imp_GetLastError
0x18006bf9f  cmp     eax, 3E5h
0x18006bfa4  jnz     short loc_18006BF82
0x18006bfa6  test    rbx, rbx
0x18006bfa9  jz      short loc_18006BFDA
0x18006bfab  or      edi, 0FFFFFFFFh
0x18006bfae  jmp     short loc_18006BFBC
0x18006bfb0  cmp     eax, 0C0h
0x18006bfb5  jz      short loc_18006BFBC
0x18006bfb7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006bfbc  mov     r8d, 1; bAlertable
0x18006bfc2  mov     edx, edi; dwMilliseconds
0x18006bfc4  mov     rcx, rbx; hHandle
0x18006bfc7  call    cs:__imp_WaitForSingleObjectEx
0x18006bfcd  test    eax, eax
0x18006bfcf  jnz     short loc_18006BFB0
0x18006bfd1  mov     rcx, rbx; hObject
0x18006bfd4  call    cs:__imp_CloseHandle
0x18006bfda  add     rsp, 38h
0x18006bfde  pop     r14
0x18006bfe0  pop     r12
0x18006bfe2  pop     rdi
0x18006bfe3  pop     rsi
0x18006bfe4  pop     rbp
0x18006bfe5  pop     rbx
0x18006bfe6  jmp     ?FwDeleteProfileToIntIFMapping@@YAXXZ; FwDeleteProfileToIntIFMapping(void)
```
