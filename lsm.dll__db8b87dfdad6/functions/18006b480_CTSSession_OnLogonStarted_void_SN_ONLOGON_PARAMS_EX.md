# CTSSession::OnLogonStarted(void *,_SN_ONLOGON_PARAMS_EX *)

- ea: `0x18006b480`
- end: `0x18006bba9`
- name: `?OnLogonStarted@CTSSession@@UEAAJPEAXPEAU_SN_ONLOGON_PARAMS_EX@@@Z`
- size: `1833`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, void *, struct _SN_ONLOGON_PARAMS_EX *)`
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

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
- `0x180009e28`
- `0x18000a4d0`
- `0x18000aad4`
- `0x18000fa38`
- `0x180010fb0`
- `0x180017150`
- `0x1800180ec`
- `0x1800189d4`
- `0x18001ce00`
- `0x18001f27c`
- `0x18001fd20`
- `0x180024884`
- `0x180025600`
- `0x180028784`
- `0x180028bbc`
- `0x18002bf6c`
- `0x18002f624`
- `0x1800343e4`
- `0x180034644`
- `0x18004b460`
- `0x18004b86c`
- `0x18005b590`
- `0x18006a6d0`
- `0x18006b480`
- `0x18006caec`
- `0x18006d910`
- `0x180094040`
- `0x180097010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18006b872`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006b872`
- `ntdll!NtQuerySystemTime` at `0x18006b930`
- `ntdll!NtQuerySystemTime` at `0x18006b930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bb31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bb31`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b6e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b70d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b6e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b70d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006b940`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006b940`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006b79a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006b79a`

## string_xrefs

- `0x18006b697`: `this->SecurityDescriptor.AddUserAce failed: 0x%x in %s`
- `0x18006b64e`: `GetUserSid failed: 0x%x in %s`
- `0x18006b673`: `this->ConfigurePerSessionSecurity failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTSSession::OnLogonStarted(CTSSession *this, void *a2, struct _SN_ONLOGON_PARAMS_EX *a3)
{
  struct ITerminal *v6; // rbx
  struct _GUID *v7; // r13
  int v8; // eax
  int v9; // edi
  int *v10; // r14
  int v11; // eax
  const char *StateName; // rax
  const unsigned __int16 *LsmEventName; // rax
  CUserName *v14; // rax
  struct IUserName **v15; // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  ULONGLONG TickCount64; // r15
  ULONGLONG v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  void *v24; // rbx
  DWORD SecurityDescriptorLength; // eax
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  char v30; // r15
  unsigned int v31; // r12d
  unsigned int v32; // r13d
  __int64 *v33; // rdi
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // rcx
  int v37; // eax
  int v38; // eax
  struct _EVENT_DESCRIPTOR *v40; // [rsp+20h] [rbp-E0h]
  __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  struct ITerminal *v43; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v45[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 Buf1; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-50h] BYREF
  PRTL_RESOURCE Resource; // [rsp+B8h] [rbp-48h] BYREF
  int v49; // [rsp+C0h] [rbp-40h]
  __int64 v50; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v51; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v52; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v53; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v54; // [rsp+E8h] [rbp-18h] BYREF
  __int128 Parameter; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v56[4]; // [rsp+100h] [rbp+0h]
  __int128 v57; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v58[6]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v59[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v60[192]; // [rsp+170h] [rbp+70h] BYREF

  pv = 0;
  v47 = 0;
  v6 = 0;
  v43 = 0;
  v7 = (struct _GUID *)((char *)this + 3208);
  CAutoSetActivityId::CAutoSetActivityId((CAutoSetActivityId *)v59, (struct _GUID *)((char *)this + 3208));
  CTSSessionTrace::CTSSessionTrace((CTSSessionTrace *)v60, "CTSSession::OnLogonStarted", this);
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)&Resource, (struct _RTL_RESOURCE *)((char *)this + 1856));
  v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 199) + 24LL))(
         *((_QWORD *)this + 199),
         &IID_ITSSession,
         &v47);
  v9 = v8;
  if ( v8 < 0 )
  {
    _DbgPrintMessage(8, "QI( ITSSession ) failed: 0x%x in %s", (unsigned int)v8, "CTSSession::OnLogonStarted");
LABEL_36:
    v15 = (struct IUserName **)((char *)this + 5928);
    goto LABEL_37;
  }
  v10 = (int *)((char *)this + 3256);
  v11 = CTSSession::CState::CheckState((char *)this + 3256, 5);
  v9 = v11;
  if ( v11 < 0 )
  {
    StateName = (const char *)CUtils::GetStateName((unsigned int)*v10);
    _DbgPrintMessage(8, "invalid state for EvLogon, state is: \"%s\"", StateName);
    goto LABEL_36;
  }
  if ( v11 == 1 )
  {
    GetLsmStateName(*v10);
    LsmEventName = GetLsmEventName(5);
    if ( (g_DebugTraceComponent & 4) != 0 )
    {
      HIDWORD(v40) = HIDWORD(LsmEventName);
      _DbgPrintMessage(2, "No change to session %d state %ws with event %ws", *((unsigned int *)this + 436));
    }
    goto LABEL_39;
  }
  v14 = (CUserName *)operator new(0xA88u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)&Buf1 = v14;
  if ( v14 )
    v14 = CUserName::CUserName(v14);
  v15 = (struct IUserName **)((char *)this + 5928);
  SmartPtr<IUserName>::operator=((char *)this + 5928, v14);
  if ( !*((_QWORD *)this + 741) )
  {
    v9 = -2147024882;
LABEL_37:
    SmartPtr<IUserName>::operator=(v15, 0);
    goto LABEL_56;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, void *, __int64))(**((_QWORD **)this + 741) + 24LL))(
          *((_QWORD *)this + 741),
          a2,
          1);
  v9 = v16;
  if ( v16 < 0 )
  {
    _DbgPrintMessage(8, "UserName->Initialize failed: 0x%x in %s", (unsigned int)v16, "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  v17 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)*v15 + 72LL))(*v15, &pv);
  v9 = v17;
  if ( v17 < 0 )
  {
    _DbgPrintMessage(8, "GetUserSid failed: 0x%x in %s", (unsigned int)v17, "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  v18 = CTSSession::ConfigurePerSessionSecurity(*((_DWORD *)this + 436), pv);
  v9 = v18;
  if ( v18 < 0 )
  {
    _DbgPrintMessage(
      8,
      "this->ConfigurePerSessionSecurity failed: 0x%x in %s",
      (unsigned int)v18,
      "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  v19 = CTSSessionSecurityDescriptor::AddUserAce((CTSSession *)((char *)this + 5872), *v15);
  v9 = v19;
  if ( v19 < 0 )
  {
    _DbgPrintMessage(
      8,
      "this->SecurityDescriptor.AddUserAce failed: 0x%x in %s",
      (unsigned int)v19,
      "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  if ( *((_QWORD *)this + 227) )
  {
    Buf1 = EVENT_TERMINAL_LOGON_TOOLONG;
    CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(
      (char *)&Parameter,
      v7,
      *((_DWORD *)this + 436),
      this,
      (struct _EVENT_DESCRIPTOR *)&Buf1,
      "pNewTerminal->LoggedOn");
    TickCount64 = GetTickCount64();
    v9 = (*(__int64 (__fastcall **)(_QWORD, struct IUserName *))(**((_QWORD **)this + 227) + 64LL))(
           *((_QWORD *)this + 227),
           *v15);
    v21 = GetTickCount64();
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v44 = v21 - TickCount64;
      LODWORD(v41) = *((_DWORD *)this + 436);
      v45[0] = (const unsigned __int16 *)"ptrTerminal->LoggedOnStarted took this long";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)dword_1800DA020,
        (unsigned __int8 *)byte_1800C3F47,
        v22,
        v23,
        v45,
        (__int64)&v41,
        (__int64)&v44);
    }
    if ( v9 < 0 )
    {
      _DbgPrintMessage(
        8,
        "Terminal->LoggedOnStarted failed: 0x%x in %s",
        (unsigned int)v9,
        "CTSSession::OnLogonStarted");
LABEL_25:
      CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)&Parameter);
      goto LABEL_36;
    }
    v24 = (void *)*((_QWORD *)this + 739);
    SecurityDescriptorLength = GetSecurityDescriptorLength(v24);
    (*(void (__fastcall **)(_QWORD, void *, _QWORD))(**((_QWORD **)this + 227) + 192LL))(
      *((_QWORD *)this + 227),
      v24,
      SecurityDescriptorLength);
    v26 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 227) + 160LL))(
            *((_QWORD *)this + 227),
            (char *)this + 2116);
    v9 = v26;
    if ( v26 < 0 )
    {
      _DbgPrintMessage(
        8,
        "GetSessionInitialProgram failed: 0x%x in %s",
        (unsigned int)v26,
        "CTSSession::OnLogonStarted");
      goto LABEL_25;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl) )
    {
      Buf1 = *(_OWORD *)((char *)this + 5832);
      if ( !memcmp_0(&Buf1, TERMINAL_TYPE_AGENT, 0x10u) )
        CTSSession::SetIsolationConfigId(this, v27, v28, v29);
    }
    CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)&Parameter);
  }
  SmartPtr<ITerminal>::operator=((__int64 *)&v43, *((_QWORD *)this + 227));
  CAutoLock::Unlock((CAutoLock *)&Resource);
  v9 = CTSSession::SetTimeZone(this);
  v49 = 1;
  if ( LODWORD(Resource[1].Lock.DebugInfo) )
    RtlAcquireResourceExclusive(Resource, 1u);
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "SetTimeZone failed: 0x%x in %s", (unsigned int)v9, "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  v6 = v43;
LABEL_39:
  CTSSession::UpdateDomainUsernameString(this);
  Parameter = 0;
  *(_OWORD *)v56 = 0;
  v57 = 0;
  v58[0] = 0;
  v30 = 0;
  v9 = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)&Parameter);
  if ( v9 >= 0 )
  {
    if ( *((_DWORD *)a3 + 4) == 1 )
    {
      v30 = 1;
      _DbgPrintMessage(1, "This logon is an ARSO, PIN Reset, or Kiosk mode logon");
    }
    v31 = *v10;
    LODWORD(v40) = 6108;
    CTSSession::CState::ChangeState((char *)this + 3256, 5, (char *)&v57 + 8, v58, v40);
    v32 = *v10;
    v33 = (__int64 *)((char *)this + 1992);
    NtQuerySystemTime((PLARGE_INTEGER)this + 249);
    GetSystemTime((LPSYSTEMTIME)this + 128);
    if ( (unsigned int)dword_1800DA020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DA020, 0x400000000000LL) )
    {
      v45[0] = (const unsigned __int16 *)"Logon";
      v34 = *((_QWORD *)this + 247);
      v35 = *v33;
      v36 = *v33 - v34;
      v44 = v36 / 10000000;
      v41 = v36;
      v50 = v35;
      v51 = (__int64)this + 3208;
      v52 = (__int64)this + 2048;
      v53 = (__int64)this + 2016;
      v54 = v34;
      *(_QWORD *)&Buf1 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v36,
        (int)byte_1800C3EB5,
        v35,
        v34,
        (__int64)&Buf1,
        (__int64)&v54,
        &v53,
        &v52,
        &v51,
        (__int64)&v50,
        (__int64)&v41,
        (__int64)&v44,
        v45);
    }
    CAutoLock::Unlock((CAutoLock *)&Resource);
    v37 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL)
                                                                         + 56LL))(
            *((_QWORD *)this + 228) + 1832LL,
            &Parameter,
            v32,
            v31);
    v9 = v37;
    if ( v37 < 0 )
      _DbgPrintMessage(8, "EventDispatch->OnLogon failed: 0x%x", v37);
    CTSSession::PublishWNFNotification(this, 5u, v56[2]);
    if ( (_QWORD)Parameter )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Parameter + 16LL))(Parameter);
      *(_QWORD *)&Parameter = 0;
    }
    if ( (_QWORD)v57 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v57 + 16LL))(v57);
      *(_QWORD *)&v57 = 0;
    }
    v38 = CTSSession::SendSessionNotificationMsg(this, 0);
    if ( v38 < 0 )
      _DbgPrintMessage(8, "SendSessionNotificationMsg failed: 0x%x", v38);
  }
  if ( v6 )
  {
    CTSSession::LogSessionEvent(this, &EVENT_SESSION_LOGON, v6);
    if ( v30 )
    {
      CTSSession::LogSessionEvent(this, &EVENT_SESSION_LOCK_ON_LOGON, v6);
      CTSSession::OnDesktopLock(this);
    }
  }
LABEL_56:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v9 < 0 )
    CTSSession::LogFailedTransition(this, 5, (unsigned int)v9);
  CAutoLock::Unlock((CAutoLock *)&Resource);
  CTSSessionTrace::~CTSSessionTrace((CTSSessionTrace *)v60);
  CAutoSetActivityId::~CAutoSetActivityId((CAutoSetActivityId *)v59);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>((__int64 *)&v43);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v47);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006b480  mov     [rsp-8+arg_10], rbx
0x18006b485  push    rbp
0x18006b486  push    rsi
0x18006b487  push    rdi
0x18006b488  push    r12
0x18006b48a  push    r13
0x18006b48c  push    r14
0x18006b48e  push    r15
0x18006b490  lea     rbp, [rsp-140h]
0x18006b498  sub     rsp, 240h
0x18006b49f  mov     rax, cs:__security_cookie
0x18006b4a6  xor     rax, rsp
0x18006b4a9  mov     [rbp+170h+var_40], rax
0x18006b4b0  mov     r12, r8
0x18006b4b3  mov     r15, rdx
0x18006b4b6  mov     rsi, rcx
0x18006b4b9  mov     [rsp+270h+pv], 0
0x18006b4c2  mov     [rbp+170h+var_1C0], 0
0x18006b4ca  xor     ebx, ebx
0x18006b4cc  mov     [rbp+170h+var_1F0], rbx
0x18006b4d0  lea     r13, [rcx+0C88h]
0x18006b4d7  mov     rdx, r13; struct _GUID *
0x18006b4da  lea     rcx, [rbp+170h+var_120]; this
0x18006b4de  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x18006b4e3  nop
0x18006b4e4  mov     r8, rsi; struct ITSSession *
0x18006b4e7  lea     rdx, aCtssessionOnlo_1; "CTSSession::OnLogonStarted"
0x18006b4ee  lea     rcx, [rbp+170h+var_100]; this
0x18006b4f2  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x18006b4f7  nop
0x18006b4f8  lea     rdx, [rsi+740h]; struct CResource *
0x18006b4ff  lea     rcx, [rbp+170h+Resource]; this
0x18006b503  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18006b508  nop
0x18006b509  mov     rcx, [rsi+638h]
0x18006b510  mov     rax, [rcx]
0x18006b513  lea     r8, [rbp+170h+var_1C0]
0x18006b517  lea     rdx, IID_ITSSession
0x18006b51e  mov     rax, [rax+18h]
0x18006b522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b527  mov     edi, eax
0x18006b529  test    eax, eax
0x18006b52b  jns     short loc_18006B53C
0x18006b52d  mov     r8d, eax
0x18006b530  lea     rdx, aQiItssessionFa; "QI( ITSSession ) failed: 0x%x in %s"
0x18006b537  jmp     loc_18006B886
0x18006b53c  lea     r14, [rsi+0CB8h]
0x18006b543  mov     edx, 5
0x18006b548  mov     rcx, r14
0x18006b54b  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x18006b550  mov     edi, eax
0x18006b552  test    eax, eax
0x18006b554  jns     short loc_18006B577
0x18006b556  mov     ecx, [r14]
0x18006b559  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18006b55e  mov     r8, rax
0x18006b561  lea     rdx, aInvalidStateFo_2; "invalid state for EvLogon, state is: \""...
0x18006b568  mov     ecx, 8; int
0x18006b56d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b572  jmp     loc_18006B897
0x18006b577  cmp     eax, 1
0x18006b57a  jnz     short loc_18006B5C0
0x18006b57c  mov     ecx, [r14]; int
0x18006b57f  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x18006b584  mov     r9, rax
0x18006b587  mov     ecx, 5; int
0x18006b58c  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x18006b591  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006b598  jz      loc_18006B8B1
0x18006b59e  mov     [rsp+270h+var_250], rax
0x18006b5a3  mov     r8d, [rsi+6D0h]
0x18006b5aa  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x18006b5b1  mov     ecx, 2; int
0x18006b5b6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b5bb  jmp     loc_18006B8B1
0x18006b5c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006b5c7  mov     ecx, 0A88h; unsigned __int64
0x18006b5cc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006b5d1  mov     qword ptr [rbp+170h+Buf1], rax
0x18006b5d5  test    rax, rax
0x18006b5d8  jz      short loc_18006B5E3
0x18006b5da  mov     rcx, rax; this
0x18006b5dd  call    ??0CUserName@@QEAA@XZ; CUserName::CUserName(void)
0x18006b5e2  nop
0x18006b5e3  lea     rbx, [rsi+1728h]
0x18006b5ea  mov     rdx, rax
0x18006b5ed  mov     rcx, rbx
0x18006b5f0  call    ??4?$SmartPtr@UIUserName@@@@QEAAAEAV0@PEAUIUserName@@@Z; SmartPtr<IUserName>::operator=(IUserName *)
0x18006b5f5  mov     rcx, [rbx]
0x18006b5f8  test    rcx, rcx
0x18006b5fb  jnz     short loc_18006B607
0x18006b5fd  mov     edi, 8007000Eh
0x18006b602  jmp     loc_18006B89E
0x18006b607  mov     rax, [rcx]
0x18006b60a  mov     r8d, 1
0x18006b610  mov     rdx, r15
0x18006b613  mov     rax, [rax+18h]
0x18006b617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b61c  mov     edi, eax
0x18006b61e  test    eax, eax
0x18006b620  jns     short loc_18006B631
0x18006b622  mov     r8d, eax
0x18006b625  lea     rdx, aUsernameInitia_0; "UserName->Initialize failed: 0x%x in %s"
0x18006b62c  jmp     loc_18006B886
0x18006b631  mov     rcx, [rbx]
0x18006b634  mov     rax, [rcx]
0x18006b637  lea     rdx, [rsp+270h+pv]
0x18006b63c  mov     rax, [rax+48h]
0x18006b640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b645  mov     edi, eax
0x18006b647  test    eax, eax
0x18006b649  jns     short loc_18006B65A
0x18006b64b  mov     r8d, eax
0x18006b64e  lea     rdx, aGetusersidFail_0; "GetUserSid failed: 0x%x in %s"
0x18006b655  jmp     loc_18006B886
0x18006b65a  mov     rdx, [rsp+270h+pv]; void *
0x18006b65f  mov     ecx, [rsi+6D0h]; int
0x18006b665  call    ?ConfigurePerSessionSecurity@CTSSession@@CAJJPEAX@Z; CTSSession::ConfigurePerSessionSecurity(long,void *)
0x18006b66a  mov     edi, eax
0x18006b66c  test    eax, eax
0x18006b66e  jns     short loc_18006B67F
0x18006b670  mov     r8d, eax
0x18006b673  lea     rdx, aThisConfigurep; "this->ConfigurePerSessionSecurity faile"...
0x18006b67a  jmp     loc_18006B886
0x18006b67f  lea     rcx, [rsi+16F0h]; this
0x18006b686  mov     rdx, [rbx]; struct IUserName *
0x18006b689  call    ?AddUserAce@CTSSessionSecurityDescriptor@@QEAAJPEAUIUserName@@@Z; CTSSessionSecurityDescriptor::AddUserAce(IUserName *)
0x18006b68e  mov     edi, eax
0x18006b690  test    eax, eax
0x18006b692  jns     short loc_18006B6A3
0x18006b694  mov     r8d, eax
0x18006b697  lea     rdx, aThisSecurityde_1; "this->SecurityDescriptor.AddUserAce fai"...
0x18006b69e  jmp     loc_18006B886
0x18006b6a3  cmp     qword ptr [rsi+718h], 0
0x18006b6ab  jz      loc_18006B83C
0x18006b6b1  movups  xmm0, cs:EVENT_TERMINAL_LOGON_TOOLONG
0x18006b6b8  movdqu  [rbp+170h+Buf1], xmm0
0x18006b6bd  lea     rax, aPnewterminalLo; "pNewTerminal->LoggedOn"
0x18006b6c4  mov     [rsp+270h+var_248], rax; char *
0x18006b6c9  lea     rax, [rbp+170h+Buf1]
0x18006b6cd  mov     [rsp+270h+var_250], rax; struct _EVENT_DESCRIPTOR
0x18006b6d2  mov     r9, rsi; struct ITSSession *
0x18006b6d5  mov     r8d, [rsi+6D0h]; int
0x18006b6dc  mov     rdx, r13; struct _GUID *
0x18006b6df  lea     rcx, [rbp+170h+Parameter]; Parameter
0x18006b6e3  call    ??0CTSTerminalOpsMonitor@@QEAA@PEAU_GUID@@JPEAUITSSession@@U_EVENT_DESCRIPTOR@@PEBDK@Z; CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(_GUID *,long,ITSSession *,_EVENT_DESCRIPTOR,char const *,ulong)
0x18006b6e8  nop
0x18006b6e9  call    cs:__imp_GetTickCount64
0x18006b6ef  mov     r15, rax
0x18006b6f2  mov     r8, [rsi+718h]
0x18006b6f9  mov     rcx, [r8]
0x18006b6fc  mov     rax, [rcx+40h]
0x18006b700  mov     rdx, [rbx]
0x18006b703  mov     rcx, r8
0x18006b706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b70b  mov     edi, eax
0x18006b70d  call    cs:__imp_GetTickCount64
0x18006b713  mov     ecx, cs:dword_1800DA020
0x18006b719  cmp     ecx, 4
0x18006b71c  jbe     short loc_18006B762
0x18006b71e  sub     rax, r15
0x18006b721  mov     [rbp+170h+var_1E8], rax
0x18006b725  mov     eax, [rsi+6D0h]
0x18006b72b  mov     dword ptr [rsp+270h+var_200], eax
0x18006b72f  lea     rax, aPtrterminalLog; "ptrTerminal->LoggedOnStarted took this "...
0x18006b736  mov     [rbp+170h+var_1E0], rax
0x18006b73a  lea     rax, [rbp+170h+var_1E8]
0x18006b73e  mov     [rsp+270h+var_240], rax
0x18006b743  lea     rax, [rsp+270h+var_200]
0x18006b748  mov     [rsp+270h+var_248], rax
0x18006b74d  lea     rax, [rbp+170h+var_1E0]
0x18006b751  mov     [rsp+270h+var_250], rax
0x18006b756  lea     rdx, byte_1800C3F47
0x18006b75d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18006b762  test    edi, edi
0x18006b764  jns     short loc_18006B790
0x18006b766  mov     r8d, edi
0x18006b769  lea     rdx, aTerminalLogged_0; "Terminal->LoggedOnStarted failed: 0x%x "...
0x18006b770  lea     r9, aCtssessionOnlo_1; "CTSSession::OnLogonStarted"
0x18006b777  mov     ecx, 8; int
0x18006b77c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b781  nop
0x18006b782  lea     rcx, [rbp+170h+Parameter]; this
0x18006b786  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006b78b  jmp     loc_18006B897
0x18006b790  mov     rbx, [rsi+1718h]
0x18006b797  mov     rcx, rbx; pSecurityDescriptor
0x18006b79a  call    cs:__imp_GetSecurityDescriptorLength
0x18006b7a0  mov     r10, [rsi+718h]
0x18006b7a7  mov     rcx, [r10]
0x18006b7aa  mov     r9, [rcx+0C0h]
0x18006b7b1  mov     r8d, eax
0x18006b7b4  mov     rdx, rbx
0x18006b7b7  mov     rcx, r10
0x18006b7ba  mov     rax, r9
0x18006b7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7c2  mov     rcx, [rsi+718h]
0x18006b7c9  mov     rax, [rcx]
0x18006b7cc  lea     rdx, [rsi+844h]
0x18006b7d3  mov     rax, [rax+0A0h]
0x18006b7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7df  mov     edi, eax
0x18006b7e1  test    eax, eax
0x18006b7e3  jns     short loc_18006B7F4
0x18006b7e5  mov     r8d, eax
0x18006b7e8  lea     rdx, aGetsessioninit; "GetSessionInitialProgram failed: 0x%x i"...
0x18006b7ef  jmp     loc_18006B770
0x18006b7f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18006b7fb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18006b800  test    al, al
0x18006b802  jz      short loc_18006B833
0x18006b804  movups  xmm0, xmmword ptr [rsi+16C8h]
0x18006b80b  movdqu  [rbp+170h+Buf1], xmm0
0x18006b810  mov     r8d, 10h; Size
0x18006b816  lea     rdx, TERMINAL_TYPE_AGENT; Buf2
0x18006b81d  lea     rcx, [rbp+170h+Buf1]; Buf1
0x18006b821  call    memcmp_0
0x18006b826  test    eax, eax
0x18006b828  jnz     short loc_18006B833
0x18006b82a  mov     rcx, rsi; this
0x18006b82d  call    ?SetIsolationConfigId@CTSSession@@AEAAXXZ; CTSSession::SetIsolationConfigId(void)
0x18006b832  nop
0x18006b833  lea     rcx, [rbp+170h+Parameter]; this
0x18006b837  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006b83c  mov     rdx, [rsi+718h]
0x18006b843  lea     rcx, [rbp+170h+var_1F0]
0x18006b847  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18006b84c  lea     rcx, [rbp+170h+Resource]; this
0x18006b850  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006b855  mov     rcx, rsi; this
0x18006b858  call    ?SetTimeZone@CTSSession@@AEAAJXZ; CTSSession::SetTimeZone(void)
0x18006b85d  mov     edi, eax
0x18006b85f  mov     [rbp+170h+var_1B0], 1
0x18006b866  mov     rcx, [rbp+170h+Resource]; Resource
0x18006b86a  cmp     dword ptr [rcx+60h], 0
0x18006b86e  jz      short loc_18006B878
0x18006b870  mov     dl, 1; Wait
0x18006b872  call    cs:__imp_RtlAcquireResourceExclusive
0x18006b878  test    edi, edi
0x18006b87a  jns     short loc_18006B8AD
0x18006b87c  mov     r8d, edi
0x18006b87f  lea     rdx, aSettimezoneFai; "SetTimeZone failed: 0x%x in %s"
0x18006b886  lea     r9, aCtssessionOnlo_1; "CTSSession::OnLogonStarted"
0x18006b88d  mov     ecx, 8; int
0x18006b892  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b897  lea     rbx, [rsi+1728h]
0x18006b89e  xor     edx, edx
0x18006b8a0  mov     rcx, rbx
0x18006b8a3  call    ??4?$SmartPtr@UIUserName@@@@QEAAAEAV0@PEAUIUserName@@@Z; SmartPtr<IUserName>::operator=(IUserName *)
0x18006b8a8  jmp     loc_18006BB27
0x18006b8ad  mov     rbx, [rbp+170h+var_1F0]
0x18006b8b1  mov     rcx, rsi; this
0x18006b8b4  call    ?UpdateDomainUsernameString@CTSSession@@AEAAJXZ; CTSSession::UpdateDomainUsernameString(void)
0x18006b8b9  xorps   xmm0, xmm0
0x18006b8bc  xor     eax, eax
0x18006b8be  movups  [rbp+170h+Parameter], xmm0
0x18006b8c2  movups  xmmword ptr [rbp+170h+var_170], xmm0
0x18006b8c6  movups  [rbp+170h+var_160], xmm0
0x18006b8ca  mov     [rbp+170h+var_150], rax
0x18006b8ce  xor     r15b, r15b
0x18006b8d1  lea     rdx, [rbp+170h+Parameter]; struct __PTSSessInfo *
0x18006b8d5  mov     rcx, rsi; this
0x18006b8d8  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x18006b8dd  mov     edi, eax
0x18006b8df  test    eax, eax
0x18006b8e1  js      loc_18006BAF1
0x18006b8e7  cmp     dword ptr [r12+10h], 1
0x18006b8ed  jnz     short loc_18006B903
0x18006b8ef  mov     r15b, 1
0x18006b8f2  lea     rdx, aThisLogonIsAnA; "This logon is an ARSO, PIN Reset, or Ki"...
0x18006b8f9  mov     ecx, 1; int
0x18006b8fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b903  mov     r12d, [r14]
0x18006b906  mov     dword ptr [rsp+270h+var_250], 17DCh
0x18006b90e  lea     r9, [rbp+170h+var_150]
0x18006b912  lea     r8, [rbp+170h+var_160+8]
0x18006b916  mov     edx, 5
0x18006b91b  mov     rcx, r14
0x18006b91e  call    ?ChangeState@CState@CTSSession@@QEAA?AW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAKPEAT_LARGE_INTEGER@@K@Z; CTSSession::CState::ChangeState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,ulong *,_LARGE_INTEGER *,ulong)
0x18006b923  mov     r13d, [r14]
0x18006b926  lea     rdi, [rsi+7C8h]
0x18006b92d  mov     rcx, rdi; SystemTime
0x18006b930  call    cs:__imp_NtQuerySystemTime
0x18006b936  lea     r14, [rsi+800h]
0x18006b93d  mov     rcx, r14; lpSystemTime
0x18006b940  call    cs:__imp_GetSystemTime
0x18006b946  mov     eax, cs:dword_1800DA020
0x18006b94c  cmp     eax, 5
0x18006b94f  jbe     loc_18006BA3D
0x18006b955  mov     rdx, 400000000000h
0x18006b95f  lea     rcx, dword_1800DA020
0x18006b966  call    _tlgKeywordOn
0x18006b96b  test    al, al
0x18006b96d  jz      loc_18006BA3D
0x18006b973  lea     rax, aLogon; "Logon"
0x18006b97a  mov     [rbp+170h+var_1E0], rax
0x18006b97e  mov     r9, [rsi+7B8h]
0x18006b985  mov     r8, [rdi]
0x18006b988  mov     rcx, r8
0x18006b98b  sub     rcx, r9
  ... truncated ...
```
