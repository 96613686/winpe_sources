# StopIISAdminMonitor(void)

- ea: `0x180016830`
- end: `0x180016935`
- name: `?StopIISAdminMonitor@@YAXXZ`
- size: `261`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007300`
- `0x180016830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016877`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016863`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016863`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016840`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016840`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016902`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001691f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016902`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001691f`

## string_xrefs

- `0x1800168a2`: `Failed to wait for iis admin thread to shutdown. hr = %08x\n`
- `0x18001689b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x1800168ef`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x1800168d6`: `Inetinfo monitor thread has completed\n`

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
0x180016830  sub     rsp, 38h
0x180016834  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; hEvent
0x18001683b  test    rcx, rcx
0x18001683e  jz      short loc_18001684D
0x180016840  call    cs:__imp_SetEvent
0x180016846  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; void * g_IISAdminMonitorShutdownEvent
0x18001684d  mov     rax, cs:?g_hIISAdminMonitorThread@@3PEAXEA; void * g_hIISAdminMonitorThread
0x180016854  test    rax, rax
0x180016857  jz      loc_18001691A
0x18001685d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180016860  mov     rcx, rax; hHandle
0x180016863  call    cs:__imp_WaitForSingleObject
0x180016869  test    eax, eax
0x18001686b  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180016871  jz      short loc_1800168BF
0x180016873  test    al, 3
0x180016875  jz      short loc_1800168C1
0x180016877  call    cs:__imp_GetLastError
0x18001687d  test    eax, eax
0x18001687f  jle     short loc_180016889
0x180016881  movzx   eax, ax
0x180016884  or      eax, 80070000h
0x180016889  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180016890  lea     r9, aStopiisadminmo_0; "StopIISAdminMonitor"
0x180016897  mov     dword ptr [rsp+38h+var_10], eax; char
0x18001689b  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800168a2  lea     rax, aFailedToWaitFo; "Failed to wait for iis admin thread to "...
0x1800168a9  mov     r8d, 11Eh; unsigned int
0x1800168af  mov     [rsp+38h+var_18], rax; char *
0x1800168b4  call    PuDbgPrint
0x1800168b9  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800168bf  test    al, 3
0x1800168c1  setnz   cl
0x1800168c4  bt      eax, 1Bh
0x1800168c8  setb    al
0x1800168cb  test    al, cl
0x1800168cd  jz      short loc_1800168FB
0x1800168cf  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800168d6  lea     rax, aInetinfoMonito; "Inetinfo monitor thread has completed\n"
0x1800168dd  lea     r9, aStopiisadminmo_0; "StopIISAdminMonitor"
0x1800168e4  mov     [rsp+38h+var_18], rax; char *
0x1800168e9  mov     r8d, 123h; unsigned int
0x1800168ef  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800168f6  call    PuDbgPrint
0x1800168fb  mov     rcx, cs:?g_hIISAdminMonitorThread@@3PEAXEA; hObject
0x180016902  call    cs:__imp_CloseHandle
0x180016908  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; hObject
0x18001690f  mov     cs:?g_hIISAdminMonitorThread@@3PEAXEA, 0; void * g_hIISAdminMonitorThread
0x18001691a  test    rcx, rcx
0x18001691d  jz      short loc_180016930
0x18001691f  call    cs:__imp_CloseHandle
0x180016925  mov     cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA, 0; void * g_IISAdminMonitorShutdownEvent
0x180016930  add     rsp, 38h
0x180016934  retn
```
