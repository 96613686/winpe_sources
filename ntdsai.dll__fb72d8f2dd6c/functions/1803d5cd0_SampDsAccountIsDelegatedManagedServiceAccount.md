# SampDsAccountIsDelegatedManagedServiceAccount

- ea: `0x1803d5cd0`
- end: `0x1803d6df9`
- name: `SampDsAccountIsDelegatedManagedServiceAccount`
- size: `4393`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180030af8`
- `0x180030d80`
- `0x180030e34`
- `0x18003dc50`
- `0x180102874`
- `0x18012378c`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803c23c4`
- `0x1803d5cd0`
- `0x1803d6f14`
- `0x1803dd5d8`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1803d6731`
- `RPCRT4!RpcRevertToSelf` at `0x1803d6731`
- `RPCRT4!RpcImpersonateClient` at `0x1803d65ea`
- `RPCRT4!RpcImpersonateClient` at `0x1803d65ea`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1803d6861`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1803d6861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803d686f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803d6acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803d6c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803d686f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803d6acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803d6c5d`
- `AUTHZ!AuthzFreeContext` at `0x1803d6dbc`
- `AUTHZ!AuthzFreeContext` at `0x180476b9d`
- `AUTHZ!AuthzFreeContext` at `0x1803d6dbc`
- `AUTHZ!AuthzFreeContext` at `0x180476b9d`
- `AUTHZ!AuthzAccessCheck` at `0x1803d6c4f`
- `AUTHZ!AuthzAccessCheck` at `0x1803d6c4f`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x1803d6abe`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x1803d6abe`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1803d6aae`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1803d6aae`
- `ntdll!NtOpenThreadToken` at `0x1803d6724`
- `ntdll!NtOpenThreadToken` at `0x1803d6724`
- `ntdll!NtClose` at `0x1803d6dcf`
- `ntdll!NtClose` at `0x180476bb0`
- `ntdll!NtClose` at `0x1803d6dcf`
- `ntdll!NtClose` at `0x180476bb0`
- `ntdll!RtlInitUnicodeString` at `0x1803d5fcb`
- `ntdll!RtlInitUnicodeString` at `0x1803d5fcb`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1803d64c9`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1803d64c9`

## pseudocode

```c
__int64 __fastcall SampDsAccountIsDelegatedManagedServiceAccount(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        int *a3,
        BOOL *a4)
{
  struct _DSNAME *v5; // rdi
  __int64 v6; // r13
  unsigned int v7; // r15d
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // edi
  BOOL v11; // r14d
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // edi
  BOOL v16; // r14d
  __int64 v17; // rbx
  int LastError; // r14d
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // edi
  BOOL v22; // r15d
  int v23; // edi
  struct _DSNAME *v24; // r12
  __int64 v25; // rdx
  __int64 v26; // rcx
  BOOL v27; // r15d
  __int64 i; // rdx
  _DWORD *v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rcx
  BOOL v32; // r15d
  int v33; // edx
  int v34; // r8d
  int v35; // r9d
  unsigned int j; // edx
  int v37; // r12d
  __int64 v38; // rax
  void *v39; // rbx
  ULONG v40; // edx
  __int64 v41; // rdx
  __int64 v42; // rcx
  BOOL v43; // r14d
  __int64 v44; // rdx
  __int64 v45; // rcx
  BOOL v46; // r15d
  __int16 v47; // cx
  int v48; // edx
  __int64 v49; // rdx
  __int64 v50; // rcx
  BOOL v51; // r15d
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // rcx
  int v55; // r15d
  __int64 v56; // rdx
  __int64 v57; // rcx
  BOOL v58; // r14d
  BOOL v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  BOOL v62; // r15d
  __int64 v63; // rdx
  __int64 v64; // rcx
  BOOL v65; // r15d
  BOOL v66; // ebx
  PCWSTR SourceString; // [rsp+70h] [rbp-198h] BYREF
  int v68; // [rsp+78h] [rbp-190h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+80h] [rbp-188h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-180h] BYREF
  struct _DSNAME *v71; // [rsp+90h] [rbp-178h] BYREF
  int v72; // [rsp+98h] [rbp-170h]
  DWORD cbSid; // [rsp+9Ch] [rbp-16Ch] BYREF
  _DWORD v74[2]; // [rsp+A0h] [rbp-168h] BYREF
  __int64 v75; // [rsp+A8h] [rbp-160h]
  int v76; // [rsp+B0h] [rbp-158h]
  int v77; // [rsp+B4h] [rbp-154h]
  int *v78; // [rsp+B8h] [rbp-150h]
  BOOL *v79; // [rsp+C0h] [rbp-148h]
  int *v80; // [rsp+C8h] [rbp-140h]
  BOOL *v81; // [rsp+D0h] [rbp-138h]
  _QWORD v82[2]; // [rsp+D8h] [rbp-130h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+E8h] [rbp-120h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+108h] [rbp-100h] BYREF
  int v85; // [rsp+118h] [rbp-F0h] BYREF
  __int64 v86; // [rsp+120h] [rbp-E8h]
  int v87; // [rsp+128h] [rbp-E0h] BYREF
  __int64 v88; // [rsp+130h] [rbp-D8h]
  _DWORD v89[4]; // [rsp+138h] [rbp-D0h] BYREF
  int *v90; // [rsp+148h] [rbp-C0h]
  int v91; // [rsp+150h] [rbp-B8h]
  int v92; // [rsp+158h] [rbp-B0h]
  int *v93; // [rsp+160h] [rbp-A8h]
  __int64 v94; // [rsp+168h] [rbp-A0h]
  __int64 v95; // [rsp+170h] [rbp-98h]
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+178h] [rbp-90h] BYREF
  _OWORD pSid[2]; // [rsp+1A0h] [rbp-68h] BYREF

  v79 = a4;
  v78 = a3;
  v75 = (__int64)a2;
  v80 = a3;
  v81 = a4;
  pSid[0] = 0;
  v5 = qword_18052B2C0;
  v6 = 0;
  v71 = 0;
  TokenHandle = 0;
  hAuthzClientContext = 0;
  DestinationString = 0;
  SourceString = 0;
  *a3 = 0;
  *a4 = 0;
  v7 = SampMaybeBeginDsTransaction(0);
  if ( (v7 & 0x80000000) != 0 )
  {
    if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
      && !(unsigned int)THStateCheckForTraceOverride(v9, v8)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
    {
      if ( !gfTraceToSecondProvider )
        return v7;
      if ( !(unsigned int)THStateCheckForTraceOverride(v9, v8) )
      {
        if ( (unsigned int)ThStateCheckIfTraceToSecondProvier() )
        {
          v10 = 1;
          if ( (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13) )
            goto LABEL_11;
        }
        return v7;
      }
    }
    v10 = 1;
LABEL_11:
    v11 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v9, v8)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
    if ( !(unsigned int)THStateCheckForTraceOverride(v9, v8)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
    {
      v10 = 0;
    }
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      520421630,
      2,
      13,
      v10,
      v11,
      15,
      (__int64)&WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids);
    return v7;
  }
  if ( (unsigned int)DnsDomainFromDSName(v5, &SourceString) )
  {
    if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
      && !(unsigned int)THStateCheckForTraceOverride(v14, v13)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
    {
      if ( !gfTraceToSecondProvider )
        goto LABEL_42;
      if ( !(unsigned int)THStateCheckForTraceOverride(v14, v13) )
      {
        if ( (unsigned int)ThStateCheckIfTraceToSecondProvier() )
        {
          v15 = 1;
          if ( (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13) )
            goto LABEL_32;
        }
LABEL_42:
        SampMaybeEndDsTransaction(2);
        return 3221225524LL;
      }
    }
    v15 = 1;
LABEL_32:
    v16 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v14, v13)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
    if ( !(unsigned int)THStateCheckForTraceOverride(v14, v13)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
    {
      v15 = 0;
    }
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      520421645,
      2,
      13,
      v15,
      v16,
      16,
      &WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids);
    goto LABEL_42;
  }
  v17 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  LastError = SampLookupUserByUPNOrAccountName(v5, &DestinationString, a2, &v71);
  if ( LastError < 0 )
  {
    if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
      && !(unsigned int)THStateCheckForTraceOverride(v20, v19)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
    {
      if ( !gfTraceToSecondProvider )
        goto LABEL_256;
      if ( !(unsigned int)THStateCheckForTraceOverride(v20, v19) )
      {
        if ( (unsigned int)ThStateCheckIfTraceToSecondProvier() )
        {
          v21 = 1;
          if ( (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13) )
            goto LABEL_53;
        }
LABEL_256:
        v37 = 0;
        goto LABEL_257;
      }
    }
    v21 = 1;
LABEL_53:
    v22 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v20, v19)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
    if ( !(unsigned int)THStateCheckForTraceOverride(v20, v19)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
    {
      v21 = 0;
    }
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      520421669,
      2,
      13,
      v21,
      v22,
      17,
      &WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids,
      (__int64)a2,
      LastError);
    goto LABEL_256;
  }
  v76 = 112;
  v77 = 143;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89[0] = 112;
  v23 = 1;
  v89[2] = 1;
  v90 = &v85;
  v91 = 143;
  v92 = 1;
  v93 = &v87;
  v82[0] = 2;
  v82[1] = v89;
  v24 = v71;
  LastError = SampDsReadWithClaims(v71, 0, 4, v82, 0, pSid);
  if ( LastError < 0 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v26, v25)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v26, v25)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v27 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v26, v25)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride(v26, v25)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
      {
        v23 = 0;
      }
      WPP_SF__DS_NAME_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520421700,
        2,
        13,
        v23,
        v27,
        18,
        &WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids,
        (__int64)v24,
        LastError);
    }
    goto LABEL_256;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v72 = i;
    if ( (unsigned int)i >= LODWORD(pSid[0]) )
      break;
    v29 = (_DWORD *)(*((_QWORD *)&pSid[0] + 1) + 24 * i);
    if ( *v29 == 112 )
    {
      v17 = *((_QWORD *)&pSid[0] + 1) + 24 * i;
      v95 = v17;
    }
    else if ( *v29 == 143 )
    {
      v6 = *((_QWORD *)&pSid[0] + 1) + 24 * i;
      v94 = v6;
    }
  }
  if ( !v17 )
  {
    LastError = -1073741811;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v31, v30)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v32 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride(v31, v30)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
      {
        v23 = 0;
      }
      WPP_SF__DS_NAME_dqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, v34, v35, v23, v32, 0);
    }
    goto LABEL_256;
  }
  for ( j = 0; ; ++j )
  {
    v74[1] = j;
    if ( j >= *(_DWORD *)(v17 + 8) )
      goto LABEL_256;
    if ( **(_DWORD **)(*(_QWORD *)(v17 + 16) + 16LL * j + 8) == 655662 )
      break;
  }
  v37 = 1;
  if ( !v6 )
    goto LABEL_257;
  v38 = *(_QWORD *)(v6 + 16);
  v39 = *(void **)(v38 + 8);
  v40 = *(_DWORD *)v38;
  memset(&pRequest, 0, sizeof(pRequest));
  memset(&pReply, 0, sizeof(pReply));
  v74[0] = 0;
  LODWORD(v71) = 0;
  SourceString = 0;
  if ( !RtlValidRelativeSecurityDescriptor(v39, v40, 5u) )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
      || (unsigned int)THStateCheckForTraceOverride(v42, v41)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
    {
      v43 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride(v42, v41)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13) )
      {
        v23 = 0;
      }
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520421770,
        3,
        13,
        v23,
        v43,
        20,
        &WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids,
        v75);
    }
    LastError = -1073741703;
    goto LABEL_257;
  }
  LastError = RpcImpersonateClient(0);
  if ( LastError )
  {
    if ( !(unsigned int)IncrementWPPPerfCountersForLevel(3)
      && !(unsigned int)THStateCheckForTraceOverride(v45, v44)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
      && (!gfTraceToSecondProvider
       || !(unsigned int)THStateCheckForTraceOverride(v45, v44)
       && (!(unsigned int)ThStateCheckIfTraceToSecondProvier()
        || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13))) )
    {
      goto LABEL_149;
    }
    v46 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v45, v44)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
    if ( !(unsigned int)THStateCheckForTraceOverride(v45, v44)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13) )
    {
      v23 = 0;
    }
    v47 = 21;
    v48 = 520421783;
LABEL_148:
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v48,
      3,
      13,
      v23,
      v46,
      v47,
      (__int64)&WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids);
LABEL_149:
    if ( LastError <= 0 )
      goto LABEL_257;
    LastError = (unsigned __int16)LastError;
    goto LABEL_151;
  }
  LastError = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  RpcRevertToSelf();
  if ( LastError < 0 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
      || (unsigned int)THStateCheckForTraceOverride(v50, v49)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v50, v49)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
    {
      v51 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v50, v49)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride(v50, v49)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13) )
      {
        v23 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520421799,
        3,
        13,
        v23,
        v51,
        22,
        &WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids);
    }
    goto LABEL_257;
  }
  cbSid = 28;
  v68 = 0;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
    LastError = GetLastError();
    if ( !(unsigned int)IncrementWPPPerfCountersForLevel(3)
      && !(unsigned int)THStateCheckForTraceOverride(v54, v53)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
      && (!gfTraceToSecondProvider
       || !(unsigned int)THStateCheckForTraceOverride(v54, v53)
       && (!(unsigned int)ThStateCheckIfTraceToSecondProvier()
        || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13))) )
    {
      goto LABEL_149;
    }
    v46 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v54, v53)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
    if ( !(unsigned int)THStateCheckForTraceOverride(v54, v53)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13) )
    {
      v23 = 0;
    }
    v47 = 23;
    v48 = 520421817;
    goto LABEL_148;
  }
  v55 = SidMatchesUserSidInSuppliedToken(TokenHandle, pSid, v52, &v68);
  if ( !v55 )
  {
    if ( v68 )
      v59 = AuthzInitializeContextFromSid(
              0,
              (PSID)(qword_18052B430 + 24),
              ghAuthzRM,
              0,
              (LUID)SourceString,
              0,
              &hAuthzClientContext);
    else
      v59 = AuthzInitializeContextFromToken(0, TokenHandle, ghAuthzRM, 0, (LUID)SourceString, 0, &hAuthzClientContext);
    if ( !v59 )
    {
      LastError = GetLastError();
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v61, v60)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v61, v60)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v62 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v61, v60)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( !(unsigned int)THStateCheckForTraceOverride(v61, v60)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
        {
          v23 = 0;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          520421869,
          2,
          13,
          v23,
          v62,
          25,
          (__int64)&WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0xC0070000;
      goto LABEL_257;
    }
    pRequest.DesiredAccess = 16;
    pReply.ResultListLength = 1;
    pReply.Error = v74;
    pReply.GrantedAccessMask = (PACCESS_MASK)&v71;
    if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, v39, 0, 0, &pReply, 0) )
    {
      v66 = !*pReply.Error && (*(_BYTE *)pReply.GrantedAccessMask & 0x10) != 0;
      goto LABEL_258;
    }
    LastError = GetLastError();
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
      || (unsigned int)THStateCheckForTraceOverride(v64, v63)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
    {
      v65 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride(v64, v63)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13) )
      {
        v23 = 0;
      }
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520421900,
        3,
        13,
        v23,
        v65,
        26,
        &WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids,
        v75,
        LastError);
    }
    goto LABEL_149;
  }
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
    || (unsigned int)THStateCheckForTraceOverride(v57, v56)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v57, v56)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
  {
    v58 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v57, v56)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
    if ( !(unsigned int)THStateCheckForTraceOverride(v57, v56)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13) )
    {
      v23 = 0;
    }
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      520421835,
      3,
      13,
      v23,
      v58,
      24,
      (__int64)&WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids);
  }
  if ( v55 > 0 )
  {
    LastError = (unsigned __int16)v55;
LABEL_151:
    LastError |= 0xC0070000;
    goto LABEL_257;
  }
  LastError = v55;
LABEL_257:
  v66 = 0;
LABEL_258:
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  if ( TokenHandle )
    NtClose(TokenHandle);
  SampMaybeEndDsTransaction(3);
  *v78 = v37;
  *v79 = v66;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1803d5cd0  mov     r11, rsp
0x1803d5cd3  push    rbx
0x1803d5cd4  push    rsi
0x1803d5cd5  push    rdi
0x1803d5cd6  push    r12
0x1803d5cd8  push    r13
0x1803d5cda  push    r14
0x1803d5cdc  push    r15
0x1803d5cde  sub     rsp, 1D0h
0x1803d5ce5  mov     rax, cs:__security_cookie
0x1803d5cec  xor     rax, rsp
0x1803d5cef  mov     [rsp+208h+var_48], rax
0x1803d5cf7  mov     [rsp+208h+var_148], r9
0x1803d5cff  mov     rax, r8
0x1803d5d02  mov     [rsp+208h+var_150], rax
0x1803d5d0a  mov     r12, rdx
0x1803d5d0d  mov     [rsp+208h+var_160], rdx
0x1803d5d15  mov     [rsp+208h+var_140], rax
0x1803d5d1d  mov     [rsp+208h+var_138], r9
0x1803d5d25  xorps   xmm0, xmm0
0x1803d5d28  movups  xmmword ptr [r11-68h], xmm0
0x1803d5d2d  mov     rdi, cs:qword_18052B2C0
0x1803d5d34  xor     r13d, r13d
0x1803d5d37  mov     [r11-178h], r13
0x1803d5d3e  mov     [r11-180h], r13
0x1803d5d45  mov     [r11-188h], r13
0x1803d5d4c  movups  xmmword ptr [rsp+208h+DestinationString.Length], xmm0
0x1803d5d54  mov     [rsp+208h+SourceString], r13
0x1803d5d59  mov     [r8], r13d
0x1803d5d5c  mov     [r9], r13d
0x1803d5d5f  xor     ecx, ecx
0x1803d5d61  call    SampMaybeBeginDsTransaction
0x1803d5d66  mov     r15d, eax
0x1803d5d69  test    eax, eax
0x1803d5d6b  jns     loc_1803D5E95
0x1803d5d71  lea     esi, [r13+2]
0x1803d5d75  mov     ecx, esi
0x1803d5d77  call    IncrementWPPPerfCountersForLevel
0x1803d5d7c  test    eax, eax
0x1803d5d7e  jnz     short loc_1803D5DD9
0x1803d5d80  call    THStateCheckForTraceOverride
0x1803d5d85  test    eax, eax
0x1803d5d87  jnz     short loc_1803D5DD9
0x1803d5d89  lea     ebx, [rsi+0Bh]
0x1803d5d8c  mov     r8d, ebx
0x1803d5d8f  mov     edx, esi
0x1803d5d91  xor     ecx, ecx
0x1803d5d93  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d5d98  test    eax, eax
0x1803d5d9a  jnz     short loc_1803D5DDE
0x1803d5d9c  mov     eax, cs:gfTraceToSecondProvider
0x1803d5da2  test    eax, eax
0x1803d5da4  jz      loc_1803D5E6F
0x1803d5daa  call    THStateCheckForTraceOverride
0x1803d5daf  test    eax, eax
0x1803d5db1  jnz     short loc_1803D5DDE
0x1803d5db3  call    ThStateCheckIfTraceToSecondProvier
0x1803d5db8  test    eax, eax
0x1803d5dba  jz      loc_1803D5E6F
0x1803d5dc0  mov     r8d, ebx
0x1803d5dc3  mov     edx, esi
0x1803d5dc5  lea     edi, [rsi-1]
0x1803d5dc8  mov     ecx, edi
0x1803d5dca  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d5dcf  test    eax, eax
0x1803d5dd1  jz      loc_1803D5E6F
0x1803d5dd7  jmp     short loc_1803D5DE3
0x1803d5dd9  mov     ebx, 0Dh
0x1803d5dde  mov     edi, 1
0x1803d5de3  mov     eax, cs:gfTraceToSecondProvider
0x1803d5de9  test    eax, eax
0x1803d5deb  jz      short loc_1803D5E14
0x1803d5ded  call    THStateCheckForTraceOverride
0x1803d5df2  test    eax, eax
0x1803d5df4  jnz     short loc_1803D5E0F
0x1803d5df6  call    ThStateCheckIfTraceToSecondProvier
0x1803d5dfb  test    eax, eax
0x1803d5dfd  jz      short loc_1803D5E14
0x1803d5dff  mov     r8d, ebx
0x1803d5e02  mov     edx, esi
0x1803d5e04  mov     ecx, edi
0x1803d5e06  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d5e0b  test    eax, eax
0x1803d5e0d  jz      short loc_1803D5E14
0x1803d5e0f  mov     r14d, edi
0x1803d5e12  jmp     short loc_1803D5E17
0x1803d5e14  mov     r14d, r13d
0x1803d5e17  call    THStateCheckForTraceOverride
0x1803d5e1c  test    eax, eax
0x1803d5e1e  jnz     short loc_1803D5E33
0x1803d5e20  mov     r8d, ebx
0x1803d5e23  mov     edx, esi
0x1803d5e25  xor     ecx, ecx
0x1803d5e27  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d5e2c  test    eax, eax
0x1803d5e2e  jnz     short loc_1803D5E33
0x1803d5e30  mov     edi, r13d
0x1803d5e33  mov     dword ptr [rsp+208h+phAccessCheckResults], r15d
0x1803d5e38  lea     rax, WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids
0x1803d5e3f  mov     [rsp+208h+pReply], rax
0x1803d5e44  mov     word ptr [rsp+208h+phAuthzClientContext], 0Fh
0x1803d5e4b  mov     dword ptr [rsp+208h+DynamicGroupArgs], r14d
0x1803d5e50  mov     [rsp+208h+Identifier.LowPart], edi
0x1803d5e54  mov     r9d, ebx
0x1803d5e57  mov     r8d, esi
0x1803d5e5a  mov     edx, 1F0500FEh
0x1803d5e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1803d5e66  mov     rcx, [rcx+10h]
0x1803d5e6a  call    WPP_SF__ATTRTYP_LOG_
0x1803d5e6f  mov     eax, r15d
0x1803d5e72  mov     rcx, [rsp+208h+var_48]
0x1803d5e7a  xor     rcx, rsp; StackCookie
0x1803d5e7d  call    __security_check_cookie
0x1803d5e82  add     rsp, 1D0h
0x1803d5e89  pop     r15
0x1803d5e8b  pop     r14
0x1803d5e8d  pop     r13
0x1803d5e8f  pop     r12
0x1803d5e91  pop     rdi
0x1803d5e92  pop     rsi
0x1803d5e93  pop     rbx
0x1803d5e94  retn
0x1803d5e95  lea     rdx, [rsp+208h+SourceString]
0x1803d5e9a  mov     rcx, rdi
0x1803d5e9d  call    DnsDomainFromDSName
0x1803d5ea2  test    eax, eax
0x1803d5ea4  jz      loc_1803D5FB4
0x1803d5eaa  mov     esi, 2
0x1803d5eaf  mov     ecx, esi
0x1803d5eb1  call    IncrementWPPPerfCountersForLevel
0x1803d5eb6  test    eax, eax
0x1803d5eb8  jnz     short loc_1803D5F13
0x1803d5eba  call    THStateCheckForTraceOverride
0x1803d5ebf  test    eax, eax
0x1803d5ec1  jnz     short loc_1803D5F13
0x1803d5ec3  lea     ebx, [rsi+0Bh]
0x1803d5ec6  mov     r8d, ebx
0x1803d5ec9  mov     edx, esi
0x1803d5ecb  xor     ecx, ecx
0x1803d5ecd  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d5ed2  test    eax, eax
0x1803d5ed4  jnz     short loc_1803D5F18
0x1803d5ed6  mov     eax, cs:gfTraceToSecondProvider
0x1803d5edc  test    eax, eax
0x1803d5ede  jz      loc_1803D5FA3
0x1803d5ee4  call    THStateCheckForTraceOverride
0x1803d5ee9  test    eax, eax
0x1803d5eeb  jnz     short loc_1803D5F18
0x1803d5eed  call    ThStateCheckIfTraceToSecondProvier
0x1803d5ef2  test    eax, eax
0x1803d5ef4  jz      loc_1803D5FA3
0x1803d5efa  mov     r8d, ebx
0x1803d5efd  mov     edx, esi
0x1803d5eff  lea     edi, [rsi-1]
0x1803d5f02  mov     ecx, edi
0x1803d5f04  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d5f09  test    eax, eax
0x1803d5f0b  jz      loc_1803D5FA3
0x1803d5f11  jmp     short loc_1803D5F1D
0x1803d5f13  mov     ebx, 0Dh
0x1803d5f18  mov     edi, 1
0x1803d5f1d  mov     eax, cs:gfTraceToSecondProvider
0x1803d5f23  test    eax, eax
0x1803d5f25  jz      short loc_1803D5F4E
0x1803d5f27  call    THStateCheckForTraceOverride
0x1803d5f2c  test    eax, eax
0x1803d5f2e  jnz     short loc_1803D5F49
0x1803d5f30  call    ThStateCheckIfTraceToSecondProvier
0x1803d5f35  test    eax, eax
0x1803d5f37  jz      short loc_1803D5F4E
0x1803d5f39  mov     r8d, ebx
0x1803d5f3c  mov     edx, esi
0x1803d5f3e  mov     ecx, edi
0x1803d5f40  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d5f45  test    eax, eax
0x1803d5f47  jz      short loc_1803D5F4E
0x1803d5f49  mov     r14d, edi
0x1803d5f4c  jmp     short loc_1803D5F51
0x1803d5f4e  xor     r14d, r14d
0x1803d5f51  call    THStateCheckForTraceOverride
0x1803d5f56  test    eax, eax
0x1803d5f58  jnz     short loc_1803D5F6C
0x1803d5f5a  mov     r8d, ebx
0x1803d5f5d  mov     edx, esi
0x1803d5f5f  xor     ecx, ecx
0x1803d5f61  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d5f66  test    eax, eax
0x1803d5f68  jnz     short loc_1803D5F6C
0x1803d5f6a  xor     edi, edi
0x1803d5f6c  lea     rax, WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids
0x1803d5f73  mov     [rsp+208h+pReply], rax; LPCGUID
0x1803d5f78  mov     word ptr [rsp+208h+phAuthzClientContext], 10h; __int16
0x1803d5f7f  mov     dword ptr [rsp+208h+DynamicGroupArgs], r14d; int
0x1803d5f84  mov     [rsp+208h+Identifier.LowPart], edi; int
0x1803d5f88  mov     r9d, ebx; int
0x1803d5f8b  mov     r8d, esi; int
0x1803d5f8e  mov     edx, 1F05010Dh; int
0x1803d5f93  mov     rcx, cs:WPP_GLOBAL_Control
0x1803d5f9a  mov     rcx, [rcx+10h]; int
0x1803d5f9e  call    WPP_SF_
0x1803d5fa3  mov     ecx, esi
0x1803d5fa5  call    SampMaybeEndDsTransaction
0x1803d5faa  mov     eax, 0C0000034h
0x1803d5faf  jmp     loc_1803D5E72
0x1803d5fb4  xor     ebx, ebx
0x1803d5fb6  mov     [rsp+208h+var_1A4], ebx
0x1803d5fba  mov     [rsp+208h+var_1A8], ebx
0x1803d5fbe  mov     rdx, [rsp+208h+SourceString]; SourceString
0x1803d5fc3  lea     rcx, [rsp+208h+DestinationString]; DestinationString
0x1803d5fcb  call    cs:__imp_RtlInitUnicodeString
0x1803d5fd1  nop
0x1803d5fd2  lea     r9, [rsp+208h+var_178]; struct _DSNAME **
0x1803d5fda  mov     r8, r12; struct _UNICODE_STRING *
0x1803d5fdd  lea     rdx, [rsp+208h+DestinationString]; struct _UNICODE_STRING *
0x1803d5fe5  mov     rcx, rdi; struct _DSNAME *
0x1803d5fe8  call    ?SampLookupUserByUPNOrAccountName@@YAJPEAU_DSNAME@@PEAU_UNICODE_STRING@@1PEAPEAU1@@Z; SampLookupUserByUPNOrAccountName(_DSNAME *,_UNICODE_STRING *,_UNICODE_STRING *,_DSNAME * *)
0x1803d5fed  mov     r14d, eax
0x1803d5ff0  mov     [rsp+208h+var_1A0], eax
0x1803d5ff4  test    eax, eax
0x1803d5ff6  jns     loc_1803D6105
0x1803d5ffc  lea     esi, [rbx+2]
0x1803d5fff  mov     ecx, esi
0x1803d6001  call    IncrementWPPPerfCountersForLevel
0x1803d6006  test    eax, eax
0x1803d6008  jnz     short loc_1803D6063
0x1803d600a  call    THStateCheckForTraceOverride
0x1803d600f  test    eax, eax
0x1803d6011  jnz     short loc_1803D6063
0x1803d6013  lea     ebx, [rsi+0Bh]
0x1803d6016  mov     r8d, ebx
0x1803d6019  mov     edx, esi
0x1803d601b  xor     ecx, ecx
0x1803d601d  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d6022  test    eax, eax
0x1803d6024  jnz     short loc_1803D6068
0x1803d6026  mov     eax, cs:gfTraceToSecondProvider
0x1803d602c  test    eax, eax
0x1803d602e  jz      loc_1803D6DA1
0x1803d6034  call    THStateCheckForTraceOverride
0x1803d6039  test    eax, eax
0x1803d603b  jnz     short loc_1803D6068
0x1803d603d  call    ThStateCheckIfTraceToSecondProvier
0x1803d6042  test    eax, eax
0x1803d6044  jz      loc_1803D6DA1
0x1803d604a  mov     r8d, ebx
0x1803d604d  mov     edx, esi
0x1803d604f  lea     edi, [rsi-1]
0x1803d6052  mov     ecx, edi
0x1803d6054  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d6059  test    eax, eax
0x1803d605b  jz      loc_1803D6DA1
0x1803d6061  jmp     short loc_1803D606D
0x1803d6063  mov     ebx, 0Dh
0x1803d6068  mov     edi, 1
0x1803d606d  mov     eax, cs:gfTraceToSecondProvider
0x1803d6073  test    eax, eax
0x1803d6075  jz      short loc_1803D609E
0x1803d6077  call    THStateCheckForTraceOverride
0x1803d607c  test    eax, eax
0x1803d607e  jnz     short loc_1803D6099
0x1803d6080  call    ThStateCheckIfTraceToSecondProvier
0x1803d6085  test    eax, eax
0x1803d6087  jz      short loc_1803D609E
0x1803d6089  mov     r8d, ebx
0x1803d608c  mov     edx, esi
0x1803d608e  mov     ecx, edi
0x1803d6090  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d6095  test    eax, eax
0x1803d6097  jz      short loc_1803D609E
0x1803d6099  mov     r15d, edi
0x1803d609c  jmp     short loc_1803D60A1
0x1803d609e  xor     r15d, r15d
0x1803d60a1  call    THStateCheckForTraceOverride
0x1803d60a6  test    eax, eax
0x1803d60a8  jnz     short loc_1803D60BC
0x1803d60aa  mov     r8d, ebx
0x1803d60ad  mov     edx, esi
0x1803d60af  xor     ecx, ecx
0x1803d60b1  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d60b6  test    eax, eax
0x1803d60b8  jnz     short loc_1803D60BC
0x1803d60ba  xor     edi, edi
0x1803d60bc  mov     ecx, 11h
0x1803d60c1  mov     dword ptr [rsp+208h+var_1C0], r14d; char
0x1803d60c6  mov     [rsp+208h+phAccessCheckResults], r12; __int64
0x1803d60cb  lea     rax, WPP_9a7efa1386f63a4a9ca71a4aa63a86d8_Traceguids
0x1803d60d2  mov     [rsp+208h+pReply], rax; LPCGUID
0x1803d60d7  mov     word ptr [rsp+208h+phAuthzClientContext], cx; __int16
0x1803d60dc  mov     dword ptr [rsp+208h+DynamicGroupArgs], r15d; int
0x1803d60e1  mov     [rsp+208h+Identifier.LowPart], edi; int
0x1803d60e5  mov     r9d, ebx; int
0x1803d60e8  mov     r8d, esi; int
0x1803d60eb  mov     edx, 1F050125h; int
0x1803d60f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1803d60f7  mov     rcx, [rcx+10h]; int
0x1803d60fb  call    WPP_SF_Zd
0x1803d6100  jmp     loc_1803D6DA1
0x1803d6105  mov     r15d, 70h ; 'p'
0x1803d610b  mov     [rsp+208h+var_158], r15d
0x1803d6113  lea     ecx, [r15+1Fh]
  ... truncated ...
```
