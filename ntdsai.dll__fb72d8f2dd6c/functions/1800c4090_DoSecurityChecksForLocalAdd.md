# DoSecurityChecksForLocalAdd

- ea: `0x1800c4090`
- end: `0x1800c5d2a`
- name: `DoSecurityChecksForLocalAdd`
- size: `7322`
- prototype: ``
- caller_count: `2`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011d94`
- `0x180404288`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000dc7c`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180030af8`
- `0x180030b60`
- `0x180033b28`
- `0x180037ce0`
- `0x18003dc50`
- `0x18003dd0c`
- `0x18003dd78`
- `0x180041be0`
- `0x180041f68`
- `0x180048664`
- `0x180049ef0`
- `0x180065310`
- `0x1800b8ae8`
- `0x1800b9324`
- `0x1800bc0e0`
- `0x1800c077c`
- `0x1800c279c`
- `0x1800c3db4`
- `0x1800c4090`
- `0x1800c849c`
- `0x180105898`
- `0x180105bb4`
- `0x180166f10`
- `0x18016a988`
- `0x180172edc`
- `0x180181db0`
- `0x18019c940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c40d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c40d3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800c4f80`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800c4f80`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c50f0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c50f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4f8e`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800c4f2d`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800c4f2d`
- `ntdll!RtlSubAuthoritySid` at `0x1800c4f1d`
- `ntdll!RtlSubAuthoritySid` at `0x1800c4f1d`
- `ntdll!RtlNtStatusToDosError` at `0x1800c455d`
- `ntdll!RtlNtStatusToDosError` at `0x1800c488a`
- `ntdll!RtlNtStatusToDosError` at `0x1800c455d`
- `ntdll!RtlNtStatusToDosError` at `0x1800c488a`
- `ntdll!RtlLengthSid` at `0x1800c494b`
- `ntdll!RtlLengthSid` at `0x1800c50c2`
- `ntdll!RtlLengthSid` at `0x1800c494b`
- `ntdll!RtlLengthSid` at `0x1800c50c2`
- `ADVAPI32!LsaOpenPolicy` at `0x1800c4546`
- `ADVAPI32!LsaOpenPolicy` at `0x1800c4546`
- `ADVAPI32!LsaLookupSids` at `0x1800c4687`
- `ADVAPI32!LsaLookupSids` at `0x1800c4687`
- `ADVAPI32!LsaClose` at `0x1800c4ccc`
- `ADVAPI32!LsaClose` at `0x18045ae8d`
- `ADVAPI32!LsaClose` at `0x1800c4ccc`
- `ADVAPI32!LsaClose` at `0x18045ae8d`
- `ADVAPI32!LsaFreeMemory` at `0x1800c4ca6`
- `ADVAPI32!LsaFreeMemory` at `0x1800c4cb9`
- `ADVAPI32!LsaFreeMemory` at `0x18045ae67`
- `ADVAPI32!LsaFreeMemory` at `0x18045ae7a`
- `ADVAPI32!LsaFreeMemory` at `0x1800c4ca6`
- `ADVAPI32!LsaFreeMemory` at `0x1800c4cb9`
- `ADVAPI32!LsaFreeMemory` at `0x18045ae67`
- `ADVAPI32!LsaFreeMemory` at `0x18045ae7a`

## pseudocode

```c
__int64 __fastcall DoSecurityChecksForLocalAdd(__int64 *a1, __int64 a2, __int64 a3, void *a4, int a5, int a6)
{
  __int64 *v7; // r12
  __int64 *Value; // rdi
  __int64 v9; // r9
  __int64 LastError; // r15
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // r9d
  __int64 v16; // r10
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // esi
  __int64 v22; // rax
  __int64 *v23; // r14
  BOOL v24; // ebx
  BOOL v25; // ecx
  _BYTE *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  BOOL v29; // ebx
  BOOL v30; // ecx
  int v31; // ebx
  unsigned int v32; // r11d
  __int64 v33; // rax
  unsigned int v34; // r9d
  __int64 v35; // r10
  int v36; // edx
  __int64 *v37; // rcx
  int v38; // eax
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rcx
  BOOL v42; // ebx
  int v43; // eax
  NTSTATUS v44; // eax
  NTSTATUS v45; // ebx
  __int64 v46; // rdx
  __int64 v47; // rcx
  BOOL v48; // ebx
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rcx
  BOOL v52; // r15d
  int v53; // eax
  unsigned int v54; // ebx
  int v55; // edx
  __int64 v56; // rdx
  __int64 v57; // rcx
  BOOL v58; // ebx
  BOOL v59; // ecx
  __int64 v60; // rdx
  __int64 v61; // rcx
  BOOL v62; // ebx
  int v63; // eax
  __int16 v64; // cx
  int v65; // edx
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rcx
  BOOL v72; // ebx
  struct _LSA_REFERENCED_DOMAIN_LIST *v73; // rbx
  ULONG v74; // ebx
  struct _SID_IDENTIFIER_AUTHORITY *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rcx
  BOOL v78; // ebx
  __int64 v79; // rbx
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // rdx
  BOOL v83; // ebx
  BOOL v84; // ecx
  int v85; // eax
  int v86; // ecx
  int v87; // eax
  __int64 v88; // rdx
  __int64 v89; // rcx
  BOOL v90; // ebx
  __int64 v91; // rdx
  __int64 v92; // rcx
  BOOL v93; // ebx
  __int64 v94; // rdx
  __int64 v95; // rcx
  BOOL v96; // ebx
  int v97; // eax
  __int64 v98; // rdx
  __int64 v99; // rcx
  BOOL v100; // ebx
  __int64 v101; // rdx
  __int64 v102; // rcx
  BOOL v103; // ebx
  __int64 v104; // rdx
  __int64 v105; // rcx
  BOOL v106; // ebx
  __int64 v107; // rcx
  __int64 v108; // rdx
  __int64 v109; // rcx
  BOOL v110; // ebx
  int v111; // r8d
  int v112; // r9d
  __int64 v113; // rdx
  __int64 v114; // rcx
  BOOL v115; // ebx
  struct _DSNAME *v116; // rdx
  unsigned int v117; // ebx
  __int64 v118; // rdx
  __int64 v119; // rcx
  BOOL v120; // ebx
  __int64 v121; // rdx
  __int64 v122; // rcx
  BOOL v123; // ebx
  int Names; // [rsp+20h] [rbp-218h]
  int nSubAuthority3; // [rsp+28h] [rbp-210h]
  int v127; // [rsp+70h] [rbp-1C8h]
  int v128; // [rsp+74h] [rbp-1C4h]
  PVOID PolicyHandle; // [rsp+80h] [rbp-1B8h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+88h] [rbp-1B0h] BYREF
  int v132; // [rsp+90h] [rbp-1A8h]
  int v133; // [rsp+94h] [rbp-1A4h] BYREF
  PLSA_TRANSLATED_NAME v134; // [rsp+98h] [rbp-1A0h] BYREF
  PSID Sids; // [rsp+A0h] [rbp-198h] BYREF
  __int128 hMem; // [rsp+A8h] [rbp-190h] BYREF
  __int64 v137; // [rsp+B8h] [rbp-180h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-178h] BYREF
  _DWORD v139[4]; // [rsp+F0h] [rbp-148h] BYREF
  PSID v140; // [rsp+100h] [rbp-138h]
  char v141[200]; // [rsp+108h] [rbp-130h] BYREF
  DWORD nSubAuthority1[4]; // [rsp+1D0h] [rbp-68h] BYREF
  __int64 v143; // [rsp+1E0h] [rbp-58h]

  v7 = a1;
  Sids = a4;
  Value = (__int64 *)TlsGetValue(dwTSindex);
  hMem = 0;
  v137 = 0;
  v133 = 0;
  if ( a3 )
  {
    if ( (unsigned int)fNullUuid(a3) )
    {
      v9 = 51723340;
LABEL_4:
      LODWORD(LastError) = DoSetSvcError(5003, 8423, 0, v9);
      goto LABEL_213;
    }
    if ( (unsigned int)fNullUuid(*v7 + 8) )
    {
      *(_OWORD *)v11 = *(_OWORD *)a3;
    }
    else
    {
      v22 = *(_QWORD *)v11 - *(_QWORD *)a3;
      if ( *(_QWORD *)v11 == *(_QWORD *)a3 )
        v22 = *(_QWORD *)(v11 + 8) - *(_QWORD *)(a3 + 8);
      if ( v22 )
      {
        v9 = 51723354;
        goto LABEL_4;
      }
    }
  }
  if ( (unsigned int)fNullUuid(*v7 + 8) )
  {
    if ( (_DWORD)v14 )
      goto LABEL_20;
    DsUuidCreate(v13);
    if ( !(unsigned int)THStateCheckForTraceOverride(v18, v17)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3) )
    {
      if ( !gfTraceToSecondProvider )
        goto LABEL_20;
      if ( !(unsigned int)THStateCheckForTraceOverride(v20, v19) )
      {
        if ( (unsigned int)ThStateCheckIfTraceToSecondProvier() )
        {
          v21 = 1;
          if ( !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3) )
            goto LABEL_21;
          goto LABEL_23;
        }
LABEL_20:
        v21 = 1;
LABEL_21:
        v23 = a1;
        goto LABEL_62;
      }
    }
    v21 = 1;
LABEL_23:
    v24 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v20, v19)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3));
    v25 = (unsigned int)THStateCheckForTraceOverride(v20, v19)
       || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3);
    v23 = a1;
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51723385,
      5,
      3,
      v25,
      v24,
      115,
      (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids,
      *a1 + 8);
    goto LABEL_62;
  }
  if ( !(_DWORD)v14 && (v15 & 0x800) == 0 && (v15 & 0x80000) == 0 && (*((_BYTE *)Value + 5612) & 8) == 0 )
  {
    v26 = (_BYTE *)v7[5];
    if ( (!v26 || (*v26 & 8) == 0) && !(unsigned int)IsAccessGrantedAddGuid(v16) )
    {
      v9 = 51723400;
      goto LABEL_4;
    }
  }
  if ( (unsigned int)THStateCheckForTraceOverride(v13, v12)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3) )
  {
    goto LABEL_50;
  }
  if ( !gfTraceToSecondProvider )
    goto LABEL_20;
  if ( (unsigned int)THStateCheckForTraceOverride(v28, v27) )
  {
LABEL_50:
    v21 = 1;
  }
  else
  {
    if ( !(unsigned int)ThStateCheckIfTraceToSecondProvier() )
      goto LABEL_20;
    v21 = 1;
    if ( !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3) )
      goto LABEL_21;
  }
  v29 = gfTraceToSecondProvider
     && ((unsigned int)THStateCheckForTraceOverride(v28, v27)
      || (unsigned int)ThStateCheckIfTraceToSecondProvier()
      && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3));
  v30 = (unsigned int)THStateCheckForTraceOverride(v28, v27)
     || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3);
  v23 = a1;
  WPP_SF__guid_(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    51723408,
    5,
    3,
    v30,
    v29,
    116,
    (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids,
    *a1 + 8);
LABEL_62:
  LODWORD(LastError) = 0;
  v132 = 0;
  v31 = 0;
  if ( *(_DWORD *)gfADAM )
  {
    v128 = 0;
    v32 = 0;
    do
    {
      if ( v32 )
        v33 = SCGetClassById(Value, *(unsigned int *)(*(_QWORD *)(a2 + 88) + 4LL * (v32 - 1)));
      else
        v33 = a2;
      v34 = *(_DWORD *)(v33 + 100);
      if ( v34 )
      {
        v14 = 0;
        v35 = *(_QWORD *)(v33 + 104);
        do
        {
          if ( *(_DWORD *)(v35 + 4 * v14) == 655366 || *(_DWORD *)(v35 + 4 * v14) == 655604 )
          {
            v128 = 1;
          }
          else if ( *(_DWORD *)(v35 + 4 * v14) == 655605 )
          {
            v31 = 1;
          }
          v14 = (unsigned int)(v14 + 1);
        }
        while ( (unsigned int)v14 < v34 );
      }
      ++v32;
    }
    while ( v32 <= *(_DWORD *)(a2 + 80) );
    LODWORD(LastError) = v132;
    v23 = a1;
    v36 = v128;
  }
  else
  {
    v36 = 0;
    v128 = 0;
  }
  v37 = Value;
  if ( !*(_DWORD *)gfADAM )
    goto LABEL_217;
  if ( !a5 )
    goto LABEL_217;
  if ( dsaInitPhase != 1 )
    goto LABEL_217;
  v38 = *((_DWORD *)Value + 1401);
  if ( (v38 & 0x800) != 0 || (v38 & 0x100) != 0 )
    goto LABEL_217;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ReferencedDomains = 0;
  v134 = 0;
  if ( v36 || !v31 )
  {
    LODWORD(LastError) = 8358;
  }
  else if ( v23[5] )
  {
    LODWORD(LastError) = 8313;
  }
  else
  {
    v39 = LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &PolicyHandle);
    v132 = v39;
    if ( v39 < 0 )
    {
      LODWORD(LastError) = RtlNtStatusToDosError(v39);
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v41, v40)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v41, v40)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
      {
        v42 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v41, v40)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
        if ( (unsigned int)THStateCheckForTraceOverride(v41, v40)
          || (v43 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
        {
          v43 = 1;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51723471,
          2,
          3,
          v43,
          v42,
          117,
          (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
      }
      goto LABEL_204;
    }
    v44 = LsaLookupSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &v134);
    v45 = v44;
    if ( v44 < 0 )
    {
      if ( v44 == -1073741709 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v47, v46)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v48 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          if ( (unsigned int)THStateCheckForTraceOverride(v47, v46)
            || (v49 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
          {
            v49 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51723485,
            2,
            3,
            v49,
            v48,
            118,
            (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
        }
        LODWORD(LastError) = 1317;
      }
      else
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v51, v50)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v51, v50)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v52 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v51, v50)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          if ( (unsigned int)THStateCheckForTraceOverride(v51, v50)
            || (v53 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
          {
            v53 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51723489,
            2,
            3,
            v53,
            v52,
            119,
            (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
        }
        LODWORD(LastError) = RtlNtStatusToDosError(v45);
      }
      goto LABEL_204;
    }
    if ( v134->Use == SidTypeUser )
    {
      memset_0(v139, 0, 0xE0u);
      *(_OWORD *)nSubAuthority1 = 0;
      v143 = 0;
      v54 = *(_DWORD *)(Value[697] + 24);
      v127 = NCLGetNCInfo(*(_DWORD *)(v23[4] + 24), 0, 0, 0, 0, 0, (__int64)v139);
      v55 = v139[0];
      if ( v127 )
        v55 = 0;
      v139[0] = v55;
      v139[1] = 589970;
      v139[2] = RtlLengthSid(Sids);
      v140 = Sids;
      InitCommarg(v141);
      LODWORD(LastError) = LocalFind(v139, nSubAuthority1);
      DBFindDNT(Value[697], v54);
      if ( (_DWORD)LastError == 2 && *(_WORD *)(Value[696] + 12) == 2001 )
      {
        ((void (*)(void))THClearErrors)();
        LODWORD(LastError) = 0;
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
          || (unsigned int)THStateCheckForTraceOverride(v57, v56)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v57, v56)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3)) )
        {
          v58 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v57, v56)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3));
          v59 = (unsigned int)THStateCheckForTraceOverride(v57, v56)
             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3);
          WPP_SF__sid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51723552,
            5,
            3,
            v59,
            v58,
            122,
            &WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids,
            Sids);
        }
        goto LABEL_204;
      }
      if ( (_DWORD)LastError )
      {
        if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
          && !(unsigned int)THStateCheckForTraceOverride(v67, v66)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          && (!gfTraceToSecondProvider
           || !(unsigned int)THStateCheckForTraceOverride(v67, v66)
           && (!(unsigned int)ThStateCheckIfTraceToSecondProvier()
            || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3))) )
        {
          goto LABEL_204;
        }
        v62 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v67, v66)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
        if ( (unsigned int)THStateCheckForTraceOverride(v67, v66)
          || (v63 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
        {
          v63 = 1;
        }
        v64 = 121;
        v65 = 51723544;
      }
      else
      {
        LODWORD(LastError) = 8471;
        if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
          && !(unsigned int)THStateCheckForTraceOverride(v61, v60)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          && (!gfTraceToSecondProvider
           || !(unsigned int)THStateCheckForTraceOverride(v61, v60)
           && (!(unsigned int)ThStateCheckIfTraceToSecondProvier()
            || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3))) )
        {
          goto LABEL_204;
        }
        v62 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v61, v60)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
        if ( (unsigned int)THStateCheckForTraceOverride(v61, v60)
          || (v63 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)) != 0 )
        {
          v63 = 1;
        }
        v64 = 120;
        v65 = 51723539;
      }
      WPP_SF__ATTRTYP_LOG_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v65,
        2,
        3,
        v63,
        v62,
        v64,
        (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
    }
    else
    {
      LODWORD(LastError) = 1317;
    }
  }
LABEL_204:
  if ( v134 )
    LsaFreeMemory(v134);
  if ( ReferencedDomains )
    LsaFreeMemory(ReferencedDomains);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( (_DWORD)LastError )
  {
    DoSetSvcError(5003, 8423, (unsigned int)LastError, 51723568);
LABEL_212:
    v7 = a1;
    goto LABEL_213;
  }
  v37 = Value;
LABEL_217:
  if ( *(_DWORD *)gfADAM )
  {
    if ( (*((_DWORD *)v37 + 1401) & 0x100) == 0 && !a5 )
    {
      v37 = a1;
      if ( !*(_DWORD *)(*a1 + 4) )
      {
        if ( v128 )
        {
          PolicyHandle = 0;
          *(_OWORD *)nSubAuthority1 = 0;
          v69 = *(unsigned int *)(a1[4] + 24);
          if ( (_DWORD)v69 == dword_18052B2F8 || (_DWORD)v69 == dword_18052B288 )
          {
            v73 = (struct _LSA_REFERENCED_DOMAIN_LIST *)((char *)qword_18052B2F0 + 24);
          }
          else
          {
            ReferencedDomains = 0;
            if ( (unsigned int)NCLGetSID(v69, 2 - (unsigned int)(dword_18052B32C != 0), &v134, &ReferencedDomains) )
            {
              LODWORD(LastError) = DoSetSvcError(5001, 8409, 0, 51723594);
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                || (unsigned int)THStateCheckForTraceOverride(v71, v70)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
              {
                v72 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
                if ( !(unsigned int)THStateCheckForTraceOverride(v71, v70)
                  && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
                {
                  v21 = 0;
                }
                WPP_SF__ATTRTYP_LOG_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  51723595,
                  2,
                  3,
                  v21,
                  v72,
                  123,
                  (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
              }
              goto LABEL_212;
            }
            v73 = ReferencedDomains;
          }
          ReferencedDomains = v73;
          DsUuidCreate(nSubAuthority1);
          v74 = *RtlSubAuthoritySid(v73, 0);
          v75 = RtlIdentifierAuthoritySid(ReferencedDomains);
          if ( !AllocateAndInitializeSid(
                  v75,
                  5u,
                  v74,
                  nSubAuthority1[0],
                  nSubAuthority1[1],
                  nSubAuthority1[2],
                  nSubAuthority1[3],
                  0,
                  0,
                  0,
                  &PolicyHandle) )
          {
            LastError = GetLastError();
            DoLogUnhandledError2(51723612, &word_18049B11A, LastError, 1);
            DoSetSvcError(5012, 8431, (unsigned int)LastError, 51723613);
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
              || (unsigned int)THStateCheckForTraceOverride(v77, v76)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v77, v76)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
            {
              v78 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v77, v76)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
              if ( !(unsigned int)THStateCheckForTraceOverride(v77, v76)
                && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
              {
                v21 = 0;
              }
              WPP_SF__ATTRTYP_LOG_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                51723619,
                2,
                3,
                v21,
                v78,
                124,
                (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
            }
            goto LABEL_212;
          }
          v79 = *a1;
          *(_DWORD *)(v79 + 4) = RtlLengthSid(PolicyHandle);
          memcpy_0((void *)(*a1 + 24), PolicyHandle, *(unsigned int *)(*a1 + 4));
          FreeSid(PolicyHandle);
          if ( (unsigned int)THStateCheckForTraceOverride(v81, v80)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v37, v82)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3)) )
          {
            v83 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v37, v82)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 3));
            v84 = (unsigned int)THStateCheckForTraceOverride(v37, v82)
               || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 3);
            WPP_SF__sid_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51723633,
              5,
              3,
              v84,
              v83,
              125,
              &WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids,
              (PSID)(*a1 + 24));
          }
        }
      }
    }
  }
  v85 = *((_DWORD *)Value + 1401);
  if ( (v85 & 0x80000) != 0 )
    return 0;
  v7 = a1;
  if ( a1[5] )
  {
LABEL_437:
    if ( (a1[9] & 0x1000000) == 0 )
      goto LABEL_441;
    v116 = (struct _DSNAME *)qword_18052B2F0;
    if ( !*(_DWORD *)gfADAM )
      v116 = qword_18052B2C0;
    *(_OWORD *)nSubAuthority1 = RIGHT_DS_REPL_MANAGE_REPLICAS;
    if ( (unsigned int)CheckControlAccessOnObjectOptErr(v37, v116, nSubAuthority1, 1) )
    {
LABEL_441:
      v117 = *((_DWORD *)a1 + 2);
      LODWORD(LastError) = CreateSecurityDescriptorForNewObject2(
                             (_DWORD)Value,
                             a2,
                             (_DWORD)a1,
                             DWORD2(hMem),
                             DWORD1(hMem),
                             a6,
                             1,
                             1,
                             0,
                             0);
      if ( (_DWORD)LastError )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v119, v118)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v119, v118)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v120 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v119, v118)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          if ( !(unsigned int)THStateCheckForTraceOverride(v119, v118)
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
          {
            v21 = 0;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51723862,
            2,
            3,
            v21,
            v120,
            134,
            (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
        }
      }
      else
      {
        LODWORD(LastError) = AuditAddedAttributes(Value, a1, a2, *((_DWORD *)a1 + 2) <= v117);
        if ( (_DWORD)LastError
          && ((unsigned int)IncrementWPPPerfCountersForLevel(2)
           || (unsigned int)THStateCheckForTraceOverride(v122, v121)
           || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
           || gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v122, v121)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3))) )
        {
          v123 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v122, v121)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          if ( !(unsigned int)THStateCheckForTraceOverride(v122, v121)
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) )
          {
            v21 = 0;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51723878,
            2,
            3,
            v21,
            v123,
            135,
            (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
        }
      }
    }
    goto LABEL_213;
  }
  if ( *(_DWORD *)gfADAM || dsaInitPhase != 1 || (v85 & 0x800) != 0 || (v85 & 0x100) != 0 )
  {
    v86 = a2;
  }
  else
  {
    v86 = a2;
    if ( *(_DWORD *)(a2 + 20) == 196638 )
    {
      v87 = 1;
      goto LABEL_289;
    }
  }
  v87 = 0;
LABEL_289:
  CheckParentSecurity(a1[4], v86, v14, 0, 1, 0, 0, *a1, &hMem, (unsigned __int64)&v133 & -(__int64)(v87 != 0));
  LODWORD(LastError) = *((_DWORD *)Value + 1390);
  if ( !(_DWORD)LastError )
  {
    CheckParentValidity(a1[4], a2);
    LODWORD(LastError) = *((_DWORD *)Value + 1390);
    if ( (_DWORD)LastError )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v89, v88)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v89, v88)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
      {
        v90 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v89, v88)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v89, v88)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) )
        {
          v21 = 0;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51723693,
          3,
          3,
          v21,
          v90,
          126,
          (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
      }
      goto LABEL_213;
    }
    LODWORD(LastError) = CheckAttributeSecurityForLocalAddWithLogging(
                           (_DWORD)Value,
                           (_DWORD)a1,
                           a2,
                           DWORD2(hMem),
                           DWORD1(hMem),
                           a6);
    if ( (_DWORD)LastError )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v92, v91)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v92, v91)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
      {
        v93 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v92, v91)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v92, v91)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) )
        {
          v21 = 0;
        }
        WPP_SF__ATTRTYP_LOG_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51723711,
          3,
          3,
          v21,
          v93,
          127,
          (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
      }
      goto LABEL_213;
    }
LABEL_345:
    LODWORD(LastError) = CheckAddSecretAndConfidentialSecurity(Value, a1);
    if ( (_DWORD)LastError )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v99, v98)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v99, v98)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
      {
        v100 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v99, v98)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v99, v98)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) )
        {
          v21 = 0;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51723827,
          3,
          3,
          v21,
          v100,
          133,
          (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
      }
      goto LABEL_213;
    }
    goto LABEL_437;
  }
  if ( (Value[702] & 4) != 0 && *(_DWORD *)(a2 + 20) == 196638 )
  {
    *((_DWORD *)Value + 1390) = 0;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
      || (unsigned int)THStateCheckForTraceOverride(v95, v94)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v95, v94)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
    {
      v96 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v95, v94)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
      if ( (unsigned int)THStateCheckForTraceOverride(v95, v94)
        || (v97 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)) != 0 )
      {
        v97 = 1;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51723726,
        3,
        3,
        v97,
        v96,
        128,
        &WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
    }
    goto LABEL_345;
  }
  if ( (_DWORD)LastError == 4 )
  {
    if ( *(_DWORD *)(a2 + 20) != 196638 || (*((_DWORD *)Value + 1401) & 0x2000) != 0 )
      goto LABEL_213;
    if ( v133 )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v105, v104)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v105, v104)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
      {
        v106 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v105, v104)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
        if ( !(unsigned int)THStateCheckForTraceOverride(v105, v104)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) )
        {
          v21 = 0;
        }
        WPP_SF__DS_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51723768,
          3,
          3,
          v21,
          v106,
          130,
          &WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids,
          *a1);
      }
    }
    else
    {
      THClearErrors(a2);
      CheckParentValidity(a1[4], a2);
      LODWORD(LastError) = *((_DWORD *)Value + 1390);
      if ( (_DWORD)LastError )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
          || (unsigned int)THStateCheckForTraceOverride(v109, v108)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v109, v108)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
        {
          v110 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v109, v108)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
          if ( !(unsigned int)THStateCheckForTraceOverride(v109, v108)
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) )
          {
            v21 = 0;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51723788,
            3,
            3,
            v21,
            v110,
            131,
            (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
        }
      }
      else
      {
        THClearErrors(v107);
        LODWORD(LastError) = DoComputerCreateByPrivilegeChecks(
                               (_DWORD)Value,
                               (_DWORD)a1,
                               v111,
                               v112,
                               Names,
                               nSubAuthority3);
        if ( !(_DWORD)LastError )
          goto LABEL_345;
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
          || (unsigned int)THStateCheckForTraceOverride(v114, v113)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v114, v113)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
        {
          v115 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v114, v113)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
          if ( !(unsigned int)THStateCheckForTraceOverride(v114, v113)
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) )
          {
            v21 = 0;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51723810,
            3,
            3,
            v21,
            v115,
            132,
            (__int64)&WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids);
        }
      }
    }
  }
  else if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
         || (unsigned int)THStateCheckForTraceOverride(v102, v101)
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
         || gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v102, v101)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
  {
    v103 = gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v102, v101)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
    if ( !(unsigned int)THStateCheckForTraceOverride(v102, v101)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) )
    {
      v21 = 0;
    }
    WPP_SF__DS_NAME_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51723739,
      3,
      3,
      v21,
      v103,
      129,
      &WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids,
      *a1,
      LastError);
  }
LABEL_213:
  if ( (_DWORD)LastError )
  {
    CheckObjDisclosure(Value, v7[4], 0);
    return *((unsigned int *)Value + 1390);
  }
  return 0;
}

```

## disassembly

```asm
0x1800c4090  push    rbx
0x1800c4092  push    rsi
0x1800c4093  push    rdi
0x1800c4094  push    r12
0x1800c4096  push    r13
0x1800c4098  push    r14
0x1800c409a  push    r15
0x1800c409c  sub     rsp, 200h
0x1800c40a3  mov     rax, cs:__security_cookie
0x1800c40aa  xor     rax, rsp
0x1800c40ad  mov     [rsp+238h+var_48], rax
0x1800c40b5  mov     rbx, r8
0x1800c40b8  mov     qword ptr [rsp+238h+var_1C0], rdx
0x1800c40bd  mov     r12, rcx
0x1800c40c0  mov     [rsp+238h+var_1D0], rcx
0x1800c40c5  mov     [rsp+238h+Sids], r9
0x1800c40cd  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1800c40d3  call    cs:__imp_TlsGetValue
0x1800c40d9  mov     rdi, rax
0x1800c40dc  mov     [rsp+238h+var_1D8], rax
0x1800c40e1  xorps   xmm0, xmm0
0x1800c40e4  xor     eax, eax
0x1800c40e6  movups  [rsp+238h+hMem], xmm0
0x1800c40ee  mov     [rsp+238h+var_180], rax
0x1800c40f6  mov     [rsp+238h+var_1A4], eax
0x1800c40fd  test    rbx, rbx
0x1800c4100  jz      short loc_1800C414A
0x1800c4102  mov     rcx, rbx
0x1800c4105  call    fNullUuid
0x1800c410a  test    eax, eax
0x1800c410c  jz      short loc_1800C412E
0x1800c410e  mov     r9d, 3153C4Ch
0x1800c4114  mov     ecx, 138Bh
0x1800c4119  xor     r8d, r8d
0x1800c411c  mov     edx, 20E7h
0x1800c4121  call    DoSetSvcError
0x1800c4126  mov     r15d, eax
0x1800c4129  jmp     loc_1800C4CF9
0x1800c412e  mov     rcx, [r12]
0x1800c4132  add     rcx, 8
0x1800c4136  call    fNullUuid
0x1800c413b  test    eax, eax
0x1800c413d  jz      loc_1800C41D3
0x1800c4143  movups  xmm0, xmmword ptr [rbx]
0x1800c4146  movdqu  xmmword ptr [rcx], xmm0
0x1800c414a  mov     r10, [r12]
0x1800c414e  lea     rcx, [r10+8]
0x1800c4152  mov     r9d, [rdi+15E4h]
0x1800c4159  mov     r8d, r9d
0x1800c415c  shr     r8d, 9
0x1800c4160  sbb     r8d, r8d
0x1800c4163  call    fNullUuid
0x1800c4168  test    eax, eax
0x1800c416a  jz      loc_1800C42A1
0x1800c4170  test    r8d, r8d
0x1800c4173  jnz     loc_1800C4293
0x1800c4179  call    DsUuidCreate
0x1800c417e  call    THStateCheckForTraceOverride
0x1800c4183  mov     edi, 3
0x1800c4188  lea     r12d, [rdi+2]
0x1800c418c  test    eax, eax
0x1800c418e  jnz     short loc_1800C420D
0x1800c4190  mov     r8d, edi
0x1800c4193  mov     edx, r12d
0x1800c4196  xor     ecx, ecx
0x1800c4198  call    CheckWPPLevelFlagsEnabledForProvider
0x1800c419d  test    eax, eax
0x1800c419f  jnz     short loc_1800C420D
0x1800c41a1  mov     eax, cs:gfTraceToSecondProvider
0x1800c41a7  test    eax, eax
0x1800c41a9  jz      short loc_1800C41F7
0x1800c41ab  call    THStateCheckForTraceOverride
0x1800c41b0  test    eax, eax
0x1800c41b2  jnz     short loc_1800C420D
0x1800c41b4  call    ThStateCheckIfTraceToSecondProvier
0x1800c41b9  test    eax, eax
0x1800c41bb  jz      short loc_1800C41F7
0x1800c41bd  mov     r8d, edi
0x1800c41c0  mov     edx, r12d
0x1800c41c3  lea     esi, [rdi-2]
0x1800c41c6  mov     ecx, esi
0x1800c41c8  call    CheckWPPLevelFlagsEnabledForProvider
0x1800c41cd  test    eax, eax
0x1800c41cf  jnz     short loc_1800C4212
0x1800c41d1  jmp     short loc_1800C41FC
0x1800c41d3  mov     rax, [rcx]
0x1800c41d6  sub     rax, [rbx]
0x1800c41d9  jnz     short loc_1800C41E3
0x1800c41db  mov     rax, [rcx+8]
0x1800c41df  sub     rax, [rbx+8]
0x1800c41e3  test    rax, rax
0x1800c41e6  jz      loc_1800C414A
0x1800c41ec  mov     r9d, 3153C5Ah
0x1800c41f2  jmp     loc_1800C4114
0x1800c41f7  mov     esi, 1
0x1800c41fc  lea     r13, WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids
0x1800c4203  mov     r14, [rsp+238h+var_1D0]
0x1800c4208  jmp     loc_1800C43E2
0x1800c420d  mov     esi, 1
0x1800c4212  mov     eax, cs:gfTraceToSecondProvider
0x1800c4218  test    eax, eax
0x1800c421a  jz      short loc_1800C4243
0x1800c421c  call    THStateCheckForTraceOverride
0x1800c4221  test    eax, eax
0x1800c4223  jnz     short loc_1800C423F
0x1800c4225  call    ThStateCheckIfTraceToSecondProvier
0x1800c422a  test    eax, eax
0x1800c422c  jz      short loc_1800C4243
0x1800c422e  mov     r8d, edi
0x1800c4231  mov     edx, r12d
0x1800c4234  mov     ecx, esi
0x1800c4236  call    CheckWPPLevelFlagsEnabledForProvider
0x1800c423b  test    eax, eax
0x1800c423d  jz      short loc_1800C4243
0x1800c423f  mov     ebx, esi
0x1800c4241  jmp     short loc_1800C4245
0x1800c4243  xor     ebx, ebx
0x1800c4245  call    THStateCheckForTraceOverride
0x1800c424a  test    eax, eax
0x1800c424c  jnz     short loc_1800C4263
0x1800c424e  mov     r8d, edi
0x1800c4251  mov     edx, r12d
0x1800c4254  xor     ecx, ecx
0x1800c4256  call    CheckWPPLevelFlagsEnabledForProvider
0x1800c425b  test    eax, eax
0x1800c425d  jnz     short loc_1800C4263
0x1800c425f  xor     ecx, ecx
0x1800c4261  jmp     short loc_1800C4265
0x1800c4263  mov     ecx, esi
0x1800c4265  mov     r14, [rsp+238h+var_1D0]
0x1800c426a  mov     rax, [r14]
0x1800c426d  add     rax, 8
0x1800c4271  mov     qword ptr [rsp+238h+nSubAuthority6], rax
0x1800c4276  lea     r13, WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids
0x1800c427d  mov     qword ptr [rsp+238h+nSubAuthority5], r13
0x1800c4282  mov     word ptr [rsp+238h+nSubAuthority4], 73h ; 's'
0x1800c4289  mov     edx, 3153C79h
0x1800c428e  jmp     loc_1800C43C4
0x1800c4293  mov     edi, 3
0x1800c4298  lea     r12d, [rdi+2]
0x1800c429c  jmp     loc_1800C41F7
0x1800c42a1  test    r8d, r8d
0x1800c42a4  jnz     short loc_1800C42E3
0x1800c42a6  bt      r9d, 0Bh
0x1800c42ab  jb      short loc_1800C42E3
0x1800c42ad  bt      r9d, 13h
0x1800c42b2  jb      short loc_1800C42E3
0x1800c42b4  test    byte ptr [rdi+15ECh], 8
0x1800c42bb  jnz     short loc_1800C42E3
0x1800c42bd  mov     rax, [r12+28h]
0x1800c42c2  test    rax, rax
0x1800c42c5  jz      short loc_1800C42CC
0x1800c42c7  test    byte ptr [rax], 8
0x1800c42ca  jnz     short loc_1800C42E3
0x1800c42cc  mov     rcx, r10
0x1800c42cf  call    IsAccessGrantedAddGuid
0x1800c42d4  test    eax, eax
0x1800c42d6  jnz     short loc_1800C42E3
0x1800c42d8  mov     r9d, 3153C88h
0x1800c42de  jmp     loc_1800C4114
0x1800c42e3  call    THStateCheckForTraceOverride
0x1800c42e8  mov     edi, 3
0x1800c42ed  lea     r12d, [rdi+2]
0x1800c42f1  test    eax, eax
0x1800c42f3  jnz     short loc_1800C4343
0x1800c42f5  mov     r8d, edi
0x1800c42f8  mov     edx, r12d
0x1800c42fb  xor     ecx, ecx
0x1800c42fd  call    CheckWPPLevelFlagsEnabledForProvider
0x1800c4302  test    eax, eax
0x1800c4304  jnz     short loc_1800C4343
0x1800c4306  mov     eax, cs:gfTraceToSecondProvider
0x1800c430c  test    eax, eax
0x1800c430e  jz      loc_1800C41F7
0x1800c4314  call    THStateCheckForTraceOverride
0x1800c4319  test    eax, eax
0x1800c431b  jnz     short loc_1800C4343
0x1800c431d  call    ThStateCheckIfTraceToSecondProvier
0x1800c4322  test    eax, eax
0x1800c4324  jz      loc_1800C41F7
0x1800c432a  mov     r8d, edi
0x1800c432d  mov     edx, r12d
0x1800c4330  lea     esi, [rdi-2]
0x1800c4333  mov     ecx, esi
0x1800c4335  call    CheckWPPLevelFlagsEnabledForProvider
0x1800c433a  test    eax, eax
0x1800c433c  jnz     short loc_1800C4348
0x1800c433e  jmp     loc_1800C41FC
0x1800c4343  mov     esi, 1
0x1800c4348  mov     eax, cs:gfTraceToSecondProvider
0x1800c434e  test    eax, eax
0x1800c4350  jz      short loc_1800C4379
0x1800c4352  call    THStateCheckForTraceOverride
0x1800c4357  test    eax, eax
0x1800c4359  jnz     short loc_1800C4375
0x1800c435b  call    ThStateCheckIfTraceToSecondProvier
0x1800c4360  test    eax, eax
0x1800c4362  jz      short loc_1800C4379
0x1800c4364  mov     r8d, edi
0x1800c4367  mov     edx, r12d
0x1800c436a  mov     ecx, esi
0x1800c436c  call    CheckWPPLevelFlagsEnabledForProvider
0x1800c4371  test    eax, eax
0x1800c4373  jz      short loc_1800C4379
0x1800c4375  mov     ebx, esi
0x1800c4377  jmp     short loc_1800C437B
0x1800c4379  xor     ebx, ebx
0x1800c437b  call    THStateCheckForTraceOverride
0x1800c4380  test    eax, eax
0x1800c4382  jnz     short loc_1800C4399
0x1800c4384  mov     r8d, edi
0x1800c4387  mov     edx, r12d
0x1800c438a  xor     ecx, ecx
0x1800c438c  call    CheckWPPLevelFlagsEnabledForProvider
0x1800c4391  test    eax, eax
0x1800c4393  jnz     short loc_1800C4399
0x1800c4395  xor     ecx, ecx
0x1800c4397  jmp     short loc_1800C439B
0x1800c4399  mov     ecx, esi
0x1800c439b  mov     r14, [rsp+238h+var_1D0]
0x1800c43a0  mov     rax, [r14]
0x1800c43a3  add     rax, 8
0x1800c43a7  mov     qword ptr [rsp+238h+nSubAuthority6], rax
0x1800c43ac  lea     r13, WPP_5bd57464c3213b04f4fd97c431540a5f_Traceguids
0x1800c43b3  mov     qword ptr [rsp+238h+nSubAuthority5], r13
0x1800c43b8  mov     word ptr [rsp+238h+nSubAuthority4], 74h ; 't'
0x1800c43bf  mov     edx, 3153C90h
0x1800c43c4  mov     [rsp+238h+nSubAuthority3], ebx
0x1800c43c8  mov     dword ptr [rsp+238h+Names], ecx
0x1800c43cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c43d3  mov     r9d, edi
0x1800c43d6  mov     r8d, r12d
0x1800c43d9  mov     rcx, [rcx+10h]
0x1800c43dd  call    WPP_SF__guid_
0x1800c43e2  xor     r15d, r15d
0x1800c43e5  mov     [rsp+238h+var_1A8], r15d
0x1800c43ed  xor     ebx, ebx
0x1800c43ef  cmp     cs:gfADAM, r15d
0x1800c43f6  jz      loc_1800C4481
0x1800c43fc  xor     eax, eax
0x1800c43fe  mov     [rsp+238h+var_1C4], eax
0x1800c4402  xor     r11d, r11d
0x1800c4405  mov     r14, [rsp+238h+var_1D8]
0x1800c440a  mov     r15, qword ptr [rsp+238h+var_1C0]
0x1800c440f  test    r11d, r11d
0x1800c4412  jnz     short loc_1800C4419
0x1800c4414  mov     rax, r15
0x1800c4417  jmp     short loc_1800C442C
0x1800c4419  lea     eax, [r11-1]
0x1800c441d  mov     rdx, [r15+58h]
0x1800c4421  mov     edx, [rdx+rax*4]
0x1800c4424  mov     rcx, r14
0x1800c4427  call    SCGetClassById
0x1800c442c  mov     r9d, [rax+64h]
0x1800c4430  test    r9d, r9d
0x1800c4433  jz      short loc_1800C4465
0x1800c4435  xor     r8d, r8d
0x1800c4438  mov     r10, [rax+68h]
0x1800c443c  mov     edx, [r10+r8*4]
0x1800c4440  sub     edx, 0A0006h
0x1800c4446  jz      short loc_1800C4459
0x1800c4448  sub     edx, 0EEh
0x1800c444e  jz      short loc_1800C4459
0x1800c4450  cmp     edx, 1
0x1800c4453  jnz     short loc_1800C445D
0x1800c4455  mov     ebx, esi
0x1800c4457  jmp     short loc_1800C445D
0x1800c4459  mov     [rsp+238h+var_1C4], esi
0x1800c445d  add     r8d, esi
0x1800c4460  cmp     r8d, r9d
0x1800c4463  jb      short loc_1800C443C
0x1800c4465  add     r11d, esi
0x1800c4468  cmp     r11d, [r15+50h]
0x1800c446c  jbe     short loc_1800C440F
0x1800c446e  mov     r15d, [rsp+238h+var_1A8]
0x1800c4476  mov     r14, [rsp+238h+var_1D0]
0x1800c447b  mov     edx, [rsp+238h+var_1C4]
0x1800c447f  jmp     short loc_1800C4487
0x1800c4481  xor     edx, edx
0x1800c4483  mov     [rsp+238h+var_1C4], edx
0x1800c4487  mov     rcx, [rsp+238h+var_1D8]
0x1800c448c  cmp     cs:gfADAM, 0
0x1800c4493  jz      loc_1800C4D1D
0x1800c4499  cmp     [rsp+238h+arg_20], 0
0x1800c44a1  jbe     loc_1800C4D1D
0x1800c44a7  cmp     cs:dsaInitPhase, esi
0x1800c44ad  jnz     loc_1800C4D1D
0x1800c44b3  mov     eax, [rcx+15E4h]
0x1800c44b9  bt      eax, 0Bh
0x1800c44bd  jb      loc_1800C4D1D
0x1800c44c3  bt      eax, 8
0x1800c44c7  jb      loc_1800C4D1D
0x1800c44cd  mov     [rsp+238h+PolicyHandle], 0
0x1800c44d9  xorps   xmm0, xmm0
0x1800c44dc  movups  xmmword ptr [rsp+238h+ObjectAttributes.Length], xmm0
0x1800c44e4  movups  xmmword ptr [rsp+238h+ObjectAttributes.ObjectName], xmm0
0x1800c44ec  movups  xmmword ptr [rsp+238h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c44f4  mov     [rsp+238h+ReferencedDomains], 0
0x1800c4500  mov     [rsp+238h+var_1A0], 0
0x1800c450c  test    edx, edx
  ... truncated ...
```
