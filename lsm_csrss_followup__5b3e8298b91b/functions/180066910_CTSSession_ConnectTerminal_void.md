# CTSSession::ConnectTerminal(void)

- ea: `0x180066910`
- end: `0x180067313`
- name: `?ConnectTerminal@CTSSession@@UEAAJXZ`
- size: `2563`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `0`
- callee_count: `36`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b80`
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
- `0x18000a5d0`
- `0x18000aad4`
- `0x18000f154`
- `0x180010fb0`
- `0x180018200`
- `0x18001ce00`
- `0x18001fd20`
- `0x180022d58`
- `0x1800243c4`
- `0x180024884`
- `0x180024910`
- `0x180024ce0`
- `0x180025890`
- `0x1800267c4`
- `0x180028784`
- `0x180028bbc`
- `0x18002bf6c`
- `0x180034644`
- `0x18004b460`
- `0x18004bf44`
- `0x180066910`
- `0x18006a634`
- `0x18007a9bc`
- `0x180097010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180066d51`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800671e8`
- `ntdll!RtlAcquireResourceExclusive` at `0x180066d51`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800671e8`
- `ntdll!EtwEventActivityIdControl` at `0x180066dcb`
- `ntdll!EtwEventActivityIdControl` at `0x180066dcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180066c64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180066c64`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180066f4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180066f7a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180066f4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180066f7a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180066d17`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180066d17`

## string_xrefs

- `0x180066b8f`: `Session has no temp terminal (ptrTerminalTmp), not connecting terminal`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTSSession::ConnectTerminal(CTSSession *this)
{
  signed int v2; // edi
  int v3; // r8d
  int v4; // r9d
  int *v5; // r14
  CGpuManager *v6; // r15
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v10; // eax
  const char *StateName; // rax
  __int64 v12; // rcx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rbx
  char *v16; // rax
  __int64 *v17; // rdx
  int v18; // eax
  int v19; // r8d
  int v20; // r9d
  __int64 (__fastcall *v21)(__int64, _BYTE *, _QWORD, _QWORD, DWORD); // rdi
  DWORD CurrentProcessId; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  void *v26; // rdi
  DWORD SecurityDescriptorLength; // eax
  int v28; // eax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  DWORD v32; // edx
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  ULONGLONG TickCount64; // rbx
  ULONGLONG v37; // rax
  int v38; // r8d
  int v39; // r9d
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  signed int v46; // edx
  int v47; // r8d
  int v48; // r9d
  unsigned int v49; // edi
  unsigned int v50; // ebx
  int v51; // ecx
  int v52; // r8d
  int v53; // r9d
  unsigned int v55; // [rsp+30h] [rbp-D0h]
  unsigned int v56; // [rsp+30h] [rbp-D0h]
  unsigned int v57; // [rsp+30h] [rbp-D0h]
  CGpuManager *v58; // [rsp+40h] [rbp-C0h] BYREF
  struct _LUID v59; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DESCRIPTOR v60; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v61[2]; // [rsp+60h] [rbp-A0h] BYREF
  PRTL_RESOURCE Resource; // [rsp+68h] [rbp-98h] BYREF
  int v63; // [rsp+70h] [rbp-90h]
  __int64 v64; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v65[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v66; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v67; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 Parameter[48]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v69[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v70[4]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v71; // [rsp+144h] [rbp+44h]
  int v72; // [rsp+25Ch] [rbp+15Ch]
  int v73; // [rsp+280h] [rbp+180h]
  struct _LUID v74; // [rsp+284h] [rbp+184h]
  _BYTE v75[192]; // [rsp+5C0h] [rbp+4C0h] BYREF

  memset_0(v70, 0, 0x480u);
  v64 = 0;
  memset(v65, 0, sizeof(v65));
  v66 = 0;
  v67 = 0;
  CAutoSetActivityId::CAutoSetActivityId((CAutoSetActivityId *)v69, (struct _GUID *)((char *)this + 3208));
  CTSSessionTrace::CTSSessionTrace((CTSSessionTrace *)v75, "CTSSession::ConnectTerminal", this);
  *(_QWORD *)&v65[0] = 0;
  memset_0(v70, 0, 0x480u);
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)&Resource, (CTSSession *)((char *)this + 1856));
  if ( *((_DWORD *)this + 811) )
    CTSSession::OnBrokenConnectionEx(this, 3u, 2u, 0x20Eu);
  v2 = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)v65);
  if ( v2 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v58 = (CGpuManager *)"ConnectTerminal";
      v61[0] = v2;
      v59 = (struct _LUID)"InitializeNotifyInfo";
      *(_QWORD *)&v60.Id = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1800DA020,
        (unsigned int)qword_1800C43F8,
        v3,
        v4,
        (__int64)&v60,
        (__int64)&v59,
        (__int64)v61,
        (__int64)&v58);
    }
    goto LABEL_66;
  }
  v5 = (int *)((char *)this + 3256);
  v6 = (CGpuManager *)*((int *)this + 814);
  if ( (unsigned int)IsDisconnectedState(*((unsigned int *)this + 814)) )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      *(_QWORD *)&v60.Id = *((int *)this + 436);
      v58 = v6;
      v59 = (struct _LUID)"Session in disconnected state, not connecting terminal.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v7,
        (unsigned int)byte_1800C43C1,
        v8,
        v9,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v60);
    }
    goto LABEL_10;
  }
  v10 = CTSSession::CState::CheckState((char *)this + 3256, 2);
  v2 = v10;
  if ( v10 < 0 )
  {
LABEL_12:
    StateName = (const char *)CUtils::GetStateName((unsigned int)*v5);
    _DbgPrintMessage(8, "invalid state for EvCsrInitialized, state is: \"%s\"", StateName);
    goto LABEL_66;
  }
  if ( v10 == 1 )
    goto LABEL_14;
  SmartPtr<ITerminal>::operator=(&v64, *((_QWORD *)this + 227));
  CAutoLock::Unlock((CAutoLock *)&Resource);
  v15 = v64;
  if ( !v64 )
  {
    if ( (unsigned int)dword_1800DA020 <= 2 )
    {
LABEL_10:
      v2 = -2147022646;
LABEL_66:
      CTSSession::LogFailedTransition(this, 2, (unsigned int)v2);
      goto LABEL_67;
    }
    *(_QWORD *)&v60.Id = *((int *)this + 436);
    v16 = "Session has no temp terminal (ptrTerminalTmp), not connecting terminal";
    v17 = (__int64 *)byte_1800C4391;
LABEL_19:
    v58 = (CGpuManager *)v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v12,
      (_DWORD)v17,
      v13,
      v14,
      (__int64)&v58,
      (__int64)&v60);
    goto LABEL_10;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD, __int64))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL)
                                                                      + 32LL))(
          *((_QWORD *)this + 228) + 1832LL,
          v65,
          (unsigned int)v6,
          v64);
  if ( v18 < 0 && (unsigned int)dword_1800DA020 > 3 )
  {
    v61[0] = v18;
    *(_QWORD *)&v60.Id = "EventDispatch->OnCsrInitialized failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DA020,
      (unsigned int)&byte_1800C4367,
      v19,
      v20,
      (__int64)&v60,
      (__int64)v61);
  }
  v60 = (struct _EVENT_DESCRIPTOR)EVENT_TERMINAL_DOCONNECT_TOOLONG;
  CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(
    Parameter,
    (struct _GUID *)((char *)this + 3208),
    *((_DWORD *)this + 436),
    this,
    &v60,
    "ptrTerminalTmp->DoConnect",
    v55);
  v21 = *(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD, DWORD))(*(_QWORD *)v15 + 32LL);
  CurrentProcessId = GetCurrentProcessId();
  v2 = v21(v15, v70, *(_QWORD *)&v65[0], *((_QWORD *)this + 808), CurrentProcessId);
  if ( v2 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      *(_QWORD *)&v60.Id = "ConnectTerminal";
      v61[0] = v2;
      v58 = (CGpuManager *)"Terminal->DoConnect";
      v59 = (struct _LUID)"Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v23,
        (unsigned int)qword_1800C4328,
        v24,
        v25,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)v61,
        (__int64)&v60);
    }
LABEL_26:
    CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
    goto LABEL_66;
  }
  CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
  v26 = (void *)*((_QWORD *)this + 739);
  SecurityDescriptorLength = GetSecurityDescriptorLength(v26);
  (*(void (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v15 + 192LL))(v15, v26, SecurityDescriptorLength);
  v63 = 1;
  if ( LODWORD(Resource[1].Lock.DebugInfo) )
    RtlAcquireResourceExclusive(Resource, 1u);
  v28 = CTSSession::CState::CheckState((char *)this + 3256, 2);
  v2 = v28;
  if ( v28 < 0 )
    goto LABEL_12;
  if ( v28 == 1 )
  {
LABEL_14:
    GetLsmStateName(*v5);
    GetLsmEventName(2);
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "No change to session %d state %ws with event %ws", *((unsigned int *)this + 436));
    goto LABEL_67;
  }
  v12 = *((_QWORD *)this + 227);
  if ( !v12 )
  {
    if ( (unsigned int)dword_1800DA020 <= 2 )
      goto LABEL_10;
    *(_QWORD *)&v60.Id = *((int *)this + 436);
    v16 = "Session has no terminal (ptrTerminal), not connecting terminal";
    v17 = qword_1800C42F8;
    goto LABEL_19;
  }
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 216LL))(v12, (char *)this + 3208);
  EtwEventActivityIdControl(2, (char *)this + 3208);
  if ( v72 == 1 )
  {
    v58 = 0;
    if ( (int)CGpuManager::GetInstanceOfGpuManager(&v58) >= 0 && *((_DWORD *)v58 + 400) )
    {
      v59 = 0;
      v29 = CGpuManager::LoadBalanceSessionToGpu(v58, this, &v59);
      if ( v29 < 0 )
      {
        v32 = *((_DWORD *)this + 436);
        if ( (unsigned int)dword_1800DA020 > 5 )
        {
          v61[0] = v29;
          v59.LowPart = v32;
          *(_QWORD *)&v60.Id = "GPU assignment to session failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v29,
            (unsigned int)byte_1800C42C5,
            v30,
            v31,
            (__int64)&v60,
            (__int64)&v59,
            (__int64)v61);
        }
      }
      else
      {
        v73 = 1;
        v74 = v59;
      }
    }
    SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v58);
  }
  v60 = (struct _EVENT_DESCRIPTOR)EVENT_SENDCSR_CONNECTMSG;
  CTSSendCSRMsgMonitor::CTSSendCSRMsgMonitor(
    Parameter,
    (struct _GUID *)((char *)this + 3208),
    *((_DWORD *)this + 436),
    this,
    &v60,
    "Connect",
    v56);
  v34 = v71;
  v35 = HIDWORD(v71);
  if ( (unsigned int)(v71 - 1) > 0xF || HIDWORD(v71) >= (unsigned int)v71 )
  {
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(
        2,
        "Terminal return invalid monitors data, number of monitor %d, primary monitor %d, reset to default",
        v71,
        HIDWORD(v71));
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      *(_QWORD *)&v60.Id = HIDWORD(v71);
      v58 = (CGpuManager *)(unsigned int)v71;
      v59 = (struct _LUID)"Terminal returned invalid number of monitors, resetting to default (NumMonitors=1, PrimaryMonitor=0)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v33,
        (unsigned int)byte_1800C4281,
        v34,
        v35,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v60);
    }
    v71 = 1;
  }
  TickCount64 = GetTickCount64();
  v2 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, _QWORD, _DWORD))(**((_QWORD **)this + 223) + 88LL))(
         *((_QWORD *)this + 223),
         v70,
         0,
         0,
         0);
  v37 = GetTickCount64();
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    *(_QWORD *)&v60.Id = v37 - TickCount64;
    v58 = (CGpuManager *)*((int *)this + 436);
    v59 = (struct _LUID)"SendConnectMsg";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      dword_1800DA020,
      (unsigned int)byte_1800C4231,
      v38,
      v39,
      (__int64)&v59,
      (__int64)&v58,
      (__int64)&v60);
  }
  CTSSendCSRMsgMonitor::~CTSSendCSRMsgMonitor((CTSSendCSRMsgMonitor *)Parameter);
  if ( v2 < 0 )
  {
    StringCchPrintfW(Parameter, 0x28u, L"connect (%d)", *((unsigned int *)this + 436));
    CrimsonHelper::RaiseEvent<unsigned short *,long>(
      &CrimsonHelper::s_instance,
      EVENT_LSM_CSRSS_MESSAGESEND_FAILED,
      Parameter,
      (unsigned int)v2);
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      *(_QWORD *)&v60.Id = "ConnectTerminal";
      v59.LowPart = v2;
      v58 = (CGpuManager *)"CsrPipe->SendConnectMsg";
      *(_QWORD *)v61 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v40,
        (unsigned int)word_1800C41F2,
        v41,
        v42,
        (__int64)v61,
        (__int64)&v58,
        (__int64)&v59,
        (__int64)&v60);
    }
    goto LABEL_66;
  }
  *((_DWORD *)this + 430) = 1;
  v60 = (struct _EVENT_DESCRIPTOR)EVENT_TERMINAL_CONNECTED_TOOLONG;
  CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(
    Parameter,
    (struct _GUID *)((char *)this + 3208),
    *((_DWORD *)this + 436),
    this,
    &v60,
    "ptrTerminal->Connected",
    v57);
  v2 = (*(__int64 (__fastcall **)(_QWORD, CTSSession *))(**((_QWORD **)this + 227) + 56LL))(
         *((_QWORD *)this + 227),
         this);
  if ( v2 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      *(_QWORD *)&v60.Id = "ConnectTerminal";
      v59.LowPart = v2;
      v58 = (CGpuManager *)"Terminal->Connected";
      *(_QWORD *)v61 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v43,
        (unsigned int)byte_1800C41B3,
        v44,
        v45,
        (__int64)v61,
        (__int64)&v58,
        (__int64)&v59,
        (__int64)&v60);
    }
    goto LABEL_26;
  }
  CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
  CAutoLock::Unlock((CAutoLock *)&Resource);
  v46 = CTSSession::SetTimeZone(this);
  if ( v46 < 0 && (unsigned int)dword_1800DA020 > 3 )
  {
    *(_QWORD *)&v60.Id = "ConnectTerminal";
    v59.LowPart = v46;
    v58 = (CGpuManager *)"SetTimeZone";
    *(_QWORD *)v61 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_1800DA020,
      (unsigned int)&dword_1800C4174,
      v47,
      v48,
      (__int64)v61,
      (__int64)&v58,
      (__int64)&v59,
      (__int64)&v60);
  }
  v63 = 1;
  if ( LODWORD(Resource[1].Lock.DebugInfo) )
    RtlAcquireResourceExclusive(Resource, 1u);
  v49 = *v5;
  CTSSession::CState::ChangeState((char *)this + 3256, 2, (char *)&v66 + 8, &v67, 5174);
  v50 = *v5;
  CAutoLock::Unlock((CAutoLock *)&Resource);
  v2 = (*(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL)
                                                                    + 112LL))(
         *((_QWORD *)this + 228) + 1832LL,
         v65,
         v50,
         v49);
  if ( v2 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v59.LowPart = v2;
      *(_QWORD *)&v60.Id = "EventDispatch->OnCsrInitialized failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v51,
        (unsigned int)word_1800C414A,
        v52,
        v53,
        (__int64)&v60,
        (__int64)&v59);
    }
    goto LABEL_66;
  }
LABEL_67:
  if ( *(_QWORD *)&v65[0] )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v65[0] + 16LL))(*(_QWORD *)&v65[0]);
    *(_QWORD *)&v65[0] = 0;
  }
  if ( (_QWORD)v66 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v66 + 16LL))(v66);
    *(_QWORD *)&v66 = 0;
  }
  CAutoLock::Unlock((CAutoLock *)&Resource);
  CTSSessionTrace::~CTSSessionTrace((CTSSessionTrace *)v75);
  CAutoSetActivityId::~CAutoSetActivityId((CAutoSetActivityId *)v69);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v64);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180066910  push    rbp
0x180066912  push    rbx
0x180066913  push    rsi
0x180066914  push    rdi
0x180066915  push    r12
0x180066917  push    r13
0x180066919  push    r14
0x18006691b  push    r15
0x18006691d  lea     rbp, [rsp-598h]
0x180066925  sub     rsp, 698h
0x18006692c  mov     rax, cs:__security_cookie
0x180066933  xor     rax, rsp
0x180066936  mov     [rbp+5D0h+var_50], rax
0x18006693d  mov     rsi, rcx
0x180066940  mov     ebx, 480h
0x180066945  mov     r8d, ebx; Size
0x180066948  xor     edx, edx; Val
0x18006694a  lea     rcx, [rbp+5D0h+var_590]; void *
0x18006694e  call    memset_0
0x180066953  xor     r13d, r13d
0x180066956  mov     [rsp+6D0h+var_658], r13
0x18006695b  xorps   xmm0, xmm0
0x18006695e  xor     eax, eax
0x180066960  movups  [rbp+5D0h+var_650], xmm0
0x180066964  movups  [rbp+5D0h+var_640], xmm0
0x180066968  movups  [rbp+5D0h+var_630], xmm0
0x18006696c  mov     [rbp+5D0h+var_620], rax
0x180066970  lea     r12, [rsi+0C88h]
0x180066977  mov     rdx, r12; struct _GUID *
0x18006697a  lea     rcx, [rbp+5D0h+var_5B0]; this
0x18006697e  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x180066983  nop
0x180066984  mov     r8, rsi; struct ITSSession *
0x180066987  lea     rdx, aCtssessionConn_6; "CTSSession::ConnectTerminal"
0x18006698e  lea     rcx, [rbp+5D0h+var_110]; this
0x180066995  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x18006699a  nop
0x18006699b  mov     qword ptr [rbp+5D0h+var_650], r13
0x18006699f  mov     r8d, ebx; Size
0x1800669a2  xor     edx, edx; Val
0x1800669a4  lea     rcx, [rbp+5D0h+var_590]; void *
0x1800669a8  call    memset_0
0x1800669ad  lea     rdx, [rsi+740h]; struct CResource *
0x1800669b4  lea     rcx, [rsp+6D0h+Resource]; this
0x1800669b9  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800669be  nop
0x1800669bf  cmp     [rsi+0CACh], r13d
0x1800669c6  jz      short loc_1800669DE
0x1800669c8  lea     edx, [r13+3]; unsigned int
0x1800669cc  mov     r9d, 20Eh; unsigned int
0x1800669d2  lea     r8d, [r13+2]; unsigned int
0x1800669d6  mov     rcx, rsi; this
0x1800669d9  call    ?OnBrokenConnectionEx@CTSSession@@AEAAJKKK@Z; CTSSession::OnBrokenConnectionEx(ulong,ulong,ulong)
0x1800669de  lea     rdx, [rbp+5D0h+var_650]; struct __PTSSessInfo *
0x1800669e2  mov     rcx, rsi; this
0x1800669e5  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x1800669ea  mov     edi, eax
0x1800669ec  test    eax, eax
0x1800669ee  jns     short loc_180066A60
0x1800669f0  mov     ecx, cs:dword_1800DA020
0x1800669f6  cmp     ecx, 3
0x1800669f9  jbe     loc_180067280
0x1800669ff  lea     rax, aConnecttermina_0; "ConnectTerminal"
0x180066a06  mov     [rsp+6D0h+var_690], rax
0x180066a0b  mov     [rsp+6D0h+var_670], edi
0x180066a0f  lea     rax, aInitializenoti; "InitializeNotifyInfo"
0x180066a16  mov     qword ptr [rsp+6D0h+var_688.LowPart], rax
0x180066a1b  lea     rax, aWarningHresult; "Warning HResult failed"
0x180066a22  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x180066a27  lea     rax, [rsp+6D0h+var_690]
0x180066a2c  mov     [rsp+6D0h+var_698], rax
0x180066a31  lea     rax, [rsp+6D0h+var_670]
0x180066a36  mov     qword ptr [rsp+6D0h+var_6A0], rax
0x180066a3b  lea     rax, [rsp+6D0h+var_688]
0x180066a40  mov     [rsp+6D0h+var_6A8], rax
0x180066a45  lea     rax, [rsp+6D0h+var_680]
0x180066a4a  lea     rdx, qword_1800C43F8
0x180066a51  mov     [rsp+6D0h+var_6B0], rax
0x180066a56  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180066a5b  jmp     loc_180067280
0x180066a60  lea     r14, [rsi+0CB8h]
0x180066a67  movsxd  r15, dword ptr [r14]
0x180066a6a  mov     ecx, r15d
0x180066a6d  call    IsDisconnectedState
0x180066a72  test    eax, eax
0x180066a74  jz      short loc_180066AD2
0x180066a76  mov     eax, cs:dword_1800DA020
0x180066a7c  cmp     eax, 3
0x180066a7f  jbe     short loc_180066AC8
0x180066a81  movsxd  rax, dword ptr [rsi+6D0h]
0x180066a88  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x180066a8d  mov     [rsp+6D0h+var_690], r15
0x180066a92  lea     rax, aSessionInDisco; "Session in disconnected state, not conn"...
0x180066a99  mov     qword ptr [rsp+6D0h+var_688.LowPart], rax
0x180066a9e  lea     rax, [rsp+6D0h+var_680]
0x180066aa3  mov     qword ptr [rsp+6D0h+var_6A0], rax
0x180066aa8  lea     rax, [rsp+6D0h+var_690]
0x180066aad  mov     [rsp+6D0h+var_6A8], rax
0x180066ab2  lea     rax, [rsp+6D0h+var_688]
0x180066ab7  mov     [rsp+6D0h+var_6B0], rax
0x180066abc  lea     rdx, byte_1800C43C1
0x180066ac3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180066ac8  mov     edi, 800708CAh
0x180066acd  jmp     loc_180067280
0x180066ad2  mov     edx, 2
0x180066ad7  mov     rcx, r14
0x180066ada  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x180066adf  mov     edi, eax
0x180066ae1  test    eax, eax
0x180066ae3  jns     short loc_180066B06
0x180066ae5  mov     ecx, [r14]
0x180066ae8  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x180066aed  mov     r8, rax
0x180066af0  lea     rdx, aInvalidStateFo_4; "invalid state for EvCsrInitialized, sta"...
0x180066af7  mov     ecx, 8; int
0x180066afc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180066b01  jmp     loc_180067280
0x180066b06  cmp     eax, 1
0x180066b09  jnz     short loc_180066B4F
0x180066b0b  mov     ecx, [r14]; int
0x180066b0e  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x180066b13  mov     r9, rax
0x180066b16  mov     ecx, 2; int
0x180066b1b  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x180066b20  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x180066b27  jz      loc_180067290
0x180066b2d  mov     [rsp+6D0h+var_6B0], rax
0x180066b32  mov     r8d, [rsi+6D0h]
0x180066b39  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x180066b40  mov     ecx, 2; int
0x180066b45  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180066b4a  jmp     loc_180067290
0x180066b4f  mov     rdx, [rsi+718h]
0x180066b56  lea     rcx, [rsp+6D0h+var_658]
0x180066b5b  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180066b60  lea     rcx, [rsp+6D0h+Resource]; this
0x180066b65  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180066b6a  mov     rbx, [rsp+6D0h+var_658]
0x180066b6f  test    rbx, rbx
0x180066b72  jnz     short loc_180066BC0
0x180066b74  mov     eax, cs:dword_1800DA020
0x180066b7a  cmp     eax, 2
0x180066b7d  jbe     loc_180066AC8
0x180066b83  movsxd  rax, dword ptr [rsi+6D0h]
0x180066b8a  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x180066b8f  lea     rax, aSessionHasNoTe_0; "Session has no temp terminal (ptrTermin"...
0x180066b96  lea     rdx, byte_1800C4391
0x180066b9d  mov     [rsp+6D0h+var_690], rax
0x180066ba2  lea     rax, [rsp+6D0h+var_680]
0x180066ba7  mov     [rsp+6D0h+var_6A8], rax
0x180066bac  lea     rax, [rsp+6D0h+var_690]
0x180066bb1  mov     [rsp+6D0h+var_6B0], rax
0x180066bb6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180066bbb  jmp     loc_180066AC8
0x180066bc0  mov     rcx, [rsi+720h]
0x180066bc7  add     rcx, 728h
0x180066bce  mov     rax, [rcx]
0x180066bd1  mov     r9, rbx
0x180066bd4  mov     r8d, r15d
0x180066bd7  lea     rdx, [rbp+5D0h+var_650]
0x180066bdb  mov     rax, [rax+20h]
0x180066bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066be4  lea     rdx, aEventdispatchO_3; "EventDispatch->OnCsrInitialized failed"
0x180066beb  test    eax, eax
0x180066bed  jns     short loc_180066C23
0x180066bef  mov     ecx, cs:dword_1800DA020
0x180066bf5  cmp     ecx, 3
0x180066bf8  jbe     short loc_180066C23
0x180066bfa  mov     [rsp+6D0h+var_670], eax
0x180066bfe  mov     qword ptr [rsp+6D0h+var_680.Id], rdx
0x180066c03  lea     rax, [rsp+6D0h+var_670]
0x180066c08  mov     [rsp+6D0h+var_6A8], rax
0x180066c0d  lea     rax, [rsp+6D0h+var_680]
0x180066c12  mov     [rsp+6D0h+var_6B0], rax
0x180066c17  lea     rdx, byte_1800C4367
0x180066c1e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180066c23  movups  xmm0, cs:EVENT_TERMINAL_DOCONNECT_TOOLONG
0x180066c2a  movdqu  xmmword ptr [rsp+6D0h+var_680.Id], xmm0
0x180066c30  lea     rax, aPtrterminaltmp_1; "ptrTerminalTmp->DoConnect"
0x180066c37  mov     [rsp+6D0h+var_6A8], rax; char *
0x180066c3c  lea     rax, [rsp+6D0h+var_680]
0x180066c41  mov     [rsp+6D0h+var_6B0], rax; struct _EVENT_DESCRIPTOR
0x180066c46  mov     r9, rsi; struct ITSSession *
0x180066c49  mov     r8d, [rsi+6D0h]; int
0x180066c50  mov     rdx, r12; struct _GUID *
0x180066c53  lea     rcx, [rbp+5D0h+Parameter]; Parameter
0x180066c57  call    ??0CTSTerminalOpsMonitor@@QEAA@PEAU_GUID@@JPEAUITSSession@@U_EVENT_DESCRIPTOR@@PEBDK@Z; CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(_GUID *,long,ITSSession *,_EVENT_DESCRIPTOR,char const *,ulong)
0x180066c5c  nop
0x180066c5d  mov     rax, [rbx]
0x180066c60  mov     rdi, [rax+20h]
0x180066c64  call    cs:__imp_GetCurrentProcessId
0x180066c6a  mov     dword ptr [rsp+6D0h+var_6B0], eax
0x180066c6e  mov     r9, [rsi+1940h]
0x180066c75  mov     r8, qword ptr [rbp+5D0h+var_650]
0x180066c79  lea     rdx, [rbp+5D0h+var_590]
0x180066c7d  mov     rcx, rbx
0x180066c80  mov     rax, rdi
0x180066c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c88  mov     edi, eax
0x180066c8a  test    eax, eax
0x180066c8c  jns     short loc_180066D04
0x180066c8e  mov     eax, cs:dword_1800DA020
0x180066c94  cmp     eax, 3
0x180066c97  jbe     short loc_180066CF6
0x180066c99  lea     rax, aConnecttermina_0; "ConnectTerminal"
0x180066ca0  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x180066ca5  mov     [rsp+6D0h+var_670], edi
0x180066ca9  lea     rax, aTerminalDoconn; "Terminal->DoConnect"
0x180066cb0  mov     [rsp+6D0h+var_690], rax
0x180066cb5  lea     rax, aWarningHresult; "Warning HResult failed"
0x180066cbc  mov     qword ptr [rsp+6D0h+var_688.LowPart], rax
0x180066cc1  lea     rax, [rsp+6D0h+var_680]
0x180066cc6  mov     [rsp+6D0h+var_698], rax
0x180066ccb  lea     rax, [rsp+6D0h+var_670]
0x180066cd0  mov     qword ptr [rsp+6D0h+var_6A0], rax
0x180066cd5  lea     rax, [rsp+6D0h+var_690]
0x180066cda  mov     [rsp+6D0h+var_6A8], rax
0x180066cdf  lea     rax, [rsp+6D0h+var_688]
0x180066ce4  mov     [rsp+6D0h+var_6B0], rax
0x180066ce9  lea     rdx, qword_1800C4328
0x180066cf0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180066cf5  nop
0x180066cf6  lea     rcx, [rbp+5D0h+Parameter]; this
0x180066cfa  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x180066cff  jmp     loc_180067280
0x180066d04  lea     rcx, [rbp+5D0h+Parameter]; this
0x180066d08  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x180066d0d  mov     rdi, [rsi+1718h]
0x180066d14  mov     rcx, rdi; pSecurityDescriptor
0x180066d17  call    cs:__imp_GetSecurityDescriptorLength
0x180066d1d  mov     rcx, [rbx]
0x180066d20  mov     r9, [rcx+0C0h]
0x180066d27  mov     r8d, eax
0x180066d2a  mov     rdx, rdi
0x180066d2d  mov     rcx, rbx
0x180066d30  mov     rax, r9
0x180066d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d38  mov     r15d, 1
0x180066d3e  mov     [rsp+6D0h+var_660], r15d
0x180066d43  mov     rcx, [rsp+6D0h+Resource]; Resource
0x180066d48  cmp     [rcx+60h], r13d
0x180066d4c  jz      short loc_180066D57
0x180066d4e  mov     dl, r15b; Wait
0x180066d51  call    cs:__imp_RtlAcquireResourceExclusive
0x180066d57  mov     edx, 2
0x180066d5c  mov     rcx, r14
0x180066d5f  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x180066d64  mov     edi, eax
0x180066d66  test    eax, eax
0x180066d68  js      loc_180066AE5
0x180066d6e  cmp     eax, r15d
0x180066d71  jz      loc_180066B0B
0x180066d77  mov     rcx, [rsi+718h]
0x180066d7e  test    rcx, rcx
0x180066d81  jnz     short loc_180066DB1
0x180066d83  mov     eax, cs:dword_1800DA020
0x180066d89  cmp     eax, 2
0x180066d8c  jbe     loc_180066AC8
0x180066d92  movsxd  rax, dword ptr [rsi+6D0h]
0x180066d99  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x180066d9e  lea     rax, aSessionHasNoTe; "Session has no terminal (ptrTerminal), "...
0x180066da5  lea     rdx, qword_1800C42F8
0x180066dac  jmp     loc_180066B9D
0x180066db1  mov     rax, [rcx]
0x180066db4  mov     rdx, r12
0x180066db7  mov     rax, [rax+0D8h]
0x180066dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066dc3  mov     rdx, r12
0x180066dc6  mov     ecx, 2
0x180066dcb  call    cs:__imp_EtwEventActivityIdControl
0x180066dd1  cmp     [rbp+5D0h+var_474], r15d
0x180066dd8  jnz     loc_180066E8A
0x180066dde  mov     [rsp+6D0h+var_690], r13
0x180066de3  lea     rcx, [rsp+6D0h+var_690]; struct CGpuManager **
0x180066de8  call    ?GetInstanceOfGpuManager@CGpuManager@@SAJPEAPEAV1@@Z; CGpuManager::GetInstanceOfGpuManager(CGpuManager * *)
0x180066ded  test    eax, eax
0x180066def  js      loc_180066E80
0x180066df5  mov     rcx, [rsp+6D0h+var_690]; this
0x180066dfa  cmp     [rcx+640h], r13d
0x180066e01  jz      short loc_180066E80
0x180066e03  mov     qword ptr [rsp+6D0h+var_688.LowPart], r13
0x180066e08  lea     r8, [rsp+6D0h+var_688]; struct _LUID *
0x180066e0d  mov     rdx, rsi; struct ITSSessionPrivate *
0x180066e10  call    ?LoadBalanceSessionToGpu@CGpuManager@@QEAAJPEAVITSSessionPrivate@@PEAU_LUID@@@Z; CGpuManager::LoadBalanceSessionToGpu(ITSSessionPrivate *,_LUID *)
0x180066e15  mov     ecx, eax
0x180066e17  test    eax, eax
0x180066e19  js      short loc_180066E30
0x180066e1b  mov     [rbp+5D0h+var_450], r15d
0x180066e22  mov     rax, qword ptr [rsp+6D0h+var_688.LowPart]
0x180066e27  mov     [rbp+5D0h+var_44C], rax
0x180066e2e  jmp     short loc_180066E80
0x180066e30  mov     edx, [rsi+6D0h]
0x180066e36  mov     eax, cs:dword_1800DA020
0x180066e3c  cmp     eax, 5
0x180066e3f  jbe     short loc_180066E80
0x180066e41  mov     [rsp+6D0h+var_670], ecx
0x180066e45  mov     [rsp+6D0h+var_688.LowPart], edx
0x180066e49  lea     rax, aGpuAssignmentT; "GPU assignment to session failed"
0x180066e50  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x180066e55  lea     rax, [rsp+6D0h+var_670]
  ... truncated ...
```
