# ServiceMain(ulong,ushort * *)

- ea: `0x18001cd80`
- end: `0x18001ce40`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `192`
- prototype: `void __fastcall(__int64, const WCHAR **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18001cd14`
- `0x18001cd80`
- `0x18001f0a0`
- `0x18001f1b0`
- `0x18001f56c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001cd9b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001cd9b`
- `ntdll!RtlNtStatusToDosError` at `0x18001ce14`
- `ntdll!RtlNtStatusToDosError` at `0x18001ce14`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, const WCHAR **a2)
{
  const WCHAR *v2; // rcx
  SERVICE_STATUS_HANDLE v3; // rax
  int v4; // eax
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = *a2;
  v7 = 0;
  v3 = RegisterServiceCtrlHandlerExW(v2, PsmpServiceControlHandler, 0);
  PsmpServiceGlobals.dwServiceType = 32;
  PsmpServiceGlobals.dwCurrentState = 2;
  hServiceStatus = v3;
  *(_QWORD *)&PsmpServiceGlobals.dwWin32ExitCode = 0;
  PsmpServiceGlobals.dwCheckPoint = 0;
  PsmpUpdateServiceState(2u);
  v4 = PsmpQueryServiceStartupFlags(&v7);
  v5 = v7;
  if ( v4 < 0 )
    v5 = 0;
  v6 = PsmpInitialize(v5);
  if ( v6 < 0 )
  {
    PsmpServiceGlobals.dwWin32ExitCode = 1066;
    PsmpServiceGlobals.dwServiceSpecificExitCode = RtlNtStatusToDosError(v6);
    PsmpUpdateServiceState(3u);
    PsmpCleanup(v5);
    PsmpUpdateServiceState(1u);
  }
  else
  {
    PsmpServiceGlobals.dwControlsAccepted = 4288;
    PsmpUpdateServiceState(4u);
  }
}

```

## disassembly

```asm
0x18001cd80  push    rbx
0x18001cd82  sub     rsp, 20h
0x18001cd86  mov     rcx, [rdx]; lpServiceName
0x18001cd89  xor     r8d, r8d; lpContext
0x18001cd8c  lea     rdx, ?PsmpServiceControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18001cd93  mov     [rsp+28h+arg_8], 0
0x18001cd9b  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18001cda1  mov     ecx, 2; unsigned int
0x18001cda6  mov     cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwServiceType, 20h ; ' '; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001cdb0  mov     cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwCurrentState, ecx; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001cdb6  mov     cs:hServiceStatus, rax
0x18001cdbd  mov     qword ptr cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwWin32ExitCode, 0; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001cdc8  mov     cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwCheckPoint, 0; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001cdd2  call    ?PsmpUpdateServiceState@@YAJK@Z; PsmpUpdateServiceState(ulong)
0x18001cdd7  lea     rcx, [rsp+28h+arg_8]
0x18001cddc  call    PsmpQueryServiceStartupFlags
0x18001cde1  mov     ebx, [rsp+28h+arg_8]
0x18001cde5  xor     ecx, ecx
0x18001cde7  test    eax, eax
0x18001cde9  cmovs   ebx, ecx
0x18001cdec  mov     ecx, ebx
0x18001cdee  call    PsmpInitialize
0x18001cdf3  test    eax, eax
0x18001cdf5  js      short loc_18001CE08
0x18001cdf7  mov     cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwControlsAccepted, 10C0h; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001ce01  mov     ecx, 4
0x18001ce06  jmp     short loc_18001CE36
0x18001ce08  mov     ecx, eax; Status
0x18001ce0a  mov     cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwWin32ExitCode, 42Ah; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001ce14  call    cs:__imp_RtlNtStatusToDosError
0x18001ce1a  mov     ecx, 3; unsigned int
0x18001ce1f  mov     cs:?PsmpServiceGlobals@@3U_PSM_SERVICE_GLOBALS@@A.dwServiceSpecificExitCode, eax; _PSM_SERVICE_GLOBALS PsmpServiceGlobals ...
0x18001ce25  call    ?PsmpUpdateServiceState@@YAJK@Z; PsmpUpdateServiceState(ulong)
0x18001ce2a  mov     ecx, ebx
0x18001ce2c  call    PsmpCleanup
0x18001ce31  mov     ecx, 1; unsigned int
0x18001ce36  add     rsp, 20h
0x18001ce3a  pop     rbx
0x18001ce3b  jmp     ?PsmpUpdateServiceState@@YAJK@Z; PsmpUpdateServiceState(ulong)
```
