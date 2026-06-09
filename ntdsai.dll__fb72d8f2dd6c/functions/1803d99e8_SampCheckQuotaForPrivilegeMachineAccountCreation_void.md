# SampCheckQuotaForPrivilegeMachineAccountCreation(void)

- ea: `0x1803d99e8`
- end: `0x1803da41c`
- name: `?SampCheckQuotaForPrivilegeMachineAccountCreation@@YAJXZ`
- size: `2612`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1803b5280`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x180030af8`
- `0x180030b60`
- `0x18003dd78`
- `0x18003de48`
- `0x1803b0860`
- `0x1803d9158`
- `0x1803d99e8`
- `0x1803da424`
- `0x1803dc65c`
- `0x1803dd5d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803da3f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803da3ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803da40e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803da3f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803da3ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803da40e`
- `ntdll!RtlEqualSid` at `0x1803d9d1e`
- `ntdll!RtlEqualSid` at `0x1803d9d1e`
- `SAMSRV!SampUsingDsData` at `0x1803d9d02`
- `SAMSRV!SampUsingDsData` at `0x1803d9d02`
- `SAMSRV!SampGetDomainSidFromIndex` at `0x1803d9d11`
- `SAMSRV!SampGetDomainSidFromIndex` at `0x1803d9d11`
- `SAMSRV!SampDsIsRunning` at `0x1803d9a49`
- `SAMSRV!SampDsIsRunning` at `0x1803d9a49`
- `SAMSRV!SampSplitSid` at `0x1803d9ce4`
- `SAMSRV!SampSplitSid` at `0x1803d9ce4`
- `SAMSRV!SampGetCurrentOwnerAndPrimaryGroup` at `0x1803d9cc4`
- `SAMSRV!SampGetCurrentOwnerAndPrimaryGroup` at `0x1803d9cc4`

## pseudocode

```c
__int64 SampCheckQuotaForPrivilegeMachineAccountCreation(void)
{
  int v0; // r15d
  int v1; // ebx
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  int CurrentOwnerAndPrimaryGroup; // r14d
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r9
  BOOL v13; // r14d
  __int64 v15; // rax
  unsigned int v16; // r12d
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // r9
  BOOL v23; // r14d
  bool v24; // zf
  int v25; // eax
  char v26; // al
  void *DomainSidFromIndex; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  PSID pSid; // r15
  __int64 v33; // r8
  __int64 v34; // r9
  BOOL v35; // r14d
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  PSID v43; // r15
  __int64 v44; // r8
  __int64 v45; // r9
  BOOL v46; // esi
  int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  PSID v52; // r15
  __int64 v53; // r8
  __int64 v54; // r9
  BOOL v55; // esi
  int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // r8
  __int64 v62; // r9
  BOOL v63; // esi
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // r9
  PSID v68; // r13
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // r8
  __int64 v74; // r9
  PSID v75; // r13
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // r8
  __int64 v83; // r9
  BOOL v84; // esi
  int v85; // [rsp+38h] [rbp-61h]
  HLOCAL v86; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v87[2]; // [rsp+68h] [rbp-31h] BYREF
  __int128 v88; // [rsp+78h] [rbp-21h] BYREF
  int v89; // [rsp+88h] [rbp-11h] BYREF
  __int64 v90; // [rsp+90h] [rbp-9h]
  _DWORD v91[4]; // [rsp+98h] [rbp-1h] BYREF
  int *v92; // [rsp+A8h] [rbp+Fh]
  unsigned int v93; // [rsp+100h] [rbp+67h] BYREF
  int v94; // [rsp+108h] [rbp+6Fh] BYREF
  HLOCAL hMem; // [rsp+110h] [rbp+77h] BYREF
  PSID Sid1; // [rsp+118h] [rbp+7Fh] BYREF

  v0 = 0;
  v91[0] = 120;
  v93 = 0;
  v92 = &v89;
  hMem = 0;
  v1 = 1;
  v86 = 0;
  v91[2] = 1;
  v87[0] = 1;
  Sid1 = 0;
  v94 = 0;
  v89 = 0;
  v90 = 0;
  v88 = 0;
  v87[1] = v91;
  if ( !(unsigned __int8)SampDsIsRunning() )
    return 0;
  LOBYTE(v2) = 1;
  SampSetDsa(v2);
  v3 = SampDsReadWithClaims(RootObjectName, 0, 1, v87, 0, &v88);
  CurrentOwnerAndPrimaryGroup = v3;
  if ( v3 == -1073741151 )
  {
    if ( (unsigned int)THStateCheckForTraceOverride(v5, v4)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v8, v7)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v8, v7, v9, v10)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
    {
      v13 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v8, v7)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v8, v7, v11, v12)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride(v8, v7)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13) )
      {
        v1 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520488725,
        5,
        13,
        v1,
        v13,
        32,
        &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids);
    }
    return 0;
  }
  if ( v3 < 0 )
    goto LABEL_100;
  if ( (_DWORD)v88 != 1
    || !*((_QWORD *)&v88 + 1)
    || *(_DWORD *)(*((_QWORD *)&v88 + 1) + 8LL) != 1
    || (v15 = *(_QWORD *)(*((_QWORD *)&v88 + 1) + 16LL)) == 0 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v79, v78)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v79, v78)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v79, v78, v80, v81)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v84 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v79, v78)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v79, v78, v82, v83)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride(v79, v78)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
      {
        v1 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520488759,
        2,
        13,
        v1,
        v84,
        34,
        &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids);
    }
    return 3221226215LL;
  }
  v16 = **(_DWORD **)(v15 + 8);
  if ( (unsigned int)THStateCheckForTraceOverride(v5, v4)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v18, v17)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v18, v17, v19, v20)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
  {
    v23 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v18, v17)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v18, v17, v21, v22)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13));
    if ( (unsigned int)THStateCheckForTraceOverride(v18, v17)
      || (v24 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13) == 0, v25 = 0, !v24) )
    {
      v25 = 1;
    }
    WPP_SF__ATTRTYP_LOG_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      520488748,
      5,
      13,
      v25,
      v23,
      33,
      (__int64)&WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids);
  }
  if ( !v16 )
    return 3221226215LL;
  CurrentOwnerAndPrimaryGroup = SampGetCurrentOwnerAndPrimaryGroup(&hMem, &v86);
  if ( CurrentOwnerAndPrimaryGroup < 0 )
    goto LABEL_100;
  CurrentOwnerAndPrimaryGroup = SampSplitSid(*(_QWORD *)v86, &Sid1, &v94);
  if ( CurrentOwnerAndPrimaryGroup < 0 )
    goto LABEL_100;
  if ( v94 == 515 )
  {
    v26 = SampUsingDsData();
    DomainSidFromIndex = (void *)SampGetDomainSidFromIndex(v26 != 0 ? 3 : 1);
    if ( !RtlEqualSid(Sid1, DomainSidFromIndex) )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v29, v28)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v29, v28)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v29, v28, v30, v31)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
      {
        pSid = *(PSID *)hMem;
        v35 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v29, v28)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v29, v28, v33, v34)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v29, v28)
          || (v36 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)) != 0 )
        {
          v36 = 1;
        }
        WPP_SF__sid_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          520488822,
          3,
          13,
          v36,
          v35,
          35,
          &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids,
          pSid);
      }
      CurrentOwnerAndPrimaryGroup = -1073741790;
      goto LABEL_101;
    }
    CurrentOwnerAndPrimaryGroup = SampCheckMachineAccountTreeQuota(*(PSID *)hMem, v16, &v93);
    if ( CurrentOwnerAndPrimaryGroup < 0 )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v40, v39)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v40, v39)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v40, v39, v41, v42)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v43 = *(PSID *)hMem;
        v46 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v40, v39)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v40, v39, v44, v45)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v40, v39)
          || (v47 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
        {
          v47 = 1;
        }
        WPP_SF__sid_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          520488854,
          2,
          13,
          v47,
          v46,
          36,
          &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids,
          v43,
          CurrentOwnerAndPrimaryGroup);
      }
      goto LABEL_100;
    }
LABEL_113:
    if ( v93 < v16 )
    {
      if ( (unsigned int)THStateCheckForTraceOverride(v38, v37)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v72, v71)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v72, v71, v73, v74)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
      {
        v75 = *(PSID *)hMem;
        if ( gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v72, v71)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v72, v71, v76, v77)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
        {
          v0 = 1;
        }
        if ( !(unsigned int)THStateCheckForTraceOverride(v72, v71)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13) )
        {
          v1 = 0;
        }
        WPP_SF__sid_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 520488897, 5, v1, v0, 39, v85, v75, v93, v16);
      }
    }
    else
    {
      CurrentOwnerAndPrimaryGroup = -1073741081;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v65, v64)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v65, v64)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v65, v64, v66, v67)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
      {
        v68 = *(PSID *)hMem;
        if ( gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v65, v64)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v65, v64, v69, v70)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
        {
          v0 = 1;
        }
        if ( !(unsigned int)THStateCheckForTraceOverride(v65, v64)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13) )
        {
          v1 = 0;
        }
        WPP_SF__sid_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 520488889, 3, v1, v0, 38, v85, v68, v93, v16);
      }
    }
    goto LABEL_169;
  }
  CurrentOwnerAndPrimaryGroup = SampCheckUserSimpleQuota(*(PSID *)hMem, v16, &v93);
  if ( CurrentOwnerAndPrimaryGroup >= 0 )
    goto LABEL_113;
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
    || (unsigned int)THStateCheckForTraceOverride(v49, v48)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v49, v48)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v49, v48, v50, v51)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
  {
    v52 = *(PSID *)hMem;
    v55 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v49, v48)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v49, v48, v53, v54)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
    if ( (unsigned int)THStateCheckForTraceOverride(v49, v48)
      || (v56 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
    {
      v56 = 1;
    }
    WPP_SF__sid_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      520488871,
      2,
      13,
      v56,
      v55,
      37,
      &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids,
      v52,
      CurrentOwnerAndPrimaryGroup);
  }
LABEL_100:
  if ( CurrentOwnerAndPrimaryGroup != -1073741081 )
  {
LABEL_101:
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v58, v57)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v58, v57)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v58, v57, v59, v60)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v63 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v58, v57)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v58, v57, v61, v62)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride(v58, v57)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
      {
        v1 = 0;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520488906,
        2,
        13,
        v1,
        v63,
        40,
        (__int64)&WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids);
    }
  }
LABEL_169:
  if ( Sid1 )
    LocalFree(Sid1);
  if ( hMem )
    LocalFree(hMem);
  if ( v86 )
    LocalFree(v86);
  return (unsigned int)CurrentOwnerAndPrimaryGroup;
}

```

## disassembly

```asm
0x1803d99e8  push    rbp
0x1803d99ea  push    rbx
0x1803d99eb  push    rsi
0x1803d99ec  push    rdi
0x1803d99ed  push    r12
0x1803d99ef  push    r13
0x1803d99f1  push    r14
0x1803d99f3  push    r15
0x1803d99f5  lea     rbp, [rsp-1Fh]
0x1803d99fa  sub     rsp, 0B8h
0x1803d9a01  xor     r15d, r15d
0x1803d9a04  mov     [rbp+57h+var_58], 78h ; 'x'
0x1803d9a0b  lea     rax, [rbp+57h+var_68]
0x1803d9a0f  mov     [rbp+57h+arg_0], r15d
0x1803d9a13  mov     [rbp+57h+var_48], rax
0x1803d9a17  xorps   xmm0, xmm0
0x1803d9a1a  lea     rax, [rbp+57h+var_58]
0x1803d9a1e  mov     [rbp+57h+hMem], r15
0x1803d9a22  lea     ebx, [r15+1]
0x1803d9a26  mov     [rbp+57h+var_90], r15
0x1803d9a2a  mov     [rbp+57h+var_50], ebx
0x1803d9a2d  mov     [rbp+57h+var_88], rbx
0x1803d9a31  mov     [rbp+57h+Sid1], r15
0x1803d9a35  mov     [rbp+57h+arg_8], r15d
0x1803d9a39  mov     [rbp+57h+var_68], r15d
0x1803d9a3d  mov     [rbp+57h+var_60], r15
0x1803d9a41  movups  [rbp+57h+var_78], xmm0
0x1803d9a45  mov     [rbp+57h+var_80], rax
0x1803d9a49  call    cs:__imp_SampDsIsRunning
0x1803d9a4f  test    al, al
0x1803d9a51  jz      loc_1803D9B72
0x1803d9a57  mov     cl, bl
0x1803d9a59  call    SampSetDsa
0x1803d9a5e  mov     rcx, cs:RootObjectName
0x1803d9a65  lea     rax, [rbp+57h+var_78]
0x1803d9a69  mov     qword ptr [rsp+0F0h+var_C0], r15
0x1803d9a6e  lea     r9, [rbp+57h+var_88]
0x1803d9a72  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1803d9a77  mov     r8d, ebx
0x1803d9a7a  xor     edx, edx
0x1803d9a7c  mov     qword ptr [rsp+0F0h+var_D0], r15
0x1803d9a81  call    ?SampDsReadWithClaims@@YAJPEAU_DSNAME@@KW4_SAMP_OBJECT_TYPE@@PEAU_ATTRBLOCKSIMPLE@@PEAU_SAMP_CLAIM_CONFIG_ARRAY@@2PEAU_SAM_CLAIMS_ARRAY@@@Z; SampDsReadWithClaims(_DSNAME *,ulong,_SAMP_OBJECT_TYPE,_ATTRBLOCKSIMPLE *,_SAMP_CLAIM_CONFIG_ARRAY *,_ATTRBLOCKSIMPLE *,_SAM_CLAIMS_ARRAY *)
0x1803d9a86  mov     r14d, eax
0x1803d9a89  cmp     eax, 0C00002A1h
0x1803d9a8e  jnz     loc_1803D9B88
0x1803d9a94  call    THStateCheckForTraceOverride
0x1803d9a99  lea     edi, [rbx+0Ch]
0x1803d9a9c  lea     esi, [rbx+4]
0x1803d9a9f  test    eax, eax
0x1803d9aa1  jnz     short loc_1803D9AEB
0x1803d9aa3  mov     r8d, edi
0x1803d9aa6  mov     edx, esi
0x1803d9aa8  xor     ecx, ecx
0x1803d9aaa  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9aaf  test    eax, eax
0x1803d9ab1  jnz     short loc_1803D9AEB
0x1803d9ab3  mov     eax, cs:gfTraceToSecondProvider
0x1803d9ab9  test    eax, eax
0x1803d9abb  jz      loc_1803D9B72
0x1803d9ac1  call    THStateCheckForTraceOverride
0x1803d9ac6  test    eax, eax
0x1803d9ac8  jnz     short loc_1803D9AEB
0x1803d9aca  call    ThStateCheckIfTraceToSecondProvier
0x1803d9acf  test    eax, eax
0x1803d9ad1  jz      loc_1803D9B72
0x1803d9ad7  mov     r8d, edi
0x1803d9ada  mov     edx, esi
0x1803d9adc  mov     ecx, ebx
0x1803d9ade  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9ae3  test    eax, eax
0x1803d9ae5  jz      loc_1803D9B72
0x1803d9aeb  mov     eax, cs:gfTraceToSecondProvider
0x1803d9af1  test    eax, eax
0x1803d9af3  jz      short loc_1803D9B1C
0x1803d9af5  call    THStateCheckForTraceOverride
0x1803d9afa  test    eax, eax
0x1803d9afc  jnz     short loc_1803D9B17
0x1803d9afe  call    ThStateCheckIfTraceToSecondProvier
0x1803d9b03  test    eax, eax
0x1803d9b05  jz      short loc_1803D9B1C
0x1803d9b07  mov     r8d, edi
0x1803d9b0a  mov     edx, esi
0x1803d9b0c  mov     ecx, ebx
0x1803d9b0e  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9b13  test    eax, eax
0x1803d9b15  jz      short loc_1803D9B1C
0x1803d9b17  mov     r14d, ebx
0x1803d9b1a  jmp     short loc_1803D9B1F
0x1803d9b1c  mov     r14d, r15d
0x1803d9b1f  call    THStateCheckForTraceOverride
0x1803d9b24  test    eax, eax
0x1803d9b26  jnz     short loc_1803D9B3B
0x1803d9b28  mov     r8d, edi
0x1803d9b2b  mov     edx, esi
0x1803d9b2d  xor     ecx, ecx
0x1803d9b2f  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9b34  test    eax, eax
0x1803d9b36  jnz     short loc_1803D9B3B
0x1803d9b38  mov     ebx, r15d
0x1803d9b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1803d9b42  lea     r13, WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids
0x1803d9b49  mov     [rsp+0F0h+var_B8], r13; LPCGUID
0x1803d9b4e  mov     r9d, edi; int
0x1803d9b51  mov     [rsp+0F0h+var_C0], 20h ; ' '; __int16
0x1803d9b58  mov     r8d, esi; int
0x1803d9b5b  mov     [rsp+0F0h+var_C8], r14d; int
0x1803d9b60  mov     edx, 1F060715h; int
0x1803d9b65  mov     rcx, [rcx+10h]; int
0x1803d9b69  mov     [rsp+0F0h+var_D0], ebx; int
0x1803d9b6d  call    WPP_SF_
0x1803d9b72  xor     eax, eax
0x1803d9b74  add     rsp, 0B8h
0x1803d9b7b  pop     r15
0x1803d9b7d  pop     r14
0x1803d9b7f  pop     r13
0x1803d9b81  pop     r12
0x1803d9b83  pop     rdi
0x1803d9b84  pop     rsi
0x1803d9b85  pop     rbx
0x1803d9b86  pop     rbp
0x1803d9b87  retn
0x1803d9b88  lea     r13, WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids
0x1803d9b8f  mov     edi, 0Dh
0x1803d9b94  lea     r12d, [rdi-0Bh]
0x1803d9b98  test    eax, eax
0x1803d9b9a  js      loc_1803DA034
0x1803d9ba0  cmp     dword ptr [rbp+57h+var_78], ebx
0x1803d9ba3  jnz     loc_1803DA2AA
0x1803d9ba9  mov     rax, qword ptr [rbp+57h+var_78+8]
0x1803d9bad  test    rax, rax
0x1803d9bb0  jz      loc_1803DA2AA
0x1803d9bb6  cmp     [rax+8], ebx
0x1803d9bb9  jnz     loc_1803DA2AA
0x1803d9bbf  mov     rax, [rax+10h]
0x1803d9bc3  test    rax, rax
0x1803d9bc6  jz      loc_1803DA2AA
0x1803d9bcc  mov     rax, [rax+8]
0x1803d9bd0  mov     r12d, [rax]
0x1803d9bd3  call    THStateCheckForTraceOverride
0x1803d9bd8  lea     esi, [rdi-8]
0x1803d9bdb  test    eax, eax
0x1803d9bdd  jnz     short loc_1803D9C27
0x1803d9bdf  mov     r8d, edi
0x1803d9be2  mov     edx, esi
0x1803d9be4  xor     ecx, ecx
0x1803d9be6  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9beb  test    eax, eax
0x1803d9bed  jnz     short loc_1803D9C27
0x1803d9bef  mov     eax, cs:gfTraceToSecondProvider
0x1803d9bf5  test    eax, eax
0x1803d9bf7  jz      loc_1803D9CB3
0x1803d9bfd  call    THStateCheckForTraceOverride
0x1803d9c02  test    eax, eax
0x1803d9c04  jnz     short loc_1803D9C27
0x1803d9c06  call    ThStateCheckIfTraceToSecondProvier
0x1803d9c0b  test    eax, eax
0x1803d9c0d  jz      loc_1803D9CB3
0x1803d9c13  mov     r8d, edi
0x1803d9c16  mov     edx, esi
0x1803d9c18  mov     ecx, ebx
0x1803d9c1a  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9c1f  test    eax, eax
0x1803d9c21  jz      loc_1803D9CB3
0x1803d9c27  mov     eax, cs:gfTraceToSecondProvider
0x1803d9c2d  test    eax, eax
0x1803d9c2f  jz      short loc_1803D9C58
0x1803d9c31  call    THStateCheckForTraceOverride
0x1803d9c36  test    eax, eax
0x1803d9c38  jnz     short loc_1803D9C53
0x1803d9c3a  call    ThStateCheckIfTraceToSecondProvier
0x1803d9c3f  test    eax, eax
0x1803d9c41  jz      short loc_1803D9C58
0x1803d9c43  mov     r8d, edi
0x1803d9c46  mov     edx, esi
0x1803d9c48  mov     ecx, ebx
0x1803d9c4a  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9c4f  test    eax, eax
0x1803d9c51  jz      short loc_1803D9C58
0x1803d9c53  mov     r14d, ebx
0x1803d9c56  jmp     short loc_1803D9C5B
0x1803d9c58  mov     r14d, r15d
0x1803d9c5b  call    THStateCheckForTraceOverride
0x1803d9c60  test    eax, eax
0x1803d9c62  jnz     short loc_1803D9C77
0x1803d9c64  mov     r8d, edi
0x1803d9c67  mov     edx, esi
0x1803d9c69  xor     ecx, ecx
0x1803d9c6b  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9c70  test    eax, eax
0x1803d9c72  mov     eax, r15d
0x1803d9c75  jz      short loc_1803D9C79
0x1803d9c77  mov     eax, ebx
0x1803d9c79  mov     rcx, cs:WPP_GLOBAL_Control
0x1803d9c80  mov     r9d, edi
0x1803d9c83  mov     dword ptr [rsp+0F0h+var_A8], r12d
0x1803d9c88  mov     r8d, esi
0x1803d9c8b  mov     dword ptr [rsp+0F0h+pSid], r12d
0x1803d9c90  mov     edx, 1F06072Ch
0x1803d9c95  mov     [rsp+0F0h+var_B8], r13; int
0x1803d9c9a  mov     rcx, [rcx+10h]
0x1803d9c9e  mov     [rsp+0F0h+var_C0], 21h ; '!'
0x1803d9ca5  mov     [rsp+0F0h+var_C8], r14d
0x1803d9caa  mov     [rsp+0F0h+var_D0], eax
0x1803d9cae  call    WPP_SF__ATTRTYP_LOG_d
0x1803d9cb3  test    r12d, r12d
0x1803d9cb6  jz      loc_1803DA389
0x1803d9cbc  lea     rdx, [rbp+57h+var_90]
0x1803d9cc0  lea     rcx, [rbp+57h+hMem]
0x1803d9cc4  call    cs:__imp_SampGetCurrentOwnerAndPrimaryGroup
0x1803d9cca  mov     r14d, eax
0x1803d9ccd  test    eax, eax
0x1803d9ccf  js      loc_1803DA034
0x1803d9cd5  mov     rcx, [rbp+57h+var_90]
0x1803d9cd9  lea     r8, [rbp+57h+arg_8]
0x1803d9cdd  lea     rdx, [rbp+57h+Sid1]
0x1803d9ce1  mov     rcx, [rcx]
0x1803d9ce4  call    cs:__imp_SampSplitSid
0x1803d9cea  mov     r14d, eax
0x1803d9ced  test    eax, eax
0x1803d9cef  js      loc_1803DA034
0x1803d9cf5  cmp     [rbp+57h+arg_8], 203h
0x1803d9cfc  jnz     loc_1803D9F1F
0x1803d9d02  call    cs:__imp_SampUsingDsData
0x1803d9d08  neg     al
0x1803d9d0a  sbb     ecx, ecx
0x1803d9d0c  and     ecx, 2
0x1803d9d0f  add     ecx, ebx
0x1803d9d11  call    cs:__imp_SampGetDomainSidFromIndex
0x1803d9d17  mov     rcx, [rbp+57h+Sid1]; Sid1
0x1803d9d1b  mov     rdx, rax; Sid2
0x1803d9d1e  call    cs:__imp_RtlEqualSid
0x1803d9d24  test    al, al
0x1803d9d26  jnz     loc_1803D9E26
0x1803d9d2c  mov     esi, 3
0x1803d9d31  mov     ecx, esi
0x1803d9d33  call    IncrementWPPPerfCountersForLevel
0x1803d9d38  test    eax, eax
0x1803d9d3a  jnz     short loc_1803D9D8D
0x1803d9d3c  call    THStateCheckForTraceOverride
0x1803d9d41  test    eax, eax
0x1803d9d43  jnz     short loc_1803D9D8D
0x1803d9d45  mov     r8d, edi
0x1803d9d48  mov     edx, esi
0x1803d9d4a  xor     ecx, ecx
0x1803d9d4c  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9d51  test    eax, eax
0x1803d9d53  jnz     short loc_1803D9D8D
0x1803d9d55  mov     eax, cs:gfTraceToSecondProvider
0x1803d9d5b  test    eax, eax
0x1803d9d5d  jz      loc_1803D9E1B
0x1803d9d63  call    THStateCheckForTraceOverride
0x1803d9d68  test    eax, eax
0x1803d9d6a  jnz     short loc_1803D9D8D
0x1803d9d6c  call    ThStateCheckIfTraceToSecondProvier
0x1803d9d71  test    eax, eax
0x1803d9d73  jz      loc_1803D9E1B
0x1803d9d79  mov     r8d, edi
0x1803d9d7c  mov     edx, esi
0x1803d9d7e  mov     ecx, ebx
0x1803d9d80  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9d85  test    eax, eax
0x1803d9d87  jz      loc_1803D9E1B
0x1803d9d8d  mov     rax, [rbp+57h+hMem]
0x1803d9d91  mov     r15, [rax]
0x1803d9d94  mov     eax, cs:gfTraceToSecondProvider
0x1803d9d9a  test    eax, eax
0x1803d9d9c  jz      short loc_1803D9DC5
0x1803d9d9e  call    THStateCheckForTraceOverride
0x1803d9da3  test    eax, eax
0x1803d9da5  jnz     short loc_1803D9DC0
0x1803d9da7  call    ThStateCheckIfTraceToSecondProvier
0x1803d9dac  test    eax, eax
0x1803d9dae  jz      short loc_1803D9DC5
0x1803d9db0  mov     r8d, edi
0x1803d9db3  mov     edx, esi
0x1803d9db5  mov     ecx, ebx
0x1803d9db7  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9dbc  test    eax, eax
0x1803d9dbe  jz      short loc_1803D9DC5
0x1803d9dc0  mov     r14d, ebx
0x1803d9dc3  jmp     short loc_1803D9DC8
0x1803d9dc5  xor     r14d, r14d
0x1803d9dc8  call    THStateCheckForTraceOverride
0x1803d9dcd  test    eax, eax
0x1803d9dcf  jnz     short loc_1803D9DE1
0x1803d9dd1  mov     r8d, edi
0x1803d9dd4  mov     edx, esi
0x1803d9dd6  xor     ecx, ecx
0x1803d9dd8  call    CheckWPPLevelFlagsEnabledForProvider
0x1803d9ddd  test    eax, eax
0x1803d9ddf  jz      short loc_1803D9DE3
0x1803d9de1  mov     eax, ebx
0x1803d9de3  mov     rcx, cs:WPP_GLOBAL_Control
0x1803d9dea  mov     r9d, edi; int
0x1803d9ded  mov     [rsp+0F0h+pSid], r15; pSid
0x1803d9df2  mov     r8d, esi; int
0x1803d9df5  mov     [rsp+0F0h+var_B8], r13; LPCGUID
0x1803d9dfa  mov     edx, 1F060776h; int
0x1803d9dff  mov     [rsp+0F0h+var_C0], 23h ; '#'; __int16
0x1803d9e06  mov     rcx, [rcx+10h]; int
  ... truncated ...
```
