# StartIISAdminMonitor(void (*)(INETINFO_CRASH_ACTION))

- ea: `0x180023e70`
- end: `0x180024050`
- name: `?StartIISAdminMonitor@@YAJP6AXW4INETINFO_CRASH_ACTION@@@Z@Z`
- size: `480`
- prototype: `__int64 __fastcall(void (__high *)(enum INETINFO_CRASH_ACTION))`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007300`
- `0x180023e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023fe6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023fd4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023fd4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002400b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002400b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023efd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023f6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023efd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023f6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024027`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024027`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024042`

## string_xrefs

- `0x180023ede`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180023f4e`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180023ec1`: `Start monitoring called when we were all ready monitoring, setting hr to equal %08x\n`
- `0x180023f2f`: `Can not create startup complete event for monitoring the inetinfo process, hr = %08x\n`
- `0x180023f9e`: `Can not create shutdown event for monitoring the inetinfo process, hr = %08x\n`

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
0x180023e70  push    rbx
0x180023e72  sub     rsp, 50h
0x180023e76  mov     [rsp+58h+var_18], 0
0x180023e7f  mov     [rsp+58h+hHandle], 0
0x180023e88  mov     [rsp+58h+Parameter], rcx
0x180023e8d  test    rcx, rcx
0x180023e90  jnz     short loc_180023E9C
0x180023e92  mov     eax, 80070057h
0x180023e97  jmp     loc_18002404A
0x180023e9c  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; void * g_IISAdminMonitorShutdownEvent
0x180023ea3  test    rcx, rcx
0x180023ea6  jz      short loc_180023EEF
0x180023ea8  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023eaf  mov     ebx, 8000FFFFh
0x180023eb4  jz      loc_180024022
0x180023eba  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180023ec1  lea     rax, aStartMonitorin; "Start monitoring called when we were al"...
0x180023ec8  mov     dword ptr [rsp+58h+lpThreadId], ebx; char
0x180023ecc  lea     r9, aStartiisadminm_0; "StartIISAdminMonitor"
0x180023ed3  mov     r8d, 87h; unsigned int
0x180023ed9  mov     qword ptr [rsp+58h+dwCreationFlags], rax; char *
0x180023ede  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180023ee5  call    PuDbgPrint
0x180023eea  jmp     loc_18002401B
0x180023eef  xor     r9d, r9d; lpName
0x180023ef2  xor     r8d, r8d; bInitialState
0x180023ef5  xor     ecx, ecx; lpEventAttributes
0x180023ef7  lea     ebx, [r9+1]
0x180023efb  mov     edx, ebx; bManualReset
0x180023efd  call    cs:__imp_CreateEventW
0x180023f03  mov     [rsp+58h+hHandle], rax
0x180023f08  test    rax, rax
0x180023f0b  jnz     short loc_180023F64
0x180023f0d  call    cs:__imp_GetLastError
0x180023f13  mov     ebx, eax
0x180023f15  test    eax, eax
0x180023f17  jle     short loc_180023F22
0x180023f19  movzx   ebx, ax
0x180023f1c  or      ebx, 80070000h
0x180023f22  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023f29  jz      loc_180023FFB
0x180023f2f  lea     rax, aCanNotCreateSt; "Can not create startup complete event f"...
0x180023f36  mov     r8d, 99h; unsigned int
0x180023f3c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180023f43  lea     r9, aStartiisadminm_0; "StartIISAdminMonitor"
0x180023f4a  mov     dword ptr [rsp+58h+lpThreadId], ebx; char
0x180023f4e  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180023f55  mov     qword ptr [rsp+58h+dwCreationFlags], rax; char *
0x180023f5a  call    PuDbgPrint
0x180023f5f  jmp     loc_180023FFB
0x180023f64  xor     r9d, r9d; lpName
0x180023f67  xor     r8d, r8d; bInitialState
0x180023f6a  mov     edx, ebx; bManualReset
0x180023f6c  xor     ecx, ecx; lpEventAttributes
0x180023f6e  call    cs:__imp_CreateEventW
0x180023f74  mov     cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA, rax; void * g_IISAdminMonitorShutdownEvent
0x180023f7b  test    rax, rax
0x180023f7e  jnz     short loc_180023FAD
0x180023f80  call    cs:__imp_GetLastError
0x180023f86  mov     ebx, eax
0x180023f88  test    eax, eax
0x180023f8a  jle     short loc_180023F95
0x180023f8c  movzx   ebx, ax
0x180023f8f  or      ebx, 80070000h
0x180023f95  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023f9c  jz      short loc_180023FFB
0x180023f9e  lea     rax, aCanNotCreateSh; "Can not create shutdown event for monit"...
0x180023fa5  mov     r8d, 0B6h
0x180023fab  jmp     short loc_180023F3C
0x180023fad  lea     rax, ?g_dwIISAdminThreadId@@3KA; ulong g_dwIISAdminThreadId
0x180023fb4  mov     edx, 8000h; dwStackSize
0x180023fb9  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180023fbe  lea     r9, [rsp+58h+Parameter]; lpParameter
0x180023fc3  lea     r8, ?StartMonitoring@@YAKPEAX@Z; lpStartAddress
0x180023fca  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180023fd2  xor     ecx, ecx; lpThreadAttributes
0x180023fd4  call    cs:__imp_CreateThread
0x180023fda  mov     cs:?g_hIISAdminMonitorThread@@3PEAXEA, rax; void * g_hIISAdminMonitorThread
0x180023fe1  test    rax, rax
0x180023fe4  jnz     short loc_180024001
0x180023fe6  call    cs:__imp_GetLastError
0x180023fec  mov     ebx, eax
0x180023fee  test    eax, eax
0x180023ff0  jle     short loc_180023FFB
0x180023ff2  movzx   ebx, ax
0x180023ff5  or      ebx, 80070000h
0x180023ffb  test    ebx, ebx
0x180023ffd  js      short loc_18002401B
0x180023fff  jmp     short loc_180024011
0x180024001  mov     rcx, [rsp+58h+hHandle]; hHandle
0x180024006  xor     ebx, ebx
0x180024008  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002400b  call    cs:__imp_WaitForSingleObject
0x180024011  mov     eax, dword ptr [rsp+58h+var_18]
0x180024015  test    eax, eax
0x180024017  jns     short loc_180024038
0x180024019  mov     ebx, eax
0x18002401b  mov     rcx, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; hObject
0x180024022  test    rcx, rcx
0x180024025  jz      short loc_180024038
0x180024027  call    cs:__imp_CloseHandle
0x18002402d  mov     cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA, 0; void * g_IISAdminMonitorShutdownEvent
0x180024038  mov     rcx, [rsp+58h+hHandle]; hObject
0x18002403d  test    rcx, rcx
0x180024040  jz      short loc_180024048
0x180024042  call    cs:__imp_CloseHandle
0x180024048  mov     eax, ebx
0x18002404a  add     rsp, 50h
0x18002404e  pop     rbx
0x18002404f  retn
```
