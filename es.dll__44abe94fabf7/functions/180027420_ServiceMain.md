# ServiceMain

- ea: `0x180027420`
- end: `0x1800274e1`
- name: `ServiceMain`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009034`
- `0x180027420`
- `0x1800274e8`
- `0x18003ecb0`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180027432`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180027432`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800274ad`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800274ad`

## string_xrefs

- `0x1800274bb`: `SetServiceStatus`
- `0x180027455`: `com\complus\src\events\tier2\service.cpp`
- `0x1800274c7`: `com\complus\src\events\tier2\service.cpp`
- `0x18002744b`: `RegisterServiceControlHandle`

## pseudocode

```c
void ServiceMain()
{
  SERVICE_STATUS_HANDLE v0; // rcx

  v0 = RegisterServiceCtrlHandlerW(L"EventSystem", ServiceControl);
  g_statusHandle = v0;
  if ( !v0 )
  {
    InternalError_Win32(L"com\\complus\\src\\events\\tier2\\service.cpp", 0x4Cu, 0x11u, L"RegisterServiceControlHandle");
    v0 = g_statusHandle;
  }
  g_status.dwServiceType = 32;
  *(_QWORD *)&g_status.dwWin32ExitCode = 0;
  *(_QWORD *)&g_status.dwCurrentState = 2;
  g_status.dwWaitHint = 3000;
  g_status.dwCheckPoint = ++dword_1800642F8;
  if ( !SetServiceStatus(v0, &g_status) )
    InternalError_Win32(L"com\\complus\\src\\events\\tier2\\service.cpp", 0x172u, 0x11u, L"SetServiceStatus");
  RunService();
}

```

## disassembly

```asm
0x180027420  sub     rsp, 38h
0x180027424  lea     rdx, ?ServiceControl@@YAXK@Z; lpHandlerProc
0x18002742b  lea     rcx, ServiceName; "EventSystem"
0x180027432  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180027438  mov     rcx, rax
0x18002743b  mov     cs:?g_statusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_statusHandle
0x180027442  test    rax, rax
0x180027445  jnz     short loc_180027468
0x180027447  lea     r8d, [rax+11h]; unsigned __int16
0x18002744b  lea     r9, aRegisterservic_0; "RegisterServiceControlHandle"
0x180027452  lea     edx, [rax+4Ch]; unsigned int
0x180027455  lea     rcx, aComComplusSrcE_8; "com\\complus\\src\\events\\tier2\\servi"...
0x18002745c  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x180027461  mov     rcx, cs:?g_statusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180027468  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_status ...
0x180027472  mov     qword ptr cs:?g_status@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_status ...
0x18002747d  mov     qword ptr cs:?g_status@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_status ...
0x180027488  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwWaitHint, 0BB8h; _SERVICE_STATUS g_status ...
0x180027492  mov     eax, cs:dword_1800642F8
0x180027498  inc     eax
0x18002749a  mov     cs:dword_1800642F8, eax
0x1800274a0  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCheckPoint, eax; _SERVICE_STATUS g_status ...
0x1800274a6  lea     rdx, ?g_status@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800274ad  call    cs:__imp_SetServiceStatus
0x1800274b3  test    eax, eax
0x1800274b5  jnz     short loc_1800274D4
0x1800274b7  lea     r8d, [rax+11h]; unsigned __int16
0x1800274bb  lea     r9, aSetservicestat_0; "SetServiceStatus"
0x1800274c2  mov     edx, 172h; unsigned int
0x1800274c7  lea     rcx, aComComplusSrcE_8; "com\\complus\\src\\events\\tier2\\servi"...
0x1800274ce  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x1800274d3  nop
0x1800274d4  call    ?RunService@@YAXXZ; RunService(void)
0x1800274d9  nop
0x1800274da  jmp     short $+2
0x1800274dc  add     rsp, 38h
0x1800274e0  retn
0x180045202  push    rbp
0x180045204  sub     rsp, 20h
0x180045208  mov     rbp, rdx
0x18004520b  add     rsp, 20h
0x18004520f  pop     rbp
0x180045210  retn
0x180045212  push    rbp
0x180045214  sub     rsp, 20h
0x180045218  mov     rbp, rdx
0x18004521b  lea     rdx, [rbp+20h]; int *
0x18004521f  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180045224  nop
0x180045225  add     rsp, 20h
0x180045229  pop     rbp
0x18004522a  retn
```
