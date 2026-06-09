# CPolicyMonitor::PolicyMonitorWorker(void)

- ea: `0x180054be4`
- end: `0x180055417`
- name: `?PolicyMonitorWorker@CPolicyMonitor@@AEAAJXZ`
- size: `2099`
- prototype: `__int64 __fastcall(CPolicyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180055b10`

## callees

- `0x180001ad0`
- `0x180001b90`
- `0x180001c98`
- `0x180001d34`
- `0x1800077a0`
- `0x18000c684`
- `0x18000f320`
- `0x1800125d0`
- `0x180012cf8`
- `0x18001f2d0`
- `0x180026c8c`
- `0x18002701c`
- `0x18002772c`
- `0x1800288ac`
- `0x180028f54`
- `0x18002ae68`
- `0x18002b94c`
- `0x18002bb04`
- `0x18002bb90`
- `0x18002e238`
- `0x180030984`
- `0x1800311f4`
- `0x180031448`
- `0x180031650`
- `0x18004a5ac`
- `0x18004b01c`
- `0x1800530d8`
- `0x180053708`
- `0x180053e6c`
- `0x180054be4`
- `0x1800555d4`
- `0x18005592c`
- `0x180055a58`
- `0x1800800ac`
- `0x1800834ec`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180054f4d`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180054f4d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800553e0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800553e0`

## string_xrefs

- `0x180054cc3`: `DelayInitializeCOM`
- `0x180054eaf`: `SetupServiceStatusChangeCallback failed`
- `0x180055073`: `SysPrep Setup is in progress, attempting to stop RCM if it was running.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPolicyMonitor::PolicyMonitorWorker(CPolicyMonitor *this)
{
  int InstanceOfPublicRpc; // edi
  int v3; // r8d
  int v4; // r9d
  CPolicyMonitor *v5; // rcx
  const char *v6; // rax
  __int16 *v7; // rdx
  unsigned int v8; // r14d
  int v9; // r12d
  int v10; // r13d
  int v11; // edi
  int v12; // r8d
  int v13; // r9d
  CPolicyMonitor *v14; // rcx
  CPolicyMonitor *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  CWPPConfig *v18; // rcx
  CPolicyMonitor *v19; // rcx
  int IsDenyChildSessions; // ebx
  int started; // ebx
  int v22; // r8d
  int v23; // r9d
  struct IPublicRpc *v24; // rbx
  unsigned int v25; // esi
  int v26; // edi
  void *v27; // rdx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  CPolicyMonitor *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  unsigned int v34; // esi
  unsigned int GlassSessionId; // eax
  int v36; // r8d
  int v37; // r9d
  CPolicyMonitor *v38; // rcx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  int IsDenyTSConnectionsPolicy; // edi
  CPolicyMonitor *v45; // rcx
  int v46; // eax
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // r14d
  CPolicyMonitor *v51; // rcx
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  int v58; // ecx
  int v59; // r8d
  int v60; // r9d
  CWPPConfig *v61; // rcx
  struct CGpuManager *v63; // [rsp+50h] [rbp-29h] BYREF
  int v64; // [rsp+58h] [rbp-21h] BYREF
  struct ISessionManagerInternal *v65; // [rsp+60h] [rbp-19h] BYREF
  int v66; // [rsp+68h] [rbp-11h] BYREF
  BOOL v67; // [rsp+6Ch] [rbp-Dh] BYREF
  int v68; // [rsp+70h] [rbp-9h] BYREF
  __int64 v69; // [rsp+78h] [rbp-1h] BYREF
  struct IPublicRpc *v70[10]; // [rsp+80h] [rbp+7h] BYREF
  const char *v71; // [rsp+E0h] [rbp+67h] BYREF
  const char *v72; // [rsp+E8h] [rbp+6Fh] BYREF
  const char *v73; // [rsp+F0h] [rbp+77h] BYREF
  const char *v74; // [rsp+F8h] [rbp+7Fh] BYREF

  v70[0] = 0;
  LODWORD(v72) = 0;
  InstanceOfPublicRpc = IPublicRpc::GetInstanceOfPublicRpc(v70);
  if ( InstanceOfPublicRpc < 0 )
  {
    LODWORD(v5) = dword_1800DF020;
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_93;
    v72 = "PolicyMonitorWorker";
    v6 = "IPublicRpc::GetInstanceOfPublicRpc";
    v7 = word_1800C54A2;
    goto LABEL_4;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LSMComInitialization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LSMComInitialization>::GetImpl'::`2'::impl) )
  {
    InstanceOfPublicRpc = CPolicyMonitor::DelayInitializeCOM(this);
    if ( InstanceOfPublicRpc < 0 )
    {
      if ( (unsigned int)dword_1800DF020 <= 3 )
        goto LABEL_93;
      v72 = "PolicyMonitorWorker";
      v6 = "DelayInitializeCOM";
      v7 = &word_1800C545E;
      goto LABEL_4;
    }
  }
  InstanceOfPublicRpc = CPolicyMonitor::TestDelayStartConnectionManager(v5);
  if ( InstanceOfPublicRpc < 0 )
  {
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_93;
    v72 = "PolicyMonitorWorker";
    v6 = "TestDelayStartConnectionManager";
    v7 = word_1800C541A;
LABEL_4:
    v73 = v6;
    v74 = "Warning HResult failed";
    LODWORD(v71) = InstanceOfPublicRpc;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v5,
      (_DWORD)v7,
      v3,
      v4,
      (__int64)&v74,
      (__int64)&v73,
      (__int64)&v71,
      (__int64)&v72);
    goto LABEL_93;
  }
  LODWORD(v71) = 1;
  v8 = 0;
  LODWORD(v74) = 0;
  v9 = 0;
  v10 = 0;
  v11 = IsVmBusPresent();
  LODWORD(v73) = v11;
  if ( v11 && (unsigned int)dword_1800DF020 > 4 )
  {
    v63 = (struct CGpuManager *)"Running on a VM... we will start RCM irrespective of the user setting";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      dword_1800DF020,
      (unsigned int)&unk_1800C53F0,
      v12,
      v13,
      (__int64)&v63);
  }
  CPolicyMonitor::AllowRCMRegAccess(this);
  if ( (unsigned int)CPolicyMonitor::IsSysprepSetupInProgress(v14) )
  {
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v63 = (struct CGpuManager *)"SysPrep Setup is in progress, not starting RCM yet.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v15,
        (unsigned int)&word_1800C53C6,
        v16,
        v17,
        (__int64)&v63);
    }
    CrimsonHelper::RaiseEventInternal(
      (CrimsonHelper *)&CrimsonHelper::s_instance,
      &EVENT_TS_CONNECTION_MANAGER_DISABLED_DUE_TO_SETUP,
      0,
      0);
  }
  else
  {
    IsDenyChildSessions = CPolicyMonitor::IsDenyChildSessions(v15);
    if ( v11 == 1 || !(unsigned int)CPolicyMonitor::IsDenyTSConnectionsPolicy(v19) || !IsDenyChildSessions )
    {
      if ( !IsDenyChildSessions )
        CUtils::EnableChildSessionsCredentialsDelegationPolicy(1);
      started = CPolicyMonitor::StartConnectionManager(this, 1, 0x80000000);
      v18 = (CWPPConfig *)(unsigned int)dword_1800DF020;
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        v63 = (struct CGpuManager *)"Starting RCM";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          dword_1800DF020,
          (unsigned int)&dword_1800C539C,
          v22,
          v23,
          (__int64)&v63);
      }
      if ( started < 0 )
      {
        if ( (unsigned int)dword_1800DF020 > 3 )
        {
          v68 = 1;
          v64 = started;
          v63 = (struct CGpuManager *)"StartConnectionManager failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v18,
            (unsigned int)&unk_1800C5360,
            v22,
            v23,
            (__int64)&v63,
            (__int64)&v64,
            (__int64)&v68);
        }
      }
      else
      {
        LODWORD(v71) = 0;
      }
    }
  }
  CWPPConfig::Refresh(v18);
  v24 = v70[0];
  while ( 1 )
  {
    v25 = -1;
    v65 = 0;
    ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v65);
    v26 = (*(__int64 (__fastcall **)(struct ISessionManagerInternal *))(*(_QWORD *)v65 + 152LL))(v65);
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v65);
    if ( v26 < 0 )
    {
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v64 = v26;
        v63 = (struct CGpuManager *)"SetupServiceStatusChangeCallback failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_1800DF020,
          (unsigned int)byte_1800C5331,
          v29,
          v30,
          (__int64)&v63,
          (__int64)&v64);
      }
      CrimsonHelper::RaiseEvent<long>(
        &CrimsonHelper::s_instance,
        EVENT_TS_SCM_SERVICESTATUS_CHANGE_FAILED,
        (unsigned int)v26);
      v25 = 600000;
    }
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v63 = (struct CGpuManager *)"Waiting for TS Connection policy changes";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v28,
        (unsigned int)&byte_1800C5307,
        v29,
        v30,
        (__int64)&v63);
    }
    InstanceOfPublicRpc = CPolicyMonitor::WaitForTSConnectionsPolicyChanges(this, v27, (unsigned int *)&v72, v25);
    if ( InstanceOfPublicRpc < 0 )
    {
      if ( (g_DebugTraceComponent & 0x40) != 0 )
        _DbgPrintMessage(2, "WaitForTSConnectionsPolicyChanges has failed, yielding");
      SwitchToThread();
    }
    v34 = (unsigned int)v72;
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v63 = (struct CGpuManager *)(unsigned int)v72;
      v65 = (struct ISessionManagerInternal *)"TS Connection policy changed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v31,
        (unsigned int)&word_1800C52CE,
        v32,
        v33,
        (__int64)&v65,
        (__int64)&v63);
    }
    if ( InstanceOfPublicRpc >= 0 )
      break;
LABEL_50:
    if ( v34 || (GlassSessionId = CPolicyMonitor::GetGlassSessionId(v31), GlassSessionId == v8) )
    {
      if ( InstanceOfPublicRpc >= 0 )
      {
        if ( (unsigned int)CPolicyMonitor::IsSysprepSetupInProgress(v31) )
        {
          if ( (unsigned int)dword_1800DF020 > 4 )
          {
            v63 = (struct CGpuManager *)"SysPrep Setup is in progress, attempting to stop RCM if it was running.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (_DWORD)v38,
              (unsigned int)&unk_1800C5250,
              v39,
              v40,
              (__int64)&v63);
          }
          v41 = CPolicyMonitor::StopConnectionManager(v38);
          if ( v41 < 0 )
          {
            if ( (unsigned int)dword_1800DF020 > 3 )
            {
              v64 = v41;
              v63 = (struct CGpuManager *)"this->StopConnectionManager failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v41,
                (unsigned int)&byte_1800C51F7,
                v42,
                v43,
                (__int64)&v63,
                (__int64)&v64);
            }
          }
          else
          {
            if ( (unsigned int)dword_1800DF020 > 4 )
            {
              v63 = (struct CGpuManager *)"RCM stopped successfully";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v41,
                (unsigned int)&word_1800C5226,
                v42,
                v43,
                (__int64)&v63);
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
          v63 = 0;
          IsDenyTSConnectionsPolicy = CPolicyMonitor::IsDenyTSConnectionsPolicy(v38);
          v46 = CPolicyMonitor::IsDenyChildSessions(v45);
          v50 = v46;
          if ( !(_DWORD)v73 && IsDenyTSConnectionsPolicy && v46 )
          {
            v51 = (CPolicyMonitor *)(unsigned int)dword_1800DF020;
            if ( (unsigned int)dword_1800DF020 > 4 )
            {
              v64 = v46;
              v66 = IsDenyTSConnectionsPolicy;
              v67 = 0;
              v65 = (struct ISessionManagerInternal *)"Disabling RCM because of policy changes";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                dword_1800DF020,
                (unsigned int)&unk_1800C51A0,
                v48,
                v49,
                (__int64)&v65,
                (__int64)&v67,
                (__int64)&v66,
                (__int64)&v64);
            }
            CPolicyMonitor::DisableConnectionManager(v51);
            if ( !v10 || v9 == 1 )
            {
              if ( (unsigned int)dword_1800DF020 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
              {
                v67 = 0;
                v66 = 0;
                v64 = 0;
                LODWORD(v65) = 0;
                v69 = 0x2000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v52,
                  (unsigned int)&word_1800C511E,
                  v53,
                  v54,
                  (__int64)&v69,
                  (__int64)&v65,
                  (__int64)&v64,
                  (__int64)&v66,
                  (__int64)&v67);
              }
              v9 = 0;
              v10 = 1;
            }
          }
          else
          {
            if ( (unsigned int)dword_1800DF020 > 4 )
            {
              LODWORD(v65) = (_DWORD)v71;
              v69 = (__int64)"Starting/Refreshing RCM";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v47,
                (unsigned int)&byte_1800C50E7,
                v48,
                v49,
                (__int64)&v69,
                (__int64)&v65);
            }
            FeedbackHubPredownloadScenario();
            v55 = CPolicyMonitor::StartConnectionManager(this, (int)v71, v34);
            if ( v55 < 0 )
            {
              if ( (unsigned int)dword_1800DF020 > 3 )
              {
                LODWORD(v65) = v55;
                v69 = (__int64)"Starting/Refreshing RCM failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v55,
                  (unsigned int)&unk_1800C50B8,
                  v56,
                  v57,
                  (__int64)&v69,
                  (__int64)&v65);
              }
            }
            else
            {
              LODWORD(v71) = 0;
            }
            if ( !v10 || !v9 )
            {
              if ( (unsigned int)dword_1800DF020 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
              {
                LODWORD(v65) = v50 == 0;
                v67 = IsDenyTSConnectionsPolicy == 0;
                v66 = (int)v73;
                v69 = 0x2000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v58,
                  (unsigned int)byte_1800C5049,
                  v59,
                  v60,
                  (__int64)&v69,
                  (__int64)&v66,
                  (__int64)&v67,
                  (__int64)&v65);
              }
              v9 = 1;
              v10 = 1;
            }
          }
          if ( (int)CGpuManager::GetInstanceOfGpuManager(&v63) >= 0 )
            CGpuManager::EnableDisableHWGpuInSessions(v63);
          SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v63);
          v8 = (unsigned int)v74;
        }
      }
      (*(void (__fastcall **)(struct IPublicRpc *))(*(_QWORD *)v24 + 40LL))(v24);
      CWPPConfig::Refresh(v61);
    }
    else
    {
      v8 = GlassSessionId;
      LODWORD(v74) = GlassSessionId;
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        v63 = (struct CGpuManager *)"Glass session id changed, this is noise, ignoring.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v31,
          (unsigned int)word_1800C527A,
          v36,
          v37,
          (__int64)&v63);
      }
    }
  }
  if ( v34 != 7 )
  {
    if ( v34 != 0x80000000 )
    {
      if ( v34 == 6 )
      {
LABEL_49:
        v65 = 0;
        v63 = 0;
        ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v63);
        v65 = v63;
        v68 = 0;
        (*(void (__fastcall **)(struct CGpuManager *, int *, __int64))(*(_QWORD *)v63 + 80LL))(v63, &v68, 1);
        SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v65);
        goto LABEL_50;
      }
      InstanceOfPublicRpc = CPolicyMonitor::StartWaitOnRegistry(this, v34);
      if ( InstanceOfPublicRpc < 0 )
        goto LABEL_50;
    }
    if ( v34 != 6 )
      goto LABEL_50;
    goto LABEL_49;
  }
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v71 = "Got a shutdown event, breaking out of the loop";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v31,
      (unsigned int)&dword_1800C52A4,
      v32,
      v33,
      (__int64)&v71);
  }
LABEL_93:
  if ( *((_DWORD *)this + 432) == 1 )
  {
    CoUninitialize();
    *((_DWORD *)this + 432) = 0;
  }
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(v70);
  return (unsigned int)InstanceOfPublicRpc;
}

```

## disassembly

```asm
0x180054be4  push    rbp
0x180054be6  push    rbx
0x180054be7  push    rsi
0x180054be8  push    rdi
0x180054be9  push    r12
0x180054beb  push    r13
0x180054bed  push    r14
0x180054bef  push    r15
0x180054bf1  lea     rbp, [rsp-1Fh]
0x180054bf6  sub     rsp, 98h
0x180054bfd  mov     r15, rcx
0x180054c00  mov     [rbp+57h+var_50], 0
0x180054c08  mov     dword ptr [rbp+57h+arg_8], 0
0x180054c0f  lea     rcx, [rbp+57h+var_50]; struct IPublicRpc **
0x180054c13  call    ?GetInstanceOfPublicRpc@IPublicRpc@@SAJPEAPEAV1@@Z; IPublicRpc::GetInstanceOfPublicRpc(IPublicRpc * *)
0x180054c18  mov     edi, eax
0x180054c1a  mov     esi, 1
0x180054c1f  test    eax, eax
0x180054c21  jns     short loc_180054C8B
0x180054c23  mov     ecx, cs:dword_1800DF020
0x180054c29  cmp     ecx, 3
0x180054c2c  jbe     loc_1800553D7
0x180054c32  lea     rax, aPolicymonitorw; "PolicyMonitorWorker"
0x180054c39  mov     [rbp+57h+arg_8], rax
0x180054c3d  lea     rax, aIpublicrpcGeti; "IPublicRpc::GetInstanceOfPublicRpc"
0x180054c44  lea     rdx, word_1800C54A2
0x180054c4b  mov     [rbp+57h+arg_10], rax
0x180054c4f  lea     rax, aWarningHresult; "Warning HResult failed"
0x180054c56  mov     [rbp+57h+arg_18], rax
0x180054c5a  lea     rax, [rbp+57h+arg_8]
0x180054c5e  mov     [rsp+0D0h+var_98], rax
0x180054c63  lea     rax, [rbp+57h+arg_0]
0x180054c67  mov     [rsp+0D0h+var_A0], rax
0x180054c6c  lea     rax, [rbp+57h+arg_10]
0x180054c70  mov     [rsp+0D0h+var_A8], rax
0x180054c75  lea     rax, [rbp+57h+arg_18]
0x180054c79  mov     dword ptr [rbp+57h+arg_0], edi
0x180054c7c  mov     [rsp+0D0h+var_B0], rax
0x180054c81  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180054c86  jmp     loc_1800553D7
0x180054c8b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LSMComInitialization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LSMComInitialization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LSMComInitialization> `wil::Feature<__WilFeatureTraits_Feature_LSMComInitialization>::GetImpl(void)'::`2'::impl
0x180054c92  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LSMComInitialization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LSMComInitialization>::__private_IsEnabled(void)
0x180054c97  test    al, al
0x180054c99  jz      short loc_180054CD6
0x180054c9b  mov     rcx, r15; this
0x180054c9e  call    ?DelayInitializeCOM@CPolicyMonitor@@AEAAJXZ; CPolicyMonitor::DelayInitializeCOM(void)
0x180054ca3  mov     edi, eax
0x180054ca5  test    eax, eax
0x180054ca7  jns     short loc_180054CD6
0x180054ca9  mov     eax, cs:dword_1800DF020
0x180054caf  cmp     eax, 3
0x180054cb2  jbe     loc_1800553D7
0x180054cb8  lea     rax, aPolicymonitorw; "PolicyMonitorWorker"
0x180054cbf  mov     [rbp+57h+arg_8], rax
0x180054cc3  lea     rax, aDelayinitializ; "DelayInitializeCOM"
0x180054cca  lea     rdx, word_1800C545E
0x180054cd1  jmp     loc_180054C4B
0x180054cd6  call    ?TestDelayStartConnectionManager@CPolicyMonitor@@AEAAJXZ; CPolicyMonitor::TestDelayStartConnectionManager(void)
0x180054cdb  mov     edi, eax
0x180054cdd  test    eax, eax
0x180054cdf  jns     short loc_180054D0E
0x180054ce1  mov     eax, cs:dword_1800DF020
0x180054ce7  cmp     eax, 3
0x180054cea  jbe     loc_1800553D7
0x180054cf0  lea     rax, aPolicymonitorw; "PolicyMonitorWorker"
0x180054cf7  mov     [rbp+57h+arg_8], rax
0x180054cfb  lea     rax, aTestdelaystart; "TestDelayStartConnectionManager"
0x180054d02  lea     rdx, word_1800C541A
0x180054d09  jmp     loc_180054C4B
0x180054d0e  mov     dword ptr [rbp+57h+arg_0], esi
0x180054d11  xor     r14d, r14d
0x180054d14  mov     dword ptr [rbp+57h+arg_18], r14d
0x180054d18  xor     r12d, r12d
0x180054d1b  xor     r13d, r13d
0x180054d1e  call    ?IsVmBusPresent@@YAHXZ; IsVmBusPresent(void)
0x180054d23  mov     edi, eax
0x180054d25  mov     dword ptr [rbp+57h+arg_10], eax
0x180054d28  test    eax, eax
0x180054d2a  jz      short loc_180054D57
0x180054d2c  mov     ecx, cs:dword_1800DF020
0x180054d32  cmp     ecx, 4
0x180054d35  jbe     short loc_180054D57
0x180054d37  lea     rax, aRunningOnAVmWe; "Running on a VM... we will start RCM ir"...
0x180054d3e  mov     [rbp+57h+var_80], rax
0x180054d42  lea     rax, [rbp+57h+var_80]
0x180054d46  mov     [rsp+0D0h+var_B0], rax
0x180054d4b  lea     rdx, unk_1800C53F0
0x180054d52  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180054d57  mov     rcx, r15; this
0x180054d5a  call    ?AllowRCMRegAccess@CPolicyMonitor@@AEAAJXZ; CPolicyMonitor::AllowRCMRegAccess(void)
0x180054d5f  call    ?IsSysprepSetupInProgress@CPolicyMonitor@@AEAAHXZ; CPolicyMonitor::IsSysprepSetupInProgress(void)
0x180054d64  test    eax, eax
0x180054d66  jz      short loc_180054DB1
0x180054d68  mov     eax, cs:dword_1800DF020
0x180054d6e  cmp     eax, 4
0x180054d71  jbe     short loc_180054D93
0x180054d73  lea     rax, aSysprepSetupIs_0; "SysPrep Setup is in progress, not start"...
0x180054d7a  mov     [rbp+57h+var_80], rax
0x180054d7e  lea     rax, [rbp+57h+var_80]
0x180054d82  mov     [rsp+0D0h+var_B0], rax
0x180054d87  lea     rdx, word_1800C53C6
0x180054d8e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180054d93  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x180054d96  xor     r8d, r8d; unsigned int
0x180054d99  lea     rdx, EVENT_TS_CONNECTION_MANAGER_DISABLED_DUE_TO_SETUP; struct _EVENT_DESCRIPTOR *
0x180054da0  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x180054da7  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x180054dac  jmp     loc_180054E62
0x180054db1  call    ?IsDenyChildSessions@CPolicyMonitor@@AEAAHXZ; CPolicyMonitor::IsDenyChildSessions(void)
0x180054db6  mov     ebx, eax
0x180054db8  cmp     edi, esi
0x180054dba  jz      short loc_180054DCD
0x180054dbc  call    ?IsDenyTSConnectionsPolicy@CPolicyMonitor@@AEAAHXZ; CPolicyMonitor::IsDenyTSConnectionsPolicy(void)
0x180054dc1  test    eax, eax
0x180054dc3  jz      short loc_180054DCD
0x180054dc5  test    ebx, ebx
0x180054dc7  jnz     loc_180054E62
0x180054dcd  test    ebx, ebx
0x180054dcf  jnz     short loc_180054DD8
0x180054dd1  mov     ecx, esi; int
0x180054dd3  call    ?EnableChildSessionsCredentialsDelegationPolicy@CUtils@@SAJH@Z; CUtils::EnableChildSessionsCredentialsDelegationPolicy(int)
0x180054dd8  mov     r8d, 80000000h; unsigned int
0x180054dde  mov     edx, esi; int
0x180054de0  mov     rcx, r15; this
0x180054de3  call    ?StartConnectionManager@CPolicyMonitor@@AEAAJHK@Z; CPolicyMonitor::StartConnectionManager(int,ulong)
0x180054de8  mov     ebx, eax
0x180054dea  mov     ecx, cs:dword_1800DF020
0x180054df0  cmp     ecx, 4
0x180054df3  jbe     short loc_180054E15
0x180054df5  lea     rax, aStartingRcm; "Starting RCM"
0x180054dfc  mov     [rbp+57h+var_80], rax
0x180054e00  lea     rax, [rbp+57h+var_80]
0x180054e04  mov     [rsp+0D0h+var_B0], rax
0x180054e09  lea     rdx, dword_1800C539C
0x180054e10  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180054e15  test    ebx, ebx
0x180054e17  js      short loc_180054E1F
0x180054e19  mov     dword ptr [rbp+57h+arg_0], r12d
0x180054e1d  jmp     short loc_180054E62
0x180054e1f  mov     eax, cs:dword_1800DF020
0x180054e25  cmp     eax, 3
0x180054e28  jbe     short loc_180054E62
0x180054e2a  mov     [rbp+57h+var_60], esi
0x180054e2d  mov     [rbp+57h+var_78], ebx
0x180054e30  lea     rax, aStartconnectio; "StartConnectionManager failed"
0x180054e37  mov     [rbp+57h+var_80], rax
0x180054e3b  lea     rax, [rbp+57h+var_60]
0x180054e3f  mov     [rsp+0D0h+var_A0], rax
0x180054e44  lea     rax, [rbp+57h+var_78]
0x180054e48  mov     [rsp+0D0h+var_A8], rax
0x180054e4d  lea     rax, [rbp+57h+var_80]
0x180054e51  mov     [rsp+0D0h+var_B0], rax
0x180054e56  lea     rdx, unk_1800C5360
0x180054e5d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180054e62  call    ?Refresh@CWPPConfig@@QEAAJXZ; CWPPConfig::Refresh(void)
0x180054e67  mov     rbx, [rbp+57h+var_50]
0x180054e6b  or      esi, 0FFFFFFFFh
0x180054e6e  mov     [rbp+57h+var_70], 0
0x180054e76  lea     rcx, [rbp+57h+var_70]; struct ISessionManagerInternal **
0x180054e7a  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180054e7f  mov     rcx, [rbp+57h+var_70]
0x180054e83  mov     rax, [rcx]
0x180054e86  mov     rax, [rax+98h]
0x180054e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e92  mov     edi, eax
0x180054e94  lea     rcx, [rbp+57h+var_70]
0x180054e98  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180054e9d  test    edi, edi
0x180054e9f  jns     short loc_180054EF3
0x180054ea1  mov     ecx, cs:dword_1800DF020
0x180054ea7  cmp     ecx, 3
0x180054eaa  jbe     short loc_180054ED8
0x180054eac  mov     [rbp+57h+var_78], edi
0x180054eaf  lea     rax, aSetupservicest; "SetupServiceStatusChangeCallback failed"
0x180054eb6  mov     [rbp+57h+var_80], rax
0x180054eba  lea     rax, [rbp+57h+var_78]
0x180054ebe  mov     [rsp+0D0h+var_A8], rax
0x180054ec3  lea     rax, [rbp+57h+var_80]
0x180054ec7  mov     [rsp+0D0h+var_B0], rax
0x180054ecc  lea     rdx, byte_1800C5331
0x180054ed3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180054ed8  mov     r8d, edi
0x180054edb  lea     rdx, EVENT_TS_SCM_SERVICESTATUS_CHANGE_FAILED
0x180054ee2  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180054ee9  call    ??$RaiseEvent@J@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@J@Z; CrimsonHelper::RaiseEvent<long>(_EVENT_DESCRIPTOR const &,long)
0x180054eee  mov     esi, 927C0h
0x180054ef3  mov     eax, cs:dword_1800DF020
0x180054ef9  cmp     eax, 5
0x180054efc  jbe     short loc_180054F1E
0x180054efe  lea     rax, aWaitingForTsCo; "Waiting for TS Connection policy change"...
0x180054f05  mov     [rbp+57h+var_80], rax
0x180054f09  lea     rax, [rbp+57h+var_80]
0x180054f0d  mov     [rsp+0D0h+var_B0], rax
0x180054f12  lea     rdx, byte_1800C5307
0x180054f19  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180054f1e  mov     r9d, esi; unsigned int
0x180054f21  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x180054f25  mov     rcx, r15; this
0x180054f28  call    ?WaitForTSConnectionsPolicyChanges@CPolicyMonitor@@AEAAJPEAXPEAKK@Z; CPolicyMonitor::WaitForTSConnectionsPolicyChanges(void *,ulong *,ulong)
0x180054f2d  mov     edi, eax
0x180054f2f  test    eax, eax
0x180054f31  jns     short loc_180054F59
0x180054f33  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h; ulong g_DebugTraceComponent
0x180054f3a  jz      short loc_180054F4D
0x180054f3c  lea     rdx, aWaitfortsconne; "WaitForTSConnectionsPolicyChanges has f"...
0x180054f43  mov     ecx, 2; int
0x180054f48  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180054f4d  call    cs:__imp_SwitchToThread
0x180054f54  nop     dword ptr [rax+rax+00h]
0x180054f59  mov     eax, cs:dword_1800DF020
0x180054f5f  mov     esi, dword ptr [rbp+57h+arg_8]
0x180054f62  cmp     eax, 4
0x180054f65  jbe     short loc_180054F94
0x180054f67  mov     [rbp+57h+var_80], rsi
0x180054f6b  lea     rax, aTsConnectionPo; "TS Connection policy changed"
0x180054f72  mov     [rbp+57h+var_70], rax
0x180054f76  lea     rax, [rbp+57h+var_80]
0x180054f7a  mov     [rsp+0D0h+var_A8], rax
0x180054f7f  lea     rax, [rbp+57h+var_70]
0x180054f83  mov     [rsp+0D0h+var_B0], rax
0x180054f88  lea     rdx, word_1800C52CE
0x180054f8f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180054f94  test    edi, edi
0x180054f96  js      short loc_18005500B
0x180054f98  cmp     esi, 7
0x180054f9b  jz      loc_1800553A7
0x180054fa1  cmp     esi, 80000000h
0x180054fa7  jz      short loc_180054FBE
0x180054fa9  cmp     esi, 6
0x180054fac  jz      short loc_180054FC3
0x180054fae  mov     edx, esi; unsigned int
0x180054fb0  mov     rcx, r15; this
0x180054fb3  call    ?StartWaitOnRegistry@CPolicyMonitor@@AEAAJK@Z; CPolicyMonitor::StartWaitOnRegistry(ulong)
0x180054fb8  mov     edi, eax
0x180054fba  test    eax, eax
0x180054fbc  js      short loc_18005500B
0x180054fbe  cmp     esi, 6
0x180054fc1  jnz     short loc_18005500B
0x180054fc3  mov     [rbp+57h+var_70], 0
0x180054fcb  mov     [rbp+57h+var_80], 0
0x180054fd3  lea     rcx, [rbp+57h+var_80]; struct ISessionManagerInternal **
0x180054fd7  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180054fdc  mov     rcx, [rbp+57h+var_80]
0x180054fe0  mov     [rbp+57h+var_70], rcx
0x180054fe4  mov     [rbp+57h+var_60], 0
0x180054feb  mov     rax, [rcx]
0x180054fee  mov     r8d, 1
0x180054ff4  lea     rdx, [rbp+57h+var_60]
0x180054ff8  mov     rax, [rax+50h]
0x180054ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055001  nop
0x180055002  lea     rcx, [rbp+57h+var_70]
0x180055006  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18005500b  test    esi, esi
0x18005500d  jnz     short loc_180055053
0x18005500f  call    ?GetGlassSessionId@CPolicyMonitor@@AEAAKXZ; CPolicyMonitor::GetGlassSessionId(void)
0x180055014  cmp     eax, r14d
0x180055017  jz      short loc_180055053
0x180055019  mov     r14d, eax
0x18005501c  mov     dword ptr [rbp+57h+arg_18], eax
0x18005501f  mov     eax, cs:dword_1800DF020
0x180055025  cmp     eax, 5
0x180055028  jbe     loc_180054E6B
0x18005502e  lea     rax, aGlassSessionId; "Glass session id changed, this is noise"...
0x180055035  mov     [rbp+57h+var_80], rax
0x180055039  lea     rax, [rbp+57h+var_80]
0x18005503d  mov     [rsp+0D0h+var_B0], rax
0x180055042  lea     rdx, word_1800C527A
0x180055049  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005504e  jmp     loc_180054E6B
0x180055053  test    edi, edi
0x180055055  js      loc_18005538E
0x18005505b  call    ?IsSysprepSetupInProgress@CPolicyMonitor@@AEAAHXZ; CPolicyMonitor::IsSysprepSetupInProgress(void)
0x180055060  test    eax, eax
0x180055062  jz      loc_180055121
0x180055068  mov     eax, cs:dword_1800DF020
0x18005506e  cmp     eax, 4
0x180055071  jbe     short loc_180055093
0x180055073  lea     rax, aSysprepSetupIs; "SysPrep Setup is in progress, attemptin"...
0x18005507a  mov     [rbp+57h+var_80], rax
0x18005507e  lea     rax, [rbp+57h+var_80]
0x180055082  mov     [rsp+0D0h+var_B0], rax
0x180055087  lea     rdx, unk_1800C5250
0x18005508e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180055093  call    ?StopConnectionManager@CPolicyMonitor@@AEAAJXZ; CPolicyMonitor::StopConnectionManager(void)
0x180055098  mov     ecx, eax
0x18005509a  test    eax, eax
0x18005509c  mov     eax, cs:dword_1800DF020
0x1800550a2  js      short loc_1800550E7
0x1800550a4  cmp     eax, 4
0x1800550a7  jbe     short loc_1800550C9
0x1800550a9  lea     rax, aRcmStoppedSucc; "RCM stopped successfully"
0x1800550b0  mov     [rbp+57h+var_80], rax
0x1800550b4  lea     rax, [rbp+57h+var_80]
0x1800550b8  mov     [rsp+0D0h+var_B0], rax
0x1800550bd  lea     rdx, word_1800C5226
0x1800550c4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800550c9  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x1800550cc  xor     r8d, r8d; unsigned int
0x1800550cf  lea     rdx, EVENT_TS_CONNECTION_MANAGER_DISABLED_DUE_TO_SETUP; struct _EVENT_DESCRIPTOR *
  ... truncated ...
```
