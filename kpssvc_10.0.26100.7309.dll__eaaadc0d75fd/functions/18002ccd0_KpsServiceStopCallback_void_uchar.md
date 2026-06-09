# KpsServiceStopCallback(void *,uchar)

- ea: `0x18002ccd0`
- end: `0x18002cf54`
- name: `?KpsServiceStopCallback@@YAXPEAXE@Z`
- size: `644`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001a868`
- `0x18001ada8`
- `0x18001ae0c`
- `0x18001ae7c`
- `0x18001b1a0`
- `0x18001b1f4`
- `0x180021828`
- `0x18002a080`
- `0x18002ccd0`
- `0x18002d904`
- `0x18002fd30`
- `0x18002febc`
- `0x18003100e`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cd33`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cd33`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002cd89`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002cd89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002ce14`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002ce14`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002ce01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002ce01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002cdee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002cdee`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002cea1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002cea1`
- `KERNEL32!UnregisterWait` at `0x18002ce36`
- `KERNEL32!UnregisterWait` at `0x18002ce36`

## pseudocode

```c
void __fastcall KpsServiceStopCallback(void *a1, unsigned __int8 a2)
{
  DWORD v2; // ebx
  DWORD LastError; // eax
  DWORD v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // r8
  _BYTE v10[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, a1, a2);
  v2 = WaitForSingleObject(hMutex, 0xFFFFFFFF);
  if ( v2 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v2, LastError);
  }
  if ( !ResetEvent(hEvent)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = GetLastError();
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v2, v4);
  }
  KpsSqmFlushAll();
  KpsHttpShutdown(v6, v5, v7);
  CloseThreadpoolCleanupGroupMembers(ptpcg, 1, 0);
  CloseThreadpoolCleanupGroup(ptpcg);
  CloseThreadpool(ptpp);
  KpsGPShutdown();
  KpsKerbShutdown();
  KpsPerfShutdown();
  UnregisterWait(WaitHandle);
  CloseHandle(qword_18003AD30);
  CloseHandle(hEvent);
  CloseHandle(hMutex);
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWaitHint = 0;
  ServiceStatus.dwCurrentState = 1;
  SetServiceStatus(hServiceStatus, &ServiceStatus);
  memset_0(&KpsServiceData, 0, 0xA8u);
  if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v8, ServiceStop, v9, 1, v10);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids);
  McGenEventUnregister_EventUnregister();
  KpsUnloadDebugTrace();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids);
}

```

## disassembly

```asm
0x18002ccd0  mov     [rsp+arg_8], rbx
0x18002ccd5  mov     [rsp+arg_10], rsi
0x18002ccda  push    rdi
0x18002ccdb  sub     rsp, 50h
0x18002ccdf  mov     rax, cs:__security_cookie
0x18002cce6  xor     rax, rsp
0x18002cce9  mov     [rsp+58h+var_18], rax
0x18002ccee  mov     r9, rcx
0x18002ccf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccf8  lea     rdi, WPP_GLOBAL_Control
0x18002ccff  lea     rsi, WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids
0x18002cd06  cmp     rcx, rdi
0x18002cd09  jz      short loc_18002CD29
0x18002cd0b  test    byte ptr [rcx+1Ch], 20h
0x18002cd0f  jz      short loc_18002CD29
0x18002cd11  mov     rcx, [rcx+10h]
0x18002cd15  mov     r8, rsi
0x18002cd18  movzx   eax, dl
0x18002cd1b  mov     edx, 0Fh
0x18002cd20  mov     dword ptr [rsp+58h+var_38], eax
0x18002cd24  call    WPP_SF_qd
0x18002cd29  mov     rcx, cs:hMutex; hHandle
0x18002cd30  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002cd33  call    cs:__imp_WaitForSingleObject
0x18002cd3a  nop     dword ptr [rax+rax+00h]
0x18002cd3f  mov     ebx, eax
0x18002cd41  test    eax, eax
0x18002cd43  jz      short loc_18002CD82
0x18002cd45  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd4c  cmp     rcx, rdi
0x18002cd4f  jz      short loc_18002CD82
0x18002cd51  test    byte ptr [rcx+1Ch], 1
0x18002cd55  jz      short loc_18002CD82
0x18002cd57  call    cs:__imp_GetLastError
0x18002cd5e  nop     dword ptr [rax+rax+00h]
0x18002cd63  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd6a  mov     edx, 10h
0x18002cd6f  mov     r9d, ebx
0x18002cd72  mov     dword ptr [rsp+58h+var_38], eax
0x18002cd76  mov     r8, rsi
0x18002cd79  mov     rcx, [rcx+10h]
0x18002cd7d  call    WPP_SF_dD
0x18002cd82  mov     rcx, cs:hEvent; hEvent
0x18002cd89  call    cs:__imp_ResetEvent
0x18002cd90  nop     dword ptr [rax+rax+00h]
0x18002cd95  test    eax, eax
0x18002cd97  jnz     short loc_18002CDD6
0x18002cd99  mov     rax, cs:WPP_GLOBAL_Control
0x18002cda0  cmp     rax, rdi
0x18002cda3  jz      short loc_18002CDD6
0x18002cda5  test    byte ptr [rax+1Ch], 1
0x18002cda9  jz      short loc_18002CDD6
0x18002cdab  call    cs:__imp_GetLastError
0x18002cdb2  nop     dword ptr [rax+rax+00h]
0x18002cdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cdbe  mov     edx, 11h
0x18002cdc3  mov     r9d, ebx
0x18002cdc6  mov     dword ptr [rsp+58h+var_38], eax
0x18002cdca  mov     r8, rsi
0x18002cdcd  mov     rcx, [rcx+10h]
0x18002cdd1  call    WPP_SF_dD
0x18002cdd6  call    ?KpsSqmFlushAll@@YAXXZ; KpsSqmFlushAll(void)
0x18002cddb  call    ?KpsHttpShutdown@@YAXXZ; KpsHttpShutdown(void)
0x18002cde0  mov     rcx, cs:ptpcg; ptpcg
0x18002cde7  xor     r8d, r8d; pvCleanupContext
0x18002cdea  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18002cdee  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002cdf5  nop     dword ptr [rax+rax+00h]
0x18002cdfa  mov     rcx, cs:ptpcg; ptpcg
0x18002ce01  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002ce08  nop     dword ptr [rax+rax+00h]
0x18002ce0d  mov     rcx, cs:ptpp; ptpp
0x18002ce14  call    cs:__imp_CloseThreadpool
0x18002ce1b  nop     dword ptr [rax+rax+00h]
0x18002ce20  call    ?KpsGPShutdown@@YAXXZ; KpsGPShutdown(void)
0x18002ce25  call    ?KpsKerbShutdown@@YAXXZ; KpsKerbShutdown(void)
0x18002ce2a  call    ?KpsPerfShutdown@@YAXXZ; KpsPerfShutdown(void)
0x18002ce2f  mov     rcx, cs:WaitHandle; WaitHandle
0x18002ce36  call    cs:__imp_UnregisterWait
0x18002ce3d  nop     dword ptr [rax+rax+00h]
0x18002ce42  mov     rcx, cs:qword_18003AD30; hObject
0x18002ce49  call    cs:__imp_CloseHandle
0x18002ce50  nop     dword ptr [rax+rax+00h]
0x18002ce55  mov     rcx, cs:hEvent; hObject
0x18002ce5c  call    cs:__imp_CloseHandle
0x18002ce63  nop     dword ptr [rax+rax+00h]
0x18002ce68  mov     rcx, cs:hMutex; hObject
0x18002ce6f  call    cs:__imp_CloseHandle
0x18002ce76  nop     dword ptr [rax+rax+00h]
0x18002ce7b  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18002ce82  lea     rdx, ServiceStatus; lpServiceStatus
0x18002ce89  and     cs:ServiceStatus.dwCheckPoint, 0
0x18002ce90  and     cs:ServiceStatus.dwWaitHint, 0
0x18002ce97  mov     cs:ServiceStatus.dwCurrentState, 1
0x18002cea1  call    cs:__imp_SetServiceStatus
0x18002cea8  nop     dword ptr [rax+rax+00h]
0x18002cead  xor     edx, edx; Val
0x18002ceaf  lea     rcx, ?KpsServiceData@@3U_KPS_SERVICE_DATA@@A; void *
0x18002ceb6  mov     r8d, 0A8h; Size
0x18002cebc  call    memset_0
0x18002cec1  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 8
0x18002cec8  jz      short loc_18002CEE6
0x18002ceca  lea     rax, [rsp+58h+var_28]
0x18002cecf  mov     r9d, 1
0x18002ced5  lea     rdx, ServiceStop
0x18002cedc  mov     [rsp+58h+var_38], rax
0x18002cee1  call    McGenEventWrite_EventWriteTransfer
0x18002cee6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ceed  cmp     rcx, rdi
0x18002cef0  jz      short loc_18002CF09
0x18002cef2  test    byte ptr [rcx+1Ch], 10h
0x18002cef6  jz      short loc_18002CF09
0x18002cef8  mov     rcx, [rcx+10h]
0x18002cefc  mov     edx, 12h
0x18002cf01  mov     r8, rsi
0x18002cf04  call    WPP_SF_
0x18002cf09  call    McGenEventUnregister_EventUnregister
0x18002cf0e  call    ?KpsUnloadDebugTrace@@YAXXZ; KpsUnloadDebugTrace(void)
0x18002cf13  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf1a  cmp     rcx, rdi
0x18002cf1d  jz      short loc_18002CF36
0x18002cf1f  test    byte ptr [rcx+1Ch], 20h
0x18002cf23  jz      short loc_18002CF36
0x18002cf25  mov     rcx, [rcx+10h]
0x18002cf29  mov     edx, 13h
0x18002cf2e  mov     r8, rsi
0x18002cf31  call    WPP_SF_
0x18002cf36  mov     rcx, [rsp+58h+var_18]
0x18002cf3b  xor     rcx, rsp; StackCookie
0x18002cf3e  call    __security_check_cookie
0x18002cf43  mov     rbx, [rsp+58h+arg_8]
0x18002cf48  mov     rsi, [rsp+58h+arg_10]
0x18002cf4d  add     rsp, 50h
0x18002cf51  pop     rdi
0x18002cf52  retn
```
