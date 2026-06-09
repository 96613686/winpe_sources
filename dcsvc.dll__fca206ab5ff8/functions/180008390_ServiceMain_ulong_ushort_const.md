# ServiceMain(ulong,ushort * * const)

- ea: `0x180008390`
- end: `0x1800085c9`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `569`
- prototype: `void __fastcall(int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001cf0`
- `0x1800060b0`
- `0x180008390`
- `0x18000947c`
- `0x18000a7e8`
- `0x18000a850`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800083ef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800083ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000847c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000847c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008577`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008577`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000844e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000844e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008556`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008556`

## pseudocode

```c
void __fastcall ServiceMain(int a1, LPCWSTR *a2)
{
  signed int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned __int16 **v7; // rdx
  unsigned int v8; // ecx
  signed int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // edx
  unsigned int v13; // ecx
  signed int v14; // [rsp+40h] [rbp-9h] BYREF
  signed int v15; // [rsp+48h] [rbp-1h] BYREF
  char v16[16]; // [rsp+50h] [rbp+7h] BYREF
  signed int *v17; // [rsp+60h] [rbp+17h]
  __int64 v18; // [rsp+68h] [rbp+1Fh]
  signed int *v19; // [rsp+70h] [rbp+27h]
  __int64 v20; // [rsp+78h] [rbp+2Fh]
  char v21[16]; // [rsp+80h] [rbp+37h] BYREF

  TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18001B028);
  TraceLoggingRegister_EventRegister_EventSetInformation(&dword_18001B060);
  McGenEventRegister_EventRegister();
  if ( !a1 )
    goto LABEL_2;
  if ( !(unsigned int)_o__wcsicmp(L"TestCallInitOnly", *a2) )
    return;
  if ( (byte_18001B741 & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v5, EnterpriseDiagnosticsDcSvcInitialized, v6, 1, v21);
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
      goto LABEL_16;
    }
    v4 = InitializeService(v8, v7);
    if ( v4 < 0 )
    {
LABEL_16:
      if ( WaitHandle && UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
        WaitHandle = 0;
      if ( hEvent )
      {
        CloseHandle(hEvent);
        hEvent = 0;
      }
      v12 = v4;
      v13 = 1;
      goto LABEL_23;
    }
    v9 = (*(__int64 (__fastcall **)(HANDLE *, const wchar_t *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_18001B6F0 + 192))(
           &WaitHandle,
           L"dcsvc",
           hEvent,
           StopService,
           0,
           8);
    v4 = v9;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v15 = v9;
      v14 = v4;
      v17 = &v14;
      v18 = 4;
      v19 = &v15;
      v20 = 4;
      McGenEventWrite_EventWriteTransfer(v10, EnterpriseDiagnosticDcSvcStopServiceHandlerRegistered, v11, 3, v16);
    }
    if ( v4 )
    {
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_16;
    }
  }
  v12 = 0;
  ServiceStatus.dwControlsAccepted = 1;
  v13 = 4;
LABEL_23:
  SvcEngUpdateServiceStatus(v13, v12, 0);
}

```

## disassembly

```asm
0x180008390  mov     [rsp-8+arg_10], rbx
0x180008395  mov     [rsp-8+arg_18], rdi
0x18000839a  push    rbp
0x18000839b  lea     rbp, [rsp-57h]
0x1800083a0  sub     rsp, 0A0h
0x1800083a7  mov     rax, cs:__security_cookie
0x1800083ae  xor     rax, rsp
0x1800083b1  mov     [rbp+57h+var_10], rax
0x1800083b5  mov     ebx, ecx
0x1800083b7  mov     rdi, rdx
0x1800083ba  lea     rcx, dword_18001B028; CallbackContext
0x1800083c1  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x1800083c6  lea     rcx, dword_18001B060; CallbackContext
0x1800083cd  call    TraceLoggingRegister_EventRegister_EventSetInformation
0x1800083d2  call    McGenEventRegister_EventRegister
0x1800083d7  test    ebx, ebx
0x1800083d9  jnz     short loc_1800083E5
0x1800083db  mov     ebx, 8000FFFFh
0x1800083e0  jmp     loc_180008546
0x1800083e5  mov     rdx, [rdi]
0x1800083e8  lea     rcx, aTestcalliniton; "TestCallInitOnly"
0x1800083ef  call    cs:__imp__o__wcsicmp
0x1800083f5  test    eax, eax
0x1800083f7  jz      loc_1800085A8
0x1800083fd  test    cs:byte_18001B741, 4
0x180008404  jz      short loc_180008421
0x180008406  lea     rax, [rbp+57h+var_20]
0x18000840a  mov     r9d, 1
0x180008410  lea     rdx, EnterpriseDiagnosticsDcSvcInitialized
0x180008417  mov     [rsp+0A0h+var_80], rax
0x18000841c  call    McGenEventWrite_EventWriteTransfer
0x180008421  xorps   xmm0, xmm0
0x180008424  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x18000842f  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x180008437  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180008441  lea     rdx, ServiceHandler; lpHandlerProc
0x180008448  mov     rcx, [rdi]; lpServiceName
0x18000844b  xor     r8d, r8d; lpContext
0x18000844e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180008454  mov     cs:hServiceStatus, rax
0x18000845b  test    rax, rax
0x18000845e  jz      loc_180008591
0x180008464  xor     edx, edx; unsigned int
0x180008466  lea     ecx, [rdx+2]; unsigned int
0x180008469  lea     r8d, [rdx+64h]; unsigned int
0x18000846d  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x180008472  xor     r9d, r9d; lpName
0x180008475  xor     r8d, r8d; bInitialState
0x180008478  xor     edx, edx; bManualReset
0x18000847a  xor     ecx, ecx; lpEventAttributes
0x18000847c  call    cs:__imp_CreateEventW
0x180008482  mov     cs:hEvent, rax
0x180008489  test    rax, rax
0x18000848c  jz      loc_1800083DB
0x180008492  call    ?InitializeService@@YAJKQEAPEAG@Z; InitializeService(ulong,ushort * * const)
0x180008497  mov     ebx, eax
0x180008499  test    eax, eax
0x18000849b  js      loc_180008546
0x1800084a1  mov     rax, cs:qword_18001B6F0
0x1800084a8  lea     r9, StopService
0x1800084af  mov     r8, cs:hEvent
0x1800084b6  lea     rdx, aDcsvc; "dcsvc"
0x1800084bd  mov     [rsp+0A0h+var_78], 8
0x1800084c5  lea     rcx, WaitHandle
0x1800084cc  mov     [rsp+0A0h+var_80], 0
0x1800084d5  mov     rax, [rax+0C0h]
0x1800084dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084e1  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x1800084e8  mov     ebx, eax
0x1800084ea  mov     edi, 80070000h
0x1800084ef  jz      short loc_18000853B
0x1800084f1  test    eax, eax
0x1800084f3  jle     short loc_1800084FA
0x1800084f5  movzx   eax, bx
0x1800084f8  or      eax, edi
0x1800084fa  mov     [rbp+57h+var_58], eax
0x1800084fd  lea     rdx, EnterpriseDiagnosticDcSvcStopServiceHandlerRegistered
0x180008504  lea     rax, [rbp+57h+var_60]
0x180008508  mov     [rbp+57h+var_60], ebx
0x18000850b  mov     [rbp+57h+var_40], rax
0x18000850f  mov     r9d, 3
0x180008515  lea     rax, [rbp+57h+var_58]
0x180008519  mov     [rbp+57h+var_38], 4
0x180008521  mov     [rbp+57h+var_30], rax
0x180008525  lea     rax, [rbp+57h+var_50]
0x180008529  mov     [rsp+0A0h+var_80], rax
0x18000852e  mov     [rbp+57h+var_28], 4
0x180008536  call    McGenEventWrite_EventWriteTransfer
0x18000853b  test    ebx, ebx
0x18000853d  jz      short loc_180008591
0x18000853f  jle     short loc_180008546
0x180008541  movzx   ebx, bx
0x180008544  or      ebx, edi
0x180008546  mov     rcx, cs:WaitHandle; WaitHandle
0x18000854d  test    rcx, rcx
0x180008550  jz      short loc_18000856B
0x180008552  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180008556  call    cs:__imp_UnregisterWaitEx
0x18000855c  test    eax, eax
0x18000855e  jz      short loc_18000856B
0x180008560  mov     cs:WaitHandle, 0
0x18000856b  mov     rcx, cs:hEvent; hObject
0x180008572  test    rcx, rcx
0x180008575  jz      short loc_180008588
0x180008577  call    cs:__imp_CloseHandle
0x18000857d  mov     cs:hEvent, 0
0x180008588  mov     edx, ebx
0x18000858a  mov     ecx, 1
0x18000858f  jmp     short loc_1800085A0
0x180008591  xor     edx, edx; unsigned int
0x180008593  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x18000859d  lea     ecx, [rdx+4]; unsigned int
0x1800085a0  xor     r8d, r8d; unsigned int
0x1800085a3  call    ?SvcEngUpdateServiceStatus@@YAJKKK@Z; SvcEngUpdateServiceStatus(ulong,ulong,ulong)
0x1800085a8  mov     rcx, [rbp+57h+var_10]
0x1800085ac  xor     rcx, rsp; StackCookie
0x1800085af  call    __security_check_cookie
0x1800085b4  lea     r11, [rsp+0A0h+var_s0]
0x1800085bc  mov     rbx, [r11+20h]
0x1800085c0  mov     rdi, [r11+28h]
0x1800085c4  mov     rsp, r11
0x1800085c7  pop     rbp
0x1800085c8  retn
```
