# NGENService::ServiceMain(ulong,ushort * *)

- ea: `0x18001b340`
- end: `0x18001b57c`
- name: `?ServiceMain@NGENService@@YAXKPEAPEAG@Z`
- size: `572`
- prototype: `void(NGENService *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18001bcfc`

## callees

- `0x180004af4`
- `0x180007bf8`
- `0x18001a25c`
- `0x18001a790`
- `0x18001a9d8`
- `0x18001ac30`
- `0x18001b1e4`
- `0x18001b340`
- `0x18002e1d0`
- `0x18002e418`
- `0x180030d84`
- `0x1800366a8`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18001b38b`
- `KERNEL32!DebugBreak` at `0x18001b38b`
- `KERNEL32!TerminateProcess` at `0x18001b3a5`
- `KERNEL32!TerminateProcess` at `0x18001b44c`
- `KERNEL32!TerminateProcess` at `0x18001b3a5`
- `KERNEL32!TerminateProcess` at `0x18001b44c`
- `KERNEL32!GetCurrentProcess` at `0x18001b39a`
- `KERNEL32!GetCurrentProcess` at `0x18001b441`
- `KERNEL32!GetCurrentProcess` at `0x18001b39a`
- `KERNEL32!GetCurrentProcess` at `0x18001b441`
- `KERNEL32!SetEvent` at `0x18001b51f`
- `KERNEL32!SetEvent` at `0x18001b51f`
- `KERNEL32!CloseHandle` at `0x18001b547`
- `KERNEL32!CloseHandle` at `0x18001b547`
- `KERNEL32!GetLastError` at `0x18001b43b`
- `KERNEL32!GetLastError` at `0x18001b43b`
- `ucrtbase_clr0400!_wcsicmp` at `0x18001b3b9`
- `ucrtbase_clr0400!_wcsicmp` at `0x18001b3b9`

## string_xrefs

- `0x18001b52a`: `ShutdownService()\n`
- `0x18001b452`: `Registered service control handler\n`
- `0x18001b47d`: `ServiceMain(): Failed to service to autostart\n`
- `0x18001b4db`: `ServiceMain(): Failed to set non latest service as demand start\n`
- `0x18001b4e7`: `Tried to start a service that wasn't the latest version of CLR Optimization service. Will shutdown\n`

## pseudocode

```c
void __fastcall NGENService::ServiceMain(NGENService *this, _BOOL8 a2, unsigned __int16 **a3)
{
  const wchar_t **v3; // rdi
  int v4; // ebx
  unsigned int ConfigValue; // eax
  const unsigned __int16 *v6; // rdx
  HANDLE CurrentProcess; // rax
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  unsigned int (*v11)(unsigned int, unsigned int, void *, void *); // rdx
  void *v12; // r8
  const unsigned __int16 *v13; // rdx
  HANDLE v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // edx
  const unsigned __int16 *v17; // rdx
  NGENService *v18; // rcx
  unsigned int v19; // eax
  const unsigned __int16 *v20; // rdx
  NGENService *v21; // rcx
  unsigned int v22; // edx
  const unsigned __int16 *v23; // [rsp+20h] [rbp-18h]
  bool v24; // [rsp+40h] [rbp+8h] BYREF
  bool v25; // [rsp+50h] [rbp+18h] BYREF

  v3 = (const wchar_t **)a2;
  v4 = (int)this;
  if ( byte_18007081C )
  {
    ConfigValue = dword_180070818;
  }
  else
  {
    ConfigValue = CLRConfig::GetConfigValue(
                    (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_NGENServiceBreakOnStart,
                    a2,
                    &v24);
    dword_180070818 = ConfigValue;
    byte_18007081C = 1;
  }
  if ( ConfigValue )
    DebugBreak();
  if ( (int)NGENService::InitService(this) < 0 )
  {
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, 1u);
  }
  for ( ; v4; --v4 )
  {
    v8 = _wcsicmp(*v3, L"-startpaused");
    v9 = dword_18006FC10;
    ++v3;
    if ( !v8 )
      v9 = 1;
    dword_18006FC10 = v9;
  }
  v10 = NGENService::g_Options;
  if ( NGENService::g_Options != 1 )
  {
    NGENService::DebugLog((NGENService *)L"Running as standalone executable!\n", v6);
    v10 = NGENService::g_Options;
  }
  NGENService::g_ServiceStatus.dwServiceType = 16;
  *(_QWORD *)&NGENService::g_ServiceStatus.dwControlsAccepted = 0;
  *(_QWORD *)&NGENService::g_ServiceStatus.dwServiceSpecificExitCode = 0;
  NGENService::g_ServiceStatus.dwWaitHint = 0;
  if ( v10 == 1 )
  {
    SString::ConvertToUnicode((SString *)&NGENService::g_sServiceName);
    NGENService::g_hServiceStatusHandle = CLRRegisterServiceCtrlHandlerEx(lpMem, v11, v12);
    if ( !NGENService::g_hServiceStatusHandle )
    {
      GetLastError();
      v14 = GetCurrentProcess();
      TerminateProcess(v14, 1u);
    }
    NGENService::DebugLog((NGENService *)L"Registered service control handler\n", v13);
  }
  NGENService::ServiceUpdateState((NGENService *)2, (unsigned int)v6);
  NGENService::ServiceUpdateState((NGENService *)4, v15);
  if ( (int)NGENService::SetServiceStartType((NGENService *)2, v16) < 0 )
    NGENService::DebugLog((NGENService *)L"ServiceMain(): Failed to service to autostart\n", v17);
  if ( byte_180070814 )
  {
    v19 = dword_180070810;
  }
  else
  {
    v19 = CLRConfig::GetConfigValue(
            (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_NGENUseService,
            (bool)v17,
            &v25);
    dword_180070810 = v19;
    byte_180070814 = 1;
  }
  if ( v19 )
  {
    if ( *(&NGENService::g_Options + 1) || NGENService::IsLatestServiceVersion(v18) )
    {
      if ( dword_18006FC10 )
      {
        NGENService::ServiceUpdateState((NGENService *)6, (unsigned int)v17);
        NGENService::g_bPauseRequested = 1;
        SetEvent(NGENService::g_hSCMRequestEvent);
      }
      NGENService::ServiceWorker(v18);
    }
    else
    {
      if ( (int)NGENService::SetServiceStartType((NGENService *)3, (unsigned int)v17) < 0 )
        NGENService::DebugLog((NGENService *)L"ServiceMain(): Failed to set non latest service as demand start\n", v20);
      NGENService::EventLog(
        0,
        (const unsigned __int16 *)1,
        0x44Fu,
        (unsigned int)L"Tried to start a service that wasn't the latest version of CLR Optimization service. Will shutdown\n",
        v23);
    }
  }
  NGENService::DebugLog((NGENService *)L"ShutdownService()\n", v17);
  NGENService::ControllerShutdown(v21);
  if ( NGENService::g_hRestartEvent )
  {
    CloseHandle(NGENService::g_hRestartEvent);
    NGENService::g_hRestartEvent = 0;
  }
  NGENService::g_bPauseRequested = 0;
  NGENService::g_bStopRequested = 0;
  NGENService::g_LogFile = 0;
  NGENService::ServiceUpdateState((NGENService *)1, v22);
}

```

## disassembly

```asm
0x18001b340  mov     [rsp+arg_8], rbx
0x18001b345  push    rbp
0x18001b346  push    rsi
0x18001b347  push    rdi; unsigned __int16 *
0x18001b348  sub     rsp, 20h
0x18001b34c  xor     esi, esi
0x18001b34e  mov     rdi, rdx
0x18001b351  cmp     cs:byte_18007081C, sil
0x18001b358  mov     ebx, ecx
0x18001b35a  mov     ebp, 1
0x18001b35f  jnz     short loc_18001B381
0x18001b361  lea     r8, [rsp+38h+arg_0]; bool *
0x18001b366  lea     rcx, ?UNSUPPORTED_NGENServiceBreakOnStart@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18001b36d  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18001b372  mov     cs:dword_180070818, eax
0x18001b378  mov     cs:byte_18007081C, bpl
0x18001b37f  jmp     short loc_18001B387
0x18001b381  mov     eax, cs:dword_180070818
0x18001b387  test    eax, eax
0x18001b389  jz      short loc_18001B391
0x18001b38b  call    cs:__imp_DebugBreak
0x18001b391  call    ?InitService@NGENService@@YAJXZ; NGENService::InitService(void)
0x18001b396  test    eax, eax
0x18001b398  jns     short loc_18001B3AB
0x18001b39a  call    cs:__imp_GetCurrentProcess
0x18001b3a0  mov     rcx, rax; hProcess
0x18001b3a3  mov     edx, ebp; uExitCode
0x18001b3a5  call    cs:__imp_TerminateProcess
0x18001b3ab  test    ebx, ebx
0x18001b3ad  jz      short loc_18001B3D9
0x18001b3af  mov     rcx, [rdi]; String1
0x18001b3b2  lea     rdx, aStartpaused; "-startpaused"
0x18001b3b9  call    cs:__imp__wcsicmp
0x18001b3bf  mov     ecx, cs:dword_18006FC10
0x18001b3c5  lea     rdi, [rdi+8]
0x18001b3c9  test    eax, eax
0x18001b3cb  cmovz   ecx, ebp
0x18001b3ce  mov     cs:dword_18006FC10, ecx
0x18001b3d4  add     ebx, 0FFFFFFFFh
0x18001b3d7  jnz     short loc_18001B3AF
0x18001b3d9  mov     eax, dword ptr cs:?g_Options@NGENService@@3U_ServiceOptions@@A; _ServiceOptions NGENService::g_Options
0x18001b3df  cmp     eax, ebp
0x18001b3e1  jz      short loc_18001B3F5
0x18001b3e3  lea     rcx, aRunningAsStand; "Running as standalone executable!\n"
0x18001b3ea  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001b3ef  mov     eax, dword ptr cs:?g_Options@NGENService@@3U_ServiceOptions@@A; _ServiceOptions NGENService::g_Options
0x18001b3f5  mov     cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwServiceType, 10h; _SERVICE_STATUS NGENService::g_ServiceStatus ...
0x18001b3ff  mov     qword ptr cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwControlsAccepted, rsi; _SERVICE_STATUS NGENService::g_ServiceStatus ...
0x18001b406  mov     qword ptr cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, rsi; _SERVICE_STATUS NGENService::g_ServiceStatus ...
0x18001b40d  mov     cs:?g_ServiceStatus@NGENService@@3U_SERVICE_STATUS@@A.dwWaitHint, esi; _SERVICE_STATUS NGENService::g_ServiceStatus ...
0x18001b413  cmp     eax, ebp
0x18001b415  jnz     short loc_18001B45E
0x18001b417  lea     rcx, ?g_sServiceName@NGENService@@3VSString@@A; this
0x18001b41e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001b423  mov     rcx, cs:lpMem; unsigned __int16 *
0x18001b42a  call    ?CLRRegisterServiceCtrlHandlerEx@@YAPEAUSERVICE_STATUS_HANDLE__@@PEBGP6AKKKPEAX1@Z1@Z; CLRRegisterServiceCtrlHandlerEx(ushort const *,ulong (*)(ulong,ulong,void *,void *),void *)
0x18001b42f  mov     cs:?g_hServiceStatusHandle@NGENService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * NGENService::g_hServiceStatusHandle
0x18001b436  test    rax, rax
0x18001b439  jnz     short loc_18001B452
0x18001b43b  call    cs:__imp_GetLastError
0x18001b441  call    cs:__imp_GetCurrentProcess
0x18001b447  mov     rcx, rax; hProcess
0x18001b44a  mov     edx, ebp; uExitCode
0x18001b44c  call    cs:__imp_TerminateProcess
0x18001b452  lea     rcx, aRegisteredServ; "Registered service control handler\n"
0x18001b459  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001b45e  mov     ebx, 2
0x18001b463  mov     ecx, ebx; this
0x18001b465  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001b46a  lea     ecx, [rbx+2]; this
0x18001b46d  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001b472  mov     ecx, ebx; this
0x18001b474  call    ?SetServiceStartType@NGENService@@YAJK@Z; NGENService::SetServiceStartType(ulong)
0x18001b479  test    eax, eax
0x18001b47b  jns     short loc_18001B489
0x18001b47d  lea     rcx, aServicemainFai; "ServiceMain(): Failed to service to aut"...
0x18001b484  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001b489  cmp     cs:byte_180070814, sil
0x18001b490  jnz     short loc_18001B4B2
0x18001b492  lea     r8, [rsp+38h+arg_10]; bool *
0x18001b497  lea     rcx, ?EXTERNAL_NGENUseService@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18001b49e  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18001b4a3  mov     cs:dword_180070810, eax
0x18001b4a9  mov     cs:byte_180070814, bpl
0x18001b4b0  jmp     short loc_18001B4B8
0x18001b4b2  mov     eax, cs:dword_180070810
0x18001b4b8  test    eax, eax
0x18001b4ba  jz      short loc_18001B52A
0x18001b4bc  cmp     dword ptr cs:?g_Options@NGENService@@3U_ServiceOptions@@A+4, esi; _ServiceOptions NGENService::g_Options
0x18001b4c2  jnz     short loc_18001B4FF
0x18001b4c4  call    ?IsLatestServiceVersion@NGENService@@YA_NXZ; NGENService::IsLatestServiceVersion(void)
0x18001b4c9  test    al, al
0x18001b4cb  jnz     short loc_18001B4FF
0x18001b4cd  mov     ecx, 3; this
0x18001b4d2  call    ?SetServiceStartType@NGENService@@YAJK@Z; NGENService::SetServiceStartType(ulong)
0x18001b4d7  test    eax, eax
0x18001b4d9  jns     short loc_18001B4E7
0x18001b4db  lea     rcx, aServicemainFai_0; "ServiceMain(): Failed to set non latest"...
0x18001b4e2  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001b4e7  lea     r9, aTriedToStartAS; "Tried to start a service that wasn't th"...
0x18001b4ee  mov     r8d, 44Fh; unsigned __int16
0x18001b4f4  mov     edx, ebp; unsigned __int16 *
0x18001b4f6  xor     ecx, ecx; this
0x18001b4f8  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x18001b4fd  jmp     short loc_18001B52A
0x18001b4ff  cmp     cs:dword_18006FC10, esi
0x18001b505  jz      short loc_18001B525
0x18001b507  mov     ecx, 6; this
0x18001b50c  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x18001b511  mov     rcx, cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA; hEvent
0x18001b518  mov     cs:?g_bPauseRequested@NGENService@@3V?$Volatile@_N@@A, bpl; Volatile<bool> NGENService::g_bPauseRequested
0x18001b51f  call    cs:__imp_SetEvent
0x18001b525  call    ?ServiceWorker@NGENService@@YAXXZ; NGENService::ServiceWorker(void)
0x18001b52a  lea     rcx, aShutdownservic; "ShutdownService()\n"
0x18001b531  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001b536  call    ?ControllerShutdown@NGENService@@YAXXZ; NGENService::ControllerShutdown(void)
0x18001b53b  mov     rcx, cs:?g_hRestartEvent@NGENService@@3PEAXEA; hObject
0x18001b542  test    rcx, rcx
0x18001b545  jz      short loc_18001B554
0x18001b547  call    cs:__imp_CloseHandle
0x18001b54d  mov     cs:?g_hRestartEvent@NGENService@@3PEAXEA, rsi; void * NGENService::g_hRestartEvent
0x18001b554  mov     cs:?g_bPauseRequested@NGENService@@3V?$Volatile@_N@@A, sil; Volatile<bool> NGENService::g_bPauseRequested
0x18001b55b  mov     ecx, ebp; this
0x18001b55d  mov     cs:?g_bStopRequested@NGENService@@3V?$Volatile@_N@@A, sil; Volatile<bool> NGENService::g_bStopRequested
0x18001b564  mov     cs:?g_LogFile@NGENService@@3VCircularLog@@A, sil; CircularLog NGENService::g_LogFile
0x18001b56b  mov     rbx, [rsp+38h+arg_8]
0x18001b570  add     rsp, 20h
0x18001b574  pop     rdi
0x18001b575  pop     rsi
0x18001b576  pop     rbp
0x18001b577  jmp     ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
```
