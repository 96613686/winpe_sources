# CPolicyMonitor::PolicyMonitorWorker(void)

- ea: `0x180051464`
- end: `0x180051ce3`
- name: `?PolicyMonitorWorker@CPolicyMonitor@@AEAAJXZ`
- size: `2175`
- prototype: `__int64 __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800523a0`

## callees

- `0x180001ac0`
- `0x180001b80`
- `0x180001c88`
- `0x180001d24`
- `0x1800074c0`
- `0x180008f64`
- `0x18000a6f0`
- `0x18000f154`
- `0x180014ff0`
- `0x18001dbb0`
- `0x180024ce0`
- `0x180025070`
- `0x180025890`
- `0x1800267c4`
- `0x180026e5c`
- `0x180028c30`
- `0x1800291d8`
- `0x180029808`
- `0x18002c400`
- `0x18002e990`
- `0x18002f288`
- `0x18002f40c`
- `0x18002f624`
- `0x180047744`
- `0x180047e7c`
- `0x18004fb2c`
- `0x1800500dc`
- `0x1800507e4`
- `0x180051464`
- `0x180051e9c`
- `0x1800521d8`
- `0x1800522f0`
- `0x18007b828`
- `0x18007e9dc`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800517c2`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800517c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800517db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800517db`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180051824`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180051824`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180051cb3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180051cb3`

## string_xrefs

- `0x18005153c`: `DelayInitializeCOM`
- `0x180051729`: `SetupServiceStatusChangeCallback failed`
- `0x18005194a`: `SysPrep Setup is in progress, attempting to stop RCM if it was running.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPolicyMonitor::PolicyMonitorWorker(HANDLE *this)
{
  CPolicyMonitor *v2; // rcx
  signed int InstanceOfPublicRpc; // edi
  int v4; // r8d
  int v5; // r9d
  const char *v6; // rax
  __int16 *v7; // rdx
  int v8; // r12d
  int v9; // r13d
  int v10; // edi
  int v11; // r8d
  int v12; // r9d
  CPolicyMonitor *v13; // rcx
  CPolicyMonitor *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  CWPPConfig *v17; // rcx
  CPolicyMonitor *v18; // rcx
  int IsDenyChildSessions; // ebx
  int started; // ebx
  int v21; // r8d
  int v22; // r9d
  struct IPublicRpc *v23; // rbx
  DWORD v24; // r14d
  int v25; // edi
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  unsigned int v29; // esi
  DWORD v30; // eax
  CPolicyMonitor *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  signed int LastError; // eax
  int v35; // r14d
  unsigned int GlassSessionId; // eax
  int v37; // r8d
  int v38; // r9d
  CPolicyMonitor *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  int IsDenyTSConnectionsPolicy; // edi
  CPolicyMonitor *v46; // rcx
  int v47; // eax
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  int v51; // r14d
  CPolicyMonitor *v52; // rcx
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  int v59; // ecx
  int v60; // r8d
  int v61; // r9d
  CWPPConfig *v62; // rcx
  int v64; // [rsp+50h] [rbp-19h] BYREF
  int v65; // [rsp+54h] [rbp-15h] BYREF
  int v66; // [rsp+58h] [rbp-11h] BYREF
  const char *v67; // [rsp+60h] [rbp-9h] BYREF
  struct CGpuManager *v68; // [rsp+68h] [rbp-1h] BYREF
  struct IPublicRpc *v69; // [rsp+70h] [rbp+7h] BYREF
  _QWORD v70[9]; // [rsp+78h] [rbp+Fh] BYREF
  const char *v71; // [rsp+D0h] [rbp+67h] BYREF
  const char *v72; // [rsp+D8h] [rbp+6Fh] BYREF
  const char *v73; // [rsp+E0h] [rbp+77h] BYREF
  struct ISessionManagerInternal *v74; // [rsp+E8h] [rbp+7Fh] BYREF

  v69 = 0;
  InstanceOfPublicRpc = IPublicRpc::GetInstanceOfPublicRpc(&v69);
  if ( InstanceOfPublicRpc < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_104;
    v72 = "PolicyMonitorWorker";
    v6 = "IPublicRpc::GetInstanceOfPublicRpc";
    v7 = word_1800C031A;
    goto LABEL_4;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LSMComInitialization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LSMComInitialization>::GetImpl'::`2'::impl) )
  {
    InstanceOfPublicRpc = CPolicyMonitor::DelayInitializeCOM((CPolicyMonitor *)this);
    if ( InstanceOfPublicRpc < 0 )
    {
      if ( (unsigned int)dword_1800DA020 <= 3 )
        goto LABEL_104;
      v72 = "PolicyMonitorWorker";
      v6 = "DelayInitializeCOM";
      v7 = &word_1800C02D6;
      goto LABEL_4;
    }
  }
  InstanceOfPublicRpc = CPolicyMonitor::TestDelayStartConnectionManager(v2);
  if ( InstanceOfPublicRpc < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_104;
    v72 = "PolicyMonitorWorker";
    v6 = "TestDelayStartConnectionManager";
    v7 = word_1800C0292;
LABEL_4:
    v73 = v6;
    v74 = (struct ISessionManagerInternal *)"Warning HResult failed";
    LODWORD(v71) = InstanceOfPublicRpc;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v2,
      (_DWORD)v7,
      v4,
      v5,
      (__int64)&v74,
      (__int64)&v73,
      (__int64)&v71,
      (__int64)&v72);
    goto LABEL_104;
  }
  LODWORD(v71) = 1;
  LODWORD(v72) = 0;
  v8 = 0;
  v9 = 0;
  v10 = IsVmBusPresent();
  LODWORD(v73) = v10;
  if ( v10 && (unsigned int)dword_1800DA020 > 4 )
  {
    v74 = (struct ISessionManagerInternal *)"Running on a VM... we will start RCM irrespective of the user setting";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      dword_1800DA020,
      (unsigned int)&unk_1800C0268,
      v11,
      v12,
      (__int64)&v74);
  }
  CPolicyMonitor::AllowRCMRegAccess((CPolicyMonitor *)this);
  if ( (unsigned int)CPolicyMonitor::IsSysprepSetupInProgress(v13) )
  {
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v74 = (struct ISessionManagerInternal *)"SysPrep Setup is in progress, not starting RCM yet.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v14,
        (unsigned int)&word_1800C023E,
        v15,
        v16,
        (__int64)&v74);
    }
    CrimsonHelper::RaiseEventInternal(
      (CrimsonHelper *)&CrimsonHelper::s_instance,
      &EVENT_TS_CONNECTION_MANAGER_DISABLED_DUE_TO_SETUP,
      0,
      0);
  }
  else
  {
    IsDenyChildSessions = CPolicyMonitor::IsDenyChildSessions(v14);
    if ( v10 == 1 || !(unsigned int)CPolicyMonitor::IsDenyTSConnectionsPolicy(v18) || !IsDenyChildSessions )
    {
      if ( !IsDenyChildSessions )
        CUtils::EnableChildSessionsCredentialsDelegationPolicy(1);
      started = CPolicyMonitor::StartConnectionManager((CPolicyMonitor *)this, 1, 0x80000000);
      v17 = (CWPPConfig *)(unsigned int)dword_1800DA020;
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v74 = (struct ISessionManagerInternal *)"Starting RCM";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          dword_1800DA020,
          (unsigned int)&dword_1800C0214,
          v21,
          v22,
          (__int64)&v74);
      }
      if ( started < 0 )
      {
        if ( (unsigned int)dword_1800DA020 > 3 )
        {
          LODWORD(v74) = 1;
          v64 = started;
          v68 = (struct CGpuManager *)"StartConnectionManager failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v17,
            (unsigned int)&unk_1800C01D8,
            v21,
            v22,
            (__int64)&v68,
            (__int64)&v64,
            (__int64)&v74);
        }
      }
      else
      {
        LODWORD(v71) = 0;
      }
    }
  }
  CWPPConfig::Refresh(v17);
  v23 = v69;
  while ( 1 )
  {
    while ( 1 )
    {
      v24 = -1;
      v74 = 0;
      ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v74);
      v25 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v74 + 152LL))(v74);
      SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v74);
      if ( v25 < 0 )
      {
        if ( (unsigned int)dword_1800DA020 > 3 )
        {
          LODWORD(v74) = v25;
          v68 = (struct CGpuManager *)"SetupServiceStatusChangeCallback failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1800DA020,
            (unsigned int)byte_1800C01A9,
            v27,
            v28,
            (__int64)&v68,
            (__int64)&v74);
        }
        CrimsonHelper::RaiseEvent<long>(
          &CrimsonHelper::s_instance,
          EVENT_TS_SCM_SERVICESTATUS_CHANGE_FAILED,
          (unsigned int)v25);
        v24 = 600000;
      }
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        v74 = (struct ISessionManagerInternal *)"Waiting for TS Connection policy changes";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v26,
          (unsigned int)&byte_1800C017F,
          v27,
          v28,
          (__int64)&v74);
      }
      this[212] = 0;
      v29 = 0x80000000;
      v30 = WaitForMultipleObjectsEx(8u, this + 204, 0, v24, 1);
      if ( v30 == 192 || v30 == 258 )
        goto LABEL_50;
      if ( v30 != -1 )
      {
        if ( v30 < 0x80 )
        {
          v29 = v30;
LABEL_50:
          v35 = 0;
          InstanceOfPublicRpc = 0;
          goto LABEL_51;
        }
        v35 = -2147418113;
        InstanceOfPublicRpc = -2147418113;
LABEL_46:
        if ( (g_DebugTraceComponent & 0x40) != 0 )
          _DbgPrintMessage(2, "WaitForTSConnectionsPolicyChanges has failed, yielding");
        SwitchToThread();
        goto LABEL_51;
      }
      LastError = GetLastError();
      InstanceOfPublicRpc = LastError;
      if ( LastError > 0 )
        InstanceOfPublicRpc = (unsigned __int16)LastError | 0x80070000;
      v35 = InstanceOfPublicRpc;
      if ( InstanceOfPublicRpc < 0 )
        goto LABEL_46;
LABEL_51:
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v74 = (struct ISessionManagerInternal *)v29;
        v68 = (struct CGpuManager *)"TS Connection policy changed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          (_DWORD)v31,
          (unsigned int)&word_1800C0146,
          v32,
          v33,
          (__int64)&v68,
          (__int64)&v74);
      }
      if ( v35 >= 0 )
        break;
LABEL_61:
      if ( v29 || (GlassSessionId = CPolicyMonitor::GetGlassSessionId(v31), GlassSessionId == (_DWORD)v72) )
      {
        if ( InstanceOfPublicRpc < 0 )
          goto LABEL_101;
        goto LABEL_66;
      }
      LODWORD(v72) = GlassSessionId;
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        v74 = (struct ISessionManagerInternal *)"Glass session id changed, this is noise, ignoring.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v31,
          (unsigned int)word_1800C00F2,
          v37,
          v38,
          (__int64)&v74);
      }
    }
    if ( v29 == 7 )
      break;
    if ( v29 != 0x80000000 && v29 != 6 )
      InstanceOfPublicRpc = CPolicyMonitor::StartWaitOnRegistry((CPolicyMonitor *)this, v29);
    if ( InstanceOfPublicRpc < 0 || v29 != 6 )
      goto LABEL_61;
    v68 = 0;
    v74 = 0;
    ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v74);
    v68 = v74;
    v64 = 0;
    (*(void (__fastcall **)(struct ISessionManagerInternal *, int *, __int64))(*(_QWORD *)v74 + 80LL))(v74, &v64, 1);
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v68);
LABEL_66:
    if ( (unsigned int)CPolicyMonitor::IsSysprepSetupInProgress(v31) )
    {
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v74 = (struct ISessionManagerInternal *)"SysPrep Setup is in progress, attempting to stop RCM if it was running.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v39,
          (unsigned int)&unk_1800C00C8,
          v40,
          v41,
          (__int64)&v74);
      }
      v42 = CPolicyMonitor::StopConnectionManager(v39);
      if ( v42 < 0 )
      {
        if ( (unsigned int)dword_1800DA020 > 3 )
        {
          LODWORD(v74) = v42;
          v68 = (struct CGpuManager *)"this->StopConnectionManager failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v42,
            (unsigned int)&byte_1800C006F,
            v43,
            v44,
            (__int64)&v68,
            (__int64)&v74);
        }
      }
      else
      {
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          v74 = (struct ISessionManagerInternal *)"RCM stopped successfully";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v42,
            (unsigned int)&word_1800C009E,
            v43,
            v44,
            (__int64)&v74);
        }
        CrimsonHelper::RaiseEventInternal(
          (CrimsonHelper *)&CrimsonHelper::s_instance,
          &EVENT_TS_CONNECTION_MANAGER_DISABLED_DUE_TO_SETUP,
          0,
          0);
      }
    }
    else
    {
      v68 = 0;
      IsDenyTSConnectionsPolicy = CPolicyMonitor::IsDenyTSConnectionsPolicy(v39);
      v47 = CPolicyMonitor::IsDenyChildSessions(v46);
      v51 = v47;
      if ( !(_DWORD)v73 && IsDenyTSConnectionsPolicy && v47 )
      {
        v52 = (CPolicyMonitor *)(unsigned int)dword_1800DA020;
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          LODWORD(v74) = v47;
          v65 = IsDenyTSConnectionsPolicy;
          v66 = 0;
          v67 = "Disabling RCM because of policy changes";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            dword_1800DA020,
            (unsigned int)&unk_1800C0018,
            v49,
            v50,
            (__int64)&v67,
            (__int64)&v66,
            (__int64)&v65,
            (__int64)&v74);
        }
        CPolicyMonitor::DisableConnectionManager(v52);
        if ( !v9 || v8 == 1 )
        {
          if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
          {
            LODWORD(v74) = 0;
            v66 = 0;
            v65 = 0;
            LODWORD(v67) = 0;
            v70[0] = 0x2000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v53,
              (unsigned int)&word_1800BFF96,
              v54,
              v55,
              (__int64)v70,
              (__int64)&v67,
              (__int64)&v65,
              (__int64)&v66,
              (__int64)&v74);
          }
          v8 = 0;
          v9 = 1;
        }
      }
      else
      {
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          LODWORD(v74) = (_DWORD)v71;
          v70[0] = "Starting/Refreshing RCM";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v48,
            (unsigned int)&byte_1800BFF5F,
            v49,
            v50,
            (__int64)v70,
            (__int64)&v74);
        }
        FeedbackHubPredownloadScenario();
        v56 = CPolicyMonitor::StartConnectionManager((CPolicyMonitor *)this, (int)v71, v29);
        if ( v56 < 0 )
        {
          if ( (unsigned int)dword_1800DA020 > 3 )
          {
            LODWORD(v74) = v56;
            v70[0] = "Starting/Refreshing RCM failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v56,
              (unsigned int)&unk_1800BFF30,
              v57,
              v58,
              (__int64)v70,
              (__int64)&v74);
          }
        }
        else
        {
          LODWORD(v71) = 0;
        }
        if ( !v9 || !v8 )
        {
          if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
          {
            LODWORD(v74) = v51 == 0;
            LODWORD(v67) = IsDenyTSConnectionsPolicy == 0;
            v66 = (int)v73;
            v70[0] = 0x2000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v59,
              (unsigned int)byte_1800BFEC1,
              v60,
              v61,
              (__int64)v70,
              (__int64)&v66,
              (__int64)&v67,
              (__int64)&v74);
          }
          v8 = 1;
          v9 = 1;
        }
      }
      if ( (int)CGpuManager::GetInstanceOfGpuManager(&v68) >= 0 )
        CGpuManager::EnableDisableHWGpuInSessions(v68);
      SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v68);
    }
LABEL_101:
    (*(void (__fastcall **)(struct IPublicRpc *))(*(_QWORD *)v23 + 40LL))(v23);
    CWPPConfig::Refresh(v62);
  }
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v71 = "Got a shutdown event, breaking out of the loop";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v31,
      (unsigned int)&dword_1800C011C,
      v32,
      v33,
      (__int64)&v71);
  }
LABEL_104:
  if ( *((_DWORD *)this + 432) == 1 )
  {
    CoUninitialize();
    *((_DWORD *)this + 432) = 0;
  }
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v69);
  return (unsigned int)InstanceOfPublicRpc;
}

```

## disassembly

```asm
0x180051464  push    rbp
0x180051466  push    rbx
0x180051467  push    rsi
0x180051468  push    rdi
0x180051469  push    r12
0x18005146b  push    r13
0x18005146d  push    r14
0x18005146f  push    r15
0x180051471  lea     rbp, [rsp-1Fh]
0x180051476  sub     rsp, 88h
0x18005147d  mov     r15, rcx
0x180051480  mov     [rbp+57h+var_50], 0
0x180051488  lea     rcx, [rbp+57h+var_50]; struct IPublicRpc **
0x18005148c  call    ?GetInstanceOfPublicRpc@IPublicRpc@@SAJPEAPEAV1@@Z; IPublicRpc::GetInstanceOfPublicRpc(IPublicRpc * *)
0x180051491  mov     edi, eax
0x180051493  mov     esi, 1
0x180051498  test    eax, eax
0x18005149a  jns     short loc_180051504
0x18005149c  mov     edx, cs:dword_1800DA020
0x1800514a2  cmp     edx, 3
0x1800514a5  jbe     loc_180051CAA
0x1800514ab  lea     rax, aPolicymonitorw; "PolicyMonitorWorker"
0x1800514b2  mov     [rbp+57h+arg_8], rax
0x1800514b6  lea     rax, aIpublicrpcGeti; "IPublicRpc::GetInstanceOfPublicRpc"
0x1800514bd  lea     rdx, word_1800C031A
0x1800514c4  mov     [rbp+57h+arg_10], rax
0x1800514c8  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800514cf  mov     [rbp+57h+arg_18], rax
0x1800514d3  lea     rax, [rbp+57h+arg_8]
0x1800514d7  mov     [rsp+0C0h+var_88], rax
0x1800514dc  lea     rax, [rbp+57h+arg_0]
0x1800514e0  mov     [rsp+0C0h+var_90], rax
0x1800514e5  lea     rax, [rbp+57h+arg_10]
0x1800514e9  mov     [rsp+0C0h+var_98], rax
0x1800514ee  lea     rax, [rbp+57h+arg_18]
0x1800514f2  mov     dword ptr [rbp+57h+arg_0], edi
0x1800514f5  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x1800514fa  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800514ff  jmp     loc_180051CAA
0x180051504  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LSMComInitialization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LSMComInitialization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LSMComInitialization> `wil::Feature<__WilFeatureTraits_Feature_LSMComInitialization>::GetImpl(void)'::`2'::impl
0x18005150b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LSMComInitialization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LSMComInitialization>::__private_IsEnabled(void)
0x180051510  test    al, al
0x180051512  jz      short loc_18005154F
0x180051514  mov     rcx, r15; this
0x180051517  call    ?DelayInitializeCOM@CPolicyMonitor@@AEAAJXZ; CPolicyMonitor::DelayInitializeCOM(void)
0x18005151c  mov     edi, eax
0x18005151e  test    eax, eax
0x180051520  jns     short loc_18005154F
0x180051522  mov     eax, cs:dword_1800DA020
0x180051528  cmp     eax, 3
0x18005152b  jbe     loc_180051CAA
0x180051531  lea     rax, aPolicymonitorw; "PolicyMonitorWorker"
0x180051538  mov     [rbp+57h+arg_8], rax
0x18005153c  lea     rax, aDelayinitializ; "DelayInitializeCOM"
0x180051543  lea     rdx, word_1800C02D6
0x18005154a  jmp     loc_1800514C4
0x18005154f  call    ?TestDelayStartConnectionManager@CPolicyMonitor@@AEAAJXZ; CPolicyMonitor::TestDelayStartConnectionManager(void)
0x180051554  mov     edi, eax
0x180051556  test    eax, eax
0x180051558  jns     short loc_180051587
0x18005155a  mov     eax, cs:dword_1800DA020
0x180051560  cmp     eax, 3
0x180051563  jbe     loc_180051CAA
0x180051569  lea     rax, aPolicymonitorw; "PolicyMonitorWorker"
0x180051570  mov     [rbp+57h+arg_8], rax
0x180051574  lea     rax, aTestdelaystart; "TestDelayStartConnectionManager"
0x18005157b  lea     rdx, word_1800C0292
0x180051582  jmp     loc_1800514C4
0x180051587  mov     dword ptr [rbp+57h+arg_0], esi
0x18005158a  mov     dword ptr [rbp+57h+arg_8], 0
0x180051591  xor     r12d, r12d
0x180051594  xor     r13d, r13d
0x180051597  call    ?IsVmBusPresent@@YAHXZ; IsVmBusPresent(void)
0x18005159c  mov     edi, eax
0x18005159e  mov     dword ptr [rbp+57h+arg_10], eax
0x1800515a1  test    eax, eax
0x1800515a3  jz      short loc_1800515D0
0x1800515a5  mov     ecx, cs:dword_1800DA020
0x1800515ab  cmp     ecx, 4
0x1800515ae  jbe     short loc_1800515D0
0x1800515b0  lea     rax, aRunningOnAVmWe; "Running on a VM... we will start RCM ir"...
0x1800515b7  mov     [rbp+57h+arg_18], rax
0x1800515bb  lea     rax, [rbp+57h+arg_18]
0x1800515bf  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x1800515c4  lea     rdx, unk_1800C0268
0x1800515cb  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800515d0  mov     rcx, r15; this
0x1800515d3  call    ?AllowRCMRegAccess@CPolicyMonitor@@AEAAJXZ; CPolicyMonitor::AllowRCMRegAccess(void)
0x1800515d8  call    ?IsSysprepSetupInProgress@CPolicyMonitor@@AEAAHXZ; CPolicyMonitor::IsSysprepSetupInProgress(void)
0x1800515dd  test    eax, eax
0x1800515df  jz      short loc_18005162A
0x1800515e1  mov     eax, cs:dword_1800DA020
0x1800515e7  cmp     eax, 4
0x1800515ea  jbe     short loc_18005160C
0x1800515ec  lea     rax, aSysprepSetupIs_0; "SysPrep Setup is in progress, not start"...
0x1800515f3  mov     [rbp+57h+arg_18], rax
0x1800515f7  lea     rax, [rbp+57h+arg_18]
0x1800515fb  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x180051600  lea     rdx, word_1800C023E
0x180051607  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005160c  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x18005160f  xor     r8d, r8d; unsigned int
0x180051612  lea     rdx, EVENT_TS_CONNECTION_MANAGER_DISABLED_DUE_TO_SETUP; struct _EVENT_DESCRIPTOR *
0x180051619  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180051620  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180051625  jmp     loc_1800516DB
0x18005162a  call    ?IsDenyChildSessions@CPolicyMonitor@@AEAAHXZ; CPolicyMonitor::IsDenyChildSessions(void)
0x18005162f  mov     ebx, eax
0x180051631  cmp     edi, esi
0x180051633  jz      short loc_180051646
0x180051635  call    ?IsDenyTSConnectionsPolicy@CPolicyMonitor@@AEAAHXZ; CPolicyMonitor::IsDenyTSConnectionsPolicy(void)
0x18005163a  test    eax, eax
0x18005163c  jz      short loc_180051646
0x18005163e  test    ebx, ebx
0x180051640  jnz     loc_1800516DB
0x180051646  test    ebx, ebx
0x180051648  jnz     short loc_180051651
0x18005164a  mov     ecx, esi; int
0x18005164c  call    ?EnableChildSessionsCredentialsDelegationPolicy@CUtils@@SAJH@Z; CUtils::EnableChildSessionsCredentialsDelegationPolicy(int)
0x180051651  mov     r8d, 80000000h; unsigned int
0x180051657  mov     edx, esi; int
0x180051659  mov     rcx, r15; this
0x18005165c  call    ?StartConnectionManager@CPolicyMonitor@@AEAAJHK@Z; CPolicyMonitor::StartConnectionManager(int,ulong)
0x180051661  mov     ebx, eax
0x180051663  mov     ecx, cs:dword_1800DA020
0x180051669  cmp     ecx, 4
0x18005166c  jbe     short loc_18005168E
0x18005166e  lea     rax, aStartingRcm; "Starting RCM"
0x180051675  mov     [rbp+57h+arg_18], rax
0x180051679  lea     rax, [rbp+57h+arg_18]
0x18005167d  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x180051682  lea     rdx, dword_1800C0214
0x180051689  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005168e  test    ebx, ebx
0x180051690  js      short loc_180051698
0x180051692  mov     dword ptr [rbp+57h+arg_0], r12d
0x180051696  jmp     short loc_1800516DB
0x180051698  mov     eax, cs:dword_1800DA020
0x18005169e  cmp     eax, 3
0x1800516a1  jbe     short loc_1800516DB
0x1800516a3  mov     dword ptr [rbp+57h+arg_18], esi
0x1800516a6  mov     [rbp+57h+var_70], ebx
0x1800516a9  lea     rax, aStartconnectio; "StartConnectionManager failed"
0x1800516b0  mov     [rbp+57h+var_58], rax
0x1800516b4  lea     rax, [rbp+57h+arg_18]
0x1800516b8  mov     [rsp+0C0h+var_90], rax
0x1800516bd  lea     rax, [rbp+57h+var_70]
0x1800516c1  mov     [rsp+0C0h+var_98], rax
0x1800516c6  lea     rax, [rbp+57h+var_58]
0x1800516ca  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x1800516cf  lea     rdx, unk_1800C01D8
0x1800516d6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800516db  call    ?Refresh@CWPPConfig@@QEAAJXZ; CWPPConfig::Refresh(void)
0x1800516e0  mov     rbx, [rbp+57h+var_50]
0x1800516e4  or      r14d, 0FFFFFFFFh
0x1800516e8  mov     [rbp+57h+arg_18], 0
0x1800516f0  lea     rcx, [rbp+57h+arg_18]; struct ISessionManagerInternal **
0x1800516f4  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x1800516f9  mov     rcx, [rbp+57h+arg_18]
0x1800516fd  mov     rax, [rcx]
0x180051700  mov     rax, [rax+98h]
0x180051707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005170c  mov     edi, eax
0x18005170e  lea     rcx, [rbp+57h+arg_18]
0x180051712  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180051717  test    edi, edi
0x180051719  jns     short loc_18005176E
0x18005171b  mov     ecx, cs:dword_1800DA020
0x180051721  cmp     ecx, 3
0x180051724  jbe     short loc_180051752
0x180051726  mov     dword ptr [rbp+57h+arg_18], edi
0x180051729  lea     rax, aSetupservicest; "SetupServiceStatusChangeCallback failed"
0x180051730  mov     [rbp+57h+var_58], rax
0x180051734  lea     rax, [rbp+57h+arg_18]
0x180051738  mov     [rsp+0C0h+var_98], rax
0x18005173d  lea     rax, [rbp+57h+var_58]
0x180051741  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x180051746  lea     rdx, byte_1800C01A9
0x18005174d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180051752  mov     r8d, edi
0x180051755  lea     rdx, EVENT_TS_SCM_SERVICESTATUS_CHANGE_FAILED
0x18005175c  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180051763  call    ??$RaiseEvent@J@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@J@Z; CrimsonHelper::RaiseEvent<long>(_EVENT_DESCRIPTOR const &,long)
0x180051768  mov     r14d, 927C0h
0x18005176e  mov     eax, cs:dword_1800DA020
0x180051774  cmp     eax, 5
0x180051777  jbe     short loc_180051799
0x180051779  lea     rax, aWaitingForTsCo; "Waiting for TS Connection policy change"...
0x180051780  mov     [rbp+57h+arg_18], rax
0x180051784  lea     rax, [rbp+57h+arg_18]
0x180051788  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x18005178d  lea     rdx, byte_1800C017F
0x180051794  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180051799  mov     qword ptr [r15+6A0h], 0
0x1800517a4  mov     esi, 80000000h
0x1800517a9  mov     [rsp+0C0h+bAlertable], 1; bAlertable
0x1800517b1  mov     r9d, r14d; dwMilliseconds
0x1800517b4  xor     r8d, r8d; bWaitAll
0x1800517b7  lea     rdx, [r15+660h]; lpHandles
0x1800517be  lea     ecx, [r8+8]; nCount
0x1800517c2  call    cs:__imp_WaitForMultipleObjectsEx
0x1800517c8  cmp     eax, 0C0h
0x1800517cd  jz      short loc_18005182E
0x1800517cf  cmp     eax, 102h
0x1800517d4  jz      short loc_18005182E
0x1800517d6  cmp     eax, 0FFFFFFFFh
0x1800517d9  jnz     short loc_1800517F9
0x1800517db  call    cs:__imp_GetLastError
0x1800517e1  mov     edi, eax
0x1800517e3  test    eax, eax
0x1800517e5  jle     short loc_1800517F0
0x1800517e7  movzx   edi, ax
0x1800517ea  or      edi, 80070000h
0x1800517f0  mov     r14d, edi
0x1800517f3  test    edi, edi
0x1800517f5  jns     short loc_180051833
0x1800517f7  jmp     short loc_18005180A
0x1800517f9  cmp     eax, 80h
0x1800517fe  jb      short loc_18005182C
0x180051800  mov     eax, 8000FFFFh
0x180051805  mov     r14d, eax
0x180051808  mov     edi, eax
0x18005180a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h; ulong g_DebugTraceComponent
0x180051811  jz      short loc_180051824
0x180051813  lea     rdx, aWaitfortsconne; "WaitForTSConnectionsPolicyChanges has f"...
0x18005181a  mov     ecx, 2; int
0x18005181f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180051824  call    cs:__imp_SwitchToThread
0x18005182a  jmp     short loc_180051833
0x18005182c  mov     esi, eax
0x18005182e  xor     r14d, r14d
0x180051831  xor     edi, edi
0x180051833  mov     eax, cs:dword_1800DA020
0x180051839  cmp     eax, 4
0x18005183c  jbe     short loc_18005186D
0x18005183e  mov     eax, esi
0x180051840  mov     [rbp+57h+arg_18], rax
0x180051844  lea     rax, aTsConnectionPo; "TS Connection policy changed"
0x18005184b  mov     [rbp+57h+var_58], rax
0x18005184f  lea     rax, [rbp+57h+arg_18]
0x180051853  mov     [rsp+0C0h+var_98], rax
0x180051858  lea     rax, [rbp+57h+var_58]
0x18005185c  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x180051861  lea     rdx, word_1800C0146
0x180051868  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18005186d  test    r14d, r14d
0x180051870  js      short loc_1800518E5
0x180051872  cmp     esi, 7
0x180051875  jz      loc_180051C7A
0x18005187b  cmp     esi, 80000000h
0x180051881  jz      short loc_180051894
0x180051883  cmp     esi, 6
0x180051886  jz      short loc_180051894
0x180051888  mov     edx, esi; unsigned int
0x18005188a  mov     rcx, r15; this
0x18005188d  call    ?StartWaitOnRegistry@CPolicyMonitor@@AEAAJK@Z; CPolicyMonitor::StartWaitOnRegistry(ulong)
0x180051892  mov     edi, eax
0x180051894  test    edi, edi
0x180051896  js      short loc_1800518E5
0x180051898  cmp     esi, 6
0x18005189b  jnz     short loc_1800518E5
0x18005189d  mov     [rbp+57h+var_58], 0
0x1800518a5  mov     [rbp+57h+arg_18], 0
0x1800518ad  lea     rcx, [rbp+57h+arg_18]; struct ISessionManagerInternal **
0x1800518b1  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x1800518b6  mov     rcx, [rbp+57h+arg_18]
0x1800518ba  mov     [rbp+57h+var_58], rcx
0x1800518be  mov     [rbp+57h+var_70], 0
0x1800518c5  mov     rax, [rcx]
0x1800518c8  lea     r8d, [rsi-5]
0x1800518cc  lea     rdx, [rbp+57h+var_70]
0x1800518d0  mov     rax, [rax+50h]
0x1800518d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800518d9  nop
0x1800518da  lea     rcx, [rbp+57h+var_58]
0x1800518de  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x1800518e3  jmp     short loc_180051932
0x1800518e5  test    esi, esi
0x1800518e7  jnz     short loc_18005192A
0x1800518e9  call    ?GetGlassSessionId@CPolicyMonitor@@AEAAKXZ; CPolicyMonitor::GetGlassSessionId(void)
0x1800518ee  cmp     eax, dword ptr [rbp+57h+arg_8]
0x1800518f1  jz      short loc_18005192A
0x1800518f3  mov     dword ptr [rbp+57h+arg_8], eax
0x1800518f6  mov     eax, cs:dword_1800DA020
0x1800518fc  cmp     eax, 5
0x1800518ff  jbe     loc_1800516E4
0x180051905  lea     rax, aGlassSessionId; "Glass session id changed, this is noise"...
0x18005190c  mov     [rbp+57h+arg_18], rax
0x180051910  lea     rax, [rbp+57h+arg_18]
0x180051914  mov     qword ptr [rsp+0C0h+bAlertable], rax
0x180051919  lea     rdx, word_1800C00F2
0x180051920  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180051925  jmp     loc_1800516E4
0x18005192a  test    edi, edi
0x18005192c  js      loc_180051C61
0x180051932  call    ?IsSysprepSetupInProgress@CPolicyMonitor@@AEAAHXZ; CPolicyMonitor::IsSysprepSetupInProgress(void)
0x180051937  test    eax, eax
0x180051939  jz      loc_1800519F8
0x18005193f  mov     eax, cs:dword_1800DA020
0x180051945  cmp     eax, 4
  ... truncated ...
```
