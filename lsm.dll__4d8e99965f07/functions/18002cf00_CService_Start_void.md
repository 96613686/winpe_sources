# CService::Start(void)

- ea: `0x18002cf00`
- end: `0x18002dc01`
- name: `?Start@CService@@QEAAJXZ`
- size: `3329`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002cdf0`

## callees

- `0x180001b90`
- `0x1800077a0`
- `0x18000c684`
- `0x18000f320`
- `0x180012cf8`
- `0x180012fd8`
- `0x18001f2d0`
- `0x18001f5f0`
- `0x180022030`
- `0x18002701c`
- `0x18002772c`
- `0x18002c2c4`
- `0x18002cf00`
- `0x18003020c`
- `0x180031448`
- `0x1800493fc`
- `0x18004985c`
- `0x180049e54`
- `0x18004a428`
- `0x18004a5ec`
- `0x18004a858`
- `0x18004ae70`
- `0x18004b168`
- `0x18004b200`
- `0x18004b24c`
- `0x18004d00c`
- `0x18004ec5c`
- `0x1800530d8`
- `0x180055694`
- `0x18006d7cc`
- `0x18007e144`
- `0x180097fc8`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfb4`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18002d7d2`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18002d7d2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002d0ad`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002dacb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002d0ad`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002dacb`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002cf9f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002cf9f`

## string_xrefs

- `0x18002cf46`: `LSM Service Start...`
- `0x18002cff9`: `RegisterServiceCtrlHandlerEx`
- `0x18002d065`: `RegisterGpuStateUpdateNotifications`
- `0x18002d597`: `this->CreateRCMReadyEvent failed`
- `0x18002d711`: `TestDelaySetReadyEvent`
- `0x18002d786`: `SetTermSrvReadyEvent`
- `0x18002d99a`: `Console not created by SMSS`
- `0x18002da40`: `GetInstanceOfPluginMgr() failed`
- `0x18002da8b`: `ptrPluginMgr->Initialize() failed`
- `0x18002db8a`: `LSM Service Start failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CService::Start(CService *this)
{
  struct ISessionManagerInternal **v1; // rsi
  unsigned __int16 *v2; // rdx
  unsigned __int16 *v3; // rcx
  int v4; // r8d
  int v5; // r9d
  SERVICE_STATUS_HANDLE v6; // rax
  signed int LastError; // eax
  signed int v8; // ebx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char **v12; // rax
  char *v13; // rdx
  int updated; // eax
  const char **v15; // rax
  int v16; // eax
  int InstanceOfSessionManagerInternal; // eax
  CDefTSNotifySink *v18; // rax
  CDefTSNotifySink *v19; // rdi
  int v20; // eax
  int v21; // eax
  int InstanceOfWinlogonNotify; // eax
  _QWORD *v23; // r14
  int InstanceOfPublicRpc; // eax
  int InstanceOfPrivateRpc; // eax
  int InstanceOfCsrMgr; // eax
  int InstanceOfGpuManager; // eax
  int RCMReadyEvent; // ebx
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  int v32; // eax
  int v33; // eax
  CService *v34; // rcx
  int ready; // eax
  int v36; // eax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64, _QWORD, __int64); // rbx
  unsigned int v39; // eax
  int v40; // eax
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  int v44; // eax
  int v45; // eax
  CPolicyMonitor *v46; // rax
  CPolicyMonitor *v47; // rax
  const char *v48; // rax
  int InstanceOfPluginMgr; // eax
  int v50; // r8d
  int v51; // r9d
  int v52; // eax
  CService *v53; // rcx
  int v54; // r8d
  int v55; // r9d
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  int v59; // eax
  const char **v61; // [rsp+28h] [rbp-50h]
  const char **v62; // [rsp+38h] [rbp-40h]
  const char *v63; // [rsp+40h] [rbp-38h] BYREF
  const char *v64; // [rsp+48h] [rbp-30h] BYREF
  const char *v65; // [rsp+50h] [rbp-28h] BYREF
  __int64 v66; // [rsp+58h] [rbp-20h] BYREF
  __int64 v67; // [rsp+60h] [rbp-18h] BYREF
  __int64 v68; // [rsp+68h] [rbp-10h] BYREF
  const char *v69; // [rsp+C0h] [rbp+48h] BYREF
  const char *v70; // [rsp+C8h] [rbp+50h] BYREF
  __int64 v71; // [rsp+D0h] [rbp+58h] BYREF
  CDefTSNotifySink *v72; // [rsp+D8h] [rbp+60h] BYREF

  v69 = (const char *)this;
  v1 = _pService;
  v68 = 0;
  v67 = 0;
  v66 = 0;
  v71 = 0;
  v72 = 0;
  RegisterTraceLoggingProvider();
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v69 = "LSM Service Start...";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v3,
      (unsigned int)&dword_1800C5A7C,
      v4,
      v5,
      (__int64)&v69);
  }
  CUtils::DebugBreakIfAskedEx(v3, v2);
  *((_DWORD *)v1 + 24) = 32;
  *(struct ISessionManagerInternal **)((char *)v1 + 100) = (struct ISessionManagerInternal *)2;
  *(struct ISessionManagerInternal **)((char *)v1 + 108) = 0;
  *((_DWORD *)v1 + 29) = 0;
  *((_DWORD *)v1 + 30) = 60000;
  v6 = RegisterServiceCtrlHandlerExW(L"Lsm", CService::ServiceCtrlHandler, v1);
  v1[11] = (struct ISessionManagerInternal *)v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v8, 0);
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_92;
      v70 = "Start";
      v63 = "RegisterServiceCtrlHandlerEx";
      v64 = "Warning HResult failed";
      v62 = &v70;
      v12 = &v63;
      v13 = (char *)qword_1800C5A40;
      goto LABEL_90;
    }
  }
  updated = CService::RegisterGpuStateUpdateNotifications((CService *)v1);
  v8 = updated;
  if ( updated < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)updated, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "RegisterGpuStateUpdateNotifications";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C5A04;
    goto LABEL_91;
  }
  SetServiceStatus((SERVICE_STATUS_HANDLE)v1[11], (LPSERVICE_STATUS)(v1 + 12));
  v16 = CGlassTerminal::InitializeGlassTerminalWork();
  v8 = v16;
  if ( v16 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v16, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "CGlassTerminal::InitializeGlassTerminalWork";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)qword_1800C59C8;
    goto LABEL_91;
  }
  InstanceOfSessionManagerInternal = ISessionManagerInternal::GetInstanceOfSessionManagerInternal(v1);
  v8 = InstanceOfSessionManagerInternal;
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfSessionManagerInternal, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "::GetInstanceOfSessionManager";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C598C;
    goto LABEL_91;
  }
  v18 = (CDefTSNotifySink *)operator new(0x6C0u, (const struct std::nothrow_t *)&std::nothrow);
  v19 = v18;
  v69 = (const char *)v18;
  if ( v18 )
  {
    CDefTSNotifySink::CDefTSNotifySink(v18, "CSCMNotify");
    *(_QWORD *)v19 = &CSCMNotify::`vftable';
    *((_DWORD *)v19 + 422) = 0;
    v8 = CSCMNotify::Initialize(v19);
  }
  else
  {
    v19 = 0;
  }
  v72 = v19;
  if ( !v19 )
  {
    v8 = -2147024882;
    goto LABEL_87;
  }
  (*(void (__fastcall **)(CDefTSNotifySink *))(*(_QWORD *)v19 + 8LL))(v19);
  if ( v8 < 0 )
  {
LABEL_87:
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v8, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v48 = "new CSCMNotify";
    v13 = (char *)qword_1800C5950;
    goto LABEL_89;
  }
  v20 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)*v1 + 32LL))(*v1, &v71);
  v8 = v20;
  if ( v20 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v20, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "GetInstanceOfEventDispatcher";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C5914;
    goto LABEL_91;
  }
  v21 = (*(__int64 (__fastcall **)(__int64, CDefTSNotifySink *, struct ISessionManagerInternal **))(*(_QWORD *)v71 + 48LL))(
          v71,
          v19,
          v1 + 6);
  v8 = v21;
  if ( v21 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v21, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "EventDisp->Advise";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)qword_1800C58D8;
    goto LABEL_91;
  }
  InstanceOfWinlogonNotify = IWinlogonNotify::GetInstanceOfWinlogonNotify(v1 + 4);
  v8 = InstanceOfWinlogonNotify;
  if ( InstanceOfWinlogonNotify < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfWinlogonNotify, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "IWinlogonNotify::GetInstanceOfWinlogonNotify";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C589C;
    goto LABEL_91;
  }
  v23 = v1 + 1;
  InstanceOfPublicRpc = IPublicRpc::GetInstanceOfPublicRpc(v1 + 1);
  v8 = InstanceOfPublicRpc;
  if ( InstanceOfPublicRpc < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfPublicRpc, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "IPublicRpc::GetInstanceOfPublicRpc";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)qword_1800C5860;
    goto LABEL_91;
  }
  InstanceOfPrivateRpc = IPrivateRpc::GetInstanceOfPrivateRpc(v1 + 2);
  v8 = InstanceOfPrivateRpc;
  if ( InstanceOfPrivateRpc < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfPrivateRpc, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "IPrivateRpc::GetInstanceOfPrivateRpc";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C5824;
    goto LABEL_91;
  }
  InstanceOfCsrMgr = ICsrMgr::GetInstanceOfCsrMgr(v1 + 3);
  v8 = InstanceOfCsrMgr;
  if ( InstanceOfCsrMgr < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfCsrMgr, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "ICsrMgr::GetInstanceOfCsrMgr";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)qword_1800C57E8;
    goto LABEL_91;
  }
  InstanceOfGpuManager = CGpuManager::GetInstanceOfGpuManager(v1 + 7);
  v8 = InstanceOfGpuManager;
  if ( InstanceOfGpuManager < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfGpuManager, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "CGpuManager::GetInstanceOfGpuManager";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C57AC;
    goto LABEL_91;
  }
  CGpuManager::EnableDisableHWGpuInSessions(v1[7]);
  RCMReadyEvent = CService::CreateRCMReadyEvent((CService *)v1);
  if ( RCMReadyEvent < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      LODWORD(v69) = RCMReadyEvent;
      v70 = "this->CreateRCMReadyEvent failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DF020,
        (unsigned int)byte_1800C5785,
        v29,
        v30,
        (__int64)&v70,
        (__int64)&v69);
    }
  }
  v31 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v1[2] + 24LL))(v1[2]);
  v8 = v31;
  if ( v31 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v31, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "PrivateRpc->Start";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C5749;
    goto LABEL_91;
  }
  v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 24LL))(*v23);
  v8 = v32;
  if ( v32 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v32, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "PublicRpc->Start";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C570D;
    goto LABEL_91;
  }
  v33 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 40LL))(*v23);
  if ( v33 < 0 )
    _DbgPrintMessage(8, "StartRemote failed with 0x%x", v33);
  ready = CService::TestDelaySetReadyEvent(v34);
  v8 = ready;
  if ( ready < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)ready, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "TestDelaySetReadyEvent";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C56D1;
    goto LABEL_91;
  }
  v36 = CService::SetTermSrvReadyEvent((CService *)v1);
  v8 = v36;
  if ( v36 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v36, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "SetTermSrvReadyEvent";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C5695;
    goto LABEL_91;
  }
  v37 = v71;
  v38 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v71 + 32LL);
  v39 = WTSGetServiceSessionId();
  v40 = v38(v37, 3, v39, 0xFFFFFFFFLL);
  v8 = v40;
  LODWORD(v69) = v40;
  if ( v40 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v40, 0);
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v64 = "WaitForSessionState( Disconnected, SessionZero )";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C5659;
    goto LABEL_91;
  }
  if ( (unsigned int)CUtility::IsConsoleSessionCreatedBySmss() )
  {
    LODWORD(v70) = -1;
    v44 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, const char **))(*(_QWORD *)*v1 + 216LL))(
            *v1,
            &v70);
    v8 = v44;
    if ( v44 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v44, 0);
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_92;
      v64 = "Start";
      v63 = "GetInitialConsoleSessionId";
      v65 = "Warning HResult failed";
      v62 = &v64;
      v61 = &v63;
      v15 = &v65;
      v13 = byte_1800C561D;
      goto LABEL_91;
    }
    v45 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v71 + 32LL))(
            v71,
            9,
            (unsigned int)v70,
            0xFFFFFFFFLL);
    v8 = v45;
    LODWORD(v69) = v45;
    if ( v45 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v45, 0);
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_92;
      v65 = "Start";
      v64 = "WaitForSessionState( CsrInitialized, SessionOne )";
      v63 = "Warning HResult failed";
      v62 = &v65;
      v61 = &v64;
      v15 = &v63;
      v13 = byte_1800C55E1;
      goto LABEL_91;
    }
  }
  else if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v70 = "Console not created by SMSS";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v41,
      (unsigned int)&byte_1800C55BF,
      v42,
      v43,
      (__int64)&v70);
  }
  v46 = (CPolicyMonitor *)operator new(0x6C8u, (const struct std::nothrow_t *)&std::nothrow);
  v70 = (const char *)v46;
  if ( v46 )
  {
    v47 = CPolicyMonitor::CPolicyMonitor(v46, (int *)&v69);
    v8 = (int)v69;
  }
  else
  {
    v47 = 0;
  }
  SmartPtr<ITerminal>::operator=(v1 + 5, v47);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_92;
    v70 = "Start";
    v48 = "CPolicyMonitor";
    v13 = byte_1800C5583;
LABEL_89:
    v65 = v48;
    v64 = "Warning HResult failed";
    v62 = &v70;
    v12 = &v65;
LABEL_90:
    v61 = v12;
    v15 = &v64;
LABEL_91:
    LODWORD(v69) = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v9,
      (_DWORD)v13,
      v10,
      v11,
      (__int64)v15,
      (__int64)v61,
      (__int64)&v69,
      (__int64)v62);
    goto LABEL_92;
  }
  InstanceOfPluginMgr = ITSPluginMgr::GetInstanceOfPluginMgr(v1 + 8);
  if ( InstanceOfPluginMgr < 0 && (unsigned int)dword_1800DF020 > 3 )
  {
    LODWORD(v69) = InstanceOfPluginMgr;
    v70 = "GetInstanceOfPluginMgr() failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DF020,
      (unsigned int)byte_1800C5559,
      v50,
      v51,
      (__int64)&v70,
      (__int64)&v69);
  }
  v52 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v1[8] + 32LL))(v1[8]);
  if ( v52 < 0 )
  {
    v53 = (CService *)(unsigned int)dword_1800DF020;
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      LODWORD(v69) = v52;
      v70 = "ptrPluginMgr->Initialize() failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DF020,
        (unsigned int)&byte_1800C552F,
        v54,
        v55,
        (__int64)&v70,
        (__int64)&v69);
    }
  }
  CService::ResetRegKeyValues(v53);
  *((_DWORD *)v1 + 25) = 4;
  *(struct ISessionManagerInternal **)((char *)v1 + 116) = 0;
  SetServiceStatus((SERVICE_STATUS_HANDLE)v1[11], (LPSERVICE_STATUS)(v1 + 12));
LABEL_92:
  if ( v8 )
  {
    CrimsonHelper::RaiseEvent<long>(&CrimsonHelper::s_instance, EVENT_LSM_FAILED_TO_START, (unsigned int)v8);
    v59 = (unsigned __int16)v8;
    if ( (v8 & 0x1FFF0000) != 0x70000 )
      v59 = 1359;
    *((_DWORD *)v1 + 27) = v59;
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      LODWORD(v69) = v8;
      v70 = "LSM Service Start failed!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v56,
        (unsigned int)qword_1800C5508,
        v57,
        v58,
        (__int64)&v70,
        (__int64)&v69);
    }
    CService::Stop((CService *)v1);
  }
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v72);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v71);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v66);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v67);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v68);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002cf00  mov     [rsp-40h+arg_0], rcx
0x18002cf05  push    rbp
0x18002cf06  push    rbx
0x18002cf07  push    rsi
0x18002cf08  push    rdi
0x18002cf09  push    r12
0x18002cf0b  push    r13
0x18002cf0d  push    r14
0x18002cf0f  push    r15
0x18002cf11  mov     rbp, rsp
0x18002cf14  sub     rsp, 78h
0x18002cf18  mov     rsi, cs:?_pService@@3PEAVCService@@EA; CService * _pService
0x18002cf1f  xor     r13d, r13d
0x18002cf22  mov     [rbp+var_10], r13
0x18002cf26  mov     [rbp+var_18], r13
0x18002cf2a  mov     [rbp+var_20], r13
0x18002cf2e  mov     [rbp+arg_10], r13
0x18002cf32  mov     [rbp+arg_18], r13
0x18002cf36  call    ?RegisterTraceLoggingProvider@@YAXXZ; RegisterTraceLoggingProvider(void)
0x18002cf3b  mov     eax, cs:dword_1800DF020
0x18002cf41  cmp     eax, 4
0x18002cf44  jbe     short loc_18002CF66
0x18002cf46  lea     rax, aLsmServiceStar; "LSM Service Start..."
0x18002cf4d  mov     [rbp+arg_0], rax
0x18002cf51  lea     rax, [rbp+arg_0]
0x18002cf55  mov     [rsp+78h+var_58], rax
0x18002cf5a  lea     rdx, dword_1800C5A7C
0x18002cf61  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002cf66  call    ?DebugBreakIfAskedEx@CUtils@@SAXPEAG0@Z; CUtils::DebugBreakIfAskedEx(ushort *,ushort *)
0x18002cf6b  lea     r12, [rsi+60h]
0x18002cf6f  mov     dword ptr [r12], 20h ; ' '
0x18002cf77  mov     qword ptr [rsi+64h], 2
0x18002cf7f  mov     [rsi+6Ch], r13
0x18002cf83  mov     [rsi+74h], r13d
0x18002cf87  mov     dword ptr [rsi+78h], 0EA60h
0x18002cf8e  mov     r8, rsi; lpContext
0x18002cf91  lea     rdx, ?ServiceCtrlHandler@CService@@KAKKKPEAX0@Z; lpHandlerProc
0x18002cf98  lea     rcx, ?SERVICE_NAME@CService@@2QBGB; "Lsm"
0x18002cf9f  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18002cfa6  nop     dword ptr [rax+rax+00h]
0x18002cfab  mov     [rsi+58h], rax
0x18002cfaf  test    rax, rax
0x18002cfb2  jnz     short loc_18002D031
0x18002cfb4  call    cs:__imp_GetLastError
0x18002cfbb  nop     dword ptr [rax+rax+00h]
0x18002cfc0  mov     ebx, eax
0x18002cfc2  test    eax, eax
0x18002cfc4  jle     short loc_18002CFCF
0x18002cfc6  movzx   ebx, ax
0x18002cfc9  or      ebx, 80070000h
0x18002cfcf  test    ebx, ebx
0x18002cfd1  jns     short loc_18002D031
0x18002cfd3  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "RegisterServiceCtrlHandlerEx")
0x18002cfd6  mov     edx, ebx
0x18002cfd8  xor     ecx, ecx
0x18002cfda  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002cfdf  mov     eax, cs:dword_1800DF020
0x18002cfe5  cmp     eax, 3
0x18002cfe8  jbe     loc_18002DB49
0x18002cfee  lea     rax, aStart; "Start"
0x18002cff5  mov     [rbp+arg_8], rax
0x18002cff9  lea     rax, aRegisterservic_0; "RegisterServiceCtrlHandlerEx"
0x18002d000  mov     [rbp+var_38], rax
0x18002d004  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002d00b  mov     [rbp+var_30], rax
0x18002d00f  lea     rax, [rbp+arg_8]
0x18002d013  mov     [rsp+78h+var_40], rax
0x18002d018  lea     rax, [rbp+arg_0]
0x18002d01c  mov     [rsp+78h+var_48], rax
0x18002d021  lea     rax, [rbp+var_38]
0x18002d025  lea     rdx, qword_1800C5A40
0x18002d02c  jmp     loc_18002DB33
0x18002d031  mov     rcx, rsi; this
0x18002d034  call    ?RegisterGpuStateUpdateNotifications@CService@@IEAAJXZ; CService::RegisterGpuStateUpdateNotifications(void)
0x18002d039  mov     ebx, eax
0x18002d03b  test    eax, eax
0x18002d03d  jns     short loc_18002D0A6
0x18002d03f  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "RegisterGpuStateUpdateNotifications")
0x18002d042  mov     edx, eax
0x18002d044  xor     ecx, ecx
0x18002d046  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002d04b  mov     eax, cs:dword_1800DF020
0x18002d051  cmp     eax, 3
0x18002d054  jbe     loc_18002DB49
0x18002d05a  lea     rax, aStart; "Start"
0x18002d061  mov     [rbp+arg_8], rax
0x18002d065  lea     rax, aRegistergpusta; "RegisterGpuStateUpdateNotifications"
0x18002d06c  mov     [rbp+var_30], rax
0x18002d070  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002d077  mov     [rbp+var_38], rax
0x18002d07b  lea     rax, [rbp+arg_8]
0x18002d07f  mov     [rsp+78h+var_40], rax
0x18002d084  lea     rax, [rbp+arg_0]
0x18002d088  mov     [rsp+78h+var_48], rax
0x18002d08d  lea     rax, [rbp+var_30]
0x18002d091  mov     [rsp+78h+var_50], rax
0x18002d096  lea     rax, [rbp+var_38]
0x18002d09a  lea     rdx, dword_1800C5A04
0x18002d0a1  jmp     loc_18002DB3C
0x18002d0a6  mov     rdx, r12; lpServiceStatus
0x18002d0a9  mov     rcx, [rsi+58h]; hServiceStatus
0x18002d0ad  call    cs:__imp_SetServiceStatus
0x18002d0b4  nop     dword ptr [rax+rax+00h]
0x18002d0b9  call    ?InitializeGlassTerminalWork@CGlassTerminal@@SAJXZ; CGlassTerminal::InitializeGlassTerminalWork(void)
0x18002d0be  mov     ebx, eax
0x18002d0c0  test    eax, eax
0x18002d0c2  jns     short loc_18002D12B
0x18002d0c4  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "CGlassTerminal::InitializeGlassTerminalWork")
0x18002d0c7  mov     edx, eax
0x18002d0c9  xor     ecx, ecx
0x18002d0cb  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002d0d0  mov     eax, cs:dword_1800DF020
0x18002d0d6  cmp     eax, 3
0x18002d0d9  jbe     loc_18002DB49
0x18002d0df  lea     rax, aStart; "Start"
0x18002d0e6  mov     [rbp+arg_8], rax
0x18002d0ea  lea     rax, aCglassterminal_0; "CGlassTerminal::InitializeGlassTerminal"...
0x18002d0f1  mov     [rbp+var_30], rax
0x18002d0f5  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002d0fc  mov     [rbp+var_38], rax
0x18002d100  lea     rax, [rbp+arg_8]
0x18002d104  mov     [rsp+78h+var_40], rax
0x18002d109  lea     rax, [rbp+arg_0]
0x18002d10d  mov     [rsp+78h+var_48], rax
0x18002d112  lea     rax, [rbp+var_30]
0x18002d116  mov     [rsp+78h+var_50], rax
0x18002d11b  lea     rax, [rbp+var_38]
0x18002d11f  lea     rdx, qword_1800C59C8
0x18002d126  jmp     loc_18002DB3C
0x18002d12b  mov     rcx, rsi; struct ISessionManagerInternal **
0x18002d12e  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18002d133  mov     ebx, eax
0x18002d135  test    eax, eax
0x18002d137  jns     short loc_18002D1A0
0x18002d139  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "::GetInstanceOfSessionManager")
0x18002d13c  mov     edx, eax
0x18002d13e  xor     ecx, ecx
0x18002d140  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002d145  mov     eax, cs:dword_1800DF020
0x18002d14b  cmp     eax, 3
0x18002d14e  jbe     loc_18002DB49
0x18002d154  lea     rax, aStart; "Start"
0x18002d15b  mov     [rbp+arg_8], rax
0x18002d15f  lea     rax, aGetinstanceofs_7; "::GetInstanceOfSessionManager"
0x18002d166  mov     [rbp+var_30], rax
0x18002d16a  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002d171  mov     [rbp+var_38], rax
0x18002d175  lea     rax, [rbp+arg_8]
0x18002d179  mov     [rsp+78h+var_40], rax
0x18002d17e  lea     rax, [rbp+arg_0]
0x18002d182  mov     [rsp+78h+var_48], rax
0x18002d187  lea     rax, [rbp+var_30]
0x18002d18b  mov     [rsp+78h+var_50], rax
0x18002d190  lea     rax, [rbp+var_38]
0x18002d194  lea     rdx, dword_1800C598C
0x18002d19b  jmp     loc_18002DB3C
0x18002d1a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d1a7  mov     ecx, 6C0h; unsigned __int64
0x18002d1ac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d1b1  mov     rdi, rax
0x18002d1b4  mov     [rbp+arg_0], rax
0x18002d1b8  test    rax, rax
0x18002d1bb  jz      short loc_18002D1ED
0x18002d1bd  lea     rdx, aCscmnotify; "CSCMNotify"
0x18002d1c4  mov     rcx, rax; this
0x18002d1c7  call    ??0CDefTSNotifySink@@QEAA@PEBD@Z; CDefTSNotifySink::CDefTSNotifySink(char const *)
0x18002d1cc  nop
0x18002d1cd  lea     rax, ??_7CSCMNotify@@6B@; const CSCMNotify::`vftable'
0x18002d1d4  mov     [rdi], rax
0x18002d1d7  mov     [rdi+698h], r13d
0x18002d1de  mov     rcx, rdi; pv
0x18002d1e1  call    ?Initialize@CSCMNotify@@AEAAJXZ; CSCMNotify::Initialize(void)
0x18002d1e6  mov     ebx, eax
0x18002d1e8  mov     r14d, eax
0x18002d1eb  jmp     short loc_18002D1F3
0x18002d1ed  mov     rdi, r13
0x18002d1f0  mov     r14d, ebx
0x18002d1f3  mov     [rbp+arg_18], rdi
0x18002d1f7  test    rdi, rdi
0x18002d1fa  jz      loc_18002DAD9
0x18002d200  mov     rax, [rdi]
0x18002d203  mov     rcx, rdi
0x18002d206  mov     rax, [rax+8]
0x18002d20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d20f  test    r14d, r14d
0x18002d212  js      loc_18002DADE
0x18002d218  mov     rcx, [rsi]
0x18002d21b  mov     rax, [rcx]
0x18002d21e  lea     rdx, [rbp+arg_10]
0x18002d222  mov     rax, [rax+20h]
0x18002d226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d22b  mov     ebx, eax
0x18002d22d  test    eax, eax
0x18002d22f  jns     short loc_18002D298
0x18002d231  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "GetInstanceOfEventDispatcher")
0x18002d234  mov     edx, eax
0x18002d236  xor     ecx, ecx
0x18002d238  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002d23d  mov     eax, cs:dword_1800DF020
0x18002d243  cmp     eax, 3
0x18002d246  jbe     loc_18002DB49
0x18002d24c  lea     rax, aStart; "Start"
0x18002d253  mov     [rbp+arg_8], rax
0x18002d257  lea     rax, aGetinstanceofe_2; "GetInstanceOfEventDispatcher"
0x18002d25e  mov     [rbp+var_30], rax
0x18002d262  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002d269  mov     [rbp+var_38], rax
0x18002d26d  lea     rax, [rbp+arg_8]
0x18002d271  mov     [rsp+78h+var_40], rax
0x18002d276  lea     rax, [rbp+arg_0]
0x18002d27a  mov     [rsp+78h+var_48], rax
0x18002d27f  lea     rax, [rbp+var_30]
0x18002d283  mov     [rsp+78h+var_50], rax
0x18002d288  lea     rax, [rbp+var_38]
0x18002d28c  lea     rdx, dword_1800C5914
0x18002d293  jmp     loc_18002DB3C
0x18002d298  mov     rcx, [rbp+arg_10]
0x18002d29c  mov     rax, [rcx]
0x18002d29f  lea     r8, [rsi+30h]
0x18002d2a3  mov     rdx, rdi
0x18002d2a6  mov     rax, [rax+30h]
0x18002d2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2af  mov     ebx, eax
0x18002d2b1  test    eax, eax
0x18002d2b3  jns     short loc_18002D31C
0x18002d2b5  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "EventDisp->Advise")
0x18002d2b8  mov     edx, eax
0x18002d2ba  xor     ecx, ecx
0x18002d2bc  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002d2c1  mov     eax, cs:dword_1800DF020
0x18002d2c7  cmp     eax, 3
0x18002d2ca  jbe     loc_18002DB49
0x18002d2d0  lea     rax, aStart; "Start"
0x18002d2d7  mov     [rbp+arg_8], rax
0x18002d2db  lea     rax, aEventdispAdvis_0; "EventDisp->Advise"
0x18002d2e2  mov     [rbp+var_30], rax
0x18002d2e6  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002d2ed  mov     [rbp+var_38], rax
0x18002d2f1  lea     rax, [rbp+arg_8]
0x18002d2f5  mov     [rsp+78h+var_40], rax
0x18002d2fa  lea     rax, [rbp+arg_0]
0x18002d2fe  mov     [rsp+78h+var_48], rax
0x18002d303  lea     rax, [rbp+var_30]
0x18002d307  mov     [rsp+78h+var_50], rax
0x18002d30c  lea     rax, [rbp+var_38]
0x18002d310  lea     rdx, qword_1800C58D8
0x18002d317  jmp     loc_18002DB3C
0x18002d31c  lea     rcx, [rsi+20h]; struct IWinlogonNotify **
0x18002d320  call    ?GetInstanceOfWinlogonNotify@IWinlogonNotify@@SAJPEAPEAV1@@Z; IWinlogonNotify::GetInstanceOfWinlogonNotify(IWinlogonNotify * *)
0x18002d325  mov     ebx, eax
0x18002d327  test    eax, eax
0x18002d329  jns     short loc_18002D392
0x18002d32b  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "IWinlogonNotify::GetInstanceOfWinlogonNotify")
0x18002d32e  mov     edx, eax
0x18002d330  xor     ecx, ecx
0x18002d332  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002d337  mov     eax, cs:dword_1800DF020
0x18002d33d  cmp     eax, 3
0x18002d340  jbe     loc_18002DB49
0x18002d346  lea     rax, aStart; "Start"
0x18002d34d  mov     [rbp+arg_8], rax
0x18002d351  lea     rax, aIwinlogonnotif; "IWinlogonNotify::GetInstanceOfWinlogonN"...
0x18002d358  mov     [rbp+var_30], rax
0x18002d35c  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002d363  mov     [rbp+var_38], rax
0x18002d367  lea     rax, [rbp+arg_8]
0x18002d36b  mov     [rsp+78h+var_40], rax
0x18002d370  lea     rax, [rbp+arg_0]
0x18002d374  mov     [rsp+78h+var_48], rax
0x18002d379  lea     rax, [rbp+var_30]
0x18002d37d  mov     [rsp+78h+var_50], rax
0x18002d382  lea     rax, [rbp+var_38]
0x18002d386  lea     rdx, dword_1800C589C
0x18002d38d  jmp     loc_18002DB3C
0x18002d392  lea     r14, [rsi+8]
0x18002d396  mov     rcx, r14; struct IPublicRpc **
0x18002d399  call    ?GetInstanceOfPublicRpc@IPublicRpc@@SAJPEAPEAV1@@Z; IPublicRpc::GetInstanceOfPublicRpc(IPublicRpc * *)
0x18002d39e  mov     ebx, eax
0x18002d3a0  test    eax, eax
0x18002d3a2  jns     short loc_18002D40B
0x18002d3a4  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "IPublicRpc::GetInstanceOfPublicRpc")
0x18002d3a7  mov     edx, eax
0x18002d3a9  xor     ecx, ecx
0x18002d3ab  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002d3b0  mov     eax, cs:dword_1800DF020
0x18002d3b6  cmp     eax, 3
0x18002d3b9  jbe     loc_18002DB49
0x18002d3bf  lea     rax, aStart; "Start"
0x18002d3c6  mov     [rbp+arg_8], rax
0x18002d3ca  lea     rax, aIpublicrpcGeti; "IPublicRpc::GetInstanceOfPublicRpc"
0x18002d3d1  mov     [rbp+var_30], rax
0x18002d3d5  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002d3dc  mov     [rbp+var_38], rax
0x18002d3e0  lea     rax, [rbp+arg_8]
0x18002d3e4  mov     [rsp+78h+var_40], rax
0x18002d3e9  lea     rax, [rbp+arg_0]
0x18002d3ed  mov     [rsp+78h+var_48], rax
0x18002d3f2  lea     rax, [rbp+var_30]
0x18002d3f6  mov     [rsp+78h+var_50], rax
0x18002d3fb  lea     rax, [rbp+var_38]
  ... truncated ...
```
