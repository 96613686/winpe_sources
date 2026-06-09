# StartIISAdminMonitor(void (*)(INETINFO_CRASH_ACTION))

- ea: `0x180025870`
- end: `0x180025a87`
- name: `?StartIISAdminMonitor@@YAJP6AXW4INETINFO_CRASH_ACTION@@@Z@Z`
- size: `535`
- prototype: `__int64 __fastcall(void (__high *)(enum INETINFO_CRASH_ACTION))`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008000`
- `0x180025870`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a04`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800259ec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800259ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025a2f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025a2f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800258fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002597a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800258fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002597a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025a72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025a72`

## string_xrefs

- `0x1800258de`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x18002595a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x1800258c1`: `Start monitoring called when we were all ready monitoring, setting hr to equal %08x\n`
- `0x18002593b`: `Can not create startup complete event for monitoring the inetinfo process, hr = %08x\n`
- `0x1800259b6`: `Can not create shutdown event for monitoring the inetinfo process, hr = %08x\n`

## pseudocode

```c
__int64 __fastcall StartIISAdminMonitor(void (__high *a1)(enum INETINFO_CRASH_ACTION))
{
  HANDLE v2; // rcx
  signed int v3; // ebx
  signed int v4; // eax
  char *v5; // rax
  unsigned int v6; // r8d
  signed int v7; // eax
  signed int LastError; // eax
  void (__high *Parameter)(enum INETINFO_CRASH_ACTION); // [rsp+30h] [rbp-28h] BYREF
  HANDLE hHandle; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+40h] [rbp-18h]

  v11 = 0;
  hHandle = 0;
  Parameter = a1;
  if ( !a1 )
    return 2147942487LL;
  v2 = g_IISAdminMonitorShutdownEvent;
  if ( g_IISAdminMonitorShutdownEvent )
  {
    v3 = -2147418113;
    if ( (g_dwDebugFlagsIISUtil & 3) == 0 )
      goto LABEL_26;
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
      0x87u,
      "StartIISAdminMonitor",
      "Start monitoring called when we were all ready monitoring, setting hr to equal %08x\n",
      255);
LABEL_25:
    v2 = g_IISAdminMonitorShutdownEvent;
LABEL_26:
    if ( v2 )
    {
      CloseHandle(v2);
      g_IISAdminMonitorShutdownEvent = 0;
    }
    goto LABEL_28;
  }
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( hHandle )
  {
    g_IISAdminMonitorShutdownEvent = CreateEventW(0, 1, 0, 0);
    if ( g_IISAdminMonitorShutdownEvent )
    {
      g_hIISAdminMonitorThread = CreateThread(0, 0x8000u, StartMonitoring, &Parameter, 0, &g_dwIISAdminThreadId);
      if ( g_hIISAdminMonitorThread )
      {
        v3 = 0;
        WaitForSingleObject(hHandle, 0xFFFFFFFF);
        goto LABEL_23;
      }
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      {
        v5 = "Can not create shutdown event for monitoring the inetinfo process, hr = %08x\n";
        v6 = 182;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v4 = GetLastError();
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    {
      v5 = "Can not create startup complete event for monitoring the inetinfo process, hr = %08x\n";
      v6 = 153;
LABEL_11:
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
        v6,
        "StartIISAdminMonitor",
        v5,
        v3);
    }
  }
  if ( v3 < 0 )
    goto LABEL_25;
LABEL_23:
  if ( (int)v11 < 0 )
  {
    v3 = v11;
    goto LABEL_25;
  }
LABEL_28:
  if ( hHandle )
    CloseHandle(hHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180025870  push    rbx
0x180025872  sub     rsp, 50h
0x180025876  mov     [rsp+58h+var_18], 0
0x18002587f  mov     [rsp+58h+hHandle], 0
0x180025888  mov     [rsp+58h+Parameter], rcx
0x18002588d  test    rcx, rcx
0x180025890  jnz     short loc_18002589C
0x180025892  mov     eax, 80070057h
0x180025897  jmp     loc_180025A80
0x18002589c  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; void * g_IISAdminMonitorShutdownEvent
0x1800258a3  test    rcx, rcx
0x1800258a6  jz      short loc_1800258EF
0x1800258a8  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800258af  mov     ebx, 8000FFFFh
0x1800258b4  jz      loc_180025A4C
0x1800258ba  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800258c1  lea     rax, aStartMonitorin; "Start monitoring called when we were al"...
0x1800258c8  mov     dword ptr [rsp+58h+lpThreadId], ebx; char
0x1800258cc  lea     r9, aStartiisadminm_0; "StartIISAdminMonitor"
0x1800258d3  mov     r8d, 87h; unsigned int
0x1800258d9  mov     qword ptr [rsp+58h+dwCreationFlags], rax; char *
0x1800258de  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800258e5  call    PuDbgPrint
0x1800258ea  jmp     loc_180025A45
0x1800258ef  xor     r9d, r9d; lpName
0x1800258f2  xor     r8d, r8d; bInitialState
0x1800258f5  xor     ecx, ecx; lpEventAttributes
0x1800258f7  lea     ebx, [r9+1]
0x1800258fb  mov     edx, ebx; bManualReset
0x1800258fd  call    cs:__imp_CreateEventW
0x180025904  nop     dword ptr [rax+rax+00h]
0x180025909  mov     [rsp+58h+hHandle], rax
0x18002590e  test    rax, rax
0x180025911  jnz     short loc_180025970
0x180025913  call    cs:__imp_GetLastError
0x18002591a  nop     dword ptr [rax+rax+00h]
0x18002591f  mov     ebx, eax
0x180025921  test    eax, eax
0x180025923  jle     short loc_18002592E
0x180025925  movzx   ebx, ax
0x180025928  or      ebx, 80070000h
0x18002592e  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180025935  jz      loc_180025A1F
0x18002593b  lea     rax, aCanNotCreateSt; "Can not create startup complete event f"...
0x180025942  mov     r8d, 99h; unsigned int
0x180025948  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002594f  lea     r9, aStartiisadminm_0; "StartIISAdminMonitor"
0x180025956  mov     dword ptr [rsp+58h+lpThreadId], ebx; char
0x18002595a  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180025961  mov     qword ptr [rsp+58h+dwCreationFlags], rax; char *
0x180025966  call    PuDbgPrint
0x18002596b  jmp     loc_180025A1F
0x180025970  xor     r9d, r9d; lpName
0x180025973  xor     r8d, r8d; bInitialState
0x180025976  mov     edx, ebx; bManualReset
0x180025978  xor     ecx, ecx; lpEventAttributes
0x18002597a  call    cs:__imp_CreateEventW
0x180025981  nop     dword ptr [rax+rax+00h]
0x180025986  mov     cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA, rax; void * g_IISAdminMonitorShutdownEvent
0x18002598d  test    rax, rax
0x180025990  jnz     short loc_1800259C5
0x180025992  call    cs:__imp_GetLastError
0x180025999  nop     dword ptr [rax+rax+00h]
0x18002599e  mov     ebx, eax
0x1800259a0  test    eax, eax
0x1800259a2  jle     short loc_1800259AD
0x1800259a4  movzx   ebx, ax
0x1800259a7  or      ebx, 80070000h
0x1800259ad  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800259b4  jz      short loc_180025A1F
0x1800259b6  lea     rax, aCanNotCreateSh; "Can not create shutdown event for monit"...
0x1800259bd  mov     r8d, 0B6h
0x1800259c3  jmp     short loc_180025948
0x1800259c5  lea     rax, ?g_dwIISAdminThreadId@@3KA; ulong g_dwIISAdminThreadId
0x1800259cc  mov     edx, 8000h; dwStackSize
0x1800259d1  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x1800259d6  lea     r9, [rsp+58h+Parameter]; lpParameter
0x1800259db  lea     r8, ?StartMonitoring@@YAKPEAX@Z; lpStartAddress
0x1800259e2  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1800259ea  xor     ecx, ecx; lpThreadAttributes
0x1800259ec  call    cs:__imp_CreateThread
0x1800259f3  nop     dword ptr [rax+rax+00h]
0x1800259f8  mov     cs:?g_hIISAdminMonitorThread@@3PEAXEA, rax; void * g_hIISAdminMonitorThread
0x1800259ff  test    rax, rax
0x180025a02  jnz     short loc_180025A25
0x180025a04  call    cs:__imp_GetLastError
0x180025a0b  nop     dword ptr [rax+rax+00h]
0x180025a10  mov     ebx, eax
0x180025a12  test    eax, eax
0x180025a14  jle     short loc_180025A1F
0x180025a16  movzx   ebx, ax
0x180025a19  or      ebx, 80070000h
0x180025a1f  test    ebx, ebx
0x180025a21  js      short loc_180025A45
0x180025a23  jmp     short loc_180025A3B
0x180025a25  mov     rcx, [rsp+58h+hHandle]; hHandle
0x180025a2a  xor     ebx, ebx
0x180025a2c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180025a2f  call    cs:__imp_WaitForSingleObject
0x180025a36  nop     dword ptr [rax+rax+00h]
0x180025a3b  mov     eax, dword ptr [rsp+58h+var_18]
0x180025a3f  test    eax, eax
0x180025a41  jns     short loc_180025A68
0x180025a43  mov     ebx, eax
0x180025a45  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; hObject
0x180025a4c  test    rcx, rcx
0x180025a4f  jz      short loc_180025A68
0x180025a51  call    cs:__imp_CloseHandle
0x180025a58  nop     dword ptr [rax+rax+00h]
0x180025a5d  mov     cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA, 0; void * g_IISAdminMonitorShutdownEvent
0x180025a68  mov     rcx, [rsp+58h+hHandle]; hObject
0x180025a6d  test    rcx, rcx
0x180025a70  jz      short loc_180025A7E
0x180025a72  call    cs:__imp_CloseHandle
0x180025a79  nop     dword ptr [rax+rax+00h]
0x180025a7e  mov     eax, ebx
0x180025a80  add     rsp, 50h
0x180025a84  pop     rbx
0x180025a85  retn
```
