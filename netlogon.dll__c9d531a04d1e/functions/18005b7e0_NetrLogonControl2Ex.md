# NetrLogonControl2Ex

- ea: `0x18005b7e0`
- end: `0x18005c3a3`
- name: `NetrLogonControl2Ex`
- size: `3011`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, int, PCWSTR *, union _NETLOGON_CONTROL_QUERY_INFORMATION *)`
- caller_count: `2`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005b760`
- `0x18005b7d0`

## callees

- `0x180003170`
- `0x180003700`
- `0x180005420`
- `0x180007278`
- `0x180007b50`
- `0x18000bd98`
- `0x18000c3ac`
- `0x18000d710`
- `0x18000da94`
- `0x180020620`
- `0x180025708`
- `0x18002601c`
- `0x18002707c`
- `0x180033a34`
- `0x1800382f8`
- `0x180039830`
- `0x18003e350`
- `0x18003e71c`
- `0x180057aec`
- `0x180059e9c`
- `0x18005b7e0`
- `0x180064228`
- `0x180064f64`
- `0x18006541c`
- `0x1800675c0`
- `0x180067df0`
- `0x180068458`
- `0x1800694d0`
- `0x180083180`
- `0x1800844d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c347`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c35e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c36c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c347`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c35e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005c36c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005bc74`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18005bc74`
- `LSASRV!LsaIIsContainerized` at `0x18005b996`
- `LSASRV!LsaIIsContainerized` at `0x18005b996`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005b9e5`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005bae1`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005bbf5`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005bc93`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005be8f`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005b9e5`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005bae1`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005bbf5`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005bc93`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005be8f`
- `ntdll!RtlEqualDomainName` at `0x18005c092`
- `ntdll!RtlEqualDomainName` at `0x18005c092`
- `ntdll!RtlLeaveCriticalSection` at `0x18005bfc6`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c1b1`
- `ntdll!RtlLeaveCriticalSection` at `0x18005bfc6`
- `ntdll!RtlLeaveCriticalSection` at `0x18005c1b1`
- `ntdll!RtlEnterCriticalSection` at `0x18005bf8b`
- `ntdll!RtlEnterCriticalSection` at `0x18005c198`
- `ntdll!RtlEnterCriticalSection` at `0x18005bf8b`
- `ntdll!RtlEnterCriticalSection` at `0x18005c198`
- `ntdll!RtlInitUnicodeString` at `0x18005c084`
- `ntdll!RtlInitUnicodeString` at `0x18005c084`
- `netutils!NetApiBufferFree` at `0x18005c325`
- `netutils!NetApiBufferFree` at `0x18005c334`
- `netutils!NetApiBufferFree` at `0x18005c325`
- `netutils!NetApiBufferFree` at `0x18005c334`

## string_xrefs

- `0x18005b8a0`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005bbca`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005bc48`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005be54`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`
- `0x18005bd72`: `NetrLogonControl2: Can't become writer of client session.\n`
- `0x18005b9a0`: `NetrLogonControl called with NETLOGON_CONTROL_CHANGE_PASSWORD when running inside a container.\n`

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
  int v20; // ebx
  PCWSTR v21; // r8
  NTSTATUS v22; // eax
  NTSTATUS v23; // r14d
  int v24; // eax
  char *v25; // r9
  char *v26; // r9
  wchar_t *v27; // r14
  unsigned int v28; // eax
  unsigned int v29; // eax
  NTSTATUS v30; // ecx
  char *v31; // r9
  struct _CLIENT_SESSION *NamedClientSession; // rax
  size_t v33; // rcx
  _DWORD *v34; // rax
  HLOCAL *i; // rax
  int v36; // r13d
  int v37; // r13d
  int v38; // r13d
  struct _CLIENT_SESSION *v39; // rax
  void *v40; // rcx
  __int64 v41; // r15
  unsigned int v42; // r15d
  unsigned int v43; // r15d
  NTSTATUS v44; // ebx
  char v45; // cl
  struct _CLIENT_SESSION *v46; // rax
  struct _CLIENT_SESSION *v47; // rbx
  int v49[2]; // [rsp+20h] [rbp-81h]
  int v50[2]; // [rsp+20h] [rbp-81h]
  __int64 v51; // [rsp+50h] [rbp-51h]
  unsigned __int16 *Block; // [rsp+58h] [rbp-49h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-41h] BYREF
  int v54; // [rsp+70h] [rbp-31h] BYREF
  unsigned int v55; // [rsp+74h] [rbp-2Dh] BYREF
  unsigned int v56; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int16 *v57; // [rsp+80h] [rbp-21h] BYREF
  PCWSTR SourceString; // [rsp+88h] [rbp-19h] BYREF
  LPVOID Buffer; // [rsp+90h] [rbp-11h] BYREF
  struct _NL_DC_CACHE_ENTRY *v60; // [rsp+98h] [rbp-9h] BYREF
  struct _UNICODE_STRING DomainName1; // [rsp+A0h] [rbp-1h] BYREF
  int v62; // [rsp+120h] [rbp+7Fh]

  Block = 0;
  v6 = 0;
  v57 = 0;
  v51 = 0;
  *(_QWORD *)a5 = 0;
  Buffer = 0;
  DestinationString = 0;
  v10 = 0;
  SourceString = 0;
  v54 = 0;
  v55 = 0;
  v60 = 0;
  v56 = 0;
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
    NlAssertFailed("InputData != NULL", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx", 0x15E5u, v13);
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
  v62 = 1;
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
        v62 = 1;
        RtlEnterCriticalSection(&NlGlobalDnsCritSect);
        for ( i = (HLOCAL *)NlGlobalDnsList; i != &NlGlobalDnsList; i = (HLOCAL *)*i )
        {
          if ( *((_DWORD *)i + 60) != 4 && *((_DWORD *)i + 61) )
          {
            v62 = 0;
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
        v24 = NetIGetEncTypes(&v56);
        if ( v24 >= 0 )
        {
LABEL_118:
          v33 = 8;
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
        0x170Au,
        v31);
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
          v30 = NlVerifyTrust(NamedClientSession, a5);
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
          NlUnrefClientSession(v10);
          goto LABEL_189;
        }
        v20 = NlChangePassword(v19, 1u, 0);
        if ( v20 < 0 )
        {
          NlPrintCsRoutine(0x100u, v10, L"NetrLogonControl: Password Change failed %lx\n", (unsigned int)v20);
LABEL_97:
          v30 = v20;
LABEL_98:
          v14 = NetpNtStatusToApiStatus(v30);
          goto LABEL_188;
        }
        goto LABEL_132;
      }
      v21 = *a4;
      DomainName1 = 0;
      NlPrintRoutine(2u, L"NETLOGON_CONTROL_FIND_USER function received for %ws.\n", v21);
      if ( a3 != 4 )
        goto LABEL_46;
      if ( NlGlobalMemberWorkstation )
        goto LABEL_43;
      v22 = RtlInitUnicodeStringEx(&DomainName1, *a4);
      v23 = v22;
      if ( v22 < 0 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetrLogonControl2Ex: RtlInitUnicdeStringEx on InputData->UserName failed: 0x%08x\n",
          (unsigned int)v22);
        v18 = v23;
        goto LABEL_49;
      }
      LODWORD(v6) = 0;
      v24 = NlPickDomainWithAccount(DomainByServerName, &DomainName1, 0, 464, 0, 0, 0, &Buffer, &SourceString, &v54);
      if ( v24 >= 0 )
      {
        if ( (v54 & 3) == 0 )
        {
LABEL_136:
          v33 = 16;
          goto LABEL_119;
        }
        v49[0] = v54;
        NlPrintDomRoutine(
          0x100u,
          DomainByServerName,
          L"NetrLogonControl: User %ws is in a trusted forest (%lx).\n",
          *a4,
          *(_QWORD *)v49);
LABEL_63:
        v14 = 2221;
        goto LABEL_190;
      }
      if ( v24 == -1073741601 )
        goto LABEL_63;
LABEL_64:
      v18 = v24;
      goto LABEL_49;
    }
    NlPrintDomRoutine(0x200u, DomainByServerName, L"NETLOGON_CONTROL_TC_QUERY function received.\n");
    if ( !*a4 )
      NlAssertFailed(
        "InputData->TrustedDomainName != NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
        0x16DDu,
        v25);
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
      0x163Bu,
      v26);
  if ( !*a4 )
  {
    NlPrintDomRoutine(
      0x100u,
      DomainByServerName,
      L"NetrLogonControl called with function code NETLOGON_CONTROL_REDISCOVER specified NULL trusted domain name. \n");
    goto LABEL_46;
  }
  v27 = wcschr(*a4, 0x5Cu);
  if ( v27 )
    *v27++ = 0;
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
  if ( v27 )
  {
    v28 = NlPingDcName(v10, 0, 1, 0, 1, 0, v27, 0, &v60);
    v14 = v28;
    if ( v28 )
    {
      v50[0] = v28;
      NlPrintCsRoutine(0x200u, v10, L"NetrLogonControl: Unsuccessful response from DC %ws 0x%lx\n", v27, *(_QWORD *)v50);
      if ( v14 == 1062 )
        goto LABEL_188;
LABEL_88:
      v14 = 1311;
      goto LABEL_188;
    }
    NlPrintCsRoutine(0x200u, v10, L"NetrLogonControl: Successful response from DC %ws\n", v27);
  }
  if ( !(unsigned int)NlTimeoutSetWriterClientSession(v10, dwMilliseconds) )
  {
    NlPrintDomRoutine(0x100u, DomainByServerName, L"NetrLogonControl2: Can't become writer of client session.\n");
    goto LABEL_88;
  }
  NlSetStatusClientSession(v10, -1073741730);
  v6 = (unsigned __int16 *)v60;
  if ( v60 )
  {
    v29 = NlSetServerClientSession(v10, v60, 1, 0);
    v6 = 0;
    v14 = v29;
    if ( v29 )
    {
      NlPrintCsRoutine(0x100u, v10, L"NetrLogonControl: NlSetServerClientSession failed 0x%lx\n", v29);
      NlResetWriterClientSession(v10);
      goto LABEL_188;
    }
  }
  v20 = NlSessionSetupEx(v10);
  NlResetWriterClientSession(v10);
  if ( v20 < 0 )
  {
    NlPrintCsRoutine(0x100u, v10, L"NetrLogonControl: Discovery failed %lx\n", (unsigned int)v20);
    goto LABEL_97;
  }
LABEL_132:
  v33 = (size_t)v6;
  switch ( a3 )
  {
    case 1:
      goto LABEL_118;
    case 2:
      v33 = 24;
      break;
    case 3:
      v33 = 28;
      break;
    case 4:
      goto LABEL_136;
    default:
      break;
  }
LABEL_119:
  v34 = MIDL_user_allocate(v33);
  *(_QWORD *)a5 = v34;
  if ( !v34 )
  {
LABEL_120:
    v14 = 8;
    goto LABEL_187;
  }
  v36 = a3 - 1;
  if ( !v36 )
  {
LABEL_173:
    v45 = v55;
    **(_DWORD **)a5 = (_DWORD)v6;
    if ( v45 < 0 )
      **(_DWORD **)a5 |= 0x20u;
    if ( (v45 & 0x10) != 0 )
      **(_DWORD **)a5 |= 0x10u;
    if ( v62 == (_DWORD)v6 )
      **(_DWORD **)a5 |= 0x40u;
    if ( v56 )
      **(_DWORD **)a5 = v56;
    if ( *((_DWORD *)DomainByServerName + 147) == 1 )
    {
      *(_DWORD *)(*(_QWORD *)a5 + 4LL) = (_DWORD)v6;
    }
    else
    {
      v46 = NlRefDomClientSession(DomainByServerName);
      v47 = v46;
      if ( v46 )
      {
        *(_DWORD *)(*(_QWORD *)a5 + 4LL) = NetpNtStatusToApiStatus(*((_DWORD *)v46 + 72));
        NlUnrefClientSession(v47);
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)a5 + 4LL) = 50;
      }
    }
    goto LABEL_186;
  }
  v37 = v36 - 1;
  if ( !v37 )
  {
    v42 = a2 - 5;
    if ( v42 )
    {
      v43 = v42 - 1;
      if ( v43 )
      {
        if ( v43 != 4 )
          goto LABEL_144;
      }
    }
    if ( v10 )
    {
      v44 = NlCaptureServerClientSession(v10, &v57, &v55);
      *(_DWORD *)(*(_QWORD *)a5 + 16LL) = NetpNtStatusToApiStatus(v44);
      if ( v44 >= 0 )
      {
        v6 = v57;
        Block = v57;
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
  v38 = v37 - 1;
  if ( v38 )
  {
    if ( v38 == 1 )
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
        v51 = NetpAllocWStrFromWStr((char *)DomainByServerName + 72);
        v41 = v51;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)DomainByServerName + 10);
        if ( !v51 )
          goto LABEL_120;
      }
      else
      {
        v39 = NlFindNamedClientSession(DomainByServerName, &DomainName1, 0x10u, 0);
        v10 = v39;
        if ( !v39 )
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
        if ( (*((_BYTE *)v39 + 292) & 0x10) != 0 )
        {
          if ( (int)NlCaptureServerClientSession(v39, &v57, 0) >= 0 )
          {
            v6 = v57;
            Block = v57;
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
        v40 = (void *)*((_QWORD *)v10 + 23);
        if ( v40 )
        {
          v51 = NetpAllocWStrFromWStr(v40);
          v41 = v51;
          if ( !v51 )
          {
LABEL_154:
            v14 = 8;
            goto LABEL_188;
          }
        }
        else
        {
          v41 = 0;
          v51 = 0;
        }
      }
      **(_QWORD **)a5 = v6;
      LODWORD(v6) = 0;
      *(_QWORD *)(*(_QWORD *)a5 + 8LL) = v41;
    }
  }
  else
  {
    *v34 = (_DWORD)v6;
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
  v10 = (struct _CLIENT_SESSION *)v51;
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
  if ( v60 )
    NetpDcDerefCacheEntry(v60);
  return v14;
}

```

## disassembly

```asm
0x18005b7e0  push    rbp
0x18005b7e2  push    rbx
0x18005b7e3  push    rsi
0x18005b7e4  push    rdi
0x18005b7e5  push    r12
0x18005b7e7  push    r13
0x18005b7e9  push    r14
0x18005b7eb  push    r15
0x18005b7ed  lea     rbp, [rsp-17h]
0x18005b7f2  sub     rsp, 0B8h
0x18005b7f9  mov     r12, [rbp+4Fh+arg_20]
0x18005b7fd  xor     eax, eax
0x18005b7ff  xorps   xmm0, xmm0
0x18005b802  mov     [rbp+4Fh+Block], rax
0x18005b806  xor     r14d, r14d
0x18005b809  mov     [rbp+4Fh+var_70], rax
0x18005b80d  mov     rbx, r9
0x18005b810  mov     [rbp+4Fh+var_A0], rax
0x18005b814  mov     [r12], r14
0x18005b818  mov     r13d, r8d
0x18005b81b  mov     r15d, edx
0x18005b81e  mov     [rbp+4Fh+Buffer], rax
0x18005b822  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18005b826  mov     edi, eax
0x18005b828  mov     [rbp+4Fh+SourceString], rax
0x18005b82c  mov     [rbp+4Fh+var_80], eax
0x18005b82f  mov     [rbp+4Fh+var_7C], eax
0x18005b832  mov     [rbp+4Fh+var_58], rax
0x18005b836  mov     [rbp+4Fh+var_78], r14d
0x18005b83a  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18005b83f  mov     rsi, rax
0x18005b842  test    rax, rax
0x18005b845  jnz     short loc_18005B851
0x18005b847  mov     ebx, 4BAh
0x18005b84c  jmp     loc_18005C31C
0x18005b851  mov     eax, r13d
0x18005b854  sub     eax, 1
0x18005b857  jz      short loc_18005B872
0x18005b859  sub     eax, 1
0x18005b85c  jz      short loc_18005B872
0x18005b85e  sub     eax, 1
0x18005b861  jz      short loc_18005B872
0x18005b863  cmp     eax, 1
0x18005b866  jz      short loc_18005B872
0x18005b868  mov     ebx, 7Ch ; '|'
0x18005b86d  jmp     loc_18005C31C
0x18005b872  mov     eax, r15d
0x18005b875  sub     eax, 5
0x18005b878  jz      short loc_18005B895
0x18005b87a  sub     eax, 1
0x18005b87d  jz      short loc_18005B895
0x18005b87f  sub     eax, 2
0x18005b882  jz      short loc_18005B895
0x18005b884  sub     eax, 1
0x18005b887  jz      short loc_18005B895
0x18005b889  sub     eax, 1
0x18005b88c  jz      short loc_18005B895
0x18005b88e  cmp     eax, 0FFF4h
0x18005b893  jnz     short loc_18005B8BD
0x18005b895  test    rbx, rbx
0x18005b898  jnz     short loc_18005B8BD
0x18005b89a  mov     r8d, 15E5h; unsigned int
0x18005b8a0  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005b8a7  lea     rcx, aInputdataNull; "InputData != NULL"
0x18005b8ae  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005b8b3  mov     ebx, 57h ; 'W'
0x18005b8b8  jmp     loc_18005C31C
0x18005b8bd  mov     eax, 0FFFCh
0x18005b8c2  cmp     r15d, eax
0x18005b8c5  ja      short loc_18005B8F2
0x18005b8c7  jz      short loc_18005B8F2
0x18005b8c9  cmp     r15d, 7
0x18005b8cd  ja      short loc_18005B917
0x18005b8cf  jz      short loc_18005B933
0x18005b8d1  mov     eax, r15d
0x18005b8d4  sub     eax, 1
0x18005b8d7  jz      short loc_18005B933
0x18005b8d9  sub     eax, 1
0x18005b8dc  jz      short loc_18005B8F2
0x18005b8de  sub     eax, 1
0x18005b8e1  jz      short loc_18005B8F2
0x18005b8e3  sub     eax, 1
0x18005b8e6  jz      short loc_18005B8F2
0x18005b8e8  sub     eax, 1
0x18005b8eb  jz      short loc_18005B8F2
0x18005b8ed  cmp     eax, 1
0x18005b8f0  jz      short loc_18005B933
0x18005b8f2  mov     edx, 4; DesiredAccess
0x18005b8f7  mov     rcx, cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; pSecurityDescriptor
0x18005b8fe  mov     r9d, 1
0x18005b904  call    NetpAccessCheck2
0x18005b909  test    eax, eax
0x18005b90b  jz      short loc_18005B93A
0x18005b90d  mov     ebx, 5
0x18005b912  jmp     loc_18005C31C
0x18005b917  mov     eax, r15d
0x18005b91a  sub     eax, 8
0x18005b91d  jz      short loc_18005B8F2
0x18005b91f  sub     eax, 1
0x18005b922  jz      short loc_18005B8F2
0x18005b924  sub     eax, 1
0x18005b927  jz      short loc_18005B8F2
0x18005b929  sub     eax, 1
0x18005b92c  jz      short loc_18005B8F2
0x18005b92e  sub     eax, 1
0x18005b931  jnz     short loc_18005B8ED
0x18005b933  mov     edx, 8
0x18005b938  jmp     short loc_18005B8F7
0x18005b93a  mov     ecx, 1; int
0x18005b93f  mov     dword ptr [rbp+4Fh+arg_20], ecx
0x18005b942  cmp     r15d, 0Ah
0x18005b946  ja      loc_18005BED0
0x18005b94c  jz      loc_18005BE35
0x18005b952  mov     eax, r15d
0x18005b955  sub     eax, ecx
0x18005b957  jz      loc_18005BE1C
0x18005b95d  sub     eax, 4
0x18005b960  jz      loc_18005BC29
0x18005b966  sub     eax, ecx
0x18005b968  jz      loc_18005BBAB
0x18005b96e  sub     eax, ecx
0x18005b970  jz      loc_18005BB90
0x18005b976  sub     eax, ecx
0x18005b978  jz      loc_18005BAA8
0x18005b97e  cmp     eax, ecx
0x18005b980  jnz     short loc_18005B9B4
0x18005b982  lea     r8, aNetlogonContro; "NETLOGON_CONTROL_CHANGE_PASSWORD functi"...
0x18005b989  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005b98c  mov     ecx, 200h; unsigned int
0x18005b991  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005b996  call    cs:__imp_LsaIIsContainerized
0x18005b99c  test    al, al
0x18005b99e  jz      short loc_18005B9BE
0x18005b9a0  lea     r8, aNetrlogoncontr_11; "NetrLogonControl called with NETLOGON_C"...
0x18005b9a7  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005b9aa  mov     ecx, 100h; unsigned int
0x18005b9af  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005b9b4  mov     ebx, 32h ; '2'
0x18005b9b9  jmp     loc_18005C31C
0x18005b9be  mov     rdx, [rbx]; SourceString
0x18005b9c1  test    rdx, rdx
0x18005b9c4  jnz     short loc_18005B9E1
0x18005b9c6  lea     r8, aNetrlogoncontr_3; "NetrLogonControl called with NETLOGON_C"...
0x18005b9cd  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005b9d0  mov     ecx, 100h; unsigned int
0x18005b9d5  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005b9da  mov     ebx, 57h ; 'W'
0x18005b9df  jmp     short loc_18005B9B9
0x18005b9e1  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18005b9e5  call    cs:__imp_RtlInitUnicodeStringEx
0x18005b9eb  mov     ebx, eax
0x18005b9ed  test    eax, eax
0x18005b9ef  jns     short loc_18005BA10
0x18005b9f1  mov     r8d, ebx
0x18005b9f4  lea     rdx, aNetrlogoncontr_9; "NetrLogonControl2Ex: RtlInitUnicdeStrin"...
0x18005b9fb  mov     ecx, 100h; unsigned int
0x18005ba00  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005ba05  mov     ecx, ebx; Status
0x18005ba07  call    NetpNtStatusToApiStatus
0x18005ba0c  mov     ebx, eax
0x18005ba0e  jmp     short loc_18005B9B9
0x18005ba10  xor     r9d, r9d; unsigned __int8 *
0x18005ba13  lea     rdx, [rbp+4Fh+DestinationString]; struct _UNICODE_STRING *
0x18005ba17  mov     rcx, rsi; struct _DOMAIN_INFO *
0x18005ba1a  lea     r8d, [r9+15h]; unsigned int
0x18005ba1e  call    ?NlFindNamedClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@KPEAE@Z; NlFindNamedClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,ulong,uchar *)
0x18005ba23  mov     rdi, rax
0x18005ba26  test    rax, rax
0x18005ba29  jnz     short loc_18005BA50
0x18005ba2b  lea     r9, [rbp+4Fh+DestinationString]
0x18005ba2f  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005ba32  lea     r8, aNetrlogoncontr_14; "NetrLogonControl can't find the client "...
0x18005ba39  mov     ecx, 100h; unsigned int
0x18005ba3e  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005ba43  mov     ebx, 54Bh
0x18005ba48  mov     rdi, r14
0x18005ba4b  jmp     loc_18005C31C
0x18005ba50  cmp     dword ptr [rsi+24Ch], 2
0x18005ba57  jnz     short loc_18005BA85
0x18005ba59  mov     eax, [rax+118h]
0x18005ba5f  sub     eax, 3
0x18005ba62  cmp     eax, 1
0x18005ba65  ja      short loc_18005BA85
0x18005ba67  lea     r8, aNetrlogoncontr_17; "NetrLogonControl called with NETLOGON_C"...
0x18005ba6e  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005ba71  mov     ecx, 100h; unsigned int
0x18005ba76  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005ba7b  mov     ebx, 54Ah
0x18005ba80  jmp     loc_18005C310
0x18005ba85  xor     r8d, r8d; unsigned int *
0x18005ba88  mov     dl, 1; unsigned __int8
0x18005ba8a  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18005ba8d  call    ?NlChangePassword@@YAJPEAU_CLIENT_SESSION@@EPEAK@Z; NlChangePassword(_CLIENT_SESSION *,uchar,ulong *)
0x18005ba92  mov     ebx, eax
0x18005ba94  test    eax, eax
0x18005ba96  jns     loc_18005BFFD
0x18005ba9c  lea     r8, aNetrlogoncontr_2; "NetrLogonControl: Password Change faile"...
0x18005baa3  jmp     loc_18005BDFE
0x18005baa8  mov     r8, [rbx]
0x18005baab  lea     rdx, aNetlogonContro_0; "NETLOGON_CONTROL_FIND_USER function rec"...
0x18005bab2  xorps   xmm0, xmm0
0x18005bab5  mov     ecx, 2; unsigned int
0x18005baba  movups  xmmword ptr [rbp+4Fh+DomainName1.Length], xmm0
0x18005babe  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005bac3  cmp     r13d, 4
0x18005bac7  jnz     loc_18005B9DA
0x18005bacd  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r14d; int NlGlobalMemberWorkstation
0x18005bad4  jnz     loc_18005B9B4
0x18005bada  mov     rdx, [rbx]; SourceString
0x18005badd  lea     rcx, [rbp+4Fh+DomainName1]; DestinationString
0x18005bae1  call    cs:__imp_RtlInitUnicodeStringEx
0x18005bae7  mov     r14d, eax
0x18005baea  test    eax, eax
0x18005baec  jns     short loc_18005BB0A
0x18005baee  mov     r8d, eax
0x18005baf1  lea     rdx, aNetrlogoncontr_16; "NetrLogonControl2Ex: RtlInitUnicdeStrin"...
0x18005baf8  mov     ecx, 100h; unsigned int
0x18005bafd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005bb02  mov     ecx, r14d
0x18005bb05  jmp     loc_18005BA07
0x18005bb0a  xor     r14d, r14d
0x18005bb0d  lea     rax, [rbp+4Fh+var_80]
0x18005bb11  mov     [rsp+0F0h+var_A8], rax
0x18005bb16  lea     rdx, [rbp+4Fh+DomainName1]
0x18005bb1a  lea     rax, [rbp+4Fh+SourceString]
0x18005bb1e  mov     r9d, 1D0h
0x18005bb24  mov     [rsp+0F0h+var_B0], rax
0x18005bb29  xor     r8d, r8d
0x18005bb2c  lea     rax, [rbp+4Fh+Buffer]
0x18005bb30  mov     rcx, rsi
0x18005bb33  mov     [rsp+0F0h+var_B8], rax
0x18005bb38  mov     byte ptr [rsp+0F0h+var_C0], r14b
0x18005bb3d  mov     byte ptr [rsp+0F0h+var_C8], r14b
0x18005bb42  mov     [rsp+0F0h+var_D0], r14d
0x18005bb47  call    ?NlPickDomainWithAccount@@YAJPEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@1KW4_NETLOGON_SECURE_CHANNEL_TYPE@@EEPEAPEAG3PEAK@Z; NlPickDomainWithAccount(_DOMAIN_INFO *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,_NETLOGON_SECURE_CHANNEL_TYPE,uchar,uchar,ushort * *,ushort * *,ulong *)
0x18005bb4c  test    eax, eax
0x18005bb4e  jns     short loc_18005BB68
0x18005bb50  cmp     eax, 0C00000DFh
0x18005bb55  jnz     short loc_18005BB61
0x18005bb57  mov     ebx, 8ADh
0x18005bb5c  jmp     loc_18005B9B9
0x18005bb61  mov     ecx, eax
0x18005bb63  jmp     loc_18005BA07
0x18005bb68  mov     eax, [rbp+4Fh+var_80]
0x18005bb6b  test    al, 3
0x18005bb6d  jz      loc_18005C01F
0x18005bb73  mov     r9, [rbx]
0x18005bb76  lea     r8, aNetrlogoncontr; "NetrLogonControl: User %ws is in a trus"...
0x18005bb7d  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005bb80  mov     [rsp+0F0h+var_D0], eax
0x18005bb84  mov     ecx, 100h; unsigned int
0x18005bb89  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005bb8e  jmp     short loc_18005BB57
0x18005bb90  lea     rdx, aNetlogonContro_1; "NETLOGON_CONTROL_TRANSPORT_NOTIFY funct"...
0x18005bb97  mov     ecx, 200h; unsigned int
0x18005bb9c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005bba1  call    ?NlFlushCacheOnPnp@@YAXXZ; NlFlushCacheOnPnp(void)
0x18005bba6  jmp     loc_18005BFFD
0x18005bbab  lea     r8, aNetlogonContro_5; "NETLOGON_CONTROL_TC_QUERY function rece"...
0x18005bbb2  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005bbb5  mov     ecx, 200h; unsigned int
0x18005bbba  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005bbbf  cmp     [rbx], r14
0x18005bbc2  jnz     short loc_18005BBDD
0x18005bbc4  mov     r8d, 16DDh; unsigned int
0x18005bbca  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005bbd1  lea     rcx, aInputdataTrust; "InputData->TrustedDomainName != NULL"
0x18005bbd8  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005bbdd  mov     rdx, [rbx]; SourceString
0x18005bbe0  test    rdx, rdx
0x18005bbe3  jnz     short loc_18005BBF1
0x18005bbe5  lea     r8, aNetrlogoncontr_4; "NetrLogonControl called with NETLOGON_C"...
0x18005bbec  jmp     loc_18005B9CD
0x18005bbf1  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18005bbf5  call    cs:__imp_RtlInitUnicodeStringEx
0x18005bbfb  mov     ebx, eax
0x18005bbfd  test    eax, eax
0x18005bbff  js      loc_18005B9F1
0x18005bc05  xor     r9d, r9d; unsigned __int8 *
0x18005bc08  lea     rdx, [rbp+4Fh+DestinationString]; struct _UNICODE_STRING *
0x18005bc0c  mov     rcx, rsi; struct _DOMAIN_INFO *
0x18005bc0f  lea     r8d, [r9+11h]; unsigned int
0x18005bc13  call    ?NlFindNamedClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@KPEAE@Z; NlFindNamedClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,ulong,uchar *)
0x18005bc18  mov     rdi, rax
0x18005bc1b  test    rax, rax
0x18005bc1e  jnz     loc_18005BFFD
0x18005bc24  jmp     loc_18005BA2B
0x18005bc29  lea     r8, aNetlogonContro_2; "NETLOGON_CONTROL_REDISCOVER function re"...
0x18005bc30  mov     rdx, rsi; struct _DOMAIN_INFO *
0x18005bc33  mov     ecx, 200h; unsigned int
0x18005bc38  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005bc3d  cmp     [rbx], r14
0x18005bc40  jnz     short loc_18005BC5B
0x18005bc42  mov     r8d, 163Bh; unsigned int
0x18005bc48  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005bc4f  lea     rcx, aInputdataTrust; "InputData->TrustedDomainName != NULL"
0x18005bc56  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005bc5b  mov     rcx, [rbx]; Str
0x18005bc5e  test    rcx, rcx
0x18005bc61  jnz     short loc_18005BC6F
  ... truncated ...
```
