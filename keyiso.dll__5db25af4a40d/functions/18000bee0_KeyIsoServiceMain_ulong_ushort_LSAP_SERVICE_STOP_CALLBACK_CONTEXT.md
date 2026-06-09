# KeyIsoServiceMain(ulong,ushort * *,_LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)

- ea: `0x18000bee0`
- end: `0x18000c0a1`
- name: `?KeyIsoServiceMain@@YAJKPEAPEAGPEAU_LSAP_SERVICE_STOP_CALLBACK_CONTEXT@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **, struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180009674`
- `0x18000bee0`
- `0x180013c18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bf64`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bf64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c031`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c031`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bf22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bf22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c028`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c028`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000bfb6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000bfb6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c07c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c07c`

## string_xrefs

- `0x18000bf36`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\keyiso.cxx`
- `0x18000bf8e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\keyiso.cxx`
- `0x18000bff6`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\keyiso.cxx`

## pseudocode

```c
__int64 __fastcall KeyIsoServiceMain(__int64 a1, unsigned __int16 **a2, struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *a3)
{
  _QWORD *v4; // rdi
  DWORD v5; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v8; // r9
  signed int v9; // eax
  DWORD v10; // eax
  void *v11; // rcx
  SERVICE_STATUS_HANDLE v12; // rcx

  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwControlsAccepted = 1;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  v4 = LocalAlloc(0x40u, 0x10u);
  if ( !v4 )
  {
    v5 = -2146893810;
    DebugTraceError(2148073486LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\keyiso.cxx", 361);
    return v5;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v4[1] = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v8 = 370;
LABEL_7:
    DebugTraceError(v5, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\keyiso.cxx", v8);
    goto LABEL_14;
  }
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"KeyIso", KipServiceCtrlHandler, EventW);
  if ( !hServiceStatus )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v8 = 382;
    goto LABEL_7;
  }
  v10 = KipEnableRpcInterface();
  v5 = v10;
  if ( !v10 )
  {
    v12 = hServiceStatus;
    *((_QWORD *)a3 + 1) = v4[1];
    *(_QWORD *)a3 = KipStopCallback;
    *((_QWORD *)a3 + 2) = v4;
    ServiceStatus.dwControlsAccepted = 1;
    ServiceStatus.dwCurrentState = 4;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    if ( SetServiceStatus(v12, &ServiceStatus) )
      return 0;
    else
      KipDisableRpcInterface();
    return v5;
  }
  DebugTraceError(v10, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\keyiso.cxx", 394);
  ServiceStatus.dwWin32ExitCode = v5;
  ServiceStatus.dwCurrentState = 1;
LABEL_14:
  if ( (v5 & 0x80000000) != 0 )
  {
    v11 = (void *)v4[1];
    if ( v11 )
      CloseHandle(v11);
    LocalFree(v4);
  }
  return v5;
}

```

## disassembly

```asm
0x18000bee0  mov     [rsp+arg_0], rbx
0x18000bee5  mov     [rsp+arg_8], rsi
0x18000beea  push    rdi
0x18000beeb  sub     rsp, 20h
0x18000beef  mov     edx, 10h; uBytes
0x18000bef4  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18000befe  xorps   xmm0, xmm0
0x18000bf01  mov     cs:ServiceStatus.dwCurrentState, 2
0x18000bf0b  mov     rsi, r8
0x18000bf0e  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x18000bf18  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm0
0x18000bf1f  lea     ecx, [rdx+30h]; uFlags
0x18000bf22  call    cs:__imp_LocalAlloc
0x18000bf28  mov     rdi, rax
0x18000bf2b  test    rax, rax
0x18000bf2e  jnz     short loc_18000BF58
0x18000bf30  mov     r9d, 169h
0x18000bf36  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bf3d  lea     rdx, aStatus_0; "status"
0x18000bf44  mov     ecx, 8009000Eh
0x18000bf49  mov     ebx, 8009000Eh
0x18000bf4e  call    DebugTraceError
0x18000bf53  jmp     loc_18000C08F
0x18000bf58  xor     r9d, r9d; lpName
0x18000bf5b  xor     r8d, r8d; bInitialState
0x18000bf5e  xor     ecx, ecx; lpEventAttributes
0x18000bf60  lea     edx, [r9+1]; bManualReset
0x18000bf64  call    cs:__imp_CreateEventW
0x18000bf6a  mov     [rdi+8], rax
0x18000bf6e  test    rax, rax
0x18000bf71  jnz     short loc_18000BFA5
0x18000bf73  call    cs:__imp_GetLastError
0x18000bf79  mov     ebx, eax
0x18000bf7b  test    eax, eax
0x18000bf7d  jle     short loc_18000BF88
0x18000bf7f  movzx   ebx, ax
0x18000bf82  or      ebx, 80070000h
0x18000bf88  mov     r9d, 172h
0x18000bf8e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bf95  mov     ecx, ebx
0x18000bf97  lea     rdx, aStatus_0; "status"
0x18000bf9e  call    DebugTraceError
0x18000bfa3  jmp     short loc_18000C01B
0x18000bfa5  mov     r8, rax; lpContext
0x18000bfa8  lea     rdx, KipServiceCtrlHandler; lpHandlerProc
0x18000bfaf  lea     rcx, ServiceName; "KeyIso"
0x18000bfb6  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000bfbc  mov     cs:hServiceStatus, rax
0x18000bfc3  test    rax, rax
0x18000bfc6  jnz     short loc_18000BFE5
0x18000bfc8  call    cs:__imp_GetLastError
0x18000bfce  mov     ebx, eax
0x18000bfd0  test    eax, eax
0x18000bfd2  jle     short loc_18000BFDD
0x18000bfd4  movzx   ebx, ax
0x18000bfd7  or      ebx, 80070000h
0x18000bfdd  mov     r9d, 17Eh
0x18000bfe3  jmp     short loc_18000BF8E
0x18000bfe5  call    KipEnableRpcInterface
0x18000bfea  mov     ebx, eax
0x18000bfec  test    eax, eax
0x18000bfee  jz      short loc_18000C039
0x18000bff0  mov     r9d, 18Ah
0x18000bff6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bffd  lea     rdx, aStatus_0; "status"
0x18000c004  mov     ecx, eax
0x18000c006  call    DebugTraceError
0x18000c00b  mov     cs:ServiceStatus.dwWin32ExitCode, ebx
0x18000c011  mov     cs:ServiceStatus.dwCurrentState, 1
0x18000c01b  test    ebx, ebx
0x18000c01d  jns     short loc_18000C08F
0x18000c01f  mov     rcx, [rdi+8]; hObject
0x18000c023  test    rcx, rcx
0x18000c026  jz      short loc_18000C02E
0x18000c028  call    cs:__imp_CloseHandle
0x18000c02e  mov     rcx, rdi; hMem
0x18000c031  call    cs:__imp_LocalFree
0x18000c037  jmp     short loc_18000C08F
0x18000c039  mov     rax, [rdi+8]
0x18000c03d  lea     rdx, ServiceStatus; lpServiceStatus
0x18000c044  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000c04b  mov     [rsi+8], rax
0x18000c04f  lea     rax, KipStopCallback
0x18000c056  mov     [rsi], rax
0x18000c059  mov     [rsi+10h], rdi
0x18000c05d  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x18000c067  mov     cs:ServiceStatus.dwCurrentState, 4
0x18000c071  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x18000c07c  call    cs:__imp_SetServiceStatus
0x18000c082  test    eax, eax
0x18000c084  jnz     short loc_18000C08D
0x18000c086  call    KipDisableRpcInterface
0x18000c08b  jmp     short loc_18000C08F
0x18000c08d  xor     ebx, ebx
0x18000c08f  mov     rsi, [rsp+28h+arg_8]
0x18000c094  mov     eax, ebx
0x18000c096  mov     rbx, [rsp+28h+arg_0]
0x18000c09b  add     rsp, 20h
0x18000c09f  pop     rdi
0x18000c0a0  retn
```
