# NlReparse(void)

- ea: `0x18004e118`
- end: `0x18004ec0e`
- name: `?NlReparse@@YAHXZ`
- size: `2806`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007070c`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18000ed34`
- `0x1800183bc`
- `0x180020620`
- `0x180022844`
- `0x180024adc`
- `0x180040178`
- `0x18004028c`
- `0x1800403d0`
- `0x1800416f0`
- `0x1800433f4`
- `0x1800434a4`
- `0x1800465ac`
- `0x18004688c`
- `0x180048110`
- `0x18004d8b4`
- `0x18004dd9c`
- `0x18004e118`
- `0x18004ec14`
- `0x18004f688`
- `0x18006e0ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e22a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e287`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e3e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e446`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e4a6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e518`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e22a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e287`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e3e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e446`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e4a6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e518`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004eb77`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004eb77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb81`
- `ntdll!RtlLeaveCriticalSection` at `0x18004eb34`
- `ntdll!RtlLeaveCriticalSection` at `0x18004eb6a`
- `ntdll!RtlLeaveCriticalSection` at `0x18004eb34`
- `ntdll!RtlLeaveCriticalSection` at `0x18004eb6a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004e33b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004e33b`
- `ntdll!RtlEnterCriticalSection` at `0x18004eb20`
- `ntdll!RtlEnterCriticalSection` at `0x18004eb4d`
- `ntdll!RtlEnterCriticalSection` at `0x18004eb20`
- `ntdll!RtlEnterCriticalSection` at `0x18004eb4d`
- `ntdll!RtlReleaseResource` at `0x18004e35a`
- `ntdll!RtlReleaseResource` at `0x18004e35a`

## string_xrefs

- `0x18004e3f3`: `   RpcDacl = %ws\n`
- `0x18004e453`: `   RemoteAccessCheckDacl = %ws\n`
- `0x18004eb87`: `NlReparse: SetEvent failed %ld\n`
- `0x18004ebcb`: `NlReparse: NlUpdateCompoundIdentityEncTypes failed, 0x%x \n`

## pseudocode

```c
int NlReparse(void)
{
  int v0; // r12d
  int result; // eax
  char v2; // r15
  char v3; // si
  unsigned __int16 *v4; // rbx
  char v5; // r14
  __int64 v6; // rbx
  unsigned __int16 *v7; // rdi
  unsigned __int16 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rbx
  const WCHAR *v11; // rbx
  const WCHAR *v12; // rbx
  unsigned int v13; // edi
  unsigned __int16 *v14; // rbx
  char IsEnabled; // al
  unsigned __int16 *v16; // rbx
  __int64 v17; // rdi
  __int64 v18; // rax
  char v19; // al
  unsigned __int16 *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  char v23; // al
  unsigned __int16 *v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int16 *v27; // rbx
  __int64 v28; // r8
  __int64 v29; // rbx
  __int64 v30; // rdi
  unsigned __int64 v31; // rbx
  int v32; // ecx
  const char *v33; // r9
  bool v34; // zf
  __int64 v35; // rax
  __int64 v36; // rax
  DWORD LastError; // eax
  int updated; // eax
  char v39; // [rsp+30h] [rbp-D0h]
  char v40; // [rsp+34h] [rbp-CCh]
  int v41; // [rsp+38h] [rbp-C8h]
  unsigned int v42; // [rsp+3Ch] [rbp-C4h]
  int v43; // [rsp+40h] [rbp-C0h]
  int v44; // [rsp+44h] [rbp-BCh]
  int v45; // [rsp+48h] [rbp-B8h]
  int v46; // [rsp+4Ch] [rbp-B4h]
  int v47; // [rsp+50h] [rbp-B0h]
  int v48; // [rsp+54h] [rbp-ACh]
  int v49; // [rsp+58h] [rbp-A8h]
  int v50; // [rsp+5Ch] [rbp-A4h]
  _DWORD v51[52]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v52; // [rsp+130h] [rbp+30h]
  unsigned __int16 *v53; // [rsp+140h] [rbp+40h]
  __int64 v54; // [rsp+148h] [rbp+48h]
  unsigned __int16 *v55; // [rsp+150h] [rbp+50h]
  unsigned int v56; // [rsp+158h] [rbp+58h]
  unsigned __int16 *v57; // [rsp+160h] [rbp+60h]
  unsigned __int16 *v58; // [rsp+168h] [rbp+68h]
  unsigned __int16 *v59; // [rsp+170h] [rbp+70h]
  unsigned __int16 *v60; // [rsp+180h] [rbp+80h]
  int v61; // [rsp+188h] [rbp+88h]
  LPCWSTR v62; // [rsp+190h] [rbp+90h]
  int v63; // [rsp+1D0h] [rbp+D0h]
  int v64; // [rsp+1D4h] [rbp+D4h]
  int v65; // [rsp+1ECh] [rbp+ECh]
  int v66; // [rsp+1FCh] [rbp+FCh]
  int v67; // [rsp+200h] [rbp+100h]
  __int64 v68; // [rsp+218h] [rbp+118h]
  LPCWSTR v69; // [rsp+220h] [rbp+120h]
  _BYTE v70[16]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(v51, 0, 0x220u);
  v0 = dword_1800F1228;
  v42 = dword_1800F1158;
  v44 = dword_1800F111C;
  v45 = dword_1800F1138;
  v47 = dword_1800F113C;
  v46 = dword_1800F1184;
  v43 = dword_1800F1170;
  v49 = dword_1800F11C4;
  v50 = dword_1800F12A0;
  v48 = dword_1800F11C8;
  v41 = dword_1800F124C;
  result = NlparseAllSections((struct _NETLOGON_PARAMETERS *)v51, 1u);
  v2 = 0;
  if ( !result )
    return result;
  v3 = 0;
  NlPrintRoutine(1u, L"Following are the effective values after parsing\n");
  v4 = v53;
  if ( !v53 )
  {
    if ( !Src )
    {
      v5 = 0;
LABEL_8:
      v40 = v5;
      goto LABEL_9;
    }
LABEL_7:
    NlPrintRoutine(1u, L"   Sysvol = %ws\n", v4);
    v5 = 1;
    v53 = Src;
    Src = v4;
    goto LABEL_8;
  }
  if ( !Src )
    goto LABEL_7;
  v5 = 0;
  v40 = 0;
  if ( (unsigned int)_o__wcsicmp(v53) )
    goto LABEL_7;
LABEL_9:
  v6 = v54;
  if ( !v54 )
  {
    if ( !qword_1800F11E8 )
      goto LABEL_15;
    goto LABEL_14;
  }
  if ( !qword_1800F11E8 || (unsigned int)_o__wcsicmp(v54) )
  {
LABEL_14:
    NlPrintRoutine(1u, L"   Scripts = %ws\n", v6);
    v5 = 1;
    v54 = qword_1800F11E8;
    qword_1800F11E8 = v6;
    v40 = 1;
  }
LABEL_15:
  v7 = v52;
  if ( v52 || qword_1800F11D0 )
  {
    v8 = v52;
    if ( v52 )
    {
      if ( *v52 )
      {
        do
        {
          NlPrintRoutine(1u, L"   NTLM Exceptions = %ws\n", v8);
          v9 = -1;
          do
            ++v9;
          while ( v8[v9] );
          v8 += v9 + 1;
        }
        while ( *v8 );
      }
    }
    else
    {
      NlPrintRoutine(1u, L"   NTLM Exceptions = NULL\n");
    }
    RtlAcquireResourceExclusive(&NlGlobalNtlmAllowedServersLock, 1u);
    v52 = qword_1800F11D0;
    qword_1800F11D0 = v7;
    RtlReleaseResource(&NlGlobalNtlmAllowedServersLock);
  }
  if ( v63 )
  {
    if ( dword_1800F1270 )
      goto LABEL_31;
    v5 = 1;
  }
  else if ( dword_1800F1270 )
  {
    v5 = 1;
  }
  v40 = v5;
LABEL_31:
  if ( v64 )
  {
    if ( dword_1800F1274 )
      goto LABEL_37;
    v5 = 1;
  }
  else if ( dword_1800F1274 )
  {
    v5 = 1;
  }
  v40 = v5;
LABEL_37:
  v10 = v68;
  if ( !v68 )
  {
    if ( !qword_1800F12B8 )
      goto LABEL_43;
LABEL_42:
    NlPrintRoutine(1u, L"   RpcDacl = %ws\n", v10);
    v68 = qword_1800F12B8;
    qword_1800F12B8 = v10;
    NlUpdateRpcSecurityDescriptor();
    goto LABEL_43;
  }
  if ( !qword_1800F12B8 || (unsigned int)_o__wcsicmp(v68) )
    goto LABEL_42;
LABEL_43:
  v11 = v69;
  if ( !v69 )
  {
    if ( !StringSecurityDescriptor )
      goto LABEL_49;
LABEL_48:
    NlPrintRoutine(1u, L"   RemoteAccessCheckDacl = %ws\n", v11);
    v69 = StringSecurityDescriptor;
    StringSecurityDescriptor = v11;
    NlUpdateRemoteAccessCheckSecurityDescriptor();
    goto LABEL_49;
  }
  if ( !StringSecurityDescriptor || (unsigned int)_o__wcsicmp(v69) )
    goto LABEL_48;
LABEL_49:
  v12 = v62;
  if ( v62 )
  {
    if ( qword_1800F1230 && !(unsigned int)_o__wcsicmp(v62) )
      goto LABEL_55;
  }
  else if ( !qword_1800F1230 )
  {
    goto LABEL_55;
  }
  NlPrintRoutine(1u, L"   VulnerableChannelAllowList = %ws\n", v12);
  v62 = qword_1800F1230;
  qword_1800F1230 = v12;
  NlUpdateVulnerableChannelAllowList();
LABEL_55:
  v13 = v56;
  v14 = v55;
  if ( v56 != dword_1800F11F8 )
    goto LABEL_61;
  if ( !v55 )
  {
    if ( !qword_1800F11F0 )
      goto LABEL_62;
    goto LABEL_61;
  }
  if ( !qword_1800F11F0 || (v39 = 0, (unsigned int)_o__wcsicmp(v55)) )
  {
LABEL_61:
    v2 = 1;
    NlPrintRoutine(1u, L"   SiteName (%ld) = %ws\n", v13, v14);
    v55 = qword_1800F11F0;
    qword_1800F11F0 = v14;
    dword_1800F11F8 = v13;
LABEL_62:
    v39 = v2;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
  v16 = v57;
  v17 = 0;
  if ( IsEnabled )
  {
    if ( !NlSitesSetSiteCoverageParam(0x2000u, v57) )
      goto LABEL_74;
    v3 = 1;
    NlPrintRoutine(1u, L"   SiteCoverage = ");
    if ( v16 )
    {
      while ( *v16 )
      {
        NlPrintRoutine(1u, L" '%ws'", v16);
        v18 = -1;
        do
          ++v18;
        while ( v16[v18] );
        v16 += (unsigned int)(v18 + 1);
      }
      goto LABEL_73;
    }
  }
  else
  {
    if ( !NlSitesSetSiteCoverageParam_Old(0x2000u, v57) )
      goto LABEL_74;
    v3 = 1;
    NlPrintRoutine(1u, L"   SiteCoverage = ");
    if ( v16 )
    {
      while ( *v16 )
      {
        NlPrintRoutine(1u, L" '%ws'", v16);
        v22 = -1;
        do
          ++v22;
        while ( v16[v22] );
        v16 += (unsigned int)(v22 + 1);
      }
      goto LABEL_73;
    }
  }
  NlPrintRoutine(1u, L"<NULL>");
LABEL_73:
  NlPrintRoutine(1u, L"\n");
  v57 = 0;
LABEL_74:
  v19 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
  v20 = v58;
  if ( v19 )
  {
    if ( !NlSitesSetSiteCoverageParam(0x8000u, v58) )
      goto LABEL_89;
    v3 = 1;
    NlPrintRoutine(1u, L"   GcSiteCoverage = ");
    if ( v20 )
    {
      while ( *v20 )
      {
        NlPrintRoutine(1u, L" '%ws'", v20);
        v21 = -1;
        do
          ++v21;
        while ( v20[v21] );
        v20 += (unsigned int)(v21 + 1);
      }
      goto LABEL_88;
    }
  }
  else
  {
    if ( !NlSitesSetSiteCoverageParam_Old(0x8000u, v58) )
      goto LABEL_89;
    v3 = 1;
    NlPrintRoutine(1u, L"   GcSiteCoverage = ");
    if ( v20 )
    {
      while ( *v20 )
      {
        NlPrintRoutine(1u, L" '%ws'", v20);
        v26 = -1;
        do
          ++v26;
        while ( v20[v26] );
        v20 += (unsigned int)(v26 + 1);
      }
      goto LABEL_88;
    }
  }
  NlPrintRoutine(1u, L"<NULL>");
LABEL_88:
  NlPrintRoutine(1u, L"\n");
  v58 = 0;
LABEL_89:
  v23 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
  v24 = v59;
  if ( v23 )
  {
    if ( NlSitesSetSiteCoverageParam(0x4000u, v59) )
    {
      v3 = 1;
      NlPrintRoutine(1u, L"   NdncSiteCoverage = ");
      if ( v24 )
      {
        while ( *v24 )
        {
          NlPrintRoutine(1u, L" '%ws'", v24);
          v25 = -1;
          do
            ++v25;
          while ( v24[v25] );
          v24 += (unsigned int)(v25 + 1);
        }
        goto LABEL_103;
      }
LABEL_102:
      NlPrintRoutine(1u, L"<NULL>");
LABEL_103:
      NlPrintRoutine(1u, L"\n");
      v59 = 0;
    }
  }
  else if ( NlSitesSetSiteCoverageParam_Old(0x4000u, v59) )
  {
    v3 = 1;
    NlPrintRoutine(1u, L"   NdncSiteCoverage = ");
    if ( v24 )
    {
      while ( *v24 )
      {
        NlPrintRoutine(1u, L" '%ws'", v24);
        v35 = -1;
        do
          ++v35;
        while ( v24[v35] );
        v24 += (unsigned int)(v35 + 1);
      }
      goto LABEL_103;
    }
    goto LABEL_102;
  }
  v27 = v60;
  if ( (unsigned int)NlDnsSetAvoidRegisterNameParam(v60) )
  {
    v3 = 1;
    NlPrintRoutine(1u, L"   DnsAvoidRegisterRecords = ");
    if ( v27 )
    {
      while ( *v27 )
      {
        NlPrintRoutine(1u, L" '%ws'", v27);
        v36 = -1;
        do
          ++v36;
        while ( v27[v36] );
        v27 += (unsigned int)(v36 + 1);
      }
    }
    else
    {
      NlPrintRoutine(1u, L"<NULL>");
    }
    NlPrintRoutine(1u, L"\n");
    v60 = 0;
  }
  if ( v0 != v61 )
    v3 = 1;
  if ( v66 != dword_1800F129C && !v66 && (Microsoft_Windows_Security_NetlogonEnableBits & 8) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(1, (__int64)MailslotDiscoveryEnabled, v28, 1, (__int64)v70);
  if ( !NlGlobalMemberWorkstation
    && v65 != dword_1800F128C
    && !v65
    && (Microsoft_Windows_Security_NetlogonEnableBits & 8) != 0 )
  {
    McGenEventWrite_EtwEventWriteTransfer(1, (__int64)DCListeningOnMailslots, v28, 1, (__int64)v70);
  }
  v29 = 0;
  do
  {
    if ( *(_DWORD *)((char *)v51 + HIDWORD(qword_1800EEAF8[v29 + 1])) != *(_DWORD *)((char *)&NlGlobalParameters
                                                                                   + HIDWORD(qword_1800EEAF8[v29 + 1])) )
    {
      NlPrintRoutine(
        1u,
        L"   %ws = %lu (0x%lx)\n",
        *(struct _unnamed_type_ParseTable_ near **)((char *)&ParseTable + v29 * 8));
      if ( LOBYTE(qword_1800EEAF8[v29 + 2]) )
        v3 = 1;
      *(_DWORD *)((char *)&NlGlobalParameters + HIDWORD(qword_1800EEAF8[v29 + 1])) = *(_DWORD *)((char *)v51
                                                                                               + HIDWORD(qword_1800EEAF8[v29 + 1]));
    }
    ++v17;
    v29 += 4;
  }
  while ( v17 != 55 );
  v30 = 0;
  v31 = 0;
  do
  {
    v32 = *(_DWORD *)((char *)v51 + (unsigned int)dword_1800EE7DC[v31 / 4]);
    if ( v32 != *(_DWORD *)((char *)&NlGlobalParameters + (unsigned int)dword_1800EE7DC[v31 / 4]) )
    {
      v33 = "TRUE";
      if ( !v32 )
        v33 = "FALSE";
      NlPrintRoutine(
        1u,
        L"   %ws = %hs\n",
        *(struct _unnamed_type_BoolParseTable_ near **)((char *)&BoolParseTable + v31),
        v33);
      if ( LOBYTE(qword_1800EE7E0[v31 / 8]) )
        v3 = 1;
      *(_DWORD *)((char *)&NlGlobalParameters + (unsigned int)dword_1800EE7DC[v31 / 4]) = *(_DWORD *)((char *)v51 + (unsigned int)dword_1800EE7DC[v31 / 4]);
    }
    ++v30;
    v31 += 24LL;
  }
  while ( v30 != 33 );
  dword_1800F12A0 = v67;
  NlParseRecompute((struct _NETLOGON_PARAMETERS *)&NlGlobalParameters);
  v34 = NlGlobalMemberWorkstation == 0;
  LODWORD(NlGlobalEventlogHandle[1].OwningThread) = 1000 * dword_1800F1178;
  if ( v34 )
  {
    if ( v3 )
      NlDnsForceScavenge(1, dword_1800F1158 != v42);
    if ( v40 || v41 != dword_1800F124C )
      NlCreateSysvolShares();
    if ( v43 != dword_1800F1170 )
    {
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
        NlRequestUpdateNextClosestSites();
      else
        NlSitesUpdateNextClosestSites_Old();
    }
  }
  else if ( v39 )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
      NlSetSiteName(qword_1800F11F0, 0);
    else
      NlSetSiteName_Old(qword_1800F11F0, 0);
  }
  if ( v44 != dword_1800F111C || v45 != dword_1800F1138 || v46 != dword_1800F1184 )
  {
    RtlEnterCriticalSection(&NlGlobalScavengerCritSect);
    dword_1800F1BC8 = 0;
    RtlLeaveCriticalSection(&NlGlobalScavengerCritSect);
  }
  if ( v47 != dword_1800F113C )
  {
    RtlEnterCriticalSection(&NlGlobalEventLoggerCritSect);
    dword_1800F1BF0 = 1000 * dword_1800F113C;
    RtlLeaveCriticalSection(&NlGlobalEventLoggerCritSect);
    if ( !SetEvent(NlGlobalTimerEvent) )
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"NlReparse: SetEvent failed %ld\n", LastError);
    }
  }
  if ( v48 != dword_1800F11C8 || v49 != dword_1800F11C4 || v50 != dword_1800F12A0 )
  {
    updated = NlUpdateCompoundIdentityEncTypes();
    if ( updated < 0 )
      NlPrintRoutine(1u, L"NlReparse: NlUpdateCompoundIdentityEncTypes failed, 0x%x \n", (unsigned int)updated);
  }
  NlParseFree((struct _NETLOGON_PARAMETERS *)v51);
  return 1;
}

```

## disassembly

```asm
0x18004e118  push    rbp
0x18004e11a  push    rbx
0x18004e11b  push    rsi
0x18004e11c  push    rdi
0x18004e11d  push    r12
0x18004e11f  push    r13
0x18004e121  push    r14
0x18004e123  push    r15
0x18004e125  lea     rbp, [rsp-1A8h]
0x18004e12d  sub     rsp, 2A8h
0x18004e134  mov     rax, cs:__security_cookie
0x18004e13b  xor     rax, rsp
0x18004e13e  mov     [rbp+1E0h+var_50], rax
0x18004e145  xor     edx, edx; Val
0x18004e147  lea     rcx, [rsp+2E0h+var_280]; void *
0x18004e14c  mov     r8d, 220h; Size
0x18004e152  call    memset_0
0x18004e157  mov     eax, cs:dword_1800F1158
0x18004e15d  lea     rcx, [rsp+2E0h+var_280]; struct _NETLOGON_PARAMETERS *
0x18004e162  mov     r13d, cs:dword_1800F124C
0x18004e169  mov     edi, 1
0x18004e16e  mov     r12d, cs:dword_1800F1228
0x18004e175  mov     dl, dil; unsigned __int8
0x18004e178  mov     [rsp+2E0h+var_2A4], eax
0x18004e17c  mov     eax, cs:dword_1800F111C
0x18004e182  mov     [rsp+2E0h+var_29C], eax
0x18004e186  mov     eax, cs:dword_1800F1138
0x18004e18c  mov     [rsp+2E0h+var_298], eax
0x18004e190  mov     eax, cs:dword_1800F113C
0x18004e196  mov     [rsp+2E0h+var_290], eax
0x18004e19a  mov     eax, cs:dword_1800F1184
0x18004e1a0  mov     [rsp+2E0h+var_294], eax
0x18004e1a4  mov     eax, cs:dword_1800F1170
0x18004e1aa  mov     [rsp+2E0h+var_2A0], eax
0x18004e1ae  mov     eax, cs:dword_1800F11C4
0x18004e1b4  mov     [rsp+2E0h+var_288], eax
0x18004e1b8  mov     eax, cs:dword_1800F12A0
0x18004e1be  mov     [rsp+2E0h+var_284], eax
0x18004e1c2  mov     eax, cs:dword_1800F11C8
0x18004e1c8  mov     [rsp+2E0h+var_28C], eax
0x18004e1cc  mov     [rsp+2E0h+var_2A8], r13d
0x18004e1d1  call    ?NlparseAllSections@@YAHPEAU_NETLOGON_PARAMETERS@@E@Z; NlparseAllSections(_NETLOGON_PARAMETERS *,uchar)
0x18004e1d6  xor     r15d, r15d
0x18004e1d9  test    eax, eax
0x18004e1db  jz      loc_18004EBEB
0x18004e1e1  lea     rdx, aFollowingAreTh; "Following are the effective values afte"...
0x18004e1e8  mov     ecx, edi; unsigned int
0x18004e1ea  mov     sil, r15b
0x18004e1ed  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e1f2  mov     rbx, [rbp+1E0h+var_1A0]
0x18004e1f6  test    rbx, rbx
0x18004e1f9  jnz     short loc_18004E209
0x18004e1fb  cmp     cs:Src, r15
0x18004e202  jnz     short loc_18004E234
0x18004e204  mov     r14b, r15b
0x18004e207  jmp     short loc_18004E25A
0x18004e209  mov     rdx, cs:Src
0x18004e210  test    rdx, rdx
0x18004e213  jz      short loc_18004E234
0x18004e215  mov     r14b, r15b
0x18004e218  mov     [rsp+2E0h+var_2AC], r14d
0x18004e21d  test    rbx, rbx
0x18004e220  jz      short loc_18004E25F
0x18004e222  test    rdx, rdx
0x18004e225  jz      short loc_18004E25F
0x18004e227  mov     rcx, rbx
0x18004e22a  call    cs:__imp__o__wcsicmp
0x18004e230  test    eax, eax
0x18004e232  jz      short loc_18004E25F
0x18004e234  mov     r8, rbx
0x18004e237  lea     rdx, aSysvolWs; "   Sysvol = %ws\n"
0x18004e23e  mov     ecx, edi; unsigned int
0x18004e240  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e245  mov     rax, cs:Src
0x18004e24c  mov     r14b, dil
0x18004e24f  mov     [rbp+1E0h+var_1A0], rax
0x18004e253  mov     cs:Src, rbx
0x18004e25a  mov     [rsp+2E0h+var_2AC], r14d
0x18004e25f  mov     rbx, [rbp+1E0h+var_198]
0x18004e263  test    rbx, rbx
0x18004e266  jnz     short loc_18004E273
0x18004e268  cmp     cs:qword_1800F11E8, r15
0x18004e26f  jnz     short loc_18004E291
0x18004e271  jmp     short loc_18004E2BC
0x18004e273  mov     rdx, cs:qword_1800F11E8
0x18004e27a  test    rdx, rdx
0x18004e27d  jz      short loc_18004E291
0x18004e27f  test    rbx, rbx
0x18004e282  jz      short loc_18004E2BC
0x18004e284  mov     rcx, rbx
0x18004e287  call    cs:__imp__o__wcsicmp
0x18004e28d  test    eax, eax
0x18004e28f  jz      short loc_18004E2BC
0x18004e291  mov     r8, rbx
0x18004e294  lea     rdx, aScriptsWs; "   Scripts = %ws\n"
0x18004e29b  mov     ecx, edi; unsigned int
0x18004e29d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e2a2  mov     rax, cs:qword_1800F11E8
0x18004e2a9  mov     r14b, dil
0x18004e2ac  mov     [rbp+1E0h+var_198], rax
0x18004e2b0  mov     cs:qword_1800F11E8, rbx
0x18004e2b7  mov     [rsp+2E0h+var_2AC], r14d
0x18004e2bc  mov     rdi, [rbp+1E0h+var_1B0]
0x18004e2c0  test    rdi, rdi
0x18004e2c3  jnz     short loc_18004E2D3
0x18004e2c5  cmp     cs:qword_1800F11D0, r15
0x18004e2cc  jnz     short loc_18004E2E1
0x18004e2ce  jmp     loc_18004E360
0x18004e2d3  cmp     cs:qword_1800F11D0, r15
0x18004e2da  jz      short loc_18004E2E1
0x18004e2dc  test    rdi, rdi
0x18004e2df  jz      short loc_18004E360
0x18004e2e1  mov     rbx, rdi
0x18004e2e4  test    rdi, rdi
0x18004e2e7  jz      short loc_18004E321
0x18004e2e9  cmp     [rdi], r15w
0x18004e2ed  jz      short loc_18004E332
0x18004e2ef  mov     r8, rbx
0x18004e2f2  lea     rdx, aNtlmExceptions; "   NTLM Exceptions = %ws\n"
0x18004e2f9  mov     ecx, 1; unsigned int
0x18004e2fe  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e303  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e307  inc     rax
0x18004e30a  cmp     [rbx+rax*2], r15w
0x18004e30f  jnz     short loc_18004E307
0x18004e311  lea     rbx, [rbx+rax*2]
0x18004e315  add     rbx, 2
0x18004e319  cmp     [rbx], r15w
0x18004e31d  jnz     short loc_18004E2EF
0x18004e31f  jmp     short loc_18004E332
0x18004e321  lea     rdx, aNtlmExceptions_0; "   NTLM Exceptions = NULL\n"
0x18004e328  mov     ecx, 1; unsigned int
0x18004e32d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e332  mov     dl, 1; Wait
0x18004e334  lea     rcx, ?NlGlobalNtlmAllowedServersLock@@3U_RTL_RESOURCE@@A; Resource
0x18004e33b  call    cs:__imp_RtlAcquireResourceExclusive
0x18004e341  mov     rax, cs:qword_1800F11D0
0x18004e348  lea     rcx, ?NlGlobalNtlmAllowedServersLock@@3U_RTL_RESOURCE@@A; Resource
0x18004e34f  mov     [rbp+1E0h+var_1B0], rax
0x18004e353  mov     cs:qword_1800F11D0, rdi
0x18004e35a  call    cs:__imp_RtlReleaseResource
0x18004e360  mov     edi, 1
0x18004e365  cmp     [rbp+1E0h+var_110], r15d
0x18004e36c  jz      short loc_18004E37C
0x18004e36e  cmp     cs:dword_1800F1270, r15d
0x18004e375  jnz     short loc_18004E390
0x18004e377  mov     r14b, dil
0x18004e37a  jmp     short loc_18004E38B
0x18004e37c  cmp     cs:dword_1800F1270, r15d
0x18004e383  movzx   r14d, r14b
0x18004e387  cmovnz  r14d, edi
0x18004e38b  mov     [rsp+2E0h+var_2AC], r14d
0x18004e390  cmp     [rbp+1E0h+var_10C], r15d
0x18004e397  jz      short loc_18004E3A7
0x18004e399  cmp     cs:dword_1800F1274, r15d
0x18004e3a0  jnz     short loc_18004E3BB
0x18004e3a2  mov     r14b, dil
0x18004e3a5  jmp     short loc_18004E3B6
0x18004e3a7  cmp     cs:dword_1800F1274, r15d
0x18004e3ae  movzx   r14d, r14b
0x18004e3b2  cmovnz  r14d, edi
0x18004e3b6  mov     [rsp+2E0h+var_2AC], r14d
0x18004e3bb  mov     rbx, [rbp+1E0h+var_C8]
0x18004e3c2  test    rbx, rbx
0x18004e3c5  jnz     short loc_18004E3D2
0x18004e3c7  cmp     cs:qword_1800F12B8, r15
0x18004e3ce  jnz     short loc_18004E3F0
0x18004e3d0  jmp     short loc_18004E41B
0x18004e3d2  mov     rdx, cs:qword_1800F12B8
0x18004e3d9  test    rdx, rdx
0x18004e3dc  jz      short loc_18004E3F0
0x18004e3de  test    rbx, rbx
0x18004e3e1  jz      short loc_18004E41B
0x18004e3e3  mov     rcx, rbx
0x18004e3e6  call    cs:__imp__o__wcsicmp
0x18004e3ec  test    eax, eax
0x18004e3ee  jz      short loc_18004E41B
0x18004e3f0  mov     r8, rbx
0x18004e3f3  lea     rdx, aRpcdaclWs; "   RpcDacl = %ws\n"
0x18004e3fa  mov     ecx, edi; unsigned int
0x18004e3fc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e401  mov     rax, cs:qword_1800F12B8
0x18004e408  mov     [rbp+1E0h+var_C8], rax
0x18004e40f  mov     cs:qword_1800F12B8, rbx
0x18004e416  call    ?NlUpdateRpcSecurityDescriptor@@YAXXZ; NlUpdateRpcSecurityDescriptor(void)
0x18004e41b  mov     rbx, [rbp+1E0h+var_C0]
0x18004e422  test    rbx, rbx
0x18004e425  jnz     short loc_18004E432
0x18004e427  cmp     cs:StringSecurityDescriptor, r15
0x18004e42e  jnz     short loc_18004E450
0x18004e430  jmp     short loc_18004E47B
0x18004e432  mov     rdx, cs:StringSecurityDescriptor
0x18004e439  test    rdx, rdx
0x18004e43c  jz      short loc_18004E450
0x18004e43e  test    rbx, rbx
0x18004e441  jz      short loc_18004E47B
0x18004e443  mov     rcx, rbx
0x18004e446  call    cs:__imp__o__wcsicmp
0x18004e44c  test    eax, eax
0x18004e44e  jz      short loc_18004E47B
0x18004e450  mov     r8, rbx
0x18004e453  lea     rdx, aRemoteaccessch; "   RemoteAccessCheckDacl = %ws\n"
0x18004e45a  mov     ecx, edi; unsigned int
0x18004e45c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e461  mov     rax, cs:StringSecurityDescriptor
0x18004e468  mov     [rbp+1E0h+var_C0], rax
0x18004e46f  mov     cs:StringSecurityDescriptor, rbx
0x18004e476  call    ?NlUpdateRemoteAccessCheckSecurityDescriptor@@YAXXZ; NlUpdateRemoteAccessCheckSecurityDescriptor(void)
0x18004e47b  mov     rbx, [rbp+1E0h+var_150]
0x18004e482  test    rbx, rbx
0x18004e485  jnz     short loc_18004E492
0x18004e487  cmp     cs:qword_1800F1230, r15
0x18004e48e  jnz     short loc_18004E4B0
0x18004e490  jmp     short loc_18004E4DB
0x18004e492  mov     rdx, cs:qword_1800F1230
0x18004e499  test    rdx, rdx
0x18004e49c  jz      short loc_18004E4B0
0x18004e49e  test    rbx, rbx
0x18004e4a1  jz      short loc_18004E4DB
0x18004e4a3  mov     rcx, rbx
0x18004e4a6  call    cs:__imp__o__wcsicmp
0x18004e4ac  test    eax, eax
0x18004e4ae  jz      short loc_18004E4DB
0x18004e4b0  mov     r8, rbx
0x18004e4b3  lea     rdx, aVulnerablechan_0; "   VulnerableChannelAllowList = %ws\n"
0x18004e4ba  mov     ecx, edi; unsigned int
0x18004e4bc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e4c1  mov     rax, cs:qword_1800F1230
0x18004e4c8  mov     [rbp+1E0h+var_150], rax
0x18004e4cf  mov     cs:qword_1800F1230, rbx
0x18004e4d6  call    ?NlUpdateVulnerableChannelAllowList@@YAXXZ; NlUpdateVulnerableChannelAllowList(void)
0x18004e4db  mov     edi, [rbp+1E0h+var_188]
0x18004e4de  cmp     edi, cs:dword_1800F11F8
0x18004e4e4  mov     rbx, [rbp+1E0h+var_190]
0x18004e4e8  jnz     short loc_18004E522
0x18004e4ea  test    rbx, rbx
0x18004e4ed  jnz     short loc_18004E4FA
0x18004e4ef  cmp     cs:qword_1800F11F0, r15
0x18004e4f6  jnz     short loc_18004E522
0x18004e4f8  jmp     short loc_18004E555
0x18004e4fa  mov     rdx, cs:qword_1800F11F0
0x18004e501  test    rdx, rdx
0x18004e504  jz      short loc_18004E522
0x18004e506  mov     [rsp+2E0h+var_2B0], r15b
0x18004e50b  test    rbx, rbx
0x18004e50e  jz      short loc_18004E55A
0x18004e510  test    rdx, rdx
0x18004e513  jz      short loc_18004E55A
0x18004e515  mov     rcx, rbx
0x18004e518  call    cs:__imp__o__wcsicmp
0x18004e51e  test    eax, eax
0x18004e520  jz      short loc_18004E55A
0x18004e522  mov     r15d, 1
0x18004e528  lea     rdx, aSitenameLdWs; "   SiteName (%ld) = %ws\n"
0x18004e52f  mov     ecx, r15d; unsigned int
0x18004e532  mov     r9, rbx
0x18004e535  mov     r8d, edi
0x18004e538  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e53d  mov     rax, cs:qword_1800F11F0
0x18004e544  mov     [rbp+1E0h+var_190], rax
0x18004e548  mov     cs:qword_1800F11F0, rbx
0x18004e54f  mov     cs:dword_1800F11F8, edi
0x18004e555  mov     [rsp+2E0h+var_2B0], r15b
0x18004e55a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x18004e561  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x18004e566  mov     rbx, [rbp+1E0h+var_180]
0x18004e56a  xor     edi, edi
0x18004e56c  mov     ecx, 2000h; unsigned int
0x18004e571  mov     rdx, rbx; unsigned __int16 *
0x18004e574  test    al, al
0x18004e576  jz      short loc_18004E5C6
0x18004e578  call    ?NlSitesSetSiteCoverageParam@@YAHKPEAG@Z; NlSitesSetSiteCoverageParam(ulong,ushort *)
0x18004e57d  test    eax, eax
0x18004e57f  jz      loc_18004E60B
0x18004e585  lea     esi, [rdi+1]
0x18004e588  mov     ecx, esi; unsigned int
0x18004e58a  lea     rdx, aSitecoverage_0; "   SiteCoverage = "
0x18004e591  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e596  test    rbx, rbx
0x18004e599  jz      short loc_18004E5EB
0x18004e59b  cmp     [rbx], di
0x18004e59e  jz      short loc_18004E5F9
0x18004e5a0  mov     r8, rbx
0x18004e5a3  lea     rdx, aWs; " '%ws'"
0x18004e5aa  mov     ecx, esi; unsigned int
0x18004e5ac  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004e5b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e5b5  inc     rax
0x18004e5b8  cmp     [rbx+rax*2], di
0x18004e5bc  jnz     short loc_18004E5B5
0x18004e5be  inc     eax
0x18004e5c0  lea     rbx, [rbx+rax*2]
0x18004e5c4  jmp     short loc_18004E59B
0x18004e5c6  call    ?NlSitesSetSiteCoverageParam_Old@@YAHKPEAG@Z; NlSitesSetSiteCoverageParam_Old(ulong,ushort *)
0x18004e5cb  test    eax, eax
0x18004e5cd  jz      short loc_18004E60B
0x18004e5cf  mov     esi, 1
0x18004e5d4  lea     rdx, aSitecoverage_0; "   SiteCoverage = "
0x18004e5db  mov     ecx, esi; unsigned int
0x18004e5dd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
  ... truncated ...
```
