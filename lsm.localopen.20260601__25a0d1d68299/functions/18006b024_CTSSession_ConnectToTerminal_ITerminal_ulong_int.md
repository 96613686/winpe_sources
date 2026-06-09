# CTSSession::ConnectToTerminal(ITerminal *,ulong,int)

- ea: `0x18006b024`
- end: `0x18006bdc6`
- name: `?ConnectToTerminal@CTSSession@@AEAAJPEAUITerminal@@KH@Z`
- size: `3490`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, struct ITerminal *, unsigned int, int)`
- caller_count: `3`
- callee_count: `49`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006dd70`
- `0x180070c70`
- `0x180070ea0`

## callees

- `0x1800019f8`
- `0x1800077a0`
- `0x1800095f8`
- `0x1800098b4`
- `0x18000a5e0`
- `0x18000acec`
- `0x18000c17c`
- `0x18000c684`
- `0x180010ef8`
- `0x1800115a8`
- `0x1800118f4`
- `0x180011a28`
- `0x180011a50`
- `0x180011a78`
- `0x180011e6c`
- `0x1800120d0`
- `0x180012194`
- `0x1800123b0`
- `0x1800124b4`
- `0x18001266c`
- `0x1800129d0`
- `0x180012cf8`
- `0x180013658`
- `0x180014b20`
- `0x180021464`
- `0x180022030`
- `0x1800232c0`
- `0x1800260b0`
- `0x1800266bc`
- `0x180026748`
- `0x180026c8c`
- `0x180027610`
- `0x180029f3c`
- `0x18002c878`
- `0x18002ea90`
- `0x180031650`
- `0x180034508`
- `0x18003654c`
- `0x180036980`
- `0x180036da4`
- `0x18004e850`
- `0x18004f354`
- `0x180069da8`
- `0x18006b024`
- `0x1800709ac`
- `0x180072e84`
- `0x18007f1c4`
- `0x18007f568`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlConvertSharedToExclusive` at `0x18006b3f0`
- `ntdll!RtlConvertSharedToExclusive` at `0x18006b6c0`
- `ntdll!RtlConvertSharedToExclusive` at `0x18006b7f0`
- `ntdll!RtlConvertSharedToExclusive` at `0x18006b8fb`
- `ntdll!RtlConvertSharedToExclusive` at `0x18006b3f0`
- `ntdll!RtlConvertSharedToExclusive` at `0x18006b6c0`
- `ntdll!RtlConvertSharedToExclusive` at `0x18006b7f0`
- `ntdll!RtlConvertSharedToExclusive` at `0x18006b8fb`
- `ntdll!RtlConvertExclusiveToShared` at `0x18006b313`
- `ntdll!RtlConvertExclusiveToShared` at `0x18006b5db`
- `ntdll!RtlConvertExclusiveToShared` at `0x18006b7bf`
- `ntdll!RtlConvertExclusiveToShared` at `0x18006b85e`
- `ntdll!RtlConvertExclusiveToShared` at `0x18006b313`
- `ntdll!RtlConvertExclusiveToShared` at `0x18006b5db`
- `ntdll!RtlConvertExclusiveToShared` at `0x18006b7bf`
- `ntdll!RtlConvertExclusiveToShared` at `0x18006b85e`
- `ntdll!NtQuerySystemTime` at `0x18006b0bd`
- `ntdll!NtQuerySystemTime` at `0x18006b997`
- `ntdll!NtQuerySystemTime` at `0x18006b0bd`
- `ntdll!NtQuerySystemTime` at `0x18006b997`
- `ntdll!EtwEventActivityIdControl` at `0x18006b10f`
- `ntdll!EtwEventActivityIdControl` at `0x18006b177`
- `ntdll!EtwEventActivityIdControl` at `0x18006b10f`
- `ntdll!EtwEventActivityIdControl` at `0x18006b177`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006b39e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006b39e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bcac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bcac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b628`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b65f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b86a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b890`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b628`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b65f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b86a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b890`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006b0d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006b9ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006b0d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006b9ad`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006bb95`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006bb95`

## string_xrefs

- `0x18006b47c`: `GetOriginalToken failed: 0x%x in %s`
- `0x18006bb77`: `this->SecurityDescriptor.AddUserAce failed: 0x%x in %s`
- `0x18006b6e8`: `Skipping SendConnectMsg since it was already sent`
- `0x18006ba9f`: `ptrTerminal->GetProtocolName failed: 0x%x in %s`
- `0x18006bb05`: `ptrTerminal->GetSecurityDescriptor failed: 0x%x in %s`
- `0x18006bb43`: `SecurityDescriptor.Initialize failed: 0x%x in %s`
- `0x18006bcfc`: `Reconnect while session is already connected to another terminal`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  unsigned int v57; // [rsp+30h] [rbp-D0h]
  unsigned int v58; // [rsp+30h] [rbp-D0h]
  struct _LUID v59; // [rsp+60h] [rbp-A0h] BYREF
  CGpuManager *v60; // [rsp+68h] [rbp-98h] BYREF
  int v61; // [rsp+70h] [rbp-90h]
  char *v62; // [rsp+78h] [rbp-88h] BYREF
  const char *v63; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v64; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v65; // [rsp+8Ch] [rbp-74h] BYREF
  int v66; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v67[2]; // [rsp+98h] [rbp-68h] BYREF
  PRTL_RESOURCE Resource[2]; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v70; // [rsp+B8h] [rbp-48h] BYREF
  __int128 *v71; // [rsp+C0h] [rbp-40h] BYREF
  struct ICsrPipe *v72; // [rsp+C8h] [rbp-38h] BYREF
  struct IUserName *v73[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _EVENT_DESCRIPTOR v74; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v75; // [rsp+F0h] [rbp-10h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+F8h] [rbp-8h] BYREF
  struct _GUID v77; // [rsp+100h] [rbp+0h] BYREF
  struct ITSSession *v78[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v79[4]; // [rsp+120h] [rbp+20h]
  __int128 v80; // [rsp+130h] [rbp+30h] BYREF
  __int64 v81; // [rsp+140h] [rbp+40h] BYREF
  __int128 v82; // [rsp+148h] [rbp+48h] BYREF
  __int128 v83; // [rsp+158h] [rbp+58h] BYREF
  _SYSTEMTIME v84; // [rsp+168h] [rbp+68h] BYREF
  __int128 v85; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int16 Parameter[48]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v87[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v88; // [rsp+1F4h] [rbp+F4h]
  int v89; // [rsp+30Ch] [rbp+20Ch]
  int v90; // [rsp+330h] [rbp+230h]
  struct _LUID v91; // [rsp+334h] [rbp+234h]
  _BYTE v92[192]; // [rsp+670h] [rbp+570h] BYREF
  unsigned __int16 v93[40]; // [rsp+730h] [rbp+630h] BYREF

  LODWORD(v62) = a4;
  v67[0] = a3;
  memset_0(v87, 0, 0x480u);
  v75 = 0;
  v65 = 0;
  v61 = 0;
  *(_OWORD *)v78 = 0;
  *(_OWORD *)v79 = 0;
  v80 = 0;
  v81 = 0;
  pv = 0;
  v85 = 0;
  v66 = 0;
  v77 = 0;
  v64 = 0;
  v83 = 0;
  v73[0] = 0;
  SystemTime.QuadPart = 0;
  NtQuerySystemTime(&SystemTime);
  v84 = 0;
  GetSystemTime(&v84);
  v72 = 0;
  (*(void (__fastcall **)(struct ITerminal *, char *))(*(_QWORD *)a2 + 216LL))(a2, (char *)this + 3208);
  v82 = 0;
  EtwEventActivityIdControl(1, &v82);
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v60 = (CGpuManager *)"Related Activity ID was of the previous connection";
    v71 = &v82;
    v59 = (struct _LUID)((char *)this + 3208);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
      v6,
      (unsigned int)word_1800C99C2,
      (unsigned int)&v82,
      (_DWORD)this + 3208,
      (__int64)&v59,
      (__int64)&v71,
      (__int64)&v60);
  }
  EtwEventActivityIdControl(2, (char *)this + 3208);
  CTSSessionTrace::CTSSessionTrace((CTSSessionTrace *)v92, "CTSSession::ConnectToTerminal", this);
  LODWORD(v71) = *((_DWORD *)this + 806);
  memset_0(v87, 0, 0x480u);
  *(_OWORD *)v78 = 0;
  *(_OWORD *)v79 = 0;
  v80 = 0;
  v81 = 0;
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
  v13 = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)v78);
  InstanceOfGpuManager = v13;
  if ( v13 < 0 )
  {
    _DbgPrintMessage(8, "InitializeNotifyInfo failed: 0x%x in %s", (unsigned int)v13, "CTSSession::ConnectToTerminal");
    goto LABEL_96;
  }
  CurrentSessionReconnectInfo = CTSSession::getCurrentSessionReconnectInfo(
                                  this,
                                  (enum __MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0003 *)&v66,
                                  &v77);
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
          &v85,
          (char *)this + 3224,
          &v64,
          &v83);
  InstanceOfGpuManager = v15;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(8, "GetTerminalType failed: 0x%x in %s", (unsigned int)v15, "CTSSession::ConnectToTerminal");
    goto LABEL_96;
  }
  v16 = CTSSession::CSessionReconnectController::TryApplyTerminalToSession((char *)this + 5848, v64, &v83);
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
          v78,
          v10,
          a2);
  if ( v18 < 0 )
    _DbgPrintMessage(4, "EventDispatch->OnCsrInitialized failed: 0x%x", v18);
  v74 = (struct _EVENT_DESCRIPTOR)EVENT_TERMINAL_DOCONNECT_TOOLONG;
  CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(
    Parameter,
    (struct _GUID *)((char *)this + 3208),
    *((_DWORD *)this + 436),
    this,
    &v74,
    "pNewTerminal->DoConnect",
    v57);
  v19 = *(__int64 (__fastcall **)(struct ITerminal *, _BYTE *, struct ITSSession *, _QWORD, DWORD))(*(_QWORD *)a2 + 32LL);
  CurrentProcessId = GetCurrentProcessId();
  InstanceOfGpuManager = v19(a2, v87, v78[0], *((_QWORD *)this + 808), CurrentProcessId);
  CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
  if ( InstanceOfGpuManager < 0 )
  {
    _DbgPrintMessage(
      8,
      "DoConnectMsg failed: 0x%x in %s",
      (unsigned int)InstanceOfGpuManager,
      "CTSSession::ConnectToTerminal");
LABEL_95:
    *((_DWORD *)this + 1462) = v66;
    *(struct _GUID *)((char *)this + 5852) = v77;
    *((_DWORD *)this + 806) = (_DWORD)v71;
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
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)v23 + 88LL))(v23, &v75, &v65);
    InstanceOfGpuManager = v16;
    if ( v16 < 0 )
    {
      v17 = "GetOriginalToken failed: 0x%x in %s";
      goto LABEL_94;
    }
  }
  if ( v89 == 1 )
  {
    v60 = 0;
    InstanceOfGpuManager = CGpuManager::GetInstanceOfGpuManager(&v60);
    if ( InstanceOfGpuManager >= 0 )
    {
      v24 = v60;
      if ( *((_DWORD *)v60 + 400) )
      {
        v59 = 0;
        InstanceOfGpuManager = CGpuManager::VerifyGpuAssignment(v60, this);
        if ( InstanceOfGpuManager >= 0 )
        {
          v91 = *(struct _LUID *)(*((_QWORD *)this + 231) + 1904LL);
        }
        else
        {
          InstanceOfGpuManager = CGpuManager::LoadBalanceSessionToGpu(v24, this, &v59);
          if ( InstanceOfGpuManager < 0 )
          {
            v27 = *((_DWORD *)this + 436);
            if ( (unsigned int)dword_1800DF020 > 5 )
            {
              LODWORD(v70) = InstanceOfGpuManager;
              v59.LowPart = v27;
              v63 = "GPU assignment to session failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v27,
                (unsigned int)&byte_1800C998F,
                v25,
                v26,
                (__int64)&v63,
                (__int64)&v59,
                (__int64)&v70);
            }
            goto LABEL_39;
          }
          v91 = v59;
        }
        v90 = 1;
      }
    }
LABEL_39:
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v60);
  }
  SmartPtr<ICsrPipe>::operator=(&v72, *((_QWORD *)this + 223));
  v28 = *((_DWORD *)this + 430);
  v29 = v72;
  if ( v28 == 1 )
  {
    _DbgPrintMessage(1, "Skipping SendConnectMsg since it was already sent");
  }
  else
  {
    *((_DWORD *)this + 430) = 1;
    v74 = (struct _EVENT_DESCRIPTOR)EVENT_SENDCSR_CONNECTMSG;
    CTSSendCSRMsgMonitor::CTSSendCSRMsgMonitor(
      Parameter,
      (struct _GUID *)((char *)this + 3208),
      *((_DWORD *)this + 436),
      this,
      &v74,
      "Connect",
      v58);
    RtlConvertExclusiveToShared(Resource[0]);
    if ( (unsigned int)(v88 - 1) > 0xF || HIDWORD(v88) >= (unsigned int)v88 )
    {
      if ( (g_DebugTraceComponent & 4) != 0 )
        _DbgPrintMessage(
          2,
          "Terminal return invalid monitors data, number of monitor %d, primary monitor %d, reset to default",
          v88,
          HIDWORD(v88));
      v88 = 1;
    }
    TickCount64 = GetTickCount64();
    InstanceOfGpuManager = (*(__int64 (__fastcall **)(struct ICsrPipe *, _BYTE *, __int64, _QWORD, _DWORD))(*(_QWORD *)v29 + 88LL))(
                             v29,
                             v87,
                             v75,
                             v65,
                             (_DWORD)v62);
    v31 = GetTickCount64();
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v63 = (const char *)(v31 - TickCount64);
      LODWORD(v62) = *((_DWORD *)this + 436);
      v60 = (CGpuManager *)"SendConnectMsg took this long";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        dword_1800DF020,
        (unsigned int)&byte_1800C992F,
        v32,
        v33,
        (__int64)&v60,
        (__int64)&v62,
        (__int64)&v63);
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
  v61 = 1;
  v16 = (*(__int64 (__fastcall **)(_QWORD, CTSSession *))(*(_QWORD *)*v34 + 56LL))(*v34, this);
  InstanceOfGpuManager = v16;
  if ( v16 < 0 )
  {
    v17 = "Terminal->Connected failed: 0x%x in %s";
    goto LABEL_94;
  }
  SmartPtr<IUserName>::operator=(v73, *((_QWORD *)this + 741));
  RtlConvertExclusiveToShared(Resource[0]);
  v16 = CTSSession::SetTimeZoneInternalNoLock(v35, v29, a2, v73[0]);
  InstanceOfGpuManager = v16;
  if ( v16 < 0 )
  {
    v17 = "SetTimeZoneInternalNoLock failed: 0x%x in %s";
    goto LABEL_94;
  }
  RtlConvertSharedToExclusive(Resource[0]);
  if ( *((_QWORD *)this + 741) )
  {
    v59 = 0;
    v74 = (struct _EVENT_DESCRIPTOR)EVENT_TERMINAL_LOGON_TOOLONG;
    CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(
      Parameter,
      (struct _GUID *)((char *)this + 3208),
      *((_DWORD *)this + 436),
      this,
      &v74,
      "pNewTerminal->LoggedOn",
      v58);
    SmartPtr<IUserName>::operator=(&v59, *((_QWORD *)this + 741));
    RtlConvertExclusiveToShared(Resource[0]);
    v36 = GetTickCount64();
    InstanceOfGpuManager = (*(__int64 (__fastcall **)(struct ITerminal *, struct _LUID))(*(_QWORD *)a2 + 64LL))(a2, v59);
    v37 = GetTickCount64();
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v63 = (const char *)(v37 - v36);
      LODWORD(v62) = *((_DWORD *)this + 436);
      v60 = (CGpuManager *)"pNewTerminal->LoggedOnStarted() took this long";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        dword_1800DF020,
        (unsigned int)&byte_1800C98D7,
        v38,
        v39,
        (__int64)&v60,
        (__int64)&v62,
        (__int64)&v63);
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
      SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v59);
      goto LABEL_95;
    }
    CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v59);
  }
  if ( !*v34 )
  {
    InstanceOfGpuManager = -2147022646;
    _DbgPrintMessage(8, "NULL == this->ptrTerminal failed: 0x%x in %s", 2147944650LL, "CTSSession::ConnectToTerminal");
    goto LABEL_95;
  }
  *((_DWORD *)this + 518) = *((_DWORD *)this + 528);
  CTSSession::WinLogonSendMessage(this, v67[0], 0);
  v40 = (__int64 *)((char *)this + 1976);
  NtQuerySystemTime((PLARGE_INTEGER)this + 247);
  GetSystemTime((LPSYSTEMTIME)this + 126);
  if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
  {
    v63 = (char *)this + 3208;
    v42 = *v40;
    v43 = (struct _LUID)(*v40 - SystemTime.QuadPart);
    v60 = (CGpuManager *)(*(__int64 *)&v43 / 10000000);
    *(_QWORD *)v67 = &v84;
    v62 = (char *)this + 2016;
    v59 = v43;
    v70 = v42;
    *(_QWORD *)&v74.Id = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
      v43.LowPart,
      (unsigned int)word_1800C984A,
      v42,
      v41,
      (__int64)&v74,
      (__int64)&v70,
      (__int64)&v59,
      (__int64)&v62,
      (__int64)v67,
      (__int64)&v60,
      (__int64)&v63);
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(*(_QWORD *)*v34 + 96LL))(*v34, v93);
  InstanceOfGpuManager = v16;
  if ( v16 < 0 )
  {
    v17 = "ptrTerminal->GetProtocolName failed: 0x%x in %s";
    goto LABEL_94;
  }
  v44 = (char *)*((_QWORD *)this + 740);
  if ( !v44 )
    goto LABEL_80;
  v45 = (char *)((char *)v93 - v44);
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
    v67[0] = 0;
    v16 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, unsigned int *))(*(_QWORD *)*v34 + 200LL))(*v34, &pv, v67);
    InstanceOfGpuManager = v16;
    if ( v16 < 0 )
    {
      v17 = "ptrTerminal->GetSecurityDescriptor failed: 0x%x in %s";
      goto LABEL_94;
    }
    v48 = CTSSessionSecurityDescriptor::DetachSD((CTSSession *)((char *)this + 5872));
    InstanceOfGpuManager = CTSSessionSecurityDescriptor::Initialize((CTSSession *)((char *)this + 5872), v93, pv);
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
  CTSSession::CState::ChangeState((char *)this + 3256, 3, (char *)&v80 + 8, &v81, 3953);
  v53 = *((_DWORD *)this + 814);
  CAutoLock::Unlock((CAutoLock *)Resource);
  v54 = CTSSession::SendSessionNotificationMsg(this, 1);
  if ( v54 < 0 )
    _DbgPrintMessage(8, "SendSessionNotificationMsg failed: 0x%x", v54);
  if ( (_QWORD)v80 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v80 + 16LL))(v80);
  *(_QWORD *)&v80 = a2;
  (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)a2 + 8LL))(a2);
  v16 = (*(__int64 (__fastcall **)(__int64, struct ITSSession **, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 228)
                                                                                             + 1832LL)
                                                                                 + 40LL))(
          *((_QWORD *)this + 228) + 1832LL,
          v78,
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
    if ( v61 )
    {
      CAutoLock::Unlock((CAutoLock *)Resource);
      CTSSession::DisconnectSession(this, 0, 0x202u, 0);
    }
    goto LABEL_104;
  }
  v55 = IsConsole(v78[0]);
  CTSSession::PublishWNFNotification(this, v55 != 0 ? 1 : 3, v79[2]);
  CTSSession::LogSessionEvent(this, &EVENT_SESSION_RECONNECT, a2);
  if ( InstanceOfGpuManager == 1 && !v61 )
  {
    _DbgPrintMessage(8, "Reconnect while session is already connected to another terminal");
    InstanceOfGpuManager = -2147019873;
LABEL_104:
    CTSSession::LogFailedTransition(this, 3, (unsigned int)InstanceOfGpuManager);
  }
  if ( v78[0] )
  {
    (*(void (__fastcall **)(struct ITSSession *))(*(_QWORD *)v78[0] + 16LL))(v78[0]);
    v78[0] = 0;
  }
  if ( (_QWORD)v80 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v80 + 16LL))(v80);
    *(_QWORD *)&v80 = 0;
  }
  CAutoLock::Unlock((CAutoLock *)Resource);
  CTSSessionTrace::~CTSSessionTrace((CTSSessionTrace *)v92);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v72);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(v73);
  return (unsigned int)InstanceOfGpuManager;
}

```

## disassembly

```asm
0x18006b024  push    rbp
0x18006b026  push    rbx
0x18006b027  push    rsi
0x18006b028  push    rdi
0x18006b029  push    r12
0x18006b02b  push    r13
0x18006b02d  push    r14
0x18006b02f  push    r15
0x18006b031  lea     rbp, [rsp-698h]
0x18006b039  sub     rsp, 798h
0x18006b040  mov     rax, cs:__security_cookie
0x18006b047  xor     rax, rsp
0x18006b04a  mov     [rbp+6D0h+var_50], rax
0x18006b051  mov     dword ptr [rsp+7D0h+var_758], r9d
0x18006b056  mov     [rbp+6D0h+var_738], r8d
0x18006b05a  mov     r12, rdx
0x18006b05d  mov     rsi, rcx
0x18006b060  mov     edi, 480h
0x18006b065  mov     r8d, edi; Size
0x18006b068  xor     edx, edx; Val
0x18006b06a  lea     rcx, [rbp+6D0h+var_5E0]; void *
0x18006b071  call    memset_0
0x18006b076  xor     ebx, ebx
0x18006b078  mov     [rbp+6D0h+var_6E0], rbx
0x18006b07c  mov     [rbp+6D0h+var_744], ebx
0x18006b07f  mov     [rsp+7D0h+var_760], ebx
0x18006b083  xorps   xmm0, xmm0
0x18006b086  xor     eax, eax
0x18006b088  movups  xmmword ptr [rbp+6D0h+var_6C0], xmm0
0x18006b08c  movups  xmmword ptr [rbp+6D0h+var_6B0], xmm0
0x18006b090  movups  [rbp+6D0h+var_6A0], xmm0
0x18006b094  mov     [rbp+6D0h+var_690], rax
0x18006b098  mov     [rbp+6D0h+pv], rbx
0x18006b09c  movups  [rbp+6D0h+var_658], xmm0
0x18006b0a0  mov     [rbp+6D0h+var_740], ebx
0x18006b0a3  xorps   xmm1, xmm1
0x18006b0a6  movups  xmmword ptr [rbp+6D0h+var_6D0.Data1], xmm1
0x18006b0aa  mov     [rbp+6D0h+var_748], ebx
0x18006b0ad  movups  [rbp+6D0h+var_678], xmm0
0x18006b0b1  mov     [rbp+6D0h+var_700], rbx
0x18006b0b5  mov     qword ptr [rbp+6D0h+SystemTime], rbx
0x18006b0b9  lea     rcx, [rbp+6D0h+SystemTime]; SystemTime
0x18006b0bd  call    cs:__imp_NtQuerySystemTime
0x18006b0c4  nop     dword ptr [rax+rax+00h]
0x18006b0c9  xorps   xmm0, xmm0
0x18006b0cc  movups  xmmword ptr [rbp+6D0h+var_668.wYear], xmm0
0x18006b0d0  lea     rcx, [rbp+6D0h+var_668]; lpSystemTime
0x18006b0d4  call    cs:__imp_GetSystemTime
0x18006b0db  nop     dword ptr [rax+rax+00h]
0x18006b0e0  mov     [rbp+6D0h+var_708], rbx
0x18006b0e4  lea     r13, [rsi+0C88h]
0x18006b0eb  mov     rax, [r12]
0x18006b0ef  mov     rdx, r13
0x18006b0f2  mov     rcx, r12
0x18006b0f5  mov     rax, [rax+0D8h]
0x18006b0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b101  xorps   xmm0, xmm0
0x18006b104  movups  [rbp+6D0h+var_688], xmm0
0x18006b108  lea     rdx, [rbp+6D0h+var_688]
0x18006b10c  lea     ecx, [rbx+1]
0x18006b10f  call    cs:__imp_EtwEventActivityIdControl
0x18006b116  nop     dword ptr [rax+rax+00h]
0x18006b11b  mov     eax, cs:dword_1800DF020
0x18006b121  cmp     eax, 5
0x18006b124  jbe     short loc_18006B16F
0x18006b126  lea     rax, aRelatedActivit; "Related Activity ID was of the previous"...
0x18006b12d  mov     [rsp+7D0h+var_768], rax
0x18006b132  lea     rax, [rbp+6D0h+var_688]
0x18006b136  mov     [rbp+6D0h+var_710], rax
0x18006b13a  mov     qword ptr [rsp+7D0h+var_770.LowPart], r13
0x18006b13f  lea     rax, [rsp+7D0h+var_768]
0x18006b144  mov     qword ptr [rsp+7D0h+var_7A0], rax; unsigned int
0x18006b149  lea     rax, [rbp+6D0h+var_710]
0x18006b14d  mov     [rsp+7D0h+var_7A8], rax
0x18006b152  lea     rax, [rsp+7D0h+var_770]
0x18006b157  mov     [rsp+7D0h+var_7B0], rax
0x18006b15c  mov     r9, r13
0x18006b15f  lea     r8, [rbp+6D0h+var_688]
0x18006b163  lea     rdx, word_1800C99C2
0x18006b16a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x18006b16f  mov     rdx, r13
0x18006b172  mov     ecx, 2
0x18006b177  call    cs:__imp_EtwEventActivityIdControl
0x18006b17e  nop     dword ptr [rax+rax+00h]
0x18006b183  mov     r8, rsi; struct ITSSession *
0x18006b186  lea     rdx, aCtssessionConn_3; "CTSSession::ConnectToTerminal"
0x18006b18d  lea     rcx, [rbp+6D0h+var_160]; this
0x18006b194  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x18006b199  nop
0x18006b19a  lea     r14, [rsi+0C98h]
0x18006b1a1  mov     eax, [r14]
0x18006b1a4  mov     dword ptr [rbp+6D0h+var_710], eax
0x18006b1a7  mov     r8, rdi; Size
0x18006b1aa  xor     edx, edx; Val
0x18006b1ac  lea     rcx, [rbp+6D0h+var_5E0]; void *
0x18006b1b3  call    memset_0
0x18006b1b8  xorps   xmm0, xmm0
0x18006b1bb  xor     eax, eax
0x18006b1bd  movups  xmmword ptr [rbp+6D0h+var_6C0], xmm0
0x18006b1c1  movups  xmmword ptr [rbp+6D0h+var_6B0], xmm0
0x18006b1c5  movups  [rbp+6D0h+var_6A0], xmm0
0x18006b1c9  mov     [rbp+6D0h+var_690], rax
0x18006b1cd  lea     rdx, [rsi+740h]; struct CResource *
0x18006b1d4  lea     rcx, [rbp+6D0h+Resource]; this
0x18006b1d8  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18006b1dd  nop
0x18006b1de  lea     r15, [rsi+0CB8h]
0x18006b1e5  mov     edx, 3
0x18006b1ea  mov     rcx, r15
0x18006b1ed  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x18006b1f2  mov     edi, eax
0x18006b1f4  mov     ebx, [r15]
0x18006b1f7  test    eax, eax
0x18006b1f9  jns     short loc_18006B21B
0x18006b1fb  mov     ecx, ebx
0x18006b1fd  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18006b202  mov     r8, rax
0x18006b205  lea     rdx, aInvalidStateFo_0; "invalid state for EvConnected, state is"...
0x18006b20c  mov     ecx, 8; int
0x18006b211  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b216  jmp     loc_18006BCA1
0x18006b21b  cmp     eax, 1
0x18006b21e  jnz     short loc_18006B263
0x18006b220  mov     ecx, ebx; int
0x18006b222  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x18006b227  mov     r9, rax
0x18006b22a  mov     ecx, 3; int
0x18006b22f  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x18006b234  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006b23b  jz      loc_18006BCA1
0x18006b241  mov     [rsp+7D0h+var_7B0], rax
0x18006b246  mov     r8d, [rsi+6D0h]
0x18006b24d  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x18006b254  mov     ecx, 2; int
0x18006b259  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b25e  jmp     loc_18006BCA1
0x18006b263  lea     rdx, [rbp+6D0h+var_6C0]; struct __PTSSessInfo *
0x18006b267  mov     rcx, rsi; this
0x18006b26a  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x18006b26f  mov     edi, eax
0x18006b271  test    eax, eax
0x18006b273  jns     short loc_18006B295
0x18006b275  lea     rdx, aInitializenoti_0; "InitializeNotifyInfo failed: 0x%x in %s"
0x18006b27c  lea     r9, aCtssessionConn_3; "CTSSession::ConnectToTerminal"
0x18006b283  mov     r8d, eax
0x18006b286  mov     ecx, 8; int
0x18006b28b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b290  jmp     loc_18006BCA1
0x18006b295  lea     r8, [rbp+6D0h+var_6D0]; struct _GUID *
0x18006b299  lea     rdx, [rbp+6D0h+var_740]; enum __MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0003 *
0x18006b29d  mov     rcx, rsi; this
0x18006b2a0  call    ?getCurrentSessionReconnectInfo@CTSSession@@UEAAJPEAW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0003@@PEAU_GUID@@@Z; CTSSession::getCurrentSessionReconnectInfo(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0003 *,_GUID *)
0x18006b2a5  mov     edi, eax
0x18006b2a7  test    eax, eax
0x18006b2a9  jns     short loc_18006B2B4
0x18006b2ab  lea     rdx, aGetcurrentsess; "getCurrentSessionReconnectInfo failed: "...
0x18006b2b2  jmp     short loc_18006B27C
0x18006b2b4  mov     rax, [r12]
0x18006b2b8  lea     rcx, [rbp+6D0h+var_678]
0x18006b2bc  mov     [rsp+7D0h+var_7B0], rcx
0x18006b2c1  lea     r9, [rbp+6D0h+var_748]
0x18006b2c5  mov     r8, r14
0x18006b2c8  lea     rdx, [rbp+6D0h+var_658]
0x18006b2cc  mov     rcx, r12
0x18006b2cf  mov     rax, [rax+88h]
0x18006b2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2db  mov     edi, eax
0x18006b2dd  test    eax, eax
0x18006b2df  jns     short loc_18006B2EA
0x18006b2e1  lea     rdx, aGetterminaltyp; "GetTerminalType failed: 0x%x in %s"
0x18006b2e8  jmp     short loc_18006B27C
0x18006b2ea  lea     rcx, [rsi+16D8h]
0x18006b2f1  lea     r8, [rbp+6D0h+var_678]
0x18006b2f5  mov     edx, [rbp+6D0h+var_748]
0x18006b2f8  call    ?TryApplyTerminalToSession@CSessionReconnectController@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004@@AEAU_GUID@@@Z; CTSSession::CSessionReconnectController::TryApplyTerminalToSession(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0004,_GUID &)
0x18006b2fd  mov     edi, eax
0x18006b2ff  test    eax, eax
0x18006b301  jns     short loc_18006B30F
0x18006b303  lea     rdx, aSessionreconne_0; "SessionReconnectController.TryApplyTerm"...
0x18006b30a  jmp     loc_18006BC6F
0x18006b30f  mov     rcx, [rbp+6D0h+Resource]; Resource
0x18006b313  call    cs:__imp_RtlConvertExclusiveToShared
0x18006b31a  nop     dword ptr [rax+rax+00h]
0x18006b31f  mov     rcx, [rsi+720h]
0x18006b326  add     rcx, 728h
0x18006b32d  mov     rax, [rcx]
0x18006b330  mov     r9, r12
0x18006b333  mov     r8d, ebx
0x18006b336  lea     rdx, [rbp+6D0h+var_6C0]
0x18006b33a  mov     rax, [rax+20h]
0x18006b33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b343  test    eax, eax
0x18006b345  jns     short loc_18006B35B
0x18006b347  mov     r8d, eax
0x18006b34a  lea     rdx, aEventdispatchO_4; "EventDispatch->OnCsrInitialized failed:"...
0x18006b351  mov     ecx, 4; int
0x18006b356  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b35b  movups  xmm0, cs:EVENT_TERMINAL_DOCONNECT_TOOLONG
0x18006b362  movdqu  xmmword ptr [rbp+6D0h+var_6F0.Id], xmm0
0x18006b367  lea     rax, aPnewterminalDo; "pNewTerminal->DoConnect"
0x18006b36e  mov     [rsp+7D0h+var_7A8], rax; char *
0x18006b373  lea     rax, [rbp+6D0h+var_6F0]
0x18006b377  mov     [rsp+7D0h+var_7B0], rax; struct _EVENT_DESCRIPTOR
0x18006b37c  mov     r9, rsi; struct ITSSession *
0x18006b37f  mov     r8d, [rsi+6D0h]; int
0x18006b386  mov     rdx, r13; struct _GUID *
0x18006b389  lea     rcx, [rbp+6D0h+Parameter]; Parameter
0x18006b390  call    ??0CTSTerminalOpsMonitor@@QEAA@PEAU_GUID@@JPEAUITSSession@@U_EVENT_DESCRIPTOR@@PEBDK@Z; CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(_GUID *,long,ITSSession *,_EVENT_DESCRIPTOR,char const *,ulong)
0x18006b395  nop
0x18006b396  mov     rax, [r12]
0x18006b39a  mov     rbx, [rax+20h]
0x18006b39e  call    cs:__imp_GetCurrentProcessId
0x18006b3a5  nop     dword ptr [rax+rax+00h]
0x18006b3aa  mov     dword ptr [rsp+7D0h+var_7B0], eax
0x18006b3ae  mov     r9, [rsi+1940h]
0x18006b3b5  mov     r8, [rbp+6D0h+var_6C0]
0x18006b3b9  lea     rdx, [rbp+6D0h+var_5E0]
0x18006b3c0  mov     rcx, r12
0x18006b3c3  mov     rax, rbx
0x18006b3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b3cb  mov     edi, eax
0x18006b3cd  lea     rcx, [rbp+6D0h+Parameter]; this
0x18006b3d4  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006b3d9  test    edi, edi
0x18006b3db  jns     short loc_18006B3EC
0x18006b3dd  mov     r8d, edi
0x18006b3e0  lea     rdx, aDoconnectmsgFa; "DoConnectMsg failed: 0x%x in %s"
0x18006b3e7  jmp     loc_18006BC72
0x18006b3ec  mov     rcx, [rbp+6D0h+Resource]; Resource
0x18006b3f0  call    cs:__imp_RtlConvertSharedToExclusive
0x18006b3f7  nop     dword ptr [rax+rax+00h]
0x18006b3fc  mov     r8, r12; struct ITerminal *
0x18006b3ff  mov     edx, 12AAh; unsigned int
0x18006b404  mov     rcx, rsi; this
0x18006b407  call    ?AuditEvent@CTSSession@@AEAAJKPEAUITerminal@@@Z; CTSSession::AuditEvent(ulong,ITerminal *)
0x18006b40c  mov     edx, 3
0x18006b411  mov     rcx, r15
0x18006b414  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x18006b419  mov     edi, eax
0x18006b41b  test    eax, eax
0x18006b41d  jns     short loc_18006B440
0x18006b41f  mov     ecx, [r15]
0x18006b422  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18006b427  mov     r8, rax
0x18006b42a  lea     rdx, aInvalidStateFo_0; "invalid state for EvConnected, state is"...
0x18006b431  mov     ecx, 8; int
0x18006b436  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b43b  jmp     loc_18006BC83
0x18006b440  mov     r14d, 1
0x18006b446  cmp     eax, r14d
0x18006b449  jnz     short loc_18006B453
0x18006b44b  mov     ecx, [r15]
0x18006b44e  jmp     loc_18006B222
0x18006b453  mov     rcx, [rsi+1728h]
0x18006b45a  xor     r15d, r15d
0x18006b45d  test    rcx, rcx
0x18006b460  jz      short loc_18006B488
0x18006b462  mov     rax, [rcx]
0x18006b465  lea     r8, [rbp+6D0h+var_744]
0x18006b469  lea     rdx, [rbp+6D0h+var_6E0]
0x18006b46d  mov     rax, [rax+58h]
0x18006b471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b476  mov     edi, eax
0x18006b478  test    eax, eax
0x18006b47a  jns     short loc_18006B488
0x18006b47c  lea     rdx, aGetoriginaltok; "GetOriginalToken failed: 0x%x in %s"
0x18006b483  jmp     loc_18006BC6F
0x18006b488  cmp     [rbp+6D0h+var_4C4], r14d
0x18006b48f  jnz     loc_18006B56D
0x18006b495  mov     [rsp+7D0h+var_768], r15
0x18006b49a  lea     rcx, [rsp+7D0h+var_768]; struct CGpuManager **
0x18006b49f  call    ?GetInstanceOfGpuManager@CGpuManager@@SAJPEAPEAV1@@Z; CGpuManager::GetInstanceOfGpuManager(CGpuManager * *)
0x18006b4a4  mov     edi, eax
0x18006b4a6  test    eax, eax
0x18006b4a8  js      loc_18006B563
0x18006b4ae  mov     rbx, [rsp+7D0h+var_768]
0x18006b4b3  cmp     [rbx+640h], r15d
0x18006b4ba  jz      loc_18006B563
0x18006b4c0  mov     qword ptr [rsp+7D0h+var_770.LowPart], r15
0x18006b4c5  mov     rdx, rsi; struct ITSSessionPrivate *
0x18006b4c8  mov     rcx, rbx; this
0x18006b4cb  call    ?VerifyGpuAssignment@CGpuManager@@QEAAJPEAVITSSessionPrivate@@@Z; CGpuManager::VerifyGpuAssignment(ITSSessionPrivate *)
0x18006b4d0  mov     edi, eax
0x18006b4d2  test    eax, eax
0x18006b4d4  jns     short loc_18006B547
0x18006b4d6  lea     r8, [rsp+7D0h+var_770]; struct _LUID *
0x18006b4db  mov     rdx, rsi; struct ITSSessionPrivate *
0x18006b4de  mov     rcx, rbx; this
0x18006b4e1  call    ?LoadBalanceSessionToGpu@CGpuManager@@QEAAJPEAVITSSessionPrivate@@PEAU_LUID@@@Z; CGpuManager::LoadBalanceSessionToGpu(ITSSessionPrivate *,_LUID *)
0x18006b4e6  mov     edi, eax
0x18006b4e8  test    eax, eax
0x18006b4ea  js      short loc_18006B4FA
0x18006b4ec  mov     rax, qword ptr [rsp+7D0h+var_770.LowPart]
0x18006b4f1  mov     [rbp+6D0h+var_49C], rax
0x18006b4f8  jmp     short loc_18006B55C
0x18006b4fa  mov     ecx, [rsi+6D0h]
0x18006b500  mov     eax, cs:dword_1800DF020
0x18006b506  cmp     eax, 5
0x18006b509  jbe     short loc_18006B563
0x18006b50b  mov     dword ptr [rbp+6D0h+var_718], edi
  ... truncated ...
```
