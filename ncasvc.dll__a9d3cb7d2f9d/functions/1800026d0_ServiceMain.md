# ServiceMain

- ea: `0x1800026d0`
- end: `0x180002c05`
- name: `ServiceMain`
- size: `1333`
- prototype: `void()`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800024b0`
- `0x1800026d0`
- `0x180003240`
- `0x1800033bc`
- `0x1800042e8`
- `0x180004680`
- `0x180004984`
- `0x180004c8c`
- `0x180004cec`
- `0x180004f04`
- `0x180004f34`
- `0x180018ffc`
- `0x180019784`
- `0x1800199b4`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002b61`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002b61`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002960`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002960`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002bc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002bc1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002ae7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180002ae7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002862`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002862`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000277d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000277d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b11`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002aba`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180002aba`

## string_xrefs

- `0x180002881`: `SetServiceStatus`
- `0x180002888`: `NcaServiceSetStatus`
- `0x1800028ca`: `NcaServiceSetStatus`
- `0x180002795`: `RegisterServiceCtrlHandlerEx`
- `0x180002920`: `ServiceMain`
- `0x180002945`: `ServiceMain`
- `0x180002996`: `ServiceMain`
- `0x1800029e7`: `ServiceMain`
- `0x180002a38`: `ServiceMain`
- `0x180002b0a`: `ServiceMain`
- `0x180002978`: `CreateEventW`
- `0x180002ad2`: `CreateThread`
- `0x180002b03`: `CreateThreadpoolTimer`

## pseudocode

```c
void ServiceMain()
{
  int v0; // ebx
  PVOID *v1; // rcx
  const char *v2; // rdi
  __int64 v3; // rdx
  PVOID *v4; // rcx
  SERVICE_STATUS_HANDLE v5; // rax
  DWORD LastError; // eax
  signed int CancelableLock; // eax
  signed int v8; // ecx
  int v9; // eax
  int v10; // edi
  DWORD v11; // eax
  PVOID *v12; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  PVOID *v14; // rcx
  _FILETIME pftDueTime; // [rsp+60h] [rbp+18h] BYREF

  v0 = 0;
  pftDueTime = 0;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      v1 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 4) != 0 )
      WPP_SF_(v1[2], 48, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  }
  dword_180028B68 = 0;
  ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
  ServiceStatus.dwWaitHint = 30000;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWin32ExitCode = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"NcaSvc", NcaServiceHandlerEx, 0);
  if ( hServiceStatus )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
    if ( !(unsigned int)NcaRegIsKeyPresent() )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      ServiceStatus.dwWin32ExitCode = 0;
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      {
        WPP_SF_(v4[2], 36, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      v5 = hServiceStatus;
      if ( hServiceStatus )
      {
        if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
        {
          McTemplateU0q_EventWriteTransfer(v4, v3, ServiceStatus.dwCurrentState);
          v5 = hServiceStatus;
        }
        if ( !SetServiceStatus(v5, &ServiceStatus) )
        {
          LastError = GetLastError();
          v0 = NcaReportErrorAsWinError("NcaServiceSetStatus", "SetServiceStatus", LastError);
        }
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
        WPP_SF_d(v4[2], 37, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids, (unsigned int)v0);
      if ( v0 < 0 )
        NcaReportReturnError("NcaServiceSetStatus", (unsigned int)v0);
      return;
    }
    if ( qword_180028B48 )
    {
      CancelableLock = NcaCreateCancelableLock((struct _tag_NCA_CANCELABLE_LOCK *)&gNcaMain);
      if ( CancelableLock > 0 )
        v8 = (unsigned __int16)CancelableLock | 0x80070000;
      else
        v8 = CancelableLock;
      if ( v8 < 0 )
      {
        if ( CancelableLock > 0 )
          CancelableLock = (unsigned __int16)CancelableLock | 0x80070000;
        NcaReportReturnError("ServiceMain", (unsigned int)CancelableLock);
        goto LABEL_70;
      }
      v9 = NcaCriticalSectionCreate(&stru_180028AF0);
      v10 = v9;
      if ( v9 < 0 )
        goto LABEL_48;
      hEvent = CreateEventW(0, 0, 0, 0);
      if ( !hEvent )
      {
        v2 = "CreateEventW";
        goto LABEL_61;
      }
      v9 = NcaServiceChangeState(2u);
      v10 = v9;
      if ( v9 < 0 )
        goto LABEL_48;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      v9 = NcaComponentsInitialize(2, off_18001F1B0);
      v10 = v9;
      if ( v9 < 0 )
      {
LABEL_48:
        NcaReportReturnError("ServiceMain", (unsigned int)v9);
        goto LABEL_63;
      }
      byte_180028B6C = 1;
      v11 = ((__int64 (__fastcall *)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))qword_180028B48)(
              &WaitHandle,
              L"NcaSvc",
              hEvent,
              NcaServiceOnShutdownCallback,
              0,
              24);
      if ( v11 )
      {
        v2 = "SvchostRegisterStopCallback";
        goto LABEL_62;
      }
      dword_180028B68 = 1;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 )
          WPP_SF_(v12[2], 52, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
      }
      hObject = CreateThread(0, 0, NcaServiceAsyncStartupRoutine, 0, 0, 0);
      if ( hObject )
      {
        ThreadpoolTimer = CreateThreadpoolTimer(NcaSqmTimerCallback, 0, 0);
        pti = ThreadpoolTimer;
        if ( ThreadpoolTimer )
        {
          pftDueTime.dwHighDateTime = -202;
          pftDueTime.dwLowDateTime = -711573504;
          SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x5265C00u, 0x1B7740u);
          goto LABEL_70;
        }
        v2 = "CreateThreadpoolTimer";
      }
      else
      {
        v2 = "CreateThread";
      }
    }
    else
    {
      v2 = "RegisterStopCallback";
    }
  }
  else
  {
    v2 = "RegisterServiceCtrlHandlerEx";
  }
LABEL_61:
  v11 = GetLastError();
LABEL_62:
  v10 = NcaReportErrorAsWinError("ServiceMain", v2, v11);
  if ( v10 >= 0 )
    goto LABEL_70;
LABEL_63:
  ServiceStatus.dwWin32ExitCode = 1066;
  ServiceStatus.dwServiceSpecificExitCode = NcaHResultToWindowsError((unsigned int)v10);
  NcaServiceSetStatus();
  if ( dword_180028B68 )
    SetEvent(hEvent);
  else
    NcaServiceShutdown();
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_71;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
LABEL_70:
    v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_71:
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
      WPP_SF_(v14[2], 54, &WPP_c5093027d5633495648c95ae523c0e9d_Traceguids);
  }
}

```

## disassembly

```asm
0x1800026d0  mov     [rsp+arg_8], rbx
0x1800026d5  push    rsi
0x1800026d6  sub     rsp, 40h
0x1800026da  xor     ebx, ebx
0x1800026dc  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rbx
0x1800026e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026e8  lea     rsi, WPP_GLOBAL_Control
0x1800026ef  cmp     rcx, rsi
0x1800026f2  jz      short loc_180002736
0x1800026f4  test    byte ptr [rcx+1Ch], 8
0x1800026f8  jz      short loc_180002716
0x1800026fa  mov     rcx, [rcx+10h]
0x1800026fe  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180002705  mov     edx, 2Fh ; '/'
0x18000270a  call    WPP_SF_
0x18000270f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002716  cmp     rcx, rsi
0x180002719  jz      short loc_180002736
0x18000271b  test    byte ptr [rcx+1Ch], 4
0x18000271f  jz      short loc_180002736
0x180002721  mov     rcx, [rcx+10h]
0x180002725  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x18000272c  mov     edx, 30h ; '0'
0x180002731  call    WPP_SF_
0x180002736  xor     r8d, r8d; lpContext
0x180002739  mov     [rsp+48h+arg_0], rdi
0x18000273e  lea     rdx, ?NcaServiceHandlerEx@@YAKKKPEAX0@Z; lpHandlerProc
0x180002745  mov     cs:dword_180028B68, ebx
0x18000274b  lea     rcx, ServiceName; "NcaSvc"
0x180002752  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18000275c  mov     qword ptr cs:ServiceStatus.dwCurrentState, 1
0x180002767  mov     cs:ServiceStatus.dwWaitHint, 7530h
0x180002771  mov     cs:ServiceStatus.dwCheckPoint, ebx
0x180002777  mov     cs:ServiceStatus.dwWin32ExitCode, ebx
0x18000277d  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180002784  nop     dword ptr [rax+rax+00h]
0x180002789  mov     cs:hServiceStatus, rax
0x180002790  test    rax, rax
0x180002793  jnz     short loc_1800027A1
0x180002795  lea     rdi, aRegisterservic; "RegisterServiceCtrlHandlerEx"
0x18000279c  jmp     loc_180002B0A
0x1800027a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027a8  cmp     rcx, rsi
0x1800027ab  jz      short loc_1800027C8
0x1800027ad  test    byte ptr [rcx+1Ch], 4
0x1800027b1  jz      short loc_1800027C8
0x1800027b3  mov     rcx, [rcx+10h]
0x1800027b7  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x1800027be  mov     edx, 15h
0x1800027c3  call    WPP_SF_
0x1800027c8  call    NcaRegIsKeyPresent
0x1800027cd  test    eax, eax
0x1800027cf  jnz     loc_1800028DB
0x1800027d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027dc  cmp     rcx, rsi
0x1800027df  jz      short loc_180002803
0x1800027e1  test    byte ptr [rcx+1Ch], 4
0x1800027e5  jz      short loc_180002803
0x1800027e7  mov     rcx, [rcx+10h]
0x1800027eb  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x1800027f2  mov     edx, 31h ; '1'
0x1800027f7  call    WPP_SF_
0x1800027fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002803  mov     cs:ServiceStatus.dwWin32ExitCode, ebx
0x180002809  cmp     rcx, rsi
0x18000280c  jz      short loc_180002830
0x18000280e  test    byte ptr [rcx+1Ch], 8
0x180002812  jz      short loc_180002830
0x180002814  mov     rcx, [rcx+10h]
0x180002818  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x18000281f  mov     edx, 24h ; '$'
0x180002824  call    WPP_SF_
0x180002829  mov     rcx, cs:WPP_GLOBAL_Control
0x180002830  mov     rax, cs:hServiceStatus
0x180002837  test    rax, rax
0x18000283a  jz      short loc_18000289D
0x18000283c  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180002843  jz      short loc_180002858
0x180002845  mov     r8d, cs:ServiceStatus.dwCurrentState
0x18000284c  call    McTemplateU0q_EventWriteTransfer
0x180002851  mov     rax, cs:hServiceStatus
0x180002858  lea     rdx, ServiceStatus; lpServiceStatus
0x18000285f  mov     rcx, rax; hServiceStatus
0x180002862  call    cs:__imp_SetServiceStatus
0x180002869  nop     dword ptr [rax+rax+00h]
0x18000286e  test    eax, eax
0x180002870  jnz     short loc_180002896
0x180002872  call    cs:__imp_GetLastError
0x180002879  nop     dword ptr [rax+rax+00h]
0x18000287e  mov     r8d, eax
0x180002881  lea     rdx, aSetservicestat; "SetServiceStatus"
0x180002888  lea     rcx, aNcaservicesets; "NcaServiceSetStatus"
0x18000288f  call    NcaReportErrorAsWinError
0x180002894  mov     ebx, eax
0x180002896  mov     rcx, cs:WPP_GLOBAL_Control
0x18000289d  cmp     rcx, rsi
0x1800028a0  jz      short loc_1800028C0
0x1800028a2  test    byte ptr [rcx+1Ch], 8
0x1800028a6  jz      short loc_1800028C0
0x1800028a8  mov     rcx, [rcx+10h]
0x1800028ac  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x1800028b3  mov     edx, 25h ; '%'
0x1800028b8  mov     r9d, ebx
0x1800028bb  call    WPP_SF_d
0x1800028c0  test    ebx, ebx
0x1800028c2  jns     loc_180002BF4
0x1800028c8  mov     edx, ebx
0x1800028ca  lea     rcx, aNcaservicesets; "NcaServiceSetStatus"
0x1800028d1  call    NcaReportReturnError
0x1800028d6  jmp     loc_180002BF4
0x1800028db  cmp     cs:qword_180028B48, rbx
0x1800028e2  jnz     short loc_1800028F0
0x1800028e4  lea     rdi, aRegisterstopca; "RegisterStopCallback"
0x1800028eb  jmp     loc_180002B0A
0x1800028f0  lea     rcx, ?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; struct _tag_NCA_CANCELABLE_LOCK *
0x1800028f7  call    ?NcaCreateCancelableLock@@YAKPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaCreateCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x1800028fc  movzx   edx, ax
0x1800028ff  test    eax, eax
0x180002901  jg      short loc_180002907
0x180002903  mov     ecx, eax
0x180002905  jmp     short loc_18000290F
0x180002907  mov     ecx, edx
0x180002909  or      ecx, 80070000h
0x18000290f  test    ecx, ecx
0x180002911  jns     short loc_180002931
0x180002913  test    eax, eax
0x180002915  jle     short loc_18000291E
0x180002917  mov     eax, edx
0x180002919  or      eax, 80070000h
0x18000291e  mov     edx, eax
0x180002920  lea     rcx, aServicemain_0; "ServiceMain"
0x180002927  call    NcaReportReturnError
0x18000292c  jmp     loc_180002BCD
0x180002931  lea     rcx, stru_180028AF0; lpCriticalSection
0x180002938  call    NcaCriticalSectionCreate
0x18000293d  mov     edi, eax
0x18000293f  test    eax, eax
0x180002941  jns     short loc_180002956
0x180002943  mov     edx, eax
0x180002945  lea     rcx, aServicemain_0; "ServiceMain"
0x18000294c  call    NcaReportReturnError
0x180002951  jmp     loc_180002B35
0x180002956  xor     r9d, r9d; lpName
0x180002959  xor     r8d, r8d; bInitialState
0x18000295c  xor     edx, edx; bManualReset
0x18000295e  xor     ecx, ecx; lpEventAttributes
0x180002960  call    cs:__imp_CreateEventW
0x180002967  nop     dword ptr [rax+rax+00h]
0x18000296c  mov     cs:hEvent, rax
0x180002973  test    rax, rax
0x180002976  jnz     short loc_180002984
0x180002978  lea     rdi, aCreateeventw; "CreateEventW"
0x18000297f  jmp     loc_180002B0A
0x180002984  mov     ecx, 2; unsigned int
0x180002989  call    ?NcaServiceChangeState@@YAJK@Z; NcaServiceChangeState(ulong)
0x18000298e  mov     edi, eax
0x180002990  test    eax, eax
0x180002992  jns     short loc_1800029A7
0x180002994  mov     edx, eax
0x180002996  lea     rcx, aServicemain_0; "ServiceMain"
0x18000299d  call    NcaReportReturnError
0x1800029a2  jmp     loc_180002B35
0x1800029a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029ae  cmp     rcx, rsi
0x1800029b1  jz      short loc_1800029CE
0x1800029b3  test    byte ptr [rcx+1Ch], 4
0x1800029b7  jz      short loc_1800029CE
0x1800029b9  mov     rcx, [rcx+10h]
0x1800029bd  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x1800029c4  mov     edx, 32h ; '2'
0x1800029c9  call    WPP_SF_
0x1800029ce  lea     rdx, off_18001F1B0
0x1800029d5  mov     ecx, 2
0x1800029da  call    NcaComponentsInitialize
0x1800029df  mov     edi, eax
0x1800029e1  test    eax, eax
0x1800029e3  jns     short loc_1800029F8
0x1800029e5  mov     edx, eax
0x1800029e7  lea     rcx, aServicemain_0; "ServiceMain"
0x1800029ee  call    NcaReportReturnError
0x1800029f3  jmp     loc_180002B35
0x1800029f8  mov     r8, cs:hEvent
0x1800029ff  lea     r9, ?NcaServiceOnShutdownCallback@@YAXPEAXE@Z; NcaServiceOnShutdownCallback(void *,uchar)
0x180002a06  mov     rax, cs:qword_180028B48
0x180002a0d  lea     rdx, ServiceName; "NcaSvc"
0x180002a14  mov     dword ptr [rsp+48h+lpThreadId], 18h
0x180002a1c  lea     rcx, WaitHandle
0x180002a23  mov     qword ptr [rsp+48h+dwCreationFlags], rbx
0x180002a28  mov     cs:byte_180028B6C, 1
0x180002a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a34  test    eax, eax
0x180002a36  jz      short loc_180002A4B
0x180002a38  lea     rbx, aServicemain_0; "ServiceMain"
0x180002a3f  lea     rdi, aSvchostregiste; "SvchostRegisterStopCallback"
0x180002a46  jmp     loc_180002B1D
0x180002a4b  mov     cs:dword_180028B68, 1
0x180002a55  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a5c  cmp     rcx, rsi
0x180002a5f  jz      short loc_180002AA3
0x180002a61  test    byte ptr [rcx+1Ch], 4
0x180002a65  jz      short loc_180002A83
0x180002a67  mov     rcx, [rcx+10h]
0x180002a6b  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180002a72  mov     edx, 33h ; '3'
0x180002a77  call    WPP_SF_
0x180002a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a83  cmp     rcx, rsi
0x180002a86  jz      short loc_180002AA3
0x180002a88  test    byte ptr [rcx+1Ch], 4
0x180002a8c  jz      short loc_180002AA3
0x180002a8e  mov     rcx, [rcx+10h]
0x180002a92  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180002a99  mov     edx, 34h ; '4'
0x180002a9e  call    WPP_SF_
0x180002aa3  mov     [rsp+48h+lpThreadId], rbx; lpThreadId
0x180002aa8  lea     r8, ?NcaServiceAsyncStartupRoutine@@YAKPEAX@Z; lpStartAddress
0x180002aaf  xor     r9d, r9d; lpParameter
0x180002ab2  mov     [rsp+48h+dwCreationFlags], ebx; dwCreationFlags
0x180002ab6  xor     edx, edx; dwStackSize
0x180002ab8  xor     ecx, ecx; lpThreadAttributes
0x180002aba  call    cs:__imp_CreateThread
0x180002ac1  nop     dword ptr [rax+rax+00h]
0x180002ac6  mov     cs:hObject, rax
0x180002acd  test    rax, rax
0x180002ad0  jnz     short loc_180002ADB
0x180002ad2  lea     rdi, aCreatethread; "CreateThread"
0x180002ad9  jmp     short loc_180002B0A
0x180002adb  xor     r8d, r8d; pcbe
0x180002ade  lea     rcx, ?NcaSqmTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180002ae5  xor     edx, edx; pv
0x180002ae7  call    cs:__imp_CreateThreadpoolTimer
0x180002aee  nop     dword ptr [rax+rax+00h]
0x180002af3  mov     cs:pti, rax
0x180002afa  test    rax, rax
0x180002afd  jnz     loc_180002B9D
0x180002b03  lea     rdi, aCreatethreadpo; "CreateThreadpoolTimer"
0x180002b0a  lea     rbx, aServicemain_0; "ServiceMain"
0x180002b11  call    cs:__imp_GetLastError
0x180002b18  nop     dword ptr [rax+rax+00h]
0x180002b1d  mov     r8d, eax
0x180002b20  mov     rdx, rdi
0x180002b23  mov     rcx, rbx
0x180002b26  call    NcaReportErrorAsWinError
0x180002b2b  mov     edi, eax
0x180002b2d  test    eax, eax
0x180002b2f  jns     loc_180002BCD
0x180002b35  mov     ecx, edi
0x180002b37  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x180002b41  call    NcaHResultToWindowsError
0x180002b46  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x180002b4c  call    ?NcaServiceSetStatus@@YAJXZ; NcaServiceSetStatus(void)
0x180002b51  cmp     cs:dword_180028B68, 0
0x180002b58  jz      short loc_180002B6F
0x180002b5a  mov     rcx, cs:hEvent; hEvent
0x180002b61  call    cs:__imp_SetEvent
0x180002b68  nop     dword ptr [rax+rax+00h]
0x180002b6d  jmp     short loc_180002B74
0x180002b6f  call    ?NcaServiceShutdown@@YAXXZ; NcaServiceShutdown(void)
0x180002b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b7b  cmp     rcx, rsi
0x180002b7e  jz      short loc_180002BF4
0x180002b80  test    byte ptr [rcx+1Ch], 4
0x180002b84  jz      short loc_180002BD4
0x180002b86  mov     rcx, [rcx+10h]
0x180002b8a  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180002b91  mov     edx, 35h ; '5'
0x180002b96  call    WPP_SF_
0x180002b9b  jmp     short loc_180002BCD
0x180002b9d  mov     r9d, 1B7740h; msWindowLength
0x180002ba3  mov     [rsp+48h+pftDueTime.dwHighDateTime], 0FFFFFF36h
0x180002bab  mov     r8d, 5265C00h; msPeriod
0x180002bb1  mov     [rsp+48h+pftDueTime.dwLowDateTime], 0D5964000h
0x180002bb9  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180002bbe  mov     rcx, rax; pti
0x180002bc1  call    cs:__imp_SetThreadpoolTimer
0x180002bc8  nop     dword ptr [rax+rax+00h]
0x180002bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bd4  cmp     rcx, rsi
0x180002bd7  jz      short loc_180002BF4
0x180002bd9  test    byte ptr [rcx+1Ch], 8
0x180002bdd  jz      short loc_180002BF4
0x180002bdf  mov     rcx, [rcx+10h]
0x180002be3  lea     r8, WPP_c5093027d5633495648c95ae523c0e9d_Traceguids
0x180002bea  mov     edx, 36h ; '6'
0x180002bef  call    WPP_SF_
0x180002bf4  mov     rdi, [rsp+48h+arg_0]
0x180002bf9  mov     rbx, [rsp+48h+arg_8]
0x180002bfe  add     rsp, 40h
0x180002c02  pop     rsi
0x180002c03  retn
```
