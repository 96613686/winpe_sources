# StopIISAdminMonitor(void)

- ea: `0x180017460`
- end: `0x180017584`
- name: `?StopIISAdminMonitor@@YAXXZ`
- size: `292`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008000`
- `0x180017460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017499`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017499`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017470`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017544`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017567`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017544`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017567`

## string_xrefs

- `0x1800174e4`: `Failed to wait for iis admin thread to shutdown. hr = %08x\n`
- `0x1800174dd`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180017531`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180017518`: `Inetinfo monitor thread has completed\n`

## pseudocode

```c
void StopIISAdminMonitor(void)
{
  HANDLE v0; // rcx
  int v1; // eax
  bool v2; // zf
  char LastError; // al
  char v4; // [rsp+28h] [rbp-10h]

  v0 = g_IISAdminMonitorShutdownEvent;
  if ( g_IISAdminMonitorShutdownEvent )
  {
    SetEvent(g_IISAdminMonitorShutdownEvent);
    v0 = g_IISAdminMonitorShutdownEvent;
  }
  if ( g_hIISAdminMonitorThread )
  {
    v2 = WaitForSingleObject(g_hIISAdminMonitorThread, 0xFFFFFFFF) == 0;
    v1 = g_dwDebugFlagsIISUtil;
    if ( !v2 )
    {
      v2 = (g_dwDebugFlagsIISUtil & 3) == 0;
      if ( (g_dwDebugFlagsIISUtil & 3) == 0 )
      {
LABEL_8:
        if ( !v2 && (v1 & 0x8000000) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
            0x123u,
            "StopIISAdminMonitor",
            "Inetinfo monitor thread has completed\n",
            v4);
        CloseHandle(g_hIISAdminMonitorThread);
        v0 = g_IISAdminMonitorShutdownEvent;
        g_hIISAdminMonitorThread = 0;
        goto LABEL_11;
      }
      LastError = GetLastError();
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
        0x11Eu,
        "StopIISAdminMonitor",
        "Failed to wait for iis admin thread to shutdown. hr = %08x\n",
        LastError);
      v1 = g_dwDebugFlagsIISUtil;
    }
    v2 = (v1 & 3) == 0;
    goto LABEL_8;
  }
LABEL_11:
  if ( v0 )
  {
    CloseHandle(v0);
    g_IISAdminMonitorShutdownEvent = 0;
  }
}

```

## disassembly

```asm
0x180017460  sub     rsp, 38h
0x180017464  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; hEvent
0x18001746b  test    rcx, rcx
0x18001746e  jz      short loc_180017483
0x180017470  call    cs:__imp_SetEvent
0x180017477  nop     dword ptr [rax+rax+00h]
0x18001747c  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; void * g_IISAdminMonitorShutdownEvent
0x180017483  mov     rax, cs:?g_hIISAdminMonitorThread@@3PEAXEA; void * g_hIISAdminMonitorThread
0x18001748a  test    rax, rax
0x18001748d  jz      loc_180017562
0x180017493  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017496  mov     rcx, rax; hHandle
0x180017499  call    cs:__imp_WaitForSingleObject
0x1800174a0  nop     dword ptr [rax+rax+00h]
0x1800174a5  test    eax, eax
0x1800174a7  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800174ad  jz      short loc_180017501
0x1800174af  test    al, 3
0x1800174b1  jz      short loc_180017503
0x1800174b3  call    cs:__imp_GetLastError
0x1800174ba  nop     dword ptr [rax+rax+00h]
0x1800174bf  test    eax, eax
0x1800174c1  jle     short loc_1800174CB
0x1800174c3  movzx   eax, ax
0x1800174c6  or      eax, 80070000h
0x1800174cb  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800174d2  lea     r9, aStopiisadminmo_0; "StopIISAdminMonitor"
0x1800174d9  mov     dword ptr [rsp+38h+var_10], eax; char
0x1800174dd  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800174e4  lea     rax, aFailedToWaitFo; "Failed to wait for iis admin thread to "...
0x1800174eb  mov     r8d, 11Eh; unsigned int
0x1800174f1  mov     [rsp+38h+var_18], rax; char *
0x1800174f6  call    PuDbgPrint
0x1800174fb  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180017501  test    al, 3
0x180017503  setnz   cl
0x180017506  bt      eax, 1Bh
0x18001750a  setb    al
0x18001750d  test    al, cl
0x18001750f  jz      short loc_18001753D
0x180017511  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017518  lea     rax, aInetinfoMonito; "Inetinfo monitor thread has completed\n"
0x18001751f  lea     r9, aStopiisadminmo_0; "StopIISAdminMonitor"
0x180017526  mov     [rsp+38h+var_18], rax; char *
0x18001752b  mov     r8d, 123h; unsigned int
0x180017531  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017538  call    PuDbgPrint
0x18001753d  mov     rcx, cs:?g_hIISAdminMonitorThread@@3PEAXEA; hObject
0x180017544  call    cs:__imp_CloseHandle
0x18001754b  nop     dword ptr [rax+rax+00h]
0x180017550  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; hObject
0x180017557  mov     cs:?g_hIISAdminMonitorThread@@3PEAXEA, 0; void * g_hIISAdminMonitorThread
0x180017562  test    rcx, rcx
0x180017565  jz      short loc_18001757E
0x180017567  call    cs:__imp_CloseHandle
0x18001756e  nop     dword ptr [rax+rax+00h]
0x180017573  mov     cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA, 0; void * g_IISAdminMonitorShutdownEvent
0x18001757e  add     rsp, 38h
0x180017582  retn
```
