# CService::Start(void)

- ea: `0x18002ae4c`
- end: `0x18002bb57`
- name: `?Start@CService@@QEAAJXZ`
- size: `3339`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ad50`

## callees

- `0x180001b80`
- `0x1800074c0`
- `0x180008f64`
- `0x18000f154`
- `0x18000f434`
- `0x180014ff0`
- `0x18001dbb0`
- `0x18001deb8`
- `0x18001fd20`
- `0x180025070`
- `0x180025890`
- `0x18002a2c0`
- `0x18002ae4c`
- `0x18002e2f4`
- `0x18002f40c`
- `0x180046404`
- `0x180046660`
- `0x180046dec`
- `0x180047328`
- `0x180047508`
- `0x1800477c4`
- `0x180047d2c`
- `0x18004801c`
- `0x1800480d4`
- `0x180049d1c`
- `0x18004b86c`
- `0x18004fb2c`
- `0x180051f5c`
- `0x1800699cc`
- `0x1800799c4`
- `0x180092b9c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aeff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b012`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aeff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b012`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002b000`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002b000`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18002b735`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18002b735`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002afee`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002ba28`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002afee`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002ba28`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002aeeb`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18002aeeb`

## string_xrefs

- `0x18002ae92`: `LSM Service Start...`
- `0x18002af3a`: `RegisterServiceCtrlHandlerEx`
- `0x18002afa6`: `RegisterGpuStateUpdateNotifications`
- `0x18002b4fa`: `this->CreateRCMReadyEvent failed`
- `0x18002b674`: `TestDelaySetReadyEvent`
- `0x18002b6e9`: `SetTermSrvReadyEvent`
- `0x18002b8f7`: `Console not created by SMSS`
- `0x18002b99d`: `GetInstanceOfPluginMgr() failed`
- `0x18002b9e8`: `ptrPluginMgr->Initialize() failed`
- `0x18002bae1`: `LSM Service Start failed!`

## pseudocode

```c
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
  signed int v16; // eax
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
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v69 = "LSM Service Start...";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v3,
      (unsigned int)&dword_1800C08F4,
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_95;
      v70 = "Start";
      v63 = "RegisterServiceCtrlHandlerEx";
      v64 = "Warning HResult failed";
      v62 = &v70;
      v12 = &v63;
      v13 = (char *)qword_1800C08B8;
      goto LABEL_93;
    }
  }
  updated = CService::RegisterGpuStateUpdateNotifications((CService *)v1);
  v8 = updated;
  if ( updated < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)updated, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "RegisterGpuStateUpdateNotifications";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C087C;
    goto LABEL_94;
  }
  SetServiceStatus((SERVICE_STATUS_HANDLE)v1[11], (LPSERVICE_STATUS)(v1 + 12));
  CGlassTerminal::staticCreateGlassSessionWork = CreateThreadpoolWork(CGlassTerminal::staticCreateGlassSession, 0, 0);
  if ( !CGlassTerminal::staticCreateGlassSessionWork )
  {
    v16 = GetLastError();
    v8 = v16;
    if ( v16 > 0 )
      v8 = (unsigned __int16)v16 | 0x80070000;
    if ( v8 < 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v8, 0);
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_95;
      v70 = "Start";
      v64 = "CGlassTerminal::InitializeGlassTerminalWork";
      v63 = "Warning HResult failed";
      v62 = &v70;
      v61 = &v64;
      v15 = &v63;
      v13 = (char *)qword_1800C0840;
      goto LABEL_94;
    }
  }
  InstanceOfSessionManagerInternal = ISessionManagerInternal::GetInstanceOfSessionManagerInternal(v1);
  v8 = InstanceOfSessionManagerInternal;
  if ( InstanceOfSessionManagerInternal < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfSessionManagerInternal, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "::GetInstanceOfSessionManager";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C0804;
    goto LABEL_94;
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
    goto LABEL_90;
  }
  (*(void (__fastcall **)(CDefTSNotifySink *))(*(_QWORD *)v19 + 8LL))(v19);
  if ( v8 < 0 )
  {
LABEL_90:
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v8, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v48 = "new CSCMNotify";
    v13 = (char *)qword_1800C07C8;
    goto LABEL_92;
  }
  v20 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)*v1 + 32LL))(*v1, &v71);
  v8 = v20;
  if ( v20 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v20, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "GetInstanceOfEventDispatcher";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C078C;
    goto LABEL_94;
  }
  v21 = (*(__int64 (__fastcall **)(__int64, CDefTSNotifySink *, struct ISessionManagerInternal **))(*(_QWORD *)v71 + 48LL))(
          v71,
          v19,
          v1 + 6);
  v8 = v21;
  if ( v21 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v21, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "EventDisp->Advise";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)qword_1800C0750;
    goto LABEL_94;
  }
  InstanceOfWinlogonNotify = IWinlogonNotify::GetInstanceOfWinlogonNotify(v1 + 4);
  v8 = InstanceOfWinlogonNotify;
  if ( InstanceOfWinlogonNotify < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfWinlogonNotify, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "IWinlogonNotify::GetInstanceOfWinlogonNotify";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C0714;
    goto LABEL_94;
  }
  v23 = v1 + 1;
  InstanceOfPublicRpc = IPublicRpc::GetInstanceOfPublicRpc(v1 + 1);
  v8 = InstanceOfPublicRpc;
  if ( InstanceOfPublicRpc < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfPublicRpc, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "IPublicRpc::GetInstanceOfPublicRpc";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)qword_1800C06D8;
    goto LABEL_94;
  }
  InstanceOfPrivateRpc = IPrivateRpc::GetInstanceOfPrivateRpc(v1 + 2);
  v8 = InstanceOfPrivateRpc;
  if ( InstanceOfPrivateRpc < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfPrivateRpc, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "IPrivateRpc::GetInstanceOfPrivateRpc";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C069C;
    goto LABEL_94;
  }
  InstanceOfCsrMgr = ICsrMgr::GetInstanceOfCsrMgr(v1 + 3);
  v8 = InstanceOfCsrMgr;
  if ( InstanceOfCsrMgr < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfCsrMgr, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "ICsrMgr::GetInstanceOfCsrMgr";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)qword_1800C0660;
    goto LABEL_94;
  }
  InstanceOfGpuManager = CGpuManager::GetInstanceOfGpuManager(v1 + 7);
  v8 = InstanceOfGpuManager;
  if ( InstanceOfGpuManager < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)InstanceOfGpuManager, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "CGpuManager::GetInstanceOfGpuManager";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = (char *)&dword_1800C0624;
    goto LABEL_94;
  }
  CGpuManager::EnableDisableHWGpuInSessions(v1[7]);
  RCMReadyEvent = CService::CreateRCMReadyEvent((CService *)v1);
  if ( RCMReadyEvent < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      LODWORD(v69) = RCMReadyEvent;
      v70 = "this->CreateRCMReadyEvent failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DA020,
        (unsigned int)byte_1800C05FD,
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
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "PrivateRpc->Start";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C05C1;
    goto LABEL_94;
  }
  v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 24LL))(*v23);
  v8 = v32;
  if ( v32 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v32, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "PublicRpc->Start";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C0585;
    goto LABEL_94;
  }
  v33 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 40LL))(*v23);
  if ( v33 < 0 )
    _DbgPrintMessage(8, "StartRemote failed with 0x%x", v33);
  ready = CService::TestDelaySetReadyEvent(v34);
  v8 = ready;
  if ( ready < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)ready, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "TestDelaySetReadyEvent";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C0549;
    goto LABEL_94;
  }
  v36 = CService::SetTermSrvReadyEvent((CService *)v1);
  v8 = v36;
  if ( v36 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(0, (unsigned int)v36, 0);
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "SetTermSrvReadyEvent";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C050D;
    goto LABEL_94;
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
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v64 = "WaitForSessionState( Disconnected, SessionZero )";
    v63 = "Warning HResult failed";
    v62 = &v70;
    v61 = &v64;
    v15 = &v63;
    v13 = byte_1800C04D1;
    goto LABEL_94;
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_95;
      v64 = "Start";
      v63 = "GetInitialConsoleSessionId";
      v65 = "Warning HResult failed";
      v62 = &v64;
      v61 = &v63;
      v15 = &v65;
      v13 = byte_1800C0495;
      goto LABEL_94;
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
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_95;
      v65 = "Start";
      v64 = "WaitForSessionState( CsrInitialized, SessionOne )";
      v63 = "Warning HResult failed";
      v62 = &v65;
      v61 = &v64;
      v15 = &v63;
      v13 = byte_1800C0459;
      goto LABEL_94;
    }
  }
  else if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v70 = "Console not created by SMSS";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v41,
      (unsigned int)&byte_1800C0437,
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
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_95;
    v70 = "Start";
    v48 = "CPolicyMonitor";
    v13 = byte_1800C03FB;
LABEL_92:
    v65 = v48;
    v64 = "Warning HResult failed";
    v62 = &v70;
    v12 = &v65;
LABEL_93:
    v61 = v12;
    v15 = &v64;
LABEL_94:
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
    goto LABEL_95;
  }
  InstanceOfPluginMgr = ITSPluginMgr::GetInstanceOfPluginMgr(v1 + 8);
  if ( InstanceOfPluginMgr < 0 && (unsigned int)dword_1800DA020 > 3 )
  {
    LODWORD(v69) = InstanceOfPluginMgr;
    v70 = "GetInstanceOfPluginMgr() failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DA020,
      (unsigned int)byte_1800C03D1,
      v50,
      v51,
      (__int64)&v70,
      (__int64)&v69);
  }
  v52 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v1[8] + 32LL))(v1[8]);
  if ( v52 < 0 )
  {
    v53 = (CService *)(unsigned int)dword_1800DA020;
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      LODWORD(v69) = v52;
      v70 = "ptrPluginMgr->Initialize() failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DA020,
        (unsigned int)&byte_1800C03A7,
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
LABEL_95:
  if ( v8 )
  {
    CrimsonHelper::RaiseEvent<long>(&CrimsonHelper::s_instance, EVENT_LSM_FAILED_TO_START, (unsigned int)v8);
    v59 = (unsigned __int16)v8;
    if ( (v8 & 0x1FFF0000) != 0x70000 )
      v59 = 1359;
    *((_DWORD *)v1 + 27) = v59;
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      LODWORD(v69) = v8;
      v70 = "LSM Service Start failed!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v56,
        (unsigned int)qword_1800C0380,
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
0x18002ae4c  mov     [rsp-40h+arg_0], rcx
0x18002ae51  push    rbp
0x18002ae52  push    rbx
0x18002ae53  push    rsi
0x18002ae54  push    rdi
0x18002ae55  push    r12
0x18002ae57  push    r13
0x18002ae59  push    r14
0x18002ae5b  push    r15
0x18002ae5d  mov     rbp, rsp
0x18002ae60  sub     rsp, 78h
0x18002ae64  mov     rsi, cs:?_pService@@3PEAVCService@@EA; CService * _pService
0x18002ae6b  xor     r13d, r13d
0x18002ae6e  mov     [rbp+var_10], r13
0x18002ae72  mov     [rbp+var_18], r13
0x18002ae76  mov     [rbp+var_20], r13
0x18002ae7a  mov     [rbp+arg_10], r13
0x18002ae7e  mov     [rbp+arg_18], r13
0x18002ae82  call    ?RegisterTraceLoggingProvider@@YAXXZ; RegisterTraceLoggingProvider(void)
0x18002ae87  mov     eax, cs:dword_1800DA020
0x18002ae8d  cmp     eax, 4
0x18002ae90  jbe     short loc_18002AEB2
0x18002ae92  lea     rax, aLsmServiceStar; "LSM Service Start..."
0x18002ae99  mov     [rbp+arg_0], rax
0x18002ae9d  lea     rax, [rbp+arg_0]
0x18002aea1  mov     [rsp+78h+var_58], rax
0x18002aea6  lea     rdx, dword_1800C08F4
0x18002aead  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002aeb2  call    ?DebugBreakIfAskedEx@CUtils@@SAXPEAG0@Z; CUtils::DebugBreakIfAskedEx(ushort *,ushort *)
0x18002aeb7  lea     r12, [rsi+60h]
0x18002aebb  mov     dword ptr [r12], 20h ; ' '
0x18002aec3  mov     qword ptr [rsi+64h], 2
0x18002aecb  mov     [rsi+6Ch], r13
0x18002aecf  mov     [rsi+74h], r13d
0x18002aed3  mov     dword ptr [rsi+78h], 0EA60h
0x18002aeda  mov     r8, rsi; lpContext
0x18002aedd  lea     rdx, ?ServiceCtrlHandler@CService@@KAKKKPEAX0@Z; lpHandlerProc
0x18002aee4  lea     rcx, ?SERVICE_NAME@CService@@2QBGB; "Lsm"
0x18002aeeb  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18002aef1  mov     [rsi+58h], rax
0x18002aef5  mov     edi, 80070000h
0x18002aefa  test    rax, rax
0x18002aefd  jnz     short loc_18002AF72
0x18002aeff  call    cs:__imp_GetLastError
0x18002af05  mov     ebx, eax
0x18002af07  test    eax, eax
0x18002af09  jle     short loc_18002AF10
0x18002af0b  movzx   ebx, ax
0x18002af0e  or      ebx, edi
0x18002af10  test    ebx, ebx
0x18002af12  jns     short loc_18002AF72
0x18002af14  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "RegisterServiceCtrlHandlerEx")
0x18002af17  mov     edx, ebx
0x18002af19  xor     ecx, ecx
0x18002af1b  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002af20  mov     eax, cs:dword_1800DA020
0x18002af26  cmp     eax, 3
0x18002af29  jbe     loc_18002BAA0
0x18002af2f  lea     rax, aStart; "Start"
0x18002af36  mov     [rbp+arg_8], rax
0x18002af3a  lea     rax, aRegisterservic_0; "RegisterServiceCtrlHandlerEx"
0x18002af41  mov     [rbp+var_38], rax
0x18002af45  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002af4c  mov     [rbp+var_30], rax
0x18002af50  lea     rax, [rbp+arg_8]
0x18002af54  mov     [rsp+78h+var_40], rax
0x18002af59  lea     rax, [rbp+arg_0]
0x18002af5d  mov     [rsp+78h+var_48], rax
0x18002af62  lea     rax, [rbp+var_38]
0x18002af66  lea     rdx, qword_1800C08B8
0x18002af6d  jmp     loc_18002BA8A
0x18002af72  mov     rcx, rsi; this
0x18002af75  call    ?RegisterGpuStateUpdateNotifications@CService@@IEAAJXZ; CService::RegisterGpuStateUpdateNotifications(void)
0x18002af7a  mov     ebx, eax
0x18002af7c  test    eax, eax
0x18002af7e  jns     short loc_18002AFE7
0x18002af80  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "RegisterGpuStateUpdateNotifications")
0x18002af83  mov     edx, eax
0x18002af85  xor     ecx, ecx
0x18002af87  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002af8c  mov     eax, cs:dword_1800DA020
0x18002af92  cmp     eax, 3
0x18002af95  jbe     loc_18002BAA0
0x18002af9b  lea     rax, aStart; "Start"
0x18002afa2  mov     [rbp+arg_8], rax
0x18002afa6  lea     rax, aRegistergpusta; "RegisterGpuStateUpdateNotifications"
0x18002afad  mov     [rbp+var_30], rax
0x18002afb1  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002afb8  mov     [rbp+var_38], rax
0x18002afbc  lea     rax, [rbp+arg_8]
0x18002afc0  mov     [rsp+78h+var_40], rax
0x18002afc5  lea     rax, [rbp+arg_0]
0x18002afc9  mov     [rsp+78h+var_48], rax
0x18002afce  lea     rax, [rbp+var_30]
0x18002afd2  mov     [rsp+78h+var_50], rax
0x18002afd7  lea     rax, [rbp+var_38]
0x18002afdb  lea     rdx, dword_1800C087C
0x18002afe2  jmp     loc_18002BA93
0x18002afe7  mov     rdx, r12; lpServiceStatus
0x18002afea  mov     rcx, [rsi+58h]; hServiceStatus
0x18002afee  call    cs:__imp_SetServiceStatus
0x18002aff4  xor     r8d, r8d; pcbe
0x18002aff7  xor     edx, edx; pv
0x18002aff9  lea     rcx, ?staticCreateGlassSession@CGlassTerminal@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002b000  call    cs:__imp_CreateThreadpoolWork
0x18002b006  mov     cs:?staticCreateGlassSessionWork@CGlassTerminal@@0PEAU_TP_WORK@@EA, rax; _TP_WORK * CGlassTerminal::staticCreateGlassSessionWork
0x18002b00d  test    rax, rax
0x18002b010  jnz     short loc_18002B08E
0x18002b012  call    cs:__imp_GetLastError
0x18002b018  mov     ebx, eax
0x18002b01a  test    eax, eax
0x18002b01c  jle     short loc_18002B023
0x18002b01e  movzx   ebx, ax
0x18002b021  or      ebx, edi
0x18002b023  test    ebx, ebx
0x18002b025  jns     short loc_18002B08E
0x18002b027  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "CGlassTerminal::InitializeGlassTerminalWork")
0x18002b02a  mov     edx, ebx
0x18002b02c  xor     ecx, ecx
0x18002b02e  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002b033  mov     eax, cs:dword_1800DA020
0x18002b039  cmp     eax, 3
0x18002b03c  jbe     loc_18002BAA0
0x18002b042  lea     rax, aStart; "Start"
0x18002b049  mov     [rbp+arg_8], rax
0x18002b04d  lea     rax, aCglassterminal_0; "CGlassTerminal::InitializeGlassTerminal"...
0x18002b054  mov     [rbp+var_30], rax
0x18002b058  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002b05f  mov     [rbp+var_38], rax
0x18002b063  lea     rax, [rbp+arg_8]
0x18002b067  mov     [rsp+78h+var_40], rax
0x18002b06c  lea     rax, [rbp+arg_0]
0x18002b070  mov     [rsp+78h+var_48], rax
0x18002b075  lea     rax, [rbp+var_30]
0x18002b079  mov     [rsp+78h+var_50], rax
0x18002b07e  lea     rax, [rbp+var_38]
0x18002b082  lea     rdx, qword_1800C0840
0x18002b089  jmp     loc_18002BA93
0x18002b08e  mov     rcx, rsi; struct ISessionManagerInternal **
0x18002b091  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18002b096  mov     ebx, eax
0x18002b098  test    eax, eax
0x18002b09a  jns     short loc_18002B103
0x18002b09c  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "::GetInstanceOfSessionManager")
0x18002b09f  mov     edx, eax
0x18002b0a1  xor     ecx, ecx
0x18002b0a3  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002b0a8  mov     eax, cs:dword_1800DA020
0x18002b0ae  cmp     eax, 3
0x18002b0b1  jbe     loc_18002BAA0
0x18002b0b7  lea     rax, aStart; "Start"
0x18002b0be  mov     [rbp+arg_8], rax
0x18002b0c2  lea     rax, aGetinstanceofs_7; "::GetInstanceOfSessionManager"
0x18002b0c9  mov     [rbp+var_30], rax
0x18002b0cd  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002b0d4  mov     [rbp+var_38], rax
0x18002b0d8  lea     rax, [rbp+arg_8]
0x18002b0dc  mov     [rsp+78h+var_40], rax
0x18002b0e1  lea     rax, [rbp+arg_0]
0x18002b0e5  mov     [rsp+78h+var_48], rax
0x18002b0ea  lea     rax, [rbp+var_30]
0x18002b0ee  mov     [rsp+78h+var_50], rax
0x18002b0f3  lea     rax, [rbp+var_38]
0x18002b0f7  lea     rdx, dword_1800C0804
0x18002b0fe  jmp     loc_18002BA93
0x18002b103  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b10a  mov     ecx, 6C0h; unsigned __int64
0x18002b10f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002b114  mov     rdi, rax
0x18002b117  mov     [rbp+arg_0], rax
0x18002b11b  test    rax, rax
0x18002b11e  jz      short loc_18002B150
0x18002b120  lea     rdx, aCscmnotify; "CSCMNotify"
0x18002b127  mov     rcx, rax; this
0x18002b12a  call    ??0CDefTSNotifySink@@QEAA@PEBD@Z; CDefTSNotifySink::CDefTSNotifySink(char const *)
0x18002b12f  nop
0x18002b130  lea     rax, ??_7CSCMNotify@@6B@; const CSCMNotify::`vftable'
0x18002b137  mov     [rdi], rax
0x18002b13a  mov     [rdi+698h], r13d
0x18002b141  mov     rcx, rdi; pv
0x18002b144  call    ?Initialize@CSCMNotify@@AEAAJXZ; CSCMNotify::Initialize(void)
0x18002b149  mov     ebx, eax
0x18002b14b  mov     r14d, eax
0x18002b14e  jmp     short loc_18002B156
0x18002b150  mov     rdi, r13
0x18002b153  mov     r14d, ebx
0x18002b156  mov     [rbp+arg_18], rdi
0x18002b15a  test    rdi, rdi
0x18002b15d  jz      loc_18002BA30
0x18002b163  mov     rax, [rdi]
0x18002b166  mov     rcx, rdi
0x18002b169  mov     rax, [rax+8]
0x18002b16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b172  test    r14d, r14d
0x18002b175  js      loc_18002BA35
0x18002b17b  mov     rcx, [rsi]
0x18002b17e  mov     rax, [rcx]
0x18002b181  lea     rdx, [rbp+arg_10]
0x18002b185  mov     rax, [rax+20h]
0x18002b189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b18e  mov     ebx, eax
0x18002b190  test    eax, eax
0x18002b192  jns     short loc_18002B1FB
0x18002b194  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "GetInstanceOfEventDispatcher")
0x18002b197  mov     edx, eax
0x18002b199  xor     ecx, ecx
0x18002b19b  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002b1a0  mov     eax, cs:dword_1800DA020
0x18002b1a6  cmp     eax, 3
0x18002b1a9  jbe     loc_18002BAA0
0x18002b1af  lea     rax, aStart; "Start"
0x18002b1b6  mov     [rbp+arg_8], rax
0x18002b1ba  lea     rax, aGetinstanceofe_2; "GetInstanceOfEventDispatcher"
0x18002b1c1  mov     [rbp+var_30], rax
0x18002b1c5  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002b1cc  mov     [rbp+var_38], rax
0x18002b1d0  lea     rax, [rbp+arg_8]
0x18002b1d4  mov     [rsp+78h+var_40], rax
0x18002b1d9  lea     rax, [rbp+arg_0]
0x18002b1dd  mov     [rsp+78h+var_48], rax
0x18002b1e2  lea     rax, [rbp+var_30]
0x18002b1e6  mov     [rsp+78h+var_50], rax
0x18002b1eb  lea     rax, [rbp+var_38]
0x18002b1ef  lea     rdx, dword_1800C078C
0x18002b1f6  jmp     loc_18002BA93
0x18002b1fb  mov     rcx, [rbp+arg_10]
0x18002b1ff  mov     rax, [rcx]
0x18002b202  lea     r8, [rsi+30h]
0x18002b206  mov     rdx, rdi
0x18002b209  mov     rax, [rax+30h]
0x18002b20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b212  mov     ebx, eax
0x18002b214  test    eax, eax
0x18002b216  jns     short loc_18002B27F
0x18002b218  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "EventDisp->Advise")
0x18002b21b  mov     edx, eax
0x18002b21d  xor     ecx, ecx
0x18002b21f  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002b224  mov     eax, cs:dword_1800DA020
0x18002b22a  cmp     eax, 3
0x18002b22d  jbe     loc_18002BAA0
0x18002b233  lea     rax, aStart; "Start"
0x18002b23a  mov     [rbp+arg_8], rax
0x18002b23e  lea     rax, aEventdispAdvis_0; "EventDisp->Advise"
0x18002b245  mov     [rbp+var_30], rax
0x18002b249  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002b250  mov     [rbp+var_38], rax
0x18002b254  lea     rax, [rbp+arg_8]
0x18002b258  mov     [rsp+78h+var_40], rax
0x18002b25d  lea     rax, [rbp+arg_0]
0x18002b261  mov     [rsp+78h+var_48], rax
0x18002b266  lea     rax, [rbp+var_30]
0x18002b26a  mov     [rsp+78h+var_50], rax
0x18002b26f  lea     rax, [rbp+var_38]
0x18002b273  lea     rdx, qword_1800C0750
0x18002b27a  jmp     loc_18002BA93
0x18002b27f  lea     rcx, [rsi+20h]; struct IWinlogonNotify **
0x18002b283  call    ?GetInstanceOfWinlogonNotify@IWinlogonNotify@@SAJPEAPEAV1@@Z; IWinlogonNotify::GetInstanceOfWinlogonNotify(IWinlogonNotify * *)
0x18002b288  mov     ebx, eax
0x18002b28a  test    eax, eax
0x18002b28c  jns     short loc_18002B2F5
0x18002b28e  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "IWinlogonNotify::GetInstanceOfWinlogonNotify")
0x18002b291  mov     edx, eax
0x18002b293  xor     ecx, ecx
0x18002b295  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002b29a  mov     eax, cs:dword_1800DA020
0x18002b2a0  cmp     eax, 3
0x18002b2a3  jbe     loc_18002BAA0
0x18002b2a9  lea     rax, aStart; "Start"
0x18002b2b0  mov     [rbp+arg_8], rax
0x18002b2b4  lea     rax, aIwinlogonnotif; "IWinlogonNotify::GetInstanceOfWinlogonN"...
0x18002b2bb  mov     [rbp+var_30], rax
0x18002b2bf  lea     rax, aWarningHresult; "Warning HResult failed"
0x18002b2c6  mov     [rbp+var_38], rax
0x18002b2ca  lea     rax, [rbp+arg_8]
0x18002b2ce  mov     [rsp+78h+var_40], rax
0x18002b2d3  lea     rax, [rbp+arg_0]
0x18002b2d7  mov     [rsp+78h+var_48], rax
0x18002b2dc  lea     rax, [rbp+var_30]
0x18002b2e0  mov     [rsp+78h+var_50], rax
0x18002b2e5  lea     rax, [rbp+var_38]
0x18002b2e9  lea     rdx, dword_1800C0714
0x18002b2f0  jmp     loc_18002BA93
0x18002b2f5  lea     r14, [rsi+8]
0x18002b2f9  mov     rcx, r14; struct IPublicRpc **
0x18002b2fc  call    ?GetInstanceOfPublicRpc@IPublicRpc@@SAJPEAPEAV1@@Z; IPublicRpc::GetInstanceOfPublicRpc(IPublicRpc * *)
0x18002b301  mov     ebx, eax
0x18002b303  test    eax, eax
0x18002b305  jns     short loc_18002B36E
0x18002b307  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "IPublicRpc::GetInstanceOfPublicRpc")
0x18002b30a  mov     edx, eax
0x18002b30c  xor     ecx, ecx
0x18002b30e  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002b313  mov     eax, cs:dword_1800DA020
0x18002b319  cmp     eax, 3
0x18002b31c  jbe     loc_18002BAA0
0x18002b322  lea     rax, aStart; "Start"
0x18002b329  mov     [rbp+arg_8], rax
0x18002b32d  lea     rax, aIpublicrpcGeti; "IPublicRpc::GetInstanceOfPublicRpc"
0x18002b334  mov     [rbp+var_30], rax
  ... truncated ...
```
