# MonitorProcess(void (*)(INETINFO_CRASH_ACTION),int *,MONITOR_THREAD_START_STRUCT *)

- ea: `0x18002566c`
- end: `0x18002585b`
- name: `?MonitorProcess@@YAXP6AXW4INETINFO_CRASH_ACTION@@@ZPEAHPEAUMONITOR_THREAD_START_STRUCT@@@Z`
- size: `495`
- prototype: `void __fastcall(void (__fastcall *)(__int64), int *, HANDLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180025a90`

## callees

- `0x180008000`
- `0x180024bf8`
- `0x1800250ac`
- `0x18002566c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025798`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002573e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002573e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025718`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025841`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025718`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025841`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025812`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025812`

## string_xrefs

- `0x1800256d7`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180025775`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`

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
0x18002566c  mov     rax, rsp
0x18002566f  push    rbx
0x180025670  push    rbp
0x180025671  push    rsi
0x180025672  push    rdi
0x180025673  push    r14
0x180025675  push    r15
0x180025677  sub     rsp, 48h
0x18002567b  mov     ebp, [rdx]
0x18002567d  mov     r14, rcx
0x180025680  lea     rcx, [rax+10h]; void **
0x180025684  mov     qword ptr [rax+10h], 0
0x18002568c  mov     rdi, r8
0x18002568f  mov     dword ptr [rdx], 0
0x180025695  mov     rsi, rdx
0x180025698  call    ?GetProcessHandleForInetinfo@@YAJPEAPEAX@Z; GetProcessHandleForInetinfo(void * *)
0x18002569d  mov     r15, [rsp+78h+hObject]
0x1800256a5  mov     ebx, eax
0x1800256a7  test    eax, eax
0x1800256a9  jns     short loc_1800256ED
0x1800256ab  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800256b2  jz      loc_18002580A
0x1800256b8  mov     dword ptr [rsp+78h+var_50], eax; char
0x1800256bc  mov     r8d, 459h; unsigned int
0x1800256c2  lea     rax, aFailedToGetIne; "Failed to get inetinfo process handle h"...
0x1800256c9  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800256d0  lea     r9, aMonitorprocess; "MonitorProcess"
0x1800256d7  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800256de  mov     qword ptr [rsp+78h+bAlertable], rax; char *
0x1800256e3  call    PuDbgPrint
0x1800256e8  jmp     loc_18002580A
0x1800256ed  test    ebp, ebp
0x1800256ef  jz      short loc_1800256FE
0x1800256f1  mov     ecx, 2
0x1800256f6  mov     rax, r14
0x1800256f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256fe  mov     rax, cs:?g_IISAdminMonitorShutdownEvent@@3PEAXEA; void * g_IISAdminMonitorShutdownEvent
0x180025705  mov     [rsp+78h+Handles], rax
0x18002570a  mov     [rsp+78h+var_40], r15
0x18002570f  test    rdi, rdi
0x180025712  jz      short loc_180025726
0x180025714  mov     rcx, [rdi+8]; hEvent
0x180025718  call    cs:__imp_SetEvent
0x18002571f  nop     dword ptr [rax+rax+00h]
0x180025724  xor     edi, edi
0x180025726  xor     r8d, r8d; bWaitAll
0x180025729  mov     [rsp+78h+bAlertable], 0; bAlertable
0x180025731  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180025735  lea     rdx, [rsp+78h+Handles]; lpHandles
0x18002573a  lea     ecx, [r8+2]; nCount
0x18002573e  call    cs:__imp_WaitForMultipleObjectsEx
0x180025745  nop     dword ptr [rax+rax+00h]
0x18002574a  mov     ecx, cs:g_dwDebugFlagsIISUtil
0x180025750  test    cl, 3
0x180025753  mov     ebp, eax
0x180025755  setnz   dl
0x180025758  bt      ecx, 1Bh
0x18002575c  setb    cl
0x18002575f  test    cl, dl
0x180025761  jz      short loc_180025793
0x180025763  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002576a  lea     r9, aMonitorprocess; "MonitorProcess"
0x180025771  mov     dword ptr [rsp+78h+var_50], eax; char
0x180025775  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002577c  lea     rax, aWaitresultD; "WaitResult = %d \n"
0x180025783  mov     r8d, 494h; unsigned int
0x180025789  mov     qword ptr [rsp+78h+bAlertable], rax; char *
0x18002578e  call    PuDbgPrint
0x180025793  cmp     ebp, 0FFFFFFFFh
0x180025796  jnz     short loc_1800257D2
0x180025798  call    cs:__imp_GetLastError
0x18002579f  nop     dword ptr [rax+rax+00h]
0x1800257a4  mov     ebx, eax
0x1800257a6  test    eax, eax
0x1800257a8  jle     short loc_1800257B3
0x1800257aa  movzx   ebx, ax
0x1800257ad  or      ebx, 80070000h
0x1800257b3  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800257ba  jz      short loc_18002580A
0x1800257bc  mov     dword ptr [rsp+78h+var_50], ebx
0x1800257c0  lea     rax, aWaitformultipl; "WaitForMultipleObjectsEx failed, hr = %"...
0x1800257c7  mov     r8d, 49Ch
0x1800257cd  jmp     loc_1800256C9
0x1800257d2  test    ebp, ebp
0x1800257d4  jz      short loc_18002580A
0x1800257d6  xor     ecx, ecx
0x1800257d8  mov     rax, r14
0x1800257db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257e0  call    ?AdminMonitorRequiresShutdown@@YA?AW4MONITOR_ACTION_TO_TAKE@@XZ; AdminMonitorRequiresShutdown(void)
0x1800257e5  cmp     eax, 2
0x1800257e8  jnz     short loc_1800257F7
0x1800257ea  lea     ecx, [rax-1]
0x1800257ed  mov     rax, r14
0x1800257f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257f5  jmp     short loc_180025804
0x1800257f7  cmp     eax, 1
0x1800257fa  jnz     short loc_180025800
0x1800257fc  mov     [rsi], eax
0x1800257fe  jmp     short loc_18002580A
0x180025800  test    eax, eax
0x180025802  jnz     short loc_18002580A
0x180025804  mov     dword ptr [rsi], 0
0x18002580a  test    r15, r15
0x18002580d  jz      short loc_18002581E
0x18002580f  mov     rcx, r15; hObject
0x180025812  call    cs:__imp_CloseHandle
0x180025819  nop     dword ptr [rax+rax+00h]
0x18002581e  test    ebx, ebx
0x180025820  jns     short loc_180025835
0x180025822  mov     ecx, 3
0x180025827  mov     rax, r14
0x18002582a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002582f  mov     dword ptr [rsi], 0
0x180025835  test    rdi, rdi
0x180025838  jz      short loc_18002584D
0x18002583a  mov     rcx, [rdi+8]; hEvent
0x18002583e  mov     [rdi+10h], ebx
0x180025841  call    cs:__imp_SetEvent
0x180025848  nop     dword ptr [rax+rax+00h]
0x18002584d  add     rsp, 48h
0x180025851  pop     r15
0x180025853  pop     r14
0x180025855  pop     rdi
0x180025856  pop     rsi
0x180025857  pop     rbp
0x180025858  pop     rbx
0x180025859  retn
```
