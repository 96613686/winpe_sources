# NetrLogonControl2Ex

- ea: `0x18005fa30`
- end: `0x180060660`
- name: `NetrLogonControl2Ex`
- size: `3120`
- prototype: `__int64 __fastcall(int, int, int, int, union _NETLOGON_CONTROL_QUERY_INFORMATION *)`
- caller_count: `2`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005f9b0`
- `0x18005fa20`

## callees

- `0x180003250`
- `0x180003890`
- `0x1800055d4`
- `0x180007518`
- `0x180007e90`
- `0x18000c440`
- `0x18000ca88`
- `0x18000dd00`
- `0x18000e0e0`
- `0x180021524`
- `0x1800267ec`
- `0x1800271d4`
- `0x1800283ec`
- `0x180035924`
- `0x18003a51c`
- `0x18003bb30`
- `0x180040aa8`
- `0x180040f18`
- `0x18005b9cc`
- `0x18005dfe0`
- `0x18005fa30`
- `0x180068c10`
- `0x180069a30`
- `0x180069f50`
- `0x18006c2e8`
- `0x18006cbc4`
- `0x18006d2b0`
- `0x18006e444`
- `0x180089328`
- `0x18008a5c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800605f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006060e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180060622`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800605f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006060e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180060622`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005fedc`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005fedc`
- `LSASRV!LsaIIsContainerized` at `0x18005fbe6`
- `LSASRV!LsaIIsContainerized` at `0x18005fbe6`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005fc3b`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005fd3d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005fe57`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ff01`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060103`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005fc3b`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005fd3d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005fe57`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ff01`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060103`
- `ntdll!RtlEqualDomainName` at `0x18006031e`
- `ntdll!RtlEqualDomainName` at `0x18006031e`
- `ntdll!RtlLeaveCriticalSection` at `0x180060246`
- `ntdll!RtlLeaveCriticalSection` at `0x180060449`
- `ntdll!RtlLeaveCriticalSection` at `0x180060246`
- `ntdll!RtlLeaveCriticalSection` at `0x180060449`
- `ntdll!RtlEnterCriticalSection` at `0x180060205`
- `ntdll!RtlEnterCriticalSection` at `0x18006042a`
- `ntdll!RtlEnterCriticalSection` at `0x180060205`
- `ntdll!RtlEnterCriticalSection` at `0x18006042a`
- `ntdll!RtlInitUnicodeString` at `0x18006030a`
- `ntdll!RtlInitUnicodeString` at `0x18006030a`
- `netutils!NetApiBufferFree` at `0x1800605c3`
- `netutils!NetApiBufferFree` at `0x1800605d8`
- `netutils!NetApiBufferFree` at `0x1800605c3`
- `netutils!NetApiBufferFree` at `0x1800605d8`

## string_xrefs

- `0x18005faf0`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005fe2c`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005feb0`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x1800600c8`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005ffe6`: `NetrLogonControl2: Can't become writer of client session.\n`
- `0x18005fbf6`: `NetrLogonControl called with NETLOGON_CONTROL_CHANGE_PASSWORD when running inside a container.\n`

## pseudocode

```c
__int64 __fastcall NetrLogonControl2Ex(
        unsigned __int16 *a1,
        unsigned int a2,
        int a3,
        PCWSTR *a4,
        union _NETLOGON_CONTROL_QUERY_INFORMATION *a5)
{
  unsigned __int16 *v6; // r14
  struct _CLIENT_SESSION *v10; // rdi
  struct _DOMAIN_INFO *DomainByServerName; // rsi
  __int64 v12; // r8
  char *v13; // r9
  unsigned int v14; // ebx
  unsigned int v15; // eax
  DWORD v16; // edx
  NTSTATUS inited; // ebx
  NTSTATUS v18; // ecx
  struct _CLIENT_SESSION *v19; // rax
  char *v20; // r9
  int v21; // ebx
  PCWSTR v22; // r8
  NTSTATUS v23; // eax
  NTSTATUS v24; // r14d
  int v25; // eax
  char *v26; // r9
  char *v27; // r9
  wchar_t *v28; // r14
  unsigned int v29; // eax
  __int64 v30; // r8
  char *v31; // r9
  unsigned int v32; // eax
  NTSTATUS v33; // ecx
  char *v34; // r9
  struct _CLIENT_SESSION *NamedClientSession; // rax
  size_t v36; // rcx
  _DWORD *v37; // rax
  HLOCAL *i; // rax
  int v39; // r13d
  int v40; // r13d
  int v41; // r13d
  struct _CLIENT_SESSION *v42; // rax
  void *v43; // rcx
  __int64 v44; // r15
  unsigned int v45; // r15d
  unsigned int v46; // r15d
  NTSTATUS v47; // ebx
  char v48; // cl
  struct _CLIENT_SESSION *v49; // rax
  char *v50; // rbx
  int v52[2]; // [rsp+20h] [rbp-81h]
  int v53[2]; // [rsp+20h] [rbp-81h]
  __int64 v54; // [rsp+50h] [rbp-51h]
  unsigned __int16 *Block; // [rsp+58h] [rbp-49h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-41h] BYREF
  int v57; // [rsp+70h] [rbp-31h] BYREF
  unsigned int v58; // [rsp+74h] [rbp-2Dh] BYREF
  unsigned int v59; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int16 *v60; // [rsp+80h] [rbp-21h] BYREF
  PCWSTR SourceString; // [rsp+88h] [rbp-19h] BYREF
  LPVOID Buffer; // [rsp+90h] [rbp-11h] BYREF
  struct _NL_DC_CACHE_ENTRY *v63; // [rsp+98h] [rbp-9h] BYREF
  struct _UNICODE_STRING DomainName1; // [rsp+A0h] [rbp-1h] BYREF
  int v65; // [rsp+120h] [rbp+7Fh]

  Block = 0;
  v6 = 0;
  v60 = 0;
  v54 = 0;
  *(_QWORD *)a5 = 0;
  Buffer = 0;
  DestinationString = 0;
  v10 = 0;
  SourceString = 0;
  v57 = 0;
  v58 = 0;
  v63 = 0;
  v59 = 0;
  DomainByServerName = NlFindDomainByServerName(a1);
  if ( !DomainByServerName )
  {
    v14 = 1210;
    goto LABEL_190;
  }
  if ( a3 != 1 && a3 != 2 && (unsigned int)(a3 - 3) >= 2 )
  {
    v14 = 124;
    goto LABEL_190;
  }
  if ( (a2 == 5 || a2 == 6 || a2 == 8 || a2 == 9 || a2 == 10 || a2 == 65534) && !a4 )
  {
    NlAssertFailed("InputData != NULL", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx", 0x15E7u, v13);
    v14 = 87;
    goto LABEL_190;
  }
  if ( a2 >= 0xFFFC )
    goto LABEL_24;
  if ( a2 > 7 )
  {
    if ( a2 == 8 || a2 == 9 || a2 == 10 || a2 == 11 )
      goto LABEL_24;
    v15 = a2 - 12;
    if ( a2 == 12 )
      goto LABEL_32;
  }
  else
  {
    switch ( a2 )
    {
      case 7u:
      case 1u:
        goto LABEL_32;
      case 2u:
        goto LABEL_24;
      case 3u:
        goto LABEL_24;
      case 4u:
        goto LABEL_24;
    }
    v15 = a2 - 5;
    if ( a2 == 5 )
      goto LABEL_24;
  }
  if ( v15 != 1 )
  {
LABEL_24:
    v16 = 4;
    goto LABEL_25;
  }
LABEL_32:
  v16 = 8;
LABEL_25:
  if ( NetpAccessCheck2(NlGlobalNetlogonSecurityDescriptor, v16, v12, 1) )
  {
    v14 = 5;
    goto LABEL_190;
  }
  v65 = 1;
  if ( a2 > 0xA )
  {
    if ( a2 == 11 )
    {
      NlPrintRoutine(0x4000u, L"NETLOGON_CONTROL_FORCE_DNS_REG function received.\n");
      if ( NlGlobalMemberWorkstation )
        goto LABEL_43;
      NlDnsForceScavenge(1, 1);
      goto LABEL_132;
    }
    if ( a2 == 12 )
    {
      if ( NlGlobalMemberWorkstation )
        goto LABEL_43;
      if ( a3 == 1 )
      {
        v65 = 1;
        RtlEnterCriticalSection(&NlGlobalDnsCritSect);
        for ( i = (HLOCAL *)NlGlobalDnsList; i != &NlGlobalDnsList; i = (HLOCAL *)*i )
        {
          if ( *((_DWORD *)i + 60) != 4 && *((_DWORD *)i + 61) )
          {
            v65 = 0;
            break;
          }
        }
        RtlLeaveCriticalSection(&NlGlobalDnsCritSect);
        goto LABEL_118;
      }
    }
    else
    {
      if ( a2 != 13 )
      {
        if ( a2 == 65533 )
        {
          NlOpenDebugFile(1);
          NlPrintRoutine(2u, L"TRUNCATE_LOG function received.\n");
        }
        else
        {
          if ( a2 != 65534 )
            goto LABEL_43;
          NlGlobalParameters = *(_DWORD *)a4;
          NlPrintRoutine(2u, L"DbFlag is set to %lx\n");
        }
        goto LABEL_132;
      }
      if ( a3 == 1 )
      {
        v25 = NetIGetEncTypes(&v59);
        if ( v25 >= 0 )
        {
LABEL_118:
          v36 = 8;
          goto LABEL_119;
        }
        goto LABEL_64;
      }
    }
    goto LABEL_105;
  }
  if ( a2 == 10 )
  {
    NlPrintDomRoutine(0x200u, DomainByServerName, L"NETLOGON_CONTROL_TC_VERIFY function received.\n");
    if ( !*a4 )
      NlAssertFailed(
        "InputData->TrustedDomainName != NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
        0x170Cu,
        v34);
    if ( !*a4 )
    {
      NlPrintDomRoutine(
        0x100u,
        DomainByServerName,
        L"NetrLogonControl called with NETLOGON_CONTROL_TC_VERIFY and specified NULL trusted domain name. \n");
      goto LABEL_46;
    }
    if ( a3 == 2 )
    {
      inited = RtlInitUnicodeStringEx(&DestinationString, *a4);
      if ( inited >= 0 )
      {
        NamedClientSession = NlFindNamedClientSession(DomainByServerName, &DestinationString, 0x11u, 0);
        v10 = NamedClientSession;
        if ( NamedClientSession )
        {
          v33 = NlVerifyTrust(NamedClientSession, a5);
          goto LABEL_98;
        }
        goto LABEL_51;
      }
LABEL_48:
      NlPrintRoutine(
        0x100u,
        L"NetrLogonControl2Ex: RtlInitUnicdeStringEx on InputData->TrustedDomainName failed: 0x%08x\n",
        (unsigned int)inited);
      v18 = inited;
LABEL_49:
      v14 = NetpNtStatusToApiStatus(v18);
      goto LABEL_190;
    }
LABEL_105:
    v14 = 124;
    goto LABEL_190;
  }
  if ( a2 == 1 )
  {
    NlPrintDomRoutine(2u, DomainByServerName, L"QUERY function received.\n");
    goto LABEL_132;
  }
  if ( a2 != 5 )
  {
    if ( a2 != 6 )
    {
      if ( a2 == 7 )
      {
        NlPrintRoutine(0x200u, L"NETLOGON_CONTROL_TRANSPORT_NOTIFY function received.\n");
        NlFlushCacheOnPnp();
        goto LABEL_132;
      }
      if ( a2 != 8 )
      {
        if ( a2 != 9 )
        {
LABEL_43:
          v14 = 50;
          goto LABEL_190;
        }
        NlPrintDomRoutine(0x200u, DomainByServerName, L"NETLOGON_CONTROL_CHANGE_PASSWORD function received.\n");
        if ( (unsigned __int8)LsaIIsContainerized() )
        {
          NlPrintDomRoutine(
            0x100u,
            DomainByServerName,
            L"NetrLogonControl called with NETLOGON_CONTROL_CHANGE_PASSWORD when running inside a container.\n");
          goto LABEL_43;
        }
        if ( !*a4 )
        {
          NlPrintDomRoutine(
            0x100u,
            DomainByServerName,
            L"NetrLogonControl called with NETLOGON_CONTROL_CHANGE_PASSWORD and specified NULL trusted domain name. \n");
LABEL_46:
          v14 = 87;
          goto LABEL_190;
        }
        inited = RtlInitUnicodeStringEx(&DestinationString, *a4);
        if ( inited < 0 )
          goto LABEL_48;
        v19 = NlFindNamedClientSession(DomainByServerName, &DestinationString, 0x15u, 0);
        v10 = v19;
        if ( !v19 )
          goto LABEL_51;
        if ( *((_DWORD *)DomainByServerName + 147) == 2 && (unsigned int)(*((_DWORD *)v19 + 70) - 3) <= 1 )
        {
          NlPrintDomRoutine(
            0x100u,
            DomainByServerName,
            L"NetrLogonControl called with NETLOGON_CONTROL_CHANGE_PASSWORD for an interdomain trust account on a BDC. \n");
          v14 = 1354;
LABEL_188:
          NlUnrefClientSession((char *)v10);
          goto LABEL_189;
        }
        v21 = NlChangePassword(v19, 1u, 0, v20);
        if ( v21 < 0 )
        {
          NlPrintCsRoutine(0x100u, v10, L"NetrLogonControl: Password Change failed %lx\n", (unsigned int)v21);
LABEL_97:
          v33 = v21;
LABEL_98:
          v14 = NetpNtStatusToApiStatus(v33);
          goto LABEL_188;
        }
        goto LABEL_132;
      }
      v22 = *a4;
      DomainName1 = 0;
      NlPrintRoutine(2u, L"NETLOGON_CONTROL_FIND_USER function received for %ws.\n", v22);
      if ( a3 != 4 )
        goto LABEL_46;
      if ( NlGlobalMemberWorkstation )
        goto LABEL_43;
      v23 = RtlInitUnicodeStringEx(&DomainName1, *a4);
      v24 = v23;
      if ( v23 < 0 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetrLogonControl2Ex: RtlInitUnicdeStringEx on InputData->UserName failed: 0x%08x\n",
          (unsigned int)v23);
        v18 = v24;
        goto LABEL_49;
      }
      LODWORD(v6) = 0;
      v25 = NlPickDomainWithAccount(DomainByServerName, &DomainName1, 0, 464, 0, 0, 0, &Buffer, &SourceString, &v57);
      if ( v25 >= 0 )
      {
        if ( (v57 & 3) == 0 )
        {
LABEL_136:
          v36 = 16;
          goto LABEL_119;
        }
        v52[0] = v57;
        NlPrintDomRoutine(
          0x100u,
          DomainByServerName,
          L"NetrLogonControl: User %ws is in a trusted forest (%lx).\n",
          *a4,
          *(_QWORD *)v52);
LABEL_63:
        v14 = 2221;
        goto LABEL_190;
      }
      if ( v25 == -1073741601 )
        goto LABEL_63;
LABEL_64:
      v18 = v25;
      goto LABEL_49;
    }
    NlPrintDomRoutine(0x200u, DomainByServerName, L"NETLOGON_CONTROL_TC_QUERY function received.\n");
    if ( !*a4 )
      NlAssertFailed(
        "InputData->TrustedDomainName != NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
        0x16DFu,
        v26);
    if ( !*a4 )
    {
      NlPrintDomRoutine(
        0x100u,
        DomainByServerName,
        L"NetrLogonControl called with NETLOGON_CONTROL_TC_QUERY and specified NULL trusted domain name. \n");
      goto LABEL_46;
    }
    inited = RtlInitUnicodeStringEx(&DestinationString, *a4);
    if ( inited >= 0 )
    {
      v10 = NlFindNamedClientSession(DomainByServerName, &DestinationString, 0x11u, 0);
      if ( v10 )
        goto LABEL_132;
LABEL_51:
      NlPrintDomRoutine(
        0x100u,
        DomainByServerName,
        L"NetrLogonControl can't find the client structure of the domain %wZ specified.\n",
        &DestinationString);
      v14 = 1355;
      v10 = 0;
      goto LABEL_190;
    }
    goto LABEL_48;
  }
  NlPrintDomRoutine(0x200u, DomainByServerName, L"NETLOGON_CONTROL_REDISCOVER function received.\n");
  if ( !*a4 )
    NlAssertFailed(
      "InputData->TrustedDomainName != NULL",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
      0x163Du,
      v27);
  if ( !*a4 )
  {
    NlPrintDomRoutine(
      0x100u,
      DomainByServerName,
      L"NetrLogonControl called with function code NETLOGON_CONTROL_REDISCOVER specified NULL trusted domain name. \n");
    goto LABEL_46;
  }
  v28 = wcschr(*a4, 0x5Cu);
  if ( v28 )
    *v28++ = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, *a4);
  if ( inited < 0 )
    goto LABEL_48;
  v10 = NlFindNamedClientSession(DomainByServerName, &DestinationString, 0x11u, 0);
  if ( !v10 )
  {
    NlPrintDomRoutine(
      0x100u,
      DomainByServerName,
      L"NetrLogonControl can't find the client structure of the domain %wZ specified.\n",
      &DestinationString);
    goto LABEL_84;
  }
  if ( v28 )
  {
    v29 = NlPingDcName(v10, 0, 1, 0, 1, 0, v28, 0, &v63);
    v14 = v29;
    if ( v29 )
    {
      v53[0] = v29;
      NlPrintCsRoutine(0x200u, v10, L"NetrLogonControl: Unsuccessful response from DC %ws 0x%lx\n", v28, *(_QWORD *)v53);
      if ( v14 == 1062 )
        goto LABEL_188;
LABEL_88:
      v14 = 1311;
      goto LABEL_188;
    }
    NlPrintCsRoutine(0x200u, v10, L"NetrLogonControl: Successful response from DC %ws\n", v28);
  }
  if ( !(unsigned int)NlTimeoutSetWriterClientSession(v10, dwMilliseconds) )
  {
    NlPrintDomRoutine(0x100u, DomainByServerName, L"NetrLogonControl2: Can't become writer of client session.\n");
    goto LABEL_88;
  }
  NlSetStatusClientSession(v10, -1073741730, v30, v31);
  v6 = (unsigned __int16 *)v63;
  if ( v63 )
  {
    v32 = NlSetServerClientSession(v10, v63, 1, 0);
    v6 = 0;
    v14 = v32;
    if ( v32 )
    {
      NlPrintCsRoutine(0x100u, v10, L"NetrLogonControl: NlSetServerClientSession failed 0x%lx\n", v32);
      NlResetWriterClientSession(v10);
      goto LABEL_188;
    }
  }
  v21 = NlSessionSetupEx(v10);
  NlResetWriterClientSession(v10);
  if ( v21 < 0 )
  {
    NlPrintCsRoutine(0x100u, v10, L"NetrLogonControl: Discovery failed %lx\n", (unsigned int)v21);
    goto LABEL_97;
  }
LABEL_132:
  v36 = (size_t)v6;
  switch ( a3 )
  {
    case 1:
      goto LABEL_118;
    case 2:
      v36 = 24;
      break;
    case 3:
      v36 = 28;
      break;
    case 4:
      goto LABEL_136;
    default:
      break;
  }
LABEL_119:
  v37 = MIDL_user_allocate(v36);
  *(_QWORD *)a5 = v37;
  if ( !v37 )
  {
LABEL_120:
    v14 = 8;
    goto LABEL_187;
  }
  v39 = a3 - 1;
  if ( !v39 )
  {
LABEL_173:
    v48 = v58;
    **(_DWORD **)a5 = (_DWORD)v6;
    if ( v48 < 0 )
      **(_DWORD **)a5 |= 0x20u;
    if ( (v48 & 0x10) != 0 )
      **(_DWORD **)a5 |= 0x10u;
    if ( v65 == (_DWORD)v6 )
      **(_DWORD **)a5 |= 0x40u;
    if ( v59 )
      **(_DWORD **)a5 = v59;
    if ( *((_DWORD *)DomainByServerName + 147) == 1 )
    {
      *(_DWORD *)(*(_QWORD *)a5 + 4LL) = (_DWORD)v6;
    }
    else
    {
      v49 = NlRefDomClientSession(DomainByServerName);
      v50 = (char *)v49;
      if ( v49 )
      {
        *(_DWORD *)(*(_QWORD *)a5 + 4LL) = NetpNtStatusToApiStatus(*((_DWORD *)v49 + 72));
        NlUnrefClientSession(v50);
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)a5 + 4LL) = 50;
      }
    }
    goto LABEL_186;
  }
  v40 = v39 - 1;
  if ( !v40 )
  {
    v45 = a2 - 5;
    if ( v45 )
    {
      v46 = v45 - 1;
      if ( v46 )
      {
        if ( v46 != 4 )
          goto LABEL_144;
      }
    }
    if ( v10 )
    {
      v47 = NlCaptureServerClientSession(v10, &v60, &v58);
      *(_DWORD *)(*(_QWORD *)a5 + 16LL) = NetpNtStatusToApiStatus(v47);
      if ( v47 >= 0 )
      {
        v6 = v60;
        Block = v60;
      }
      else
      {
        v6 = (unsigned __int16 *)NetpAllocWStrFromWStr((void *)&LocaleName);
        Block = v6;
      }
      if ( !v6 )
        goto LABEL_154;
      *(_QWORD *)(*(_QWORD *)a5 + 8LL) = v6;
      LODWORD(v6) = 0;
      goto LABEL_173;
    }
LABEL_84:
    v14 = 1355;
    goto LABEL_189;
  }
  v41 = v40 - 1;
  if ( v41 )
  {
    if ( v41 == 1 )
    {
      if ( a2 != 8 )
      {
LABEL_144:
        v14 = 87;
        goto LABEL_187;
      }
      DomainName1 = 0;
      RtlInitUnicodeString(&DomainName1, SourceString);
      if ( RtlEqualDomainName(&DomainName1, (PUNICODE_STRING)((char *)DomainByServerName + 56))
        || (unsigned int)NlEqualDnsNameU(&DomainName1, (struct _UNICODE_STRING *)DomainByServerName + 8) )
      {
        Block = (unsigned __int16 *)NetpAllocWStrFromWStr((char *)DomainByServerName + 216);
        v6 = Block;
        if ( !Block )
          goto LABEL_120;
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)DomainByServerName + 10);
        v54 = NetpAllocWStrFromWStr((char *)DomainByServerName + 72);
        v44 = v54;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)DomainByServerName + 10);
        if ( !v54 )
          goto LABEL_120;
      }
      else
      {
        v42 = NlFindNamedClientSession(DomainByServerName, &DomainName1, 0x10u, 0);
        v10 = v42;
        if ( !v42 )
        {
          NlPrintDomRoutine(
            0x100u,
            DomainByServerName,
            L"NetrLogonControl: User %ws\\%ws apparently isn't in this forest.\n",
            Buffer,
            SourceString);
          v14 = 2221;
          goto LABEL_189;
        }
        if ( (*((_BYTE *)v42 + 292) & 0x10) != 0 )
        {
          if ( (int)NlCaptureServerClientSession(v42, &v60, 0) >= 0 )
          {
            v6 = v60;
            Block = v60;
          }
          else
          {
            v6 = (unsigned __int16 *)NetpAllocWStrFromWStr((void *)&LocaleName);
            Block = v6;
          }
          if ( !v6 )
            goto LABEL_154;
        }
        else
        {
          v6 = 0;
        }
        v43 = (void *)*((_QWORD *)v10 + 23);
        if ( v43 )
        {
          v54 = NetpAllocWStrFromWStr(v43);
          v44 = v54;
          if ( !v54 )
          {
LABEL_154:
            v14 = 8;
            goto LABEL_188;
          }
        }
        else
        {
          v44 = 0;
          v54 = 0;
        }
      }
      **(_QWORD **)a5 = v6;
      LODWORD(v6) = 0;
      *(_QWORD *)(*(_QWORD *)a5 + 8LL) = v44;
    }
  }
  else
  {
    *v37 = (_DWORD)v6;
    *(_DWORD *)(*(_QWORD *)a5 + 4LL) = (_DWORD)v6;
    *(_DWORD *)(*(_QWORD *)a5 + 8LL) = (_DWORD)v6;
    *(_DWORD *)(*(_QWORD *)a5 + 12LL) = (_DWORD)v6;
    *(_DWORD *)(*(_QWORD *)a5 + 16LL) = (_DWORD)v6;
    *(_DWORD *)(*(_QWORD *)a5 + 20LL) = (_DWORD)v6;
    *(_DWORD *)(*(_QWORD *)a5 + 24LL) = (_DWORD)v6;
  }
LABEL_186:
  v14 = (unsigned int)v6;
LABEL_187:
  if ( v10 )
    goto LABEL_188;
LABEL_189:
  v10 = (struct _CLIENT_SESSION *)v54;
LABEL_190:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( SourceString )
    NetApiBufferFree((LPVOID)SourceString);
  if ( v14 )
  {
    if ( *(_QWORD *)a5 )
    {
      free(*(void **)a5);
      *(_QWORD *)a5 = 0;
    }
    if ( Block )
      free(Block);
    if ( v10 )
      free(v10);
  }
  if ( DomainByServerName )
    NlDereferenceDomain(DomainByServerName);
  if ( v63 )
    NetpDcDerefCacheEntry(v63);
  return v14;
}

```

## disassembly

```asm
0x18005fa30  push    rbp
0x18005fa32  push    rbx
0x18005fa33  push    rsi
0x18005fa34  push    rdi
0x18005fa35  push    r12
0x18005fa37  push    r13
0x18005fa39  push    r14
0x18005fa3b  push    r15
0x18005fa3d  lea     rbp, [rsp-17h]
0x18005fa42  sub     rsp, 0B8h
0x18005fa49  mov     r12, [rbp+4Fh+arg_20]
0x18005fa4d  xor     eax, eax
0x18005fa4f  xorps   xmm0, xmm0
0x18005fa52  mov     [rbp+4Fh+Block], rax
0x18005fa56  xor     r14d, r14d
0x18005fa59  mov     [rbp+4Fh+var_70], rax
0x18005fa5d  mov     rbx, r9
0x18005fa60  mov     [rbp+4Fh+var_A0], rax
0x18005fa64  mov     [r12], r14
0x18005fa68  mov     r13d, r8d
0x18005fa6b  mov     r15d, edx
0x18005fa6e  mov     [rbp+4Fh+Buffer], rax
0x18005fa72  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18005fa76  mov     edi, eax
0x18005fa78  mov     [rbp+4Fh+SourceString], rax
0x18005fa7c  mov     [rbp+4Fh+var_80], eax
0x18005fa7f  mov     [rbp+4Fh+var_7C], eax
0x18005fa82  mov     [rbp+4Fh+var_58], rax
0x18005fa86  mov     [rbp+4Fh+var_78], r14d
0x18005fa8a  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18005fa8f  mov     rsi, rax
0x18005fa92  test    rax, rax
0x18005fa95  jnz     short loc_18005FAA1
0x18005fa97  mov     ebx, 4BAh
0x18005fa9c  jmp     loc_1800605BA
0x18005faa1  mov     eax, r13d
0x18005faa4  sub     eax, 1
0x18005faa7  jz      short loc_18005FAC2
0x18005faa9  sub     eax, 1
0x18005faac  jz      short loc_18005FAC2
0x18005faae  sub     eax, 1
0x18005fab1  jz      short loc_18005FAC2
0x18005fab3  cmp     eax, 1
0x18005fab6  jz      short loc_18005FAC2
0x18005fab8  mov     ebx, 7Ch ; '|'
0x18005fabd  jmp     loc_1800605BA
0x18005fac2  mov     eax, r15d
0x18005fac5  sub     eax, 5
0x18005fac8  jz      short loc_18005FAE5
0x18005faca  sub     eax, 1
0x18005facd  jz      short loc_18005FAE5
0x18005facf  sub     eax, 2
0x18005fad2  jz      short loc_18005FAE5
0x18005fad4  sub     eax, 1
0x18005fad7  jz      short loc_18005FAE5
0x18005fad9  sub     eax, 1
0x18005fadc  jz      short loc_18005FAE5
0x18005fade  cmp     eax, 0FFF4h
0x18005fae3  jnz     short loc_18005FB0D
0x18005fae5  test    rbx, rbx
0x18005fae8  jnz     short loc_18005FB0D
0x18005faea  mov     r8d, 15E7h; unsigned int
0x18005faf0  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005faf7  lea     rcx, aInputdataNull; "InputData != NULL"
0x18005fafe  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005fb03  mov     ebx, 57h ; 'W'
0x18005fb08  jmp     loc_1800605BA
0x18005fb0d  mov     eax, 0FFFCh
0x18005fb12  cmp     r15d, eax
0x18005fb15  ja      short loc_18005FB42
0x18005fb17  jz      short loc_18005FB42
0x18005fb19  cmp     r15d, 7
0x18005fb1d  ja      short loc_18005FB67
0x18005fb1f  jz      short loc_18005FB83
0x18005fb21  mov     eax, r15d
0x18005fb24  sub     eax, 1
0x18005fb27  jz      short loc_18005FB83
0x18005fb29  sub     eax, 1
0x18005fb2c  jz      short loc_18005FB42
0x18005fb2e  sub     eax, 1
0x18005fb31  jz      short loc_18005FB42
0x18005fb33  sub     eax, 1
0x18005fb36  jz      short loc_18005FB42
0x18005fb38  sub     eax, 1
0x18005fb3b  jz      short loc_18005FB42
0x18005fb3d  cmp     eax, 1
0x18005fb40  jz      short loc_18005FB83
0x18005fb42  mov     edx, 4; DesiredAccess
0x18005fb47  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x18005fb4e  mov     r9d, 1
0x18005fb54  call    NetpAccessCheck2
0x18005fb59  test    eax, eax
0x18005fb5b  jz      short loc_18005FB8A
0x18005fb5d  mov     ebx, 5
0x18005fb62  jmp     loc_1800605BA
0x18005fb67  mov     eax, r15d
0x18005fb6a  sub     eax, 8
0x18005fb6d  jz      short loc_18005FB42
0x18005fb6f  sub     eax, 1
0x18005fb72  jz      short loc_18005FB42
0x18005fb74  sub     eax, 1
0x18005fb77  jz      short loc_18005FB42
0x18005fb79  sub     eax, 1
0x18005fb7c  jz      short loc_18005FB42
0x18005fb7e  sub     eax, 1
0x18005fb81  jnz     short loc_18005FB3D
0x18005fb83  mov     edx, 8
0x18005fb88  jmp     short loc_18005FB47
0x18005fb8a  mov     ecx, 1; int
0x18005fb8f  mov     dword ptr [rbp+4Fh+arg_20], ecx
0x18005fb92  cmp     r15d, 0Ah
0x18005fb96  ja      loc_18006014A
0x18005fb9c  jz      loc_1800600A9
0x18005fba2  mov     eax, r15d
0x18005fba5  sub     eax, ecx
0x18005fba7  jz      loc_180060090
0x18005fbad  sub     eax, 4
0x18005fbb0  jz      loc_18005FE91
0x18005fbb6  sub     eax, ecx
0x18005fbb8  jz      loc_18005FE0D
0x18005fbbe  sub     eax, ecx
0x18005fbc0  jz      loc_18005FDF2
0x18005fbc6  sub     eax, ecx
0x18005fbc8  jz      loc_18005FD04
0x18005fbce  cmp     eax, ecx
0x18005fbd0  jnz     short loc_18005FC0A
0x18005fbd2  lea     r8, aNetlogonContro; "NETLOGON_CONTROL_CHANGE_PASSWORD functi"...
0x18005fbd9  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005fbdc  mov     ecx, 200h; unsigned int
0x18005fbe1  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005fbe6  call    cs:__imp_LsaIIsContainerized
0x18005fbed  nop     dword ptr [rax+rax+00h]
0x18005fbf2  test    al, al
0x18005fbf4  jz      short loc_18005FC14
0x18005fbf6  lea     r8, aNetrlogoncontr_11; "NetrLogonControl called with NETLOGON_C"...
0x18005fbfd  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005fc00  mov     ecx, 100h; unsigned int
0x18005fc05  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005fc0a  mov     ebx, 32h ; '2'
0x18005fc0f  jmp     loc_1800605BA
0x18005fc14  mov     rdx, [rbx]; SourceString
0x18005fc17  test    rdx, rdx
0x18005fc1a  jnz     short loc_18005FC37
0x18005fc1c  lea     r8, aNetrlogoncontr_3; "NetrLogonControl called with NETLOGON_C"...
0x18005fc23  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005fc26  mov     ecx, 100h; unsigned int
0x18005fc2b  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005fc30  mov     ebx, 57h ; 'W'
0x18005fc35  jmp     short loc_18005FC0F
0x18005fc37  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18005fc3b  call    cs:__imp_RtlInitUnicodeStringEx
0x18005fc42  nop     dword ptr [rax+rax+00h]
0x18005fc47  mov     ebx, eax
0x18005fc49  test    eax, eax
0x18005fc4b  jns     short loc_18005FC6C
0x18005fc4d  mov     r8d, ebx
0x18005fc50  lea     rdx, aNetrlogoncontr_9; "NetrLogonControl2Ex: RtlInitUnicdeStrin"...
0x18005fc57  mov     ecx, 100h; unsigned int
0x18005fc5c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005fc61  mov     ecx, ebx; Status
0x18005fc63  call    NetpNtStatusToApiStatus
0x18005fc68  mov     ebx, eax
0x18005fc6a  jmp     short loc_18005FC0F
0x18005fc6c  xor     r9d, r9d; unsigned __int8 *
0x18005fc6f  lea     rdx, [rbp+4Fh+DestinationString]; struct _UNICODE_STRING *
0x18005fc73  mov     rcx, rsi; struct _DOMAIN_INFO *
0x18005fc76  lea     r8d, [r9+15h]; unsigned int
0x18005fc7a  call    ?NlFindNamedClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@KPEAE@Z; NlFindNamedClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,ulong,uchar *)
0x18005fc7f  mov     rdi, rax
0x18005fc82  test    rax, rax
0x18005fc85  jnz     short loc_18005FCAC
0x18005fc87  lea     r9, [rbp+4Fh+DestinationString]
0x18005fc8b  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005fc8e  lea     r8, aNetrlogoncontr_14; "NetrLogonControl can't find the client "...
0x18005fc95  mov     ecx, 100h; unsigned int
0x18005fc9a  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005fc9f  mov     ebx, 54Bh
0x18005fca4  mov     rdi, r14
0x18005fca7  jmp     loc_1800605BA
0x18005fcac  cmp     dword ptr [rsi+24Ch], 2
0x18005fcb3  jnz     short loc_18005FCE1
0x18005fcb5  mov     eax, [rax+118h]
0x18005fcbb  sub     eax, 3
0x18005fcbe  cmp     eax, 1
0x18005fcc1  ja      short loc_18005FCE1
0x18005fcc3  lea     r8, aNetrlogoncontr_17; "NetrLogonControl called with NETLOGON_C"...
0x18005fcca  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005fccd  mov     ecx, 100h; unsigned int
0x18005fcd2  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005fcd7  mov     ebx, 54Ah
0x18005fcdc  jmp     loc_1800605AE
0x18005fce1  xor     r8d, r8d; unsigned int *
0x18005fce4  mov     dl, 1; unsigned __int8
0x18005fce6  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18005fce9  call    ?NlChangePassword@@YAJPEAU_CLIENT_SESSION@@EPEAK@Z; NlChangePassword(_CLIENT_SESSION *,uchar,ulong *)
0x18005fcee  mov     ebx, eax
0x18005fcf0  test    eax, eax
0x18005fcf2  jns     loc_180060283
0x18005fcf8  lea     r8, aNetrlogoncontr_2; "NetrLogonControl: Password Change faile"...
0x18005fcff  jmp     loc_180060072
0x18005fd04  mov     r8, [rbx]
0x18005fd07  lea     rdx, aNetlogonContro_0; "NETLOGON_CONTROL_FIND_USER function rec"...
0x18005fd0e  xorps   xmm0, xmm0
0x18005fd11  mov     ecx, 2; unsigned int
0x18005fd16  movups  xmmword ptr [rbp+4Fh+DomainName1.Length], xmm0
0x18005fd1a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005fd1f  cmp     r13d, 4
0x18005fd23  jnz     loc_18005FC30
0x18005fd29  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r14d; int NlGlobalMemberWorkstation
0x18005fd30  jnz     loc_18005FC0A
0x18005fd36  mov     rdx, [rbx]; SourceString
0x18005fd39  lea     rcx, [rbp+4Fh+DomainName1]; DestinationString
0x18005fd3d  call    cs:__imp_RtlInitUnicodeStringEx
0x18005fd44  nop     dword ptr [rax+rax+00h]
0x18005fd49  mov     r14d, eax
0x18005fd4c  test    eax, eax
0x18005fd4e  jns     short loc_18005FD6C
0x18005fd50  mov     r8d, eax
0x18005fd53  lea     rdx, aNetrlogoncontr_16; "NetrLogonControl2Ex: RtlInitUnicdeStrin"...
0x18005fd5a  mov     ecx, 100h; unsigned int
0x18005fd5f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005fd64  mov     ecx, r14d
0x18005fd67  jmp     loc_18005FC63
0x18005fd6c  xor     r14d, r14d
0x18005fd6f  lea     rax, [rbp+4Fh+var_80]
0x18005fd73  mov     [rsp+0F0h+var_A8], rax
0x18005fd78  lea     rdx, [rbp+4Fh+DomainName1]
0x18005fd7c  lea     rax, [rbp+4Fh+SourceString]
0x18005fd80  mov     r9d, 1D0h
0x18005fd86  mov     [rsp+0F0h+var_B0], rax
0x18005fd8b  xor     r8d, r8d
0x18005fd8e  lea     rax, [rbp+4Fh+Buffer]
0x18005fd92  mov     rcx, rsi
0x18005fd95  mov     [rsp+0F0h+var_B8], rax
0x18005fd9a  mov     byte ptr [rsp+0F0h+var_C0], r14b
0x18005fd9f  mov     byte ptr [rsp+0F0h+var_C8], r14b
0x18005fda4  mov     [rsp+0F0h+var_D0], r14d
0x18005fda9  call    ?NlPickDomainWithAccount@@YAJPEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@1KW4_NETLOGON_SECURE_CHANNEL_TYPE@@EEPEAPEAG3PEAK@Z; NlPickDomainWithAccount(_DOMAIN_INFO *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,_NETLOGON_SECURE_CHANNEL_TYPE,uchar,uchar,ushort * *,ushort * *,ulong *)
0x18005fdae  test    eax, eax
0x18005fdb0  jns     short loc_18005FDCA
0x18005fdb2  cmp     eax, 0C00000DFh
0x18005fdb7  jnz     short loc_18005FDC3
0x18005fdb9  mov     ebx, 8ADh
0x18005fdbe  jmp     loc_18005FC0F
0x18005fdc3  mov     ecx, eax
0x18005fdc5  jmp     loc_18005FC63
0x18005fdca  mov     eax, [rbp+4Fh+var_80]
0x18005fdcd  test    al, 3
0x18005fdcf  jz      loc_1800602A5
0x18005fdd5  mov     r9, [rbx]
0x18005fdd8  lea     r8, aNetrlogoncontr; "NetrLogonControl: User %ws is in a trus"...
0x18005fddf  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005fde2  mov     [rsp+0F0h+var_D0], eax
0x18005fde6  mov     ecx, 100h; unsigned int
0x18005fdeb  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005fdf0  jmp     short loc_18005FDB9
0x18005fdf2  lea     rdx, aNetlogonContro_1; "NETLOGON_CONTROL_TRANSPORT_NOTIFY funct"...
0x18005fdf9  mov     ecx, 200h; unsigned int
0x18005fdfe  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005fe03  call    ?NlFlushCacheOnPnp@@YAXXZ; NlFlushCacheOnPnp(void)
0x18005fe08  jmp     loc_180060283
0x18005fe0d  lea     r8, aNetlogonContro_5; "NETLOGON_CONTROL_TC_QUERY function rece"...
0x18005fe14  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005fe17  mov     ecx, 200h; unsigned int
0x18005fe1c  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005fe21  cmp     [rbx], r14
0x18005fe24  jnz     short loc_18005FE3F
0x18005fe26  mov     r8d, 16DFh; unsigned int
0x18005fe2c  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005fe33  lea     rcx, aInputdataTrust; "InputData->TrustedDomainName != NULL"
0x18005fe3a  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005fe3f  mov     rdx, [rbx]; SourceString
0x18005fe42  test    rdx, rdx
0x18005fe45  jnz     short loc_18005FE53
0x18005fe47  lea     r8, aNetrlogoncontr_4; "NetrLogonControl called with NETLOGON_C"...
0x18005fe4e  jmp     loc_18005FC23
0x18005fe53  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18005fe57  call    cs:__imp_RtlInitUnicodeStringEx
0x18005fe5e  nop     dword ptr [rax+rax+00h]
0x18005fe63  mov     ebx, eax
0x18005fe65  test    eax, eax
0x18005fe67  js      loc_18005FC4D
0x18005fe6d  xor     r9d, r9d; unsigned __int8 *
0x18005fe70  lea     rdx, [rbp+4Fh+DestinationString]; struct _UNICODE_STRING *
0x18005fe74  mov     rcx, rsi; struct _DOMAIN_INFO *
0x18005fe77  lea     r8d, [r9+11h]; unsigned int
0x18005fe7b  call    ?NlFindNamedClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@KPEAE@Z; NlFindNamedClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,ulong,uchar *)
0x18005fe80  mov     rdi, rax
0x18005fe83  test    rax, rax
0x18005fe86  jnz     loc_180060283
0x18005fe8c  jmp     loc_18005FC87
0x18005fe91  lea     r8, aNetlogonContro_2; "NETLOGON_CONTROL_REDISCOVER function re"...
0x18005fe98  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005fe9b  mov     ecx, 200h; unsigned int
0x18005fea0  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005fea5  cmp     [rbx], r14
0x18005fea8  jnz     short loc_18005FEC3
0x18005feaa  mov     r8d, 163Dh; unsigned int
0x18005feb0  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005feb7  lea     rcx, aInputdataTrust; "InputData->TrustedDomainName != NULL"
  ... truncated ...
```
