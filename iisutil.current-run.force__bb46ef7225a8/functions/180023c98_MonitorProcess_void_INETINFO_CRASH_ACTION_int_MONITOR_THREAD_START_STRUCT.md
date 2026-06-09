# MonitorProcess(void (*)(INETINFO_CRASH_ACTION),int *,MONITOR_THREAD_START_STRUCT *)

- ea: `0x180023c98`
- end: `0x180023e68`
- name: `?MonitorProcess@@YAXP6AXW4INETINFO_CRASH_ACTION@@@ZPEAHPEAUMONITOR_THREAD_START_STRUCT@@@Z`
- size: `464`
- prototype: `void __fastcall(void (__high *)(enum INETINFO_CRASH_ACTION), int *, struct MONITOR_THREAD_START_STRUCT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180024060`

## callees

- `0x180007300`
- `0x180023308`
- `0x180023760`
- `0x180023c98`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023db8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023db8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180023d64`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180023d64`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023d44`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023e55`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023d44`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e2c`

## string_xrefs

- `0x180023d03`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180023d95`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`

## pseudocode

```c
void __fastcall MonitorProcess(void (__fastcall *a1)(__int64), int *a2, HANDLE *a3)
{
  int v3; // ebp
  int ProcessHandleForInetinfo; // eax
  HANDLE v8; // r15
  signed int v9; // ebx
  DWORD v10; // eax
  DWORD v11; // ebp
  signed int LastError; // eax
  int v13; // eax
  HANDLE v14; // rcx
  HANDLE Handles[9]; // [rsp+30h] [rbp-48h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+10h] BYREF

  v3 = *a2;
  hObject = 0;
  *a2 = 0;
  ProcessHandleForInetinfo = GetProcessHandleForInetinfo(&hObject);
  v8 = hObject;
  v9 = ProcessHandleForInetinfo;
  if ( ProcessHandleForInetinfo < 0 )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
        0x459u,
        "MonitorProcess",
        "Failed to get inetinfo process handle hr = %08x\n",
        ProcessHandleForInetinfo);
    goto LABEL_23;
  }
  if ( v3 )
    a1(2);
  Handles[0] = g_IISAdminMonitorShutdownEvent;
  Handles[1] = v8;
  if ( a3 )
  {
    SetEvent(a3[1]);
    a3 = 0;
  }
  v10 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
  v11 = v10;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x8000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
      0x494u,
      "MonitorProcess",
      "WaitResult = %d \n",
      v10);
  if ( v11 == -1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
        0x49Cu,
        "MonitorProcess",
        "WaitForMultipleObjectsEx failed, hr = %08x\n",
        v9);
    goto LABEL_23;
  }
  if ( !v11 )
    goto LABEL_23;
  a1(0);
  v13 = AdminMonitorRequiresShutdown();
  switch ( v13 )
  {
    case 2:
      a1(1);
LABEL_22:
      *a2 = 0;
      break;
    case 1:
      *a2 = 1;
      break;
    case 0:
      goto LABEL_22;
  }
LABEL_23:
  if ( v8 )
    CloseHandle(v8);
  if ( v9 < 0 )
  {
    a1(3);
    *a2 = 0;
  }
  if ( a3 )
  {
    v14 = a3[1];
    *((_DWORD *)a3 + 4) = v9;
    SetEvent(v14);
  }
}

```

## disassembly

```asm
0x180023c98  mov     rax, rsp
0x180023c9b  push    rbx
0x180023c9c  push    rbp
0x180023c9d  push    rsi
0x180023c9e  push    rdi
0x180023c9f  push    r14
0x180023ca1  push    r15
0x180023ca3  sub     rsp, 48h
0x180023ca7  mov     ebp, [rdx]
0x180023ca9  mov     r14, rcx
0x180023cac  lea     rcx, [rax+10h]; void **
0x180023cb0  mov     qword ptr [rax+10h], 0
0x180023cb8  mov     rdi, r8
0x180023cbb  mov     dword ptr [rdx], 0
0x180023cc1  mov     rsi, rdx
0x180023cc4  call    ?GetProcessHandleForInetinfo@@YAJPEAPEAX@Z; GetProcessHandleForInetinfo(void * *)
0x180023cc9  mov     r15, [rsp+78h+hObject]
0x180023cd1  mov     ebx, eax
0x180023cd3  test    eax, eax
0x180023cd5  jns     short loc_180023D19
0x180023cd7  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023cde  jz      loc_180023E24
0x180023ce4  mov     dword ptr [rsp+78h+var_50], eax; char
0x180023ce8  mov     r8d, 459h; unsigned int
0x180023cee  lea     rax, aFailedToGetIne; "Failed to get inetinfo process handle h"...
0x180023cf5  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180023cfc  lea     r9, aMonitorprocess; "MonitorProcess"
0x180023d03  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180023d0a  mov     qword ptr [rsp+78h+bAlertable], rax; char *
0x180023d0f  call    PuDbgPrint
0x180023d14  jmp     loc_180023E24
0x180023d19  test    ebp, ebp
0x180023d1b  jz      short loc_180023D2A
0x180023d1d  mov     ecx, 2
0x180023d22  mov     rax, r14
0x180023d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d2a  mov     rax, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; void * g_IISAdminMonitorShutdownEvent
0x180023d31  mov     [rsp+78h+Handles], rax
0x180023d36  mov     [rsp+78h+var_40], r15
0x180023d3b  test    rdi, rdi
0x180023d3e  jz      short loc_180023D4C
0x180023d40  mov     rcx, [rdi+8]; hEvent
0x180023d44  call    cs:__imp_SetEvent
0x180023d4a  xor     edi, edi
0x180023d4c  xor     r8d, r8d; bWaitAll
0x180023d4f  mov     [rsp+78h+bAlertable], 0; bAlertable
0x180023d57  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180023d5b  lea     rdx, [rsp+78h+Handles]; lpHandles
0x180023d60  lea     ecx, [r8+2]; nCount
0x180023d64  call    cs:__imp_WaitForMultipleObjectsEx
0x180023d6a  mov     ecx, cs:g_dwDebugFlagsIISUtil
0x180023d70  test    cl, 3
0x180023d73  mov     ebp, eax
0x180023d75  setnz   dl
0x180023d78  bt      ecx, 1Bh
0x180023d7c  setb    cl
0x180023d7f  test    cl, dl
0x180023d81  jz      short loc_180023DB3
0x180023d83  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180023d8a  lea     r9, aMonitorprocess; "MonitorProcess"
0x180023d91  mov     dword ptr [rsp+78h+var_50], eax; char
0x180023d95  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180023d9c  lea     rax, aWaitresultD; "WaitResult = %d \n"
0x180023da3  mov     r8d, 494h; unsigned int
0x180023da9  mov     qword ptr [rsp+78h+bAlertable], rax; char *
0x180023dae  call    PuDbgPrint
0x180023db3  cmp     ebp, 0FFFFFFFFh
0x180023db6  jnz     short loc_180023DEC
0x180023db8  call    cs:__imp_GetLastError
0x180023dbe  mov     ebx, eax
0x180023dc0  test    eax, eax
0x180023dc2  jle     short loc_180023DCD
0x180023dc4  movzx   ebx, ax
0x180023dc7  or      ebx, 80070000h
0x180023dcd  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023dd4  jz      short loc_180023E24
0x180023dd6  mov     dword ptr [rsp+78h+var_50], ebx
0x180023dda  lea     rax, aWaitformultipl; "WaitForMultipleObjectsEx failed, hr = %"...
0x180023de1  mov     r8d, 49Ch
0x180023de7  jmp     loc_180023CF5
0x180023dec  test    ebp, ebp
0x180023dee  jz      short loc_180023E24
0x180023df0  xor     ecx, ecx
0x180023df2  mov     rax, r14
0x180023df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dfa  call    ?AdminMonitorRequiresShutdown@@YA?AW4MONITOR_ACTION_TO_TAKE@@XZ; AdminMonitorRequiresShutdown(void)
0x180023dff  cmp     eax, 2
0x180023e02  jnz     short loc_180023E11
0x180023e04  lea     ecx, [rax-1]
0x180023e07  mov     rax, r14
0x180023e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e0f  jmp     short loc_180023E1E
0x180023e11  cmp     eax, 1
0x180023e14  jnz     short loc_180023E1A
0x180023e16  mov     [rsi], eax
0x180023e18  jmp     short loc_180023E24
0x180023e1a  test    eax, eax
0x180023e1c  jnz     short loc_180023E24
0x180023e1e  mov     dword ptr [rsi], 0
0x180023e24  test    r15, r15
0x180023e27  jz      short loc_180023E32
0x180023e29  mov     rcx, r15; hObject
0x180023e2c  call    cs:__imp_CloseHandle
0x180023e32  test    ebx, ebx
0x180023e34  jns     short loc_180023E49
0x180023e36  mov     ecx, 3
0x180023e3b  mov     rax, r14
0x180023e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e43  mov     dword ptr [rsi], 0
0x180023e49  test    rdi, rdi
0x180023e4c  jz      short loc_180023E5B
0x180023e4e  mov     rcx, [rdi+8]; hEvent
0x180023e52  mov     [rdi+10h], ebx
0x180023e55  call    cs:__imp_SetEvent
0x180023e5b  add     rsp, 48h
0x180023e5f  pop     r15
0x180023e61  pop     r14
0x180023e63  pop     rdi
0x180023e64  pop     rsi
0x180023e65  pop     rbp
0x180023e66  pop     rbx
0x180023e67  retn
```
