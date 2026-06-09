# CTSSession::ConnectToTerminal(ITerminal *,ulong,int)

- ea: `0x18006731c`
- end: `0x18006803f`
- name: `?ConnectToTerminal@CTSSession@@AEAAJPEAUITerminal@@KH@Z`
- size: `3363`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, struct ITerminal *, unsigned int, int)`
- caller_count: `3`
- callee_count: `49`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180069f40`
- `0x18006cd90`
- `0x18006cfc0`

## callees

- `0x1800019ec`
- `0x1800074c0`
- `0x180008f04`
- `0x180008f64`
- `0x1800092a4`
- `0x1800093d0`
- `0x1800093f8`
- `0x180009420`
- `0x180009810`
- `0x180009a68`
- `0x180009b2c`
- `0x18000a2a4`
- `0x18000a4d0`
- `0x18000a5d0`
- `0x18000aad4`
- `0x18000f154`
- `0x18000fa38`
- `0x180010fb0`
- `0x180018200`
- `0x1800189d4`
- `0x180018c5c`
- `0x180019838`
- `0x180019f28`
- `0x18001ce00`
- `0x18001f064`
- `0x18001fd20`
- `0x180020ea0`
- `0x180024280`
- `0x180024884`
- `0x180024910`
- `0x180024ce0`
- `0x180025600`
- `0x180028784`
- `0x18002a83c`
- `0x18002cc70`
- `0x18002f624`
- `0x180032424`
- `0x1800343e4`
- `0x180034804`
- `0x180034c24`
- `0x18004b460`
- `0x18004bf44`
- `0x1800660e8`
- `0x18006731c`
- `0x18006caec`
- `0x18006eed4`
- `0x18007a9bc`
- `0x18007ad44`
- `0x180097010`

## import_xrefs

- `ntdll!RtlConvertSharedToExclusive` at `0x1800676c4`
- `ntdll!RtlConvertSharedToExclusive` at `0x18006797c`
- `ntdll!RtlConvertSharedToExclusive` at `0x180067aa0`
- `ntdll!RtlConvertSharedToExclusive` at `0x180067b93`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800676c4`
- `ntdll!RtlConvertSharedToExclusive` at `0x18006797c`
- `ntdll!RtlConvertSharedToExclusive` at `0x180067aa0`
- `ntdll!RtlConvertSharedToExclusive` at `0x180067b93`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800675f3`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800678a9`
- `ntdll!RtlConvertExclusiveToShared` at `0x180067a75`
- `ntdll!RtlConvertExclusiveToShared` at `0x180067b08`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800675f3`
- `ntdll!RtlConvertExclusiveToShared` at `0x1800678a9`
- `ntdll!RtlConvertExclusiveToShared` at `0x180067a75`
- `ntdll!RtlConvertExclusiveToShared` at `0x180067b08`
- `ntdll!NtQuerySystemTime` at `0x1800673b5`
- `ntdll!NtQuerySystemTime` at `0x180067c29`
- `ntdll!NtQuerySystemTime` at `0x1800673b5`
- `ntdll!NtQuerySystemTime` at `0x180067c29`
- `ntdll!EtwEventActivityIdControl` at `0x1800673fb`
- `ntdll!EtwEventActivityIdControl` at `0x18006745d`
- `ntdll!EtwEventActivityIdControl` at `0x1800673fb`
- `ntdll!EtwEventActivityIdControl` at `0x18006745d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180067678`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180067678`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067f2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067f2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800678f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180067921`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180067b0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180067b2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800678f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180067921`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180067b0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180067b2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800673c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180067c39`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800673c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180067c39`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180067e1b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180067e1b`

## string_xrefs

- `0x18006774a`: `GetOriginalToken failed: 0x%x in %s`
- `0x180067dfd`: `this->SecurityDescriptor.AddUserAce failed: 0x%x in %s`
- `0x18006799e`: `Skipping SendConnectMsg since it was already sent`
- `0x180067d25`: `ptrTerminal->GetProtocolName failed: 0x%x in %s`
- `0x180067d8b`: `ptrTerminal->GetSecurityDescriptor failed: 0x%x in %s`
- `0x180067dc9`: `SecurityDescriptor.Initialize failed: 0x%x in %s`
- `0x180067f76`: `Reconnect while session is already connected to another terminal`

## pseudocode

```c
__int64 __fastcall CTSSession::ConnectToTerminal(CTSSession *this, struct ITerminal *a2, unsigned int a3, int a4)
{
  int v6; // ecx
  int *v7; // r15
  int v8; // eax
  int InstanceOfGpuManager; // edi
  unsigned int v10; // ebx
  const char *StateName; // rax
  int v12; // ecx
  int v13; // eax
  int CurrentSessionReconnectInfo; // eax
  int v15; // eax
  int v16; // eax
  const char *v17; // rdx
  int v18; // eax
  __int64 (__fastcall *v19)(struct ITerminal *, _BYTE *, struct ITSSession *, _QWORD, DWORD); // rbx
  DWORD CurrentProcessId; // eax
  int v21; // eax
  const char *v22; // rax
  __int64 v23; // rcx
  CGpuManager *v24; // rbx
  int v25; // r8d
  int v26; // r9d
  DWORD v27; // ecx
  int v28; // r14d
  struct ICsrPipe *v29; // rbx
  ULONGLONG TickCount64; // r15
  ULONGLONG v31; // rax
  int v32; // r8d
  int v33; // r9d
  _QWORD *v34; // r14
  CTSSession *v35; // rcx
  ULONGLONG v36; // rbx
  ULONGLONG v37; // rax
  int v38; // r8d
  int v39; // r9d
  __int64 *v40; // rbx
  int v41; // r9d
  __int64 v42; // r8
  struct _LUID v43; // rcx
  char *v44; // rax
  char *v45; // r8
  int v46; // edx
  int v47; // ecx
  void *v48; // r15
  struct IUserName *v49; // rdx
  void *v50; // rbx
  DWORD SecurityDescriptorLength; // eax
  unsigned int v52; // ebx
  unsigned int v53; // edi
  int v54; // eax
  int v55; // eax
  struct _EVENT_DESCRIPTOR *v57; // [rsp+20h] [rbp-E0h]
  unsigned int v58; // [rsp+30h] [rbp-D0h]
  unsigned int v59; // [rsp+30h] [rbp-D0h]
  struct _LUID v60; // [rsp+60h] [rbp-A0h] BYREF
  CGpuManager *v61; // [rsp+68h] [rbp-98h] BYREF
  int v62; // [rsp+70h] [rbp-90h]
  char *v63; // [rsp+78h] [rbp-88h] BYREF
  const char *v64; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v65; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v66; // [rsp+8Ch] [rbp-74h] BYREF
  int v67; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v68[2]; // [rsp+98h] [rbp-68h] BYREF
  PRTL_RESOURCE Resource[2]; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-48h] BYREF
  __int128 *v72; // [rsp+C0h] [rbp-40h] BYREF
  struct ICsrPipe *v73; // [rsp+C8h] [rbp-38h] BYREF
  struct IUserName *v74[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _EVENT_DESCRIPTOR v75; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v76; // [rsp+F0h] [rbp-10h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+F8h] [rbp-8h] BYREF
  struct _GUID v78; // [rsp+100h] [rbp+0h] BYREF
  struct ITSSession *v79[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v80[4]; // [rsp+120h] [rbp+20h]
  __int128 v81; // [rsp+130h] [rbp+30h] BYREF
  __int64 v82; // [rsp+140h] [rbp+40h] BYREF
  __int128 v83; // [rsp+148h] [rbp+48h] BYREF
  __int128 v84; // [rsp+158h] [rbp+58h] BYREF
  _SYSTEMTIME v85; // [rsp+168h] [rbp+68h] BYREF
  __int128 v86; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int16 Parameter[48]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v88[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v89; // [rsp+1F4h] [rbp+F4h]
  int v90; // [rsp+30Ch] [rbp+20Ch]
  int v91; // [rsp+330h] [rbp+230h]
  struct _LUID v92; // [rsp+334h] [rbp+234h]
  _BYTE v93[192]; // [rsp+670h] [rbp+570h] BYREF
  unsigned __int16 v94[40]; // [rsp+730h] [rbp+630h] BYREF

  LODWORD(v63) = a4;
  v68[0] = a3;
  memset_0(v88, 0, 0x480u);
  v76 = 0;
  v66 = 0;
  v62 = 0;
  *(_OWORD *)v79 = 0;
  *(_OWORD *)v80 = 0;
  v81 = 0;
  v82 = 0;
  pv = 0;
  v86 = 0;
  v67 = 0;
  v78 = 0;
  v65 = 0;
  v84 = 0;
  v74[0] = 0;
  SystemTime.QuadPart = 0;
  NtQuerySystemTime(&SystemTime);
  v85 = 0;
  GetSystemTime(&v85);
  v73 = 0;
  (*(void (__fastcall **)(struct ITerminal *, char *))(*(_QWORD *)a2 + 216LL))(a2, (char *)this + 3208);
  v83 = 0;
  EtwEventActivityIdControl(1, &v83);
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v61 = (CGpuManager *)"Related Activity ID was of the previous connection";
    v72 = &v83;
    v60 = (struct _LUID)((char *)this + 3208);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
      v6,
      (unsigned int)word_1800C483A,
      (unsigned int)&v83,
      (_DWORD)this + 3208,
      (__int64)&v60,
      (__int64)&v72,
      (__int64)&v61);
  }
  EtwEventActivityIdControl(2, (char *)this + 3208);
  CTSSessionTrace::CTSSessionTrace((CTSSessionTrace *)v93, "CTSSession::ConnectToTerminal", this);
  LODWORD(v72) = *((_DWORD *)this + 806);
  memset_0(v88, 0, 0x480u);
  *(_OWORD *)v79 = 0;
  *(_OWORD *)v80 = 0;
  v81 = 0;
  v82 = 0;
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)Resource, (CTSSession *)((char *)this + 1856));
  v7 = (int *)((char *)this + 3256);
  v8 = CTSSession::CState::CheckState((char *)this + 3256, 3);
  InstanceOfGpuManager = v8;
  v10 = *((_DWORD *)this + 814);
  if ( v8 < 0 )
  {
    StateName = (const char *)CUtils::GetStateName(v10);
    _DbgPrintMessage(8, "invalid state for EvConnected, state is: \"%s\"", StateName);
    goto LABEL_96;
  }
  if ( v8 == 1 )
  {
    v12 = *((_DWORD *)this + 814);
    goto LABEL_7;
  }
  v13 = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)v79);
  InstanceOfGpuManager = v13;
  if ( v13 < 0 )
  {
    _DbgPrintMessage(8, "InitializeNotifyInfo failed: 0x%x in %s", (unsigned int)v13, "CTSSession::ConnectToTerminal");
    goto LABEL_96;
  }
  CurrentSessionReconnectInfo = CTSSession::getCurrentSessionReconnectInfo(
                                  this,
                                  (enum __MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0003 *)&v67,
                                  &v78);
  InstanceOfGpuManager = CurrentSessionReconnectInfo;
  if ( CurrentSessionReconnectInfo < 0 )
  {
    _DbgPrintMessage(
      8,
      "getCurrentSessionReconnectInfo failed: 0x%x in %s",
      (unsigned int)CurrentSessionReconnectInfo,
      "CTSSession::ConnectToTerminal");
    goto LABEL_96;
  }
  v15 = (*(__int64 (__fastcall **)(struct ITerminal *, __int128 *, char *, unsigned int *, __int128 *))(*(_QWORD *)a2 + 136LL))(
          a2,
          &v86,
          (char *)this + 3224,
          &v65,
          &v84);
  InstanceOfGpuManager = v15;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(8, "GetTerminalType failed: 0x%x in %s", (unsigned int)v15, "CTSSession::ConnectToTerminal");
    goto LABEL_96;
  }
  v16 = CTSSession::CSessionReconnectController::TryApplyTerminalToSession((char *)this + 5848, v65, &v84);
  InstanceOfGpuManager = v16;
  if ( v16 < 0 )
  {
    v17 = "SessionReconnectController.TryApplyTerminalToSession failed: 0x%x in %s";
LABEL_94:
    _DbgPrintMessage(8, v17, (unsigned int)v16, "CTSSession::ConnectToTerminal");
    goto LABEL_95;
  }
  RtlConvertExclusiveToShared(Resource[0]);
  v18 = (*(__int64 (__fastcall **)(__int64, struct ITSSession **, _QWORD, struct ITerminal *))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL)
                                                                                             + 32LL))(
          *((_QWORD *)this + 228) + 1832LL,
          v79,
          v10,
          a2);
  if ( v18 < 0 )
    _DbgPrintMessage(4, "EventDispatch->OnCsrInitialized failed: 0x%x", v18);
  v75 = (struct _EVENT_DESCRIPTOR)EVENT_TERMINAL_DOCONNECT_TOOLONG;
  CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(
    Parameter,
    (struct _GUID *)((char *)this + 3208),
    *((_DWORD *)this + 436),
    this,
    &v75,
    "pNewTerminal->DoConnect",
    v58);
  v19 = *(__int64 (__fastcall **)(struct ITerminal *, _BYTE *, struct ITSSession *, _QWORD, DWORD))(*(_QWORD *)a2 + 32LL);
  CurrentProcessId = GetCurrentProcessId();
  InstanceOfGpuManager = v19(a2, v88, v79[0], *((_QWORD *)this + 808), CurrentProcessId);
  CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
  if ( InstanceOfGpuManager < 0 )
  {
    _DbgPrintMessage(
      8,
      "DoConnectMsg failed: 0x%x in %s",
      (unsigned int)InstanceOfGpuManager,
      "CTSSession::ConnectToTerminal");
LABEL_95:
    *((_DWORD *)this + 1462) = v67;
    *(struct _GUID *)((char *)this + 5852) = v78;
    *((_DWORD *)this + 806) = (_DWORD)v72;
    goto LABEL_96;
  }
  RtlConvertSharedToExclusive(Resource[0]);
  CTSSession::AuditEvent(this, 0x12AAu, a2);
  v21 = CTSSession::CState::CheckState((char *)this + 3256, 3);
  InstanceOfGpuManager = v21;
  if ( v21 < 0 )
  {
    v22 = (const char *)CUtils::GetStateName((unsigned int)*v7);
    _DbgPrintMessage(8, "invalid state for EvConnected, state is: \"%s\"", v22);
    goto LABEL_95;
  }
  if ( v21 == 1 )
  {
    v12 = *v7;
LABEL_7:
    GetLsmStateName(v12);
    GetLsmEventName(3);
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "No change to session %d state %ws with event %ws", *((unsigned int *)this + 436));
    goto LABEL_96;
  }
  v23 = *((_QWORD *)this + 741);
  if ( v23 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v23 + 88LL))(v23, &v76, &v66);
    InstanceOfGpuManager = v16;
    if ( v16 < 0 )
    {
      v17 = "GetOriginalToken failed: 0x%x in %s";
      goto LABEL_94;
    }
  }
  if ( v90 == 1 )
  {
    v61 = 0;
    InstanceOfGpuManager = CGpuManager::GetInstanceOfGpuManager(&v61);
    if ( InstanceOfGpuManager >= 0 )
    {
      v24 = v61;
      if ( *((_DWORD *)v61 + 400) )
      {
        v60 = 0;
        InstanceOfGpuManager = CGpuManager::VerifyGpuAssignment(v61, this);
        if ( InstanceOfGpuManager >= 0 )
        {
          v92 = *(struct _LUID *)(*((_QWORD *)this + 231) + 1904LL);
        }
        else
        {
          InstanceOfGpuManager = CGpuManager::LoadBalanceSessionToGpu(v24, this, &v60);
          if ( InstanceOfGpuManager < 0 )
          {
            v27 = *((_DWORD *)this + 436);
            if ( (unsigned int)dword_1800DA020 > 5 )
            {
              LODWORD(v71) = InstanceOfGpuManager;
              v60.LowPart = v27;
              v64 = "GPU assignment to session failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v27,
                (unsigned int)&byte_1800C4807,
                v25,
                v26,
                (__int64)&v64,
                (__int64)&v60,
                (__int64)&v71);
            }
            goto LABEL_39;
          }
          v92 = v60;
        }
        v91 = 1;
      }
    }
LABEL_39:
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v61);
  }
  SmartPtr<ICsrPipe>::operator=(&v73);
  v28 = *((_DWORD *)this + 430);
  v29 = v73;
  if ( v28 == 1 )
  {
    _DbgPrintMessage(1, "Skipping SendConnectMsg since it was already sent");
  }
  else
  {
    *((_DWORD *)this + 430) = 1;
    v75 = (struct _EVENT_DESCRIPTOR)EVENT_SENDCSR_CONNECTMSG;
    CTSSendCSRMsgMonitor::CTSSendCSRMsgMonitor(
      Parameter,
      (struct _GUID *)((char *)this + 3208),
      *((_DWORD *)this + 436),
      this,
      &v75,
      "Connect",
      v59);
    RtlConvertExclusiveToShared(Resource[0]);
    if ( (unsigned int)(v89 - 1) > 0xF || HIDWORD(v89) >= (unsigned int)v89 )
    {
      if ( (g_DebugTraceComponent & 4) != 0 )
        _DbgPrintMessage(
          2,
          "Terminal return invalid monitors data, number of monitor %d, primary monitor %d, reset to default",
          v89,
          HIDWORD(v89));
      v89 = 1;
    }
    TickCount64 = GetTickCount64();
    InstanceOfGpuManager = (*(__int64 (__fastcall **)(struct ICsrPipe *, _BYTE *, __int64, _QWORD, _DWORD))(*(_QWORD *)v29 + 88LL))(
                             v29,
                             v88,
                             v76,
                             v66,
                             (_DWORD)v63);
    v31 = GetTickCount64();
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v64 = (const char *)(v31 - TickCount64);
      LODWORD(v63) = *((_DWORD *)this + 436);
      v61 = (CGpuManager *)"SendConnectMsg took this long";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        dword_1800DA020,
        (unsigned int)&byte_1800C47A7,
        v32,
        v33,
        (__int64)&v61,
        (__int64)&v63,
        (__int64)&v64);
    }
    RtlConvertSharedToExclusive(Resource[0]);
    if ( InstanceOfGpuManager < 0 )
      *((_DWORD *)this + 430) = v28;
    CTSSendCSRMsgMonitor::~CTSSendCSRMsgMonitor((CTSSendCSRMsgMonitor *)Parameter);
  }
  if ( InstanceOfGpuManager == -2147024865 )
    InstanceOfGpuManager = -2147017826;
  if ( InstanceOfGpuManager < 0 )
  {
    StringCchPrintfW(Parameter, 0x28u, L"connect (%d)", *((unsigned int *)this + 436));
    CrimsonHelper::RaiseEvent<unsigned short *,long>(
      &CrimsonHelper::s_instance,
      EVENT_LSM_CSRSS_MESSAGESEND_FAILED,
      Parameter,
      (unsigned int)InstanceOfGpuManager);
    _DbgPrintMessage(
      8,
      "SendConnectMsg failed: 0x%x in %s",
      (unsigned int)InstanceOfGpuManager,
      "CTSSession::ConnectToTerminal");
    goto LABEL_95;
  }
  v34 = (_QWORD *)((char *)this + 1816);
  SmartPtr<ITerminal>::operator=((char *)this + 1816, a2);
  if ( *((_QWORD *)this + 227) )
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 227) + 216LL))(
      *((_QWORD *)this + 227),
      (char *)this + 3208);
  v62 = 1;
  v16 = (*(__int64 (__fastcall **)(_QWORD, CTSSession *))(*(_QWORD *)*v34 + 56LL))(*v34, this);
  InstanceOfGpuManager = v16;
  if ( v16 < 0 )
  {
    v17 = "Terminal->Connected failed: 0x%x in %s";
    goto LABEL_94;
  }
  SmartPtr<IUserName>::operator=(v74, *((_QWORD *)this + 741));
  RtlConvertExclusiveToShared(Resource[0]);
  v16 = CTSSession::SetTimeZoneInternalNoLock(v35, v29, a2, v74[0]);
  InstanceOfGpuManager = v16;
  if ( v16 < 0 )
  {
    v17 = "SetTimeZoneInternalNoLock failed: 0x%x in %s";
    goto LABEL_94;
  }
  RtlConvertSharedToExclusive(Resource[0]);
  if ( *((_QWORD *)this + 741) )
  {
    v60 = 0;
    v75 = (struct _EVENT_DESCRIPTOR)EVENT_TERMINAL_LOGON_TOOLONG;
    CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(
      Parameter,
      (struct _GUID *)((char *)this + 3208),
      *((_DWORD *)this + 436),
      this,
      &v75,
      "pNewTerminal->LoggedOn",
      v59);
    SmartPtr<IUserName>::operator=(&v60, *((_QWORD *)this + 741));
    RtlConvertExclusiveToShared(Resource[0]);
    v36 = GetTickCount64();
    InstanceOfGpuManager = (*(__int64 (__fastcall **)(struct ITerminal *, struct _LUID))(*(_QWORD *)a2 + 64LL))(a2, v60);
    v37 = GetTickCount64();
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v64 = (const char *)(v37 - v36);
      LODWORD(v63) = *((_DWORD *)this + 436);
      v61 = (CGpuManager *)"pNewTerminal->LoggedOnStarted() took this long";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        dword_1800DA020,
        (unsigned int)&byte_1800C474F,
        v38,
        v39,
        (__int64)&v61,
        (__int64)&v63,
        (__int64)&v64);
    }
    *((_DWORD *)this + 527) = 1;
    RtlConvertSharedToExclusive(Resource[0]);
    if ( InstanceOfGpuManager < 0 )
    {
      _DbgPrintMessage(
        8,
        "Terminal->LoggedOn failed: 0x%x in %s",
        InstanceOfGpuManager,
        "CTSSession::ConnectToTerminal");
      CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
      SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v60);
      goto LABEL_95;
    }
    CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v60);
  }
  if ( !*v34 )
  {
    InstanceOfGpuManager = -2147022646;
    _DbgPrintMessage(8, "NULL == this->ptrTerminal failed: 0x%x in %s", 2147944650LL, "CTSSession::ConnectToTerminal");
    goto LABEL_95;
  }
  *((_DWORD *)this + 518) = *((_DWORD *)this + 528);
  CTSSession::WinLogonSendMessage(this, v68[0], 0);
  v40 = (__int64 *)((char *)this + 1976);
  NtQuerySystemTime((PLARGE_INTEGER)this + 247);
  GetSystemTime((LPSYSTEMTIME)this + 126);
  if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
  {
    v64 = (char *)this + 3208;
    v42 = *v40;
    v43 = (struct _LUID)(*v40 - SystemTime.QuadPart);
    v61 = (CGpuManager *)(*(__int64 *)&v43 / 10000000);
    *(_QWORD *)v68 = &v85;
    v63 = (char *)this + 2016;
    v60 = v43;
    v71 = v42;
    *(_QWORD *)&v75.Id = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
      v43.LowPart,
      (unsigned int)word_1800C46C2,
      v42,
      v41,
      (__int64)&v75,
      (__int64)&v71,
      (__int64)&v60,
      (__int64)&v63,
      (__int64)v68,
      (__int64)&v61,
      (__int64)&v64);
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(*(_QWORD *)*v34 + 96LL))(*v34, v94);
  InstanceOfGpuManager = v16;
  if ( v16 < 0 )
  {
    v17 = "ptrTerminal->GetProtocolName failed: 0x%x in %s";
    goto LABEL_94;
  }
  v44 = (char *)*((_QWORD *)this + 740);
  if ( !v44 )
    goto LABEL_80;
  v45 = (char *)((char *)v94 - v44);
  do
  {
    v46 = *(unsigned __int16 *)&v45[(_QWORD)v44];
    v47 = *(unsigned __int16 *)v44 - v46;
    if ( v47 )
      break;
    v44 += 2;
  }
  while ( v46 );
  if ( v47 )
  {
LABEL_80:
    v68[0] = 0;
    v16 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, unsigned int *))(*(_QWORD *)*v34 + 200LL))(*v34, &pv, v68);
    InstanceOfGpuManager = v16;
    if ( v16 < 0 )
    {
      v17 = "ptrTerminal->GetSecurityDescriptor failed: 0x%x in %s";
      goto LABEL_94;
    }
    v48 = CTSSessionSecurityDescriptor::DetachSD((CTSSession *)((char *)this + 5872));
    InstanceOfGpuManager = CTSSessionSecurityDescriptor::Initialize((CTSSession *)((char *)this + 5872), v94, pv);
    if ( InstanceOfGpuManager < 0 )
    {
      CTSSessionSecurityDescriptor::AttachSD((CTSSession *)((char *)this + 5872), v48);
      _DbgPrintMessage(
        8,
        "SecurityDescriptor.Initialize failed: 0x%x in %s",
        (unsigned int)InstanceOfGpuManager,
        "CTSSession::ConnectToTerminal");
      goto LABEL_95;
    }
    v49 = (struct IUserName *)*((_QWORD *)this + 741);
    if ( v49 )
    {
      InstanceOfGpuManager = CTSSessionSecurityDescriptor::AddUserAce((CTSSession *)((char *)this + 5872), v49);
      if ( InstanceOfGpuManager < 0 )
      {
        CTSSessionSecurityDescriptor::AttachSD((CTSSession *)((char *)this + 5872), v48);
        _DbgPrintMessage(
          8,
          "this->SecurityDescriptor.AddUserAce failed: 0x%x in %s",
          (unsigned int)InstanceOfGpuManager,
          "CTSSession::ConnectToTerminal");
        goto LABEL_95;
      }
    }
    CUtils::CleanupSD(v48);
  }
  v50 = (void *)*((_QWORD *)this + 739);
  SecurityDescriptorLength = GetSecurityDescriptorLength(v50);
  (*(void (__fastcall **)(_QWORD, void *, _QWORD))(*(_QWORD *)*v34 + 192LL))(*v34, v50, SecurityDescriptorLength);
  v52 = *((_DWORD *)this + 814);
  LODWORD(v57) = 3953;
  CTSSession::CState::ChangeState((char *)this + 3256, 3, (char *)&v81 + 8, &v82, v57);
  v53 = *((_DWORD *)this + 814);
  CAutoLock::Unlock((CAutoLock *)Resource);
  v54 = CTSSession::SendSessionNotificationMsg(this, 1);
  if ( v54 < 0 )
    _DbgPrintMessage(8, "SendSessionNotificationMsg failed: 0x%x", v54);
  if ( (_QWORD)v81 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81 + 16LL))(v81);
  *(_QWORD *)&v81 = a2;
  (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)a2 + 8LL))(a2);
  v16 = (*(__int64 (__fastcall **)(__int64, struct ITSSession **, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 228)
                                                                                             + 1832LL)
                                                                                 + 40LL))(
          *((_QWORD *)this + 228) + 1832LL,
          v79,
          v53,
          v52);
  InstanceOfGpuManager = v16;
  if ( v16 < 0 )
  {
    v17 = "EventDispatch->OnConnected failed: 0x%x in %s";
    goto LABEL_94;
  }
LABEL_96:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( InstanceOfGpuManager < 0 )
  {
    if ( v62 )
    {
      CAutoLock::Unlock((CAutoLock *)Resource);
      CTSSession::DisconnectSession(this, 0, 0x202u, 0);
    }
    goto LABEL_104;
  }
  v55 = IsConsole(v79[0]);
  CTSSession::PublishWNFNotification(this, v55 != 0 ? 1 : 3, v80[2]);
  CTSSession::LogSessionEvent(this, &EVENT_SESSION_RECONNECT, a2);
  if ( InstanceOfGpuManager == 1 && !v62 )
  {
    _DbgPrintMessage(8, "Reconnect while session is already connected to another terminal");
    InstanceOfGpuManager = -2147019873;
LABEL_104:
    CTSSession::LogFailedTransition(this, 3, (unsigned int)InstanceOfGpuManager);
  }
  if ( v79[0] )
  {
    (*(void (__fastcall **)(struct ITSSession *))(*(_QWORD *)v79[0] + 16LL))(v79[0]);
    v79[0] = 0;
  }
  if ( (_QWORD)v81 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81 + 16LL))(v81);
    *(_QWORD *)&v81 = 0;
  }
  CAutoLock::Unlock((CAutoLock *)Resource);
  CTSSessionTrace::~CTSSessionTrace((CTSSessionTrace *)v93);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v73);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(v74);
  return (unsigned int)InstanceOfGpuManager;
}

```

## disassembly

```asm
0x18006731c  push    rbp
0x18006731e  push    rbx
0x18006731f  push    rsi
0x180067320  push    rdi
0x180067321  push    r12
0x180067323  push    r13
0x180067325  push    r14
0x180067327  push    r15
0x180067329  lea     rbp, [rsp-698h]
0x180067331  sub     rsp, 798h
0x180067338  mov     rax, cs:__security_cookie
0x18006733f  xor     rax, rsp
0x180067342  mov     [rbp+6D0h+var_50], rax
0x180067349  mov     dword ptr [rsp+7D0h+var_758], r9d
0x18006734e  mov     [rbp+6D0h+var_738], r8d
0x180067352  mov     r12, rdx
0x180067355  mov     rsi, rcx
0x180067358  mov     edi, 480h
0x18006735d  mov     r8d, edi; Size
0x180067360  xor     edx, edx; Val
0x180067362  lea     rcx, [rbp+6D0h+var_5E0]; void *
0x180067369  call    memset_0
0x18006736e  xor     ebx, ebx
0x180067370  mov     [rbp+6D0h+var_6E0], rbx
0x180067374  mov     [rbp+6D0h+var_744], ebx
0x180067377  mov     [rsp+7D0h+var_760], ebx
0x18006737b  xorps   xmm0, xmm0
0x18006737e  xor     eax, eax
0x180067380  movups  xmmword ptr [rbp+6D0h+var_6C0], xmm0
0x180067384  movups  xmmword ptr [rbp+6D0h+var_6B0], xmm0
0x180067388  movups  [rbp+6D0h+var_6A0], xmm0
0x18006738c  mov     [rbp+6D0h+var_690], rax
0x180067390  mov     [rbp+6D0h+pv], rbx
0x180067394  movups  [rbp+6D0h+var_658], xmm0
0x180067398  mov     [rbp+6D0h+var_740], ebx
0x18006739b  xorps   xmm1, xmm1
0x18006739e  movups  xmmword ptr [rbp+6D0h+var_6D0.Data1], xmm1
0x1800673a2  mov     [rbp+6D0h+var_748], ebx
0x1800673a5  movups  [rbp+6D0h+var_678], xmm0
0x1800673a9  mov     [rbp+6D0h+var_700], rbx
0x1800673ad  mov     qword ptr [rbp+6D0h+SystemTime], rbx
0x1800673b1  lea     rcx, [rbp+6D0h+SystemTime]; SystemTime
0x1800673b5  call    cs:__imp_NtQuerySystemTime
0x1800673bb  xorps   xmm0, xmm0
0x1800673be  movups  xmmword ptr [rbp+6D0h+var_668.wYear], xmm0
0x1800673c2  lea     rcx, [rbp+6D0h+var_668]; lpSystemTime
0x1800673c6  call    cs:__imp_GetSystemTime
0x1800673cc  mov     [rbp+6D0h+var_708], rbx
0x1800673d0  lea     r13, [rsi+0C88h]
0x1800673d7  mov     rax, [r12]
0x1800673db  mov     rdx, r13
0x1800673de  mov     rcx, r12
0x1800673e1  mov     rax, [rax+0D8h]
0x1800673e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800673ed  xorps   xmm0, xmm0
0x1800673f0  movups  [rbp+6D0h+var_688], xmm0
0x1800673f4  lea     rdx, [rbp+6D0h+var_688]
0x1800673f8  lea     ecx, [rbx+1]
0x1800673fb  call    cs:__imp_EtwEventActivityIdControl
0x180067401  mov     eax, cs:dword_1800DA020
0x180067407  cmp     eax, 5
0x18006740a  jbe     short loc_180067455
0x18006740c  lea     rax, aRelatedActivit; "Related Activity ID was of the previous"...
0x180067413  mov     [rsp+7D0h+var_768], rax
0x180067418  lea     rax, [rbp+6D0h+var_688]
0x18006741c  mov     [rbp+6D0h+var_710], rax
0x180067420  mov     qword ptr [rsp+7D0h+var_770.LowPart], r13
0x180067425  lea     rax, [rsp+7D0h+var_768]
0x18006742a  mov     qword ptr [rsp+7D0h+var_7A0], rax; unsigned int
0x18006742f  lea     rax, [rbp+6D0h+var_710]
0x180067433  mov     [rsp+7D0h+var_7A8], rax
0x180067438  lea     rax, [rsp+7D0h+var_770]
0x18006743d  mov     [rsp+7D0h+var_7B0], rax
0x180067442  mov     r9, r13
0x180067445  lea     r8, [rbp+6D0h+var_688]
0x180067449  lea     rdx, word_1800C483A
0x180067450  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x180067455  mov     rdx, r13
0x180067458  mov     ecx, 2
0x18006745d  call    cs:__imp_EtwEventActivityIdControl
0x180067463  mov     r8, rsi; struct ITSSession *
0x180067466  lea     rdx, aCtssessionConn_3; "CTSSession::ConnectToTerminal"
0x18006746d  lea     rcx, [rbp+6D0h+var_160]; this
0x180067474  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x180067479  nop
0x18006747a  lea     r14, [rsi+0C98h]
0x180067481  mov     eax, [r14]
0x180067484  mov     dword ptr [rbp+6D0h+var_710], eax
0x180067487  mov     r8, rdi; Size
0x18006748a  xor     edx, edx; Val
0x18006748c  lea     rcx, [rbp+6D0h+var_5E0]; void *
0x180067493  call    memset_0
0x180067498  xorps   xmm0, xmm0
0x18006749b  xor     eax, eax
0x18006749d  movups  xmmword ptr [rbp+6D0h+var_6C0], xmm0
0x1800674a1  movups  xmmword ptr [rbp+6D0h+var_6B0], xmm0
0x1800674a5  movups  [rbp+6D0h+var_6A0], xmm0
0x1800674a9  mov     [rbp+6D0h+var_690], rax
0x1800674ad  lea     rdx, [rsi+740h]; struct CResource *
0x1800674b4  lea     rcx, [rbp+6D0h+Resource]; this
0x1800674b8  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800674bd  nop
0x1800674be  lea     r15, [rsi+0CB8h]
0x1800674c5  mov     edx, 3
0x1800674ca  mov     rcx, r15
0x1800674cd  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x1800674d2  mov     edi, eax
0x1800674d4  mov     ebx, [r15]
0x1800674d7  test    eax, eax
0x1800674d9  jns     short loc_1800674FB
0x1800674db  mov     ecx, ebx
0x1800674dd  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x1800674e2  mov     r8, rax
0x1800674e5  lea     rdx, aInvalidStateFo_0; "invalid state for EvConnected, state is"...
0x1800674ec  mov     ecx, 8; int
0x1800674f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800674f6  jmp     loc_180067F21
0x1800674fb  cmp     eax, 1
0x1800674fe  jnz     short loc_180067543
0x180067500  mov     ecx, ebx; int
0x180067502  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x180067507  mov     r9, rax
0x18006750a  mov     ecx, 3; int
0x18006750f  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x180067514  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006751b  jz      loc_180067F21
0x180067521  mov     [rsp+7D0h+var_7B0], rax
0x180067526  mov     r8d, [rsi+6D0h]
0x18006752d  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x180067534  mov     ecx, 2; int
0x180067539  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006753e  jmp     loc_180067F21
0x180067543  lea     rdx, [rbp+6D0h+var_6C0]; struct __PTSSessInfo *
0x180067547  mov     rcx, rsi; this
0x18006754a  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x18006754f  mov     edi, eax
0x180067551  test    eax, eax
0x180067553  jns     short loc_180067575
0x180067555  lea     rdx, aInitializenoti_0; "InitializeNotifyInfo failed: 0x%x in %s"
0x18006755c  lea     r9, aCtssessionConn_3; "CTSSession::ConnectToTerminal"
0x180067563  mov     r8d, eax
0x180067566  mov     ecx, 8; int
0x18006756b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180067570  jmp     loc_180067F21
0x180067575  lea     r8, [rbp+6D0h+var_6D0]; struct _GUID *
0x180067579  lea     rdx, [rbp+6D0h+var_740]; enum __MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0003 *
0x18006757d  mov     rcx, rsi; this
0x180067580  call    ?getCurrentSessionReconnectInfo@CTSSession@@UEAAJPEAW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0003@@PEAU_GUID@@@Z; CTSSession::getCurrentSessionReconnectInfo(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0003 *,_GUID *)
0x180067585  mov     edi, eax
0x180067587  test    eax, eax
0x180067589  jns     short loc_180067594
0x18006758b  lea     rdx, aGetcurrentsess; "getCurrentSessionReconnectInfo failed: "...
0x180067592  jmp     short loc_18006755C
0x180067594  mov     rax, [r12]
0x180067598  lea     rcx, [rbp+6D0h+var_678]
0x18006759c  mov     [rsp+7D0h+var_7B0], rcx
0x1800675a1  lea     r9, [rbp+6D0h+var_748]
0x1800675a5  mov     r8, r14
0x1800675a8  lea     rdx, [rbp+6D0h+var_658]
0x1800675ac  mov     rcx, r12
0x1800675af  mov     rax, [rax+88h]
0x1800675b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675bb  mov     edi, eax
0x1800675bd  test    eax, eax
0x1800675bf  jns     short loc_1800675CA
0x1800675c1  lea     rdx, aGetterminaltyp; "GetTerminalType failed: 0x%x in %s"
0x1800675c8  jmp     short loc_18006755C
0x1800675ca  lea     rcx, [rsi+16D8h]
0x1800675d1  lea     r8, [rbp+6D0h+var_678]
0x1800675d5  mov     edx, [rbp+6D0h+var_748]
0x1800675d8  call    ?TryApplyTerminalToSession@CSessionReconnectController@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004@@AEAU_GUID@@@Z; CTSSession::CSessionReconnectController::TryApplyTerminalToSession(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004,_GUID &)
0x1800675dd  mov     edi, eax
0x1800675df  test    eax, eax
0x1800675e1  jns     short loc_1800675EF
0x1800675e3  lea     rdx, aSessionreconne_0; "SessionReconnectController.TryApplyTerm"...
0x1800675ea  jmp     loc_180067EEF
0x1800675ef  mov     rcx, [rbp+6D0h+Resource]; Resource
0x1800675f3  call    cs:__imp_RtlConvertExclusiveToShared
0x1800675f9  mov     rcx, [rsi+720h]
0x180067600  add     rcx, 728h
0x180067607  mov     rax, [rcx]
0x18006760a  mov     r9, r12
0x18006760d  mov     r8d, ebx
0x180067610  lea     rdx, [rbp+6D0h+var_6C0]
0x180067614  mov     rax, [rax+20h]
0x180067618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006761d  test    eax, eax
0x18006761f  jns     short loc_180067635
0x180067621  mov     r8d, eax
0x180067624  lea     rdx, aEventdispatchO_4; "EventDispatch->OnCsrInitialized failed:"...
0x18006762b  mov     ecx, 4; int
0x180067630  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180067635  movups  xmm0, cs:EVENT_TERMINAL_DOCONNECT_TOOLONG
0x18006763c  movdqu  xmmword ptr [rbp+6D0h+var_6F0.Id], xmm0
0x180067641  lea     rax, aPnewterminalDo; "pNewTerminal->DoConnect"
0x180067648  mov     [rsp+7D0h+var_7A8], rax; char *
0x18006764d  lea     rax, [rbp+6D0h+var_6F0]
0x180067651  mov     [rsp+7D0h+var_7B0], rax; struct _EVENT_DESCRIPTOR
0x180067656  mov     r9, rsi; struct ITSSession *
0x180067659  mov     r8d, [rsi+6D0h]; int
0x180067660  mov     rdx, r13; struct _GUID *
0x180067663  lea     rcx, [rbp+6D0h+Parameter]; Parameter
0x18006766a  call    ??0CTSTerminalOpsMonitor@@QEAA@PEAU_GUID@@JPEAUITSSession@@U_EVENT_DESCRIPTOR@@PEBDK@Z; CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(_GUID *,long,ITSSession *,_EVENT_DESCRIPTOR,char const *,ulong)
0x18006766f  nop
0x180067670  mov     rax, [r12]
0x180067674  mov     rbx, [rax+20h]
0x180067678  call    cs:__imp_GetCurrentProcessId
0x18006767e  mov     dword ptr [rsp+7D0h+var_7B0], eax
0x180067682  mov     r9, [rsi+1940h]
0x180067689  mov     r8, [rbp+6D0h+var_6C0]
0x18006768d  lea     rdx, [rbp+6D0h+var_5E0]
0x180067694  mov     rcx, r12
0x180067697  mov     rax, rbx
0x18006769a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006769f  mov     edi, eax
0x1800676a1  lea     rcx, [rbp+6D0h+Parameter]; this
0x1800676a8  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x1800676ad  test    edi, edi
0x1800676af  jns     short loc_1800676C0
0x1800676b1  mov     r8d, edi
0x1800676b4  lea     rdx, aDoconnectmsgFa; "DoConnectMsg failed: 0x%x in %s"
0x1800676bb  jmp     loc_180067EF2
0x1800676c0  mov     rcx, [rbp+6D0h+Resource]; Resource
0x1800676c4  call    cs:__imp_RtlConvertSharedToExclusive
0x1800676ca  mov     r8, r12; struct ITerminal *
0x1800676cd  mov     edx, 12AAh; unsigned int
0x1800676d2  mov     rcx, rsi; this
0x1800676d5  call    ?AuditEvent@CTSSession@@AEAAJKPEAUITerminal@@@Z; CTSSession::AuditEvent(ulong,ITerminal *)
0x1800676da  mov     edx, 3
0x1800676df  mov     rcx, r15
0x1800676e2  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x1800676e7  mov     edi, eax
0x1800676e9  test    eax, eax
0x1800676eb  jns     short loc_18006770E
0x1800676ed  mov     ecx, [r15]
0x1800676f0  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x1800676f5  mov     r8, rax
0x1800676f8  lea     rdx, aInvalidStateFo_0; "invalid state for EvConnected, state is"...
0x1800676ff  mov     ecx, 8; int
0x180067704  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180067709  jmp     loc_180067F03
0x18006770e  mov     r14d, 1
0x180067714  cmp     eax, r14d
0x180067717  jnz     short loc_180067721
0x180067719  mov     ecx, [r15]
0x18006771c  jmp     loc_180067502
0x180067721  mov     rcx, [rsi+1728h]
0x180067728  xor     r15d, r15d
0x18006772b  test    rcx, rcx
0x18006772e  jz      short loc_180067756
0x180067730  mov     rax, [rcx]
0x180067733  lea     r8, [rbp+6D0h+var_744]
0x180067737  lea     rdx, [rbp+6D0h+var_6E0]
0x18006773b  mov     rax, [rax+58h]
0x18006773f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067744  mov     edi, eax
0x180067746  test    eax, eax
0x180067748  jns     short loc_180067756
0x18006774a  lea     rdx, aGetoriginaltok; "GetOriginalToken failed: 0x%x in %s"
0x180067751  jmp     loc_180067EEF
0x180067756  cmp     [rbp+6D0h+var_4C4], r14d
0x18006775d  jnz     loc_18006783B
0x180067763  mov     [rsp+7D0h+var_768], r15
0x180067768  lea     rcx, [rsp+7D0h+var_768]; struct CGpuManager **
0x18006776d  call    ?GetInstanceOfGpuManager@CGpuManager@@SAJPEAPEAV1@@Z; CGpuManager::GetInstanceOfGpuManager(CGpuManager * *)
0x180067772  mov     edi, eax
0x180067774  test    eax, eax
0x180067776  js      loc_180067831
0x18006777c  mov     rbx, [rsp+7D0h+var_768]
0x180067781  cmp     [rbx+640h], r15d
0x180067788  jz      loc_180067831
0x18006778e  mov     qword ptr [rsp+7D0h+var_770.LowPart], r15
0x180067793  mov     rdx, rsi; struct ITSSessionPrivate *
0x180067796  mov     rcx, rbx; this
0x180067799  call    ?VerifyGpuAssignment@CGpuManager@@QEAAJPEAVITSSessionPrivate@@@Z; CGpuManager::VerifyGpuAssignment(ITSSessionPrivate *)
0x18006779e  mov     edi, eax
0x1800677a0  test    eax, eax
0x1800677a2  jns     short loc_180067815
0x1800677a4  lea     r8, [rsp+7D0h+var_770]; struct _LUID *
0x1800677a9  mov     rdx, rsi; struct ITSSessionPrivate *
0x1800677ac  mov     rcx, rbx; this
0x1800677af  call    ?LoadBalanceSessionToGpu@CGpuManager@@QEAAJPEAVITSSessionPrivate@@PEAU_LUID@@@Z; CGpuManager::LoadBalanceSessionToGpu(ITSSessionPrivate *,_LUID *)
0x1800677b4  mov     edi, eax
0x1800677b6  test    eax, eax
0x1800677b8  js      short loc_1800677C8
0x1800677ba  mov     rax, qword ptr [rsp+7D0h+var_770.LowPart]
0x1800677bf  mov     [rbp+6D0h+var_49C], rax
0x1800677c6  jmp     short loc_18006782A
0x1800677c8  mov     ecx, [rsi+6D0h]
0x1800677ce  mov     eax, cs:dword_1800DA020
0x1800677d4  cmp     eax, 5
0x1800677d7  jbe     short loc_180067831
0x1800677d9  mov     dword ptr [rbp+6D0h+var_718], edi
0x1800677dc  mov     [rsp+7D0h+var_770.LowPart], ecx
0x1800677e0  lea     rax, aGpuAssignmentT; "GPU assignment to session failed"
0x1800677e7  mov     [rbp+6D0h+var_750], rax
0x1800677eb  lea     rax, [rbp+6D0h+var_718]
0x1800677ef  mov     qword ptr [rsp+7D0h+var_7A0], rax
0x1800677f4  lea     rax, [rsp+7D0h+var_770]
0x1800677f9  mov     [rsp+7D0h+var_7A8], rax
  ... truncated ...
```
