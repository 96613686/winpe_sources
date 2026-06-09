# ChangeNotificationLauncher(void *)

- ea: `0x18002d250`
- end: `0x18002d3d5`
- name: `?ChangeNotificationLauncher@@YAKPEAX@Z`
- size: `389`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076e0`
- `0x180007890`
- `0x18002d250`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d2d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d3c2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d2d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d3c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d2dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d2dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d2ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d2ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d30a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d30a`
- `iisutil!PuDbgPrint` at `0x18002d3a1`
- `iisutil!PuDbgPrint` at `0x18002d3a1`
- `iisutil!PuDbgPrintError` at `0x18002d2bc`
- `iisutil!PuDbgPrintError` at `0x18002d347`
- `iisutil!PuDbgPrintError` at `0x18002d2bc`
- `iisutil!PuDbgPrintError` at `0x18002d347`

## string_xrefs

- `0x18002d2b1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\changeprocessor.cxx`
- `0x18002d33c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\changeprocessor.cxx`
- `0x18002d39a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\changeprocessor.cxx`
- `0x18002d381`: `Config worker thread has exited it's work loop\n`
- `0x18002d291`: `Start listening for change notifications failed, service will not start\n`

## pseudocode

```c
__int64 __fastcall ChangeNotificationLauncher(char *Parameter)
{
  WEB_ADMIN_SERVICE *v1; // rbx
  int v3; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  void *v6; // rcx

  v1 = g_pWebAdminService;
  *((_DWORD *)Parameter + 4) = 3;
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 90) + 80LL))(*((_QWORD *)v1 + 90));
  *((_DWORD *)v1 + 248) = v3;
  if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\changeprocessor.cxx",
      577,
      "CHANGE_PROCESSOR::StartListeningForChangeNotifications",
      v3,
      "Start listening for change notifications failed, service will not start\n");
  SetEvent(*((HANDLE *)g_pWebAdminService + 123));
  WaitForSingleObject(*((HANDLE *)Parameter + 15), 0xFFFFFFFF);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)Parameter + 17) = EventW;
  if ( !EventW && (g_dwDebugFlags & 0xF) != 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\changeprocessor.cxx",
      481,
      "CHANGE_PROCESSOR::RunNotificationWorkQueue",
      LastError,
      "Failed to initialize work-queue-terminated event\n");
  }
  while ( !*((_DWORD *)Parameter + 5) )
    WORK_QUEUE::ProcessWorkItem((WORK_QUEUE *)(Parameter + 24));
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x30000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\changeprocessor.cxx",
      504,
      "CHANGE_PROCESSOR::RunNotificationWorkQueue",
      "Config worker thread has exited it's work loop\n");
  *((_DWORD *)Parameter + 4) = 4;
  WORK_QUEUE::Terminate((WORK_QUEUE *)(Parameter + 24));
  v6 = (void *)*((_QWORD *)Parameter + 17);
  if ( v6 )
    SetEvent(v6);
  return 0;
}

```

## disassembly

```asm
0x18002d250  mov     [rsp+arg_0], rbx
0x18002d255  push    rdi
0x18002d256  sub     rsp, 30h
0x18002d25a  mov     rbx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002d261  mov     rdi, rcx
0x18002d264  mov     dword ptr [rcx+10h], 3
0x18002d26b  mov     rcx, [rbx+2D0h]
0x18002d272  mov     rax, [rcx]
0x18002d275  mov     rax, [rax+50h]
0x18002d279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d27e  mov     [rbx+3E0h], eax
0x18002d284  test    eax, eax
0x18002d286  jns     short loc_18002D2C2
0x18002d288  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002d28f  jz      short loc_18002D2C2
0x18002d291  lea     rcx, aStartListening; "Start listening for change notification"...
0x18002d298  mov     r8d, 241h
0x18002d29e  mov     [rsp+38h+var_10], rcx
0x18002d2a3  lea     r9, aChangeProcesso_5; "CHANGE_PROCESSOR::StartListeningForChan"...
0x18002d2aa  mov     rcx, cs:g_pDebug
0x18002d2b1  lea     rdx, aServercommonIn_64; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002d2b8  mov     dword ptr [rsp+38h+var_18], eax
0x18002d2bc  call    cs:__imp_PuDbgPrintError
0x18002d2c2  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18002d2c9  mov     rcx, [rcx+3D8h]; hEvent
0x18002d2d0  call    cs:__imp_SetEvent
0x18002d2d6  mov     rcx, [rdi+78h]; hHandle
0x18002d2da  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002d2dd  call    cs:__imp_WaitForSingleObject
0x18002d2e3  xor     r9d, r9d; lpName
0x18002d2e6  xor     r8d, r8d; bInitialState
0x18002d2e9  xor     ecx, ecx; lpEventAttributes
0x18002d2eb  lea     edx, [r9+1]; bManualReset
0x18002d2ef  call    cs:__imp_CreateEventW
0x18002d2f5  mov     [rdi+88h], rax
0x18002d2fc  test    rax, rax
0x18002d2ff  jnz     short loc_18002D34D
0x18002d301  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002d308  jz      short loc_18002D34D
0x18002d30a  call    cs:__imp_GetLastError
0x18002d310  test    eax, eax
0x18002d312  jle     short loc_18002D31C
0x18002d314  movzx   eax, ax
0x18002d317  or      eax, 80070000h
0x18002d31c  lea     rcx, aFailedToInitia_3; "Failed to initialize work-queue-termina"...
0x18002d323  mov     r8d, 1E1h
0x18002d329  mov     [rsp+38h+var_10], rcx
0x18002d32e  lea     r9, aChangeProcesso_4; "CHANGE_PROCESSOR::RunNotificationWorkQu"...
0x18002d335  mov     rcx, cs:g_pDebug
0x18002d33c  lea     rdx, aServercommonIn_64; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002d343  mov     dword ptr [rsp+38h+var_18], eax
0x18002d347  call    cs:__imp_PuDbgPrintError
0x18002d34d  lea     rbx, [rdi+18h]
0x18002d351  cmp     dword ptr [rdi+14h], 0
0x18002d355  jnz     short loc_18002D361
0x18002d357  mov     rcx, rbx; this
0x18002d35a  call    ?ProcessWorkItem@WORK_QUEUE@@QEAAJXZ; WORK_QUEUE::ProcessWorkItem(void)
0x18002d35f  jmp     short loc_18002D351
0x18002d361  mov     eax, cs:g_dwDebugFlags
0x18002d367  test    al, 3
0x18002d369  setnz   r8b
0x18002d36d  test    eax, 30000h
0x18002d372  setnz   al
0x18002d375  test    al, r8b
0x18002d378  jz      short loc_18002D3A7
0x18002d37a  mov     rcx, cs:g_pDebug
0x18002d381  lea     rax, aConfigWorkerTh; "Config worker thread has exited it's wo"...
0x18002d388  lea     r9, aChangeProcesso_4; "CHANGE_PROCESSOR::RunNotificationWorkQu"...
0x18002d38f  mov     [rsp+38h+var_18], rax
0x18002d394  mov     r8d, 1F8h
0x18002d39a  lea     rdx, aServercommonIn_64; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002d3a1  call    cs:__imp_PuDbgPrint
0x18002d3a7  mov     rcx, rbx; this
0x18002d3aa  mov     dword ptr [rdi+10h], 4
0x18002d3b1  call    ?Terminate@WORK_QUEUE@@QEAAXXZ; WORK_QUEUE::Terminate(void)
0x18002d3b6  mov     rcx, [rdi+88h]; hEvent
0x18002d3bd  test    rcx, rcx
0x18002d3c0  jz      short loc_18002D3C8
0x18002d3c2  call    cs:__imp_SetEvent
0x18002d3c8  mov     rbx, [rsp+38h+arg_0]
0x18002d3cd  xor     eax, eax
0x18002d3cf  add     rsp, 30h
0x18002d3d3  pop     rdi
0x18002d3d4  retn
```
