# CTSSession::OnLogonStarted(void *,_SN_ONLOGON_PARAMS_EX *)

- ea: `0x18006f300`
- end: `0x18006fa54`
- name: `?OnLogonStarted@CTSSession@@UEAAJPEAXPEAU_SN_ONLOGON_PARAMS_EX@@@Z`
- size: `1876`
- prototype: `__int64 __fastcall(CTSSession *__hidden this, void *, struct _SN_ONLOGON_PARAMS_EX *)`
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800077a0`
- `0x1800095f8`
- `0x18000afd0`
- `0x18000c05c`
- `0x18000c684`
- `0x180011498`
- `0x1800115a8`
- `0x1800118f4`
- `0x180011a28`
- `0x180011a50`
- `0x180011a78`
- `0x180011e6c`
- `0x1800120d0`
- `0x180012194`
- `0x1800123b0`
- `0x18001266c`
- `0x1800129d0`
- `0x180013658`
- `0x180014b20`
- `0x18002167c`
- `0x180022030`
- `0x1800266bc`
- `0x180027610`
- `0x180029f3c`
- `0x18002ae18`
- `0x18002dfb0`
- `0x180031650`
- `0x18003654c`
- `0x1800367c0`
- `0x18004e850`
- `0x18004ec5c`
- `0x18005ef98`
- `0x18006e510`
- `0x18006f300`
- `0x1800709ac`
- `0x180071830`
- `0x180099590`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18006f704`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006f704`
- `ntdll!NtQuerySystemTime` at `0x18006f7c8`
- `ntdll!NtQuerySystemTime` at `0x18006f7c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f9d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f9d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006f569`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006f593`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006f569`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006f593`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006f7de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18006f7de`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006f626`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18006f626`

## string_xrefs

- `0x18006f517`: `this->SecurityDescriptor.AddUserAce failed: 0x%x in %s`
- `0x18006f4ce`: `GetUserSid failed: 0x%x in %s`
- `0x18006f4f3`: `this->ConfigurePerSessionSecurity failed: 0x%x in %s`

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
  CUserName *v13; // rax
  struct IUserName **v14; // rbx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  ULONGLONG TickCount64; // r15
  ULONGLONG v20; // rax
  int v21; // r8d
  int v22; // r9d
  void *v23; // rbx
  DWORD SecurityDescriptorLength; // eax
  int v25; // eax
  __int64 v26; // rdx
  int v27; // r8d
  int v28; // r9d
  char v29; // r15
  unsigned int v30; // r12d
  unsigned int v31; // r13d
  __int64 *v32; // rdi
  __int64 v33; // r9
  __int64 v34; // r8
  __int64 v35; // rcx
  int v36; // eax
  int v37; // eax
  unsigned int v39; // [rsp+30h] [rbp-D0h]
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  struct ITerminal *v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v44[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 Buf1; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h] BYREF
  PRTL_RESOURCE Resource; // [rsp+B8h] [rbp-48h] BYREF
  int v48; // [rsp+C0h] [rbp-40h]
  __int64 v49; // [rsp+C8h] [rbp-38h] BYREF
  char *v50; // [rsp+D0h] [rbp-30h] BYREF
  char *v51; // [rsp+D8h] [rbp-28h] BYREF
  char *v52; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v53; // [rsp+E8h] [rbp-18h] BYREF
  __int128 Parameter; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v55[4]; // [rsp+100h] [rbp+0h]
  __int128 v56; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v57[6]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v58[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v59[192]; // [rsp+170h] [rbp+70h] BYREF

  pv = 0;
  v46 = 0;
  v6 = 0;
  v42 = 0;
  v7 = (struct _GUID *)((char *)this + 3208);
  CAutoSetActivityId::CAutoSetActivityId((CAutoSetActivityId *)v58, (struct _GUID *)((char *)this + 3208));
  CTSSessionTrace::CTSSessionTrace((CTSSessionTrace *)v59, "CTSSession::OnLogonStarted", this);
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)&Resource, (CTSSession *)((char *)this + 1856));
  v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 199) + 24LL))(
         *((_QWORD *)this + 199),
         &IID_ITSSession,
         &v46);
  v9 = v8;
  if ( v8 < 0 )
  {
    _DbgPrintMessage(8, "QI( ITSSession ) failed: 0x%x in %s", (unsigned int)v8, "CTSSession::OnLogonStarted");
LABEL_36:
    v14 = (struct IUserName **)((char *)this + 5928);
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
    GetLsmEventName(5);
    if ( (g_DebugTraceComponent & 4) != 0 )
      _DbgPrintMessage(2, "No change to session %d state %ws with event %ws", *((unsigned int *)this + 436));
    goto LABEL_39;
  }
  v13 = (CUserName *)operator new(0xA88u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)&Buf1 = v13;
  if ( v13 )
    v13 = CUserName::CUserName(v13);
  v14 = (struct IUserName **)((char *)this + 5928);
  SmartPtr<IUserName>::operator=((char *)this + 5928, v13);
  if ( !*((_QWORD *)this + 741) )
  {
    v9 = -2147024882;
LABEL_37:
    SmartPtr<IUserName>::operator=(v14, 0);
    goto LABEL_56;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, void *, __int64))(**((_QWORD **)this + 741) + 24LL))(
          *((_QWORD *)this + 741),
          a2,
          1);
  v9 = v15;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(8, "UserName->Initialize failed: 0x%x in %s", (unsigned int)v15, "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  v16 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)*v14 + 72LL))(*v14, &pv);
  v9 = v16;
  if ( v16 < 0 )
  {
    _DbgPrintMessage(8, "GetUserSid failed: 0x%x in %s", (unsigned int)v16, "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  v17 = CTSSession::ConfigurePerSessionSecurity(*((_DWORD *)this + 436), pv);
  v9 = v17;
  if ( v17 < 0 )
  {
    _DbgPrintMessage(
      8,
      "this->ConfigurePerSessionSecurity failed: 0x%x in %s",
      (unsigned int)v17,
      "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  v18 = CTSSessionSecurityDescriptor::AddUserAce((CTSSession *)((char *)this + 5872), *v14);
  v9 = v18;
  if ( v18 < 0 )
  {
    _DbgPrintMessage(
      8,
      "this->SecurityDescriptor.AddUserAce failed: 0x%x in %s",
      (unsigned int)v18,
      "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  if ( *((_QWORD *)this + 227) )
  {
    Buf1 = EVENT_TERMINAL_LOGON_TOOLONG;
    CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(
      &Parameter,
      v7,
      *((_DWORD *)this + 436),
      this,
      (struct _EVENT_DESCRIPTOR *)&Buf1,
      "pNewTerminal->LoggedOn",
      v39);
    TickCount64 = GetTickCount64();
    v9 = (*(__int64 (__fastcall **)(_QWORD, struct IUserName *))(**((_QWORD **)this + 227) + 64LL))(
           *((_QWORD *)this + 227),
           *v14);
    v20 = GetTickCount64();
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v43 = v20 - TickCount64;
      LODWORD(v40) = *((_DWORD *)this + 436);
      v44[0] = "ptrTerminal->LoggedOnStarted took this long";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        dword_1800DF020,
        (unsigned int)&byte_1800C90CF,
        v21,
        v22,
        (__int64)v44,
        (__int64)&v40,
        (__int64)&v43);
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
    v23 = (void *)*((_QWORD *)this + 739);
    SecurityDescriptorLength = GetSecurityDescriptorLength(v23);
    (*(void (__fastcall **)(_QWORD, void *, _QWORD))(**((_QWORD **)this + 227) + 192LL))(
      *((_QWORD *)this + 227),
      v23,
      SecurityDescriptorLength);
    v25 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 227) + 160LL))(
            *((_QWORD *)this + 227),
            (char *)this + 2116);
    v9 = v25;
    if ( v25 < 0 )
    {
      _DbgPrintMessage(
        8,
        "GetSessionInitialProgram failed: 0x%x in %s",
        (unsigned int)v25,
        "CTSSession::OnLogonStarted");
      goto LABEL_25;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl) )
    {
      Buf1 = *(_OWORD *)((char *)this + 5832);
      if ( !memcmp_0(&Buf1, TERMINAL_TYPE_AGENT, 0x10u) )
        CTSSession::SetIsolationConfigId(this, v26, v27, v28);
    }
    CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)&Parameter);
  }
  SmartPtr<ITerminal>::operator=(&v42, *((_QWORD *)this + 227));
  CAutoLock::Unlock((CAutoLock *)&Resource);
  v9 = CTSSession::SetTimeZone(this);
  v48 = 1;
  if ( LODWORD(Resource[1].Lock.DebugInfo) )
    RtlAcquireResourceExclusive(Resource, 1u);
  if ( v9 < 0 )
  {
    _DbgPrintMessage(8, "SetTimeZone failed: 0x%x in %s", (unsigned int)v9, "CTSSession::OnLogonStarted");
    goto LABEL_36;
  }
  v6 = v42;
LABEL_39:
  CTSSession::UpdateDomainUsernameString(this);
  Parameter = 0;
  *(_OWORD *)v55 = 0;
  v56 = 0;
  v57[0] = 0;
  v29 = 0;
  v9 = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)&Parameter);
  if ( v9 >= 0 )
  {
    if ( *((_DWORD *)a3 + 4) == 1 )
    {
      v29 = 1;
      _DbgPrintMessage(1, "This logon is an ARSO, PIN Reset, or Kiosk mode logon");
    }
    v30 = *v10;
    CTSSession::CState::ChangeState((char *)this + 3256, 5, (char *)&v56 + 8, v57, 6108);
    v31 = *v10;
    v32 = (__int64 *)((char *)this + 1992);
    NtQuerySystemTime((PLARGE_INTEGER)this + 249);
    GetSystemTime((LPSYSTEMTIME)this + 128);
    if ( (unsigned int)dword_1800DF020 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DF020, 0x400000000000LL) )
    {
      v44[0] = "Logon";
      v33 = *((_QWORD *)this + 247);
      v34 = *v32;
      v35 = *v32 - v33;
      v43 = v35 / 10000000;
      v40 = v35;
      v49 = v34;
      v50 = (char *)this + 3208;
      v51 = (char *)this + 2048;
      v52 = (char *)this + 2016;
      v53 = v33;
      *(_QWORD *)&Buf1 = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v35,
        (unsigned int)byte_1800C903D,
        v34,
        v33,
        (__int64)&Buf1,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v51,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v40,
        (__int64)&v43,
        (__int64)v44);
    }
    CAutoLock::Unlock((CAutoLock *)&Resource);
    v36 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL)
                                                                         + 56LL))(
            *((_QWORD *)this + 228) + 1832LL,
            &Parameter,
            v31,
            v30);
    v9 = v36;
    if ( v36 < 0 )
      _DbgPrintMessage(8, "EventDispatch->OnLogon failed: 0x%x", v36);
    CTSSession::PublishWNFNotification(this, 5u, v55[2]);
    if ( (_QWORD)Parameter )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Parameter + 16LL))(Parameter);
      *(_QWORD *)&Parameter = 0;
    }
    if ( (_QWORD)v56 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v56 + 16LL))(v56);
      *(_QWORD *)&v56 = 0;
    }
    v37 = CTSSession::SendSessionNotificationMsg(this, 0);
    if ( v37 < 0 )
      _DbgPrintMessage(8, "SendSessionNotificationMsg failed: 0x%x", v37);
  }
  if ( v6 )
  {
    CTSSession::LogSessionEvent(this, &EVENT_SESSION_LOGON, v6);
    if ( v29 )
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
  CTSSessionTrace::~CTSSessionTrace((CTSSessionTrace *)v59);
  CAutoSetActivityId::~CAutoSetActivityId((CAutoSetActivityId *)v58);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v42);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v46);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006f300  mov     [rsp-8+arg_10], rbx
0x18006f305  push    rbp
0x18006f306  push    rsi
0x18006f307  push    rdi
0x18006f308  push    r12
0x18006f30a  push    r13
0x18006f30c  push    r14
0x18006f30e  push    r15
0x18006f310  lea     rbp, [rsp-140h]
0x18006f318  sub     rsp, 240h
0x18006f31f  mov     rax, cs:__security_cookie
0x18006f326  xor     rax, rsp
0x18006f329  mov     [rbp+170h+var_40], rax
0x18006f330  mov     r12, r8
0x18006f333  mov     r15, rdx
0x18006f336  mov     rsi, rcx
0x18006f339  mov     [rsp+270h+pv], 0
0x18006f342  mov     [rbp+170h+var_1C0], 0
0x18006f34a  xor     ebx, ebx
0x18006f34c  mov     [rbp+170h+var_1F0], rbx
0x18006f350  lea     r13, [rcx+0C88h]
0x18006f357  mov     rdx, r13; struct _GUID *
0x18006f35a  lea     rcx, [rbp+170h+var_120]; this
0x18006f35e  call    ??0CAutoSetActivityId@@QEAA@PEAU_GUID@@@Z; CAutoSetActivityId::CAutoSetActivityId(_GUID *)
0x18006f363  nop
0x18006f364  mov     r8, rsi; struct ITSSession *
0x18006f367  lea     rdx, aCtssessionOnlo_1; "CTSSession::OnLogonStarted"
0x18006f36e  lea     rcx, [rbp+170h+var_100]; this
0x18006f372  call    ??0CTSSessionTrace@@QEAA@PEBDPEAUITSSession@@@Z; CTSSessionTrace::CTSSessionTrace(char const *,ITSSession *)
0x18006f377  nop
0x18006f378  lea     rdx, [rsi+740h]; struct CResource *
0x18006f37f  lea     rcx, [rbp+170h+Resource]; this
0x18006f383  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18006f388  nop
0x18006f389  mov     rcx, [rsi+638h]
0x18006f390  mov     rax, [rcx]
0x18006f393  lea     r8, [rbp+170h+var_1C0]
0x18006f397  lea     rdx, IID_ITSSession
0x18006f39e  mov     rax, [rax+18h]
0x18006f3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f3a7  mov     edi, eax
0x18006f3a9  test    eax, eax
0x18006f3ab  jns     short loc_18006F3BC
0x18006f3ad  mov     r8d, eax
0x18006f3b0  lea     rdx, aQiItssessionFa; "QI( ITSSession ) failed: 0x%x in %s"
0x18006f3b7  jmp     loc_18006F71E
0x18006f3bc  lea     r14, [rsi+0CB8h]
0x18006f3c3  mov     edx, 5
0x18006f3c8  mov     rcx, r14
0x18006f3cb  call    ?CheckState@CState@CTSSession@@QEAAJW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@@Z; CTSSession::CState::CheckState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002)
0x18006f3d0  mov     edi, eax
0x18006f3d2  test    eax, eax
0x18006f3d4  jns     short loc_18006F3F7
0x18006f3d6  mov     ecx, [r14]
0x18006f3d9  call    ?GetStateName@CUtils@@SAPEBDW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@@Z; CUtils::GetStateName(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001)
0x18006f3de  mov     r8, rax
0x18006f3e1  lea     rdx, aInvalidStateFo_2; "invalid state for EvLogon, state is: \""...
0x18006f3e8  mov     ecx, 8; int
0x18006f3ed  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f3f2  jmp     loc_18006F72F
0x18006f3f7  cmp     eax, 1
0x18006f3fa  jnz     short loc_18006F440
0x18006f3fc  mov     ecx, [r14]; int
0x18006f3ff  call    ?GetLsmStateName@@YAPEBGH@Z; GetLsmStateName(int)
0x18006f404  mov     r9, rax
0x18006f407  mov     ecx, 5; int
0x18006f40c  call    ?GetLsmEventName@@YAPEBGH@Z; GetLsmEventName(int)
0x18006f411  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18006f418  jz      loc_18006F749
0x18006f41e  mov     [rsp+270h+var_250], rax
0x18006f423  mov     r8d, [rsi+6D0h]
0x18006f42a  lea     rdx, aNoChangeToSess; "No change to session %d state %ws with "...
0x18006f431  mov     ecx, 2; int
0x18006f436  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f43b  jmp     loc_18006F749
0x18006f440  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006f447  mov     ecx, 0A88h; unsigned __int64
0x18006f44c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006f451  mov     qword ptr [rbp+170h+Buf1], rax
0x18006f455  test    rax, rax
0x18006f458  jz      short loc_18006F463
0x18006f45a  mov     rcx, rax; this
0x18006f45d  call    ??0CUserName@@QEAA@XZ; CUserName::CUserName(void)
0x18006f462  nop
0x18006f463  lea     rbx, [rsi+1728h]
0x18006f46a  mov     rdx, rax
0x18006f46d  mov     rcx, rbx
0x18006f470  call    ??4?$SmartPtr@UIUserName@@@@QEAAAEAV0@PEAUIUserName@@@Z; SmartPtr<IUserName>::operator=(IUserName *)
0x18006f475  mov     rcx, [rbx]
0x18006f478  test    rcx, rcx
0x18006f47b  jnz     short loc_18006F487
0x18006f47d  mov     edi, 8007000Eh
0x18006f482  jmp     loc_18006F736
0x18006f487  mov     rax, [rcx]
0x18006f48a  mov     r8d, 1
0x18006f490  mov     rdx, r15
0x18006f493  mov     rax, [rax+18h]
0x18006f497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f49c  mov     edi, eax
0x18006f49e  test    eax, eax
0x18006f4a0  jns     short loc_18006F4B1
0x18006f4a2  mov     r8d, eax
0x18006f4a5  lea     rdx, aUsernameInitia_0; "UserName->Initialize failed: 0x%x in %s"
0x18006f4ac  jmp     loc_18006F71E
0x18006f4b1  mov     rcx, [rbx]
0x18006f4b4  mov     rax, [rcx]
0x18006f4b7  lea     rdx, [rsp+270h+pv]
0x18006f4bc  mov     rax, [rax+48h]
0x18006f4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f4c5  mov     edi, eax
0x18006f4c7  test    eax, eax
0x18006f4c9  jns     short loc_18006F4DA
0x18006f4cb  mov     r8d, eax
0x18006f4ce  lea     rdx, aGetusersidFail_0; "GetUserSid failed: 0x%x in %s"
0x18006f4d5  jmp     loc_18006F71E
0x18006f4da  mov     rdx, [rsp+270h+pv]; void *
0x18006f4df  mov     ecx, [rsi+6D0h]; int
0x18006f4e5  call    ?ConfigurePerSessionSecurity@CTSSession@@CAJJPEAX@Z; CTSSession::ConfigurePerSessionSecurity(long,void *)
0x18006f4ea  mov     edi, eax
0x18006f4ec  test    eax, eax
0x18006f4ee  jns     short loc_18006F4FF
0x18006f4f0  mov     r8d, eax
0x18006f4f3  lea     rdx, aThisConfigurep; "this->ConfigurePerSessionSecurity faile"...
0x18006f4fa  jmp     loc_18006F71E
0x18006f4ff  lea     rcx, [rsi+16F0h]; this
0x18006f506  mov     rdx, [rbx]; struct IUserName *
0x18006f509  call    ?AddUserAce@CTSSessionSecurityDescriptor@@QEAAJPEAUIUserName@@@Z; CTSSessionSecurityDescriptor::AddUserAce(IUserName *)
0x18006f50e  mov     edi, eax
0x18006f510  test    eax, eax
0x18006f512  jns     short loc_18006F523
0x18006f514  mov     r8d, eax
0x18006f517  lea     rdx, aThisSecurityde_1; "this->SecurityDescriptor.AddUserAce fai"...
0x18006f51e  jmp     loc_18006F71E
0x18006f523  cmp     qword ptr [rsi+718h], 0
0x18006f52b  jz      loc_18006F6CE
0x18006f531  movups  xmm0, cs:EVENT_TERMINAL_LOGON_TOOLONG
0x18006f538  movdqu  [rbp+170h+Buf1], xmm0
0x18006f53d  lea     rax, aPnewterminalLo; "pNewTerminal->LoggedOn"
0x18006f544  mov     [rsp+270h+var_248], rax; char *
0x18006f549  lea     rax, [rbp+170h+Buf1]
0x18006f54d  mov     [rsp+270h+var_250], rax; struct _EVENT_DESCRIPTOR
0x18006f552  mov     r9, rsi; struct ITSSession *
0x18006f555  mov     r8d, [rsi+6D0h]; int
0x18006f55c  mov     rdx, r13; struct _GUID *
0x18006f55f  lea     rcx, [rbp+170h+Parameter]; Parameter
0x18006f563  call    ??0CTSTerminalOpsMonitor@@QEAA@PEAU_GUID@@JPEAUITSSession@@U_EVENT_DESCRIPTOR@@PEBDK@Z; CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(_GUID *,long,ITSSession *,_EVENT_DESCRIPTOR,char const *,ulong)
0x18006f568  nop
0x18006f569  call    cs:__imp_GetTickCount64
0x18006f570  nop     dword ptr [rax+rax+00h]
0x18006f575  mov     r15, rax
0x18006f578  mov     r8, [rsi+718h]
0x18006f57f  mov     rcx, [r8]
0x18006f582  mov     rax, [rcx+40h]
0x18006f586  mov     rdx, [rbx]
0x18006f589  mov     rcx, r8
0x18006f58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f591  mov     edi, eax
0x18006f593  call    cs:__imp_GetTickCount64
0x18006f59a  nop     dword ptr [rax+rax+00h]
0x18006f59f  mov     ecx, cs:dword_1800DF020
0x18006f5a5  cmp     ecx, 4
0x18006f5a8  jbe     short loc_18006F5EE
0x18006f5aa  sub     rax, r15
0x18006f5ad  mov     [rbp+170h+var_1E8], rax
0x18006f5b1  mov     eax, [rsi+6D0h]
0x18006f5b7  mov     dword ptr [rsp+270h+var_200], eax
0x18006f5bb  lea     rax, aPtrterminalLog; "ptrTerminal->LoggedOnStarted took this "...
0x18006f5c2  mov     [rbp+170h+var_1E0], rax
0x18006f5c6  lea     rax, [rbp+170h+var_1E8]
0x18006f5ca  mov     [rsp+270h+var_240], rax
0x18006f5cf  lea     rax, [rsp+270h+var_200]
0x18006f5d4  mov     [rsp+270h+var_248], rax
0x18006f5d9  lea     rax, [rbp+170h+var_1E0]
0x18006f5dd  mov     [rsp+270h+var_250], rax
0x18006f5e2  lea     rdx, byte_1800C90CF
0x18006f5e9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18006f5ee  test    edi, edi
0x18006f5f0  jns     short loc_18006F61C
0x18006f5f2  mov     r8d, edi
0x18006f5f5  lea     rdx, aTerminalLogged_0; "Terminal->LoggedOnStarted failed: 0x%x "...
0x18006f5fc  lea     r9, aCtssessionOnlo_1; "CTSSession::OnLogonStarted"
0x18006f603  mov     ecx, 8; int
0x18006f608  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f60d  nop
0x18006f60e  lea     rcx, [rbp+170h+Parameter]; this
0x18006f612  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006f617  jmp     loc_18006F72F
0x18006f61c  mov     rbx, [rsi+1718h]
0x18006f623  mov     rcx, rbx; pSecurityDescriptor
0x18006f626  call    cs:__imp_GetSecurityDescriptorLength
0x18006f62d  nop     dword ptr [rax+rax+00h]
0x18006f632  mov     r10, [rsi+718h]
0x18006f639  mov     rcx, [r10]
0x18006f63c  mov     r9, [rcx+0C0h]
0x18006f643  mov     r8d, eax
0x18006f646  mov     rdx, rbx
0x18006f649  mov     rcx, r10
0x18006f64c  mov     rax, r9
0x18006f64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f654  mov     rcx, [rsi+718h]
0x18006f65b  mov     rax, [rcx]
0x18006f65e  lea     rdx, [rsi+844h]
0x18006f665  mov     rax, [rax+0A0h]
0x18006f66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f671  mov     edi, eax
0x18006f673  test    eax, eax
0x18006f675  jns     short loc_18006F686
0x18006f677  mov     r8d, eax
0x18006f67a  lea     rdx, aGetsessioninit; "GetSessionInitialProgram failed: 0x%x i"...
0x18006f681  jmp     loc_18006F5FC
0x18006f686  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18006f68d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18006f692  test    al, al
0x18006f694  jz      short loc_18006F6C5
0x18006f696  movups  xmm0, xmmword ptr [rsi+16C8h]
0x18006f69d  movdqu  [rbp+170h+Buf1], xmm0
0x18006f6a2  mov     r8d, 10h; Size
0x18006f6a8  lea     rdx, TERMINAL_TYPE_AGENT; Buf2
0x18006f6af  lea     rcx, [rbp+170h+Buf1]; Buf1
0x18006f6b3  call    memcmp_0
0x18006f6b8  test    eax, eax
0x18006f6ba  jnz     short loc_18006F6C5
0x18006f6bc  mov     rcx, rsi; this
0x18006f6bf  call    ?SetIsolationConfigId@CTSSession@@AEAAXXZ; CTSSession::SetIsolationConfigId(void)
0x18006f6c4  nop
0x18006f6c5  lea     rcx, [rbp+170h+Parameter]; this
0x18006f6c9  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006f6ce  mov     rdx, [rsi+718h]
0x18006f6d5  lea     rcx, [rbp+170h+var_1F0]
0x18006f6d9  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18006f6de  lea     rcx, [rbp+170h+Resource]; this
0x18006f6e2  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18006f6e7  mov     rcx, rsi; this
0x18006f6ea  call    ?SetTimeZone@CTSSession@@AEAAJXZ; CTSSession::SetTimeZone(void)
0x18006f6ef  mov     edi, eax
0x18006f6f1  mov     [rbp+170h+var_1B0], 1
0x18006f6f8  mov     rcx, [rbp+170h+Resource]; Resource
0x18006f6fc  cmp     dword ptr [rcx+60h], 0
0x18006f700  jz      short loc_18006F710
0x18006f702  mov     dl, 1; Wait
0x18006f704  call    cs:__imp_RtlAcquireResourceExclusive
0x18006f70b  nop     dword ptr [rax+rax+00h]
0x18006f710  test    edi, edi
0x18006f712  jns     short loc_18006F745
0x18006f714  mov     r8d, edi
0x18006f717  lea     rdx, aSettimezoneFai; "SetTimeZone failed: 0x%x in %s"
0x18006f71e  lea     r9, aCtssessionOnlo_1; "CTSSession::OnLogonStarted"
0x18006f725  mov     ecx, 8; int
0x18006f72a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f72f  lea     rbx, [rsi+1728h]
0x18006f736  xor     edx, edx
0x18006f738  mov     rcx, rbx
0x18006f73b  call    ??4?$SmartPtr@UIUserName@@@@QEAAAEAV0@PEAUIUserName@@@Z; SmartPtr<IUserName>::operator=(IUserName *)
0x18006f740  jmp     loc_18006F9CB
0x18006f745  mov     rbx, [rbp+170h+var_1F0]
0x18006f749  mov     rcx, rsi; this
0x18006f74c  call    ?UpdateDomainUsernameString@CTSSession@@AEAAJXZ; CTSSession::UpdateDomainUsernameString(void)
0x18006f751  xorps   xmm0, xmm0
0x18006f754  xor     eax, eax
0x18006f756  movups  [rbp+170h+Parameter], xmm0
0x18006f75a  movups  xmmword ptr [rbp+170h+var_170], xmm0
0x18006f75e  movups  [rbp+170h+var_160], xmm0
0x18006f762  mov     [rbp+170h+var_150], rax
0x18006f766  xor     r15b, r15b
0x18006f769  lea     rdx, [rbp+170h+Parameter]; struct __PTSSessInfo *
0x18006f76d  mov     rcx, rsi; this
0x18006f770  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x18006f775  mov     edi, eax
0x18006f777  test    eax, eax
0x18006f779  js      loc_18006F995
0x18006f77f  cmp     dword ptr [r12+10h], 1
0x18006f785  jnz     short loc_18006F79B
0x18006f787  mov     r15b, 1
0x18006f78a  lea     rdx, aThisLogonIsAnA; "This logon is an ARSO, PIN Reset, or Ki"...
0x18006f791  mov     ecx, 1; int
0x18006f796  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f79b  mov     r12d, [r14]
0x18006f79e  mov     dword ptr [rsp+270h+var_250], 17DCh
0x18006f7a6  lea     r9, [rbp+170h+var_150]
0x18006f7aa  lea     r8, [rbp+170h+var_160+8]
0x18006f7ae  mov     edx, 5
0x18006f7b3  mov     rcx, r14
0x18006f7b6  call    ?ChangeState@CState@CTSSession@@QEAA?AW4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0001@@W4__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002@@PEAKPEAT_LARGE_INTEGER@@K@Z; CTSSession::CState::ChangeState(__MIDL___MIDL_itf_lsminterfacesdef_0000_0001_0002,ulong *,_LARGE_INTEGER *,ulong)
0x18006f7bb  mov     r13d, [r14]
0x18006f7be  lea     rdi, [rsi+7C8h]
0x18006f7c5  mov     rcx, rdi; SystemTime
0x18006f7c8  call    cs:__imp_NtQuerySystemTime
0x18006f7cf  nop     dword ptr [rax+rax+00h]
0x18006f7d4  lea     r14, [rsi+800h]
0x18006f7db  mov     rcx, r14; lpSystemTime
0x18006f7de  call    cs:__imp_GetSystemTime
0x18006f7e5  nop     dword ptr [rax+rax+00h]
0x18006f7ea  mov     eax, cs:dword_1800DF020
0x18006f7f0  cmp     eax, 5
0x18006f7f3  jbe     loc_18006F8E1
0x18006f7f9  mov     rdx, 400000000000h
0x18006f803  lea     rcx, dword_1800DF020
0x18006f80a  call    _tlgKeywordOn
0x18006f80f  test    al, al
0x18006f811  jz      loc_18006F8E1
  ... truncated ...
```
