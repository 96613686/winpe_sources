# CTSSession::ConnectTerminal(void)

- ea: `0x18006a5f0`
- end: `0x18006b01e`
- name: `?ConnectTerminal@CTSSession@@UEAAJXZ`
- size: `2606`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `0`
- callee_count: `36`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b90`
- `0x1800077a0`
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
- `0x1800124b4`
- `0x18001266c`
- `0x1800129d0`
- `0x180012cf8`
- `0x180014b20`
- `0x180022030`
- `0x1800261f8`
- `0x180026238`
- `0x1800266bc`
- `0x180026748`
- `0x180026c8c`
- `0x18002772c`
- `0x1800288ac`
- `0x180029f3c`
- `0x18002ae18`
- `0x18002dfb0`
- `0x1800367c0`
- `0x18004e850`
- `0x18004f354`
- `0x18006a5f0`
- `0x18006e474`
- `0x18007f1c4`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18006aa3d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006aeec`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006aa3d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006aeec`
- `ntdll!EtwEventActivityIdControl` at `0x18006aabd`
- `ntdll!EtwEventActivityIdControl` at `0x18006aabd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006a944`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006a944`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006ac45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006ac78`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006ac45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006ac78`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006a9fd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006a9fd`

## string_xrefs

- `0x18006a86f`: `Session has no temp terminal (ptrTerminalTmp), not connecting terminal`

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
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v58 = (CGpuManager *)"ConnectTerminal";
      v61[0] = v2;
      v59 = (struct _LUID)"InitializeNotifyInfo";
      *(_QWORD *)&v60.Id = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1800DF020,
        (unsigned int)qword_1800C9580,
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
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      *(_QWORD *)&v60.Id = *((int *)this + 436);
      v58 = v6;
      v59 = (struct _LUID)"Session in disconnected state, not connecting terminal.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v7,
        (unsigned int)byte_1800C9549,
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
    if ( (unsigned int)dword_1800DF020 <= 2 )
    {
LABEL_10:
      v2 = -2147022646;
LABEL_66:
      CTSSession::LogFailedTransition(this, 2, (unsigned int)v2);
      goto LABEL_67;
    }
    *(_QWORD *)&v60.Id = *((int *)this + 436);
    v16 = "Session has no temp terminal (ptrTerminalTmp), not connecting terminal";
    v17 = (__int64 *)byte_1800C9519;
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
  if ( v18 < 0 && (unsigned int)dword_1800DF020 > 3 )
  {
    v61[0] = v18;
    *(_QWORD *)&v60.Id = "EventDispatch->OnCsrInitialized failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DF020,
      (unsigned int)&byte_1800C94EF,
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
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      *(_QWORD *)&v60.Id = "ConnectTerminal";
      v61[0] = v2;
      v58 = (CGpuManager *)"Terminal->DoConnect";
      v59 = (struct _LUID)"Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v23,
        (unsigned int)qword_1800C94B0,
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
    if ( (unsigned int)dword_1800DF020 <= 2 )
      goto LABEL_10;
    *(_QWORD *)&v60.Id = *((int *)this + 436);
    v16 = "Session has no terminal (ptrTerminal), not connecting terminal";
    v17 = qword_1800C9480;
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
        if ( (unsigned int)dword_1800DF020 > 5 )
        {
          v61[0] = v29;
          v59.LowPart = v32;
          *(_QWORD *)&v60.Id = "GPU assignment to session failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v29,
            (unsigned int)byte_1800C944D,
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
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      *(_QWORD *)&v60.Id = HIDWORD(v71);
      v58 = (CGpuManager *)(unsigned int)v71;
      v59 = (struct _LUID)"Terminal returned invalid number of monitors, resetting to default (NumMonitors=1, PrimaryMonitor=0)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v33,
        (unsigned int)byte_1800C9409,
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
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    *(_QWORD *)&v60.Id = v37 - TickCount64;
    v58 = (CGpuManager *)*((int *)this + 436);
    v59 = (struct _LUID)"SendConnectMsg";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      dword_1800DF020,
      (unsigned int)byte_1800C93B9,
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
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      *(_QWORD *)&v60.Id = "ConnectTerminal";
      v59.LowPart = v2;
      v58 = (CGpuManager *)"CsrPipe->SendConnectMsg";
      *(_QWORD *)v61 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v40,
        (unsigned int)word_1800C937A,
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
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      *(_QWORD *)&v60.Id = "ConnectTerminal";
      v59.LowPart = v2;
      v58 = (CGpuManager *)"Terminal->Connected";
      *(_QWORD *)v61 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v43,
        (unsigned int)byte_1800C933B,
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
  if ( v46 < 0 && (unsigned int)dword_1800DF020 > 3 )
  {
    *(_QWORD *)&v60.Id = "ConnectTerminal";
    v59.LowPart = v46;
    v58 = (CGpuManager *)"SetTimeZone";
    *(_QWORD *)v61 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_1800DF020,
      (unsigned int)&dword_1800C92FC,
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v59.LowPart = v2;
      *(_QWORD *)&v60.Id = "EventDispatch->OnCsrInitialized failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v51,
        (unsigned int)word_1800C92D2,
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
0x18006a5f0  push    rbp
0x18006a5f2  push    rbx
0x18006a5f3  push    rsi
0x18006a5f4  push    rdi
0x18006a5f5  push    r12
0x18006a5f7  push    r13
0x18006a5f9  push    r14
0x18006a5fb  push    r15
0x18006a5fd  lea     rbp, [rsp-598h]
0x18006a605  sub     rsp, 698h
0x18006a60c  mov     rax, cs:__security_cookie
0x18006a613  xor     rax, rsp
0x18006a616  mov     [rbp+5D0h+var_50], rax
0x18006a61d  mov     rsi, rcx
0x18006a620  mov     ebx, 480h
0x18006a625  mov     r8d, ebx; Size
0x18006a628  xor     edx, edx; Val
0x18006a62a  lea     rcx, [rbp+5D0h+var_590]; void *
0x18006a62e  call    memset_0
0x18006a633  xor     r13d, r13d
0x18006a636  mov     [rsp+6D0h+var_658], r13
0x18006a63b  xorps   xmm0, xmm0
0x18006a63e  xor     eax, eax
0x18006a640  movups  [rbp+5D0h+var_650], xmm0
0x18006a644  movups  [rbp+5D0h+var_640], xmm0
0x18006a648  movups  [rbp+5D0h+var_630], xmm0
0x18006a64c  mov     [rbp+5D0h+var_620], rax
0x18006a650  lea     r12, [rsi+0C88h]
0x18006a657  mov     rdx, r12; struct _GUID *
0x18006a65a  lea     rcx, [rbp+5D0h+var_5B0]; this
0x18006a65e  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x18006a663  nop
0x18006a664  mov     r8, rsi; struct ITSSession *
0x18006a667  lea     rdx, aCtssessionConn_6; "CTSSession::ConnectTerminal"
0x18006a66e  lea     rcx, [rbp+5D0h+var_110]; this
0x18006a675  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x18006a67a  nop
0x18006a67b  mov     qword ptr [rbp+5D0h+var_650], r13
0x18006a67f  mov     r8d, ebx; Size
0x18006a682  xor     edx, edx; Val
0x18006a684  lea     rcx, [rbp+5D0h+var_590]; void *
0x18006a688  call    memset_0
0x18006a68d  lea     rdx, [rsi+740h]; struct CResource *
0x18006a694  lea     rcx, [rsp+6D0h+Resource]; this
0x18006a699  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18006a69e  nop
0x18006a69f  cmp     [rsi+0CACh], r13d
0x18006a6a6  jz      short loc_18006A6BE
0x18006a6a8  lea     edx, [r13+3]; unsigned int
0x18006a6ac  mov     r9d, 20Eh; unsigned int
0x18006a6b2  lea     r8d, [r13+2]; unsigned int
0x18006a6b6  mov     rcx, rsi; this
0x18006a6b9  call    ?OnBrokenConnectionEx@CTSSession@@AEAAJKKK@Z; CTSSession::OnBrokenConnectionEx(ulong,ulong,ulong)
0x18006a6be  lea     rdx, [rbp+5D0h+var_650]; struct __PTSSessInfo *
0x18006a6c2  mov     rcx, rsi; this
0x18006a6c5  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x18006a6ca  mov     edi, eax
0x18006a6cc  test    eax, eax
0x18006a6ce  jns     short loc_18006A740
0x18006a6d0  mov     ecx, cs:dword_1800DF020
0x18006a6d6  cmp     ecx, 3
0x18006a6d9  jbe     loc_18006AF8A
0x18006a6df  lea     rax, aConnecttermina_0; "ConnectTerminal"
0x18006a6e6  mov     [rsp+6D0h+var_690], rax
0x18006a6eb  mov     [rsp+6D0h+var_670], edi
0x18006a6ef  lea     rax, aInitializenoti; "InitializeNotifyInfo"
0x18006a6f6  mov     qword ptr [rsp+6D0h+var_688.LowPart], rax
0x18006a6fb  lea     rax, aWarningHresult; "Warning HResult failed"
0x18006a702  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x18006a707  lea     rax, [rsp+6D0h+var_690]
0x18006a70c  mov     [rsp+6D0h+var_698], rax
0x18006a711  lea     rax, [rsp+6D0h+var_670]
0x18006a716  mov     qword ptr [rsp+6D0h+var_6A0], rax
0x18006a71b  lea     rax, [rsp+6D0h+var_688]
0x18006a720  mov     [rsp+6D0h+var_6A8], rax
0x18006a725  lea     rax, [rsp+6D0h+var_680]
0x18006a72a  lea     rdx, qword_1800C9580
0x18006a731  mov     [rsp+6D0h+var_6B0], rax
0x18006a736  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006a73b  jmp     loc_18006AF8A
0x18006a740  lea     r14, [rsi+0CB8h]
0x18006a747  movsxd  r15, dword ptr [r14]
0x18006a74a  mov     ecx, r15d
0x18006a74d  call    IsDisconnectedState
0x18006a752  test    eax, eax
0x18006a754  jz      short loc_18006A7B2
0x18006a756  mov     eax, cs:dword_1800DF020
0x18006a75c  cmp     eax, 3
0x18006a75f  jbe     short loc_18006A7A8
0x18006a761  movsxd  rax, dword ptr [rsi+6D0h]
0x18006a768  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x18006a76d  mov     [rsp+6D0h+var_690], r15
0x18006a772  lea     rax, aSessionInDisco; "Session in disconnected state, not conn"...
0x18006a779  mov     qword ptr [rsp+6D0h+var_688.LowPart], rax
0x18006a77e  lea     rax, [rsp+6D0h+var_680]
0x18006a783  mov     qword ptr [rsp+6D0h+var_6A0], rax
0x18006a788  lea     rax, [rsp+6D0h+var_690]
0x18006a78d  mov     [rsp+6D0h+var_6A8], rax
0x18006a792  lea     rax, [rsp+6D0h+var_688]
0x18006a797  mov     [rsp+6D0h+var_6B0], rax
0x18006a79c  lea     rdx, byte_1800C9549
0x18006a7a3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18006a7a8  mov     edi, 800708CAh
0x18006a7ad  jmp     loc_18006AF8A
0x18006a7b2  mov     edx, 2
0x18006a7b7  mov     rcx, r14
0x18006a7ba  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x18006a7bf  mov     edi, eax
0x18006a7c1  test    eax, eax
0x18006a7c3  jns     short loc_18006A7E6
0x18006a7c5  mov     ecx, [r14]
0x18006a7c8  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18006a7cd  mov     r8, rax
0x18006a7d0  lea     rdx, aInvalidStateFo_4; "invalid state for EvCsrInitialized, sta"...
0x18006a7d7  mov     ecx, 8; int
0x18006a7dc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006a7e1  jmp     loc_18006AF8A
0x18006a7e6  cmp     eax, 1
0x18006a7e9  jnz     short loc_18006A82F
0x18006a7eb  mov     ecx, [r14]; int
0x18006a7ee  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x18006a7f3  mov     r9, rax
0x18006a7f6  mov     ecx, 2; int
0x18006a7fb  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x18006a800  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006a807  jz      loc_18006AF9A
0x18006a80d  mov     [rsp+6D0h+var_6B0], rax
0x18006a812  mov     r8d, [rsi+6D0h]
0x18006a819  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x18006a820  mov     ecx, 2; int
0x18006a825  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006a82a  jmp     loc_18006AF9A
0x18006a82f  mov     rdx, [rsi+718h]
0x18006a836  lea     rcx, [rsp+6D0h+var_658]
0x18006a83b  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18006a840  lea     rcx, [rsp+6D0h+Resource]; this
0x18006a845  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006a84a  mov     rbx, [rsp+6D0h+var_658]
0x18006a84f  test    rbx, rbx
0x18006a852  jnz     short loc_18006A8A0
0x18006a854  mov     eax, cs:dword_1800DF020
0x18006a85a  cmp     eax, 2
0x18006a85d  jbe     loc_18006A7A8
0x18006a863  movsxd  rax, dword ptr [rsi+6D0h]
0x18006a86a  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x18006a86f  lea     rax, aSessionHasNoTe_0; "Session has no temp terminal (ptrTermin"...
0x18006a876  lea     rdx, byte_1800C9519
0x18006a87d  mov     [rsp+6D0h+var_690], rax
0x18006a882  lea     rax, [rsp+6D0h+var_680]
0x18006a887  mov     [rsp+6D0h+var_6A8], rax
0x18006a88c  lea     rax, [rsp+6D0h+var_690]
0x18006a891  mov     [rsp+6D0h+var_6B0], rax
0x18006a896  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18006a89b  jmp     loc_18006A7A8
0x18006a8a0  mov     rcx, [rsi+720h]
0x18006a8a7  add     rcx, 728h
0x18006a8ae  mov     rax, [rcx]
0x18006a8b1  mov     r9, rbx
0x18006a8b4  mov     r8d, r15d
0x18006a8b7  lea     rdx, [rbp+5D0h+var_650]
0x18006a8bb  mov     rax, [rax+20h]
0x18006a8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8c4  lea     rdx, aEventdispatchO_3; "EventDispatch->OnCsrInitialized failed"
0x18006a8cb  test    eax, eax
0x18006a8cd  jns     short loc_18006A903
0x18006a8cf  mov     ecx, cs:dword_1800DF020
0x18006a8d5  cmp     ecx, 3
0x18006a8d8  jbe     short loc_18006A903
0x18006a8da  mov     [rsp+6D0h+var_670], eax
0x18006a8de  mov     qword ptr [rsp+6D0h+var_680.Id], rdx
0x18006a8e3  lea     rax, [rsp+6D0h+var_670]
0x18006a8e8  mov     [rsp+6D0h+var_6A8], rax
0x18006a8ed  lea     rax, [rsp+6D0h+var_680]
0x18006a8f2  mov     [rsp+6D0h+var_6B0], rax
0x18006a8f7  lea     rdx, byte_1800C94EF
0x18006a8fe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006a903  movups  xmm0, cs:EVENT_TERMINAL_DOCONNECT_TOOLONG
0x18006a90a  movdqu  xmmword ptr [rsp+6D0h+var_680.Id], xmm0
0x18006a910  lea     rax, aPtrterminaltmp_1; "ptrTerminalTmp->DoConnect"
0x18006a917  mov     [rsp+6D0h+var_6A8], rax; char *
0x18006a91c  lea     rax, [rsp+6D0h+var_680]
0x18006a921  mov     [rsp+6D0h+var_6B0], rax; struct _EVENT_DESCRIPTOR
0x18006a926  mov     r9, rsi; struct ITSSession *
0x18006a929  mov     r8d, [rsi+6D0h]; int
0x18006a930  mov     rdx, r12; struct _GUID *
0x18006a933  lea     rcx, [rbp+5D0h+Parameter]; Parameter
0x18006a937  call    ??0CTSTerminalOpsMonitor@@QEAA@PEAU_GUID@@JPEAUITSSession@@U_EVENT_DESCRIPTOR@@PEBDK@Z; CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(_GUID *,long,ITSSession *,_EVENT_DESCRIPTOR,char const *,ulong)
0x18006a93c  nop
0x18006a93d  mov     rax, [rbx]
0x18006a940  mov     rdi, [rax+20h]
0x18006a944  call    cs:__imp_GetCurrentProcessId
0x18006a94b  nop     dword ptr [rax+rax+00h]
0x18006a950  mov     dword ptr [rsp+6D0h+var_6B0], eax
0x18006a954  mov     r9, [rsi+1940h]
0x18006a95b  mov     r8, qword ptr [rbp+5D0h+var_650]
0x18006a95f  lea     rdx, [rbp+5D0h+var_590]
0x18006a963  mov     rcx, rbx
0x18006a966  mov     rax, rdi
0x18006a969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a96e  mov     edi, eax
0x18006a970  test    eax, eax
0x18006a972  jns     short loc_18006A9EA
0x18006a974  mov     eax, cs:dword_1800DF020
0x18006a97a  cmp     eax, 3
0x18006a97d  jbe     short loc_18006A9DC
0x18006a97f  lea     rax, aConnecttermina_0; "ConnectTerminal"
0x18006a986  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x18006a98b  mov     [rsp+6D0h+var_670], edi
0x18006a98f  lea     rax, aTerminalDoconn; "Terminal->DoConnect"
0x18006a996  mov     [rsp+6D0h+var_690], rax
0x18006a99b  lea     rax, aWarningHresult; "Warning HResult failed"
0x18006a9a2  mov     qword ptr [rsp+6D0h+var_688.LowPart], rax
0x18006a9a7  lea     rax, [rsp+6D0h+var_680]
0x18006a9ac  mov     [rsp+6D0h+var_698], rax
0x18006a9b1  lea     rax, [rsp+6D0h+var_670]
0x18006a9b6  mov     qword ptr [rsp+6D0h+var_6A0], rax
0x18006a9bb  lea     rax, [rsp+6D0h+var_690]
0x18006a9c0  mov     [rsp+6D0h+var_6A8], rax
0x18006a9c5  lea     rax, [rsp+6D0h+var_688]
0x18006a9ca  mov     [rsp+6D0h+var_6B0], rax
0x18006a9cf  lea     rdx, qword_1800C94B0
0x18006a9d6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006a9db  nop
0x18006a9dc  lea     rcx, [rbp+5D0h+Parameter]; this
0x18006a9e0  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006a9e5  jmp     loc_18006AF8A
0x18006a9ea  lea     rcx, [rbp+5D0h+Parameter]; this
0x18006a9ee  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006a9f3  mov     rdi, [rsi+1718h]
0x18006a9fa  mov     rcx, rdi; pSecurityDescriptor
0x18006a9fd  call    cs:__imp_GetSecurityDescriptorLength
0x18006aa04  nop     dword ptr [rax+rax+00h]
0x18006aa09  mov     rcx, [rbx]
0x18006aa0c  mov     r9, [rcx+0C0h]
0x18006aa13  mov     r8d, eax
0x18006aa16  mov     rdx, rdi
0x18006aa19  mov     rcx, rbx
0x18006aa1c  mov     rax, r9
0x18006aa1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa24  mov     r15d, 1
0x18006aa2a  mov     [rsp+6D0h+var_660], r15d
0x18006aa2f  mov     rcx, [rsp+6D0h+Resource]; Resource
0x18006aa34  cmp     [rcx+60h], r13d
0x18006aa38  jz      short loc_18006AA49
0x18006aa3a  mov     dl, r15b; Wait
0x18006aa3d  call    cs:__imp_RtlAcquireResourceExclusive
0x18006aa44  nop     dword ptr [rax+rax+00h]
0x18006aa49  mov     edx, 2
0x18006aa4e  mov     rcx, r14
0x18006aa51  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x18006aa56  mov     edi, eax
0x18006aa58  test    eax, eax
0x18006aa5a  js      loc_18006A7C5
0x18006aa60  cmp     eax, r15d
0x18006aa63  jz      loc_18006A7EB
0x18006aa69  mov     rcx, [rsi+718h]
0x18006aa70  test    rcx, rcx
0x18006aa73  jnz     short loc_18006AAA3
0x18006aa75  mov     eax, cs:dword_1800DF020
0x18006aa7b  cmp     eax, 2
0x18006aa7e  jbe     loc_18006A7A8
0x18006aa84  movsxd  rax, dword ptr [rsi+6D0h]
0x18006aa8b  mov     qword ptr [rsp+6D0h+var_680.Id], rax
0x18006aa90  lea     rax, aSessionHasNoTe; "Session has no terminal (ptrTerminal), "...
0x18006aa97  lea     rdx, qword_1800C9480
0x18006aa9e  jmp     loc_18006A87D
0x18006aaa3  mov     rax, [rcx]
0x18006aaa6  mov     rdx, r12
0x18006aaa9  mov     rax, [rax+0D8h]
0x18006aab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aab5  mov     rdx, r12
0x18006aab8  mov     ecx, 2
0x18006aabd  call    cs:__imp_EtwEventActivityIdControl
0x18006aac4  nop     dword ptr [rax+rax+00h]
0x18006aac9  cmp     [rbp+5D0h+var_474], r15d
0x18006aad0  jnz     loc_18006AB82
0x18006aad6  mov     [rsp+6D0h+var_690], r13
0x18006aadb  lea     rcx, [rsp+6D0h+var_690]; struct CGpuManager **
0x18006aae0  call    ?GetInstanceOfGpuManager@CGpuManager@@SAJPEAPEAV1@@Z; CGpuManager::GetInstanceOfGpuManager(CGpuManager * *)
0x18006aae5  test    eax, eax
0x18006aae7  js      loc_18006AB78
0x18006aaed  mov     rcx, [rsp+6D0h+var_690]; this
0x18006aaf2  cmp     [rcx+640h], r13d
0x18006aaf9  jz      short loc_18006AB78
0x18006aafb  mov     qword ptr [rsp+6D0h+var_688.LowPart], r13
0x18006ab00  lea     r8, [rsp+6D0h+var_688]; struct _LUID *
0x18006ab05  mov     rdx, rsi; struct ITSSessionPrivate *
0x18006ab08  call    ?LoadBalanceSessionToGpu@CGpuManager@@QEAAJPEAVITSSessionPrivate@@PEAU_LUID@@@Z; CGpuManager::LoadBalanceSessionToGpu(ITSSessionPrivate *,_LUID *)
0x18006ab0d  mov     ecx, eax
0x18006ab0f  test    eax, eax
0x18006ab11  js      short loc_18006AB28
0x18006ab13  mov     [rbp+5D0h+var_450], r15d
0x18006ab1a  mov     rax, qword ptr [rsp+6D0h+var_688.LowPart]
0x18006ab1f  mov     [rbp+5D0h+var_44C], rax
0x18006ab26  jmp     short loc_18006AB78
0x18006ab28  mov     edx, [rsi+6D0h]
0x18006ab2e  mov     eax, cs:dword_1800DF020
0x18006ab34  cmp     eax, 5
0x18006ab37  jbe     short loc_18006AB78
0x18006ab39  mov     [rsp+6D0h+var_670], ecx
  ... truncated ...
```
