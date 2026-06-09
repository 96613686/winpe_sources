# NlpLogonSamLogon(void *,ushort *,ushort *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_LOGON_INFO_CLASS,_NETLOGON_LEVEL *,_NETLOGON_VALIDATION_INFO_CLASS,_NETLOGON_VALIDATION *,uchar *,ulong *,int)

- ea: `0x18002d3c0`
- end: `0x18002de87`
- name: `?NlpLogonSamLogon@@YAJPEAXPEAG1PEAU_NETLOGON_AUTHENTICATOR@@2W4_NETLOGON_LOGON_INFO_CLASS@@PEAT_NETLOGON_LEVEL@@W4_NETLOGON_VALIDATION_INFO_CLASS@@PEAT_NETLOGON_VALIDATION@@PEAEPEAKH@Z`
- size: `2759`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, unsigned __int16 *, struct _NETLOGON_AUTHENTICATOR *, struct _NETLOGON_AUTHENTICATOR *, enum _NETLOGON_LOGON_INFO_CLASS, union _NETLOGON_LEVEL *, unsigned int, unsigned __int8 **, _BYTE *, unsigned int *, int)`
- caller_count: `4`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180032650`
- `0x180032b30`
- `0x180032bb0`
- `0x180032c30`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x18000ccf0`
- `0x18000d094`
- `0x18000d710`
- `0x18000da94`
- `0x18000e270`
- `0x180025708`
- `0x18002601c`
- `0x18002c070`
- `0x18002c2f8`
- `0x18002cb3c`
- `0x18002ceb4`
- `0x18002cf9c`
- `0x18002d3c0`
- `0x18002de90`
- `0x18002e730`
- `0x18003121c`
- `0x1800361a8`
- `0x18003cb44`
- `0x18004fc34`
- `0x18004fcf8`
- `0x180050ca0`
- `0x18005378c`
- `0x18005f524`
- `0x180060820`
- `0x180064f64`
- `0x18006c248`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002d7c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002d7c6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002d55c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002dcbc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002d55c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002dcbc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002ddb2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002ddb2`
- `LSASRV!LsaIFreeHeap` at `0x18002dc9a`
- `LSASRV!LsaIFreeHeap` at `0x18002dc9a`
- `LSASRV!LsaIValidateTargetInfo` at `0x18002d9c6`
- `LSASRV!LsaIValidateTargetInfo` at `0x18002da28`
- `LSASRV!LsaIValidateTargetInfo` at `0x18002d9c6`
- `LSASRV!LsaIValidateTargetInfo` at `0x18002da28`
- `ntdll!RtlAcquireResourceShared` at `0x18002dd0e`
- `ntdll!RtlAcquireResourceShared` at `0x18002dd0e`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002d792`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002d792`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d68d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d6c0`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d6e6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d7e2`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d818`
- `ntdll!RtlLeaveCriticalSection` at `0x18002dda0`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d68d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d6c0`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d6e6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d7e2`
- `ntdll!RtlLeaveCriticalSection` at `0x18002d818`
- `ntdll!RtlLeaveCriticalSection` at `0x18002dda0`
- `ntdll!RtlEnterCriticalSection` at `0x18002d66e`
- `ntdll!RtlEnterCriticalSection` at `0x18002dce1`
- `ntdll!RtlEnterCriticalSection` at `0x18002d66e`
- `ntdll!RtlEnterCriticalSection` at `0x18002dce1`
- `ntdll!RtlInitUnicodeString` at `0x18002d997`
- `ntdll!RtlInitUnicodeString` at `0x18002d997`
- `ntdll!RtlReleaseResource` at `0x18002dd86`
- `ntdll!RtlReleaseResource` at `0x18002dd86`
- `SAMSRV!SamIMixedDomain` at `0x18002d901`
- `SAMSRV!SamIMixedDomain` at `0x18002d901`

## string_xrefs

- `0x18002d92b`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002dc06`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002dc2a`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002ddd2`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002d718`: `SamLogon: %hs logon of %wZ\%wZ from %wZ: failed RPC Security checks\n`
- `0x18002d9de`: `Failed to validate the passthrough target %#x for computer name %ws\n`
- `0x18002da40`: `Failed to validate the passthrough target %#x for computer name %ws\n`

## pseudocode

```c
__int64 __fastcall NlpLogonSamLogon(
        void *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _NETLOGON_AUTHENTICATOR *a4,
        struct _NETLOGON_AUTHENTICATOR *a5,
        enum _NETLOGON_LOGON_INFO_CLASS a6,
        union _NETLOGON_LEVEL *a7,
        unsigned int a8,
        unsigned __int8 **a9,
        _BYTE *a10,
        unsigned int *a11,
        int a12)
{
  unsigned int v15; // edx
  struct _NETLOGON_LOGON_IDENTITY_INFO *v16; // r12
  char *v17; // r9
  unsigned int v19; // edi
  struct _DOMAIN_INFO *v20; // r12
  int v21; // ebx
  struct _DOMAIN_INFO *DomainByServerName; // rax
  bool v23; // zf
  char v24; // cl
  char v25; // r12
  struct _SERVER_SESSION *v26; // r13
  unsigned int v27; // r14d
  struct _NETLOGON_LOGON_IDENTITY_INFO *v28; // rbx
  struct _RTL_CRITICAL_SECTION *v29; // rsi
  struct _SERVER_SESSION *NamedServerSession; // rax
  struct _NETLOGON_LOGON_IDENTITY_INFO *v31; // rsi
  char *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  void *v35; // rcx
  unsigned int *v36; // rsi
  char *v37; // r9
  char v38; // al
  __int64 v39; // r9
  int v40; // eax
  int v41; // eax
  int v42; // esi
  int v43; // eax
  struct _SECPKG_NTLM_TARGETINFO *v44; // r12
  struct _NETLOGON_LOGON_IDENTITY_INFO *v45; // r15
  int v46; // eax
  unsigned __int8 **v47; // rax
  LONGLONG v48; // rsi
  __int64 v49; // r14
  struct _CLIENT_SESSION *NamedClientSession; // rdi
  unsigned int *v51; // rdi
  __int64 v52; // rcx
  __int128 *v53; // rax
  unsigned __int8 **v54; // r14
  __int64 v55; // [rsp+90h] [rbp-80h] BYREF
  struct _NETLOGON_LOGON_IDENTITY_INFO *v56; // [rsp+98h] [rbp-78h]
  struct _DOMAIN_INFO *v57; // [rsp+A0h] [rbp-70h]
  bool v58; // [rsp+A8h] [rbp-68h]
  int v59; // [rsp+ACh] [rbp-64h] BYREF
  struct _SECPKG_NTLM_TARGETINFO *v60; // [rsp+B0h] [rbp-60h] BYREF
  unsigned int *v61; // [rsp+B8h] [rbp-58h]
  unsigned __int16 *v62; // [rsp+C0h] [rbp-50h]
  int v63; // [rsp+C8h] [rbp-48h]
  int v64; // [rsp+CCh] [rbp-44h]
  struct _NETLOGON_AUTHENTICATOR *p_DestinationString; // [rsp+D0h] [rbp-40h]
  void *v66; // [rsp+D8h] [rbp-38h]
  LARGE_INTEGER PerformanceCount; // [rsp+E0h] [rbp-30h] BYREF
  unsigned __int8 **v68; // [rsp+E8h] [rbp-28h]
  unsigned int v69; // [rsp+F0h] [rbp-20h]
  unsigned int v70; // [rsp+F4h] [rbp-1Ch]
  enum _NETLOGON_LOGON_INFO_CLASS v71; // [rsp+F8h] [rbp-18h]
  PSID pSid; // [rsp+100h] [rbp-10h]
  LARGE_INTEGER v73; // [rsp+108h] [rbp-8h] BYREF
  union _NETLOGON_LEVEL *v74; // [rsp+110h] [rbp+0h]
  __int128 v75; // [rsp+118h] [rbp+8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+128h] [rbp+18h] BYREF
  struct _UNICODE_STRING v77; // [rsp+138h] [rbp+28h] BYREF
  __int128 v78; // [rsp+148h] [rbp+38h] BYREF
  int v79; // [rsp+158h] [rbp+48h]
  _OWORD v80[2]; // [rsp+160h] [rbp+50h] BYREF

  v79 = 0;
  v70 = *a11;
  v15 = v70 & 0xFFFFCFFF;
  v66 = a1;
  *a11 = v70 & 0xFFFFCFFF;
  *a10 = 1;
  v62 = a3;
  v61 = a11;
  *a9 = 0;
  v74 = a7;
  v16 = *(struct _NETLOGON_LOGON_IDENTITY_INFO **)a7;
  v56 = *(struct _NETLOGON_LOGON_IDENTITY_INFO **)a7;
  v68 = a9;
  p_DestinationString = a5;
  DestinationString = 0;
  v69 = v15;
  v78 = 0;
  PerformanceCount.QuadPart = 0;
  memset(v80, 0, sizeof(v80));
  v73.QuadPart = 0;
  v60 = 0;
  v59 = 0;
  if ( !(unsigned int)NlStartNetlogonCall() )
    return 3221225874LL;
  v19 = a6;
  v71 = a6;
  if ( !v16 )
  {
    v20 = 0;
    v21 = -1073741811;
LABEL_5:
    LODWORD(v55) = v21;
LABEL_162:
    v31 = v56;
    goto LABEL_163;
  }
  DomainByServerName = NlFindDomainByServerName(a2);
  v20 = DomainByServerName;
  v57 = DomainByServerName;
  if ( (NlGlobalParameters & 4) != 0 )
    NlPrintLogonParameters(DomainByServerName, v62, a6, v74, *v61, 0);
  if ( !v20 )
  {
    v21 = -1073741534;
    goto LABEL_5;
  }
  if ( a8 != 2 && a8 != 3 && a8 != 4 && a8 != 5 && a8 - 6 >= 2 )
  {
LABEL_15:
    *a10 = 1;
    v21 = -1073741821;
    goto LABEL_5;
  }
  switch ( a6 )
  {
    case 1:
    case 2:
    case 3:
      goto LABEL_33;
    case 4:
      if ( a8 == 4 )
        goto LABEL_26;
      v23 = a8 == 5;
      break;
    case 5:
    case 6:
    case 7:
LABEL_33:
      if ( a8 == 2 || a8 == 3 )
        goto LABEL_26;
      v23 = a8 == 6;
      break;
    case 8:
      v23 = a8 == 7;
      break;
    default:
      goto LABEL_15;
  }
  if ( !v23 )
    goto LABEL_15;
LABEL_26:
  if ( !QueryPerformanceCounter(&PerformanceCount) )
    PerformanceCount.QuadPart = 0;
  if ( ((a6 - 2) & 0xFFFFFFFB) != 0 )
  {
    BYTE4(v55) = 0;
  }
  else
  {
    BYTE4(v55) = 1;
    if ( a6 == NetlogonNetworkTransitiveInformation )
    {
LABEL_37:
      v24 = 1;
      goto LABEL_38;
    }
  }
  v24 = 0;
  if ( ((a6 - 5) & 0xFFFFFFFD) == 0 )
    goto LABEL_37;
LABEL_38:
  v58 = (unsigned int)(a6 - 1) <= 2;
  if ( v24 || (v25 = 0, (unsigned int)(a6 - 1) <= 2) )
    v25 = 1;
  if ( !v25 && ((a6 - 4) & 0xFFFFFFFB) != 0 )
  {
    *a10 = 1;
    v21 = -1073741821;
LABEL_44:
    v20 = v57;
    LODWORD(v55) = v21;
    goto LABEL_162;
  }
  pSid = 0;
  if ( a12 )
  {
    v26 = 0;
    v79 = 19894271;
    v27 = 1;
    v64 = 0;
    v63 = 0;
    LODWORD(v66) = *((_DWORD *)v57 + 90);
    v28 = v56;
    p_DestinationString = 0;
LABEL_73:
    if ( NlGlobalMemberWorkstation || v27 != 1 )
    {
      v36 = v61;
      goto LABEL_77;
    }
LABEL_75:
    v36 = v61;
    *v61 |= 0x2000u;
LABEL_77:
    if ( a6 != 8
      || (LODWORD(v55) = IsTicketLogonRequestSupported(
                           (struct _NETLOGON_TICKET_LOGON_INFO *const)v28,
                           (*v36 & 0x2000) != 0),
          v21 = v55,
          (int)v55 >= 0) )
    {
      if ( v27 == 2
        && v25
        && ((dword_1800F11BC & 5) != 0 || (dword_1800F11C0 & 5) != 0)
        && (unsigned int)NlIsTargetAllowed(v62) )
      {
        *v36 |= 0x1000u;
      }
      if ( (NlGlobalServiceStatus.dwCurrentState == 7 || !dword_1800F124C || NlGlobalDsPaused) && v27 != 1 && v27 != 6 )
      {
        v20 = v57;
        v21 = -1073741790;
        LODWORD(v55) = -1073741790;
        *a10 = 0;
        goto LABEL_160;
      }
      if ( v58 )
      {
        if ( v27 - 1 > 1 )
          goto LABEL_121;
        v20 = v57;
        if ( !(unsigned __int8)SamIMixedDomain(*((_QWORD *)v57 + 46)) || (v79 & 0xBFFFFE00) != 0 )
        {
          switch ( a6 )
          {
            case NetlogonInteractiveInformation:
              v19 = 5;
              break;
            case NetlogonNetworkInformation:
              v19 = 6;
              break;
            case NetlogonServiceInformation:
              v19 = 7;
              break;
            default:
              NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx", 0x198Du, v37);
              v21 = -1073741821;
              *a10 = 0;
              LODWORD(v55) = -1073741821;
LABEL_160:
              if ( pSid )
                FreeSid(pSid);
              goto LABEL_162;
          }
        }
      }
      else
      {
        v20 = v57;
      }
      if ( v27 == 2 )
      {
        v38 = BYTE4(v55);
        if ( !BYTE4(v55) )
        {
          if ( a6 == NetlogonGenericInformation )
          {
            v41 = LsaIValidateTargetInfo(
                    &v56[1],
                    *(_QWORD *)&v56[1].LogonId.HighPart,
                    v56[1].ParameterControl,
                    *((_QWORD *)v20 + 23),
                    v80);
            LODWORD(v55) = v41;
            v21 = v41;
            if ( v41 < 0 )
            {
              NlPrintRoutine(
                0x100u,
                L"Failed to validate the passthrough target %#x for computer name %ws\n",
                (unsigned int)v41,
                v80);
              goto LABEL_152;
            }
            v38 = BYTE4(v55);
          }
          goto LABEL_112;
        }
        v77 = 0;
        v75 = 0;
        RtlInitUnicodeString(&v77, L"NTLM");
        v39 = *((_QWORD *)v20 + 23);
        *((_QWORD *)&v75 + 1) = v56;
        LODWORD(v75) = 2;
        v40 = LsaIValidateTargetInfo(&v77, &v75, 16, v39, v80);
        LODWORD(v55) = v40;
        v21 = v40;
        if ( v40 < 0 )
        {
          NlPrintRoutine(
            0x100u,
            L"Failed to validate the passthrough target %#x for computer name %ws\n",
            (unsigned int)v40,
            v80);
          *a10 = 1;
LABEL_152:
          if ( v21 >= 0 && PerformanceCount.QuadPart && QueryPerformanceCounter(&v73) )
          {
            v48 = v73.QuadPart - PerformanceCount.QuadPart;
            v49 = *((_QWORD *)v20 + 44);
            RtlEnterCriticalSection(&NlGlobalDomainCritSect);
            NamedClientSession = NlFindNamedClientSession(NlGlobalDomainInfo, (struct _UNICODE_STRING *)v20 + 8, 4u, 0);
            RtlAcquireResourceShared(&NlPcGlobalLock, 1u);
            if ( NamedClientSession )
            {
              NlPcIncrement64(*((_QWORD *)NamedClientSession + 84), 6, v48);
              NlPcIncrement32(*((_QWORD *)NamedClientSession + 84), 7);
            }
            NlPcIncrement64(v49, 6, v48);
            NlPcIncrement64(NlPcGlobalTotalInstance, 6, v48);
            NlPcIncrement32(v49, 7);
            NlPcIncrement32(NlPcGlobalTotalInstance, 7);
            RtlReleaseResource(&NlPcGlobalLock);
            if ( NamedClientSession )
              NlUnrefClientSession(NamedClientSession);
            RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
          }
          goto LABEL_160;
        }
        v38 = BYTE4(v55);
LABEL_122:
        if ( !NlGlobalMemberWorkstation && v26 && v27 == 2 )
        {
          v42 = 1;
          goto LABEL_118;
        }
LABEL_112:
        v42 = 0;
        if ( NlGlobalMemberWorkstation || !v38 || v27 != 2 && v27 != 7 && v27 != 3 && v27 != 4 )
        {
          v44 = v60;
LABEL_129:
          v45 = v56;
          LODWORD(v55) = NlpUserValidate(
                           v57,
                           v27,
                           (unsigned int)v66,
                           v19,
                           v56,
                           a8,
                           v68,
                           a10,
                           v61,
                           0,
                           v62,
                           p_DestinationString,
                           v64,
                           v63,
                           pSid,
                           v26,
                           v44,
                           v59,
                           v55);
          v21 = v55;
          if ( (int)v55 >= 0 )
          {
            if ( (_DWORD)v55 )
              NlAssertFailed(
                "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                0x1A3Au,
                v17);
            v47 = v68;
            if ( !*v68 )
            {
              NlAssertFailed(
                "!NT_SUCCESS(Status) || ValidationInformation->ValidationSam != NULL",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                0x1A3Bu,
                v17);
              v47 = v68;
            }
            if ( v27 != 1 )
              NlpEncryptValidationInformation(v19, a8, *v47, &v78);
            v21 = 0;
            LODWORD(v55) = 0;
            goto LABEL_146;
          }
          if ( (v79 & 1) != 0 )
            goto LABEL_136;
          if ( (_DWORD)v55 == -1073741276 )
          {
            v21 = -1073741711;
            goto LABEL_138;
          }
          if ( (_DWORD)v55 != -1073741260 )
          {
LABEL_136:
            if ( (_DWORD)v55 != -1073740781 || v79 )
            {
LABEL_146:
              if ( v42 )
                NlpNtlmlessLogServerDomain(v45, v26, v44, v59, v21);
              goto LABEL_149;
            }
            v21 = -1073741724;
          }
          else
          {
            v21 = -1073741710;
          }
LABEL_138:
          LODWORD(v55) = v21;
          goto LABEL_146;
        }
LABEL_118:
        v43 = NlpExtractNtlmTargetInfo(v56, &v60, &v59);
        LODWORD(v55) = v43;
        v21 = v43;
        if ( v43 < 0 )
        {
          NlPrintRoutine(4u, L"NlpExtractNtlmTargetInfo failed Status:0x%x\n", (unsigned int)v43);
          v44 = v60;
LABEL_120:
          v45 = v56;
          goto LABEL_146;
        }
        v44 = v60;
        v46 = NlpValidateNTLMTargetInfo(v27, v26, v56, v57, v60, v59);
        LODWORD(v55) = v46;
        v21 = v46;
        if ( v46 < 0 )
        {
          NlPrintRoutine(4u, L"NlpValidateNTLMTargetInfo failed Status:0x%x\n", (unsigned int)v46);
          goto LABEL_120;
        }
        goto LABEL_129;
      }
LABEL_121:
      v38 = BYTE4(v55);
      if ( !BYTE4(v55) )
        goto LABEL_112;
      goto LABEL_122;
    }
LABEL_59:
    *a10 = 0;
LABEL_151:
    v20 = v57;
    goto LABEL_152;
  }
  if ( NlGlobalMemberWorkstation )
  {
    v21 = -1073741637;
    goto LABEL_44;
  }
  if ( !a2 || !v62 || (!a4 || !a5) && !a1 )
  {
    v44 = v60;
    v21 = -1073741811;
    LODWORD(v55) = -1073741811;
    *a10 = 1;
LABEL_149:
    if ( v44 )
      LsaIFreeHeap(v44, 0);
    goto LABEL_151;
  }
  v29 = (struct _RTL_CRITICAL_SECTION *)((char *)v57 + 504);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v57 + 504));
  NamedServerSession = NlFindNamedServerSession(v57, v62);
  v26 = NamedServerSession;
  if ( !NamedServerSession )
  {
    RtlLeaveCriticalSection(v29);
    *a10 = 0;
    v21 = -1073741790;
    goto LABEL_44;
  }
  if ( a4 )
  {
    LODWORD(v55) = NlCheckAuthenticator(NamedServerSession, a4, p_DestinationString);
    v21 = v55;
    if ( (int)v55 < 0 )
    {
      RtlLeaveCriticalSection(v29);
      goto LABEL_59;
    }
LABEL_62:
    v27 = *((_DWORD *)v26 + 8);
    v78 = *((_OWORD *)v26 + 6);
    v79 = *((_DWORD *)v26 + 18);
    v35 = (void *)*((_QWORD *)v26 + 19);
    LODWORD(v66) = *((_DWORD *)v26 + 13);
    v64 = *((_DWORD *)v26 + 36);
    v63 = *((_DWORD *)v26 + 37);
    if ( v35 )
      pSid = NlpCopySid(v35);
    if ( *((_WORD *)v26 + 65) )
    {
      p_DestinationString = 0;
    }
    else
    {
      RtlInitUnicodeStringEx(&DestinationString, *((PCWSTR *)v26 + 17));
      p_DestinationString = (struct _NETLOGON_AUTHENTICATOR *)&DestinationString;
    }
    if ( v27 == 2 )
      _o_wcsncpy_s(v80, 16, *((_QWORD *)v26 + 21), (unsigned __int64)*((unsigned __int16 *)v26 + 80) >> 1);
    if ( (*(_BYTE *)v61 & 2) != 0 && (*((_BYTE *)v26 + 148) & 8) == 0 )
    {
      RtlLeaveCriticalSection(v29);
      v20 = v57;
      NlPrintDomRoutine(0x200u, v57, L"NlpLogonSamLogon: %ws failed because F bit isn't set on the TDO\n", v62);
      v21 = -1073741724;
      *a10 = 1;
      LODWORD(v55) = -1073741724;
      goto LABEL_160;
    }
    RtlLeaveCriticalSection(v29);
    v28 = v56;
    NlpDecryptLogonInformation(a6, (unsigned __int8 *)v56, (struct _SESSION_INFO *)&v78);
    if ( v27 == 2 )
      goto LABEL_75;
    goto LABEL_73;
  }
  if ( NlVerifyRpcIsSecured(v66, NamedServerSession, 0) )
    goto LABEL_62;
  RtlLeaveCriticalSection(v29);
  v31 = v56;
  v32 = NlpLogonTypeToText(a6);
  v20 = v57;
  NlPrintDomRoutine(
    0x100u,
    v57,
    L"SamLogon: %hs logon of %wZ\\%wZ from %wZ: failed RPC Security checks\n",
    v32,
    v56,
    v34,
    v33);
  v21 = -1073741790;
  LODWORD(v55) = -1073741790;
LABEL_163:
  v51 = v61;
  if ( (*v61 & 0xFFFFCFFF) != v69 )
    NlAssertFailed(
      "(*ExtraFlags & ~NL_EXFLAGS_INTERNAL_FLAGS) == (OriginalExtraFlags & ~NL_EXFLAGS_INTERNAL_FLAGS)",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
      0x1AA1u,
      v17);
  v52 = 16;
  *v51 ^= ((unsigned __int16)v70 ^ (unsigned __int16)*v51) & 0x3000;
  v53 = &v78;
  do
  {
    *(_BYTE *)v53 = 0;
    v53 = (__int128 *)((char *)v53 + 1);
    --v52;
  }
  while ( v52 );
  if ( v21 < 0 )
  {
    v54 = v68;
    FreeValidationInformation(*v68, a8);
    *v54 = 0;
  }
  if ( v20 )
  {
    if ( (NlGlobalParameters & 4) != 0 )
    {
      if ( v31 )
        NlPrintLogonParameters(v20, v62, v71, v74, *v51, (unsigned int *)&v55);
    }
    NlDereferenceDomain(v20);
  }
  NlEndNetlogonCall();
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18002d3c0  push    rbp
0x18002d3c2  push    rbx
0x18002d3c3  push    rsi
0x18002d3c4  push    rdi
0x18002d3c5  push    r12
0x18002d3c7  push    r13
0x18002d3c9  push    r14
0x18002d3cb  push    r15
0x18002d3cd  lea     rbp, [rsp-88h]
0x18002d3d5  sub     rsp, 198h
0x18002d3dc  mov     rax, cs:__security_cookie
0x18002d3e3  xor     rax, rsp
0x18002d3e6  mov     [rbp+0C0h+var_50], rax
0x18002d3ea  mov     rax, [rbp+0C0h+arg_50]
0x18002d3f1  mov     rbx, rdx
0x18002d3f4  mov     r15, [rbp+0C0h+arg_48]
0x18002d3fb  xor     edx, edx
0x18002d3fd  mov     r13, [rbp+0C0h+arg_20]
0x18002d404  xorps   xmm0, xmm0
0x18002d407  mov     [rbp+0C0h+var_78], edx
0x18002d40a  mov     rsi, rcx
0x18002d40d  mov     edx, [rax]
0x18002d40f  xorps   xmm1, xmm1
0x18002d412  mov     [rbp+0C0h+var_DC], edx
0x18002d415  mov     r14, r9
0x18002d418  and     edx, 0FFFFCFFFh
0x18002d41e  mov     [rbp+0C0h+var_F8], rcx
0x18002d422  mov     rcx, [rbp+0C0h+arg_40]
0x18002d429  mov     [rax], edx
0x18002d42b  mov     byte ptr [r15], 1
0x18002d42f  mov     [rbp+0C0h+var_110], r8
0x18002d433  mov     r8, [rbp+0C0h+arg_30]
0x18002d43a  mov     [rbp+0C0h+var_118], rax
0x18002d43e  xor     eax, eax
0x18002d440  mov     [rcx], rax
0x18002d443  mov     [rbp+0C0h+var_C0], r8
0x18002d447  mov     r12, [r8]
0x18002d44a  mov     [rbp+0C0h+var_138], r12
0x18002d44e  mov     [rbp+0C0h+var_E8], rcx
0x18002d452  mov     [rbp+0C0h+var_100], r13
0x18002d456  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x18002d45a  mov     [rbp+0C0h+var_E0], edx
0x18002d45d  movups  [rbp+0C0h+var_88], xmm1
0x18002d461  mov     qword ptr [rbp+0C0h+PerformanceCount], rax
0x18002d465  movups  [rbp+0C0h+var_70], xmm0
0x18002d469  mov     qword ptr [rbp+0C0h+var_C8], rax
0x18002d46d  movups  [rbp+0C0h+var_60], xmm0
0x18002d471  mov     [rbp+0C0h+var_120], rax
0x18002d475  mov     [rbp+0C0h+var_124], eax
0x18002d478  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x18002d47d  xor     edx, edx
0x18002d47f  test    eax, eax
0x18002d481  jnz     short loc_18002D48D
0x18002d483  mov     eax, 0C0000192h
0x18002d488  jmp     loc_18002DE67
0x18002d48d  mov     edi, [rbp+0C0h+arg_28]
0x18002d493  mov     [rbp+0C0h+var_D8], edi
0x18002d496  test    r12, r12
0x18002d499  jnz     short loc_18002D4AB
0x18002d49b  mov     r12, rdx
0x18002d49e  mov     ebx, 0C000000Dh
0x18002d4a3  mov     [rbp+0C0h+var_140], ebx
0x18002d4a6  jmp     loc_18002DDB8
0x18002d4ab  mov     rcx, rbx; unsigned __int16 *
0x18002d4ae  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18002d4b3  test    byte ptr cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 4; _NETLOGON_PARAMETERS NlGlobalParameters
0x18002d4ba  mov     r12, rax
0x18002d4bd  mov     [rbp+0C0h+var_130], rax
0x18002d4c1  jz      short loc_18002D4E9
0x18002d4c3  mov     rcx, [rbp+0C0h+var_118]
0x18002d4c7  mov     r8d, edi; enum _NETLOGON_LOGON_INFO_CLASS
0x18002d4ca  mov     r9, [rbp+0C0h+var_C0]; union _NETLOGON_LEVEL *
0x18002d4ce  mov     rdx, [rbp+0C0h+var_110]; unsigned __int16 *
0x18002d4d2  mov     [rsp+1D0h+var_1A8], 0; unsigned int *
0x18002d4db  mov     ecx, [rcx]
0x18002d4dd  mov     [rsp+1D0h+var_1B0], ecx; unsigned int
0x18002d4e1  mov     rcx, rax; struct _DOMAIN_INFO *
0x18002d4e4  call    ?NlPrintLogonParameters@@YAXPEAU_DOMAIN_INFO@@PEAGW4_NETLOGON_LOGON_INFO_CLASS@@PEAT_NETLOGON_LEVEL@@KPEAK@Z; NlPrintLogonParameters(_DOMAIN_INFO *,ushort *,_NETLOGON_LOGON_INFO_CLASS,_NETLOGON_LEVEL *,ulong,ulong *)
0x18002d4e9  test    r12, r12
0x18002d4ec  jnz     short loc_18002D4F5
0x18002d4ee  mov     ebx, 0C0000122h
0x18002d4f3  jmp     short loc_18002D4A3
0x18002d4f5  mov     edx, [rbp+0C0h+arg_38]
0x18002d4fb  mov     ecx, edx
0x18002d4fd  sub     ecx, 2
0x18002d500  jz      short loc_18002D529
0x18002d502  sub     ecx, 1
0x18002d505  jz      short loc_18002D529
0x18002d507  sub     ecx, 1
0x18002d50a  jz      short loc_18002D529
0x18002d50c  sub     ecx, 1
0x18002d50f  jz      short loc_18002D529
0x18002d511  sub     ecx, 1
0x18002d514  jz      short loc_18002D529
0x18002d516  cmp     ecx, 1
0x18002d519  jz      short loc_18002D529
0x18002d51b  mov     byte ptr [r15], 1
0x18002d51f  mov     ebx, 0C0000003h
0x18002d524  jmp     loc_18002D4A3
0x18002d529  mov     ecx, edi
0x18002d52b  sub     ecx, 1
0x18002d52e  jz      short loc_18002D58B
0x18002d530  sub     ecx, 1
0x18002d533  jz      short loc_18002D58B
0x18002d535  sub     ecx, 1
0x18002d538  jz      short loc_18002D58B
0x18002d53a  sub     ecx, 1
0x18002d53d  jz      short loc_18002D57F
0x18002d53f  sub     ecx, 1
0x18002d542  jz      short loc_18002D58B
0x18002d544  sub     ecx, 1
0x18002d547  jz      short loc_18002D58B
0x18002d549  sub     ecx, 1
0x18002d54c  jz      short loc_18002D58B
0x18002d54e  cmp     ecx, 1
0x18002d551  jnz     short loc_18002D51B
0x18002d553  cmp     edx, 7
0x18002d556  jnz     short loc_18002D51B
0x18002d558  lea     rcx, [rbp+0C0h+PerformanceCount]; lpPerformanceCount
0x18002d55c  call    cs:__imp_QueryPerformanceCounter
0x18002d562  xor     edx, edx
0x18002d564  test    eax, eax
0x18002d566  jnz     short loc_18002D56C
0x18002d568  mov     qword ptr [rbp+0C0h+PerformanceCount], rdx
0x18002d56c  lea     eax, [rdi-2]
0x18002d56f  mov     r8d, 0FFFFFFFBh
0x18002d575  test    r8d, eax
0x18002d578  jz      short loc_18002D59C
0x18002d57a  mov     [rbp+0C0h+var_13C], dl
0x18002d57d  jmp     short loc_18002D5A5
0x18002d57f  mov     ecx, edx
0x18002d581  sub     ecx, 4
0x18002d584  jz      short loc_18002D558
0x18002d586  cmp     ecx, 1
0x18002d589  jmp     short loc_18002D556
0x18002d58b  mov     ecx, edx
0x18002d58d  sub     ecx, 2
0x18002d590  jz      short loc_18002D558
0x18002d592  sub     ecx, 1
0x18002d595  jz      short loc_18002D558
0x18002d597  cmp     ecx, 3
0x18002d59a  jmp     short loc_18002D556
0x18002d59c  mov     [rbp+0C0h+var_13C], 1
0x18002d5a0  cmp     edi, 6
0x18002d5a3  jz      short loc_18002D5B1
0x18002d5a5  lea     eax, [rdi-5]
0x18002d5a8  mov     cl, dl
0x18002d5aa  test    eax, 0FFFFFFFDh
0x18002d5af  jnz     short loc_18002D5B3
0x18002d5b1  mov     cl, 1
0x18002d5b3  lea     eax, [rdi-1]
0x18002d5b6  cmp     eax, 2
0x18002d5b9  setbe   al
0x18002d5bc  mov     [rbp+0C0h+var_128], al
0x18002d5bf  test    cl, cl
0x18002d5c1  jnz     short loc_18002D5CA
0x18002d5c3  mov     r12b, dl
0x18002d5c6  test    al, al
0x18002d5c8  jz      short loc_18002D5CD
0x18002d5ca  mov     r12b, 1
0x18002d5cd  test    r12b, r12b
0x18002d5d0  jnz     short loc_18002D5EF
0x18002d5d2  lea     eax, [rdi-4]
0x18002d5d5  test    r8d, eax
0x18002d5d8  jz      short loc_18002D5EF
0x18002d5da  mov     byte ptr [r15], 1
0x18002d5de  mov     ebx, 0C0000003h
0x18002d5e3  mov     r12, [rbp+0C0h+var_130]
0x18002d5e7  mov     [rbp+0C0h+var_140], ebx
0x18002d5ea  jmp     loc_18002DDB8
0x18002d5ef  mov     [rbp+0C0h+pSid], rdx
0x18002d5f3  cmp     [rbp+0C0h+arg_58], edx
0x18002d5f9  jz      short loc_18002D62B
0x18002d5fb  mov     rax, [rbp+0C0h+var_130]
0x18002d5ff  mov     r13, rdx
0x18002d602  mov     [rbp+0C0h+var_78], 12F8FFFh
0x18002d609  mov     r14d, 1
0x18002d60f  mov     [rbp+0C0h+var_104], edx
0x18002d612  mov     [rbp+0C0h+var_108], edx
0x18002d615  mov     ebx, [rax+168h]
0x18002d61b  mov     dword ptr [rbp+0C0h+var_F8], ebx
0x18002d61e  mov     rbx, [rbp+0C0h+var_138]
0x18002d622  mov     [rbp+0C0h+var_100], rdx
0x18002d626  jmp     loc_18002D838
0x18002d62b  cmp     cs:?NlGlobalMemberWorkstation@@3HA, edx; int NlGlobalMemberWorkstation
0x18002d631  jz      short loc_18002D63A
0x18002d633  mov     ebx, 0C00000BBh
0x18002d638  jmp     short loc_18002D5E3
0x18002d63a  test    rbx, rbx
0x18002d63d  jz      loc_18002DC82
0x18002d643  cmp     [rbp+0C0h+var_110], rdx
0x18002d647  jz      loc_18002DC82
0x18002d64d  test    r14, r14
0x18002d650  jz      short loc_18002D657
0x18002d652  test    r13, r13
0x18002d655  jnz     short loc_18002D660
0x18002d657  test    rsi, rsi
0x18002d65a  jz      loc_18002DC82
0x18002d660  mov     rbx, [rbp+0C0h+var_130]
0x18002d664  lea     rsi, [rbx+1F8h]
0x18002d66b  mov     rcx, rsi; CriticalSection
0x18002d66e  call    cs:__imp_RtlEnterCriticalSection
0x18002d674  mov     rdx, [rbp+0C0h+var_110]; unsigned __int16 *
0x18002d678  mov     rcx, rbx; struct _DOMAIN_INFO *
0x18002d67b  call    ?NlFindNamedServerSession@@YAPEAU_SERVER_SESSION@@PEAU_DOMAIN_INFO@@PEAG@Z; NlFindNamedServerSession(_DOMAIN_INFO *,ushort *)
0x18002d680  xor     ebx, ebx
0x18002d682  mov     r13, rax
0x18002d685  test    rax, rax
0x18002d688  jnz     short loc_18002D6A0
0x18002d68a  mov     rcx, rsi; CriticalSection
0x18002d68d  call    cs:__imp_RtlLeaveCriticalSection
0x18002d693  mov     [r15], bl
0x18002d696  mov     ebx, 0C0000022h
0x18002d69b  jmp     loc_18002D5E3
0x18002d6a0  test    r14, r14
0x18002d6a3  jz      short loc_18002D6D0
0x18002d6a5  mov     r8, [rbp+0C0h+var_100]; struct _NETLOGON_AUTHENTICATOR *
0x18002d6a9  mov     rdx, r14; struct _NETLOGON_AUTHENTICATOR *
0x18002d6ac  mov     rcx, r13; struct _SERVER_SESSION *
0x18002d6af  call    ?NlCheckAuthenticator@@YAJPEAU_SERVER_SESSION@@PEAU_NETLOGON_AUTHENTICATOR@@1@Z; NlCheckAuthenticator(_SERVER_SESSION *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *)
0x18002d6b4  mov     [rbp+0C0h+var_140], eax
0x18002d6b7  mov     ebx, eax
0x18002d6b9  test    eax, eax
0x18002d6bb  jns     short loc_18002D736
0x18002d6bd  mov     rcx, rsi; CriticalSection
0x18002d6c0  call    cs:__imp_RtlLeaveCriticalSection
0x18002d6c6  xor     edx, edx
0x18002d6c8  mov     [r15], dl
0x18002d6cb  jmp     loc_18002DCA2
0x18002d6d0  mov     rcx, [rbp+0C0h+var_F8]; void *
0x18002d6d4  xor     r8d, r8d; unsigned __int8
0x18002d6d7  mov     rdx, r13; struct _SERVER_SESSION *
0x18002d6da  call    ?NlVerifyRpcIsSecured@@YAEPEAXPEAU_SERVER_SESSION@@E@Z; NlVerifyRpcIsSecured(void *,_SERVER_SESSION *,uchar)
0x18002d6df  test    al, al
0x18002d6e1  jnz     short loc_18002D738
0x18002d6e3  mov     rcx, rsi; CriticalSection
0x18002d6e6  call    cs:__imp_RtlLeaveCriticalSection
0x18002d6ec  mov     rsi, [rbp+0C0h+var_138]
0x18002d6f0  mov     ecx, edi; enum _NETLOGON_LOGON_INFO_CLASS
0x18002d6f2  lea     rdx, [rsi+30h]
0x18002d6f6  lea     r8, [rsi+20h]
0x18002d6fa  call    ?NlpLogonTypeToText@@YAPEADW4_NETLOGON_LOGON_INFO_CLASS@@@Z; NlpLogonTypeToText(_NETLOGON_LOGON_INFO_CLASS)
0x18002d6ff  mov     r12, [rbp+0C0h+var_130]
0x18002d703  mov     r9, rax
0x18002d706  mov     [rsp+1D0h+var_1A0], rdx
0x18002d70b  mov     ecx, 100h; unsigned int
0x18002d710  mov     [rsp+1D0h+var_1A8], r8
0x18002d715  mov     rdx, r12; struct _DOMAIN_INFO *
0x18002d718  lea     r8, aSamlogonHsLogo; "SamLogon: %hs logon of %wZ\\%wZ from %w"...
0x18002d71f  mov     qword ptr [rsp+1D0h+var_1B0], rsi
0x18002d724  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002d729  mov     ebx, 0C0000022h
0x18002d72e  mov     [rbp+0C0h+var_140], ebx
0x18002d731  jmp     loc_18002DDBC
0x18002d736  xor     ebx, ebx
0x18002d738  movups  xmm0, xmmword ptr [r13+60h]
0x18002d73d  mov     r14d, [r13+20h]
0x18002d741  movdqu  [rbp+0C0h+var_88], xmm0
0x18002d746  mov     eax, [r13+48h]
0x18002d74a  mov     [rbp+0C0h+var_78], eax
0x18002d74d  mov     eax, [r13+34h]
0x18002d751  mov     rcx, [r13+98h]; SourceSid
0x18002d758  mov     dword ptr [rbp+0C0h+var_F8], eax
0x18002d75b  mov     eax, [r13+90h]
0x18002d762  mov     [rbp+0C0h+var_104], eax
0x18002d765  mov     eax, [r13+94h]
0x18002d76c  mov     [rbp+0C0h+var_108], eax
0x18002d76f  test    rcx, rcx
0x18002d772  jz      short loc_18002D77D
0x18002d774  call    ?NlpCopySid@@YAPEAXPEAX@Z; NlpCopySid(void *)
0x18002d779  mov     [rbp+0C0h+pSid], rax
0x18002d77d  cmp     [r13+82h], bx
0x18002d785  jnz     short loc_18002D7A2
0x18002d787  mov     rdx, [r13+88h]; SourceString
0x18002d78e  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x18002d792  call    cs:__imp_RtlInitUnicodeStringEx
0x18002d798  lea     rax, [rbp+0C0h+DestinationString]
0x18002d79c  mov     [rbp+0C0h+var_100], rax
0x18002d7a0  jmp     short loc_18002D7A6
0x18002d7a2  mov     [rbp+0C0h+var_100], rbx
0x18002d7a6  cmp     r14d, 2
0x18002d7aa  jnz     short loc_18002D7CC
0x18002d7ac  movzx   r9d, word ptr [r13+0A0h]
0x18002d7b4  lea     edx, [r14+0Eh]
0x18002d7b8  mov     r8, [r13+0A8h]
0x18002d7bf  lea     rcx, [rbp+0C0h+var_70]
0x18002d7c3  shr     r9, 1
0x18002d7c6  call    cs:__imp__o_wcsncpy_s
0x18002d7cc  mov     rax, [rbp+0C0h+var_118]
0x18002d7d0  test    byte ptr [rax], 2
0x18002d7d3  jz      short loc_18002D815
0x18002d7d5  test    byte ptr [r13+94h], 8
0x18002d7dd  jnz     short loc_18002D815
0x18002d7df  mov     rcx, rsi; CriticalSection
0x18002d7e2  call    cs:__imp_RtlLeaveCriticalSection
0x18002d7e8  mov     r12, [rbp+0C0h+var_130]
0x18002d7ec  lea     r8, aNlplogonsamlog; "NlpLogonSamLogon: %ws failed because F "...
0x18002d7f3  mov     r9, [rbp+0C0h+var_110]
0x18002d7f7  mov     rdx, r12; struct _DOMAIN_INFO *
0x18002d7fa  mov     ecx, 200h; unsigned int
  ... truncated ...
```
