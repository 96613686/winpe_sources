# ServiceMain(ulong,ushort * *)

- ea: `0x180004f30`
- end: `0x1800050c0`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `400`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180004770`
- `0x180004b30`
- `0x180004cd4`
- `0x180004f30`

## import_xrefs

- `ntdll!EtwRegisterTraceGuidsW` at `0x180004fcc`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180004fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000508a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000508a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005080`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005080`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005040`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005040`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  __int64 *v2; // rbx
  __int64 *v3; // rdi
  __int64 v4; // r8
  SERVICE_STATUS_HANDLE v5; // rax
  int LastError; // eax
  bool v7; // zf
  bool v8; // zf
  _QWORD v9[3]; // [rsp+40h] [rbp-18h] BYREF

  qword_18000A730 = 0;
  v2 = &WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v3 = &WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  qword_18000A738 = 1;
  do
  {
    v4 = *v3;
    v9[0] = v4;
    ++v3;
    v9[1] = 0;
    v2[4] = v4;
    ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
      WppControlCallback,
      v2,
      v4,
      1,
      v9,
      0,
      0,
      v2 + 1);
    v2 = (__int64 *)*v2;
  }
  while ( v2 );
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids);
  ServiceStatus.dwWaitHint = 0;
  ServiceStatus.dwServiceType = 48;
  ServiceStatus.dwCurrentState = 2;
  *(_OWORD *)&ServiceStatus.dwControlsAccepted = 0;
  v5 = RegisterServiceCtrlHandlerExW(L"FDResPub", (LPHANDLER_FUNCTION_EX)ServiceCtrlHandler, 0);
  hServiceStatus = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v7 = LastError == 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError == 0;
    }
    if ( !v7 )
      goto LABEL_16;
    v5 = hServiceStatus;
    if ( !hServiceStatus )
      goto LABEL_15;
  }
  if ( SetServiceStatus(v5, &ServiceStatus) )
    goto LABEL_15;
  LastError = GetLastError();
  v8 = LastError == 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = LastError == 0;
  }
  if ( v8 )
  {
LABEL_15:
    LastError = FDResPub_Startup();
    if ( !LastError )
      return;
  }
LABEL_16:
  ServiceStatus.dwWin32ExitCode = LastError;
  FDResPub_ShutdownCallback(0);
}

```

## disassembly

```asm
0x180004f30  mov     [rsp+arg_0], rbx
0x180004f35  push    rdi
0x180004f36  sub     rsp, 50h
0x180004f3a  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x180004f41  mov     cs:qword_18000A730, 0
0x180004f4c  lea     rbx, WPP_MAIN_CB
0x180004f53  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180004f5a  mov     cs:WPP_GLOBAL_Control, rbx
0x180004f61  lea     rdi, WPP_REGISTRATION_GUIDS
0x180004f68  mov     cs:WPP_MAIN_CB, 0
0x180004f73  mov     cs:qword_18000A738, 1
0x180004f7e  mov     r8, [rdi]
0x180004f81  lea     rax, [rbx+8]
0x180004f85  mov     [rsp+58h+var_20], rax
0x180004f8a  lea     rcx, WppControlCallback
0x180004f91  mov     [rsp+58h+var_28], 0
0x180004f9a  lea     rax, [rsp+58h+var_18]
0x180004f9f  mov     [rsp+58h+var_18], r8
0x180004fa4  lea     rdi, [rdi+8]
0x180004fa8  mov     [rsp+58h+var_10], 0
0x180004fb1  mov     r9d, 1
0x180004fb7  mov     [rsp+58h+var_30], 0
0x180004fc0  mov     rdx, rbx
0x180004fc3  mov     [rsp+58h+var_38], rax
0x180004fc8  mov     [rbx+20h], r8
0x180004fcc  call    cs:__imp_EtwRegisterTraceGuidsW
0x180004fd2  mov     rbx, [rbx]
0x180004fd5  test    rbx, rbx
0x180004fd8  jnz     short loc_180004F7E
0x180004fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fe1  lea     rax, WPP_GLOBAL_Control
0x180004fe8  cmp     rcx, rax
0x180004feb  jz      short loc_180005006
0x180004fed  cmp     byte ptr [rcx+19h], 4
0x180004ff1  jb      short loc_180005006
0x180004ff3  mov     rcx, [rcx+10h]
0x180004ff7  lea     edx, [rbx+0Ah]
0x180004ffa  lea     r8, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids
0x180005001  call    WPP_SF_s
0x180005006  xorps   xmm0, xmm0
0x180005009  mov     cs:ServiceStatus.dwWaitHint, 0
0x180005013  xor     r8d, r8d; lpContext
0x180005016  mov     cs:ServiceStatus.dwServiceType, 30h ; '0'
0x180005020  lea     rdx, ?ServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180005027  mov     cs:ServiceStatus.dwCurrentState, 2
0x180005031  lea     rcx, ServiceName; "FDResPub"
0x180005038  movdqu  xmmword ptr cs:ServiceStatus.dwControlsAccepted, xmm0
0x180005040  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180005046  mov     cs:hServiceStatus, rax
0x18000504d  mov     ebx, 80070000h
0x180005052  test    rax, rax
0x180005055  jnz     short loc_180005076
0x180005057  call    cs:__imp_GetLastError
0x18000505d  test    eax, eax
0x18000505f  jle     short loc_180005068
0x180005061  movzx   eax, ax
0x180005064  or      eax, ebx
0x180005066  test    eax, eax
0x180005068  jnz     short loc_1800050A6
0x18000506a  mov     rax, cs:hServiceStatus
0x180005071  test    rax, rax
0x180005074  jz      short loc_18000509D
0x180005076  lea     rdx, ServiceStatus; lpServiceStatus
0x18000507d  mov     rcx, rax; hServiceStatus
0x180005080  call    cs:__imp_SetServiceStatus
0x180005086  test    eax, eax
0x180005088  jnz     short loc_18000509D
0x18000508a  call    cs:__imp_GetLastError
0x180005090  test    eax, eax
0x180005092  jle     short loc_18000509B
0x180005094  movzx   eax, ax
0x180005097  or      eax, ebx
0x180005099  test    eax, eax
0x18000509b  jnz     short loc_1800050A6
0x18000509d  call    ?FDResPub_Startup@@YAJXZ; FDResPub_Startup(void)
0x1800050a2  test    eax, eax
0x1800050a4  jz      short loc_1800050B5
0x1800050a6  xor     edx, edx; unsigned __int8
0x1800050a8  mov     cs:ServiceStatus.dwWin32ExitCode, eax
0x1800050ae  xor     ecx, ecx; void *
0x1800050b0  call    ?FDResPub_ShutdownCallback@@YAXPEAXE@Z; FDResPub_ShutdownCallback(void *,uchar)
0x1800050b5  mov     rbx, [rsp+58h+arg_0]
0x1800050ba  add     rsp, 50h
0x1800050be  pop     rdi
0x1800050bf  retn
```
