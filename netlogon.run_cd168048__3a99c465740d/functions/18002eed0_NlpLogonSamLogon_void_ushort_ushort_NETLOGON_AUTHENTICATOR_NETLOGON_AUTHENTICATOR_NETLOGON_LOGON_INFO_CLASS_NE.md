# NlpLogonSamLogon(void *,ushort *,ushort *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_LOGON_INFO_CLASS,_NETLOGON_LEVEL *,_NETLOGON_VALIDATION_INFO_CLASS,_NETLOGON_VALIDATION *,uchar *,ulong *,int)

- ea: `0x18002eed0`
- end: `0x18002fa18`
- name: `?NlpLogonSamLogon@@YAJPEAXPEAG1PEAU_NETLOGON_AUTHENTICATOR@@2W4_NETLOGON_LOGON_INFO_CLASS@@PEAT_NETLOGON_LEVEL@@W4_NETLOGON_VALIDATION_INFO_CLASS@@PEAT_NETLOGON_VALIDATION@@PEAEPEAKH@Z`
- size: `2888`
- prototype: `int __high(void *, unsigned __int16 *, unsigned __int16 *, struct _NETLOGON_AUTHENTICATOR *, struct _NETLOGON_AUTHENTICATOR *, enum _NETLOGON_LOGON_INFO_CLASS, union _NETLOGON_LEVEL *, enum _NETLOGON_VALIDATION_INFO_CLASS, union _NETLOGON_VALIDATION *, unsigned __int8 *, unsigned int *, int)`
- caller_count: `4`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180034490`
- `0x1800349b0`
- `0x180034a30`
- `0x180034ab0`

## callees

- `0x180007518`
- `0x18000c440`
- `0x18000d444`
- `0x18000d854`
- `0x18000dd00`
- `0x18000e0e0`
- `0x18000e910`
- `0x1800267ec`
- `0x1800271d4`
- `0x18002da78`
- `0x18002dd48`
- `0x18002e5fc`
- `0x18002e9a0`
- `0x18002ea90`
- `0x18002eed0`
- `0x18002fa20`
- `0x18003033c`
- `0x180032f90`
- `0x180038224`
- `0x18003f1b0`
- `0x180053360`
- `0x18005342c`
- `0x18005448c`
- `0x180057174`
- `0x1800639bc`
- `0x180064d80`
- `0x180069a30`
- `0x1800713dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002f2fe`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002f2fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f06c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f828`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f06c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002f828`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f93c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f93c`
- `LSASRV!LsaIFreeHeap` at `0x18002f800`
- `LSASRV!LsaIFreeHeap` at `0x18002f800`
- `LSASRV!LsaIValidateTargetInfo` at `0x18002f520`
- `LSASRV!LsaIValidateTargetInfo` at `0x18002f588`
- `LSASRV!LsaIValidateTargetInfo` at `0x18002f520`
- `LSASRV!LsaIValidateTargetInfo` at `0x18002f588`
- `ntdll!RtlAcquireResourceShared` at `0x18002f886`
- `ntdll!RtlAcquireResourceShared` at `0x18002f886`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002f2c4`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002f2c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f1a9`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f1e6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f212`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f320`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f35c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f924`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f1a9`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f1e6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f212`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f320`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f35c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f924`
- `ntdll!RtlEnterCriticalSection` at `0x18002f184`
- `ntdll!RtlEnterCriticalSection` at `0x18002f853`
- `ntdll!RtlEnterCriticalSection` at `0x18002f184`
- `ntdll!RtlEnterCriticalSection` at `0x18002f853`
- `ntdll!RtlInitUnicodeString` at `0x18002f4eb`
- `ntdll!RtlInitUnicodeString` at `0x18002f4eb`
- `ntdll!RtlReleaseResource` at `0x18002f904`
- `ntdll!RtlReleaseResource` at `0x18002f904`
- `SAMSRV!SamIMixedDomain` at `0x18002f44f`
- `SAMSRV!SamIMixedDomain` at `0x18002f44f`

## string_xrefs

- `0x18002f47f`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002f76c`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002f790`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002f962`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002f24a`: `SamLogon: %hs logon of %wZ\%wZ from %wZ: failed RPC Security checks\n`
- `0x18002f53e`: `Failed to validate the passthrough target %#x for computer name %ws\n`
- `0x18002f5a6`: `Failed to validate the passthrough target %#x for computer name %ws\n`

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
        void **a9,
        unsigned __int8 *a10,
        int *a11,
        int a12)
{
  unsigned int v15; // edx
  struct _NETLOGON_LOGON_IDENTITY_INFO *v16; // r12
  char *v17; // r9
  enum _NETLOGON_LOGON_INFO_CLASS v19; // edi
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
  signed int v40; // eax
  signed int v41; // eax
  int v42; // esi
  signed int v43; // eax
  struct _SECPKG_NTLM_TARGETINFO *v44; // r12
  struct _NETLOGON_LOGON_IDENTITY_INFO *v45; // r15
  signed int v46; // eax
  void **v47; // rax
  LONGLONG v48; // rsi
  __int64 v49; // r14
  struct _CLIENT_SESSION *NamedClientSession; // rdi
  unsigned int *v51; // rdi
  __int64 v52; // rcx
  __int128 *v53; // rax
  void **v54; // r14
  unsigned int v55; // [rsp+90h] [rbp-80h] BYREF
  char v56; // [rsp+94h] [rbp-7Ch]
  struct _NETLOGON_LOGON_IDENTITY_INFO *v57; // [rsp+98h] [rbp-78h]
  struct _DOMAIN_INFO *v58; // [rsp+A0h] [rbp-70h]
  bool v59; // [rsp+A8h] [rbp-68h]
  int v60; // [rsp+ACh] [rbp-64h] BYREF
  struct _SECPKG_NTLM_TARGETINFO *v61; // [rsp+B0h] [rbp-60h] BYREF
  unsigned int *v62; // [rsp+B8h] [rbp-58h]
  unsigned __int16 *v63; // [rsp+C0h] [rbp-50h]
  unsigned int v64; // [rsp+C8h] [rbp-48h]
  unsigned int v65; // [rsp+CCh] [rbp-44h]
  struct _NETLOGON_AUTHENTICATOR *p_DestinationString; // [rsp+D0h] [rbp-40h]
  void *v67; // [rsp+D8h] [rbp-38h]
  LARGE_INTEGER PerformanceCount; // [rsp+E0h] [rbp-30h] BYREF
  void **v69; // [rsp+E8h] [rbp-28h]
  unsigned int v70; // [rsp+F0h] [rbp-20h]
  int v71; // [rsp+F4h] [rbp-1Ch]
  enum _NETLOGON_LOGON_INFO_CLASS v72; // [rsp+F8h] [rbp-18h]
  PSID pSid; // [rsp+100h] [rbp-10h]
  LARGE_INTEGER v74; // [rsp+108h] [rbp-8h] BYREF
  union _NETLOGON_LEVEL *v75; // [rsp+110h] [rbp+0h]
  __int128 v76; // [rsp+118h] [rbp+8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+128h] [rbp+18h] BYREF
  struct _UNICODE_STRING v78; // [rsp+138h] [rbp+28h] BYREF
  __int128 v79; // [rsp+148h] [rbp+38h] BYREF
  int v80; // [rsp+158h] [rbp+48h]
  _OWORD v81[2]; // [rsp+160h] [rbp+50h] BYREF

  v80 = 0;
  v71 = *a11;
  v15 = v71 & 0xFFFFCFFF;
  v67 = a1;
  *a11 = v71 & 0xFFFFCFFF;
  *a10 = 1;
  v63 = a3;
  v62 = (unsigned int *)a11;
  *a9 = 0;
  v75 = a7;
  v16 = *(struct _NETLOGON_LOGON_IDENTITY_INFO **)a7;
  v57 = *(struct _NETLOGON_LOGON_IDENTITY_INFO **)a7;
  v69 = a9;
  p_DestinationString = a5;
  DestinationString = 0;
  v70 = v15;
  v79 = 0;
  PerformanceCount.QuadPart = 0;
  memset(v81, 0, sizeof(v81));
  v74.QuadPart = 0;
  v61 = 0;
  v60 = 0;
  if ( !(unsigned int)NlStartNetlogonCall() )
    return 3221225874LL;
  v19 = a6;
  v72 = a6;
  if ( !v16 )
  {
    v20 = 0;
    v21 = -1073741811;
LABEL_5:
    v55 = v21;
LABEL_162:
    v31 = v57;
    goto LABEL_163;
  }
  DomainByServerName = NlFindDomainByServerName(a2);
  v20 = DomainByServerName;
  v58 = DomainByServerName;
  if ( (NlGlobalParameters & 4) != 0 )
    NlPrintLogonParameters(DomainByServerName, v63, a6, v75, *v62, 0);
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
    v56 = 0;
  }
  else
  {
    v56 = 1;
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
  v59 = (unsigned int)(a6 - 1) <= 2;
  if ( v24 || (v25 = 0, (unsigned int)(a6 - 1) <= 2) )
    v25 = 1;
  if ( !v25 && ((a6 - 4) & 0xFFFFFFFB) != 0 )
  {
    *a10 = 1;
    v21 = -1073741821;
LABEL_44:
    v20 = v58;
    v55 = v21;
    goto LABEL_162;
  }
  pSid = 0;
  if ( a12 )
  {
    v26 = 0;
    v80 = 19894271;
    v27 = 1;
    v65 = 0;
    v64 = 0;
    LODWORD(v67) = *((_DWORD *)v58 + 90);
    v28 = v57;
    p_DestinationString = 0;
LABEL_73:
    if ( NlGlobalMemberWorkstation || v27 != 1 )
    {
      v36 = v62;
      goto LABEL_77;
    }
LABEL_75:
    v36 = v62;
    *v62 |= 0x2000u;
LABEL_77:
    if ( a6 != 8
      || (v55 = IsTicketLogonRequestSupported((struct _NETLOGON_TICKET_LOGON_INFO *const)v28, (*v36 & 0x2000) != 0),
          v21 = v55,
          (v55 & 0x80000000) == 0) )
    {
      if ( v27 == 2
        && v25
        && ((dword_1800F81BC & 5) != 0 || (dword_1800F81C0 & 5) != 0)
        && (unsigned int)NlIsTargetAllowed(v63) )
      {
        *v36 |= 0x1000u;
      }
      if ( (NlGlobalServiceStatus.dwCurrentState == 7 || !dword_1800F824C || NlGlobalDsPaused) && v27 != 1 && v27 != 6 )
      {
        v20 = v58;
        v21 = -1073741790;
        v55 = -1073741790;
        *a10 = 0;
        goto LABEL_160;
      }
      if ( v59 )
      {
        if ( v27 - 1 > 1 )
          goto LABEL_121;
        v20 = v58;
        if ( !(unsigned __int8)SamIMixedDomain(*((_QWORD *)v58 + 46), 0) || (v80 & 0xBFFFFE00) != 0 )
        {
          switch ( a6 )
          {
            case NetlogonInteractiveInformation:
              v19 = NetlogonInteractiveTransitiveInformation;
              break;
            case NetlogonNetworkInformation:
              v19 = NetlogonNetworkTransitiveInformation;
              break;
            case NetlogonServiceInformation:
              v19 = NetlogonServiceTransitiveInformation;
              break;
            default:
              NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx", 0x198Fu, v37);
              v21 = -1073741821;
              *a10 = 0;
              v55 = -1073741821;
LABEL_160:
              if ( pSid )
                FreeSid(pSid);
              goto LABEL_162;
          }
        }
      }
      else
      {
        v20 = v58;
      }
      if ( v27 == 2 )
      {
        v38 = v56;
        if ( !v56 )
        {
          if ( a6 == NetlogonGenericInformation )
          {
            v41 = LsaIValidateTargetInfo(
                    &v57[1],
                    *(_QWORD *)&v57[1].LogonId.HighPart,
                    v57[1].ParameterControl,
                    *((_QWORD *)v20 + 23),
                    v81);
            v55 = v41;
            v21 = v41;
            if ( v41 < 0 )
            {
              NlPrintRoutine(
                0x100u,
                L"Failed to validate the passthrough target %#x for computer name %ws\n",
                (unsigned int)v41,
                v81);
              goto LABEL_152;
            }
            v38 = v56;
          }
          goto LABEL_112;
        }
        v78 = 0;
        v76 = 0;
        RtlInitUnicodeString(&v78, L"NTLM");
        v39 = *((_QWORD *)v20 + 23);
        *((_QWORD *)&v76 + 1) = v57;
        LODWORD(v76) = 2;
        v40 = LsaIValidateTargetInfo(&v78, &v76, 16, v39, v81);
        v55 = v40;
        v21 = v40;
        if ( v40 < 0 )
        {
          NlPrintRoutine(
            0x100u,
            L"Failed to validate the passthrough target %#x for computer name %ws\n",
            (unsigned int)v40,
            v81);
          *a10 = 1;
LABEL_152:
          if ( v21 >= 0 && PerformanceCount.QuadPart && QueryPerformanceCounter(&v74) )
          {
            v48 = v74.QuadPart - PerformanceCount.QuadPart;
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
        v38 = v56;
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
          v44 = v61;
LABEL_129:
          v45 = v57;
          v55 = NlpUserValidate(
                  (__int64)v58,
                  v27,
                  (unsigned int)v67,
                  v19,
                  &v57->LogonDomainName,
                  a8,
                  v69,
                  a10,
                  (int *)v62,
                  0,
                  v63,
                  (struct _UNICODE_STRING *)p_DestinationString,
                  v65,
                  v64,
                  pSid,
                  v26,
                  v44,
                  v60);
          v21 = v55;
          if ( (v55 & 0x80000000) == 0 )
          {
            if ( v55 )
              NlAssertFailed(
                "!NT_SUCCESS(Status) || Status == STATUS_SUCCESS",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                0x1A3Cu,
                v17);
            v47 = v69;
            if ( !*v69 )
            {
              NlAssertFailed(
                "!NT_SUCCESS(Status) || ValidationInformation->ValidationSam != NULL",
                "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
                0x1A3Du,
                v17);
              v47 = v69;
            }
            if ( v27 != 1 )
              NlpEncryptValidationInformation((unsigned int)v19, a8, *v47, &v79);
            v21 = 0;
            v55 = 0;
            goto LABEL_146;
          }
          if ( (v80 & 1) != 0 )
            goto LABEL_136;
          if ( v55 == -1073741276 )
          {
            v21 = -1073741711;
            goto LABEL_138;
          }
          if ( v55 != -1073741260 )
          {
LABEL_136:
            if ( v55 != -1073740781 || v80 )
            {
LABEL_146:
              if ( v42 )
                NlpNtlmlessLogServerDomain(v45, v26, v44, v60, v21);
              goto LABEL_149;
            }
            v21 = -1073741724;
          }
          else
          {
            v21 = -1073741710;
          }
LABEL_138:
          v55 = v21;
          goto LABEL_146;
        }
LABEL_118:
        v43 = NlpExtractNtlmTargetInfo(v57, &v61, &v60);
        v55 = v43;
        v21 = v43;
        if ( v43 < 0 )
        {
          NlPrintRoutine(4u, L"NlpExtractNtlmTargetInfo failed Status:0x%x\n", (unsigned int)v43);
          v44 = v61;
LABEL_120:
          v45 = v57;
          goto LABEL_146;
        }
        v44 = v61;
        v46 = NlpValidateNTLMTargetInfo(v27, v26, v57, v58, v61, v60);
        v55 = v46;
        v21 = v46;
        if ( v46 < 0 )
        {
          NlPrintRoutine(4u, L"NlpValidateNTLMTargetInfo failed Status:0x%x\n", (unsigned int)v46);
          goto LABEL_120;
        }
        goto LABEL_129;
      }
LABEL_121:
      v38 = v56;
      if ( !v56 )
        goto LABEL_112;
      goto LABEL_122;
    }
LABEL_59:
    *a10 = 0;
LABEL_151:
    v20 = v58;
    goto LABEL_152;
  }
  if ( NlGlobalMemberWorkstation )
  {
    v21 = -1073741637;
    goto LABEL_44;
  }
  if ( !a2 || !v63 || (!a4 || !a5) && !a1 )
  {
    v44 = v61;
    v21 = -1073741811;
    v55 = -1073741811;
    *a10 = 1;
LABEL_149:
    if ( v44 )
      LsaIFreeHeap(v44, 0);
    goto LABEL_151;
  }
  v29 = (struct _RTL_CRITICAL_SECTION *)((char *)v58 + 504);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v58 + 504));
  NamedServerSession = NlFindNamedServerSession(v58, v63);
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
    v55 = NlCheckAuthenticator(NamedServerSession, a4, p_DestinationString);
    v21 = v55;
    if ( (v55 & 0x80000000) != 0 )
    {
      RtlLeaveCriticalSection(v29);
      goto LABEL_59;
    }
LABEL_62:
    v27 = *((_DWORD *)v26 + 8);
    v79 = *((_OWORD *)v26 + 6);
    v80 = *((_DWORD *)v26 + 18);
    v35 = (void *)*((_QWORD *)v26 + 19);
    LODWORD(v67) = *((_DWORD *)v26 + 13);
    v65 = *((_DWORD *)v26 + 36);
    v64 = *((_DWORD *)v26 + 37);
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
      _o_wcsncpy_s(v81, 16, *((_QWORD *)v26 + 21));
    if ( (*(_BYTE *)v62 & 2) != 0 && (*((_BYTE *)v26 + 148) & 8) == 0 )
    {
      RtlLeaveCriticalSection(v29);
      v20 = v58;
      NlPrintDomRoutine(0x200u, v58, L"NlpLogonSamLogon: %ws failed because F bit isn't set on the TDO\n", v63);
      v21 = -1073741724;
      *a10 = 1;
      v55 = -1073741724;
      goto LABEL_160;
    }
    RtlLeaveCriticalSection(v29);
    v28 = v57;
    NlpDecryptLogonInformation(a6, (unsigned __int8 *)v57, (struct _SESSION_INFO *)&v79);
    if ( v27 == 2 )
      goto LABEL_75;
    goto LABEL_73;
  }
  if ( NlVerifyRpcIsSecured(v67, NamedServerSession, 0) )
    goto LABEL_62;
  RtlLeaveCriticalSection(v29);
  v31 = v57;
  v32 = NlpLogonTypeToText(a6);
  v20 = v58;
  NlPrintDomRoutine(
    0x100u,
    v58,
    L"SamLogon: %hs logon of %wZ\\%wZ from %wZ: failed RPC Security checks\n",
    v32,
    v57,
    v34,
    v33);
  v21 = -1073741790;
  v55 = -1073741790;
LABEL_163:
  v51 = v62;
  if ( (*v62 & 0xFFFFCFFF) != v70 )
    NlAssertFailed(
      "(*ExtraFlags & ~NL_EXFLAGS_INTERNAL_FLAGS) == (OriginalExtraFlags & ~NL_EXFLAGS_INTERNAL_FLAGS)",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\logonapi.cxx",
      0x1AA3u,
      v17);
  v52 = 16;
  *v51 ^= ((unsigned __int16)v71 ^ (unsigned __int16)*v51) & 0x3000;
  v53 = &v79;
  do
  {
    *(_BYTE *)v53 = 0;
    v53 = (__int128 *)((char *)v53 + 1);
    --v52;
  }
  while ( v52 );
  if ( v21 < 0 )
  {
    v54 = v69;
    FreeValidationInformation((unsigned __int8 *)*v69, a8);
    *v54 = 0;
  }
  if ( v20 )
  {
    if ( (NlGlobalParameters & 4) != 0 )
    {
      if ( v31 )
        NlPrintLogonParameters(v20, v63, v72, v75, *v51, &v55);
    }
    NlDereferenceDomain(v20);
  }
  NlEndNetlogonCall();
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18002eed0  push    rbp
0x18002eed2  push    rbx
0x18002eed3  push    rsi
0x18002eed4  push    rdi
0x18002eed5  push    r12
0x18002eed7  push    r13
0x18002eed9  push    r14
0x18002eedb  push    r15
0x18002eedd  lea     rbp, [rsp-88h]
0x18002eee5  sub     rsp, 198h
0x18002eeec  mov     rax, cs:__security_cookie
0x18002eef3  xor     rax, rsp
0x18002eef6  mov     [rbp+0C0h+var_50], rax
0x18002eefa  mov     rax, [rbp+0C0h+arg_50]
0x18002ef01  mov     rbx, rdx
0x18002ef04  mov     r15, [rbp+0C0h+arg_48]
0x18002ef0b  xor     edx, edx
0x18002ef0d  mov     r13, [rbp+0C0h+arg_20]
0x18002ef14  xorps   xmm0, xmm0
0x18002ef17  mov     [rbp+0C0h+var_78], edx
0x18002ef1a  mov     rsi, rcx
0x18002ef1d  mov     edx, [rax]
0x18002ef1f  xorps   xmm1, xmm1
0x18002ef22  mov     [rbp+0C0h+var_DC], edx
0x18002ef25  mov     r14, r9
0x18002ef28  and     edx, 0FFFFCFFFh
0x18002ef2e  mov     [rbp+0C0h+var_F8], rcx
0x18002ef32  mov     rcx, [rbp+0C0h+arg_40]
0x18002ef39  mov     [rax], edx
0x18002ef3b  mov     byte ptr [r15], 1
0x18002ef3f  mov     [rbp+0C0h+var_110], r8
0x18002ef43  mov     r8, [rbp+0C0h+arg_30]
0x18002ef4a  mov     [rbp+0C0h+var_118], rax
0x18002ef4e  xor     eax, eax
0x18002ef50  mov     [rcx], rax
0x18002ef53  mov     [rbp+0C0h+var_C0], r8
0x18002ef57  mov     r12, [r8]
0x18002ef5a  mov     [rbp+0C0h+var_138], r12
0x18002ef5e  mov     [rbp+0C0h+var_E8], rcx
0x18002ef62  mov     [rbp+0C0h+var_100], r13
0x18002ef66  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x18002ef6a  mov     [rbp+0C0h+var_E0], edx
0x18002ef6d  movups  [rbp+0C0h+var_88], xmm1
0x18002ef71  mov     qword ptr [rbp+0C0h+PerformanceCount], rax
0x18002ef75  movups  [rbp+0C0h+var_70], xmm0
0x18002ef79  mov     qword ptr [rbp+0C0h+var_C8], rax
0x18002ef7d  movups  [rbp+0C0h+var_60], xmm0
0x18002ef81  mov     [rbp+0C0h+var_120], rax
0x18002ef85  mov     [rbp+0C0h+var_124], eax
0x18002ef88  call    ?NlStartNetlogonCall@@YAHXZ; NlStartNetlogonCall(void)
0x18002ef8d  xor     edx, edx
0x18002ef8f  test    eax, eax
0x18002ef91  jnz     short loc_18002EF9D
0x18002ef93  mov     eax, 0C0000192h
0x18002ef98  jmp     loc_18002F9F7
0x18002ef9d  mov     edi, [rbp+0C0h+arg_28]
0x18002efa3  mov     [rbp+0C0h+var_D8], edi
0x18002efa6  test    r12, r12
0x18002efa9  jnz     short loc_18002EFBB
0x18002efab  mov     r12, rdx
0x18002efae  mov     ebx, 0C000000Dh
0x18002efb3  mov     [rbp+0C0h+var_140], ebx
0x18002efb6  jmp     loc_18002F948
0x18002efbb  mov     rcx, rbx; unsigned __int16 *
0x18002efbe  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18002efc3  test    byte ptr cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, 4; _NETLOGON_PARAMETERS NlGlobalParameters
0x18002efca  mov     r12, rax
0x18002efcd  mov     [rbp+0C0h+var_130], rax
0x18002efd1  jz      short loc_18002EFF9
0x18002efd3  mov     rcx, [rbp+0C0h+var_118]
0x18002efd7  mov     r8d, edi; enum _NETLOGON_LOGON_INFO_CLASS
0x18002efda  mov     r9, [rbp+0C0h+var_C0]; union _NETLOGON_LEVEL *
0x18002efde  mov     rdx, [rbp+0C0h+var_110]; unsigned __int16 *
0x18002efe2  mov     [rsp+1D0h+var_1A8], 0; unsigned int *
0x18002efeb  mov     ecx, [rcx]
0x18002efed  mov     [rsp+1D0h+var_1B0], ecx; unsigned int
0x18002eff1  mov     rcx, rax; struct _DOMAIN_INFO *
0x18002eff4  call    ?NlPrintLogonParameters@@YAXPEAU_DOMAIN_INFO@@PEAGW4_NETLOGON_LOGON_INFO_CLASS@@PEAT_NETLOGON_LEVEL@@KPEAK@Z; NlPrintLogonParameters(_DOMAIN_INFO *,ushort *,_NETLOGON_LOGON_INFO_CLASS,_NETLOGON_LEVEL *,ulong,ulong *)
0x18002eff9  test    r12, r12
0x18002effc  jnz     short loc_18002F005
0x18002effe  mov     ebx, 0C0000122h
0x18002f003  jmp     short loc_18002EFB3
0x18002f005  mov     edx, [rbp+0C0h+arg_38]
0x18002f00b  mov     ecx, edx
0x18002f00d  sub     ecx, 2
0x18002f010  jz      short loc_18002F039
0x18002f012  sub     ecx, 1
0x18002f015  jz      short loc_18002F039
0x18002f017  sub     ecx, 1
0x18002f01a  jz      short loc_18002F039
0x18002f01c  sub     ecx, 1
0x18002f01f  jz      short loc_18002F039
0x18002f021  sub     ecx, 1
0x18002f024  jz      short loc_18002F039
0x18002f026  cmp     ecx, 1
0x18002f029  jz      short loc_18002F039
0x18002f02b  mov     byte ptr [r15], 1
0x18002f02f  mov     ebx, 0C0000003h
0x18002f034  jmp     loc_18002EFB3
0x18002f039  mov     ecx, edi
0x18002f03b  sub     ecx, 1
0x18002f03e  jz      short loc_18002F0A1
0x18002f040  sub     ecx, 1
0x18002f043  jz      short loc_18002F0A1
0x18002f045  sub     ecx, 1
0x18002f048  jz      short loc_18002F0A1
0x18002f04a  sub     ecx, 1
0x18002f04d  jz      short loc_18002F095
0x18002f04f  sub     ecx, 1
0x18002f052  jz      short loc_18002F0A1
0x18002f054  sub     ecx, 1
0x18002f057  jz      short loc_18002F0A1
0x18002f059  sub     ecx, 1
0x18002f05c  jz      short loc_18002F0A1
0x18002f05e  cmp     ecx, 1
0x18002f061  jnz     short loc_18002F02B
0x18002f063  cmp     edx, 7
0x18002f066  jnz     short loc_18002F02B
0x18002f068  lea     rcx, [rbp+0C0h+PerformanceCount]; lpPerformanceCount
0x18002f06c  call    cs:__imp_QueryPerformanceCounter
0x18002f073  nop     dword ptr [rax+rax+00h]
0x18002f078  xor     edx, edx
0x18002f07a  test    eax, eax
0x18002f07c  jnz     short loc_18002F082
0x18002f07e  mov     qword ptr [rbp+0C0h+PerformanceCount], rdx
0x18002f082  lea     eax, [rdi-2]
0x18002f085  mov     r8d, 0FFFFFFFBh
0x18002f08b  test    r8d, eax
0x18002f08e  jz      short loc_18002F0B2
0x18002f090  mov     [rbp+0C0h+var_13C], dl
0x18002f093  jmp     short loc_18002F0BB
0x18002f095  mov     ecx, edx
0x18002f097  sub     ecx, 4
0x18002f09a  jz      short loc_18002F068
0x18002f09c  cmp     ecx, 1
0x18002f09f  jmp     short loc_18002F066
0x18002f0a1  mov     ecx, edx
0x18002f0a3  sub     ecx, 2
0x18002f0a6  jz      short loc_18002F068
0x18002f0a8  sub     ecx, 1
0x18002f0ab  jz      short loc_18002F068
0x18002f0ad  cmp     ecx, 3
0x18002f0b0  jmp     short loc_18002F066
0x18002f0b2  mov     [rbp+0C0h+var_13C], 1
0x18002f0b6  cmp     edi, 6
0x18002f0b9  jz      short loc_18002F0C7
0x18002f0bb  lea     eax, [rdi-5]
0x18002f0be  mov     cl, dl
0x18002f0c0  test    eax, 0FFFFFFFDh
0x18002f0c5  jnz     short loc_18002F0C9
0x18002f0c7  mov     cl, 1
0x18002f0c9  lea     eax, [rdi-1]
0x18002f0cc  cmp     eax, 2
0x18002f0cf  setbe   al
0x18002f0d2  mov     [rbp+0C0h+var_128], al
0x18002f0d5  test    cl, cl
0x18002f0d7  jnz     short loc_18002F0E0
0x18002f0d9  mov     r12b, dl
0x18002f0dc  test    al, al
0x18002f0de  jz      short loc_18002F0E3
0x18002f0e0  mov     r12b, 1
0x18002f0e3  test    r12b, r12b
0x18002f0e6  jnz     short loc_18002F105
0x18002f0e8  lea     eax, [rdi-4]
0x18002f0eb  test    r8d, eax
0x18002f0ee  jz      short loc_18002F105
0x18002f0f0  mov     byte ptr [r15], 1
0x18002f0f4  mov     ebx, 0C0000003h
0x18002f0f9  mov     r12, [rbp+0C0h+var_130]
0x18002f0fd  mov     [rbp+0C0h+var_140], ebx
0x18002f100  jmp     loc_18002F948
0x18002f105  mov     [rbp+0C0h+pSid], rdx
0x18002f109  cmp     [rbp+0C0h+arg_58], edx
0x18002f10f  jz      short loc_18002F141
0x18002f111  mov     rax, [rbp+0C0h+var_130]
0x18002f115  mov     r13, rdx
0x18002f118  mov     [rbp+0C0h+var_78], 12F8FFFh
0x18002f11f  mov     r14d, 1
0x18002f125  mov     [rbp+0C0h+var_104], edx
0x18002f128  mov     [rbp+0C0h+var_108], edx
0x18002f12b  mov     ebx, [rax+168h]
0x18002f131  mov     dword ptr [rbp+0C0h+var_F8], ebx
0x18002f134  mov     rbx, [rbp+0C0h+var_138]
0x18002f138  mov     [rbp+0C0h+var_100], rdx
0x18002f13c  jmp     loc_18002F382
0x18002f141  cmp     cs:?NlGlobalMemberWorkstation@@3HA, edx; int NlGlobalMemberWorkstation
0x18002f147  jz      short loc_18002F150
0x18002f149  mov     ebx, 0C00000BBh
0x18002f14e  jmp     short loc_18002F0F9
0x18002f150  test    rbx, rbx
0x18002f153  jz      loc_18002F7E8
0x18002f159  cmp     [rbp+0C0h+var_110], rdx
0x18002f15d  jz      loc_18002F7E8
0x18002f163  test    r14, r14
0x18002f166  jz      short loc_18002F16D
0x18002f168  test    r13, r13
0x18002f16b  jnz     short loc_18002F176
0x18002f16d  test    rsi, rsi
0x18002f170  jz      loc_18002F7E8
0x18002f176  mov     rbx, [rbp+0C0h+var_130]
0x18002f17a  lea     rsi, [rbx+1F8h]
0x18002f181  mov     rcx, rsi; CriticalSection
0x18002f184  call    cs:__imp_RtlEnterCriticalSection
0x18002f18b  nop     dword ptr [rax+rax+00h]
0x18002f190  mov     rdx, [rbp+0C0h+var_110]; unsigned __int16 *
0x18002f194  mov     rcx, rbx; struct _DOMAIN_INFO *
0x18002f197  call    ?NlFindNamedServerSession@@YAPEAU_SERVER_SESSION@@PEAU_DOMAIN_INFO@@PEAG@Z; NlFindNamedServerSession(_DOMAIN_INFO *,ushort *)
0x18002f19c  xor     ebx, ebx
0x18002f19e  mov     r13, rax
0x18002f1a1  test    rax, rax
0x18002f1a4  jnz     short loc_18002F1C2
0x18002f1a6  mov     rcx, rsi; CriticalSection
0x18002f1a9  call    cs:__imp_RtlLeaveCriticalSection
0x18002f1b0  nop     dword ptr [rax+rax+00h]
0x18002f1b5  mov     [r15], bl
0x18002f1b8  mov     ebx, 0C0000022h
0x18002f1bd  jmp     loc_18002F0F9
0x18002f1c2  test    r14, r14
0x18002f1c5  jz      short loc_18002F1FC
0x18002f1c7  mov     r8, [rbp+0C0h+var_100]; struct _NETLOGON_AUTHENTICATOR *
0x18002f1cb  mov     rdx, r14; struct _NETLOGON_AUTHENTICATOR *
0x18002f1ce  mov     rcx, r13; struct _SERVER_SESSION *
0x18002f1d1  call    ?NlCheckAuthenticator@@YAJPEAU_SERVER_SESSION@@PEAU_NETLOGON_AUTHENTICATOR@@1@Z; NlCheckAuthenticator(_SERVER_SESSION *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *)
0x18002f1d6  mov     [rbp+0C0h+var_140], eax
0x18002f1d9  mov     ebx, eax
0x18002f1db  test    eax, eax
0x18002f1dd  jns     loc_18002F268
0x18002f1e3  mov     rcx, rsi; CriticalSection
0x18002f1e6  call    cs:__imp_RtlLeaveCriticalSection
0x18002f1ed  nop     dword ptr [rax+rax+00h]
0x18002f1f2  xor     edx, edx
0x18002f1f4  mov     [r15], dl
0x18002f1f7  jmp     loc_18002F80E
0x18002f1fc  mov     rcx, [rbp+0C0h+var_F8]; void *
0x18002f200  xor     r8d, r8d; unsigned __int8
0x18002f203  mov     rdx, r13; struct _SERVER_SESSION *
0x18002f206  call    ?NlVerifyRpcIsSecured@@YAEPEAXPEAU_SERVER_SESSION@@E@Z; NlVerifyRpcIsSecured(void *,_SERVER_SESSION *,uchar)
0x18002f20b  test    al, al
0x18002f20d  jnz     short loc_18002F26A
0x18002f20f  mov     rcx, rsi; CriticalSection
0x18002f212  call    cs:__imp_RtlLeaveCriticalSection
0x18002f219  nop     dword ptr [rax+rax+00h]
0x18002f21e  mov     rsi, [rbp+0C0h+var_138]
0x18002f222  mov     ecx, edi; enum _NETLOGON_LOGON_INFO_CLASS
0x18002f224  lea     rdx, [rsi+30h]
0x18002f228  lea     r8, [rsi+20h]
0x18002f22c  call    ?NlpLogonTypeToText@@YAPEADW4_NETLOGON_LOGON_INFO_CLASS@@@Z; NlpLogonTypeToText(_NETLOGON_LOGON_INFO_CLASS)
0x18002f231  mov     r12, [rbp+0C0h+var_130]
0x18002f235  mov     r9, rax
0x18002f238  mov     [rsp+1D0h+var_1A0], rdx
0x18002f23d  mov     ecx, 100h; unsigned int
0x18002f242  mov     [rsp+1D0h+var_1A8], r8
0x18002f247  mov     rdx, r12; struct _DOMAIN_INFO *
0x18002f24a  lea     r8, aSamlogonHsLogo; "SamLogon: %hs logon of %wZ\\%wZ from %w"...
0x18002f251  mov     qword ptr [rsp+1D0h+var_1B0], rsi
0x18002f256  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002f25b  mov     ebx, 0C0000022h
0x18002f260  mov     [rbp+0C0h+var_140], ebx
0x18002f263  jmp     loc_18002F94C
0x18002f268  xor     ebx, ebx
0x18002f26a  movups  xmm0, xmmword ptr [r13+60h]
0x18002f26f  mov     r14d, [r13+20h]
0x18002f273  movdqu  [rbp+0C0h+var_88], xmm0
0x18002f278  mov     eax, [r13+48h]
0x18002f27c  mov     [rbp+0C0h+var_78], eax
0x18002f27f  mov     eax, [r13+34h]
0x18002f283  mov     rcx, [r13+98h]; SourceSid
0x18002f28a  mov     dword ptr [rbp+0C0h+var_F8], eax
0x18002f28d  mov     eax, [r13+90h]
0x18002f294  mov     [rbp+0C0h+var_104], eax
0x18002f297  mov     eax, [r13+94h]
0x18002f29e  mov     [rbp+0C0h+var_108], eax
0x18002f2a1  test    rcx, rcx
0x18002f2a4  jz      short loc_18002F2AF
0x18002f2a6  call    ?NlpCopySid@@YAPEAXPEAX@Z; NlpCopySid(void *)
0x18002f2ab  mov     [rbp+0C0h+pSid], rax
0x18002f2af  cmp     [r13+82h], bx
0x18002f2b7  jnz     short loc_18002F2DA
0x18002f2b9  mov     rdx, [r13+88h]; SourceString
0x18002f2c0  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x18002f2c4  call    cs:__imp_RtlInitUnicodeStringEx
0x18002f2cb  nop     dword ptr [rax+rax+00h]
0x18002f2d0  lea     rax, [rbp+0C0h+DestinationString]
0x18002f2d4  mov     [rbp+0C0h+var_100], rax
0x18002f2d8  jmp     short loc_18002F2DE
0x18002f2da  mov     [rbp+0C0h+var_100], rbx
0x18002f2de  cmp     r14d, 2
0x18002f2e2  jnz     short loc_18002F30A
0x18002f2e4  movzx   r9d, word ptr [r13+0A0h]
0x18002f2ec  lea     edx, [r14+0Eh]
0x18002f2f0  mov     r8, [r13+0A8h]
0x18002f2f7  lea     rcx, [rbp+0C0h+var_70]
0x18002f2fb  shr     r9, 1
0x18002f2fe  call    cs:__imp__o_wcsncpy_s
0x18002f305  nop     dword ptr [rax+rax+00h]
0x18002f30a  mov     rax, [rbp+0C0h+var_118]
0x18002f30e  test    byte ptr [rax], 2
0x18002f311  jz      short loc_18002F359
0x18002f313  test    byte ptr [r13+94h], 8
0x18002f31b  jnz     short loc_18002F359
  ... truncated ...
```
