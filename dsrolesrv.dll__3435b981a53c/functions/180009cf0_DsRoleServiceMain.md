# DsRoleServiceMain

- ea: `0x180009cf0`
- end: `0x180009ed0`
- name: `DsRoleServiceMain`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180009bfc`
- `0x180009cf0`
- `0x180009ee0`
- `0x18000a020`
- `0x18000a0b0`
- `0x18001e234`
- `0x18001fc28`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009e72`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009e78`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009e72`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e1d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009d32`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180009d32`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009e14`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009e14`
- `LSASRV!LsapDssetupInitializeGetPrimaryDomainInformationOpState` at `0x180009dfe`
- `LSASRV!LsapDssetupInitializeGetPrimaryDomainInformationOpState` at `0x180009dfe`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180009d59`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180009d59`

## string_xrefs

- `0x180009e23`: `Global\DsRoleServiceStartEvent`
- `0x180009e40`: `Global\DsRoleServiceStartEvent`
- `0x180009e47`: `Error opening %ws: %d\n`
- `0x180009cff`: `DS Role Server Service starting\n`
- `0x180009e8c`: `DS Role Server Service started\n`
- `0x180009e9f`: `DS Role Server Service initialization failed. Service stopped\n`

## pseudocode

```c
__int64 __fastcall DsRoleServiceMain(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v4; // esi
  HANDLE EventW; // rax
  void *v6; // rax
  void *v7; // rdi
  DWORD LastError; // eax
  __int64 v9; // r9
  __int64 v10; // rcx
  char v12; // [rsp+68h] [rbp+20h] BYREF

  v4 = -1073741823;
  DsRolepLogPrintRoutine(4, "DS Role Server Service starting\n");
  DsRoleState = 1;
  DsRoleServiceStoppable = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  DsRoleStopEvent = EventW;
  if ( !EventW )
    goto LABEL_15;
  hService = RegisterServiceCtrlHandlerExW(L"DsRoleSvc", DsRoleServiceHandler, EventW);
  if ( !hService )
    goto LABEL_15;
  DsRoleServiceStatus.dwServiceType = 32;
  DsRoleServiceStatus.dwCurrentState = 1;
  *(_OWORD *)&DsRoleServiceStatus.dwWin32ExitCode = 0;
  DsRoleServiceStatus.dwControlsAccepted = 1;
  if ( (unsigned __int8)UpdateStatus(2)
    && (int)DsRolepInitialize() >= 0
    && (unsigned __int8)UpdateStatus(2)
    && !(unsigned int)DsRolepInitializeEvents()
    && (a3[1] = DsRoleStopEvent, *a3 = DsRoleShutDownEx, a3[2] = 0, (unsigned __int8)UpdateStatus(4)) )
  {
    LsapDssetupInitializeGetPrimaryDomainInformationOpState(DsRoleIGetPrimaryDomainInformationOpState);
    v6 = DsRoleOpenEvent();
    v7 = v6;
    if ( v6 )
    {
      SetEvent(v6);
      CloseHandle(v7);
      DsRolepLogPrintRoutine(4, "Set event %ws\n", L"Global\\DsRoleServiceStartEvent");
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 2 )
      {
        v9 = 2;
        v10 = 4;
      }
      else
      {
        v9 = LastError;
        v10 = 1;
      }
      DsRolepLogPrintRoutine(v10, "Error opening %ws: %d\n", L"Global\\DsRoleServiceStartEvent", v9);
    }
    DsRoleState = 2;
    GetTickCount64();
    DsRoleServiceLastActivity = GetTickCount64();
    DsRoleStartServiceIdleCheckTimer();
    v4 = 0;
    DsRolepLogPrintRoutine(4, "DS Role Server Service started\n");
  }
  else
  {
LABEL_15:
    DsRoleShutDownEx(&v12);
    a3[1] = 0;
    *a3 = 0;
    a3[2] = 0;
    DsRolepLogPrintRoutine(4, "DS Role Server Service initialization failed. Service stopped\n");
  }
  return v4;
}

```

## disassembly

```asm
0x180009cf0  push    rbx
0x180009cf2  push    rsi
0x180009cf3  push    rdi
0x180009cf4  push    r15
0x180009cf6  sub     rsp, 28h
0x180009cfa  mov     ebx, 4
0x180009cff  lea     rdx, aDsRoleServerSe_2; "DS Role Server Service starting\n"
0x180009d06  mov     ecx, ebx
0x180009d08  mov     rdi, r8
0x180009d0b  mov     esi, 0C0000001h
0x180009d10  call    DsRolepLogPrintRoutine
0x180009d15  lea     r15d, [rbx-3]
0x180009d19  xor     r9d, r9d; lpName
0x180009d1c  mov     edx, r15d; bManualReset
0x180009d1f  mov     cs:DsRoleState, r15d
0x180009d26  xor     r8d, r8d; bInitialState
0x180009d29  mov     cs:DsRoleServiceStoppable, r15b
0x180009d30  xor     ecx, ecx; lpEventAttributes
0x180009d32  call    cs:__imp_CreateEventW
0x180009d38  mov     cs:DsRoleStopEvent, rax
0x180009d3f  test    rax, rax
0x180009d42  jz      loc_180009E95
0x180009d48  mov     r8, rax; lpContext
0x180009d4b  lea     rdx, DsRoleServiceHandler; lpHandlerProc
0x180009d52  lea     rcx, ServiceName; "DsRoleSvc"
0x180009d59  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180009d5f  mov     cs:hService, rax
0x180009d66  test    rax, rax
0x180009d69  jz      loc_180009E95
0x180009d6f  xorps   xmm0, xmm0
0x180009d72  mov     cs:DsRoleServiceStatus.dwServiceType, 20h ; ' '
0x180009d7c  lea     ecx, [rbx-2]
0x180009d7f  mov     cs:DsRoleServiceStatus.dwCurrentState, r15d
0x180009d86  movups  xmmword ptr cs:DsRoleServiceStatus.dwWin32ExitCode, xmm0
0x180009d8d  mov     cs:DsRoleServiceStatus.dwControlsAccepted, r15d
0x180009d94  call    UpdateStatus
0x180009d99  test    al, al
0x180009d9b  jz      loc_180009E95
0x180009da1  call    DsRolepInitialize
0x180009da6  test    eax, eax
0x180009da8  js      loc_180009E95
0x180009dae  lea     ecx, [rbx-2]
0x180009db1  call    UpdateStatus
0x180009db6  test    al, al
0x180009db8  jz      loc_180009E95
0x180009dbe  call    DsRolepInitializeEvents
0x180009dc3  test    eax, eax
0x180009dc5  jnz     loc_180009E95
0x180009dcb  mov     rax, cs:DsRoleStopEvent
0x180009dd2  mov     ecx, ebx
0x180009dd4  mov     [rdi+8], rax
0x180009dd8  lea     rax, DsRoleShutDownEx
0x180009ddf  mov     [rdi], rax
0x180009de2  mov     qword ptr [rdi+10h], 0
0x180009dea  call    UpdateStatus
0x180009def  test    al, al
0x180009df1  jz      loc_180009E95
0x180009df7  lea     rcx, DsRoleIGetPrimaryDomainInformationOpState
0x180009dfe  call    cs:__imp_LsapDssetupInitializeGetPrimaryDomainInformationOpState
0x180009e04  call    DsRoleOpenEvent
0x180009e09  mov     rdi, rax
0x180009e0c  test    rax, rax
0x180009e0f  jz      short loc_180009E3A
0x180009e11  mov     rcx, rax; hEvent
0x180009e14  call    cs:__imp_SetEvent
0x180009e1a  mov     rcx, rdi; hObject
0x180009e1d  call    cs:__imp_CloseHandle
0x180009e23  lea     r8, aGlobalDsrolese; "Global\\DsRoleServiceStartEvent"
0x180009e2a  mov     ecx, ebx
0x180009e2c  lea     rdx, aSetEventWs; "Set event %ws\n"
0x180009e33  call    DsRolepLogPrintRoutine
0x180009e38  jmp     short loc_180009E68
0x180009e3a  call    cs:__imp_GetLastError
0x180009e40  lea     r8, aGlobalDsrolese; "Global\\DsRoleServiceStartEvent"
0x180009e47  lea     rdx, aErrorOpeningWs; "Error opening %ws: %d\n"
0x180009e4e  cmp     eax, 2
0x180009e51  jz      short loc_180009E5B
0x180009e53  mov     r9d, eax
0x180009e56  mov     ecx, r15d
0x180009e59  jmp     short loc_180009E63
0x180009e5b  mov     r9d, 2
0x180009e61  mov     ecx, ebx
0x180009e63  call    DsRolepLogPrintRoutine
0x180009e68  mov     cs:DsRoleState, 2
0x180009e72  call    cs:__imp_GetTickCount64
0x180009e78  call    cs:__imp_GetTickCount64
0x180009e7e  mov     cs:DsRoleServiceLastActivity, rax
0x180009e85  call    DsRoleStartServiceIdleCheckTimer
0x180009e8a  xor     esi, esi
0x180009e8c  lea     rdx, aDsRoleServerSe; "DS Role Server Service started\n"
0x180009e93  jmp     short loc_180009EBD
0x180009e95  lea     rcx, [rsp+48h+arg_18]
0x180009e9a  call    DsRoleShutDownEx
0x180009e9f  lea     rdx, aDsRoleServerSe_1; "DS Role Server Service initialization f"...
0x180009ea6  mov     qword ptr [rdi+8], 0
0x180009eae  mov     qword ptr [rdi], 0
0x180009eb5  mov     qword ptr [rdi+10h], 0
0x180009ebd  mov     ecx, ebx
0x180009ebf  call    DsRolepLogPrintRoutine
0x180009ec4  mov     eax, esi
0x180009ec6  add     rsp, 28h
0x180009eca  pop     r15
0x180009ecc  pop     rdi
0x180009ecd  pop     rsi
0x180009ece  pop     rbx
0x180009ecf  retn
```
