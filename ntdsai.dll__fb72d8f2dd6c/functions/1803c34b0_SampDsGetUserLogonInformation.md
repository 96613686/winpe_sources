# SampDsGetUserLogonInformation

- ea: `0x1803c34b0`
- end: `0x1803c4207`
- name: `SampDsGetUserLogonInformation`
- size: `3415`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180030af8`
- `0x18008df20`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803b1a18`
- `0x1803b41bc`
- `0x1803c2594`
- `0x1803c2be4`
- `0x1803c34b0`
- `0x1803c4868`
- `0x1803d0008`
- `0x1803d0a28`
- `0x1803d12e8`
- `0x1803dfee8`
- `0x1803e2ed8`
- `0x18040df60`
- `0x180419050`
- `0x180419900`
- `0x180419e88`
- `0x18041a20c`
- `0x18041ac24`
- `0x18041afe8`
- `0x18042456c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803c3ea6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803c3ea6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c36aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c36dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c370e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c3720`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c36aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c36dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c370e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803c3720`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803c3d6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803c3dc0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803c3d6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1803c3dc0`
- `ntdll!RtlCompareUnicodeString` at `0x1803c3ac3`
- `ntdll!RtlCompareUnicodeString` at `0x1803c3ac3`
- `ntdll!RtlInitUnicodeString` at `0x1803c3aaf`
- `ntdll!RtlInitUnicodeString` at `0x1803c3aaf`
- `SAMSRV!SampDeleteContext` at `0x1803c41c8`
- `SAMSRV!SampDeleteContext` at `0x1803c41c8`
- `SAMSRV!SampCreateContextEx` at `0x1803c3617`
- `SAMSRV!SampCreateContextEx` at `0x1803c3617`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1803c365e`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1803c365e`
- `SAMSRV!SampSplitSid` at `0x1803c3a88`
- `SAMSRV!SampSplitSid` at `0x1803c3a88`
- `SAMSRV!SampQueryCapabilities` at `0x1803c35d3`
- `SAMSRV!SampQueryCapabilities` at `0x1803c35d3`
- `SAMSRV!SampRetrieveUserV1aFixed` at `0x1803c3ae0`
- `SAMSRV!SampRetrieveUserV1aFixed` at `0x1803c3ae0`
- `SAMSRV!SampGetReverseMembershipTransitive` at `0x1803c3db8`
- `SAMSRV!SampGetReverseMembershipTransitive` at `0x1803c3db8`
- `SAMSRV!SampNeedUserAccountSettingsDuringQuery` at `0x1803c3d93`
- `SAMSRV!SampNeedUserAccountSettingsDuringQuery` at `0x1803c3d93`
- `SAMSRV!SampGetIgnoreGCFailures` at `0x1803c3dd0`
- `SAMSRV!SampGetIgnoreGCFailures` at `0x1803c3dd0`
- `SAMSRV!SampQueryInformationUserInternal` at `0x1803c3e4c`
- `SAMSRV!SampQueryInformationUserInternal` at `0x1803c3e4c`
- `SAMSRV!SampUpdateAccountDisabledFlag` at `0x1803c40b8`
- `SAMSRV!SampUpdateAccountDisabledFlag` at `0x1803c40b8`
- `SAMSRV!SampReferenceContext` at `0x1803c41a9`
- `SAMSRV!SampReferenceContext` at `0x1803c41a9`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1803c3643`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1803c3643`
- `SAMSRV!SamIFreeClaimsBlob` at `0x1803c3674`
- `SAMSRV!SamIFreeClaimsBlob` at `0x1803c3674`
- `SAMSRV!SampDeReferenceContext` at `0x1803c374f`
- `SAMSRV!SampDeReferenceContext` at `0x1803c374f`

## pseudocode

```c
__int64 __fastcall SampDsGetUserLogonInformation(
        unsigned int a1,
        const UNICODE_STRING *a2,
        unsigned int a3,
        unsigned int a4,
        struct _SAM_MAPPED_ATTRIBUTE_SET *a5,
        unsigned int a6,
        __int64 a7,
        unsigned int a8,
        __int64 a9,
        struct _DSNAME *a10,
        __int64 a11,
        char a12,
        __int64 a13,
        _QWORD *a14,
        _OWORD *a15,
        struct _SAM_CLAIMS_BLOB *a16,
        __int64 *a17)
{
  _QWORD *v17; // r12
  __int64 v18; // r14
  __int128 v19; // xmm6
  struct _SAMP_CLAIM_CONFIG_SET *v20; // r15
  __int64 v21; // rcx
  int NGCKeyInfo; // edi
  __int64 v23; // r12
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 Context; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  _OWORD *v30; // rbx
  __int64 *v31; // r15
  unsigned int v32; // ebx
  char *v33; // rsi
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  __int64 v36; // r8
  int v37; // ebx
  struct _UNICODE_STRING *v38; // rsi
  unsigned int v39; // r13d
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // r8
  __int64 v46; // r9
  BOOL v47; // ebx
  int v48; // eax
  struct _NGCKEY_INFO **v49; // rsi
  struct _NGCKEY_INFO *v50; // rdx
  unsigned int v51; // eax
  unsigned __int8 v52; // bl
  __int64 v53; // r8
  int v54; // ebx
  int v55; // ecx
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // r8
  __int64 v63; // r9
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // r8
  __int64 v70; // r9
  int v71; // eax
  __int64 v72; // r8
  int v73; // ebx
  unsigned int v74; // r15d
  struct _SAM_CLAIMS_BLOB *v75; // rdx
  unsigned int v76; // r15d
  unsigned int v77; // ebx
  int v78; // r12d
  HLOCAL v79; // rax
  size_t v80; // rbx
  __int64 v81; // r8
  struct _SAM_MAPPED_ATTRIBUTE_SET *v82; // r15
  __int128 v83; // xmm0
  __int64 v84; // rax
  unsigned int v85; // ecx
  __int64 v86; // rax
  int v87; // r15d
  __int64 v88; // rdx
  __int64 v89; // rcx
  __int64 v90; // r8
  __int64 v91; // r9
  __int64 v92; // r8
  __int64 v93; // r9
  int v94; // eax
  unsigned __int64 v95; // rdx
  int v97; // [rsp+28h] [rbp-E0h]
  char v98; // [rsp+58h] [rbp-B0h]
  unsigned int v101[2]; // [rsp+70h] [rbp-98h] BYREF
  struct _DSNAME *v102; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v103; // [rsp+80h] [rbp-88h]
  struct _SAM_CLAIMS_BLOB *v104; // [rsp+88h] [rbp-80h]
  __int64 *v105; // [rsp+90h] [rbp-78h]
  int v106[4]; // [rsp+98h] [rbp-70h] BYREF
  HLOCAL hMem[2]; // [rsp+A8h] [rbp-60h] BYREF
  PCUNICODE_STRING String1; // [rsp+B8h] [rbp-50h]
  HLOCAL Src[2]; // [rsp+C0h] [rbp-48h] BYREF
  int v110; // [rsp+D0h] [rbp-38h] BYREF
  _OWORD *v111; // [rsp+D8h] [rbp-30h]
  HLOCAL v112; // [rsp+E0h] [rbp-28h]
  struct _SAM_MAPPED_ATTRIBUTE_SET *v113[2]; // [rsp+E8h] [rbp-20h]
  struct _SAMP_CLAIM_CONFIG_SET *v114[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v115; // [rsp+108h] [rbp+0h]
  HLOCAL v116[2]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v117; // [rsp+128h] [rbp+20h]
  __int64 v118; // [rsp+130h] [rbp+28h] BYREF
  struct _DSNAME **v119[2]; // [rsp+138h] [rbp+30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+148h] [rbp+40h] BYREF
  _OWORD v121[2]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v122[56]; // [rsp+178h] [rbp+70h] BYREF
  int v123; // [rsp+1B0h] [rbp+A8h]

  v17 = a14;
  v18 = 0;
  v111 = a15;
  v113[0] = a5;
  v101[0] = a8;
  v102 = a10;
  v117 = a11;
  String1 = a2;
  v103 = a1;
  v105 = a17;
  v104 = a16;
  DestinationString = 0;
  memset_0(v122, 0, 0x50u);
  *a14 = 0;
  v106[0] = 0;
  v19 = 0;
  v110 = 4;
  v20 = 0;
  v112 = 0;
  v114[0] = 0;
  v118 = 0;
  *a15 = 0;
  *(_OWORD *)v119 = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v116 = 0;
  *(_OWORD *)Src = 0;
  if ( a16 )
    *(_OWORD *)a16 = 0;
  NGCKeyInfo = SampMaybeBeginDsTransaction(0);
  if ( NGCKeyInfo < 0 )
    goto LABEL_7;
  LOBYTE(v21) = 1;
  v23 = SampQueryCapabilities(v21) & 5;
  LOBYTE(v24) = 1;
  LOBYTE(v25) = *(_BYTE *)(a7 + 20) >> 7;
  LOBYTE(v26) = 1;
  Context = SampCreateContextEx(4, v26, v24, v25, 1, 1, 0, 0, v101[0]);
  v18 = Context;
  if ( !Context )
  {
    NGCKeyInfo = -1073741670;
    goto LABEL_6;
  }
  v37 = v103 & 0x20000;
  if ( (v103 & 0x20000) != 0 )
  {
    if ( dword_180528060 == 1 )
    {
      NGCKeyInfo = -1073741275;
      if ( (unsigned int)THStateCheckForTraceOverride(v29, v28)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v42, v41, v43, v44)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        v47 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v42, v41, v45, v46)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v42, v41)
          || (v48 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
        {
          v48 = 1;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          522782162,
          4,
          13,
          v48,
          v47,
          18,
          &WPP_b833ca7a2b883f3b7342df060f8a2301_Traceguids);
      }
      goto LABEL_6;
    }
    v49 = (struct _NGCKEY_INFO **)(Context + 736);
    NGCKeyInfo = SamDsGetNGCKeyInfo((struct _UNICODE_STRING *)String1);
    if ( NGCKeyInfo < 0 )
    {
LABEL_6:
      v17 = a14;
LABEL_7:
      v30 = v111;
      if ( *((_QWORD *)v111 + 1) )
        SamIFreeSidAndAttributesList(v111);
      *(_DWORD *)v30 = 0;
      *((_QWORD *)v30 + 1) = 0;
      if ( *v17 )
      {
        SamIFree_SAMPR_USER_INFO_BUFFER(*v17, 21);
        *v17 = 0;
      }
      if ( v104 )
        SamIFreeClaimsBlob(v104);
      v31 = v105;
      goto LABEL_14;
    }
    v50 = *v49;
    *(_BYTE *)(v18 + 728) = 1;
    v40 = SampDSEnforceROCAValidationPolicy(v102, v50);
    v39 = v103;
    v38 = (struct _UNICODE_STRING *)String1;
  }
  else
  {
    v38 = (struct _UNICODE_STRING *)String1;
    v39 = v103;
    v40 = SampResolveAccountName(String1, v103, a6, a9, v117, a13, v23 == 1, &v102);
  }
  NGCKeyInfo = v40;
  if ( v40 < 0 )
    goto LABEL_6;
  *(_QWORD *)(v18 + 176) = v102;
  *(_DWORD *)(v18 + 200) = v101[0];
  v51 = *(_DWORD *)(v18 + 192) & 0xFFFFFFFE;
  *(_DWORD *)(v18 + 148) = 985087;
  *(_DWORD *)(v18 + 192) = v51 | 2;
  if ( (_DWORD)v23 == 1 && !v37 )
  {
    NGCKeyInfo = SampValidateSecrets((__int64)v102, a4);
    if ( NGCKeyInfo < 0 )
      goto LABEL_6;
  }
  if ( v104 )
  {
    v101[0] = -1;
    if ( v102 )
    {
      if ( (int)SampDsGetClassIdFromObjectDsName(v102, v101) >= 0 && v101[0] != -1 )
      {
        if ( (int)SampDsGetClaimConfigSetWorker(v101[0], 0, v114) >= 0 && v113[0] )
        {
          v20 = v114[0];
          SampGetCertificateSourcedClaims(v113[0], v114[0], (struct _SAM_CLAIMS_ARRAY *)v116);
          v19 = *(_OWORD *)v116;
        }
        else
        {
          v20 = v114[0];
        }
      }
    }
  }
  if ( (v39 & 0x80000) != 0 )
  {
    *(_OWORD *)v114 = 0;
    NGCKeyInfo = SampDsGetManagedPassword(v38, (struct _SAMP_OBJECT *)v18, (struct _ATTRBLOCKSIMPLE *)v114);
    if ( NGCKeyInfo < 0 )
      goto LABEL_6;
    v52 = SampProcessDMSAPasswordChange((struct _SAMP_OBJECT *)v18);
    NGCKeyInfo = SampDsFillContextWithManagedPasswordAttrs(
                   v38,
                   (struct _ATTRBLOCKSIMPLE *)v114,
                   (struct _SAMP_OBJECT *)v18);
    if ( NGCKeyInfo < 0 )
      goto LABEL_6;
    if ( v52 )
    {
      SampMaybeEndDsTransaction(3);
      NGCKeyInfo = SampMaybeBeginDsTransaction(0);
      if ( NGCKeyInfo < 0 )
        goto LABEL_6;
    }
  }
  LOBYTE(v97) = 0;
  NGCKeyInfo = SampDsCheckObjectTypeAndFillContextWithClaims(4, v18, a3, a4, v97, v20, Src, hMem);
  if ( v20 )
    SampDsReleaseClaimConfigSet(v20);
  if ( NGCKeyInfo < 0 )
    goto LABEL_6;
  v98 = 0;
  SampSplitSid((char *)v102 + 24, 0, v18 + 248);
  if ( (v39 & 8) == 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"krbtgt");
    v54 = 1;
    if ( !RtlCompareUnicodeString(String1, &DestinationString, 1u) || (v39 & 0x3000) != 0 )
      v39 |= 1u;
    NGCKeyInfo = SampRetrieveUserV1aFixed(v18, v122);
    if ( NGCKeyInfo < 0 )
      goto LABEL_6;
    v55 = v39 | 1;
    if ( (v123 & 0x100140) == 0 )
      v55 = v39;
    v39 = v55 | 4;
    if ( !a12 )
      v39 = v55;
    if ( v117 )
    {
      v56 = *(_QWORD *)(v18 + 176);
      v57 = *(_QWORD *)(v117 + 8) - *(_QWORD *)(v56 + 8);
      if ( !v57 )
        v57 = *(_QWORD *)(v117 + 16) - *(_QWORD *)(v56 + 16);
      if ( !v57 )
        v39 |= 1u;
    }
    if ( (int)GetConfigurationInfo(2, &v110, v106) >= 0 )
    {
      if ( v106[0] >= 4 )
      {
        if ( v113[0] )
        {
          NGCKeyInfo = SampProcessMappedAttributes(v113[0], (unsigned int *)v119, &v119[1]);
          if ( NGCKeyInfo < 0 )
          {
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
              || (unsigned int)THStateCheckForTraceOverride(v66, v65)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v66, v65)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v66, v65, v67, v68)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
            {
              if ( !gfTraceToSecondProvider
                || !(unsigned int)THStateCheckForTraceOverride(v66, v65)
                && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v66, v65, v69, v70)
                 || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
              {
                v54 = 0;
              }
              if ( (unsigned int)THStateCheckForTraceOverride(v66, v65)
                || (v71 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
              {
                v71 = 1;
              }
              WPP_SF__ATTRTYP_LOG_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                522782417,
                2,
                13,
                v71,
                v54,
                20,
                (__int64)&WPP_b833ca7a2b883f3b7342df060f8a2301_Traceguids);
            }
            if ( NGCKeyInfo != -1073741811 )
              goto LABEL_6;
          }
        }
      }
    }
    else if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
           || (unsigned int)THStateCheckForTraceOverride(v59, v58)
           || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
           || gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v59, v58)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v59, v58, v60, v61)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
    {
      if ( !gfTraceToSecondProvider
        || !(unsigned int)THStateCheckForTraceOverride(v59, v58)
        && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v59, v58, v62, v63)
         || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
      {
        v54 = 0;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v59, v58)
        || (v64 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)) != 0 )
      {
        v64 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        522782400,
        3,
        13,
        v64,
        v54,
        19,
        (__int64)&WPP_b833ca7a2b883f3b7342df060f8a2301_Traceguids);
    }
    GetTickCount();
    if ( v104 )
      v39 |= 0x10000u;
    LOBYTE(v72) = SampNeedUserAccountSettingsDuringQuery(a6, a3, a4);
    NGCKeyInfo = SampGetReverseMembershipTransitive(v18, v39, v72, v119, v111, &v118);
    GetTickCount();
    if ( NGCKeyInfo == 289 )
    {
      if ( !(unsigned __int8)SampGetIgnoreGCFailures() && *(_DWORD *)(v18 + 248) != 500 )
      {
        if ( !(unsigned __int8)SampIsGroupCachingEnabled(v18) )
        {
          NGCKeyInfo = -1073741730;
          goto LABEL_6;
        }
        *(_BYTE *)(v18 + 385) = 1;
      }
    }
    else if ( NGCKeyInfo < 0 )
    {
      goto LABEL_6;
    }
    v98 = 1;
    DsSamUpdateLatencyCounter(&SampAccountGroupsLatencyInfo);
  }
  v17 = a14;
  v73 = 1;
  v74 = a4;
  LOBYTE(v53) = 1;
  NGCKeyInfo = SampQueryInformationUserInternal(v18, a6, v53, a3, a4, a14);
  if ( NGCKeyInfo < 0 )
    goto LABEL_7;
  if ( *(_WORD *)(*a14 + 96LL) > 4u )
    *(_WORD *)(*a14 + 96LL) = 4;
  v75 = v104;
  if ( v104 )
  {
    v76 = HIDWORD(Src[0]);
    *(_OWORD *)v114 = 0;
    v115 = 0;
    *(_OWORD *)v113 = 0;
    if ( HIDWORD(Src[0]) )
    {
      v77 = HIDWORD(hMem[0]);
      v78 = HIDWORD(hMem[0]) + HIDWORD(Src[0]);
      v79 = LocalAlloc(0x40u, 32LL * (unsigned int)(HIDWORD(hMem[0]) + HIDWORD(Src[0])));
      v112 = v79;
      if ( v79 )
      {
        v80 = 32LL * v77;
        memcpy_0(v79, hMem[1], v80);
        v81 = v76;
        v82 = (struct _SAM_MAPPED_ATTRIBUTE_SET *)v112;
        memcpy_0((char *)v112 + v80, Src[1], 32 * v81);
        v75 = v104;
        v73 = 1;
        HIDWORD(v113[0]) = v78;
        v17 = a14;
        LOWORD(v113[0]) = 1;
        v113[1] = v82;
        v83 = *(_OWORD *)v113;
LABEL_146:
        if ( DWORD1(v83) )
        {
          v84 = LODWORD(v114[0]);
          v85 = ++LODWORD(v114[0]);
          v121[v84] = v83;
        }
        else
        {
          v85 = (unsigned int)v114[0];
        }
        if ( HIDWORD(v116[0]) )
        {
          v86 = v85++;
          LODWORD(v114[0]) = v85;
          v121[v86] = v19;
        }
        if ( v85 )
        {
          v114[1] = (struct _SAMP_CLAIM_CONFIG_SET *)v121;
          v87 = SampEncodeClaimsBlob((struct _SAM_CLAIMS_SET *)v114, v75);
          if ( v87 < 0 )
          {
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
              || (unsigned int)THStateCheckForTraceOverride(v89, v88)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v89, v88)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v89, v88, v90, v91)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
            {
              if ( !gfTraceToSecondProvider
                || !(unsigned int)THStateCheckForTraceOverride(v89, v88)
                && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v89, v88, v92, v93)
                 || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
              {
                v73 = 0;
              }
              if ( (unsigned int)THStateCheckForTraceOverride(v89, v88)
                || (v94 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)) != 0 )
              {
                v94 = 1;
              }
              WPP_SF__ATTRTYP_LOG_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                522782594,
                3,
                13,
                v94,
                v73,
                21,
                (__int64)&WPP_b833ca7a2b883f3b7342df060f8a2301_Traceguids);
            }
            SampClaimsLogEncodingError(v102, v87);
            *(_OWORD *)v104 = 0;
          }
        }
        v74 = a4;
        goto LABEL_171;
      }
      v17 = a14;
      v73 = 1;
      v75 = v104;
    }
    v83 = *(_OWORD *)hMem;
    goto LABEL_146;
  }
LABEL_171:
  if ( !a3 || (a3 & 0x100000) != 0 )
  {
    if ( a6 != 21 && a6 != 27 )
    {
      NGCKeyInfo = -1073741811;
      goto LABEL_7;
    }
    NGCKeyInfo = SampUpdateAccountDisabledFlag(v18, *v17 + 280LL);
    if ( NGCKeyInfo < 0 )
      goto LABEL_7;
  }
  if ( v98 && (v74 & 0x2000000) != 0 )
  {
    *(_BYTE *)(*v17 + 608LL) = 1;
    v95 = (unsigned __int64)(10000000 * v118) >> 32;
    *(_DWORD *)(*v17 + 616LL) = 10000000 * v118;
    *(_DWORD *)(*v17 + 620LL) = v95;
  }
  else
  {
    *(_BYTE *)(*v17 + 608LL) = 0;
    *(_QWORD *)(*v17 + 616LL) = 0;
  }
  if ( (v39 & 0x20000) != 0 )
  {
    *(_BYTE *)(*v17 + 624LL) = 1;
    *(_BYTE *)(*v17 + 625LL) = *(_DWORD *)(*(_QWORD *)(v18 + 736) + 72LL) & 1;
    *(_BYTE *)(*v17 + 626LL) = (*(_DWORD *)(*(_QWORD *)(v18 + 736) + 72LL) & 2) == 0;
  }
  if ( (v74 & 0x20) != 0 && (*(_DWORD *)(*v17 + 328LL) & 8) != 0 )
    *(_DWORD *)(*v17 + 368LL) = *(unsigned __int16 *)(*v17 + 368LL) | (*(_DWORD *)(*v17 + 376LL) << 16);
  v31 = v105;
  if ( v105 )
  {
    *v105 = v18;
    SampReferenceContext(v18);
    if ( (v39 & 8) == 0 )
      *(_BYTE *)(v18 + 384) = 1;
  }
LABEL_14:
  if ( hMem[1] )
  {
    v32 = 0;
    if ( HIDWORD(hMem[0]) )
    {
      do
        SampFreeClaimsEntry((struct _SAM_CLAIM_ENTRY *)((char *)hMem[1] + 32 * v32++));
      while ( v32 < HIDWORD(hMem[0]) );
      v31 = v105;
    }
    LocalFree(hMem[1]);
  }
  v33 = (char *)v116[1];
  if ( v116[1] )
  {
    v34 = 0;
    if ( HIDWORD(v116[0]) )
    {
      do
        SampFreeClaimsEntry((struct _SAM_CLAIM_ENTRY *)&v33[32 * v34++]);
      while ( v34 < HIDWORD(v116[0]) );
      v31 = v105;
    }
    LocalFree(v33);
  }
  if ( Src[1] )
  {
    v35 = 0;
    if ( HIDWORD(Src[0]) )
    {
      do
        SampFreeClaimsEntry((struct _SAM_CLAIM_ENTRY *)((char *)Src[1] + 32 * v35++));
      while ( v35 < HIDWORD(Src[0]) );
      v31 = v105;
    }
    LocalFree(Src[1]);
  }
  if ( v112 )
    LocalFree(v112);
  SampMaybeEndDsTransaction(3);
  if ( v18 )
  {
    if ( v31 && NGCKeyInfo >= 0 )
    {
      SampDeReferenceContext(v18, 0, v36);
    }
    else
    {
      SampDeleteContext(v18);
      if ( v31 )
        *v31 = 0;
    }
  }
  return (unsigned int)NGCKeyInfo;
}

```

## disassembly

```asm
0x1803c34b0  mov     rax, rsp
0x1803c34b3  push    rbp
0x1803c34b4  push    rbx
0x1803c34b5  push    rsi
0x1803c34b6  push    rdi
0x1803c34b7  push    r12
0x1803c34b9  push    r13
0x1803c34bb  push    r14
0x1803c34bd  push    r15
0x1803c34bf  lea     rbp, [rax-128h]
0x1803c34c6  sub     rsp, 1E8h
0x1803c34cd  movaps  xmmword ptr [rax-58h], xmm6
0x1803c34d1  mov     rax, cs:__security_cookie
0x1803c34d8  xor     rax, rsp
0x1803c34db  mov     [rbp+120h+var_60], rax
0x1803c34e2  mov     rax, [rbp+120h+arg_70]
0x1803c34e9  xorps   xmm0, xmm0
0x1803c34ec  mov     r12, [rbp+120h+arg_68]
0x1803c34f3  xor     r14d, r14d
0x1803c34f6  mov     rdi, [rbp+120h+arg_78]
0x1803c34fd  mov     rbx, [rbp+120h+arg_30]
0x1803c3504  mov     rsi, [rbp+120h+arg_40]
0x1803c350b  mov     r13, [rbp+120h+arg_60]
0x1803c3512  mov     [rbp+120h+var_150], rax
0x1803c3516  mov     rax, [rbp+120h+arg_20]
0x1803c351d  mov     [rbp+120h+var_140], rax
0x1803c3521  mov     eax, [rbp+120h+arg_38]
0x1803c3527  mov     [rsp+220h+var_1B8], eax
0x1803c352b  mov     rax, [rbp+120h+arg_48]
0x1803c3532  mov     [rsp+220h+var_1B0], rax
0x1803c3537  mov     rax, [rbp+120h+arg_50]
0x1803c353e  mov     [rbp+120h+var_100], rax
0x1803c3542  mov     rax, [rbp+120h+arg_80]
0x1803c3549  mov     [rsp+64h], r8d
0x1803c354e  lea     r8d, [r14+50h]; Size
0x1803c3552  mov     [rbp+120h+String1], rdx
0x1803c3556  xor     edx, edx; Val
0x1803c3558  mov     [rsp+220h+var_1A8], ecx
0x1803c355c  lea     rcx, [rbp+120h+var_B0]; void *
0x1803c3560  mov     [rbp+120h+var_198], rax
0x1803c3564  mov     [rsp+220h+var_1C0], r9d
0x1803c3569  mov     qword ptr [rsp+220h+var_1C8], r12
0x1803c356e  mov     [rbp+120h+var_1A0], rdi
0x1803c3572  movups  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x1803c3576  call    memset_0
0x1803c357b  mov     rax, [rbp+120h+var_150]
0x1803c357f  xor     ecx, ecx
0x1803c3581  mov     [r12], rcx
0x1803c3585  xorps   xmm0, xmm0
0x1803c3588  mov     [rbp+120h+var_190], ecx
0x1803c358b  xorps   xmm6, xmm6
0x1803c358e  mov     [rbp+120h+var_158], 4
0x1803c3595  mov     r15d, ecx
0x1803c3598  mov     [rbp+120h+var_148], rcx
0x1803c359c  mov     [rbp+120h+var_130], rcx
0x1803c35a0  mov     [rbp+120h+var_F8], rcx
0x1803c35a4  movups  xmmword ptr [rax], xmm0
0x1803c35a7  movups  xmmword ptr [rbp+120h+var_F0], xmm0
0x1803c35ab  movups  xmmword ptr [rbp+120h+hMem], xmm0
0x1803c35af  movups  xmmword ptr [rbp+120h+var_110], xmm6
0x1803c35b3  movups  xmmword ptr [rbp+120h+Src], xmm0
0x1803c35b7  test    rdi, rdi
0x1803c35ba  jz      short loc_1803C35BF
0x1803c35bc  movups  xmmword ptr [rdi], xmm0
0x1803c35bf  call    SampMaybeBeginDsTransaction
0x1803c35c4  mov     edi, eax
0x1803c35c6  test    eax, eax
0x1803c35c8  js      short loc_1803C3633
0x1803c35ca  xor     edx, edx
0x1803c35cc  lea     r14d, [rdx+1]
0x1803c35d0  mov     cl, r14b
0x1803c35d3  call    cs:__imp_SampQueryCapabilities
0x1803c35d9  mov     r9b, [rbx+14h]
0x1803c35dd  lea     ecx, [r14+3]
0x1803c35e1  mov     r12d, eax
0x1803c35e4  xor     edi, edi
0x1803c35e6  mov     eax, [rsp+220h+var_1B8]
0x1803c35ea  and     r12d, 5
0x1803c35ee  mov     [rsp+40h], eax
0x1803c35f2  cmp     r12d, r14d
0x1803c35f5  mov     byte ptr [rsp+220h+var_1E8], r15b
0x1803c35fa  mov     r8b, r14b
0x1803c35fd  setz    dil
0x1803c3601  mov     byte ptr [rsp+220h+var_1F0], r15b
0x1803c3606  shr     r9b, 7
0x1803c360a  mov     dl, r14b
0x1803c360d  mov     byte ptr [rsp+220h+var_1F8], r14b
0x1803c3612  mov     byte ptr [rsp+220h+var_200], r14b
0x1803c3617  call    cs:__imp_SampCreateContextEx
0x1803c361d  mov     r14, rax
0x1803c3620  test    rax, rax
0x1803c3623  jnz     loc_1803C375A
0x1803c3629  mov     edi, 0C000009Ah
0x1803c362e  mov     r12, qword ptr [rsp+220h+var_1C8]
0x1803c3633  mov     rbx, [rbp+120h+var_150]
0x1803c3637  xor     r15d, r15d
0x1803c363a  cmp     [rbx+8], r15
0x1803c363e  jz      short loc_1803C3649
0x1803c3640  mov     rcx, rbx
0x1803c3643  call    cs:__imp_SamIFreeSidAndAttributesList
0x1803c3649  mov     [rbx], r15d
0x1803c364c  mov     [rbx+8], r15
0x1803c3650  mov     rcx, [r12]
0x1803c3654  test    rcx, rcx
0x1803c3657  jz      short loc_1803C3668
0x1803c3659  mov     edx, 15h
0x1803c365e  call    cs:__imp_SamIFree_SAMPR_USER_INFO_BUFFER
0x1803c3664  mov     [r12], r15
0x1803c3668  mov     rax, [rbp+120h+var_1A0]
0x1803c366c  test    rax, rax
0x1803c366f  jz      short loc_1803C367A
0x1803c3671  mov     rcx, rax
0x1803c3674  call    cs:__imp_SamIFreeClaimsBlob
0x1803c367a  mov     r15, [rbp+120h+var_198]
0x1803c367e  cmp     [rbp+120h+hMem+8], 0
0x1803c3683  jz      short loc_1803C36B0
0x1803c3685  xor     ebx, ebx
0x1803c3687  cmp     dword ptr [rbp+120h+hMem+4], ebx
0x1803c368a  jbe     short loc_1803C36A6
0x1803c368c  mov     ecx, ebx
0x1803c368e  shl     rcx, 5
0x1803c3692  add     rcx, [rbp+120h+hMem+8]; struct _SAM_CLAIM_ENTRY *
0x1803c3696  call    ?SampFreeClaimsEntry@@YAXPEAU_SAM_CLAIM_ENTRY@@@Z; SampFreeClaimsEntry(_SAM_CLAIM_ENTRY *)
0x1803c369b  inc     ebx
0x1803c369d  cmp     ebx, dword ptr [rbp+120h+hMem+4]
0x1803c36a0  jb      short loc_1803C368C
0x1803c36a2  mov     r15, [rbp+120h+var_198]
0x1803c36a6  mov     rcx, [rbp+120h+hMem+8]; hMem
0x1803c36aa  call    cs:__imp_LocalFree
0x1803c36b0  mov     rsi, [rbp+120h+var_110+8]
0x1803c36b4  test    rsi, rsi
0x1803c36b7  jz      short loc_1803C36E2
0x1803c36b9  xor     ebx, ebx
0x1803c36bb  cmp     dword ptr [rbp+120h+var_110+4], ebx
0x1803c36be  jbe     short loc_1803C36D9
0x1803c36c0  mov     ecx, ebx
0x1803c36c2  shl     rcx, 5
0x1803c36c6  add     rcx, rsi; struct _SAM_CLAIM_ENTRY *
0x1803c36c9  call    ?SampFreeClaimsEntry@@YAXPEAU_SAM_CLAIM_ENTRY@@@Z; SampFreeClaimsEntry(_SAM_CLAIM_ENTRY *)
0x1803c36ce  inc     ebx
0x1803c36d0  cmp     ebx, dword ptr [rbp+120h+var_110+4]
0x1803c36d3  jb      short loc_1803C36C0
0x1803c36d5  mov     r15, [rbp+120h+var_198]
0x1803c36d9  mov     rcx, rsi; hMem
0x1803c36dc  call    cs:__imp_LocalFree
0x1803c36e2  cmp     [rbp+120h+Src+8], 0
0x1803c36e7  jz      short loc_1803C3714
0x1803c36e9  xor     ebx, ebx
0x1803c36eb  cmp     dword ptr [rbp+120h+Src+4], ebx
0x1803c36ee  jbe     short loc_1803C370A
0x1803c36f0  mov     ecx, ebx
0x1803c36f2  shl     rcx, 5
0x1803c36f6  add     rcx, [rbp+120h+Src+8]; struct _SAM_CLAIM_ENTRY *
0x1803c36fa  call    ?SampFreeClaimsEntry@@YAXPEAU_SAM_CLAIM_ENTRY@@@Z; SampFreeClaimsEntry(_SAM_CLAIM_ENTRY *)
0x1803c36ff  inc     ebx
0x1803c3701  cmp     ebx, dword ptr [rbp+120h+Src+4]
0x1803c3704  jb      short loc_1803C36F0
0x1803c3706  mov     r15, [rbp+120h+var_198]
0x1803c370a  mov     rcx, [rbp+120h+Src+8]; hMem
0x1803c370e  call    cs:__imp_LocalFree
0x1803c3714  mov     rax, [rbp+120h+var_148]
0x1803c3718  test    rax, rax
0x1803c371b  jz      short loc_1803C3726
0x1803c371d  mov     rcx, rax; hMem
0x1803c3720  call    cs:__imp_LocalFree
0x1803c3726  mov     ecx, 3
0x1803c372b  call    SampMaybeEndDsTransaction
0x1803c3730  test    r14, r14
0x1803c3733  jz      loc_1803C41DA
0x1803c3739  test    r15, r15
0x1803c373c  jz      loc_1803C41C5
0x1803c3742  test    edi, edi
0x1803c3744  js      loc_1803C41C5
0x1803c374a  xor     edx, edx
0x1803c374c  mov     rcx, r14
0x1803c374f  call    cs:__imp_SampDeReferenceContext
0x1803c3755  jmp     loc_1803C41DA
0x1803c375a  mov     ebx, [rsp+220h+var_1A8]
0x1803c375e  and     ebx, 20000h
0x1803c3764  jnz     short loc_1803C37A5
0x1803c3766  mov     r8d, [rbp+120h+arg_28]
0x1803c376d  lea     rax, [rsp+220h+var_1B0]
0x1803c3772  mov     [rsp+220h+var_1E8], rax
0x1803c3777  mov     r9, rsi
0x1803c377a  mov     rax, [rbp+120h+var_100]
0x1803c377e  mov     rsi, [rbp+120h+String1]
0x1803c3782  mov     dword ptr [rsp+220h+var_1F0], edi
0x1803c3786  mov     rcx, rsi
0x1803c3789  mov     qword ptr [rsp+220h+var_1F8], r13
0x1803c378e  mov     r13d, [rsp+220h+var_1A8]
0x1803c3793  mov     edx, r13d
0x1803c3796  mov     qword ptr [rsp+220h+var_200], rax
0x1803c379b  call    ?SampResolveAccountName@@YAJPEAU_UNICODE_STRING@@KW4_USER_INFORMATION_CLASS@@PEAU_DSNAME@@20HPEAPEAU3@@Z; SampResolveAccountName(_UNICODE_STRING *,ulong,_USER_INFORMATION_CLASS,_DSNAME *,_DSNAME *,_UNICODE_STRING *,int,_DSNAME * *)
0x1803c37a0  jmp     loc_1803C38E5
0x1803c37a5  mov     r13d, 1
0x1803c37ab  cmp     cs:dword_180528060, r13d
0x1803c37b2  jnz     loc_1803C38A6
0x1803c37b8  mov     edi, 0C0000225h
0x1803c37bd  call    THStateCheckForTraceOverride
0x1803c37c2  lea     esi, [r13+0Ch]
0x1803c37c6  lea     r15d, [r13+3]
0x1803c37ca  test    eax, eax
0x1803c37cc  jnz     short loc_1803C3819
0x1803c37ce  mov     r8d, esi
0x1803c37d1  mov     edx, r15d
0x1803c37d4  xor     ecx, ecx
0x1803c37d6  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c37db  test    eax, eax
0x1803c37dd  jnz     short loc_1803C3819
0x1803c37df  mov     eax, cs:gfTraceToSecondProvider
0x1803c37e5  test    eax, eax
0x1803c37e7  jz      loc_1803C362E
0x1803c37ed  call    THStateCheckForTraceOverride
0x1803c37f2  test    eax, eax
0x1803c37f4  jnz     short loc_1803C3819
0x1803c37f6  call    ThStateCheckIfTraceToSecondProvier
0x1803c37fb  test    eax, eax
0x1803c37fd  jz      loc_1803C362E
0x1803c3803  mov     r8d, esi
0x1803c3806  mov     edx, r15d
0x1803c3809  mov     ecx, r13d
0x1803c380c  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c3811  test    eax, eax
0x1803c3813  jz      loc_1803C362E
0x1803c3819  mov     eax, cs:gfTraceToSecondProvider
0x1803c381f  test    eax, eax
0x1803c3821  jz      short loc_1803C384C
0x1803c3823  call    THStateCheckForTraceOverride
0x1803c3828  test    eax, eax
0x1803c382a  jnz     short loc_1803C3847
0x1803c382c  call    ThStateCheckIfTraceToSecondProvier
0x1803c3831  test    eax, eax
0x1803c3833  jz      short loc_1803C384C
0x1803c3835  mov     r8d, esi
0x1803c3838  mov     edx, r15d
0x1803c383b  mov     ecx, r13d
0x1803c383e  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c3843  test    eax, eax
0x1803c3845  jz      short loc_1803C384C
0x1803c3847  mov     ebx, r13d
0x1803c384a  jmp     short loc_1803C384E
0x1803c384c  xor     ebx, ebx
0x1803c384e  call    THStateCheckForTraceOverride
0x1803c3853  test    eax, eax
0x1803c3855  jnz     short loc_1803C3868
0x1803c3857  mov     r8d, esi
0x1803c385a  mov     edx, r15d
0x1803c385d  xor     ecx, ecx
0x1803c385f  call    CheckWPPLevelFlagsEnabledForProvider
0x1803c3864  test    eax, eax
0x1803c3866  jz      short loc_1803C386B
0x1803c3868  mov     eax, r13d
0x1803c386b  lea     rcx, WPP_b833ca7a2b883f3b7342df060f8a2301_Traceguids
0x1803c3872  mov     r9d, esi; int
0x1803c3875  mov     [rsp+220h+var_1E8], rcx; LPCGUID
0x1803c387a  mov     r8d, r15d; int
0x1803c387d  mov     rcx, cs:WPP_GLOBAL_Control
0x1803c3884  mov     edx, 1F2905D2h; int
0x1803c3889  mov     [rsp+220h+var_1F0], 12h; __int16
0x1803c3890  mov     [rsp+220h+var_1F8], ebx; int
0x1803c3894  mov     [rsp+220h+var_200], eax; int
0x1803c3898  mov     rcx, [rcx+10h]; int
0x1803c389c  call    WPP_SF_
0x1803c38a1  jmp     loc_1803C362E
0x1803c38a6  mov     rcx, [rbp+120h+String1]; struct _UNICODE_STRING *
0x1803c38aa  lea     rsi, [rax+2E0h]
0x1803c38b1  mov     r8, rsi
0x1803c38b4  lea     rdx, [rsp+220h+var_1B0]
0x1803c38b9  call    SamDsGetNGCKeyInfo
0x1803c38be  mov     edi, eax
0x1803c38c0  test    eax, eax
0x1803c38c2  js      loc_1803C362E
0x1803c38c8  mov     rdx, [rsi]; struct _NGCKEY_INFO *
0x1803c38cb  mov     [r14+2D8h], r13b
0x1803c38d2  mov     rcx, [rsp+220h+var_1B0]; struct _DSNAME *
0x1803c38d7  call    ?SampDSEnforceROCAValidationPolicy@@YAJPEAU_DSNAME@@PEAU_NGCKEY_INFO@@@Z; SampDSEnforceROCAValidationPolicy(_DSNAME *,_NGCKEY_INFO *)
0x1803c38dc  mov     r13d, [rsp+220h+var_1A8]
0x1803c38e1  mov     rsi, [rbp+120h+String1]
0x1803c38e5  mov     edi, eax
0x1803c38e7  test    eax, eax
0x1803c38e9  js      loc_1803C362E
0x1803c38ef  mov     rax, [rsp+220h+var_1B0]
0x1803c38f4  mov     [r14+0B0h], rax
0x1803c38fb  mov     eax, [rsp+220h+var_1B8]
0x1803c38ff  mov     [r14+0C8h], eax
0x1803c3906  mov     eax, [r14+0C0h]
0x1803c390d  and     eax, 0FFFFFFFEh
0x1803c3910  mov     dword ptr [r14+94h], 0F07FFh
0x1803c391b  or      eax, 2
0x1803c391e  mov     [r14+0C0h], eax
0x1803c3925  mov     eax, 1
0x1803c392a  cmp     r12d, eax
0x1803c392d  mov     r12d, [rsp+220h+var_1C0]
0x1803c3932  jnz     short loc_1803C395B
0x1803c3934  test    ebx, ebx
0x1803c3936  jnz     short loc_1803C395B
0x1803c3938  mov     r8d, [rsp+64h]
0x1803c393d  mov     r9b, al
0x1803c3940  mov     rcx, [rsp+220h+var_1B0]; __int64
0x1803c3945  mov     dl, al
  ... truncated ...
```
