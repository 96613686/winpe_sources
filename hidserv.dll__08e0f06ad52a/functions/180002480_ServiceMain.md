# ServiceMain

- ea: `0x180002480`
- end: `0x1800025b2`
- name: `ServiceMain`
- size: `306`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002480`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180002523`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180002523`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002545`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002545`
- `KERNEL32!WaitForSingleObject` at `0x18000257f`
- `KERNEL32!WaitForSingleObject` at `0x18000258a`
- `KERNEL32!WaitForSingleObject` at `0x18000257f`
- `KERNEL32!WaitForSingleObject` at `0x18000258a`
- `KERNEL32!CreateEventW` at `0x1800024de`
- `KERNEL32!CreateEventW` at `0x1800024de`
- `KERNEL32!CloseHandle` at `0x180002593`
- `KERNEL32!CloseHandle` at `0x18000259c`
- `KERNEL32!CloseHandle` at `0x180002593`
- `KERNEL32!CloseHandle` at `0x18000259c`
- `KERNEL32!CreateThread` at `0x180002569`
- `KERNEL32!CreateThread` at `0x180002569`

## pseudocode

```c
int ServiceMain()
{
  HANDLE EventW; // rax
  void *v1; // rbx
  SERVICE_STATUS_HANDLE v2; // rax
  HANDLE Thread; // rdi

  INITIAL_WAIT = 500;
  PnpEnabled = 0;
  hNotifyArrival = 0;
  hInstance = 0;
  hWndHidServ = 0;
  cThreadRef = 0;
  hMutexOOC = 0;
  hService = 0;
  REPEAT_INTERVAL = 150;
  EventW = CreateEventW(0, 0, 0, 0);
  v1 = EventW;
  if ( EventW )
  {
    ServiceStatus.dwServiceType = 32;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    v2 = RegisterServiceCtrlHandlerExW(HidservServiceName, (LPHANDLER_FUNCTION_EX)ServiceHandlerEx, 0);
    hService = v2;
    if ( v2 )
    {
      ServiceStatus.dwCurrentState = 2;
      SetServiceStatus(v2, &ServiceStatus);
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)HidServMain, v1, 0, &MessagePumpThreadId);
      if ( Thread )
      {
        WaitForSingleObject(v1, 0xFFFFFFFF);
        WaitForSingleObject(Thread, 0xFFFFFFFF);
        CloseHandle(Thread);
      }
    }
    LODWORD(EventW) = CloseHandle(v1);
  }
  return (int)EventW;
}

```

## disassembly

```asm
0x180002480  mov     [rsp+arg_0], rbx
0x180002485  mov     [rsp+arg_8], rsi
0x18000248a  push    rdi
0x18000248b  sub     rsp, 30h
0x18000248f  xor     esi, esi
0x180002491  mov     cs:INITIAL_WAIT, 1F4h
0x18000249b  xor     r9d, r9d; lpName
0x18000249e  mov     cs:PnpEnabled, esi
0x1800024a4  xor     r8d, r8d; bInitialState
0x1800024a7  mov     cs:hNotifyArrival, rsi
0x1800024ae  xor     edx, edx; bManualReset
0x1800024b0  mov     cs:hInstance, rsi
0x1800024b7  xor     ecx, ecx; lpEventAttributes
0x1800024b9  mov     cs:hWndHidServ, rsi
0x1800024c0  mov     cs:cThreadRef, esi
0x1800024c6  mov     cs:hMutexOOC, rsi
0x1800024cd  mov     cs:hService, rsi
0x1800024d4  mov     cs:REPEAT_INTERVAL, 96h
0x1800024de  call    cs:__imp_CreateEventW
0x1800024e4  mov     rbx, rax
0x1800024e7  test    rax, rax
0x1800024ea  jz      loc_1800025A2
0x1800024f0  lea     edi, [rsi+2]
0x1800024f3  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x1800024fd  xor     r8d, r8d; lpContext
0x180002500  mov     qword ptr cs:ServiceStatus.dwCurrentState, rdi
0x180002507  lea     rdx, ServiceHandlerEx; lpHandlerProc
0x18000250e  mov     qword ptr cs:ServiceStatus.dwWin32ExitCode, rsi
0x180002515  lea     rcx, HidservServiceName; "HidServ"
0x18000251c  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rsi
0x180002523  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180002529  mov     cs:hService, rax
0x180002530  test    rax, rax
0x180002533  jz      short loc_180002599
0x180002535  lea     rdx, ServiceStatus; lpServiceStatus
0x18000253c  mov     cs:ServiceStatus.dwCurrentState, edi
0x180002542  mov     rcx, rax; hServiceStatus
0x180002545  call    cs:__imp_SetServiceStatus
0x18000254b  lea     rax, MessagePumpThreadId
0x180002552  mov     r9, rbx; lpParameter
0x180002555  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000255a  lea     r8, HidServMain; lpStartAddress
0x180002561  xor     edx, edx; dwStackSize
0x180002563  mov     [rsp+38h+dwCreationFlags], esi; dwCreationFlags
0x180002567  xor     ecx, ecx; lpThreadAttributes
0x180002569  call    cs:__imp_CreateThread
0x18000256f  mov     rdi, rax
0x180002572  test    rax, rax
0x180002575  jz      short loc_180002599
0x180002577  or      esi, 0FFFFFFFFh
0x18000257a  mov     rcx, rbx; hHandle
0x18000257d  mov     edx, esi; dwMilliseconds
0x18000257f  call    cs:__imp_WaitForSingleObject
0x180002585  mov     edx, esi; dwMilliseconds
0x180002587  mov     rcx, rdi; hHandle
0x18000258a  call    cs:__imp_WaitForSingleObject
0x180002590  mov     rcx, rdi; hObject
0x180002593  call    cs:__imp_CloseHandle
0x180002599  mov     rcx, rbx; hObject
0x18000259c  call    cs:__imp_CloseHandle
0x1800025a2  mov     rbx, [rsp+38h+arg_0]
0x1800025a7  mov     rsi, [rsp+38h+arg_8]
0x1800025ac  add     rsp, 30h
0x1800025b0  pop     rdi
0x1800025b1  retn
```
