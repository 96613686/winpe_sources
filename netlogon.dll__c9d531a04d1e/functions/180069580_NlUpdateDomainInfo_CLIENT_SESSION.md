# NlUpdateDomainInfo(_CLIENT_SESSION *)

- ea: `0x180069580`
- end: `0x18006a142`
- name: `?NlUpdateDomainInfo@@YAJPEAU_CLIENT_SESSION@@@Z`
- size: `3010`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *)`
- caller_count: `3`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800378d4`
- `0x18004ecb8`
- `0x18006b2e0`

## callees

- `0x180003200`
- `0x180007278`
- `0x18000d100`
- `0x18000d710`
- `0x18000e270`
- `0x18000e660`
- `0x18000ed34`
- `0x18001091c`
- `0x18001606c`
- `0x1800160a0`
- `0x180024158`
- `0x180024adc`
- `0x180027498`
- `0x180036150`
- `0x18003e71c`
- `0x18003e7dc`
- `0x18003f034`
- `0x18003f684`
- `0x180040f0c`
- `0x180045678`
- `0x180058e0c`
- `0x18005f358`
- `0x18005f79c`
- `0x180060734`
- `0x18006515c`
- `0x18006769c`
- `0x1800688e0`
- `0x180069580`
- `0x18006a42c`
- `0x18007455c`
- `0x1800825bc`
- `0x180083180`
- `0x1800852bc`
- `0x180087b8c`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800698bb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800698bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069fde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069fde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069fef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069fef`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180069931`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180069931`
- `logoncli!I_NetLogonGetDomainInfo` at `0x180069aa9`
- `logoncli!I_NetLogonGetDomainInfo` at `0x180069aa9`
- `ntdll!WinSqmSetDWORD` at `0x18006a0ba`
- `ntdll!WinSqmSetDWORD` at `0x18006a0ba`
- `ntdll!RtlEqualSid` at `0x18006977f`
- `ntdll!RtlEqualSid` at `0x18006977f`
- `ntdll!RtlInitUnicodeString` at `0x1800699b2`
- `ntdll!RtlInitUnicodeString` at `0x1800699b2`
- `ntdll!RtlLengthSid` at `0x1800697bc`
- `ntdll!RtlLengthSid` at `0x180069d58`
- `ntdll!RtlLengthSid` at `0x180069e71`
- `ntdll!RtlLengthSid` at `0x1800697bc`
- `ntdll!RtlLengthSid` at `0x180069d58`
- `ntdll!RtlLengthSid` at `0x180069e71`
- `netutils!NetApiBufferFree` at `0x18006989a`
- `netutils!NetApiBufferFree` at `0x1800698a8`
- `netutils!NetApiBufferFree` at `0x18006989a`
- `netutils!NetApiBufferFree` at `0x1800698a8`
- `ext-ms-win-branding-winbrand-l1-1-0!BrandingFormatString` at `0x18006995a`
- `ext-ms-win-branding-winbrand-l1-1-0!BrandingFormatString` at `0x18006995a`

## string_xrefs

- `0x180069655`: `ClientSession->CsFlags & CS_WRITER`
- `0x18006962c`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006964e`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x1800696d9`: `NlUpdateDomainInfo: NlGetNt4TrustedDomainList failed Status:0x%x\n`
- `0x18006971c`: `NlUpdateDomainInfo: Secure channel is down %lx\n`
- `0x180069968`: `NlUpdateDomainInfo: BrandingFormatString failed\n`
- `0x1800699ce`: `NlUpdateDomainInfo: NlpGetSupportedEncTypes failed %#x\n`
- `0x180069a2d`: `NlUpdateDomainInfo: NlBuildAuthenticator failed with status: 0x%lx\n`
- `0x18006a116`: `NlUpdateDomainInfo: denying access after status: 0x%lx\n`
- `0x180069c3f`: `NlUpdateDomainInfo: Can't NlSetDnsDomainDomainInfo %ld\n`
- `0x180069c85`: `NlUpdateDomainInfo: Can't NetpSetDnsComputerNameAsRequired %ld\n`
- `0x180069cc3`: `NlUpdateDomainInfo: Successfully set computer name with suffix %ws\n`
- `0x180069cae`: `NlUpdateDomainInfo: Can't NlSetDnsForestName %ld\n`
- `0x180069cff`: `NlUpdateDomainInfo: Can't NlUpdatePrimaryDomainInfo 0x%lx\n`
- `0x180069fd0`: `SYSTEM\CurrentControlSet\Services\Netlogon\AvoidSpnSet`
- `0x18006a025`: `NlUpdateDomainInfo: Can't get supported encryption types %#x\n`
- `0x18006981a`: `\system32\config\netlogon.ftl`

## pseudocode

```c
__int64 __fastcall NlUpdateDomainInfo(struct _CLIENT_SESSION *a1)
{
  int v2; // r12d
  char *v3; // r9
  struct _DS_DOMAIN_TRUSTSW *v4; // rsi
  struct _DOMAIN_INFO **v5; // r14
  int Nt4TrustedDomainList; // eax
  __int64 v7; // rdx
  LPVOID DomainSid; // rcx
  int started; // ebx
  __int64 result; // rax
  HKEY v11; // r13
  unsigned int j; // r15d
  __int64 v13; // rdi
  LPWSTR DnsDomainName; // rax
  ULONG v15; // eax
  unsigned int v16; // eax
  WCHAR *v17; // r15
  int v18; // eax
  int SupportedEncTypes; // eax
  unsigned int i; // r15d
  __int64 v21; // rdx
  int DomainInfo; // eax
  unsigned __int64 v23; // rax
  __int64 v24; // rcx
  struct _UNICODE_STRING *v25; // rbx
  struct _GUID *v26; // r15
  __int64 v27; // rax
  size_t v28; // r8
  const void *v29; // rdx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  unsigned int v32; // eax
  unsigned int v33; // eax
  int updated; // eax
  _QWORD *v35; // r9
  __int64 v36; // rdx
  __int64 v37; // r8
  unsigned int v38; // ebx
  void *v39; // rcx
  unsigned int v40; // ebx
  struct _DS_DOMAIN_TRUSTSW *v41; // r12
  __int64 v42; // rdx
  __int64 v43; // r13
  __int64 v44; // r15
  ULONG *v45; // rax
  ULONG v46; // ecx
  ULONG v47; // edx
  ULONG v48; // r8d
  size_t v49; // rbx
  __int64 v50; // rcx
  __int64 v51; // rcx
  unsigned __int8 v52; // r12
  int v53; // eax
  _DWORD *v54; // rax
  unsigned __int8 v55; // bl
  unsigned __int8 v56; // r15
  bool v57; // zf
  int v58; // ecx
  unsigned int v59; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID Buffer; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 v61[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v62[4]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v63; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v64[12]; // [rsp+6Ch] [rbp-94h]
  unsigned __int64 v65; // [rsp+78h] [rbp-88h] BYREF
  struct _DS_DOMAIN_TRUSTSW *v66[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v67[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v69; // [rsp+A8h] [rbp-58h]
  int v70; // [rsp+D0h] [rbp-30h]
  _OSVERSIONINFOW *p_VersionInformation; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  int v73; // [rsp+110h] [rbp+10h]
  unsigned int v74[3]; // [rsp+114h] [rbp+14h] BYREF
  __int64 v75; // [rsp+120h] [rbp+20h] BYREF
  int v76; // [rsp+128h] [rbp+28h]
  struct _CYPHER_BLOCK v77; // [rsp+130h] [rbp+30h] BYREF
  int v78; // [rsp+138h] [rbp+38h]
  _OSVERSIONINFOW VersionInformation; // [rsp+140h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+260h] [rbp+160h] BYREF
  __int128 v81; // [rsp+268h] [rbp+168h]
  unsigned __int16 v82[20]; // [rsp+278h] [rbp+178h] BYREF
  unsigned __int16 v83[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR v84[256]; // [rsp+320h] [rbp+220h] BYREF

  v2 = 0;
  v75 = 0;
  *(_DWORD *)v62 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  Buffer = 0;
  memset_0(v67, 0, 0x90u);
  memset_0(&VersionInformation, 0, 0x11Cu);
  v4 = 0;
  hKey = 0;
  v59 = 0;
  *(_DWORD *)&v64[8] = 0;
  *(_QWORD *)v64 = 1;
  v66[0] = 0;
  v63 = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0xDF0u,
      v3);
  if ( (*((_BYTE *)a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0xDF1u,
      v3);
  memset_0(v67, 0, 0x90u);
  if ( (*((_DWORD *)a1 + 79) & 0x40000) == 0 )
  {
    v5 = (struct _DOMAIN_INFO **)((char *)a1 + 272);
    Nt4TrustedDomainList = NlGetNt4TrustedDomainList(
                             *((PCWSTR *)a1 + 63),
                             (struct _UNICODE_STRING *)(*((_QWORD *)a1 + 34) + 56LL),
                             (struct _UNICODE_STRING *)(*((_QWORD *)a1 + 34) + 128LL),
                             *(void **)(*((_QWORD *)a1 + 34) + 184LL),
                             *(struct _GUID **)(*((_QWORD *)a1 + 34) + 208LL),
                             v66,
                             &v63,
                             &v59);
    started = Nt4TrustedDomainList;
    if ( Nt4TrustedDomainList < 0 )
    {
      NlPrintCsRoutine(
        0x100u,
        a1,
        L"NlUpdateDomainInfo: NlGetNt4TrustedDomainList failed Status:0x%x\n",
        (unsigned int)Nt4TrustedDomainList);
      result = 0;
      if ( started != -1073741790 )
        return (unsigned int)started;
      return result;
    }
    v4 = v66[0];
    LODWORD(v11) = v59;
    goto LABEL_15;
  }
  if ( !*((_DWORD *)a1 + 71) )
  {
    started = *((_DWORD *)a1 + 72);
    NlPrintCsRoutine(0x100u, a1, L"NlUpdateDomainInfo: Secure channel is down %lx\n", (unsigned int)started);
    v5 = (struct _DOMAIN_INFO **)((char *)a1 + 272);
    goto LABEL_13;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
    v18 = NlCaptureSiteName(v83);
  else
    v18 = NlCaptureSiteName_Old(v83);
  if ( v18 )
    v69 = v83;
  v5 = (struct _DOMAIN_INFO **)((char *)a1 + 272);
  v68 = *(_QWORD *)(*((_QWORD *)a1 + 34) + 280LL);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    v70 = 18612508;
    p_VersionInformation = &VersionInformation;
  }
  if ( (unsigned __int8)IsBrandingFormatStringPresent() )
  {
    v17 = (WCHAR *)BrandingFormatString(L"%WINDOWS_LONG%");
    if ( !v17 )
    {
      NlPrintRoutine(0x100u, L"NlUpdateDomainInfo: BrandingFormatString failed\n");
      started = -1073741801;
      v2 = 1;
      goto LABEL_27;
    }
    v2 = 1;
    *(_DWORD *)v64 = 1;
  }
  else
  {
    *(_DWORD *)v64 = 0;
    v17 = L"Windows";
  }
  *(_QWORD *)&v64[4] = v17;
  RtlInitUnicodeString(&DestinationString, v17);
  v73 |= 3u;
  SupportedEncTypes = NlpGetSupportedEncTypes(v74);
  started = SupportedEncTypes;
  if ( SupportedEncTypes < 0 )
  {
    NlPrintRoutine(0x100u, L"NlUpdateDomainInfo: NlpGetSupportedEncTypes failed %#x\n", (unsigned int)SupportedEncTypes);
    goto LABEL_27;
  }
  if ( (*((_DWORD *)*v5 + 148) & 0x1000) != 0 && (unsigned int)NlIsCompoundId() )
    v74[0] |= 0x20000u;
  started = NlBuildAuthenticator(
              (struct _CYPHER_BLOCK *)a1 + 54,
              (struct _CLIENT_SESSION *)((char *)a1 + 440),
              (struct _NETLOGON_AUTHENTICATOR *)&v75,
              *((_DWORD *)a1 + 79));
  if ( started < 0 )
  {
    NlPrintRoutine(
      0x100u,
      L"NlUpdateDomainInfo: NlBuildAuthenticator failed with status: 0x%lx\n",
      (unsigned int)started);
    goto LABEL_27;
  }
  started = -1073610748;
  for ( i = 0; i < 2; ++i )
  {
    started = NlStartApiClientSession(a1, 1u, i, started, (struct _CLIENT_SESSION *)((char *)a1 + 680));
    if ( started >= 0 )
    {
      v21 = (*((_DWORD *)a1 + 73) & 0x40000) != 0 ? *((_QWORD *)a1 + 27) : *((_QWORD *)*v5 + 33);
      DomainInfo = I_NetLogonGetDomainInfo(*((_QWORD *)a1 + 63), v21, &v75, &v77, 1, v67, &Buffer);
      started = DomainInfo;
      if ( DomainInfo < 0 )
        NlPrintRpcDebug("I_NetLogonGetDomainInfo", DomainInfo);
    }
    v23 = (unsigned int)(started + 1073610748);
    if ( (unsigned int)v23 > 0x32 )
      break;
    v24 = 0x4000000080001LL;
    if ( !_bittest64(&v24, v23) )
      break;
  }
  if ( !NlFinishApiClientSession(a1, 1u, 1u, (struct _CLIENT_SESSION *)((char *)a1 + 680)) && started >= 0 )
  {
    started = *((_DWORD *)a1 + 72);
    goto LABEL_13;
  }
  if ( NlpDidDcFail(started)
    || (unsigned int)NlCheckRpcAuthIsNetlogon(a1)
    && !(unsigned int)NlUpdateSeed((PUCHAR)a1 + 432, &v77, (PUCHAR)a1 + 440, *((_DWORD *)a1 + 79)) )
  {
    NlPrintCsRoutine(0x100u, a1, L"NlUpdateDomainInfo: denying access after status: 0x%lx\n", (unsigned int)started);
    if ( started >= 0 )
      started = -1073741790;
    goto LABEL_26;
  }
  if ( started < 0 )
    goto LABEL_26;
  v25 = (struct _UNICODE_STRING *)Buffer;
  v26 = (struct _GUID *)((char *)Buffer + 48);
  v27 = *((_QWORD *)Buffer + 6) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( !v27 )
    v27 = *((_QWORD *)Buffer + 7) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( !v27 )
    v26 = 0;
  if ( *((_WORD *)Buffer + 8) < 0x200u && *(_WORD *)Buffer < 0x20u )
  {
    v28 = *((unsigned __int16 *)Buffer + 8);
    v29 = (const void *)*((_QWORD *)Buffer + 3);
    v61[0] = 0;
    memcpy_0(v84, v29, v28);
    v30 = v25[1].Length & 0xFFFE;
    if ( v30 >= 0x200
      || (*(WCHAR *)((char *)v84 + v30) = 0,
          memcpy_0(v82, v25->Buffer, v25->Length),
          v31 = v25->Length & 0xFFFE,
          v31 >= 0x20) )
    {
      _report_rangecheckfailure();
    }
    *(unsigned __int16 *)((char *)v82 + v31) = 0;
    v32 = NlSetDomainNameInDomainInfo(*v5, v84, v82, v26, v61, 0, 0);
    *(_DWORD *)v62 = v32;
    if ( v32 )
    {
      NlPrintCsRoutine(0x100u, a1, L"NlUpdateDomainInfo: Can't NlSetDnsDomainDomainInfo %ld\n", v32);
LABEL_82:
      started = NetpApiStatusToNtStatus(*(unsigned int *)v62);
LABEL_13:
      if ( started >= 0 )
      {
        LODWORD(v11) = (_DWORD)hKey;
LABEL_15:
        for ( j = 0; j < (unsigned int)v11; ++j )
        {
          v13 = j;
          if ( (v4[v13].Flags & 8) == 0 )
          {
            DomainSid = v4[v13].DomainSid;
            if ( DomainSid )
            {
              if ( RtlEqualSid(DomainSid, *((PSID *)*v5 + 23)) )
              {
                v81 = 0;
                hKey = (HKEY)NlGlobalUnicodeComputerName;
                DnsDomainName = v4[v13].DnsDomainName;
                if ( !DnsDomainName )
                  DnsDomainName = v4[v13].NetbiosDomainName;
                *(_QWORD *)&v81 = DnsDomainName;
                v15 = RtlLengthSid(v4[v13].DomainSid);
                NlpWriteEventlogEx(
                  0x158Cu,
                  1u,
                  0,
                  0xFFFFFFFF,
                  (unsigned __int16 **)&hKey,
                  2u,
                  (unsigned __int8 *)v4[v13].DomainSid,
                  v15);
              }
            }
          }
        }
        v16 = NlWriteFileForestTrustListEx((__int64)DomainSid, v7, (__int64)v4, (unsigned int)v11);
        *(_DWORD *)v62 = v16;
        if ( v16 )
        {
          *(_QWORD *)&v81 = v16;
          hKey = (HKEY)L"\\system32\\config\\netlogon.ftl";
          NlpWriteEventlogEx(0x1690u, 1u, 0x40000000u, 0xFFFFFFFF, (unsigned __int16 **)&hKey, 2u, v62, 4u);
        }
        NlSetForestTrustList(*v5, v66, v63, (unsigned int)v11);
        v4 = v66[0];
        goto LABEL_26;
      }
      goto LABEL_26;
    }
    if ( v61[0] )
    {
      if ( (unsigned int)NetpSetDnsComputerNameAsRequired(v84) )
        NlPrintCsRoutine(
          0x100u,
          a1,
          L"NlUpdateDomainInfo: Can't NetpSetDnsComputerNameAsRequired %ld\n",
          *(unsigned int *)v62);
      else
        NlPrintCsRoutine(2u, a1, L"NlUpdateDomainInfo: Successfully set computer name with suffix %ws\n", v84);
    }
    v25 = (struct _UNICODE_STRING *)Buffer;
  }
  v33 = NlSetDnsForestName(v25 + 2, 0);
  *(_DWORD *)v62 = v33;
  if ( v33 )
  {
    NlPrintCsRoutine(0x100u, a1, L"NlUpdateDomainInfo: Can't NlSetDnsForestName %ld\n", v33);
    goto LABEL_82;
  }
  updated = NlUpdatePrimaryDomainInfo(
              *((void **)*v5 + 49),
              (struct _UNICODE_STRING *)Buffer,
              (struct _UNICODE_STRING *)Buffer + 1,
              (struct _UNICODE_STRING *)Buffer + 2,
              (struct _GUID *)Buffer + 3);
  started = updated;
  if ( updated >= 0 )
  {
    v35 = Buffer;
    if ( *((_DWORD *)Buffer + 38) )
    {
      do
      {
        v36 = v35[20];
        v37 = 152LL * (unsigned int)v4;
        v38 = *(unsigned __int16 *)(v37 + v36) + 60 + v63 + *(unsigned __int16 *)(v37 + v36 + 16);
        v39 = *(void **)(v37 + v36 + 64);
        v63 = v38;
        if ( v39 )
        {
          v38 += RtlLengthSid(v39);
          v63 = v38;
        }
        NetpULongRoundUp(v38, 4u, &v63);
        LODWORD(v4) = (_DWORD)v4 + 1;
      }
      while ( (unsigned int)v4 < *((_DWORD *)v35 + 38) );
    }
    v66[0] = (struct _DS_DOMAIN_TRUSTSW *)NetpMemoryAllocate(v63);
    v4 = v66[0];
    if ( v66[0] )
    {
      DomainSid = Buffer;
      v40 = 0;
      v59 = 0;
      v11 = (HKEY)*((unsigned int *)Buffer + 38);
      hKey = v11;
      v41 = &v66[0][(_QWORD)v11];
      v65 = (unsigned __int64)v41;
      if ( (_DWORD)v11 )
      {
        while ( 1 )
        {
          v42 = *((_QWORD *)DomainSid + 20);
          v43 = 152LL * v40;
          v44 = v40;
          if ( *(_WORD *)(v42 + v43 + 72) < 0x10u )
          {
            *(_QWORD *)&v4[v44].Flags = 2;
            *(_QWORD *)&v4[v44].TrustType = 1;
          }
          else
          {
            v45 = *(ULONG **)(v42 + v43 + 80);
            v46 = v45[1];
            v47 = v45[2];
            v48 = v45[3];
            v4[v44].Flags = *v45;
            v4[v44].ParentIndex = v46;
            v4[v44].TrustType = v47;
            v4[v44].TrustAttributes = v48;
          }
          v4[v44].DomainGuid = *(GUID *)(*((_QWORD *)Buffer + 20) + v43 + 48);
          if ( *(_QWORD *)(*((_QWORD *)Buffer + 20) + v43 + 64) )
          {
            v4[v44].DomainSid = v41;
            v49 = RtlLengthSid(*(PSID *)(*((_QWORD *)Buffer + 20) + v43 + 64));
            memcpy_0(v41, *(const void **)(*((_QWORD *)Buffer + 20) + v43 + 64), v49);
            v41 = (struct _DS_DOMAIN_TRUSTSW *)((char *)v41 + v49);
            v40 = v59;
            v65 = (unsigned __int64)v41;
          }
          else
          {
            v4[v44].DomainSid = 0;
          }
          if ( *(_WORD *)(*((_QWORD *)Buffer + 20) + v43 + 16) )
          {
            v4[v44].DnsDomainName = (LPWSTR)v41;
            memcpy_0(
              v41,
              *(const void **)(*((_QWORD *)Buffer + 20) + v43 + 24),
              *(unsigned __int16 *)(*((_QWORD *)Buffer + 20) + v43 + 16));
            v50 = *(unsigned __int16 *)(*((_QWORD *)Buffer + 20) + v43 + 16);
            *(_WORD *)((char *)&v41->NetbiosDomainName + v50) = 0;
            v41 = (struct _DS_DOMAIN_TRUSTSW *)((char *)v41 + v50 + 2);
            v65 = (unsigned __int64)v41;
          }
          else
          {
            v4[v44].DnsDomainName = 0;
          }
          if ( *(_WORD *)(*((_QWORD *)Buffer + 20) + v43) )
          {
            v4[v44].NetbiosDomainName = (LPWSTR)v41;
            memcpy_0(
              v41,
              *(const void **)(*((_QWORD *)Buffer + 20) + v43 + 8),
              *(unsigned __int16 *)(*((_QWORD *)Buffer + 20) + v43));
            v51 = *(unsigned __int16 *)(*((_QWORD *)Buffer + 20) + v43);
            *(_WORD *)((char *)&v41->NetbiosDomainName + v51) = 0;
            v41 = (struct _DS_DOMAIN_TRUSTSW *)((char *)v41 + v51 + 2);
            v65 = (unsigned __int64)v41;
          }
          else
          {
            v4[v44].NetbiosDomainName = 0;
          }
          NetpULongPtrRoundUp((unsigned __int64)v41, 4u, &v65);
          DomainSid = Buffer;
          v59 = ++v40;
          if ( v40 >= *((_DWORD *)Buffer + 38) )
            break;
          v41 = (struct _DS_DOMAIN_TRUSTSW *)v65;
        }
        LODWORD(v11) = (_DWORD)hKey;
        v5 = (struct _DOMAIN_INFO **)((char *)a1 + 272);
      }
      v52 = 0;
      if ( (*((_BYTE *)DomainSid + 248) & 2) != 0 )
      {
        hKey = 0;
        if ( RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Services\\Netlogon\\AvoidSpnSet",
               0,
               0x2000000u,
               &hKey) )
        {
          if ( (*((_DWORD *)a1 + 73) & 0x40000) == 0 )
          {
            v59 = 0;
            v53 = NlpGetSupportedEncTypes(&v59);
            if ( v53 >= 0 )
            {
              if ( (*((_DWORD *)*v5 + 148) & 0x1000) != 0 && (unsigned int)NlIsCompoundId() )
                v59 |= 0x20000u;
            }
            else
            {
              v59 = *((_DWORD *)Buffer + 63);
              NlPrintCsRoutine(
                0x100u,
                a1,
                L"NlUpdateDomainInfo: Can't get supported encryption types %#x\n",
                (unsigned int)v53);
            }
            v54 = Buffer;
            if ( *((_QWORD *)Buffer + 24) )
            {
              v55 = 0;
              v57 = (unsigned int)NlEqualDnsNameU(
                                    (struct _UNICODE_STRING *)((char *)Buffer + 184),
                                    (struct _UNICODE_STRING *)*v5 + 17) == 0;
              v54 = Buffer;
              v56 = v57;
            }
            else
            {
              v55 = 1;
              v56 = 1;
            }
            v58 = v54[63];
            if ( v58 && v58 != v59 )
            {
              v52 = 1;
              WinSqmSetDWORD(0, 10662);
            }
            NlSetDsSPN(
              1u,
              v55,
              v56,
              v52,
              *v5,
              *((unsigned __int16 **)a1 + 63),
              *((unsigned __int16 **)*v5 + 33),
              *((unsigned __int16 **)*v5 + 35),
              v59,
              1);
          }
        }
        else
        {
          RegCloseKey(hKey);
        }
      }
      started = 0;
      goto LABEL_15;
    }
    started = -1073741801;
  }
  else
  {
    NlPrintCsRoutine(0x100u, a1, L"NlUpdateDomainInfo: Can't NlUpdatePrimaryDomainInfo 0x%lx\n", (unsigned int)updated);
  }
LABEL_26:
  v17 = *(WCHAR **)&v64[4];
  v2 = *(_DWORD *)v64;
LABEL_27:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v4 )
    NetApiBufferFree(v4);
  if ( v2 && v17 )
    GlobalFree(v17);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180069580  push    rbp
0x180069582  push    rbx
0x180069583  push    rsi
0x180069584  push    rdi
0x180069585  push    r12
0x180069587  push    r13
0x180069589  push    r14
0x18006958b  push    r15
0x18006958d  lea     rbp, [rsp-438h]
0x180069595  sub     rsp, 538h
0x18006959c  mov     rax, cs:__security_cookie
0x1800695a3  xor     rax, rsp
0x1800695a6  mov     [rbp+470h+var_50], rax
0x1800695ad  xor     eax, eax
0x1800695af  mov     rdi, rcx
0x1800695b2  xor     r12d, r12d
0x1800695b5  mov     [rbp+470h+var_450], rax
0x1800695b9  mov     r14d, 90h
0x1800695bf  mov     dword ptr [rsp+570h+var_50C], r12d
0x1800695c4  mov     r8d, r14d; Size
0x1800695c7  mov     [rbp+470h+var_448], eax
0x1800695ca  xor     edx, edx; Val
0x1800695cc  mov     qword ptr [rbp+470h+var_440.data], rax
0x1800695d0  lea     rcx, [rbp+470h+var_4E0]; void *
0x1800695d4  mov     [rbp+470h+var_438], eax
0x1800695d7  mov     [rsp+570h+Buffer], r12
0x1800695dc  call    memset_0
0x1800695e1  mov     ebx, 11Ch
0x1800695e6  lea     rcx, [rbp+470h+VersionInformation]; void *
0x1800695ea  mov     r8d, ebx; Size
0x1800695ed  xor     edx, edx; Val
0x1800695ef  call    memset_0
0x1800695f4  lea     r13d, [r12+1]
0x1800695f9  mov     eax, r12d
0x1800695fc  mov     esi, r12d
0x1800695ff  mov     [rbp+470h+hKey], rax
0x180069606  mov     [rsp+570h+var_520], eax
0x18006960a  mov     [rsp+570h+hMem], r12
0x18006960f  mov     [rsp+570h+var_504], r13d
0x180069614  mov     [rbp+470h+var_4F0], r12
0x180069618  mov     [rsp+570h+var_508], r12d
0x18006961d  cmp     [rdi+148h], r12d
0x180069624  ja      short loc_18006963F
0x180069626  mov     r8d, 0DF0h; unsigned int
0x18006962c  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180069633  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18006963a  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006963f  test    byte ptr [rdi+124h], 8
0x180069646  jnz     short loc_180069661
0x180069648  mov     r8d, 0DF1h; unsigned int
0x18006964e  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180069655  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x18006965c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180069661  mov     r8, r14; Size
0x180069664  lea     rcx, [rbp+470h+var_4E0]; void *
0x180069668  xor     edx, edx; Val
0x18006966a  call    memset_0
0x18006966f  test    dword ptr [rdi+13Ch], 40000h
0x180069679  jnz     loc_180069709
0x18006967f  mov     rcx, [rdi+1F8h]; SourceString
0x180069686  lea     rax, [rsp+570h+var_520]
0x18006968b  mov     [rsp+570h+var_538], rax; unsigned int *
0x180069690  lea     r14, [rdi+110h]
0x180069697  mov     r9, [r14]
0x18006969a  lea     rax, [rsp+570h+var_508]
0x18006969f  mov     [rsp+570h+var_540], rax; unsigned int *
0x1800696a4  lea     rax, [rbp+470h+var_4F0]
0x1800696a8  mov     [rsp+570h+var_548], rax; struct _DS_DOMAIN_TRUSTSW **
0x1800696ad  mov     rax, [r9+0D0h]
0x1800696b4  lea     r8, [r9+80h]; struct _UNICODE_STRING *
0x1800696bb  lea     rdx, [r9+38h]; struct _UNICODE_STRING *
0x1800696bf  mov     [rsp+570h+phkResult], rax; struct _GUID *
0x1800696c4  mov     r9, [r9+0B8h]; void *
0x1800696cb  call    ?NlGetNt4TrustedDomainList@@YAJPEAGPEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@PEAPEAU_DS_DOMAIN_TRUSTSW@@PEAK5@Z; NlGetNt4TrustedDomainList(ushort *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,_DS_DOMAIN_TRUSTSW * *,ulong *,ulong *)
0x1800696d0  mov     ebx, eax
0x1800696d2  test    eax, eax
0x1800696d4  jns     short loc_1800696FE
0x1800696d6  mov     r9d, eax
0x1800696d9  lea     r8, aNlupdatedomain_0; "NlUpdateDomainInfo: NlGetNt4TrustedDoma"...
0x1800696e0  mov     rdx, rdi; struct _CLIENT_SESSION *
0x1800696e3  mov     ecx, 100h; unsigned int
0x1800696e8  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800696ed  cmp     ebx, 0C0000022h
0x1800696f3  mov     eax, r12d
0x1800696f6  cmovnz  eax, ebx
0x1800696f9  jmp     loc_1800698C3
0x1800696fe  mov     rsi, [rbp+470h+var_4F0]
0x180069702  mov     r13d, [rsp+570h+var_520]
0x180069707  jmp     short loc_180069749
0x180069709  cmp     [rdi+11Ch], r12d
0x180069710  jnz     loc_1800698E6
0x180069716  mov     ebx, [rdi+120h]
0x18006971c  lea     r8, aNlupdatedomain_4; "NlUpdateDomainInfo: Secure channel is d"...
0x180069723  mov     r9d, ebx
0x180069726  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180069729  mov     ecx, 100h; unsigned int
0x18006972e  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180069733  lea     r14, [rdi+110h]
0x18006973a  test    ebx, ebx
0x18006973c  js      loc_180069886
0x180069742  mov     r13, [rbp+470h+hKey]
0x180069749  mov     r15d, r12d
0x18006974c  test    r13d, r13d
0x18006974f  jz      loc_180069805
0x180069755  mov     eax, r15d
0x180069758  imul    rdi, rax, 38h ; '8'
0x18006975c  test    byte ptr [rdi+rsi+10h], 8
0x180069761  jnz     loc_1800697F9
0x180069767  mov     rcx, [rdi+rsi+20h]; Sid1
0x18006976c  test    rcx, rcx
0x18006976f  jz      loc_1800697F9
0x180069775  mov     rdx, [r14]
0x180069778  mov     rdx, [rdx+0B8h]; Sid2
0x18006977f  call    cs:__imp_RtlEqualSid
0x180069785  test    al, al
0x180069787  jz      short loc_1800697F9
0x180069789  mov     rax, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x180069790  xorps   xmm0, xmm0
0x180069793  movdqu  [rbp+470h+var_308], xmm0
0x18006979b  mov     [rbp+470h+hKey], rax
0x1800697a2  mov     rax, [rdi+rsi+8]
0x1800697a7  test    rax, rax
0x1800697aa  jnz     short loc_1800697B0
0x1800697ac  mov     rax, [rdi+rsi]
0x1800697b0  mov     qword ptr [rbp+470h+var_308], rax
0x1800697b7  mov     rcx, [rdi+rsi+20h]; Sid
0x1800697bc  call    cs:__imp_RtlLengthSid
0x1800697c2  mov     dword ptr [rsp+570h+var_538], eax; unsigned int
0x1800697c6  xor     r8d, r8d; unsigned int
0x1800697c9  mov     rax, [rdi+rsi+20h]
0x1800697ce  or      r9d, 0FFFFFFFFh; unsigned int
0x1800697d2  mov     [rsp+570h+var_540], rax; unsigned __int8 *
0x1800697d7  mov     ecx, 158Ch; unsigned int
0x1800697dc  lea     rax, [rbp+470h+hKey]
0x1800697e3  mov     dword ptr [rsp+570h+var_548], 2; unsigned int
0x1800697eb  lea     edx, [r8+1]; unsigned int
0x1800697ef  mov     [rsp+570h+phkResult], rax; unsigned __int16 **
0x1800697f4  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x1800697f9  inc     r15d
0x1800697fc  cmp     r15d, r13d
0x1800697ff  jb      loc_180069755
0x180069805  mov     r9d, r13d
0x180069808  mov     r8, rsi
0x18006980b  call    NlWriteFileForestTrustListEx
0x180069810  mov     dword ptr [rsp+570h+var_50C], eax
0x180069814  test    eax, eax
0x180069816  jz      short loc_18006986E
0x180069818  mov     eax, eax
0x18006981a  lea     rcx, aSystem32Config; "\\system32\\config\\netlogon.ftl"
0x180069821  mov     qword ptr [rbp+470h+var_308], rax
0x180069828  or      r9d, 0FFFFFFFFh; unsigned int
0x18006982c  mov     dword ptr [rsp+570h+var_538], 4; unsigned int
0x180069834  lea     rax, [rsp+570h+var_50C]
0x180069839  mov     [rsp+570h+var_540], rax; unsigned __int8 *
0x18006983e  mov     edx, 1; unsigned int
0x180069843  lea     rax, [rbp+470h+hKey]
0x18006984a  mov     [rbp+470h+hKey], rcx
0x180069851  mov     dword ptr [rsp+570h+var_548], 2; unsigned int
0x180069859  mov     ecx, 1690h; unsigned int
0x18006985e  mov     r8d, 40000000h; unsigned int
0x180069864  mov     [rsp+570h+phkResult], rax; unsigned __int16 **
0x180069869  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006986e  mov     r8d, [rsp+570h+var_508]; unsigned int
0x180069873  lea     rdx, [rbp+470h+var_4F0]; struct _DS_DOMAIN_TRUSTSW **
0x180069877  mov     rcx, [r14]; struct _DOMAIN_INFO *
0x18006987a  mov     r9d, r13d; unsigned int
0x18006987d  call    ?NlSetForestTrustList@@YAXPEAU_DOMAIN_INFO@@PEAPEAU_DS_DOMAIN_TRUSTSW@@KK@Z; NlSetForestTrustList(_DOMAIN_INFO *,_DS_DOMAIN_TRUSTSW * *,ulong,ulong)
0x180069882  mov     rsi, [rbp+470h+var_4F0]
0x180069886  mov     r15, [rsp+570h+hMem]
0x18006988b  mov     r12d, [rsp+570h+var_504]
0x180069890  mov     rcx, [rsp+570h+Buffer]; Buffer
0x180069895  test    rcx, rcx
0x180069898  jz      short loc_1800698A0
0x18006989a  call    cs:__imp_NetApiBufferFree
0x1800698a0  test    rsi, rsi
0x1800698a3  jz      short loc_1800698AE
0x1800698a5  mov     rcx, rsi; Buffer
0x1800698a8  call    cs:__imp_NetApiBufferFree
0x1800698ae  test    r12d, r12d
0x1800698b1  jz      short loc_1800698C1
0x1800698b3  test    r15, r15
0x1800698b6  jz      short loc_1800698C1
0x1800698b8  mov     rcx, r15; hMem
0x1800698bb  call    cs:__imp_GlobalFree
0x1800698c1  mov     eax, ebx
0x1800698c3  mov     rcx, [rbp+470h+var_50]
0x1800698ca  xor     rcx, rsp; StackCookie
0x1800698cd  call    __security_check_cookie
0x1800698d2  add     rsp, 538h
0x1800698d9  pop     r15
0x1800698db  pop     r14
0x1800698dd  pop     r13
0x1800698df  pop     r12
0x1800698e1  pop     rdi
0x1800698e2  pop     rsi
0x1800698e3  pop     rbx
0x1800698e4  pop     rbp
0x1800698e5  retn
0x1800698e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x1800698ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x1800698f2  lea     rcx, [rbp+470h+var_2D0]; unsigned __int16 *
0x1800698f9  test    al, al
0x1800698fb  jz      loc_180069986
0x180069901  call    ?NlCaptureSiteName@@YAHPEAG@Z; NlCaptureSiteName(ushort *)
0x180069906  test    eax, eax
0x180069908  jz      short loc_180069915
0x18006990a  lea     rax, [rbp+470h+var_2D0]
0x180069911  mov     [rbp+470h+var_4C8], rax
0x180069915  lea     r14, [rdi+110h]
0x18006991c  mov     rax, [r14]
0x18006991f  mov     rcx, [rax+118h]
0x180069926  mov     [rbp+470h+var_4D0], rcx
0x18006992a  lea     rcx, [rbp+470h+VersionInformation]; lpVersionInformation
0x18006992e  mov     [rbp+470h+VersionInformation.dwOSVersionInfoSize], ebx
0x180069931  call    cs:__imp_GetVersionExW
0x180069937  test    eax, eax
0x180069939  jz      short loc_18006994A
0x18006993b  lea     rax, [rbp+470h+VersionInformation]
0x18006993f  mov     [rbp+470h+var_4A0], 11C011Ch
0x180069946  mov     [rbp+470h+var_498], rax
0x18006994a  call    IsBrandingFormatStringPresent
0x18006994f  test    al, al
0x180069951  jz      short loc_18006999A
0x180069953  lea     rcx, aWindowsLong; "%WINDOWS_LONG%"
0x18006995a  call    cs:__imp_BrandingFormatString
0x180069960  mov     r15, rax
0x180069963  test    rax, rax
0x180069966  jnz     short loc_180069990
0x180069968  lea     rdx, aNlupdatedomain_2; "NlUpdateDomainInfo: BrandingFormatStrin"...
0x18006996f  mov     ecx, 100h; unsigned int
0x180069974  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180069979  mov     ebx, 0C0000017h
0x18006997e  mov     r12d, r13d
0x180069981  jmp     loc_180069890
0x180069986  call    ?NlCaptureSiteName_Old@@YAHQEAG@Z; NlCaptureSiteName_Old(ushort * const)
0x18006998b  jmp     loc_180069906
0x180069990  mov     r12d, r13d
0x180069993  mov     [rsp+570h+var_504], r13d
0x180069998  jmp     short loc_1800699A6
0x18006999a  mov     [rsp+570h+var_504], r12d
0x18006999f  lea     r15, aWindows; "Windows"
0x1800699a6  mov     rdx, r15; SourceString
0x1800699a9  mov     [rsp+570h+hMem], r15
0x1800699ae  lea     rcx, [rbp+470h+DestinationString]; DestinationString
0x1800699b2  call    cs:__imp_RtlInitUnicodeString
0x1800699b8  or      [rbp+470h+var_460], 3
0x1800699bc  lea     rcx, [rbp+470h+var_45C]; unsigned int *
0x1800699c0  call    ?NlpGetSupportedEncTypes@@YAJPEAK@Z; NlpGetSupportedEncTypes(ulong *)
0x1800699c5  mov     ebx, eax
0x1800699c7  test    eax, eax
0x1800699c9  jns     short loc_1800699E4
0x1800699cb  mov     r8d, eax
0x1800699ce  lea     rdx, aNlupdatedomain_9; "NlUpdateDomainInfo: NlpGetSupportedEncT"...
0x1800699d5  mov     ecx, 100h; unsigned int
0x1800699da  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800699df  jmp     loc_180069890
0x1800699e4  mov     rax, [r14]
0x1800699e7  test    dword ptr [rax+250h], 1000h
0x1800699f1  jz      short loc_180069A01
0x1800699f3  call    ?NlIsCompoundId@@YAHXZ; NlIsCompoundId(void)
0x1800699f8  test    eax, eax
0x1800699fa  jz      short loc_180069A01
0x1800699fc  bts     [rbp+470h+var_45C], 11h
0x180069a01  mov     r9d, [rdi+13Ch]; unsigned int
0x180069a08  lea     r13, [rdi+1B8h]
0x180069a0f  mov     rdx, r13; struct _NETLOGON_SESSION_KEY *
0x180069a12  lea     rcx, [rdi+1B0h]; struct _CYPHER_BLOCK *
0x180069a19  lea     r8, [rbp+470h+var_450]; struct _NETLOGON_AUTHENTICATOR *
0x180069a1d  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x180069a22  mov     ebx, eax
0x180069a24  xor     eax, eax
0x180069a26  test    ebx, ebx
0x180069a28  jns     short loc_180069A36
0x180069a2a  mov     r8d, ebx
0x180069a2d  lea     rdx, aNlupdatedomain_6; "NlUpdateDomainInfo: NlBuildAuthenticato"...
0x180069a34  jmp     short loc_1800699D5
0x180069a36  mov     ebx, 0C0020004h
0x180069a3b  lea     r12, [rdi+2A8h]
0x180069a42  mov     r15d, eax
0x180069a45  mov     r9d, ebx; int
0x180069a48  mov     [rsp+570h+phkResult], r12; struct _CLIENT_API *
0x180069a4d  mov     r8d, r15d; unsigned int
0x180069a50  mov     dl, 1; unsigned __int8
0x180069a52  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180069a55  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x180069a5a  mov     ebx, eax
0x180069a5c  test    eax, eax
0x180069a5e  js      short loc_180069AC3
0x180069a60  test    dword ptr [rdi+124h], 40000h
0x180069a6a  jz      short loc_180069A75
0x180069a6c  mov     rdx, [rdi+0D8h]
0x180069a73  jmp     short loc_180069A7F
0x180069a75  mov     rax, [r14]
0x180069a78  mov     rdx, [rax+108h]
0x180069a7f  mov     rcx, [rdi+1F8h]
0x180069a86  lea     rax, [rsp+570h+Buffer]
0x180069a8b  mov     [rsp+570h+var_540], rax
0x180069a90  lea     r9, [rbp+470h+var_440]
0x180069a94  lea     rax, [rbp+470h+var_4E0]
0x180069a98  mov     [rsp+570h+var_548], rax
  ... truncated ...
```
