# NlReparse(void)

- ea: `0x18005179c`
- end: `0x1800522eb`
- name: `?NlReparse@@YAHXZ`
- size: `2895`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180075b60`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18000f3e4`
- `0x180018ed8`
- `0x180021524`
- `0x18002396c`
- `0x180025a74`
- `0x180042b88`
- `0x180042cd4`
- `0x180042e54`
- `0x1800442dc`
- `0x180046208`
- `0x1800462cc`
- `0x180049614`
- `0x180049924`
- `0x18004b2f0`
- `0x180050ea4`
- `0x180051400`
- `0x18005179c`
- `0x1800522f4`
- `0x180052d98`
- `0x18007331c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800518ae`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051911`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051a86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051aec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051b52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051bca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800518ae`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051911`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051a86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051aec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051b52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180051bca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180052247`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180052247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052257`
- `ntdll!RtlLeaveCriticalSection` at `0x1800521f2`
- `ntdll!RtlLeaveCriticalSection` at `0x180052234`
- `ntdll!RtlLeaveCriticalSection` at `0x1800521f2`
- `ntdll!RtlLeaveCriticalSection` at `0x180052234`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800519cf`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800519cf`
- `ntdll!RtlEnterCriticalSection` at `0x1800521d8`
- `ntdll!RtlEnterCriticalSection` at `0x180052211`
- `ntdll!RtlEnterCriticalSection` at `0x1800521d8`
- `ntdll!RtlEnterCriticalSection` at `0x180052211`
- `ntdll!RtlReleaseResource` at `0x1800519f4`
- `ntdll!RtlReleaseResource` at `0x1800519f4`

## string_xrefs

- `0x180051a99`: `   RpcDacl = %ws\n`
- `0x180051aff`: `   RemoteAccessCheckDacl = %ws\n`
- `0x180052263`: `NlReparse: SetEvent failed %ld\n`
- `0x1800522a7`: `NlReparse: NlUpdateCompoundIdentityEncTypes failed, 0x%x \n`

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
  v0 = dword_1800F8228;
  v42 = dword_1800F8158;
  v44 = dword_1800F811C;
  v45 = dword_1800F8138;
  v47 = dword_1800F813C;
  v46 = dword_1800F8184;
  v43 = dword_1800F8170;
  v49 = dword_1800F81C4;
  v50 = dword_1800F82A0;
  v48 = dword_1800F81C8;
  v41 = dword_1800F824C;
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
  if ( (unsigned int)_o__wcsicmp(v53, Src) )
    goto LABEL_7;
LABEL_9:
  v6 = v54;
  if ( !v54 )
  {
    if ( !qword_1800F81E8 )
      goto LABEL_15;
    goto LABEL_14;
  }
  if ( !qword_1800F81E8 || (unsigned int)_o__wcsicmp(v54, qword_1800F81E8) )
  {
LABEL_14:
    NlPrintRoutine(1u, L"   Scripts = %ws\n", v6);
    v5 = 1;
    v54 = qword_1800F81E8;
    qword_1800F81E8 = v6;
    v40 = 1;
  }
LABEL_15:
  v7 = v52;
  if ( v52 || qword_1800F81D0 )
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
    v52 = qword_1800F81D0;
    qword_1800F81D0 = v7;
    RtlReleaseResource(&NlGlobalNtlmAllowedServersLock);
  }
  if ( v63 )
  {
    if ( dword_1800F8270 )
      goto LABEL_31;
    v5 = 1;
  }
  else if ( dword_1800F8270 )
  {
    v5 = 1;
  }
  v40 = v5;
LABEL_31:
  if ( v64 )
  {
    if ( dword_1800F8274 )
      goto LABEL_37;
    v5 = 1;
  }
  else if ( dword_1800F8274 )
  {
    v5 = 1;
  }
  v40 = v5;
LABEL_37:
  v10 = v68;
  if ( !v68 )
  {
    if ( !qword_1800F82B8 )
      goto LABEL_43;
LABEL_42:
    NlPrintRoutine(1u, L"   RpcDacl = %ws\n", v10);
    v68 = qword_1800F82B8;
    qword_1800F82B8 = v10;
    NlUpdateRpcSecurityDescriptor();
    goto LABEL_43;
  }
  if ( !qword_1800F82B8 || (unsigned int)_o__wcsicmp(v68, qword_1800F82B8) )
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
  if ( !StringSecurityDescriptor || (unsigned int)_o__wcsicmp(v69, StringSecurityDescriptor) )
    goto LABEL_48;
LABEL_49:
  v12 = v62;
  if ( v62 )
  {
    if ( qword_1800F8230 && !(unsigned int)_o__wcsicmp(v62, qword_1800F8230) )
      goto LABEL_55;
  }
  else if ( !qword_1800F8230 )
  {
    goto LABEL_55;
  }
  NlPrintRoutine(1u, L"   VulnerableChannelAllowList = %ws\n", v12);
  v62 = qword_1800F8230;
  qword_1800F8230 = v12;
  NlUpdateVulnerableChannelAllowList();
LABEL_55:
  v13 = v56;
  v14 = v55;
  if ( v56 != dword_1800F81F8 )
    goto LABEL_61;
  if ( !v55 )
  {
    if ( !qword_1800F81F0 )
      goto LABEL_62;
    goto LABEL_61;
  }
  if ( !qword_1800F81F0 || (v39 = 0, (unsigned int)_o__wcsicmp(v55, qword_1800F81F0)) )
  {
LABEL_61:
    v2 = 1;
    NlPrintRoutine(1u, L"   SiteName (%ld) = %ws\n", v13, v14);
    v55 = qword_1800F81F0;
    qword_1800F81F0 = v14;
    dword_1800F81F8 = v13;
LABEL_62:
    v39 = v2;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
  v16 = v57;
  v17 = 0;
  if ( IsEnabled )
  {
    if ( !NlSitesSetSiteCoverageParam(0x2000, v57) )
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
    if ( !NlSitesSetSiteCoverageParam_Old(0x2000, v57) )
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
  v19 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
  v20 = v58;
  if ( v19 )
  {
    if ( !NlSitesSetSiteCoverageParam(0x8000, v58) )
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
    if ( !NlSitesSetSiteCoverageParam_Old(0x8000, v58) )
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
  v23 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
  v24 = v59;
  if ( v23 )
  {
    if ( NlSitesSetSiteCoverageParam(0x4000, v59) )
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
  else if ( NlSitesSetSiteCoverageParam_Old(0x4000, v59) )
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
  if ( v66 != dword_1800F829C && !v66 && (Microsoft_Windows_Security_NetlogonEnableBits & 8) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(1, (__int64)MailslotDiscoveryEnabled, v28, 1, (__int64)v70);
  if ( !NlGlobalMemberWorkstation
    && v65 != dword_1800F828C
    && !v65
    && (Microsoft_Windows_Security_NetlogonEnableBits & 8) != 0 )
  {
    McGenEventWrite_EtwEventWriteTransfer(1, (__int64)DCListeningOnMailslots, v28, 1, (__int64)v70);
  }
  v29 = 0;
  do
  {
    if ( *(_DWORD *)((char *)v51 + HIDWORD(qword_1800F5AF8[v29 + 1])) != *(_DWORD *)((char *)&NlGlobalParameters
                                                                                   + HIDWORD(qword_1800F5AF8[v29 + 1])) )
    {
      NlPrintRoutine(
        1u,
        L"   %ws = %lu (0x%lx)\n",
        *(struct _unnamed_type_ParseTable_ near **)((char *)&ParseTable + v29 * 8));
      if ( LOBYTE(qword_1800F5AF8[v29 + 2]) )
        v3 = 1;
      *(_DWORD *)((char *)&NlGlobalParameters + HIDWORD(qword_1800F5AF8[v29 + 1])) = *(_DWORD *)((char *)v51
                                                                                               + HIDWORD(qword_1800F5AF8[v29 + 1]));
    }
    ++v17;
    v29 += 4;
  }
  while ( v17 != 55 );
  v30 = 0;
  v31 = 0;
  do
  {
    v32 = *(_DWORD *)((char *)v51 + (unsigned int)dword_1800F57DC[v31 / 4]);
    if ( v32 != *(_DWORD *)((char *)&NlGlobalParameters + (unsigned int)dword_1800F57DC[v31 / 4]) )
    {
      v33 = "TRUE";
      if ( !v32 )
        v33 = "FALSE";
      NlPrintRoutine(
        1u,
        L"   %ws = %hs\n",
        *(struct _unnamed_type_BoolParseTable_ near **)((char *)&BoolParseTable + v31),
        v33);
      if ( LOBYTE(qword_1800F57E0[v31 / 8]) )
        v3 = 1;
      *(_DWORD *)((char *)&NlGlobalParameters + (unsigned int)dword_1800F57DC[v31 / 4]) = *(_DWORD *)((char *)v51 + (unsigned int)dword_1800F57DC[v31 / 4]);
    }
    ++v30;
    v31 += 24LL;
  }
  while ( v30 != 33 );
  dword_1800F82A0 = v67;
  NlParseRecompute((struct _NETLOGON_PARAMETERS *)&NlGlobalParameters);
  v34 = NlGlobalMemberWorkstation == 0;
  LODWORD(NlGlobalEventlogHandle[1].OwningThread) = 1000 * dword_1800F8178;
  if ( v34 )
  {
    if ( v3 )
      NlDnsForceScavenge(1, dword_1800F8158 != v42);
    if ( v40 || v41 != dword_1800F824C )
      NlCreateSysvolShares();
    if ( v43 != dword_1800F8170 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
        NlRequestUpdateNextClosestSites();
      else
        NlSitesUpdateNextClosestSites_Old();
    }
  }
  else if ( v39 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
      NlSetSiteName(qword_1800F81F0, 0);
    else
      NlSetSiteName_Old(qword_1800F81F0, 0);
  }
  if ( v44 != dword_1800F811C || v45 != dword_1800F8138 || v46 != dword_1800F8184 )
  {
    RtlEnterCriticalSection(&NlGlobalScavengerCritSect);
    dword_1800F8BA8 = 0;
    RtlLeaveCriticalSection(&NlGlobalScavengerCritSect);
  }
  if ( v47 != dword_1800F813C )
  {
    RtlEnterCriticalSection(&NlGlobalEventLoggerCritSect);
    dword_1800F8BC0 = 1000 * dword_1800F813C;
    RtlLeaveCriticalSection(&NlGlobalEventLoggerCritSect);
    if ( !SetEvent(NlGlobalTimerEvent) )
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"NlReparse: SetEvent failed %ld\n", LastError);
    }
  }
  if ( v48 != dword_1800F81C8 || v49 != dword_1800F81C4 || v50 != dword_1800F82A0 )
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
0x18005179c  push    rbp
0x18005179e  push    rbx
0x18005179f  push    rsi
0x1800517a0  push    rdi
0x1800517a1  push    r12
0x1800517a3  push    r13
0x1800517a5  push    r14
0x1800517a7  push    r15
0x1800517a9  lea     rbp, [rsp-1A8h]
0x1800517b1  sub     rsp, 2A8h
0x1800517b8  mov     rax, cs:__security_cookie
0x1800517bf  xor     rax, rsp
0x1800517c2  mov     [rbp+1E0h+var_50], rax
0x1800517c9  xor     edx, edx; Val
0x1800517cb  lea     rcx, [rsp+2E0h+var_280]; void *
0x1800517d0  mov     r8d, 220h; Size
0x1800517d6  call    memset_0
0x1800517db  mov     eax, cs:dword_1800F8158
0x1800517e1  lea     rcx, [rsp+2E0h+var_280]; struct _NETLOGON_PARAMETERS *
0x1800517e6  mov     r13d, cs:dword_1800F824C
0x1800517ed  mov     edi, 1
0x1800517f2  mov     r12d, cs:dword_1800F8228
0x1800517f9  mov     dl, dil; unsigned __int8
0x1800517fc  mov     [rsp+2E0h+var_2A4], eax
0x180051800  mov     eax, cs:dword_1800F811C
0x180051806  mov     [rsp+2E0h+var_29C], eax
0x18005180a  mov     eax, cs:dword_1800F8138
0x180051810  mov     [rsp+2E0h+var_298], eax
0x180051814  mov     eax, cs:dword_1800F813C
0x18005181a  mov     [rsp+2E0h+var_290], eax
0x18005181e  mov     eax, cs:dword_1800F8184
0x180051824  mov     [rsp+2E0h+var_294], eax
0x180051828  mov     eax, cs:dword_1800F8170
0x18005182e  mov     [rsp+2E0h+var_2A0], eax
0x180051832  mov     eax, cs:dword_1800F81C4
0x180051838  mov     [rsp+2E0h+var_288], eax
0x18005183c  mov     eax, cs:dword_1800F82A0
0x180051842  mov     [rsp+2E0h+var_284], eax
0x180051846  mov     eax, cs:dword_1800F81C8
0x18005184c  mov     [rsp+2E0h+var_28C], eax
0x180051850  mov     [rsp+2E0h+var_2A8], r13d
0x180051855  call    ?NlparseAllSections@@YAHPEAU_NETLOGON_PARAMETERS@@E@Z; NlparseAllSections(_NETLOGON_PARAMETERS *,uchar)
0x18005185a  xor     r15d, r15d
0x18005185d  test    eax, eax
0x18005185f  jz      loc_1800522C7
0x180051865  lea     rdx, aFollowingAreTh; "Following are the effective values afte"...
0x18005186c  mov     ecx, edi; unsigned int
0x18005186e  mov     sil, r15b
0x180051871  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051876  mov     rbx, [rbp+1E0h+var_1A0]
0x18005187a  test    rbx, rbx
0x18005187d  jnz     short loc_18005188D
0x18005187f  cmp     cs:Src, r15
0x180051886  jnz     short loc_1800518BE
0x180051888  mov     r14b, r15b
0x18005188b  jmp     short loc_1800518E4
0x18005188d  mov     rdx, cs:Src
0x180051894  test    rdx, rdx
0x180051897  jz      short loc_1800518BE
0x180051899  mov     r14b, r15b
0x18005189c  mov     [rsp+2E0h+var_2AC], r14d
0x1800518a1  test    rbx, rbx
0x1800518a4  jz      short loc_1800518E9
0x1800518a6  test    rdx, rdx
0x1800518a9  jz      short loc_1800518E9
0x1800518ab  mov     rcx, rbx
0x1800518ae  call    cs:__imp__o__wcsicmp
0x1800518b5  nop     dword ptr [rax+rax+00h]
0x1800518ba  test    eax, eax
0x1800518bc  jz      short loc_1800518E9
0x1800518be  mov     r8, rbx
0x1800518c1  lea     rdx, aSysvolWs; "   Sysvol = %ws\n"
0x1800518c8  mov     ecx, edi; unsigned int
0x1800518ca  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800518cf  mov     rax, cs:Src
0x1800518d6  mov     r14b, dil
0x1800518d9  mov     [rbp+1E0h+var_1A0], rax
0x1800518dd  mov     cs:Src, rbx
0x1800518e4  mov     [rsp+2E0h+var_2AC], r14d
0x1800518e9  mov     rbx, [rbp+1E0h+var_198]
0x1800518ed  test    rbx, rbx
0x1800518f0  jnz     short loc_1800518FD
0x1800518f2  cmp     cs:qword_1800F81E8, r15
0x1800518f9  jnz     short loc_180051921
0x1800518fb  jmp     short loc_18005194C
0x1800518fd  mov     rdx, cs:qword_1800F81E8
0x180051904  test    rdx, rdx
0x180051907  jz      short loc_180051921
0x180051909  test    rbx, rbx
0x18005190c  jz      short loc_18005194C
0x18005190e  mov     rcx, rbx
0x180051911  call    cs:__imp__o__wcsicmp
0x180051918  nop     dword ptr [rax+rax+00h]
0x18005191d  test    eax, eax
0x18005191f  jz      short loc_18005194C
0x180051921  mov     r8, rbx
0x180051924  lea     rdx, aScriptsWs; "   Scripts = %ws\n"
0x18005192b  mov     ecx, edi; unsigned int
0x18005192d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051932  mov     rax, cs:qword_1800F81E8
0x180051939  mov     r14b, dil
0x18005193c  mov     [rbp+1E0h+var_198], rax
0x180051940  mov     cs:qword_1800F81E8, rbx
0x180051947  mov     [rsp+2E0h+var_2AC], r14d
0x18005194c  mov     rdi, [rbp+1E0h+var_1B0]
0x180051950  test    rdi, rdi
0x180051953  jnz     short loc_180051963
0x180051955  cmp     cs:qword_1800F81D0, r15
0x18005195c  jnz     short loc_180051975
0x18005195e  jmp     loc_180051A00
0x180051963  cmp     cs:qword_1800F81D0, r15
0x18005196a  jz      short loc_180051975
0x18005196c  test    rdi, rdi
0x18005196f  jz      loc_180051A00
0x180051975  mov     rbx, rdi
0x180051978  test    rdi, rdi
0x18005197b  jz      short loc_1800519B5
0x18005197d  cmp     [rdi], r15w
0x180051981  jz      short loc_1800519C6
0x180051983  mov     r8, rbx
0x180051986  lea     rdx, aNtlmExceptions; "   NTLM Exceptions = %ws\n"
0x18005198d  mov     ecx, 1; unsigned int
0x180051992  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051997  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005199b  inc     rax
0x18005199e  cmp     [rbx+rax*2], r15w
0x1800519a3  jnz     short loc_18005199B
0x1800519a5  lea     rbx, [rbx+rax*2]
0x1800519a9  add     rbx, 2
0x1800519ad  cmp     [rbx], r15w
0x1800519b1  jnz     short loc_180051983
0x1800519b3  jmp     short loc_1800519C6
0x1800519b5  lea     rdx, aNtlmExceptions_0; "   NTLM Exceptions = NULL\n"
0x1800519bc  mov     ecx, 1; unsigned int
0x1800519c1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800519c6  mov     dl, 1; Wait
0x1800519c8  lea     rcx, ?NlGlobalNtlmAllowedServersLock@@3U_RTL_RESOURCE@@A; Resource
0x1800519cf  call    cs:__imp_RtlAcquireResourceExclusive
0x1800519d6  nop     dword ptr [rax+rax+00h]
0x1800519db  mov     rax, cs:qword_1800F81D0
0x1800519e2  lea     rcx, ?NlGlobalNtlmAllowedServersLock@@3U_RTL_RESOURCE@@A; Resource
0x1800519e9  mov     [rbp+1E0h+var_1B0], rax
0x1800519ed  mov     cs:qword_1800F81D0, rdi
0x1800519f4  call    cs:__imp_RtlReleaseResource
0x1800519fb  nop     dword ptr [rax+rax+00h]
0x180051a00  mov     edi, 1
0x180051a05  cmp     [rbp+1E0h+var_110], r15d
0x180051a0c  jz      short loc_180051A1C
0x180051a0e  cmp     cs:dword_1800F8270, r15d
0x180051a15  jnz     short loc_180051A30
0x180051a17  mov     r14b, dil
0x180051a1a  jmp     short loc_180051A2B
0x180051a1c  cmp     cs:dword_1800F8270, r15d
0x180051a23  movzx   r14d, r14b
0x180051a27  cmovnz  r14d, edi
0x180051a2b  mov     [rsp+2E0h+var_2AC], r14d
0x180051a30  cmp     [rbp+1E0h+var_10C], r15d
0x180051a37  jz      short loc_180051A47
0x180051a39  cmp     cs:dword_1800F8274, r15d
0x180051a40  jnz     short loc_180051A5B
0x180051a42  mov     r14b, dil
0x180051a45  jmp     short loc_180051A56
0x180051a47  cmp     cs:dword_1800F8274, r15d
0x180051a4e  movzx   r14d, r14b
0x180051a52  cmovnz  r14d, edi
0x180051a56  mov     [rsp+2E0h+var_2AC], r14d
0x180051a5b  mov     rbx, [rbp+1E0h+var_C8]
0x180051a62  test    rbx, rbx
0x180051a65  jnz     short loc_180051A72
0x180051a67  cmp     cs:qword_1800F82B8, r15
0x180051a6e  jnz     short loc_180051A96
0x180051a70  jmp     short loc_180051AC1
0x180051a72  mov     rdx, cs:qword_1800F82B8
0x180051a79  test    rdx, rdx
0x180051a7c  jz      short loc_180051A96
0x180051a7e  test    rbx, rbx
0x180051a81  jz      short loc_180051AC1
0x180051a83  mov     rcx, rbx
0x180051a86  call    cs:__imp__o__wcsicmp
0x180051a8d  nop     dword ptr [rax+rax+00h]
0x180051a92  test    eax, eax
0x180051a94  jz      short loc_180051AC1
0x180051a96  mov     r8, rbx
0x180051a99  lea     rdx, aRpcdaclWs; "   RpcDacl = %ws\n"
0x180051aa0  mov     ecx, edi; unsigned int
0x180051aa2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051aa7  mov     rax, cs:qword_1800F82B8
0x180051aae  mov     [rbp+1E0h+var_C8], rax
0x180051ab5  mov     cs:qword_1800F82B8, rbx
0x180051abc  call    ?NlUpdateRpcSecurityDescriptor@@YAXXZ; NlUpdateRpcSecurityDescriptor(void)
0x180051ac1  mov     rbx, [rbp+1E0h+var_C0]
0x180051ac8  test    rbx, rbx
0x180051acb  jnz     short loc_180051AD8
0x180051acd  cmp     cs:StringSecurityDescriptor, r15
0x180051ad4  jnz     short loc_180051AFC
0x180051ad6  jmp     short loc_180051B27
0x180051ad8  mov     rdx, cs:StringSecurityDescriptor
0x180051adf  test    rdx, rdx
0x180051ae2  jz      short loc_180051AFC
0x180051ae4  test    rbx, rbx
0x180051ae7  jz      short loc_180051B27
0x180051ae9  mov     rcx, rbx
0x180051aec  call    cs:__imp__o__wcsicmp
0x180051af3  nop     dword ptr [rax+rax+00h]
0x180051af8  test    eax, eax
0x180051afa  jz      short loc_180051B27
0x180051afc  mov     r8, rbx
0x180051aff  lea     rdx, aRemoteaccessch; "   RemoteAccessCheckDacl = %ws\n"
0x180051b06  mov     ecx, edi; unsigned int
0x180051b08  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051b0d  mov     rax, cs:StringSecurityDescriptor
0x180051b14  mov     [rbp+1E0h+var_C0], rax
0x180051b1b  mov     cs:StringSecurityDescriptor, rbx
0x180051b22  call    ?NlUpdateRemoteAccessCheckSecurityDescriptor@@YAXXZ; NlUpdateRemoteAccessCheckSecurityDescriptor(void)
0x180051b27  mov     rbx, [rbp+1E0h+var_150]
0x180051b2e  test    rbx, rbx
0x180051b31  jnz     short loc_180051B3E
0x180051b33  cmp     cs:qword_1800F8230, r15
0x180051b3a  jnz     short loc_180051B62
0x180051b3c  jmp     short loc_180051B8D
0x180051b3e  mov     rdx, cs:qword_1800F8230
0x180051b45  test    rdx, rdx
0x180051b48  jz      short loc_180051B62
0x180051b4a  test    rbx, rbx
0x180051b4d  jz      short loc_180051B8D
0x180051b4f  mov     rcx, rbx
0x180051b52  call    cs:__imp__o__wcsicmp
0x180051b59  nop     dword ptr [rax+rax+00h]
0x180051b5e  test    eax, eax
0x180051b60  jz      short loc_180051B8D
0x180051b62  mov     r8, rbx
0x180051b65  lea     rdx, aVulnerablechan_0; "   VulnerableChannelAllowList = %ws\n"
0x180051b6c  mov     ecx, edi; unsigned int
0x180051b6e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051b73  mov     rax, cs:qword_1800F8230
0x180051b7a  mov     [rbp+1E0h+var_150], rax
0x180051b81  mov     cs:qword_1800F8230, rbx
0x180051b88  call    ?NlUpdateVulnerableChannelAllowList@@YAXXZ; NlUpdateVulnerableChannelAllowList(void)
0x180051b8d  mov     edi, [rbp+1E0h+var_188]
0x180051b90  cmp     edi, cs:dword_1800F81F8
0x180051b96  mov     rbx, [rbp+1E0h+var_190]
0x180051b9a  jnz     short loc_180051BDA
0x180051b9c  test    rbx, rbx
0x180051b9f  jnz     short loc_180051BAC
0x180051ba1  cmp     cs:qword_1800F81F0, r15
0x180051ba8  jnz     short loc_180051BDA
0x180051baa  jmp     short loc_180051C0D
0x180051bac  mov     rdx, cs:qword_1800F81F0
0x180051bb3  test    rdx, rdx
0x180051bb6  jz      short loc_180051BDA
0x180051bb8  mov     [rsp+2E0h+var_2B0], r15b
0x180051bbd  test    rbx, rbx
0x180051bc0  jz      short loc_180051C12
0x180051bc2  test    rdx, rdx
0x180051bc5  jz      short loc_180051C12
0x180051bc7  mov     rcx, rbx
0x180051bca  call    cs:__imp__o__wcsicmp
0x180051bd1  nop     dword ptr [rax+rax+00h]
0x180051bd6  test    eax, eax
0x180051bd8  jz      short loc_180051C12
0x180051bda  mov     r15d, 1
0x180051be0  lea     rdx, aSitenameLdWs; "   SiteName (%ld) = %ws\n"
0x180051be7  mov     ecx, r15d; unsigned int
0x180051bea  mov     r9, rbx
0x180051bed  mov     r8d, edi
0x180051bf0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051bf5  mov     rax, cs:qword_1800F81F0
0x180051bfc  mov     [rbp+1E0h+var_190], rax
0x180051c00  mov     cs:qword_1800F81F0, rbx
0x180051c07  mov     cs:dword_1800F81F8, edi
0x180051c0d  mov     [rsp+2E0h+var_2B0], r15b
0x180051c12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x180051c19  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x180051c1e  mov     rbx, [rbp+1E0h+var_180]
0x180051c22  xor     edi, edi
0x180051c24  mov     ecx, 2000h; int
0x180051c29  mov     rdx, rbx; unsigned __int16 *
0x180051c2c  test    al, al
0x180051c2e  jz      short loc_180051C7E
0x180051c30  call    ?NlSitesSetSiteCoverageParam@@YAHHPEAG@Z; NlSitesSetSiteCoverageParam(int,ushort *)
0x180051c35  test    eax, eax
0x180051c37  jz      loc_180051CC3
0x180051c3d  lea     esi, [rdi+1]
0x180051c40  mov     ecx, esi; unsigned int
0x180051c42  lea     rdx, aSitecoverage_0; "   SiteCoverage = "
0x180051c49  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051c4e  test    rbx, rbx
0x180051c51  jz      short loc_180051CA3
0x180051c53  cmp     [rbx], di
0x180051c56  jz      short loc_180051CB1
0x180051c58  mov     r8, rbx
0x180051c5b  lea     rdx, aWs; " '%ws'"
0x180051c62  mov     ecx, esi; unsigned int
0x180051c64  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051c69  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051c6d  inc     rax
0x180051c70  cmp     [rbx+rax*2], di
0x180051c74  jnz     short loc_180051C6D
0x180051c76  inc     eax
0x180051c78  lea     rbx, [rbx+rax*2]
  ... truncated ...
```
