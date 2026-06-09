# CGPService::GPServiceHandlerEx(ulong,ulong,void *,void *)

- ea: `0x180019920`
- end: `0x180019fae`
- name: `?GPServiceHandlerEx@CGPService@@CAKKKPEAX0@Z`
- size: `1678`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180016640`
- `0x1800183d4`
- `0x180019920`
- `0x18001ae40`
- `0x18004de80`
- `0x18006f70c`
- `0x180075770`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b6b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019b60`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019b60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b79`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180019b93`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180019b93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e15`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019e15`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180019b38`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180019b38`

## string_xrefs

- `0x180019a82`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_PRESHUTDOWN`
- `0x180019aa4`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_PRESHUTDOWN`
- `0x180019ead`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_SHUTDOWN`
- `0x180019ed0`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_SHUTDOWN`
- `0x180019ef8`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_STOP`
- `0x180019f1d`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_STOP`
- `0x180019bb6`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_POWEREVENT`
- `0x180019bde`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_POWEREVENT`
- `0x180019995`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_TRIGGEREVENT`
- `0x1800199b7`: `CGPService::GPServiceHandlerEx: SERVICE_CONTROL_TRIGGEREVENT`
- `0x1800199e1`: `CGPService::GPServiceHandlerEx returning ERROR_SHUTDOWN_IN_PROGRESS`
- `0x180019a03`: `CGPService::GPServiceHandlerEx returning ERROR_SHUTDOWN_IN_PROGRESS`
- `0x180019a32`: `CGPService::GPServiceHandlerEx returning ERROR_SERVICE_NOT_ACTIVE`
- `0x180019a54`: `CGPService::GPServiceHandlerEx returning ERROR_SERVICE_NOT_ACTIVE`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGPService::GPServiceHandlerEx(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        struct _SERVICE_STATUS *lpContext)
{
  DWORD LastError; // r15d
  DWORD v7; // ecx
  DWORD v8; // ecx
  DWORD v9; // ecx
  int v10; // ecx
  int v11; // ecx
  void (*v12)(unsigned int, const unsigned __int16 *, ...); // rax
  HANDLE Thread; // rax
  int v14; // r8d
  void (*v15)(unsigned int, const unsigned __int16 *, ...); // rax
  void *v16; // rdx
  void (*v17)(void *, unsigned int, const unsigned __int16 *, char **); // rcx
  DWORD v18; // edi
  DWORD v19; // edi
  DWORD v20; // edi
  const wchar_t *v21; // rdx
  const wchar_t *v22; // rdx
  DWORD v23; // edi
  DWORD v24; // edi
  DWORD v25; // edi
  void **v27; // [rsp+38h] [rbp-40h] BYREF
  void *v28; // [rsp+40h] [rbp-38h] BYREF
  __int64 v29; // [rsp+48h] [rbp-30h]
  struct _EVENT_DESCRIPTOR *v30; // [rsp+50h] [rbp-28h]
  __int128 v31; // [rsp+58h] [rbp-20h]
  unsigned int v32[4]; // [rsp+68h] [rbp-10h] BYREF

  LastError = 120;
  if ( !lpContext )
    return LastError;
  v7 = dwControl - 1;
  if ( !v7 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_STOP", lpEventData);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_STOP", lpEventData);
      }
    }
    v28 = 0;
    v29 = 0;
    v30 = (struct _EVENT_DESCRIPTOR *)SCM_NOTIFICATION_INFORMATION;
    v31 = 0;
    v27 = &CGPPolicyProcessingModeEvent::`vftable';
    v32[0] = 1;
    CGPPolicyProcessingModeEvent::ReportOperationalEvent((CGPPolicyProcessingModeEvent *)&v27);
    CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(&v28);
    lpContext[1].dwControlsAccepted = 1;
    lpContext[4].dwControlsAccepted = 2;
    CGPService::UpdateServiceStatus((CGPService *)lpContext, 3u, 2u, 0x249F0u);
    return (unsigned int)CGPService::Stop((struct CGPService *)lpContext);
  }
  v8 = v7 - 4;
  if ( !v8 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      return LastError;
    v15 = g_lpDebugMsg;
    if ( !g_lpDebugMsg )
    {
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(4u, L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_SHUTDOWN");
      return LastError;
    }
    v22 = L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_SHUTDOWN";
    goto LABEL_117;
  }
  v9 = v8 - 8;
  if ( !v9 )
  {
    v14 = *(_DWORD *)&g_dwDebugLevel;
    v15 = g_lpDebugMsg;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_POWEREVENT");
      }
      else
      {
        v16 = g_lpDebugMsgContextInstance;
        v17 = g_lpDebugMsgContext;
        if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        {
LABEL_53:
          if ( dwEventType > 9 )
          {
            v23 = dwEventType - 10;
            if ( v23 )
            {
              v24 = v23 - 1;
              if ( v24 )
              {
                v25 = v24 - 7;
                if ( !v25 )
                {
                  if ( v14 )
                  {
                    if ( !v15 )
                    {
                      if ( v16 && v17 )
                        RedirectDebugMsg(4u, L"PBT_APMRESUMEAUTOMATIC");
                      goto LABEL_113;
                    }
                    v21 = L"PBT_APMRESUMEAUTOMATIC";
LABEL_109:
                    v15(4u, v21);
                  }
LABEL_113:
                  CGPService::s_dwResumeTick = GetTickCount();
                  return LastError;
                }
                if ( v25 != 32769 || !v14 )
                  return LastError;
                if ( !v15 )
                {
                  if ( v16 && v17 )
                    RedirectDebugMsg(4u, L"PBT_POWERSETTINGCHANGE");
                  return LastError;
                }
                v22 = L"PBT_POWERSETTINGCHANGE";
              }
              else
              {
                if ( !v14 )
                  return LastError;
                if ( !v15 )
                {
                  if ( v16 && v17 )
                    RedirectDebugMsg(4u, L"PBT_APMOEMEVENT");
                  return LastError;
                }
                v22 = L"PBT_APMOEMEVENT";
              }
            }
            else
            {
              if ( !v14 )
                return LastError;
              if ( !v15 )
              {
                if ( v16 && v17 )
                  RedirectDebugMsg(4u, L"PBT_APMPOWERSTATUSCHANGE");
                return LastError;
              }
              v22 = L"PBT_APMPOWERSTATUSCHANGE";
            }
          }
          else if ( dwEventType == 9 )
          {
            if ( !v14 )
              return LastError;
            if ( !v15 )
            {
              if ( v16 && v17 )
                RedirectDebugMsg(4u, L"PBT_APMBATTERYLOW");
              return LastError;
            }
            v22 = L"PBT_APMBATTERYLOW";
          }
          else if ( dwEventType )
          {
            v18 = dwEventType - 2;
            if ( v18 )
            {
              v19 = v18 - 2;
              if ( v19 )
              {
                v20 = v19 - 2;
                if ( v20 )
                {
                  if ( v20 != 1 )
                    return LastError;
                  if ( v14 )
                  {
                    if ( !v15 )
                    {
                      if ( v16 && v17 )
                        RedirectDebugMsg(4u, L"PBT_APMRESUMESUSPEND");
                      goto LABEL_113;
                    }
                    v21 = L"PBT_APMRESUMESUSPEND";
                    goto LABEL_109;
                  }
                  goto LABEL_113;
                }
                if ( !v14 )
                  return LastError;
                if ( !v15 )
                {
                  if ( v16 && v17 )
                    RedirectDebugMsg(4u, L"PBT_APMRESUMECRITICAL");
                  return LastError;
                }
                v22 = L"PBT_APMRESUMECRITICAL";
              }
              else
              {
                if ( !v14 )
                  return LastError;
                if ( !v15 )
                {
                  if ( v16 && v17 )
                    RedirectDebugMsg(4u, L"PBT_APMSUSPEND");
                  return LastError;
                }
                v22 = L"PBT_APMSUSPEND";
              }
            }
            else
            {
              if ( !v14 )
                return LastError;
              if ( !v15 )
              {
                if ( v16 && v17 )
                  RedirectDebugMsg(4u, L"PBT_APMQUERYSUSPENDFAILED");
                return LastError;
              }
              v22 = L"PBT_APMQUERYSUSPENDFAILED";
            }
          }
          else
          {
            if ( !v14 )
              return LastError;
            if ( !v15 )
            {
              if ( v16 && v17 )
                RedirectDebugMsg(4u, L"PBT_APMQUERYSUSPEND");
              return LastError;
            }
            v22 = L"PBT_APMQUERYSUSPEND";
          }
LABEL_117:
          v15(4u, v22);
          return LastError;
        }
        RedirectDebugMsg(4u, L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_POWEREVENT");
      }
      v15 = g_lpDebugMsg;
      v14 = *(_DWORD *)&g_dwDebugLevel;
    }
    v16 = g_lpDebugMsgContextInstance;
    v17 = g_lpDebugMsgContext;
    goto LABEL_53;
  }
  v10 = v9 - 2;
  if ( v10 )
  {
    if ( v10 != 17 )
      return LastError;
    v11 = *(_DWORD *)&g_dwDebugLevel;
    v12 = g_lpDebugMsg;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_14;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_TRIGGEREVENT", lpEventData);
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      {
LABEL_14:
        if ( lpContext[1].dwControlsAccepted )
        {
          if ( v11 )
          {
            if ( v12 )
            {
              v12(4u, L"CGPService::GPServiceHandlerEx returning ERROR_SHUTDOWN_IN_PROGRESS", lpEventData);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"CGPService::GPServiceHandlerEx returning ERROR_SHUTDOWN_IN_PROGRESS", lpEventData);
            }
          }
          return 1115;
        }
        else if ( !CGPService::s_pInstance )
        {
          if ( v11 )
          {
            if ( v12 )
            {
              v12(4u, L"CGPService::GPServiceHandlerEx returning ERROR_SERVICE_NOT_ACTIVE", lpEventData);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"CGPService::GPServiceHandlerEx returning ERROR_SERVICE_NOT_ACTIVE", lpEventData);
            }
          }
          return 1062;
        }
        return LastError;
      }
      RedirectDebugMsg(4u, L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_TRIGGEREVENT", lpEventData);
    }
    v12 = g_lpDebugMsg;
    v11 = *(_DWORD *)&g_dwDebugLevel;
    goto LABEL_14;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_PRESHUTDOWN", lpEventData);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::GPServiceHandlerEx: SERVICE_CONTROL_PRESHUTDOWN", lpEventData);
    }
  }
  v28 = 0;
  v29 = 0;
  v30 = (struct _EVENT_DESCRIPTOR *)SCM_NOTIFICATION_INFORMATION;
  v31 = 0;
  v27 = &CGPPolicyProcessingModeEvent::`vftable';
  v32[0] = 0;
  COperationalBaseEvent::AddArg((COperationalBaseEvent *)&v28, v32);
  if ( v30 )
    COperationalBaseEvent::ReportOperationalEvent((COperationalBaseEvent *)&v28, v30);
  CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(&v28);
  lpContext[1].dwControlsAccepted = 1;
  lpContext[4].dwControlsAccepted = 2;
  if ( !lpContext[4].dwServiceSpecificExitCode )
  {
    lpContext[2].dwCurrentState = 3;
    lpContext[2].dwCheckPoint = 2;
    lpContext[2].dwWaitHint = 30000;
    if ( !SetServiceStatus(*(SERVICE_STATUS_HANDLE *)&lpContext->dwServiceType, lpContext + 2) )
      GetLastError();
  }
  Thread = CreateThread(0, 0, CGPService::PreshutdownAndStopThread, lpContext, 0, 0);
  if ( Thread )
    CloseHandle(Thread);
  else
    LastError = GetLastError();
  RegDeleteKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\GPStartup", 0, 0);
  return LastError;
}

```

## disassembly

```asm
0x180019920  push    rbp
0x180019922  push    rbx
0x180019923  push    rsi
0x180019924  push    rdi
0x180019925  push    r12
0x180019927  push    r15
0x180019929  mov     rbp, rsp
0x18001992c  sub     rsp, 78h
0x180019930  mov     rsi, r9
0x180019933  mov     edi, edx
0x180019935  mov     r15d, 78h ; 'x'
0x18001993b  xor     r12d, r12d
0x18001993e  mov     [rbp+arg_18], r12
0x180019942  mov     [rbp+var_48], r12
0x180019946  test    r9, r9
0x180019949  jz      loc_180019F9E
0x18001994f  sub     ecx, 1
0x180019952  jz      loc_180019EE3
0x180019958  lea     ebx, [r15-74h]
0x18001995c  sub     ecx, ebx
0x18001995e  jz      loc_180019E94
0x180019964  sub     ecx, 8
0x180019967  jz      loc_180019B9E
0x18001996d  sub     ecx, 2
0x180019970  jz      loc_180019A6D
0x180019976  cmp     ecx, 11h
0x180019979  jnz     loc_180019F9E
0x18001997f  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x180019985  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001998c  test    ecx, ecx
0x18001998e  jz      short loc_1800199D2
0x180019990  test    rax, rax
0x180019993  jz      short loc_1800199A5
0x180019995  lea     rdx, aCgpserviceGpse_4; "CGPService::GPServiceHandlerEx: SERVICE"...
0x18001999c  mov     ecx, ebx
0x18001999e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199a3  jmp     short loc_1800199C5
0x1800199a5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800199ac  jz      short loc_1800199D2
0x1800199ae  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800199b5  jz      short loc_1800199D2
0x1800199b7  lea     rdx, aCgpserviceGpse_4; "CGPService::GPServiceHandlerEx: SERVICE"...
0x1800199be  mov     ecx, ebx; unsigned int
0x1800199c0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800199c5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800199cc  mov     ecx, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x1800199d2  cmp     [rsi+24h], r12d
0x1800199d6  jz      short loc_180019A1C
0x1800199d8  test    ecx, ecx
0x1800199da  jz      short loc_180019A11
0x1800199dc  test    rax, rax
0x1800199df  jz      short loc_1800199F1
0x1800199e1  lea     rdx, aCgpserviceGpse_2; "CGPService::GPServiceHandlerEx returnin"...
0x1800199e8  mov     ecx, ebx
0x1800199ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199ef  jmp     short loc_180019A11
0x1800199f1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800199f8  jz      short loc_180019A11
0x1800199fa  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180019a01  jz      short loc_180019A11
0x180019a03  lea     rdx, aCgpserviceGpse_2; "CGPService::GPServiceHandlerEx returnin"...
0x180019a0a  mov     ecx, ebx; unsigned int
0x180019a0c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180019a11  mov     r15d, 45Bh
0x180019a17  jmp     loc_180019F9E
0x180019a1c  cmp     cs:?s_pInstance@CGPService@@2PEAV1@EA, r12; CGPService * CGPService::s_pInstance
0x180019a23  jnz     loc_180019F9E
0x180019a29  test    ecx, ecx
0x180019a2b  jz      short loc_180019A62
0x180019a2d  test    rax, rax
0x180019a30  jz      short loc_180019A42
0x180019a32  lea     rdx, aCgpserviceGpse_1; "CGPService::GPServiceHandlerEx returnin"...
0x180019a39  mov     ecx, ebx
0x180019a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a40  jmp     short loc_180019A62
0x180019a42  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180019a49  jz      short loc_180019A62
0x180019a4b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180019a52  jz      short loc_180019A62
0x180019a54  lea     rdx, aCgpserviceGpse_1; "CGPService::GPServiceHandlerEx returnin"...
0x180019a5b  mov     ecx, ebx; unsigned int
0x180019a5d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180019a62  mov     r15d, 426h
0x180019a68  jmp     loc_180019F9E
0x180019a6d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180019a74  jz      short loc_180019AB2
0x180019a76  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180019a7d  test    rax, rax
0x180019a80  jz      short loc_180019A92
0x180019a82  lea     rdx, aCgpserviceGpse_3; "CGPService::GPServiceHandlerEx: SERVICE"...
0x180019a89  mov     ecx, ebx
0x180019a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a90  jmp     short loc_180019AB2
0x180019a92  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180019a99  jz      short loc_180019AB2
0x180019a9b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180019aa2  jz      short loc_180019AB2
0x180019aa4  lea     rdx, aCgpserviceGpse_3; "CGPService::GPServiceHandlerEx: SERVICE"...
0x180019aab  mov     ecx, ebx; unsigned int
0x180019aad  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180019ab2  mov     [rbp+var_38], r12
0x180019ab6  mov     [rbp+var_30], r12
0x180019aba  lea     rax, SCM_NOTIFICATION_INFORMATION
0x180019ac1  mov     [rbp+var_28], rax
0x180019ac5  xorps   xmm0, xmm0
0x180019ac8  movdqu  [rbp+var_20], xmm0
0x180019acd  lea     rax, ??_7CGPPolicyProcessingModeEvent@@6B@; const CGPPolicyProcessingModeEvent::`vftable'
0x180019ad4  mov     [rbp+var_40], rax
0x180019ad8  mov     [rbp+var_10], r12d
0x180019adc  lea     rdx, [rbp+var_10]; unsigned int *
0x180019ae0  lea     rcx, [rbp+var_38]; this
0x180019ae4  call    ?AddArg@COperationalBaseEvent@@IEAAKAEAK@Z; COperationalBaseEvent::AddArg(ulong &)
0x180019ae9  mov     rdx, [rbp+var_28]; struct _EVENT_DESCRIPTOR *
0x180019aed  test    rdx, rdx
0x180019af0  jz      short loc_180019AFC
0x180019af2  lea     rcx, [rbp+var_38]; this
0x180019af6  call    ?ReportOperationalEvent@COperationalBaseEvent@@IEAAKPEBU_EVENT_DESCRIPTOR@@@Z; COperationalBaseEvent::ReportOperationalEvent(_EVENT_DESCRIPTOR const *)
0x180019afb  nop
0x180019afc  lea     rcx, [rbp+var_38]; this
0x180019b00  call    ??1CServiceConfigurationChangeOperationalEvent@@QEAA@XZ; CServiceConfigurationChangeOperationalEvent::~CServiceConfigurationChangeOperationalEvent(void)
0x180019b05  mov     dword ptr [rsi+24h], 1
0x180019b0c  mov     dword ptr [rsi+78h], 2
0x180019b13  cmp     [rsi+80h], r12d
0x180019b1a  jnz     short loc_180019B48
0x180019b1c  lea     rdx, [rsi+38h]; lpServiceStatus
0x180019b20  mov     dword ptr [rdx+4], 3
0x180019b27  mov     dword ptr [rsi+4Ch], 2
0x180019b2e  mov     dword ptr [rsi+50h], 7530h
0x180019b35  mov     rcx, [rsi]; hServiceStatus
0x180019b38  call    cs:__imp_SetServiceStatus
0x180019b3e  test    eax, eax
0x180019b40  jnz     short loc_180019B48
0x180019b42  call    cs:__imp_GetLastError
0x180019b48  mov     [rsp+78h+lpThreadId], r12; lpThreadId
0x180019b4d  mov     [rsp+78h+dwCreationFlags], r12d; dwCreationFlags
0x180019b52  mov     r9, rsi; lpParameter
0x180019b55  lea     r8, ?PreshutdownAndStopThread@CGPService@@CAKPEAX@Z; lpStartAddress
0x180019b5c  xor     edx, edx; dwStackSize
0x180019b5e  xor     ecx, ecx; lpThreadAttributes
0x180019b60  call    cs:__imp_CreateThread
0x180019b66  test    rax, rax
0x180019b69  jnz     short loc_180019B76
0x180019b6b  call    cs:__imp_GetLastError
0x180019b71  mov     r15d, eax
0x180019b74  jmp     short loc_180019B7F
0x180019b76  mov     rcx, rax; hObject
0x180019b79  call    cs:__imp_CloseHandle
0x180019b7f  xor     r9d, r9d; Reserved
0x180019b82  xor     r8d, r8d; samDesired
0x180019b85  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180019b8c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019b93  call    cs:__imp_RegDeleteKeyExW
0x180019b99  jmp     loc_180019F9E
0x180019b9e  mov     r8d, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x180019ba5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180019bac  test    r8d, r8d
0x180019baf  jz      short loc_180019BFA
0x180019bb1  test    rax, rax
0x180019bb4  jz      short loc_180019BC6
0x180019bb6  lea     rdx, aCgpserviceGpse_0; "CGPService::GPServiceHandlerEx: SERVICE"...
0x180019bbd  mov     ecx, ebx
0x180019bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bc4  jmp     short loc_180019BEC
0x180019bc6  mov     rdx, cs:?g_lpDebugMsgContextInstance@@3PEAXEA; void * g_lpDebugMsgContextInstance
0x180019bcd  mov     rcx, cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180019bd4  test    rdx, rdx
0x180019bd7  jz      short loc_180019C08
0x180019bd9  test    rcx, rcx
0x180019bdc  jz      short loc_180019C08
0x180019bde  lea     rdx, aCgpserviceGpse_0; "CGPService::GPServiceHandlerEx: SERVICE"...
0x180019be5  mov     ecx, ebx; unsigned int
0x180019be7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180019bec  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180019bf3  mov     r8d, cs:?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x180019bfa  mov     rdx, cs:?g_lpDebugMsgContextInstance@@3PEAXEA; void * g_lpDebugMsgContextInstance
0x180019c01  mov     rcx, cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180019c08  cmp     edi, 9
0x180019c0b  ja      loc_180019D8B
0x180019c11  jz      loc_180019D53
0x180019c17  test    edi, edi
0x180019c19  jz      loc_180019D1B
0x180019c1f  sub     edi, 2
0x180019c22  jz      loc_180019CE3
0x180019c28  sub     edi, 2
0x180019c2b  jz      short loc_180019CAB
0x180019c2d  sub     edi, 2
0x180019c30  jz      short loc_180019C73
0x180019c32  cmp     edi, 1
0x180019c35  jnz     loc_180019F9E
0x180019c3b  test    r8d, r8d
0x180019c3e  jz      loc_180019E15
0x180019c44  test    rax, rax
0x180019c47  jz      short loc_180019C55
0x180019c49  lea     rdx, aPbtApmresumesu; "PBT_APMRESUMESUSPEND"
0x180019c50  jmp     loc_180019DF4
0x180019c55  test    rdx, rdx
0x180019c58  jz      loc_180019E15
0x180019c5e  test    rcx, rcx
0x180019c61  jz      loc_180019E15
0x180019c67  lea     rdx, aPbtApmresumesu; "PBT_APMRESUMESUSPEND"
0x180019c6e  jmp     loc_180019E0E
0x180019c73  test    r8d, r8d
0x180019c76  jz      loc_180019F9E
0x180019c7c  test    rax, rax
0x180019c7f  jz      short loc_180019C8D
0x180019c81  lea     rdx, aPbtApmresumecr; "PBT_APMRESUMECRITICAL"
0x180019c88  jmp     loc_180019E3B
0x180019c8d  test    rdx, rdx
0x180019c90  jz      loc_180019F9E
0x180019c96  test    rcx, rcx
0x180019c99  jz      loc_180019F9E
0x180019c9f  lea     rdx, aPbtApmresumecr; "PBT_APMRESUMECRITICAL"
0x180019ca6  jmp     loc_180019ED7
0x180019cab  test    r8d, r8d
0x180019cae  jz      loc_180019F9E
0x180019cb4  test    rax, rax
0x180019cb7  jz      short loc_180019CC5
0x180019cb9  lea     rdx, aPbtApmsuspend; "PBT_APMSUSPEND"
0x180019cc0  jmp     loc_180019E3B
0x180019cc5  test    rdx, rdx
0x180019cc8  jz      loc_180019F9E
0x180019cce  test    rcx, rcx
0x180019cd1  jz      loc_180019F9E
0x180019cd7  lea     rdx, aPbtApmsuspend; "PBT_APMSUSPEND"
0x180019cde  jmp     loc_180019ED7
0x180019ce3  test    r8d, r8d
0x180019ce6  jz      loc_180019F9E
0x180019cec  test    rax, rax
0x180019cef  jz      short loc_180019CFD
0x180019cf1  lea     rdx, aPbtApmquerysus; "PBT_APMQUERYSUSPENDFAILED"
0x180019cf8  jmp     loc_180019E3B
0x180019cfd  test    rdx, rdx
0x180019d00  jz      loc_180019F9E
0x180019d06  test    rcx, rcx
0x180019d09  jz      loc_180019F9E
0x180019d0f  lea     rdx, aPbtApmquerysus; "PBT_APMQUERYSUSPENDFAILED"
0x180019d16  jmp     loc_180019ED7
0x180019d1b  test    r8d, r8d
0x180019d1e  jz      loc_180019F9E
0x180019d24  test    rax, rax
0x180019d27  jz      short loc_180019D35
0x180019d29  lea     rdx, aPbtApmquerysus_0; "PBT_APMQUERYSUSPEND"
0x180019d30  jmp     loc_180019E3B
0x180019d35  test    rdx, rdx
0x180019d38  jz      loc_180019F9E
0x180019d3e  test    rcx, rcx
0x180019d41  jz      loc_180019F9E
0x180019d47  lea     rdx, aPbtApmquerysus_0; "PBT_APMQUERYSUSPEND"
0x180019d4e  jmp     loc_180019ED7
0x180019d53  test    r8d, r8d
0x180019d56  jz      loc_180019F9E
0x180019d5c  test    rax, rax
0x180019d5f  jz      short loc_180019D6D
0x180019d61  lea     rdx, aPbtApmbatteryl; "PBT_APMBATTERYLOW"
0x180019d68  jmp     loc_180019E3B
0x180019d6d  test    rdx, rdx
0x180019d70  jz      loc_180019F9E
0x180019d76  test    rcx, rcx
0x180019d79  jz      loc_180019F9E
0x180019d7f  lea     rdx, aPbtApmbatteryl; "PBT_APMBATTERYLOW"
0x180019d86  jmp     loc_180019ED7
0x180019d8b  sub     edi, 0Ah
0x180019d8e  jz      loc_180019E62
0x180019d94  sub     edi, 1
0x180019d97  jz      loc_180019E26
0x180019d9d  sub     edi, 7
0x180019da0  jz      short loc_180019DE3
0x180019da2  cmp     edi, 8001h
0x180019da8  jnz     loc_180019F9E
0x180019dae  test    r8d, r8d
0x180019db1  jz      loc_180019F9E
0x180019db7  test    rax, rax
0x180019dba  jz      short loc_180019DC5
0x180019dbc  lea     rdx, aPbtPowersettin; "PBT_POWERSETTINGCHANGE"
0x180019dc3  jmp     short loc_180019E3B
0x180019dc5  test    rdx, rdx
0x180019dc8  jz      loc_180019F9E
0x180019dce  test    rcx, rcx
0x180019dd1  jz      loc_180019F9E
0x180019dd7  lea     rdx, aPbtPowersettin; "PBT_POWERSETTINGCHANGE"
0x180019dde  jmp     loc_180019ED7
0x180019de3  test    r8d, r8d
0x180019de6  jz      short loc_180019E15
0x180019de8  test    rax, rax
0x180019deb  jz      short loc_180019DFD
0x180019ded  lea     rdx, aPbtApmresumeau; "PBT_APMRESUMEAUTOMATIC"
0x180019df4  mov     ecx, ebx
0x180019df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dfb  jmp     short loc_180019E15
0x180019dfd  test    rdx, rdx
0x180019e00  jz      short loc_180019E15
0x180019e02  test    rcx, rcx
0x180019e05  jz      short loc_180019E15
0x180019e07  lea     rdx, aPbtApmresumeau; "PBT_APMRESUMEAUTOMATIC"
0x180019e0e  mov     ecx, ebx; unsigned int
0x180019e10  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180019e15  call    cs:__imp_GetTickCount
0x180019e1b  mov     cs:?s_dwResumeTick@CGPService@@0KA, eax; ulong CGPService::s_dwResumeTick
0x180019e21  jmp     loc_180019F9E
0x180019e26  test    r8d, r8d
  ... truncated ...
```
