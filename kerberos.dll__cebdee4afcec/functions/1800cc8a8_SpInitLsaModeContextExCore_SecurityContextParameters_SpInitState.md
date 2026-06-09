# SpInitLsaModeContextExCore(SecurityContextParameters &,SpInitState &)

- ea: `0x1800cc8a8`
- end: `0x1800cda0a`
- name: `?SpInitLsaModeContextExCore@@YAXAEAUSecurityContextParameters@@AEAUSpInitState@@@Z`
- size: `4450`
- prototype: `void __fastcall(struct SecurityContextParameters *this, struct SpInitState *)`
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800cc5e4`

## callees

- `0x1800063e8`
- `0x1800068d0`
- `0x1800069e0`
- `0x180009afc`
- `0x180029360`
- `0x18002b71c`
- `0x18002bd40`
- `0x18002d85c`
- `0x18002f8b0`
- `0x18002ffa8`
- `0x180032964`
- `0x180045970`
- `0x180045cd0`
- `0x180046e70`
- `0x1800484f8`
- `0x1800548b4`
- `0x1800566a8`
- `0x18005de50`
- `0x180062d28`
- `0x18006e98c`
- `0x1800744cf`
- `0x180085c20`
- `0x180087070`
- `0x18008a304`
- `0x18008a714`
- `0x18008b70c`
- `0x180092c24`
- `0x1800c22ec`
- `0x1800c237c`
- `0x1800c23b4`
- `0x1800caf98`
- `0x1800cb168`
- `0x1800cb31c`
- `0x1800cb5b8`
- `0x1800cb694`
- `0x1800cba38`
- `0x1800cc8a8`
- `0x1800cda10`
- `0x1800ce658`
- `0x1800ce694`
- `0x1800ce6c8`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cd9bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cd9bc`
- `ntdll!RtlSystemTimeToLocalTime` at `0x1800cd972`
- `ntdll!RtlSystemTimeToLocalTime` at `0x1800cd972`
- `ntdll!EtwLogTraceEvent` at `0x1800cc942`
- `ntdll!EtwLogTraceEvent` at `0x1800cc942`

## string_xrefs

- `0x1800cd62b`: `Output token is too small - sent in %d, needed %d`
- `0x1800cd4a9`: `Trying to initialize a context with no output token!`
- `0x1800cd896`: `Failed to create client context: 0x%x`
- `0x1800cd9f8`: `Failed to create session key entry: 0x%x`
- `0x1800cceb3`: `Trying to use local service credentials for outbound authentication`
- `0x1800cd00e`: `Attempting to use cached Service Ticket for local user Kerberos`
- `0x1800ccfd4`: `Attempting to get auth ticket through IAKerb`
- `0x1800cd252`: `Getting service ticket for S4UProxy`
- `0x1800cd379`: `Failed to get serviceticket: STATUS_USER2USER_REQUIRED`
- `0x1800cd2d5`: `Getting service ticket`
- `0x1800cd3d3`: `Failed to get outbound ticket, KerbGetServiceTicket %s failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SpInitLsaModeContextExCore(struct SecurityContextParameters *this, struct SpInitState *a2)
{
  const void *v4; // rax
  int v5; // edx
  struct _KERBEROS_LIST_ENTRY *v6; // rcx
  int ChannelBindings; // eax
  int *v8; // r14
  bool v9; // al
  __int64 v10; // rcx
  _BOOL8 v11; // rcx
  int v12; // eax
  char IsEnabled; // al
  struct _KERB_CREDENTIAL *v14; // rcx
  int v15; // eax
  struct _KERB_LOGON_SESSION *v16; // rax
  struct _KERB_LOGON_SESSION *v17; // rcx
  __int64 v18; // rax
  char v19; // al
  struct _KERB_CREDENTIAL **v20; // r12
  int v21; // eax
  const char *v22; // r9
  __int64 v23; // r8
  __int64 v24; // rcx
  int v25; // edi
  int v26; // eax
  struct _KERB_LOGON_SESSION *LogonSession; // rax
  int v28; // edi
  struct _KERB_CREDENTIAL *v29; // r10
  unsigned int v30; // edx
  __int64 v31; // rax
  const void *v32; // rax
  const void *v33; // rax
  struct _KERB_INTERNAL_NAME *v34; // rdx
  int S4UProxyEvidence; // eax
  int updated; // eax
  __int64 v37; // rax
  bool IsUsableServiceTicketInCache; // al
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rcx
  struct _KERB_INTERNAL_NAME **v42; // r13
  int ServiceTicketByS4UProxy; // eax
  int v44; // ecx
  const char *v45; // rax
  struct _UNICODE_STRING *v46; // r13
  int v47; // ecx
  PVOID v48; // r8
  unsigned __int8 v49; // cl
  void **v50; // rdi
  DWORD *v51; // r12
  int v52; // eax
  int v53; // ecx
  _WORD *v54; // rax
  int v55; // eax
  unsigned int v56; // edx
  DWORD v57; // ebx
  struct _SecBuffer *OutputToken; // rax
  size_t v59; // rcx
  struct _SecBuffer *v60; // rax
  struct _KERB_TICKET_CACHE_ENTRY *v61; // rbx
  struct _KERB_CONTEXT *v62; // rdi
  struct _SecBuffer *v63; // rax
  const void *v64; // rdi
  size_t v65; // rbx
  struct _SecBuffer *v66; // rax
  void *v67; // rbx
  unsigned int v68; // ebx
  unsigned int *v69; // rbx
  SecurityContextParameters *v70; // rcx
  struct _KERB_CONTEXT *v71; // rcx
  unsigned int v72; // edx
  unsigned int v73; // r8d
  unsigned int v74; // r10d
  struct _KERB_TICKET_CACHE_ENTRY **v75; // rbx
  char *v76; // rdi
  struct _KERB_TICKET_CACHE_ENTRY *v77; // rcx
  struct _UNICODE_STRING *v78; // [rsp+20h] [rbp-59h]
  PCUNICODE_STRING String1; // [rsp+28h] [rbp-51h]
  struct _UNICODE_STRING *v80; // [rsp+30h] [rbp-49h]
  struct _UNICODE_STRING *v81; // [rsp+38h] [rbp-41h]
  struct _UNICODE_STRING *v82; // [rsp+40h] [rbp-39h]
  union _LARGE_INTEGER *v83; // [rsp+48h] [rbp-31h]
  struct _KERB_CONTEXT **v84; // [rsp+50h] [rbp-29h]
  union _LARGE_INTEGER *v85; // [rsp+58h] [rbp-21h]
  struct _KERB_TICKET_CACHE_ENTRY **v86; // [rsp+60h] [rbp-19h]
  struct _GUID *v87; // [rsp+68h] [rbp-11h]
  struct _GUID *v88; // [rsp+70h] [rbp-9h]
  struct _UNICODE_STRING **v89; // [rsp+80h] [rbp+7h]
  __int128 v90; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v91; // [rsp+98h] [rbp+1Fh]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+E0h] [rbp+67h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+F0h] [rbp+77h] BYREF
  struct _KERB_LOGON_SESSION *v94; // [rsp+F8h] [rbp+7Fh] BYREF

  v94 = 0;
  SystemTime.QuadPart = 0;
  if ( *((_QWORD *)this + 6) )
    v4 = (const void *)*((unsigned __int16 *)this + 25);
  else
    v4 = 0;
  KerbTracerT::Log(7, "SpInitLsaModeContextExCore", 1909, "ContextHandle %p called", v4);
  if ( KerbEventTraceFlag )
  {
    *((_OWORD *)a2 + 21) = KerbInitSCGuid;
    *((_BYTE *)a2 + 316) = 1;
    *((_DWORD *)a2 + 89) = 0x20000;
    *((_WORD *)a2 + 156) = 48;
    EtwLogTraceEvent(KerbTraceLoggerHandle, (char *)a2 + 312);
  }
  if ( !KerbGlobalInitialized )
  {
    v5 = -1073741604;
    *((_DWORD *)a2 + 1) = -1073741604;
LABEL_8:
    KerbLogDebugStatus("SpInitLsaModeContextExCore", v5);
    return;
  }
  v6 = (struct _KERBEROS_LIST_ENTRY *)*((_QWORD *)this + 6);
  if ( v6 )
  {
    ChannelBindings = KerbReferenceContext(v6, 0, (struct _KERB_CONTEXT **)a2 + 9);
    v8 = (int *)((char *)a2 + 4);
    *((_DWORD *)a2 + 1) = ChannelBindings;
    if ( ChannelBindings < 0 )
    {
LABEL_12:
      v5 = ChannelBindings;
      goto LABEL_8;
    }
  }
  else
  {
    v8 = (int *)((char *)a2 + 4);
  }
  v9 = TryInitiateIAKerb(this, a2);
  v5 = *v8;
  if ( v9 || v5 < 0 )
    goto LABEL_8;
  KerbTracerT::Log(3, "SpInitLsaModeContextExCore", 1952, "Not starting or continuing an IAKerb INIT loop");
  **((_DWORD **)this + 12) = 0;
  **((_QWORD **)this + 10) = 0;
  **((union _LARGE_INTEGER **)this + 13) = KerbGlobalHasNeverTime;
  **((_BYTE **)this + 14) = 0;
  *(_QWORD *)(*((_QWORD *)this + 15) + 8LL) = 0;
  **((_DWORD **)this + 15) = 0;
  ((void (__fastcall *)(char *))LsaFunctions->GetExtendedCallFlags)((char *)a2 + 196);
  if ( (*((_BYTE *)a2 + 196) & 4) != 0 )
    *((_DWORD *)a2 + 52) |= 0x80000u;
  if ( (*((_BYTE *)this + 64) & 1) != 0 )
  {
    *((_BYTE *)a2 + 219) = 1;
    *((_DWORD *)this + 16) = *((_DWORD *)this + 16) & 0xFFEFFFFE | 0x100000;
  }
  else if ( (*((_DWORD *)this + 16) & 0x100000) != 0 )
  {
    *((_BYTE *)a2 + 220) = 1;
  }
  KerbProcessSpInitTargetNames(this, a2);
  v5 = *v8;
  if ( *v8 < 0 )
    goto LABEL_8;
  ChannelBindings = SspGetChannelBindings(v10, *((_QWORD *)this + 9), (char *)a2 + 304);
  *v8 = ChannelBindings;
  if ( ChannelBindings < 0 )
    goto LABEL_12;
  if ( (*((_DWORD *)this + 16) & 0x20000000) != 0 )
    *((_DWORD *)a2 + 29) |= 0x20000000u;
  if ( *((_QWORD *)this + 6) )
  {
    KerbContinueSpInit(this, a2);
    if ( SpInitState::IsContinuationFinished(a2) )
      return;
  }
  else
  {
    KerbTracerT::Log(9, "SpInitLsaModeContextExCore", 2038, "First call to Initialize");
  }
  v11 = *((_QWORD *)a2 + 9) != 0;
  if ( *((_QWORD *)a2 + 28) || *((_QWORD *)a2 + 31) || (v12 = 0, *((_DWORD *)a2 + 20) == 7) )
    v12 = 1;
  if ( v12 != v11 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_Phase2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NTLMless_Phase2>::GetImpl'::`2'::impl);
  v14 = (struct _KERB_CREDENTIAL *)*((_QWORD *)this + 5);
  if ( IsEnabled )
  {
    v20 = (struct _KERB_CREDENTIAL **)((char *)a2 + 32);
    v25 = KerbReferenceCredentialEx(v14, 0x80000002, 0, 0, (struct _KERB_CREDENTIAL **)a2 + 4);
    *v8 = v25;
    if ( v25 < 0 )
    {
      v26 = KerbReferenceCredentialEx(
              *((struct _KERB_CREDENTIAL **)this + 5),
              2u,
              0,
              0,
              (struct _KERB_CREDENTIAL **)a2 + 4);
      *v8 = v26;
      if ( v26 < 0 || *((_QWORD *)*v20 + 9) )
      {
        KerbTracerT::Log(
          2,
          "SpInitLsaModeContextExCore",
          2174,
          "Failed to locate credential 0x%x, InitialStatus %#x",
          v26,
          v25);
        *v8 = v25;
        v5 = v25;
        goto LABEL_8;
      }
    }
    *(_QWORD *)((char *)a2 + 12) = *(_QWORD *)((char *)*v20 + 28);
    LogonSession = KerbLocateLogonSession((const struct _LUID *)((char *)a2 + 12), 0);
    *((_QWORD *)a2 + 3) = LogonSession;
    if ( !LogonSession )
    {
      v5 = -1073741729;
      goto LABEL_69;
    }
  }
  else
  {
    SystemTimeAsFileTime = 0;
    v15 = KerbReferenceCredentialEx(v14, 2u, 0, 0, (struct _KERB_CREDENTIAL **)&SystemTimeAsFileTime);
    *v8 = v15;
    if ( v15 < 0 )
    {
      KerbTracerT::Log(2, "SpInitLsaModeContextExCore", 2067, "Failed to locate credential 0x%x", v15);
      v5 = *v8;
      goto LABEL_8;
    }
    *(_QWORD *)((char *)a2 + 12) = *(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 28LL);
    v16 = KerbLocateLogonSession((const struct _LUID *)((char *)a2 + 12), 0);
    v17 = v16;
    *((_QWORD *)a2 + 3) = v16;
    if ( !v16 )
    {
      v5 = -1073741729;
LABEL_41:
      *v8 = v5;
      goto LABEL_8;
    }
    if ( (*((_DWORD *)v16 + 226) & 0x800) != 0
      && !(_BYTE)KerbGlobalRoles
      && !*(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 72LL) )
    {
      v5 = -1073741477;
      goto LABEL_41;
    }
    v18 = *(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 72LL);
    if ( v18 )
    {
      v19 = *(_BYTE *)(v18 + 411) & 1;
    }
    else
    {
      v19 = 0;
      if ( (*((_DWORD *)v17 + 132) & 0x1000000) != 0 )
      {
        v20 = (struct _KERB_CREDENTIAL **)((char *)a2 + 32);
        goto LABEL_49;
      }
    }
    v20 = (struct _KERB_CREDENTIAL **)((char *)a2 + 32);
    if ( v19 )
    {
LABEL_49:
      *v20 = (struct _KERB_CREDENTIAL *)SystemTimeAsFileTime;
      goto LABEL_50;
    }
    v21 = KerbReferenceCredentialEx(
            *((struct _KERB_CREDENTIAL **)this + 5),
            0x80000002,
            0,
            0,
            (struct _KERB_CREDENTIAL **)a2 + 4);
    *v8 = v21;
    if ( v21 < 0 )
    {
      if ( *(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 72LL) )
      {
        v22 = "Failed to locate credential and get TGT 0x%x";
        v23 = 2137;
LABEL_58:
        LODWORD(v78) = v21;
        v24 = 2;
LABEL_59:
        KerbTracerT::Log(
          v24,
          "SpInitLsaModeContextExCore",
          v23,
          v22,
          v78,
          String1,
          v80,
          v81,
          v82,
          v83,
          v84,
          v85,
          v86,
          v87,
          v88);
LABEL_60:
        v5 = *v8;
        goto LABEL_8;
      }
      *v20 = (struct _KERB_CREDENTIAL *)SystemTimeAsFileTime;
      *v8 = 0;
    }
  }
LABEL_50:
  if ( (*((_BYTE *)a2 + 196) & 4) != 0 && !*((_QWORD *)*v20 + 9) )
    goto LABEL_52;
  wil::EnterCriticalSection(&SystemTimeAsFileTime, *((_QWORD *)a2 + 3) + 80LL);
  v28 = *(_DWORD *)(*((_QWORD *)a2 + 3) + 904LL);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&SystemTimeAsFileTime);
  v29 = *v20;
  if ( *((_QWORD *)*v20 + 9) )
  {
    KerbTracerT::Log(3, "SpInitLsaModeContextExCore", 2242, "Should get auth ticket with supplied creds");
    goto LABEL_108;
  }
  if ( (*((_DWORD *)v29 + 16) & 0x20000000) != 0 || (v30 = *((_DWORD *)this + 16), (v30 & 0x40000) != 0) )
  {
    *((_BYTE *)a2 + 216) = 1;
    *((_DWORD *)a2 + 51) |= 0x40000u;
  }
  else if ( (v28 & 0xF000) != 0 )
  {
    v31 = *((_QWORD *)a2 + 3);
    if ( (v28 & 0x100) == 0 )
    {
      if ( v31 )
        v32 = (const void *)*((unsigned __int16 *)a2 + 13);
      else
        v32 = 0;
      KerbTracerT::Log(1, "SpInitLsaModeContextExCore", 2259, "Calling ISC from a nondelegatable S4U ls (%p)", v32);
      goto LABEL_52;
    }
    if ( v31 )
      v33 = (const void *)*((unsigned __int16 *)a2 + 13);
    else
      v33 = 0;
    KerbTracerT::Log(21, "SpInitLsaModeContextExCore", 2267, "Trying S4UProxy for ls %p", v33);
    S4UProxyEvidence = KerbGetS4UProxyEvidence(
                         *((struct _KERB_LOGON_SESSION **)a2 + 3),
                         v34,
                         *v20,
                         &v94,
                         (struct _KERB_TICKET_CACHE_ENTRY **)a2 + 37);
    *v8 = S4UProxyEvidence;
    if ( S4UProxyEvidence < 0 )
    {
      v90 = 0;
      v91 = 0;
      ((void (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v90);
      KerbTracerT::Log(
        1,
        "SpInitLsaModeContextExCore",
        2290,
        "Failed to get S4UProxy Evidence ticket %x, caller process id %d for %#x:%#x",
        *v8,
        (_DWORD)v90,
        *(_DWORD *)(*((_QWORD *)a2 + 3) + 68LL),
        *(_DWORD *)(*((_QWORD *)a2 + 3) + 64LL));
LABEL_52:
      v5 = -2146893042;
LABEL_69:
      *v8 = v5;
      goto LABEL_8;
    }
  }
  else
  {
    if ( *((_DWORD *)a2 + 3) == 997 && !*((_DWORD *)a2 + 4) )
    {
      KerbTracerT::Log(
        2,
        "SpInitLsaModeContextExCore",
        2308,
        "Trying to use local service credentials for outbound authentication");
      goto LABEL_52;
    }
    if ( v29 && (*((_BYTE *)v29 + 64) & 0x10) != 0 || (*((_BYTE *)a2 + 196) & 4) != 0 )
    {
      KerbTracerT::Log(
        1,
        "SpInitLsaModeContextExCore",
        2333,
        "Autologon restricted for %#x:%#x",
        *(_DWORD *)(*((_QWORD *)a2 + 3) + 68LL),
        *(_DWORD *)(*((_QWORD *)a2 + 3) + 64LL));
      goto LABEL_52;
    }
    updated = KerbCheckCredMgrForGivenTarget(
                *((struct _KERB_LOGON_SESSION **)a2 + 3),
                v29,
                *((struct _UNICODE_STRING **)this + 7),
                *((struct _KERB_INTERNAL_NAME **)a2 + 21),
                (v30 >> 5) & 4,
                (struct _UNICODE_STRING *)((char *)a2 + 136),
                0,
                (struct _KERB_CREDMAN_CRED **)a2 + 5,
                (unsigned __int8 **)a2 + 6,
                (unsigned int *)a2 + 14);
    *v8 = updated;
    if ( updated < 0 )
    {
      v22 = "Failed to get outbound ticket, KerbCheckCredMgrForGivenTarget failed with 0x%x";
      v23 = 2367;
LABEL_94:
      LODWORD(v78) = updated;
LABEL_95:
      v24 = 1;
      goto LABEL_59;
    }
    if ( *((_QWORD *)a2 + 5) )
    {
      KerbTracerT::Log(3, "SpInitLsaModeContextExCore", 2374, "Should get auth ticket with credman creds");
      *((_DWORD *)a2 + 50) &= ~0x2000u;
    }
    else
    {
      v37 = *((_QWORD *)a2 + 67);
      if ( v37 && *(_DWORD *)(v37 + 216) )
      {
        KerbTracerT::Log(3, "SpInitLsaModeContextExCore", 2379, "Attempting to get auth ticket through IAKerb");
      }
      else if ( (*((_DWORD *)*v20 + 16) & 0x8000000) != 0 )
      {
        IsUsableServiceTicketInCache = KerbIsUsableServiceTicketInCache(a2);
        if ( *((_BYTE *)a2 + 216) || *((_QWORD *)a2 + 37) || !IsUsableServiceTicketInCache )
        {
          KerbTracerT::Log(
            2,
            "SpInitLsaModeContextExCore",
            2398,
            "Trying to use a local logon session with Kerberos but IAKerb and Local KDC also failed");
          v5 = -1073741730;
          goto LABEL_69;
        }
        KerbTracerT::Log(
          3,
          "SpInitLsaModeContextExCore",
          2394,
          "Attempting to use cached Service Ticket for local user Kerberos");
      }
    }
  }
LABEL_108:
  wil::EnterCriticalSection(&SystemTimeAsFileTime, *((_QWORD *)a2 + 3) + 80LL);
  KerbTracerT::Log(
    9,
    "SpInitLsaModeContextExCore",
    2414,
    "Initailizing context for %wZ\\%wZ",
    *((_QWORD *)a2 + 3) + 136LL,
    *((_QWORD *)a2 + 3) + 120LL);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&SystemTimeAsFileTime);
  KerbProcessSpInitFlags(this, a2);
  v5 = *v8;
  if ( *v8 < 0 )
    goto LABEL_8;
  v89 = (struct _UNICODE_STRING **)((char *)this + 56);
  if ( *((_BYTE *)a2 + 216) )
  {
    v46 = (struct _UNICODE_STRING *)((char *)a2 + 204);
    *((_DWORD *)a2 + 51) &= 0x40D00u;
    v47 = *((_DWORD *)a2 + 51);
    v89 = (struct _UNICODE_STRING **)((char *)this + 56);
  }
  else
  {
    KerbTracerT::Log(
      9,
      "SpInitLsaModeContextExCore",
      2450,
      "Getting outbound ticket for %wZ (%wZ)",
      *((_QWORD *)this + 7),
      (char *)a2 + 120);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF__KERB_NAME_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_7762c21234cf3b78a2e4f6ed9e5abd41_Traceguids,
        *((_QWORD *)a2 + 21));
    kerb_context_lock::reader(&v90);
    v39 = *((_QWORD *)a2 + 28);
    if ( v39 )
    {
      if ( *(_DWORD *)(v39 + 52) == 37 )
      {
        v40 = *((_QWORD *)a2 + 9);
        v41 = *(_QWORD *)(v40 + 272);
        if ( v41 )
        {
          *((_QWORD *)a2 + 8) = v41;
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v40 + 272) + 16LL));
        }
      }
    }
    kerb_context_lock::~kerb_context_lock((kerb_context_lock *)&v90);
    if ( !*((_QWORD *)a2 + 8) )
    {
      if ( (*((_DWORD *)a2 + 52) & 0x40000) != 0 )
      {
        KerbFreeString((__int64)a2 + 136);
        v42 = (struct _KERB_INTERNAL_NAME **)((char *)a2 + 168);
        KerbFreeKdcName((struct _KERB_INTERNAL_NAME **)a2 + 21);
        KerbTracerT::Log(2, "SpInitLsaModeContextExCore", 2491, "Could not achieve server auth.");
        v21 = KerbProcessTargetNames(
                (const struct _UNICODE_STRING *)((char *)a2 + 152),
                0,
                0,
                0,
                1,
                (unsigned int *)a2 + 50,
                (struct _KERB_INTERNAL_NAME **)a2 + 21,
                (struct _UNICODE_STRING *)((char *)a2 + 136));
        *v8 = v21;
        if ( v21 < 0 )
        {
          v22 = "Failed to process name from server error message failed with 0x%x";
          v23 = 2506;
          goto LABEL_58;
        }
      }
      else
      {
        v42 = (struct _KERB_INTERNAL_NAME **)((char *)a2 + 168);
      }
      if ( *((_QWORD *)a2 + 37) )
      {
        KerbTracerT::Log(3, "SpInitLsaModeContextExCore", 2514, "Getting service ticket for S4UProxy");
        ServiceTicketByS4UProxy = KerbGetServiceTicketByS4UProxy(
                                    *((struct _RTL_CRITICAL_SECTION **)a2 + 3),
                                    v94,
                                    *((struct _KERB_CREDENTIAL **)a2 + 4),
                                    *((struct _KERB_TICKET_CACHE_ENTRY **)a2 + 37),
                                    *v42,
                                    (UNICODE_STRING *)((char *)a2 + 136),
                                    *((_DWORD *)a2 + 50),
                                    0,
                                    0,
                                    *((struct KERB_ERROR **)a2 + 28),
                                    0,
                                    *((struct KERB_TGT_REPLY **)a2 + 31),
                                    (struct _KERB_TICKET_CACHE_ENTRY **)a2 + 8,
                                    0);
      }
      else
      {
        KerbTracerT::Log(3, "SpInitLsaModeContextExCore", 2534, "Getting service ticket");
        ServiceTicketByS4UProxy = KerbGetServiceTicketEx(
                                    *((struct _KERB_LOGON_SESSION **)a2 + 3),
                                    *v20,
                                    *((struct _KERB_CREDMAN_CRED **)a2 + 5),
                                    0,
                                    0,
                                    *v42,
                                    (struct _UNICODE_STRING *)((char *)a2 + 136),
                                    *((_DWORD *)a2 + 50) | (KerbGlobalUseForestSearch != 0 ? 1179652 : 1048580),
                                    0,
                                    0,
                                    *((struct KERB_ERROR **)a2 + 28),
                                    0,
                                    *((struct KERB_TGT_REPLY **)a2 + 31),
                                    (struct _KERB_TICKET_CACHE_ENTRY **)a2 + 8,
                                    0,
                                    0);
      }
      v44 = ServiceTicketByS4UProxy;
      *v8 = ServiceTicketByS4UProxy;
      if ( ServiceTicketByS4UProxy == -1073740792 )
      {
        KerbTracerT::Log(
          25,
          "SpInitLsaModeContextExCore",
          2557,
          "Failed to get serviceticket: STATUS_USER2USER_REQUIRED");
        *v8 = 0;
        *((_DWORD *)a2 + 51) |= 0x20u;
        *((_BYTE *)a2 + 217) = 1;
      }
      else if ( ServiceTicketByS4UProxy < 0 )
      {
        v45 = "(proxy)";
        if ( !*((_QWORD *)a2 + 37) )
          v45 = (const char *)&word_1800FEE0E;
        KerbTracerT::Log(
          2,
          "SpInitLsaModeContextExCore",
          2585,
          "Failed to get outbound ticket, KerbGetServiceTicket %s failed with 0x%x",
          v45,
          v44);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF__KERB_NAME_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_7762c21234cf3b78a2e4f6ed9e5abd41_Traceguids,
            *v42);
        goto LABEL_60;
      }
    }
    v46 = (struct _UNICODE_STRING *)((char *)a2 + 204);
    v47 = *((_DWORD *)a2 + 51);
    if ( (v47 & 0x420) == 0x420 )
    {
      KerbTracerT::Log(
        1,
        "SpInitLsaModeContextExCore",
        2600,
        "Client needed session key in datagram, dropping session key");
      *(_DWORD *)&v46->Length |= 0xFFFFFFDF;
      v5 = -1073741715;
      goto LABEL_69;
    }
  }
  if ( (v47 & 0x400) != 0 )
  {
    v69 = (unsigned int *)((char *)a2 + 176);
    if ( KerbAllocateNonce((PUCHAR)a2 + 176) )
    {
      if ( SecurityContextParameters::HasOutputToken(this) )
        SecurityContextParameters::GetOutputToken(v70)->cbBuffer = 0;
      goto LABEL_170;
    }
    goto LABEL_167;
  }
  if ( !SecurityContextParameters::HasOutputToken(this) )
  {
    KerbTracerT::Log(1, "SpInitLsaModeContextExCore", 2641, "Trying to initialize a context with no output token!");
LABEL_140:
    v5 = -2146893048;
    goto LABEL_69;
  }
  if ( *((_BYTE *)a2 + 216) )
  {
    v49 = 1;
LABEL_143:
    v50 = (void **)((char *)a2 + 88);
    v51 = (DWORD *)((char *)a2 + 96);
    v52 = KerbBuildEmptyApRequest(v49, (unsigned __int8 **)a2 + 11, (unsigned int *)a2 + 24);
    v53 = v52;
    goto LABEL_160;
  }
  if ( *((_BYTE *)a2 + 218) )
  {
    v49 = 0;
    goto LABEL_143;
  }
  if ( *((_BYTE *)a2 + 217) )
  {
    if ( WPP_GLOBAL_Control != v48 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF__KERB_NAME_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_7762c21234cf3b78a2e4f6ed9e5abd41_Traceguids,
        *((_QWORD *)a2 + 21));
    if ( (*((_BYTE *)this + 64) & 2) != 0 )
    {
      v54 = (_WORD *)*((_QWORD *)this + 7);
      if ( !v54 || !*v54 )
      {
        KerbTracerT::Log(
          1,
          "SpInitLsaModeContextExCore",
          2663,
          "Client wanted mutual auth, but did not supply target name");
        v5 = -2146893054;
        goto LABEL_69;
      }
    }
    v51 = (DWORD *)((char *)a2 + 96);
    v50 = (void **)((char *)a2 + 88);
    v55 = KerbBuildTgtRequest(
            *((struct _KERB_INTERNAL_NAME **)a2 + 21),
            (struct _UNICODE_STRING *)((char *)a2 + 136),
            (unsigned int *)a2 + 52,
            (unsigned __int8 **)a2 + 11,
            (unsigned int *)a2 + 24);
    *v8 = v55;
    KerbTracerT::Log(25, "SpInitLsaModeContextExCore", 2678, "Built TGT request %#x", v55);
    v5 = *v8;
    if ( *v8 < 0 )
      goto LABEL_8;
    goto LABEL_155;
  }
  KerbTracerT::Log(14, "SpInitLsaModeContextExCore", 2684, "Building AP request for connection oriented context");
  v51 = (DWORD *)((char *)a2 + 96);
  v50 = (void **)((char *)a2 + 88);
  v88 = (struct _GUID *)*((_QWORD *)a2 + 67);
  LODWORD(v87) = *((_DWORD *)a2 + 29);
  v86 = (struct _KERB_TICKET_CACHE_ENTRY **)*((_QWORD *)a2 + 38);
  v85 = (union _LARGE_INTEGER *)((char *)a2 + 256);
  v84 = (struct _KERB_CONTEXT **)((char *)a2 + 184);
  v83 = (union _LARGE_INTEGER *)((char *)a2 + 176);
  v82 = (struct _UNICODE_STRING *)((char *)a2 + 96);
  v81 = (struct _UNICODE_STRING *)((char *)a2 + 88);
  v80 = v46;
  LODWORD(String1) = *((_DWORD *)a2 + 52);
  v78 = (struct _UNICODE_STRING *)*((_QWORD *)a2 + 28);
  v53 = KerbBuildApRequest(*((_QWORD *)a2 + 3), *((_QWORD *)a2 + 4), *((_QWORD *)a2 + 5));
  *((_DWORD *)a2 + 45) = *((_DWORD *)a2 + 44);
  v52 = v53;
LABEL_160:
  *v8 = v52;
  if ( v53 < 0 )
  {
    LODWORD(v78) = v53;
    v22 = "Failed to build AP request: 0x%x";
    v23 = 2714;
    goto LABEL_95;
  }
LABEL_155:
  if ( !SecurityContextParameters::HasOutputToken(this) )
    goto LABEL_140;
  KerbTelemetry::KerbRecordMaxTokenSize((KerbTelemetry *)*v51, v56);
  if ( (*((_DWORD *)this + 16) & 0x100) == 0 )
  {
    v57 = *v51;
    OutputToken = SecurityContextParameters::GetOutputToken(this);
    v59 = *v51;
    SystemTimeAsFileTime.dwLowDateTime = *v51;
    if ( OutputToken->cbBuffer < v57 )
    {
      v60 = SecurityContextParameters::GetOutputToken(this);
      KerbTracerT::Log(
        1,
        "SpInitLsaModeContextExCore",
        2737,
        "Output token is too small - sent in %d, needed %d",
        v60->cbBuffer,
        SystemTimeAsFileTime.dwLowDateTime);
      v61 = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)a2 + 8);
      v62 = (struct _KERB_CONTEXT *)*((_QWORD *)a2 + 9);
      v63 = SecurityContextParameters::GetOutputToken(this);
      KerbReportBufferTooSmallError(*v51, v63->cbBuffer, v62, v61);
      LODWORD(v61) = *v51;
      SecurityContextParameters::GetOutputToken(this)->cbBuffer = (unsigned int)v61;
      v5 = -1073741789;
      goto LABEL_69;
    }
    v64 = (const void *)*((_QWORD *)a2 + 11);
    v65 = v59;
    v66 = SecurityContextParameters::GetOutputToken(this);
    memcpy_0(v66->pvBuffer, v64, v65);
    goto LABEL_165;
  }
  v67 = *v50;
  SecurityContextParameters::GetOutputToken(this)->pvBuffer = v67;
  if ( !SecurityContextParameters::GetOutputToken(this)->pvBuffer )
  {
LABEL_167:
    v5 = -1073741670;
    goto LABEL_69;
  }
  **((_DWORD **)this + 12) |= 0x100u;
  *v50 = 0;
LABEL_165:
  v68 = *v51;
  SecurityContextParameters::GetOutputToken(this)->cbBuffer = v68;
  v69 = (unsigned int *)((char *)a2 + 176);
  v20 = (struct _KERB_CREDENTIAL **)((char *)a2 + 32);
LABEL_170:
  v71 = (struct _KERB_CONTEXT *)*((_QWORD *)a2 + 9);
  v72 = *((_DWORD *)a2 + 52);
  v73 = *(_DWORD *)&v46->Length;
  v74 = *v69;
  v75 = (struct _KERB_TICKET_CACHE_ENTRY **)((char *)a2 + 64);
  if ( v71 )
    updated = KerbUpdateClientContext(
                v71,
                *v75,
                v74,
                (union _LARGE_INTEGER *)a2 + 23,
                *((_DWORD *)a2 + 45),
                v73,
                v72,
                (struct SpInitState *)((char *)a2 + 256),
                (struct _UNICODE_STRING *)((char *)a2 + 152),
                &SystemTime);
  else
    updated = KerbCreateClientContext(
                (struct _KERB_LOGON_SESSION *)&SystemTime,
                *v20,
                *((struct _KERB_CREDMAN_CRED **)a2 + 5),
                *v75,
                *v89,
                v74,
                (union _LARGE_INTEGER *)a2 + 23,
                v73,
                v72,
                (struct SpInitState *)((char *)a2 + 256),
                (struct _KERB_CONTEXT **)a2 + 9,
                &SystemTime);
  *v8 = updated;
  if ( updated < 0 )
  {
    v22 = "Failed to create client context: 0x%x";
    v23 = 2846;
    goto LABEL_94;
  }
  if ( (*((_DWORD *)a2 + 3) == 999 || *((_DWORD *)a2 + 3) == 996) && !*((_DWORD *)a2 + 4) )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(_QWORD *)&SystemTimeAsFileTime += 2 * KerbGlobalSkewTime.QuadPart;
    updated = KerbCreateSKeyEntry(
                (struct _LUID *)((char *)a2 + 12),
                (struct SpInitState *)((char *)a2 + 256),
                &SystemTimeAsFileTime,
                *((void **)*v20 + 13));
    *v8 = updated;
    if ( updated < 0 )
    {
      v22 = "Failed to create session key entry: 0x%x";
      v23 = 2872;
      goto LABEL_94;
    }
  }
  kerb_context_lock::writer(&v90);
  v76 = (char *)a2 + 72;
  if ( *v75 )
  {
    v77 = *(struct _KERB_TICKET_CACHE_ENTRY **)(*(_QWORD *)v76 + 272LL);
    if ( v77 )
      KerbDereferenceTicketCacheEntry(v77);
    _InterlockedIncrement((volatile signed __int32 *)*v75 + 4);
    *(_QWORD *)(*(_QWORD *)v76 + 272LL) = *v75;
  }
  *((_DWORD *)a2 + 48) = *(_DWORD *)(*(_QWORD *)v76 + 104LL);
  kerb_context_lock::~kerb_context_lock((kerb_context_lock *)&v90);
  if ( *v8 >= 0 && *((_QWORD *)a2 + 6) )
  {
    kerb_context_lock::writer(&v90);
    if ( !*(_QWORD *)(*(_QWORD *)v76 + 344LL) )
    {
      *(_QWORD *)(*(_QWORD *)v76 + 344LL) = *((_QWORD *)a2 + 6);
      *(_DWORD *)(*(_QWORD *)v76 + 352LL) = *((_DWORD *)a2 + 14);
      *((_QWORD *)a2 + 6) = 0;
    }
    kerb_context_lock::~kerb_context_lock((kerb_context_lock *)&v90);
  }
  **((_QWORD **)this + 10) = *(_QWORD *)v76;
  **((_DWORD **)this + 12) |= *(_DWORD *)&v46->Length;
  RtlSystemTimeToLocalTime(&SystemTime, *((PLARGE_INTEGER *)this + 13));
  if ( (*(_DWORD *)&v46->Length & 0x602) != 0 || *((_BYTE *)a2 + 217) || *((_BYTE *)a2 + 218) )
    *v8 = 590610;
}

```

## disassembly

```asm
0x1800cc8a8  mov     [rsp-8+arg_8], rbx
0x1800cc8ad  push    rbp
0x1800cc8ae  push    rsi
0x1800cc8af  push    rdi
0x1800cc8b0  push    r12
0x1800cc8b2  push    r13
0x1800cc8b4  push    r14
0x1800cc8b6  push    r15
0x1800cc8b8  lea     rbp, [rsp-27h]
0x1800cc8bd  sub     rsp, 0A0h
0x1800cc8c4  mov     rsi, rdx
0x1800cc8c7  mov     r15, rcx
0x1800cc8ca  xor     edi, edi
0x1800cc8cc  mov     [rbp+57h+arg_18], rdi
0x1800cc8d0  mov     qword ptr [rbp+57h+SystemTime], rdi
0x1800cc8d4  cmp     [rcx+30h], rdi
0x1800cc8d8  jz      short loc_1800CC8E0
0x1800cc8da  movzx   eax, word ptr [rcx+32h]
0x1800cc8de  jmp     short loc_1800CC8E3
0x1800cc8e0  mov     rax, rdi
0x1800cc8e3  mov     [rsp+0D0h+var_B0], rax
0x1800cc8e8  lea     r9, aContexthandleP; "ContextHandle %p called"
0x1800cc8ef  mov     r8d, 775h
0x1800cc8f5  lea     r12, aSpinitlsamodec_28; "SpInitLsaModeContextExCore"
0x1800cc8fc  mov     rdx, r12
0x1800cc8ff  mov     ecx, 7
0x1800cc904  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cc909  cmp     cs:KerbEventTraceFlag, dil
0x1800cc910  jz      short loc_1800CC948
0x1800cc912  lea     rdx, [rsi+138h]
0x1800cc919  movups  xmm0, cs:KerbInitSCGuid
0x1800cc920  movdqu  xmmword ptr [rdx+18h], xmm0
0x1800cc925  mov     byte ptr [rsi+13Ch], 1
0x1800cc92c  mov     dword ptr [rsi+164h], 20000h
0x1800cc936  mov     word ptr [rdx], 30h ; '0'
0x1800cc93b  mov     rcx, cs:KerbTraceLoggerHandle
0x1800cc942  call    cs:__imp_EtwLogTraceEvent
0x1800cc948  cmp     cs:?KerbGlobalInitialized@@3EA, dil; uchar KerbGlobalInitialized
0x1800cc94f  jnz     short loc_1800CC97C
0x1800cc951  mov     edx, 0C00000DCh; int
0x1800cc956  mov     [rsi+4], edx
0x1800cc959  mov     rcx, r12; char *
0x1800cc95c  call    ?KerbLogDebugStatus@@YAXPEBDJ@Z; KerbLogDebugStatus(char const *,long)
0x1800cc961  mov     rbx, [rsp+0D0h+arg_8]
0x1800cc969  add     rsp, 0A0h
0x1800cc970  pop     r15
0x1800cc972  pop     r14
0x1800cc974  pop     r13
0x1800cc976  pop     r12
0x1800cc978  pop     rdi
0x1800cc979  pop     rsi
0x1800cc97a  pop     rbp
0x1800cc97b  retn
0x1800cc97c  mov     rcx, [r15+30h]; struct _KERBEROS_LIST_ENTRY *
0x1800cc980  test    rcx, rcx
0x1800cc983  jz      short loc_1800CC99F
0x1800cc985  lea     r8, [rsi+48h]; struct _KERB_CONTEXT **
0x1800cc989  xor     edx, edx; unsigned __int8
0x1800cc98b  call    ?KerbReferenceContext@@YAJ_KEPEAPEAU_KERB_CONTEXT@@@Z; KerbReferenceContext(unsigned __int64,uchar,_KERB_CONTEXT * *)
0x1800cc990  lea     r14, [rsi+4]
0x1800cc994  mov     [r14], eax
0x1800cc997  test    eax, eax
0x1800cc999  jns     short loc_1800CC9A3
0x1800cc99b  mov     edx, eax
0x1800cc99d  jmp     short loc_1800CC959
0x1800cc99f  lea     r14, [rsi+4]
0x1800cc9a3  mov     rdx, rsi; struct SpInitState *
0x1800cc9a6  mov     rcx, r15; struct SecurityContextParameters *
0x1800cc9a9  call    ?TryInitiateIAKerb@@YA_NAEAUSecurityContextParameters@@AEAUSpInitState@@@Z; TryInitiateIAKerb(SecurityContextParameters &,SpInitState &)
0x1800cc9ae  mov     edx, [r14]
0x1800cc9b1  test    al, al
0x1800cc9b3  jnz     short loc_1800CC959
0x1800cc9b5  test    edx, edx
0x1800cc9b7  js      short loc_1800CC959
0x1800cc9b9  lea     r9, aNotStartingOrC; "Not starting or continuing an IAKerb IN"...
0x1800cc9c0  mov     r8d, 7A0h
0x1800cc9c6  mov     rdx, r12
0x1800cc9c9  mov     ecx, 3
0x1800cc9ce  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cc9d3  mov     rax, [r15+60h]
0x1800cc9d7  mov     [rax], edi
0x1800cc9d9  mov     rax, [r15+50h]
0x1800cc9dd  mov     [rax], rdi
0x1800cc9e0  mov     rcx, [r15+68h]
0x1800cc9e4  mov     rax, cs:?KerbGlobalHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalHasNeverTime
0x1800cc9eb  mov     [rcx], rax
0x1800cc9ee  mov     rax, [r15+70h]
0x1800cc9f2  mov     [rax], dil
0x1800cc9f5  mov     rax, [r15+78h]
0x1800cc9f9  mov     [rax+8], rdi
0x1800cc9fd  mov     rax, [r15+78h]
0x1800cca01  mov     [rax], edi
0x1800cca03  lea     rbx, [rsi+0C4h]
0x1800cca0a  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800cca11  mov     rcx, rbx
0x1800cca14  mov     rax, [rax+1B0h]
0x1800cca1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cca20  test    byte ptr [rbx], 4
0x1800cca23  jz      short loc_1800CCA2D
0x1800cca25  bts     dword ptr [rsi+0D0h], 13h
0x1800cca2d  test    byte ptr [r15+40h], 1
0x1800cca32  jz      short loc_1800CCA4C
0x1800cca34  mov     byte ptr [rsi+0DBh], 1
0x1800cca3b  mov     eax, [r15+40h]
0x1800cca3f  and     eax, 0FFFFFFFEh
0x1800cca42  bts     eax, 14h
0x1800cca46  mov     [r15+40h], eax
0x1800cca4a  jmp     short loc_1800CCA5D
0x1800cca4c  test    dword ptr [r15+40h], 100000h
0x1800cca54  jz      short loc_1800CCA5D
0x1800cca56  mov     byte ptr [rsi+0DCh], 1
0x1800cca5d  mov     rdx, rsi; struct SpInitState *
0x1800cca60  mov     rcx, r15; this
0x1800cca63  call    ?KerbProcessSpInitTargetNames@@YAXAEAUSecurityContextParameters@@AEAUSpInitState@@@Z; KerbProcessSpInitTargetNames(SecurityContextParameters &,SpInitState &)
0x1800cca68  mov     edx, [r14]
0x1800cca6b  test    edx, edx
0x1800cca6d  js      loc_1800CC959
0x1800cca73  lea     r8, [rsi+130h]
0x1800cca7a  mov     rdx, [r15+48h]
0x1800cca7e  call    SspGetChannelBindings
0x1800cca83  mov     [r14], eax
0x1800cca86  test    eax, eax
0x1800cca88  js      loc_1800CC99B
0x1800cca8e  mov     eax, 20000000h
0x1800cca93  test    [r15+40h], eax
0x1800cca97  jz      short loc_1800CCA9C
0x1800cca99  or      [rsi+74h], eax
0x1800cca9c  cmp     [r15+30h], rdi
0x1800ccaa0  jz      short loc_1800CCABF
0x1800ccaa2  mov     rdx, rsi; struct SpInitState *
0x1800ccaa5  mov     rcx, r15; this
0x1800ccaa8  call    ?KerbContinueSpInit@@YAXAEAUSecurityContextParameters@@AEAUSpInitState@@@Z; KerbContinueSpInit(SecurityContextParameters &,SpInitState &)
0x1800ccaad  mov     rcx, rsi; this
0x1800ccab0  call    ?IsContinuationFinished@SpInitState@@QEAA_NXZ; SpInitState::IsContinuationFinished(void)
0x1800ccab5  test    al, al
0x1800ccab7  jnz     loc_1800CC961
0x1800ccabd  jmp     short loc_1800CCAD9
0x1800ccabf  lea     r9, aFirstCallToIni; "First call to Initialize"
0x1800ccac6  mov     r8d, 7F6h
0x1800ccacc  mov     rdx, r12
0x1800ccacf  mov     ecx, 9
0x1800ccad4  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ccad9  mov     ecx, edi
0x1800ccadb  cmp     [rsi+48h], rdi
0x1800ccadf  setnz   cl
0x1800ccae2  cmp     [rsi+0E0h], rdi
0x1800ccae9  jnz     short loc_1800CCAFC
0x1800ccaeb  cmp     [rsi+0F8h], rdi
0x1800ccaf2  jnz     short loc_1800CCAFC
0x1800ccaf4  cmp     dword ptr [rsi+50h], 7
0x1800ccaf8  mov     eax, edi
0x1800ccafa  jnz     short loc_1800CCB01
0x1800ccafc  mov     eax, 1
0x1800ccb01  cmp     eax, ecx
0x1800ccb03  jz      short loc_1800CCB0A
0x1800ccb05  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ccb0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NTLMless_Phase2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_Phase2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_Phase2> `wil::Feature<__WilFeatureTraits_Feature_NTLMless_Phase2>::GetImpl(void)'::`2'::impl
0x1800ccb11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NTLMless_Phase2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NTLMless_Phase2>::__private_IsEnabled(void)
0x1800ccb16  mov     rcx, [r15+28h]; struct _KERB_CREDENTIAL *
0x1800ccb1a  xor     r9d, r9d; int
0x1800ccb1d  xor     r8d, r8d; unsigned __int8
0x1800ccb20  test    al, al
0x1800ccb22  jnz     loc_1800CCC7A
0x1800ccb28  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800ccb2c  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x1800ccb30  mov     [rsp+0D0h+var_B0], rax; struct _KERB_CREDENTIAL **
0x1800ccb35  lea     ebx, [r9+2]
0x1800ccb39  mov     edx, ebx; unsigned int
0x1800ccb3b  call    ?KerbReferenceCredentialEx@@YAJ_KKEHPEAPEAU_KERB_CREDENTIAL@@@Z; KerbReferenceCredentialEx(unsigned __int64,ulong,uchar,int,_KERB_CREDENTIAL * *)
0x1800ccb40  mov     [r14], eax
0x1800ccb43  test    eax, eax
0x1800ccb45  jns     short loc_1800CCB6A
0x1800ccb47  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800ccb4b  lea     r9, aFailedToLocate_5; "Failed to locate credential 0x%x"
0x1800ccb52  mov     r8d, 813h
0x1800ccb58  mov     rdx, r12
0x1800ccb5b  mov     ecx, ebx
0x1800ccb5d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ccb62  mov     edx, [r14]
0x1800ccb65  jmp     loc_1800CC959
0x1800ccb6a  lea     rcx, [rsi+0Ch]; struct _LUID *
0x1800ccb6e  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800ccb72  mov     rdx, [rax+1Ch]
0x1800ccb76  mov     [rcx], rdx
0x1800ccb79  xor     edx, edx; unsigned __int8
0x1800ccb7b  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x1800ccb80  mov     rcx, rax
0x1800ccb83  mov     [rsi+18h], rax
0x1800ccb87  test    rax, rax
0x1800ccb8a  jnz     short loc_1800CCB99
0x1800ccb8c  mov     edx, 0C000005Fh
0x1800ccb91  mov     [r14], edx
0x1800ccb94  jmp     loc_1800CC959
0x1800ccb99  mov     rdx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800ccb9d  test    dword ptr [rax+388h], 800h
0x1800ccba7  jz      short loc_1800CCBBF
0x1800ccba9  cmp     byte ptr cs:?KerbGlobalRoles@@3U_KerberosSystemRole@@A, dil; _KerberosSystemRole KerbGlobalRoles
0x1800ccbb0  jnz     short loc_1800CCBBF
0x1800ccbb2  cmp     [rdx+48h], rdi
0x1800ccbb6  jnz     short loc_1800CCBBF
0x1800ccbb8  mov     edx, 0C000015Bh
0x1800ccbbd  jmp     short loc_1800CCB91
0x1800ccbbf  mov     rax, [rdx+48h]
0x1800ccbc3  test    rax, rax
0x1800ccbc6  jz      short loc_1800CCC01
0x1800ccbc8  mov     al, [rax+19Bh]
0x1800ccbce  and     al, 1
0x1800ccbd0  lea     r12, [rsi+20h]
0x1800ccbd4  test    al, al
0x1800ccbd6  jz      short loc_1800CCC16
0x1800ccbd8  mov     [r12], rdx
0x1800ccbdc  test    byte ptr [rsi+0C4h], 4
0x1800ccbe3  jz      loc_1800CCD23
0x1800ccbe9  mov     rax, [r12]
0x1800ccbed  cmp     [rax+48h], rdi
0x1800ccbf1  jnz     loc_1800CCD23
0x1800ccbf7  mov     edx, 8009030Eh
0x1800ccbfc  jmp     loc_1800CCD1B
0x1800ccc01  mov     al, dil
0x1800ccc04  test    dword ptr [rcx+210h], 1000000h
0x1800ccc0e  jz      short loc_1800CCBD0
0x1800ccc10  lea     r12, [rsi+20h]
0x1800ccc14  jmp     short loc_1800CCBD8
0x1800ccc16  mov     [rsp+0D0h+var_B0], r12; struct _KERB_CREDENTIAL **
0x1800ccc1b  xor     r9d, r9d; int
0x1800ccc1e  xor     r8d, r8d; unsigned __int8
0x1800ccc21  mov     edx, 80000002h; unsigned int
0x1800ccc26  mov     rcx, [r15+28h]; struct _KERB_CREDENTIAL *
0x1800ccc2a  call    ?KerbReferenceCredentialEx@@YAJ_KKEHPEAPEAU_KERB_CREDENTIAL@@@Z; KerbReferenceCredentialEx(unsigned __int64,ulong,uchar,int,_KERB_CREDENTIAL * *)
0x1800ccc2f  mov     [r14], eax
0x1800ccc32  test    eax, eax
0x1800ccc34  jns     short loc_1800CCBDC
0x1800ccc36  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800ccc3a  cmp     [rcx+48h], rdi
0x1800ccc3e  jz      short loc_1800CCC6E
0x1800ccc40  lea     r9, aFailedToLocate_4; "Failed to locate credential and get TGT"...
0x1800ccc47  mov     r8d, 859h
0x1800ccc4d  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800ccc51  mov     ecx, ebx
0x1800ccc53  lea     rdx, aSpinitlsamodec_28; "SpInitLsaModeContextExCore"
0x1800ccc5a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ccc5f  mov     edx, [r14]
0x1800ccc62  lea     rcx, aSpinitlsamodec_28; "SpInitLsaModeContextExCore"
0x1800ccc69  jmp     loc_1800CC95C
0x1800ccc6e  mov     [r12], rcx
0x1800ccc72  mov     [r14], edi
0x1800ccc75  jmp     loc_1800CCBDC
0x1800ccc7a  lea     r12, [rsi+20h]
0x1800ccc7e  mov     [rsp+0D0h+var_B0], r12; struct _KERB_CREDENTIAL **
0x1800ccc83  mov     edx, 80000002h; unsigned int
0x1800ccc88  call    ?KerbReferenceCredentialEx@@YAJ_KKEHPEAPEAU_KERB_CREDENTIAL@@@Z; KerbReferenceCredentialEx(unsigned __int64,ulong,uchar,int,_KERB_CREDENTIAL * *)
0x1800ccc8d  mov     edi, eax
0x1800ccc8f  mov     [r14], eax
0x1800ccc92  mov     ebx, 2
0x1800ccc97  test    eax, eax
0x1800ccc99  jns     short loc_1800CCCF1
0x1800ccc9b  mov     [rsp+0D0h+var_B0], r12; struct _KERB_CREDENTIAL **
0x1800ccca0  xor     r9d, r9d; int
0x1800ccca3  xor     r8d, r8d; unsigned __int8
0x1800ccca6  mov     edx, ebx; unsigned int
0x1800ccca8  mov     rcx, [r15+28h]; struct _KERB_CREDENTIAL *
0x1800cccac  call    ?KerbReferenceCredentialEx@@YAJ_KKEHPEAPEAU_KERB_CREDENTIAL@@@Z; KerbReferenceCredentialEx(unsigned __int64,ulong,uchar,int,_KERB_CREDENTIAL * *)
0x1800cccb1  mov     [r14], eax
0x1800cccb4  xor     edx, edx
0x1800cccb6  test    eax, eax
0x1800cccb8  js      short loc_1800CCCC4
0x1800cccba  mov     rcx, [r12]
0x1800cccbe  cmp     [rcx+48h], rdx
0x1800cccc2  jz      short loc_1800CCCF1
0x1800cccc4  mov     dword ptr [rsp+0D0h+String1], edi
0x1800cccc8  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800ccccc  lea     r9, aFailedToLocate_6; "Failed to locate credential 0x%x, Initi"...
0x1800cccd3  mov     r8d, 87Eh
0x1800cccd9  lea     rdx, aSpinitlsamodec_28; "SpInitLsaModeContextExCore"
0x1800ccce0  mov     ecx, ebx
0x1800ccce2  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800ccce7  mov     [r14], edi
0x1800cccea  mov     edx, edi
0x1800cccec  jmp     loc_1800CCC62
0x1800cccf1  lea     rcx, [rsi+0Ch]; struct _LUID *
0x1800cccf5  mov     rax, [r12]
0x1800cccf9  mov     rdx, [rax+1Ch]
0x1800cccfd  mov     [rcx], rdx
0x1800ccd00  xor     edx, edx; unsigned __int8
0x1800ccd02  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x1800ccd07  mov     [rsi+18h], rax
0x1800ccd0b  xor     edi, edi
0x1800ccd0d  test    rax, rax
0x1800ccd10  jnz     loc_1800CCBDC
0x1800ccd16  mov     edx, 0C000005Fh
0x1800ccd1b  mov     [r14], edx
0x1800ccd1e  jmp     loc_1800CCC62
0x1800ccd23  mov     rdx, [rsi+18h]
0x1800ccd27  add     rdx, 50h ; 'P'
0x1800ccd2b  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x1800ccd2f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800ccd34  mov     rax, [rsi+18h]
0x1800ccd38  mov     edi, [rax+388h]
0x1800ccd3e  lea     rcx, [rbp+57h+SystemTimeAsFileTime]
0x1800ccd42  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
  ... truncated ...
```
