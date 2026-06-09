# SampDsValidateComputerAccountReuseAttempt

- ea: `0x1803f8760`
- end: `0x1803fa46e`
- name: `SampDsValidateComputerAccountReuseAttempt`
- size: `7438`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180030af8`
- `0x180030b60`
- `0x18003dc50`
- `0x18003dd78`
- `0x18003de48`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803b2bc4`
- `0x1803b4fc4`
- `0x1803dc57c`
- `0x1803f39bc`
- `0x1803f44f8`
- `0x1803f4a94`
- `0x1803f8760`
- `0x180410934`
- `0x1804119b4`
- `0x180411d34`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803f890f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803f9958`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803fa370`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803fa39d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803f890f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803f9958`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803fa370`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1803fa39d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f9758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fa09b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803f9758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fa09b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fa40d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fa41c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fa42b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fa40d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fa41c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803fa42b`
- `AUTHZ!AuthzFreeContext` at `0x1803fa3fe`
- `AUTHZ!AuthzFreeContext` at `0x1803fa3fe`
- `AUTHZ!AuthzAccessCheck` at `0x1803fa08d`
- `AUTHZ!AuthzAccessCheck` at `0x1803fa08d`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1803f9745`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1803f9745`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1803f8c7e`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1803f8c7e`
- `ntdll!RtlInitUnicodeString` at `0x1803f8928`
- `ntdll!RtlInitUnicodeString` at `0x1803f8e74`
- `ntdll!RtlInitUnicodeString` at `0x1803fa389`
- `ntdll!RtlInitUnicodeString` at `0x1803fa3b6`
- `ntdll!RtlInitUnicodeString` at `0x1803f8928`
- `ntdll!RtlInitUnicodeString` at `0x1803f8e74`
- `ntdll!RtlInitUnicodeString` at `0x1803fa389`
- `ntdll!RtlInitUnicodeString` at `0x1803fa3b6`
- `ntdll!RtlEqualSid` at `0x1803f9282`
- `ntdll!RtlEqualSid` at `0x1803f9487`
- `ntdll!RtlEqualSid` at `0x1803f9282`
- `ntdll!RtlEqualSid` at `0x1803f9487`
- `SAMSRV!SampWriteEventLog` at `0x1803f8e90`
- `SAMSRV!SampWriteEventLog` at `0x1803fa3ee`
- `SAMSRV!SampWriteEventLog` at `0x1803f8e90`
- `SAMSRV!SampWriteEventLog` at `0x1803fa3ee`

## pseudocode

```c
__int64 __fastcall SampDsValidateComputerAccountReuseAttempt(__int64 a1, void *a2, void *a3, int *a4)
{
  int v4; // edi
  int v7; // r13d
  int v8; // r15d
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // eax
  BOOL v13; // eax
  const WCHAR *v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  BOOL v17; // esi
  int v18; // eax
  int v19; // edx
  BOOL v20; // esi
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  BOOL v26; // esi
  int v27; // eax
  const WCHAR *v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rcx
  PSID v31; // rsi
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  PSID v37; // rsi
  int v38; // eax
  BOOL v39; // edi
  int v40; // eax
  PSID v41; // rsi
  __int64 v42; // rdx
  __int64 v43; // rcx
  BOOL v44; // edi
  int v45; // eax
  BOOL v46; // edi
  int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // rcx
  BOOL v50; // edi
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rcx
  BOOL v54; // edi
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rcx
  BOOL v58; // edi
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  DWORD LastError; // r14d
  __int64 v63; // rdx
  __int64 v64; // rcx
  PSID v65; // r15
  BOOL v66; // esi
  int v67; // eax
  __int64 v68; // rdx
  __int64 v69; // rcx
  BOOL v70; // esi
  int v71; // eax
  BOOL v72; // eax
  __int64 v73; // rdx
  __int64 v74; // rcx
  PSID v75; // r14
  BOOL v76; // esi
  int v77; // eax
  PSID v78; // r15
  BOOL v79; // esi
  int v80; // eax
  __int64 v81; // rdx
  __int64 v82; // rcx
  PSID v83; // r14
  BOOL v84; // esi
  int v85; // eax
  __int64 v86; // rdx
  __int64 v87; // rcx
  BOOL v88; // esi
  int v89; // eax
  BOOL v90; // edi
  int v91; // eax
  BOOL v92; // edi
  int v93; // eax
  __int64 v94; // rdx
  __int64 v95; // rcx
  BOOL v96; // esi
  int v97; // eax
  BOOL v98; // esi
  int v99; // eax
  BOOL v100; // edi
  int v101; // eax
  __int64 v102; // rdx
  __int64 v103; // rcx
  BOOL v104; // edi
  BOOL v105; // eax
  const WCHAR *v106; // rdx
  BOOL v107; // eax
  const WCHAR *v108; // rdx
  LUID Identifier; // [rsp+20h] [rbp-E0h]
  __int16 phAuthzClientContext; // [rsp+30h] [rbp-D0h]
  NTSTATUS ObjectSDAndClassId; // [rsp+50h] [rbp-B0h]
  unsigned __int8 OwnerDefaulted[4]; // [rsp+54h] [rbp-ACh] BYREF
  PSID Owner; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v115; // [rsp+60h] [rbp-A0h] BYREF
  int v116; // [rsp+68h] [rbp-98h] BYREF
  PSID Sid2; // [rsp+70h] [rbp-90h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+78h] [rbp-88h] BYREF
  LPWSTR v119; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v120; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v121; // [rsp+98h] [rbp-68h] BYREF
  int v122; // [rsp+9Ch] [rbp-64h] BYREF
  int v123; // [rsp+A0h] [rbp-60h] BYREF
  int v124; // [rsp+A4h] [rbp-5Ch] BYREF
  LPWSTR StringSid; // [rsp+A8h] [rbp-58h] BYREF
  LPWSTR v126; // [rsp+B0h] [rbp-50h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B8h] [rbp-48h] BYREF
  PSID Sid1; // [rsp+C0h] [rbp-40h] BYREF
  LUID v129; // [rsp+C8h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  int *v131; // [rsp+E0h] [rbp-20h]
  struct _UNICODE_STRING v132; // [rsp+E8h] [rbp-18h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+F8h] [rbp-8h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+120h] [rbp+20h] BYREF
  __int64 v135[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v136; // [rsp+150h] [rbp+50h]
  _BYTE v137[28]; // [rsp+160h] [rbp+60h] BYREF

  v4 = 0;
  v131 = a4;
  StringSid = 0;
  memset(v137, 0, sizeof(v137));
  SecurityDescriptor = 0;
  v7 = 0;
  v121 = 0;
  v8 = 0;
  v115 = 0;
  *(_OWORD *)v135 = 0;
  OwnerDefaulted[0] = 0;
  v136 = 0;
  v122 = 0;
  Sid2 = 0;
  DestinationString = 0;
  v126 = 0;
  v132 = 0;
  Sid1 = 0;
  Owner = 0;
  v119 = 0;
  v120 = 0;
  v116 = 0;
  v129 = 0;
  v123 = 0;
  v124 = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  hAuthzClientContext = 0;
  *a4 = 0;
  memset(&pReply, 0, sizeof(pReply));
  v11 = 1;
  if ( (unsigned int)THStateCheckForTraceOverride(0, a2)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v10, v9)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
  {
    if ( gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v10, v9)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
    {
      v4 = 1;
    }
    if ( (unsigned int)THStateCheckForTraceOverride(v10, v9)
      || (v12 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
    {
      v12 = 1;
    }
    WPP_SF__sid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      522719244,
      4,
      13,
      v12,
      v4,
      54,
      &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
      a2);
    v4 = 0;
  }
  v13 = ConvertSidToStringSidW(a2, &StringSid);
  v14 = StringSid;
  if ( !v13 )
    v14 = L"Unavailable";
  RtlInitUnicodeString(&DestinationString, v14);
  ObjectSDAndClassId = SampBuildDsNameFromSidNew(a2);
  if ( ObjectSDAndClassId < 0 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v16, v15)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v17 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
        || (v18 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
      {
        v18 = 1;
      }
      v19 = 522719265;
      phAuthzClientContext = 55;
LABEL_36:
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        2,
        13,
        v18,
        v17,
        phAuthzClientContext,
        (__int64)&WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
      goto LABEL_457;
    }
    goto LABEL_457;
  }
  ObjectSDAndClassId = SampMaybeBeginDsTransaction(0);
  if ( ObjectSDAndClassId < 0 )
    goto LABEL_457;
  v8 = 1;
  ObjectSDAndClassId = SampDsGetObjectSDAndClassId((struct _DSNAME *)v135, &SecurityDescriptor, &v121, &v115);
  if ( ObjectSDAndClassId >= 0 )
  {
    if ( v115 != 196638 )
    {
      ObjectSDAndClassId = -1073741811;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v16, v15)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v20 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (v21 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
        {
          v21 = 1;
        }
        WPP_SF__DS_NAME_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          522719307,
          2,
          13,
          v21,
          v20,
          57,
          &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
          (__int64)v135,
          13);
      }
      goto LABEL_457;
    }
    ObjectSDAndClassId = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, OwnerDefaulted);
    if ( ObjectSDAndClassId < 0 )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v16, v15)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v17 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (v18 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
        {
          v18 = 1;
        }
        v19 = 522719320;
        phAuthzClientContext = 58;
        goto LABEL_36;
      }
      goto LABEL_457;
    }
    if ( !Owner )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v25, v24)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v25, v24)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v26 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v25, v24)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v25, v24)
          || (v27 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
        {
          v27 = 1;
        }
        WPP_SF__sid_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          522719332,
          2,
          13,
          v27,
          v26,
          59,
          &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
          a2);
      }
      v28 = L"Empty owner";
LABEL_111:
      RtlInitUnicodeString(&v120, v28);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))SampWriteEventLog)(
        SAMMSG_COMPUTER_ACCOUNT_ORPHANED,
        L"uu",
        &DestinationString,
        &v120,
        Identifier);
      goto LABEL_457;
    }
    if ( (unsigned int)THStateCheckForTraceOverride(v23, v22)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
    {
      v31 = Owner;
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        v4 = 1;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v30, v29)
        || (v32 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
      {
        v32 = 1;
      }
      WPP_SF__sid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        522719348,
        4,
        13,
        v32,
        v4,
        60,
        &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
        v31);
      v4 = 0;
    }
    ObjectSDAndClassId = SampIsLocalSystemOrAnyKindOfAdminAccessGranted(&Sid2, &v122);
    if ( ObjectSDAndClassId < 0 )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v16, v15)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v17 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (v18 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
        {
          v18 = 1;
        }
        v19 = 522719367;
        phAuthzClientContext = 61;
        goto LABEL_36;
      }
      goto LABEL_457;
    }
    if ( (unsigned int)THStateCheckForTraceOverride(v34, v33)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v36, v35)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
    {
      v37 = Sid2;
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v36, v35)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
      {
        v4 = 1;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v36, v35)
        || (v38 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)) != 0 )
      {
        v38 = 1;
      }
      WPP_SF__sid_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        522719375,
        5,
        13,
        v38,
        v4,
        62,
        &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
        v37);
    }
    ObjectSDAndClassId = SampDsGetCreatorSidFromAccount((struct _DSNAME *)v135, &Sid1);
    if ( ObjectSDAndClassId < 0 )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v16, v15)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
      {
        v39 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (v40 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)) != 0 )
        {
          v40 = 1;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          522719394,
          3,
          13,
          v40,
          v39,
          63,
          (__int64)&WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
      }
      goto LABEL_457;
    }
    v41 = Sid1;
    if ( Sid1 )
    {
      if ( RtlEqualSid(Sid1, Sid2) )
      {
        if ( (unsigned int)THStateCheckForTraceOverride(v43, v42)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v44 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (v45 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v45 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719404,
            4,
            13,
            v45,
            v44,
            64,
            &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
        goto LABEL_196;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v43, v42)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        v46 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (v47 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
        {
          v47 = 1;
        }
        WPP_SF__sid_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          522719415,
          4,
          13,
          v47,
          v46,
          65,
          &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
          v41);
      }
    }
    else
    {
      if ( RtlEqualSid(Owner, Sid2) )
      {
        if ( (unsigned int)THStateCheckForTraceOverride(v49, v48)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v50 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (v51 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v51 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719434,
            4,
            13,
            v51,
            v50,
            66,
            &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
        goto LABEL_196;
      }
      if ( (unsigned int)SampIsSidAnyKindOfAdminGroup(Owner) )
      {
        if ( (unsigned int)THStateCheckForTraceOverride(v53, v52)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v54 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (v55 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v55 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719447,
            4,
            13,
            v55,
            v54,
            67,
            &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
        goto LABEL_196;
      }
      if ( (int)SampCheckTokenMembershipAnyClient(Owner) >= 0 )
      {
        if ( (unsigned int)THStateCheckForTraceOverride(v57, v56)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v58 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (v59 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v59 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719462,
            4,
            13,
            v59,
            v58,
            68,
            &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
        goto LABEL_196;
      }
      ObjectSDAndClassId = -1073741790;
      if ( !AuthzInitializeContextFromSid(0, Owner, ghAuthzRM, 0, v129, 0, &hAuthzClientContext) )
      {
        LastError = GetLastError();
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v64, v63)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v65 = Owner;
          v66 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v64, v63)
            || (v67 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
          {
            v67 = 1;
          }
          WPP_SF__sid_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719492,
            2,
            v67,
            v66,
            69,
            &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
            v65,
            LastError);
          v8 = 1;
        }
        if ( LastError == 1332 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v69, v68)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v69, v68)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
          {
            v70 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v69, v68)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
            if ( (unsigned int)THStateCheckForTraceOverride(v69, v68)
              || (v71 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
            {
              v71 = 1;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              522719502,
              2,
              13,
              v71,
              v70,
              70,
              &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
          }
          v72 = ConvertSidToStringSidW(Owner, &v119);
          v28 = v119;
          if ( !v72 )
            v28 = L"Unavailable";
          goto LABEL_111;
        }
        if ( (unsigned int)THStateCheckForTraceOverride(v64, v63)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v74, v73)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v75 = Owner;
          v76 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v74, v73)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v74, v73)
            || (v77 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v77 = 1;
          }
          WPP_SF__sid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719530,
            4,
            13,
            v77,
            v76,
            71,
            &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
            v75);
        }
        ObjectSDAndClassId = SampDsAuthzBuildContextManuallyForFSP(Owner, &hAuthzClientContext);
        if ( ObjectSDAndClassId < 0 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
          {
            v78 = Owner;
            v79 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
            if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
              || (v80 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
            {
              v80 = 1;
            }
            WPP_SF__sid_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              522719542,
              2,
              13,
              v80,
              v79,
              72,
              &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
              v78,
              ObjectSDAndClassId);
            v8 = 1;
          }
          goto LABEL_457;
        }
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v61, v60)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v82, v81)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        v83 = Owner;
        v84 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v82, v81)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v82, v81)
          || (v85 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
        {
          v85 = 1;
        }
        WPP_SF__sid_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          522719552,
          4,
          13,
          v85,
          v84,
          73,
          &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids,
          v83);
      }
      if ( (unsigned int)SampIsAuthzContextAnyKindOfAdmin(hAuthzClientContext, &v116) )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v88 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (v89 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
          {
            v89 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719566,
            2,
            13,
            v89,
            v88,
            74,
            (__int64)&WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
        goto LABEL_457;
      }
      if ( v116 )
      {
        if ( (unsigned int)THStateCheckForTraceOverride(v87, v86)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v90 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (v91 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v91 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719574,
            4,
            13,
            v91,
            v90,
            75,
            &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
        goto LABEL_196;
      }
      if ( a3 )
      {
        if ( (unsigned int)THStateCheckForTraceOverride(v87, v86)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v95, v94)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v96 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v95, v94)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v95, v94)
            || (v97 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v97 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719599,
            4,
            13,
            v97,
            v96,
            77,
            &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
        pReply.GrantedAccessMask = (PACCESS_MASK)&v123;
        pRequest.DesiredAccess = 0x20000;
        pReply.Error = (PDWORD)&v124;
        pRequest.OptionalArguments = 0;
        memset(&pRequest.PrincipalSelfSid, 0, 20);
        pReply.ResultListLength = 1;
        if ( !AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, a3, 0, 0, &pReply, 0) )
        {
          GetLastError();
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
          {
            v98 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
            if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
              || (v99 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
            {
              v99 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              522719628,
              2,
              13,
              v99,
              v98,
              78,
              (__int64)&WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
          }
          goto LABEL_457;
        }
        if ( *pReply.Error )
        {
          ObjectSDAndClassId = 0;
          goto LABEL_457;
        }
        if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v100 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (v101 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v101 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            522719640,
            4,
            13,
            v101,
            v100,
            79,
            &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
        }
LABEL_196:
        v7 = 1;
        ObjectSDAndClassId = 0;
        goto LABEL_457;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v87, v86)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        v92 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
          || (v93 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
        {
          v93 = 1;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          522719587,
          4,
          13,
          v93,
          v92,
          76,
          &WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
      }
    }
    ObjectSDAndClassId = 0;
    goto LABEL_457;
  }
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
    || (unsigned int)THStateCheckForTraceOverride(v16, v15)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
  {
    v17 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
    if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
      || (v18 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
    {
      v18 = 1;
    }
    v19 = 522719293;
    phAuthzClientContext = 56;
    goto LABEL_36;
  }
LABEL_457:
  *v131 = v7;
  if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v103, v102)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
  {
    v104 = gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v103, v102)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
    if ( !(unsigned int)THStateCheckForTraceOverride(v103, v102)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13) )
    {
      v11 = 0;
    }
    WPP_SF__ATTRTYP_LOG_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      522719661,
      4,
      13,
      v11,
      v104,
      80,
      (__int64)&WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids);
  }
  if ( !v7 )
  {
    if ( !Owner || (v105 = ConvertSidToStringSidW(Owner, &v119), v106 = v119, !v105) )
      v106 = L"Unavailable";
    RtlInitUnicodeString(&v120, v106);
    if ( !Sid2 || (v107 = ConvertSidToStringSidW(Sid2, &v126), v108 = v126, !v107) )
      v108 = L"Unavailable";
    RtlInitUnicodeString(&v132, v108);
    SampWriteEventLog(SAMMSG_COMPUTER_ACCOUNT_REUSE_BLOCKED, L"uuub", &DestinationString, &v120, &v132);
  }
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v119 )
    LocalFree(v119);
  if ( v126 )
    LocalFree(v126);
  if ( v8 )
    SampMaybeEndDsTransaction(3);
  return (unsigned int)ObjectSDAndClassId;
}

```

## disassembly

```asm
0x1803f8760  mov     [rsp-8+arg_0], rbx
0x1803f8765  push    rbp
0x1803f8766  push    rsi
0x1803f8767  push    rdi
0x1803f8768  push    r12
0x1803f876a  push    r13
0x1803f876c  push    r14
0x1803f876e  push    r15
0x1803f8770  lea     rbp, [rsp-90h]
0x1803f8778  sub     rsp, 190h
0x1803f877f  mov     rax, cs:__security_cookie
0x1803f8786  xor     rax, rsp
0x1803f8789  mov     [rbp+0C0h+var_40], rax
0x1803f8790  xor     edi, edi
0x1803f8792  mov     [rbp+0C0h+var_E0], r9
0x1803f8796  xorps   xmm0, xmm0
0x1803f8799  mov     dword ptr [rsp+1C0h+var_170], 0C0000022h
0x1803f87a1  xor     ecx, ecx
0x1803f87a3  mov     [rbp+0C0h+StringSid], rdi
0x1803f87a7  movups  xmmword ptr [rbp+0C0h+var_60], xmm0
0x1803f87ab  mov     [rbp+0C0h+pRequest.OptionalArguments], rcx
0x1803f87af  mov     r12, r8
0x1803f87b2  mov     r14, rdx
0x1803f87b5  mov     [rbp+0C0h+SecurityDescriptor], rdi
0x1803f87b9  mov     r13d, edi
0x1803f87bc  mov     [rbp+0C0h+var_128], edi
0x1803f87bf  mov     r15d, edi
0x1803f87c2  mov     [rsp+1C0h+var_160], edi
0x1803f87c6  movups  xmmword ptr [rbp+0C0h+var_80], xmm0
0x1803f87ca  mov     [rsp+1C0h+OwnerDefaulted], dil
0x1803f87cf  movups  [rbp+0C0h+var_70], xmm0
0x1803f87d3  mov     [rbp+0C0h+var_124], edi
0x1803f87d6  movups  xmmword ptr [rbp+0C0h+var_60+0Ch], xmm0
0x1803f87da  mov     [rsp+1C0h+Sid2], rdi
0x1803f87df  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x1803f87e3  mov     [rbp+0C0h+var_110], rdi
0x1803f87e7  movups  xmmword ptr [rbp+0C0h+var_D8.Length], xmm0
0x1803f87eb  mov     [rbp+0C0h+Sid1], rdi
0x1803f87ef  mov     [rsp+1C0h+Owner], rdi
0x1803f87f4  mov     [rbp+0C0h+var_140], rdi
0x1803f87f8  movups  xmmword ptr [rbp+0C0h+var_138.Length], xmm0
0x1803f87fc  mov     [rsp+1C0h+var_158], edi
0x1803f8800  mov     qword ptr [rbp+0C0h+var_F8.LowPart], rdi
0x1803f8804  mov     [rbp+0C0h+var_120], edi
0x1803f8807  mov     [rbp+0C0h+var_11C], edi
0x1803f880a  movups  xmmword ptr [rbp+0C0h+pRequest.DesiredAccess], xmm0
0x1803f880e  mov     [rsp+1C0h+hAuthzClientContext], rdi
0x1803f8813  movups  xmmword ptr [rbp+0C0h+pRequest.ObjectTypeList], xmm0
0x1803f8817  mov     [r9], edi
0x1803f881a  movups  xmmword ptr [rbp+0C0h+var_A0.ResultListLength], xmm0
0x1803f881e  movups  xmmword ptr [rbp+0C0h+var_A0.SaclEvaluationResults], xmm0
0x1803f8822  call    THStateCheckForTraceOverride
0x1803f8827  lea     ebx, [rdi+1]
0x1803f882a  lea     esi, [rdi+0Dh]
0x1803f882d  test    eax, eax
0x1803f882f  jnz     short loc_1803F887B
0x1803f8831  mov     r8d, esi
0x1803f8834  lea     edx, [rdi+4]
0x1803f8837  xor     ecx, ecx
0x1803f8839  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f883e  test    eax, eax
0x1803f8840  jnz     short loc_1803F887B
0x1803f8842  mov     eax, cs:gfTraceToSecondProvider
0x1803f8848  test    eax, eax
0x1803f884a  jz      loc_1803F8908
0x1803f8850  call    THStateCheckForTraceOverride
0x1803f8855  test    eax, eax
0x1803f8857  jnz     short loc_1803F887B
0x1803f8859  call    ThStateCheckIfTraceToSecondProvier
0x1803f885e  test    eax, eax
0x1803f8860  jz      loc_1803F8908
0x1803f8866  mov     r8d, esi
0x1803f8869  lea     edx, [rdi+4]
0x1803f886c  mov     ecx, ebx
0x1803f886e  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f8873  test    eax, eax
0x1803f8875  jz      loc_1803F8908
0x1803f887b  mov     eax, cs:gfTraceToSecondProvider
0x1803f8881  test    eax, eax
0x1803f8883  jz      short loc_1803F88AC
0x1803f8885  call    THStateCheckForTraceOverride
0x1803f888a  test    eax, eax
0x1803f888c  jnz     short loc_1803F88AA
0x1803f888e  call    ThStateCheckIfTraceToSecondProvier
0x1803f8893  test    eax, eax
0x1803f8895  jz      short loc_1803F88AC
0x1803f8897  mov     r8d, esi
0x1803f889a  mov     edx, 4
0x1803f889f  mov     ecx, ebx
0x1803f88a1  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f88a6  test    eax, eax
0x1803f88a8  jz      short loc_1803F88AC
0x1803f88aa  mov     edi, ebx
0x1803f88ac  call    THStateCheckForTraceOverride
0x1803f88b1  test    eax, eax
0x1803f88b3  jnz     short loc_1803F88C6
0x1803f88b5  mov     r8d, esi
0x1803f88b8  lea     edx, [rax+4]
0x1803f88bb  xor     ecx, ecx
0x1803f88bd  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f88c2  test    eax, eax
0x1803f88c4  jz      short loc_1803F88C8
0x1803f88c6  mov     eax, ebx
0x1803f88c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1803f88cf  lea     rdx, WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids
0x1803f88d6  mov     [rsp+1C0h+phAccessCheckResults], r14; pSid
0x1803f88db  mov     r9d, esi; int
0x1803f88de  mov     [rsp+1C0h+pReply], rdx; LPCGUID
0x1803f88e3  mov     r8d, 4; int
0x1803f88e9  mov     word ptr [rsp+1C0h+phAuthzClientContext], 36h ; '6'; __int16
0x1803f88f0  mov     edx, 1F28100Ch; int
0x1803f88f5  mov     rcx, [rcx+10h]; int
0x1803f88f9  mov     dword ptr [rsp+1C0h+DynamicGroupArgs], edi; int
0x1803f88fd  mov     [rsp+1C0h+Identifier.LowPart], eax; int
0x1803f8901  call    WPP_SF__sid_
0x1803f8906  xor     edi, edi
0x1803f8908  lea     rdx, [rbp+0C0h+StringSid]; StringSid
0x1803f890c  mov     rcx, r14; Sid
0x1803f890f  call    cs:__imp_ConvertSidToStringSidW
0x1803f8915  mov     rdx, [rbp+0C0h+StringSid]
0x1803f8919  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x1803f891d  test    eax, eax
0x1803f891f  jnz     short loc_1803F8928
0x1803f8921  lea     rdx, aUnavailable_3; "Unavailable"
0x1803f8928  call    cs:__imp_RtlInitUnicodeString
0x1803f892e  lea     rdx, [rbp+0C0h+var_80]
0x1803f8932  mov     rcx, r14; Src
0x1803f8935  call    SampBuildDsNameFromSidNew
0x1803f893a  mov     dword ptr [rsp+1C0h+var_170], eax
0x1803f893e  test    eax, eax
0x1803f8940  jns     loc_1803F8A41
0x1803f8946  mov     edi, 2
0x1803f894b  mov     ecx, edi
0x1803f894d  call    IncrementWPPPerfCountersForLevel
0x1803f8952  test    eax, eax
0x1803f8954  jnz     short loc_1803F89AC
0x1803f8956  call    THStateCheckForTraceOverride
0x1803f895b  mov     r12d, esi
0x1803f895e  test    eax, eax
0x1803f8960  jnz     short loc_1803F89AF
0x1803f8962  mov     r8d, esi
0x1803f8965  mov     edx, edi
0x1803f8967  xor     ecx, ecx
0x1803f8969  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f896e  test    eax, eax
0x1803f8970  jnz     short loc_1803F89AF
0x1803f8972  mov     eax, cs:gfTraceToSecondProvider
0x1803f8978  test    eax, eax
0x1803f897a  jz      loc_1803FA263
0x1803f8980  call    THStateCheckForTraceOverride
0x1803f8985  test    eax, eax
0x1803f8987  jnz     short loc_1803F89AF
0x1803f8989  call    ThStateCheckIfTraceToSecondProvier
0x1803f898e  test    eax, eax
0x1803f8990  jz      loc_1803FA263
0x1803f8996  mov     r8d, esi
0x1803f8999  mov     edx, edi
0x1803f899b  mov     ecx, ebx
0x1803f899d  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f89a2  test    eax, eax
0x1803f89a4  jz      loc_1803FA263
0x1803f89aa  jmp     short loc_1803F89AF
0x1803f89ac  mov     r12d, esi
0x1803f89af  mov     eax, cs:gfTraceToSecondProvider
0x1803f89b5  mov     r14d, dword ptr [rsp+1C0h+var_170]
0x1803f89ba  test    eax, eax
0x1803f89bc  jz      short loc_1803F89E4
0x1803f89be  call    THStateCheckForTraceOverride
0x1803f89c3  test    eax, eax
0x1803f89c5  jnz     short loc_1803F89E0
0x1803f89c7  call    ThStateCheckIfTraceToSecondProvier
0x1803f89cc  test    eax, eax
0x1803f89ce  jz      short loc_1803F89E4
0x1803f89d0  mov     r8d, r12d
0x1803f89d3  mov     edx, edi
0x1803f89d5  mov     ecx, ebx
0x1803f89d7  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f89dc  test    eax, eax
0x1803f89de  jz      short loc_1803F89E4
0x1803f89e0  mov     esi, ebx
0x1803f89e2  jmp     short loc_1803F89E6
0x1803f89e4  xor     esi, esi
0x1803f89e6  call    THStateCheckForTraceOverride
0x1803f89eb  test    eax, eax
0x1803f89ed  jnz     short loc_1803F89FF
0x1803f89ef  mov     r8d, r12d
0x1803f89f2  mov     edx, edi
0x1803f89f4  xor     ecx, ecx
0x1803f89f6  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f89fb  test    eax, eax
0x1803f89fd  jz      short loc_1803F8A01
0x1803f89ff  mov     eax, ebx
0x1803f8a01  lea     rdx, WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids
0x1803f8a08  mov     dword ptr [rsp+1C0h+phAccessCheckResults], r14d
0x1803f8a0d  mov     [rsp+1C0h+pReply], rdx
0x1803f8a12  mov     edx, 1F281021h
0x1803f8a17  mov     word ptr [rsp+1C0h+phAuthzClientContext], 37h ; '7'
0x1803f8a1e  mov     dword ptr [rsp+1C0h+DynamicGroupArgs], esi
0x1803f8a22  mov     r8d, edi
0x1803f8a25  mov     rcx, cs:WPP_GLOBAL_Control
0x1803f8a2c  mov     r9d, r12d
0x1803f8a2f  mov     [rsp+1C0h+Identifier.LowPart], eax
0x1803f8a33  mov     rcx, [rcx+10h]
0x1803f8a37  call    WPP_SF__ATTRTYP_LOG_
0x1803f8a3c  jmp     loc_1803FA263
0x1803f8a41  xor     ecx, ecx
0x1803f8a43  call    SampMaybeBeginDsTransaction
0x1803f8a48  mov     dword ptr [rsp+1C0h+var_170], eax
0x1803f8a4c  test    eax, eax
0x1803f8a4e  js      loc_1803FA260
0x1803f8a54  lea     r9, [rsp+1C0h+var_160]; unsigned int *
0x1803f8a59  mov     r15d, ebx
0x1803f8a5c  lea     r8, [rbp+0C0h+var_128]; unsigned int *
0x1803f8a60  lea     rdx, [rbp+0C0h+SecurityDescriptor]; void **
0x1803f8a64  lea     rcx, [rbp+0C0h+var_80]; struct _DSNAME *
0x1803f8a68  call    ?SampDsGetObjectSDAndClassId@@YAJPEAU_DSNAME@@PEAPEAXPEAK2@Z; SampDsGetObjectSDAndClassId(_DSNAME *,void * *,ulong *,ulong *)
0x1803f8a6d  mov     dword ptr [rsp+1C0h+var_170], eax
0x1803f8a71  test    eax, eax
0x1803f8a73  jns     loc_1803F8B56
0x1803f8a79  mov     edi, 2
0x1803f8a7e  mov     ecx, edi
0x1803f8a80  call    IncrementWPPPerfCountersForLevel
0x1803f8a85  test    eax, eax
0x1803f8a87  jnz     short loc_1803F8ADF
0x1803f8a89  call    THStateCheckForTraceOverride
0x1803f8a8e  mov     r12d, esi
0x1803f8a91  test    eax, eax
0x1803f8a93  jnz     short loc_1803F8AE2
0x1803f8a95  mov     r8d, esi
0x1803f8a98  mov     edx, edi
0x1803f8a9a  xor     ecx, ecx
0x1803f8a9c  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f8aa1  test    eax, eax
0x1803f8aa3  jnz     short loc_1803F8AE2
0x1803f8aa5  mov     eax, cs:gfTraceToSecondProvider
0x1803f8aab  test    eax, eax
0x1803f8aad  jz      loc_1803FA263
0x1803f8ab3  call    THStateCheckForTraceOverride
0x1803f8ab8  test    eax, eax
0x1803f8aba  jnz     short loc_1803F8AE2
0x1803f8abc  call    ThStateCheckIfTraceToSecondProvier
0x1803f8ac1  test    eax, eax
0x1803f8ac3  jz      loc_1803FA263
0x1803f8ac9  mov     r8d, esi
0x1803f8acc  mov     edx, edi
0x1803f8ace  mov     ecx, ebx
0x1803f8ad0  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f8ad5  test    eax, eax
0x1803f8ad7  jz      loc_1803FA263
0x1803f8add  jmp     short loc_1803F8AE2
0x1803f8adf  mov     r12d, esi
0x1803f8ae2  mov     eax, cs:gfTraceToSecondProvider
0x1803f8ae8  mov     r14d, dword ptr [rsp+1C0h+var_170]
0x1803f8aed  test    eax, eax
0x1803f8aef  jz      short loc_1803F8B17
0x1803f8af1  call    THStateCheckForTraceOverride
0x1803f8af6  test    eax, eax
0x1803f8af8  jnz     short loc_1803F8B13
0x1803f8afa  call    ThStateCheckIfTraceToSecondProvier
0x1803f8aff  test    eax, eax
0x1803f8b01  jz      short loc_1803F8B17
0x1803f8b03  mov     r8d, r12d
0x1803f8b06  mov     edx, edi
0x1803f8b08  mov     ecx, ebx
0x1803f8b0a  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f8b0f  test    eax, eax
0x1803f8b11  jz      short loc_1803F8B17
0x1803f8b13  mov     esi, ebx
0x1803f8b15  jmp     short loc_1803F8B19
0x1803f8b17  xor     esi, esi
0x1803f8b19  call    THStateCheckForTraceOverride
0x1803f8b1e  test    eax, eax
0x1803f8b20  jnz     short loc_1803F8B32
0x1803f8b22  mov     r8d, r12d
0x1803f8b25  mov     edx, edi
0x1803f8b27  xor     ecx, ecx
0x1803f8b29  call    CheckWPPLevelFlagsEnabledForProvider
0x1803f8b2e  test    eax, eax
0x1803f8b30  jz      short loc_1803F8B34
0x1803f8b32  mov     eax, ebx
0x1803f8b34  lea     rdx, WPP_5727aa13a1463dd5a5d80cce1ace8ffa_Traceguids
0x1803f8b3b  mov     dword ptr [rsp+1C0h+phAccessCheckResults], r14d
0x1803f8b40  mov     [rsp+1C0h+pReply], rdx
0x1803f8b45  mov     edx, 1F28103Dh
0x1803f8b4a  mov     word ptr [rsp+1C0h+phAuthzClientContext], 38h ; '8'
0x1803f8b51  jmp     loc_1803F8A1E
0x1803f8b56  cmp     [rsp+1C0h+var_160], 3001Eh
0x1803f8b5e  jz      loc_1803F8C70
0x1803f8b64  mov     dword ptr [rsp+1C0h+var_170], 0C000000Dh
0x1803f8b6c  mov     edi, 2
0x1803f8b71  mov     ecx, edi
0x1803f8b73  call    IncrementWPPPerfCountersForLevel
0x1803f8b78  test    eax, eax
0x1803f8b7a  jnz     short loc_1803F8BD2
0x1803f8b7c  call    THStateCheckForTraceOverride
0x1803f8b81  mov     r12d, esi
0x1803f8b84  test    eax, eax
0x1803f8b86  jnz     short loc_1803F8BD5
0x1803f8b88  mov     r8d, esi
0x1803f8b8b  mov     edx, edi
  ... truncated ...
```
