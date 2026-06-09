# NlUpdateDomainInfo(_CLIENT_SESSION *)

- ea: `0x18006e50c`
- end: `0x18006f123`
- name: `?NlUpdateDomainInfo@@YAJPEAU_CLIENT_SESSION@@@Z`
- size: `3095`
- prototype: `__int64 __fastcall(struct _CLIENT_SESSION *)`
- caller_count: `3`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180039ac4`
- `0x18005239c`
- `0x180070380`

## callees

- `0x180003320`
- `0x180007518`
- `0x18000d7a0`
- `0x18000dd00`
- `0x18000e910`
- `0x18000ed00`
- `0x18000f3e4`
- `0x180010fcc`
- `0x180016a70`
- `0x180016aa4`
- `0x18002520c`
- `0x180025a74`
- `0x180028860`
- `0x1800381c0`
- `0x180040f18`
- `0x180040fe4`
- `0x180041924`
- `0x180041fbc`
- `0x180043a40`
- `0x1800485d0`
- `0x18005cdb4`
- `0x1800637d0`
- `0x180063c38`
- `0x180064c90`
- `0x180069c60`
- `0x18006c3e4`
- `0x18006d794`
- `0x18006e50c`
- `0x18006f430`
- `0x180079f10`
- `0x180088690`
- `0x180089328`
- `0x18008b510`
- `0x18008e0f0`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006e85f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006e85f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006efad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006efad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006efc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006efc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18006e8dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18006e8dc`
- `logoncli!I_NetLogonGetDomainInfo` at `0x18006ea66`
- `logoncli!I_NetLogonGetDomainInfo` at `0x18006ea66`
- `ntdll!WinSqmSetDWORD` at `0x18006f095`
- `ntdll!WinSqmSetDWORD` at `0x18006f095`
- `ntdll!RtlEqualSid` at `0x18006e70b`
- `ntdll!RtlEqualSid` at `0x18006e70b`
- `ntdll!RtlInitUnicodeString` at `0x18006e969`
- `ntdll!RtlInitUnicodeString` at `0x18006e969`
- `ntdll!RtlLengthSid` at `0x18006e74e`
- `ntdll!RtlLengthSid` at `0x18006ed1b`
- `ntdll!RtlLengthSid` at `0x18006ee3a`
- `ntdll!RtlLengthSid` at `0x18006e74e`
- `ntdll!RtlLengthSid` at `0x18006ed1b`
- `ntdll!RtlLengthSid` at `0x18006ee3a`
- `netutils!NetApiBufferFree` at `0x18006e832`
- `netutils!NetApiBufferFree` at `0x18006e846`
- `netutils!NetApiBufferFree` at `0x18006e832`
- `netutils!NetApiBufferFree` at `0x18006e846`
- `ext-ms-win-branding-winbrand-l1-1-0!BrandingFormatString` at `0x18006e90b`
- `ext-ms-win-branding-winbrand-l1-1-0!BrandingFormatString` at `0x18006e90b`

## string_xrefs

- `0x18006e5e1`: `ClientSession->CsFlags & CS_WRITER`
- `0x18006e5b8`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006e5da`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006e665`: `NlUpdateDomainInfo: NlGetNt4TrustedDomainList failed Status:0x%x\n`
- `0x18006e6a8`: `NlUpdateDomainInfo: Secure channel is down %lx\n`
- `0x18006e91f`: `NlUpdateDomainInfo: BrandingFormatString failed\n`
- `0x18006e98b`: `NlUpdateDomainInfo: NlpGetSupportedEncTypes failed %#x\n`
- `0x18006e9ea`: `NlUpdateDomainInfo: NlBuildAuthenticator failed with status: 0x%lx\n`
- `0x18006f0f7`: `NlUpdateDomainInfo: denying access after status: 0x%lx\n`
- `0x18006ec02`: `NlUpdateDomainInfo: Can't NlSetDnsDomainDomainInfo %ld\n`
- `0x18006ec48`: `NlUpdateDomainInfo: Can't NetpSetDnsComputerNameAsRequired %ld\n`
- `0x18006ec86`: `NlUpdateDomainInfo: Successfully set computer name with suffix %ws\n`
- `0x18006ec71`: `NlUpdateDomainInfo: Can't NlSetDnsForestName %ld\n`
- `0x18006ecc2`: `NlUpdateDomainInfo: Can't NlUpdatePrimaryDomainInfo 0x%lx\n`
- `0x18006ef9f`: `SYSTEM\CurrentControlSet\Services\Netlogon\AvoidSpnSet`
- `0x18006f000`: `NlUpdateDomainInfo: Can't get supported encryption types %#x\n`
- `0x18006e7b2`: `\system32\config\netlogon.ftl`

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
        v16 = NlWriteFileForestTrustListEx(DomainSid, v7, v4, (unsigned int)v11);
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
0x18006e50c  push    rbp
0x18006e50e  push    rbx
0x18006e50f  push    rsi
0x18006e510  push    rdi
0x18006e511  push    r12
0x18006e513  push    r13
0x18006e515  push    r14
0x18006e517  push    r15
0x18006e519  lea     rbp, [rsp-438h]
0x18006e521  sub     rsp, 538h
0x18006e528  mov     rax, cs:__security_cookie
0x18006e52f  xor     rax, rsp
0x18006e532  mov     [rbp+470h+var_50], rax
0x18006e539  xor     eax, eax
0x18006e53b  mov     rdi, rcx
0x18006e53e  xor     r12d, r12d
0x18006e541  mov     [rbp+470h+var_450], rax
0x18006e545  mov     r14d, 90h
0x18006e54b  mov     dword ptr [rsp+570h+var_50C], r12d
0x18006e550  mov     r8d, r14d; Size
0x18006e553  mov     [rbp+470h+var_448], eax
0x18006e556  xor     edx, edx; Val
0x18006e558  mov     qword ptr [rbp+470h+var_440.data], rax
0x18006e55c  lea     rcx, [rbp+470h+var_4E0]; void *
0x18006e560  mov     [rbp+470h+var_438], eax
0x18006e563  mov     [rsp+570h+Buffer], r12
0x18006e568  call    memset_0
0x18006e56d  mov     ebx, 11Ch
0x18006e572  lea     rcx, [rbp+470h+VersionInformation]; void *
0x18006e576  mov     r8d, ebx; Size
0x18006e579  xor     edx, edx; Val
0x18006e57b  call    memset_0
0x18006e580  lea     r13d, [r12+1]
0x18006e585  mov     eax, r12d
0x18006e588  mov     esi, r12d
0x18006e58b  mov     [rbp+470h+hKey], rax
0x18006e592  mov     [rsp+570h+var_520], eax
0x18006e596  mov     [rsp+570h+hMem], r12
0x18006e59b  mov     [rsp+570h+var_504], r13d
0x18006e5a0  mov     [rbp+470h+var_4F0], r12
0x18006e5a4  mov     [rsp+570h+var_508], r12d
0x18006e5a9  cmp     [rdi+148h], r12d
0x18006e5b0  ja      short loc_18006E5CB
0x18006e5b2  mov     r8d, 0DF0h; unsigned int
0x18006e5b8  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006e5bf  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18006e5c6  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006e5cb  test    byte ptr [rdi+124h], 8
0x18006e5d2  jnz     short loc_18006E5ED
0x18006e5d4  mov     r8d, 0DF1h; unsigned int
0x18006e5da  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006e5e1  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x18006e5e8  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006e5ed  mov     r8, r14; Size
0x18006e5f0  lea     rcx, [rbp+470h+var_4E0]; void *
0x18006e5f4  xor     edx, edx; Val
0x18006e5f6  call    memset_0
0x18006e5fb  test    dword ptr [rdi+13Ch], 40000h
0x18006e605  jnz     loc_18006E695
0x18006e60b  mov     rcx, [rdi+1F8h]; SourceString
0x18006e612  lea     rax, [rsp+570h+var_520]
0x18006e617  mov     [rsp+570h+var_538], rax; unsigned int *
0x18006e61c  lea     r14, [rdi+110h]
0x18006e623  mov     r9, [r14]
0x18006e626  lea     rax, [rsp+570h+var_508]
0x18006e62b  mov     [rsp+570h+var_540], rax; unsigned int *
0x18006e630  lea     rax, [rbp+470h+var_4F0]
0x18006e634  mov     [rsp+570h+var_548], rax; struct _DS_DOMAIN_TRUSTSW **
0x18006e639  mov     rax, [r9+0D0h]
0x18006e640  lea     r8, [r9+80h]; struct _UNICODE_STRING *
0x18006e647  lea     rdx, [r9+38h]; struct _UNICODE_STRING *
0x18006e64b  mov     [rsp+570h+phkResult], rax; struct _GUID *
0x18006e650  mov     r9, [r9+0B8h]; void *
0x18006e657  call    ?NlGetNt4TrustedDomainList@@YAJPEAGPEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@PEAPEAU_DS_DOMAIN_TRUSTSW@@PEAK5@Z; NlGetNt4TrustedDomainList(ushort *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,_DS_DOMAIN_TRUSTSW * *,ulong *,ulong *)
0x18006e65c  mov     ebx, eax
0x18006e65e  test    eax, eax
0x18006e660  jns     short loc_18006E68A
0x18006e662  mov     r9d, eax
0x18006e665  lea     r8, aNlupdatedomain_0; "NlUpdateDomainInfo: NlGetNt4TrustedDoma"...
0x18006e66c  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006e66f  mov     ecx, 100h; unsigned int
0x18006e674  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006e679  cmp     ebx, 0C0000022h
0x18006e67f  mov     eax, r12d
0x18006e682  cmovnz  eax, ebx
0x18006e685  jmp     loc_18006E86D
0x18006e68a  mov     rsi, [rbp+470h+var_4F0]
0x18006e68e  mov     r13d, [rsp+570h+var_520]
0x18006e693  jmp     short loc_18006E6D5
0x18006e695  cmp     [rdi+11Ch], r12d
0x18006e69c  jnz     loc_18006E891
0x18006e6a2  mov     ebx, [rdi+120h]
0x18006e6a8  lea     r8, aNlupdatedomain_4; "NlUpdateDomainInfo: Secure channel is d"...
0x18006e6af  mov     r9d, ebx
0x18006e6b2  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006e6b5  mov     ecx, 100h; unsigned int
0x18006e6ba  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006e6bf  lea     r14, [rdi+110h]
0x18006e6c6  test    ebx, ebx
0x18006e6c8  js      loc_18006E81E
0x18006e6ce  mov     r13, [rbp+470h+hKey]
0x18006e6d5  mov     r15d, r12d
0x18006e6d8  test    r13d, r13d
0x18006e6db  jz      loc_18006E79D
0x18006e6e1  mov     eax, r15d
0x18006e6e4  imul    rdi, rax, 38h ; '8'
0x18006e6e8  test    byte ptr [rdi+rsi+10h], 8
0x18006e6ed  jnz     loc_18006E791
0x18006e6f3  mov     rcx, [rdi+rsi+20h]; Sid1
0x18006e6f8  test    rcx, rcx
0x18006e6fb  jz      loc_18006E791
0x18006e701  mov     rdx, [r14]
0x18006e704  mov     rdx, [rdx+0B8h]; Sid2
0x18006e70b  call    cs:__imp_RtlEqualSid
0x18006e712  nop     dword ptr [rax+rax+00h]
0x18006e717  test    al, al
0x18006e719  jz      short loc_18006E791
0x18006e71b  mov     rax, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x18006e722  xorps   xmm0, xmm0
0x18006e725  movdqu  [rbp+470h+var_308], xmm0
0x18006e72d  mov     [rbp+470h+hKey], rax
0x18006e734  mov     rax, [rdi+rsi+8]
0x18006e739  test    rax, rax
0x18006e73c  jnz     short loc_18006E742
0x18006e73e  mov     rax, [rdi+rsi]
0x18006e742  mov     qword ptr [rbp+470h+var_308], rax
0x18006e749  mov     rcx, [rdi+rsi+20h]; Sid
0x18006e74e  call    cs:__imp_RtlLengthSid
0x18006e755  nop     dword ptr [rax+rax+00h]
0x18006e75a  mov     dword ptr [rsp+570h+var_538], eax; unsigned int
0x18006e75e  xor     r8d, r8d; unsigned int
0x18006e761  mov     rax, [rdi+rsi+20h]
0x18006e766  or      r9d, 0FFFFFFFFh; unsigned int
0x18006e76a  mov     [rsp+570h+var_540], rax; unsigned __int8 *
0x18006e76f  mov     ecx, 158Ch; unsigned int
0x18006e774  lea     rax, [rbp+470h+hKey]
0x18006e77b  mov     dword ptr [rsp+570h+var_548], 2; unsigned int
0x18006e783  lea     edx, [r8+1]; unsigned int
0x18006e787  mov     [rsp+570h+phkResult], rax; unsigned __int16 **
0x18006e78c  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006e791  inc     r15d
0x18006e794  cmp     r15d, r13d
0x18006e797  jb      loc_18006E6E1
0x18006e79d  mov     r9d, r13d
0x18006e7a0  mov     r8, rsi
0x18006e7a3  call    NlWriteFileForestTrustListEx
0x18006e7a8  mov     dword ptr [rsp+570h+var_50C], eax
0x18006e7ac  test    eax, eax
0x18006e7ae  jz      short loc_18006E806
0x18006e7b0  mov     eax, eax
0x18006e7b2  lea     rcx, aSystem32Config; "\\system32\\config\\netlogon.ftl"
0x18006e7b9  mov     qword ptr [rbp+470h+var_308], rax
0x18006e7c0  or      r9d, 0FFFFFFFFh; unsigned int
0x18006e7c4  mov     dword ptr [rsp+570h+var_538], 4; unsigned int
0x18006e7cc  lea     rax, [rsp+570h+var_50C]
0x18006e7d1  mov     [rsp+570h+var_540], rax; unsigned __int8 *
0x18006e7d6  mov     edx, 1; unsigned int
0x18006e7db  lea     rax, [rbp+470h+hKey]
0x18006e7e2  mov     [rbp+470h+hKey], rcx
0x18006e7e9  mov     dword ptr [rsp+570h+var_548], 2; unsigned int
0x18006e7f1  mov     ecx, 1690h; unsigned int
0x18006e7f6  mov     r8d, 40000000h; unsigned int
0x18006e7fc  mov     [rsp+570h+phkResult], rax; unsigned __int16 **
0x18006e801  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006e806  mov     r8d, [rsp+570h+var_508]; unsigned int
0x18006e80b  lea     rdx, [rbp+470h+var_4F0]; struct _DS_DOMAIN_TRUSTSW **
0x18006e80f  mov     rcx, [r14]; struct _DOMAIN_INFO *
0x18006e812  mov     r9d, r13d; unsigned int
0x18006e815  call    ?NlSetForestTrustList@@YAXPEAU_DOMAIN_INFO@@PEAPEAU_DS_DOMAIN_TRUSTSW@@KK@Z; NlSetForestTrustList(_DOMAIN_INFO *,_DS_DOMAIN_TRUSTSW * *,ulong,ulong)
0x18006e81a  mov     rsi, [rbp+470h+var_4F0]
0x18006e81e  mov     r15, [rsp+570h+hMem]
0x18006e823  mov     r12d, [rsp+570h+var_504]
0x18006e828  mov     rcx, [rsp+570h+Buffer]; Buffer
0x18006e82d  test    rcx, rcx
0x18006e830  jz      short loc_18006E83E
0x18006e832  call    cs:__imp_NetApiBufferFree
0x18006e839  nop     dword ptr [rax+rax+00h]
0x18006e83e  test    rsi, rsi
0x18006e841  jz      short loc_18006E852
0x18006e843  mov     rcx, rsi; Buffer
0x18006e846  call    cs:__imp_NetApiBufferFree
0x18006e84d  nop     dword ptr [rax+rax+00h]
0x18006e852  test    r12d, r12d
0x18006e855  jz      short loc_18006E86B
0x18006e857  test    r15, r15
0x18006e85a  jz      short loc_18006E86B
0x18006e85c  mov     rcx, r15; hMem
0x18006e85f  call    cs:__imp_GlobalFree
0x18006e866  nop     dword ptr [rax+rax+00h]
0x18006e86b  mov     eax, ebx
0x18006e86d  mov     rcx, [rbp+470h+var_50]
0x18006e874  xor     rcx, rsp; StackCookie
0x18006e877  call    __security_check_cookie
0x18006e87c  add     rsp, 538h
0x18006e883  pop     r15
0x18006e885  pop     r14
0x18006e887  pop     r13
0x18006e889  pop     r12
0x18006e88b  pop     rdi
0x18006e88c  pop     rsi
0x18006e88d  pop     rbx
0x18006e88e  pop     rbp
0x18006e88f  retn
0x18006e891  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x18006e898  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x18006e89d  lea     rcx, [rbp+470h+var_2D0]; unsigned __int16 *
0x18006e8a4  test    al, al
0x18006e8a6  jz      loc_18006E93D
0x18006e8ac  call    ?NlCaptureSiteName@@YAHPEAG@Z; NlCaptureSiteName(ushort *)
0x18006e8b1  test    eax, eax
0x18006e8b3  jz      short loc_18006E8C0
0x18006e8b5  lea     rax, [rbp+470h+var_2D0]
0x18006e8bc  mov     [rbp+470h+var_4C8], rax
0x18006e8c0  lea     r14, [rdi+110h]
0x18006e8c7  mov     rax, [r14]
0x18006e8ca  mov     rcx, [rax+118h]
0x18006e8d1  mov     [rbp+470h+var_4D0], rcx
0x18006e8d5  lea     rcx, [rbp+470h+VersionInformation]; lpVersionInformation
0x18006e8d9  mov     [rbp+470h+VersionInformation.dwOSVersionInfoSize], ebx
0x18006e8dc  call    cs:__imp_GetVersionExW
0x18006e8e3  nop     dword ptr [rax+rax+00h]
0x18006e8e8  test    eax, eax
0x18006e8ea  jz      short loc_18006E8FB
0x18006e8ec  lea     rax, [rbp+470h+VersionInformation]
0x18006e8f0  mov     [rbp+470h+var_4A0], 11C011Ch
0x18006e8f7  mov     [rbp+470h+var_498], rax
0x18006e8fb  call    IsBrandingFormatStringPresent
0x18006e900  test    al, al
0x18006e902  jz      short loc_18006E951
0x18006e904  lea     rcx, aWindowsLong; "%WINDOWS_LONG%"
0x18006e90b  call    cs:__imp_BrandingFormatString
0x18006e912  nop     dword ptr [rax+rax+00h]
0x18006e917  mov     r15, rax
0x18006e91a  test    rax, rax
0x18006e91d  jnz     short loc_18006E947
0x18006e91f  lea     rdx, aNlupdatedomain_2; "NlUpdateDomainInfo: BrandingFormatStrin"...
0x18006e926  mov     ecx, 100h; unsigned int
0x18006e92b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006e930  mov     ebx, 0C0000017h
0x18006e935  mov     r12d, r13d
0x18006e938  jmp     loc_18006E828
0x18006e93d  call    ?NlCaptureSiteName_Old@@YAHQEAG@Z; NlCaptureSiteName_Old(ushort * const)
0x18006e942  jmp     loc_18006E8B1
0x18006e947  mov     r12d, r13d
0x18006e94a  mov     [rsp+570h+var_504], r13d
0x18006e94f  jmp     short loc_18006E95D
0x18006e951  mov     [rsp+570h+var_504], r12d
0x18006e956  lea     r15, aWindows; "Windows"
0x18006e95d  mov     rdx, r15; SourceString
0x18006e960  mov     [rsp+570h+hMem], r15
0x18006e965  lea     rcx, [rbp+470h+DestinationString]; DestinationString
0x18006e969  call    cs:__imp_RtlInitUnicodeString
0x18006e970  nop     dword ptr [rax+rax+00h]
0x18006e975  or      [rbp+470h+var_460], 3
0x18006e979  lea     rcx, [rbp+470h+var_45C]; unsigned int *
0x18006e97d  call    ?NlpGetSupportedEncTypes@@YAJPEAK@Z; NlpGetSupportedEncTypes(ulong *)
0x18006e982  mov     ebx, eax
0x18006e984  test    eax, eax
0x18006e986  jns     short loc_18006E9A1
0x18006e988  mov     r8d, eax
0x18006e98b  lea     rdx, aNlupdatedomain_9; "NlUpdateDomainInfo: NlpGetSupportedEncT"...
0x18006e992  mov     ecx, 100h; unsigned int
0x18006e997  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006e99c  jmp     loc_18006E828
0x18006e9a1  mov     rax, [r14]
0x18006e9a4  test    dword ptr [rax+250h], 1000h
0x18006e9ae  jz      short loc_18006E9BE
0x18006e9b0  call    ?NlIsCompoundId@@YAHXZ; NlIsCompoundId(void)
0x18006e9b5  test    eax, eax
0x18006e9b7  jz      short loc_18006E9BE
0x18006e9b9  bts     [rbp+470h+var_45C], 11h
0x18006e9be  mov     r9d, [rdi+13Ch]; unsigned int
0x18006e9c5  lea     r13, [rdi+1B8h]
0x18006e9cc  mov     rdx, r13; struct _NETLOGON_SESSION_KEY *
0x18006e9cf  lea     rcx, [rdi+1B0h]; struct _CYPHER_BLOCK *
0x18006e9d6  lea     r8, [rbp+470h+var_450]; struct _NETLOGON_AUTHENTICATOR *
0x18006e9da  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x18006e9df  mov     ebx, eax
0x18006e9e1  xor     eax, eax
0x18006e9e3  test    ebx, ebx
0x18006e9e5  jns     short loc_18006E9F3
0x18006e9e7  mov     r8d, ebx
0x18006e9ea  lea     rdx, aNlupdatedomain_6; "NlUpdateDomainInfo: NlBuildAuthenticato"...
0x18006e9f1  jmp     short loc_18006E992
0x18006e9f3  mov     ebx, 0C0020004h
0x18006e9f8  lea     r12, [rdi+2A8h]
0x18006e9ff  mov     r15d, eax
0x18006ea02  mov     r9d, ebx; int
0x18006ea05  mov     [rsp+570h+phkResult], r12; struct _CLIENT_API *
0x18006ea0a  mov     r8d, r15d; unsigned int
0x18006ea0d  mov     dl, 1; unsigned __int8
0x18006ea0f  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18006ea12  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x18006ea17  mov     ebx, eax
0x18006ea19  test    eax, eax
0x18006ea1b  js      short loc_18006EA86
0x18006ea1d  test    dword ptr [rdi+124h], 40000h
0x18006ea27  jz      short loc_18006EA32
0x18006ea29  mov     rdx, [rdi+0D8h]
0x18006ea30  jmp     short loc_18006EA3C
  ... truncated ...
```
