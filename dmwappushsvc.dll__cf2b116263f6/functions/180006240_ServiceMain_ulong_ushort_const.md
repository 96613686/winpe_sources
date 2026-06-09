# ServiceMain(ulong,ushort * * const)

- ea: `0x180006240`
- end: `0x180006426`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `486`
- prototype: `void __fastcall(int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800011f8`
- `0x180001a70`
- `0x180004968`
- `0x180006124`
- `0x180006240`
- `0x18000650c`
- `0x180006738`
- `0x1800067a0`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006280`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006280`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000630e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000630e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800062e0`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800062e0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800063b9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800063b9`

## string_xrefs

- `0x180006344`: `dmwappushservice`

## pseudocode

```c
void __fastcall ServiceMain(int a1, LPCWSTR *a2)
{
  signed int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned __int16 **v7; // rdx
  unsigned int v8; // ecx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r9
  unsigned int v12; // edx
  unsigned int v13; // ecx
  _BYTE v14[16]; // [rsp+40h] [rbp-28h] BYREF

  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  McGenEventRegister_EventRegister();
  if ( !a1 )
    goto LABEL_2;
  if ( !(unsigned int)_o__wcsicmp(L"TestCallInitOnly", *a2) )
    return;
  if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v5, PushRouterDmWapPushSvcInitialized, v6, 1, v14);
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  *(_OWORD *)&ServiceStatus.dwCurrentState = 0;
  ServiceStatus.dwServiceType = 32;
  hServiceStatus = RegisterServiceCtrlHandlerExW(*a2, ServiceHandler, 0);
  if ( hServiceStatus )
  {
    SvcEngUpdateServiceStatus(2u, 0, 0x64u);
    hEvent = CreateEventW(0, 0, 0, 0);
    if ( !hEvent )
    {
LABEL_2:
      v4 = -2147418113;
      goto LABEL_17;
    }
    v4 = InitializeService(v8, v7);
    if ( v4 < 0 )
    {
LABEL_17:
      if ( WaitHandle && UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
        WaitHandle = 0;
      if ( hEvent )
      {
        CloseHandle(hEvent);
        hEvent = 0;
      }
      v12 = v4;
      v13 = 1;
      goto LABEL_24;
    }
    v9 = (*(__int64 (__fastcall **)(HANDLE *, const wchar_t *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_18001C8A0 + 192))(
           &WaitHandle,
           L"dmwappushservice",
           hEvent,
           StopService,
           0,
           8);
    v4 = v9;
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
    {
      if ( v9 > 0 )
        v11 = (unsigned __int16)v9 | 0x80070000;
      else
        v11 = (unsigned int)v9;
      McTemplateU0dd_EventWriteTransfer(
        v10,
        EnterpriseDiagnosticDmWapPushSvcStopServiceHandlerRegistered,
        (unsigned int)v9,
        v11);
    }
    if ( v4 )
    {
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_17;
    }
  }
  v12 = 0;
  ServiceStatus.dwControlsAccepted = 1;
  v13 = 4;
LABEL_24:
  SvcEngUpdateServiceStatus(v13, v12, 0);
}

```

## disassembly

```asm
0x180006240  mov     [rsp+arg_10], rbx
0x180006245  push    rdi
0x180006246  sub     rsp, 60h
0x18000624a  mov     rax, cs:__security_cookie
0x180006251  xor     rax, rsp
0x180006254  mov     [rsp+68h+var_18], rax
0x180006259  mov     rdi, rdx
0x18000625c  mov     ebx, ecx
0x18000625e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180006263  call    McGenEventRegister_EventRegister
0x180006268  test    ebx, ebx
0x18000626a  jnz     short loc_180006276
0x18000626c  mov     ebx, 8000FFFFh
0x180006271  jmp     loc_1800063A9
0x180006276  mov     rdx, [rdi]
0x180006279  lea     rcx, aTestcalliniton; "TestCallInitOnly"
0x180006280  call    cs:__imp__o__wcsicmp
0x180006286  test    eax, eax
0x180006288  jz      loc_18000640B
0x18000628e  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180006295  jz      short loc_1800062B3
0x180006297  lea     rax, [rsp+68h+var_28]
0x18000629c  mov     r9d, 1
0x1800062a2  lea     rdx, PushRouterDmWapPushSvcInitialized
0x1800062a9  mov     [rsp+68h+var_48], rax
0x1800062ae  call    McGenEventWrite_EventWriteTransfer
0x1800062b3  xorps   xmm0, xmm0
0x1800062b6  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x1800062c1  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x1800062c9  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x1800062d3  lea     rdx, ServiceHandler; lpHandlerProc
0x1800062da  mov     rcx, [rdi]; lpServiceName
0x1800062dd  xor     r8d, r8d; lpContext
0x1800062e0  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800062e6  mov     cs:hServiceStatus, rax
0x1800062ed  test    rax, rax
0x1800062f0  jz      loc_1800063F4
0x1800062f6  xor     edx, edx; unsigned int
0x1800062f8  lea     ecx, [rdx+2]; unsigned int
0x1800062fb  lea     r8d, [rdx+64h]; unsigned int
0x1800062ff  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x180006304  xor     r9d, r9d; lpName
0x180006307  xor     r8d, r8d; bInitialState
0x18000630a  xor     edx, edx; bManualReset
0x18000630c  xor     ecx, ecx; lpEventAttributes
0x18000630e  call    cs:__imp_CreateEventW
0x180006314  mov     cs:hEvent, rax
0x18000631b  test    rax, rax
0x18000631e  jz      loc_18000626C
0x180006324  call    ?InitializeService@@YAJKQEAPEAG@Z; InitializeService(ulong,ushort * * const)
0x180006329  mov     ebx, eax
0x18000632b  test    eax, eax
0x18000632d  js      short loc_1800063A9
0x18000632f  mov     rax, cs:qword_18001C8A0
0x180006336  lea     r9, StopService
0x18000633d  mov     r8, cs:hEvent
0x180006344  lea     rdx, aDmwappushservi_0; "dmwappushservice"
0x18000634b  mov     [rsp+68h+var_40], 8
0x180006353  lea     rcx, WaitHandle
0x18000635a  mov     [rsp+68h+var_48], 0
0x180006363  mov     rax, [rax+0C0h]
0x18000636a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636f  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x180006376  mov     ebx, eax
0x180006378  mov     edi, 80070000h
0x18000637d  jz      short loc_18000639E
0x18000637f  test    eax, eax
0x180006381  jg      short loc_180006388
0x180006383  mov     r9d, eax
0x180006386  jmp     short loc_18000638F
0x180006388  movzx   r9d, bx
0x18000638c  or      r9d, edi
0x18000638f  mov     r8d, ebx
0x180006392  lea     rdx, EnterpriseDiagnosticDmWapPushSvcStopServiceHandlerRegistered
0x180006399  call    McTemplateU0dd_EventWriteTransfer
0x18000639e  test    ebx, ebx
0x1800063a0  jz      short loc_1800063F4
0x1800063a2  jle     short loc_1800063A9
0x1800063a4  movzx   ebx, bx
0x1800063a7  or      ebx, edi
0x1800063a9  mov     rcx, cs:WaitHandle; WaitHandle
0x1800063b0  test    rcx, rcx
0x1800063b3  jz      short loc_1800063CE
0x1800063b5  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800063b9  call    cs:__imp_UnregisterWaitEx
0x1800063bf  test    eax, eax
0x1800063c1  jz      short loc_1800063CE
0x1800063c3  mov     cs:WaitHandle, 0
0x1800063ce  mov     rcx, cs:hEvent; hObject
0x1800063d5  test    rcx, rcx
0x1800063d8  jz      short loc_1800063EB
0x1800063da  call    cs:__imp_CloseHandle
0x1800063e0  mov     cs:hEvent, 0
0x1800063eb  mov     edx, ebx
0x1800063ed  mov     ecx, 1
0x1800063f2  jmp     short loc_180006403
0x1800063f4  xor     edx, edx; unsigned int
0x1800063f6  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x180006400  lea     ecx, [rdx+4]; unsigned int
0x180006403  xor     r8d, r8d; unsigned int
0x180006406  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x18000640b  mov     rcx, [rsp+68h+var_18]
0x180006410  xor     rcx, rsp; StackCookie
0x180006413  call    __security_check_cookie
0x180006418  mov     rbx, [rsp+68h+arg_10]
0x180006420  add     rsp, 60h
0x180006424  pop     rdi
0x180006425  retn
```
