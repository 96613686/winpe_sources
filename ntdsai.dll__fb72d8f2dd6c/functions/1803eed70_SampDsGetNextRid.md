# SampDsGetNextRid

- ea: `0x1803eed70`
- end: `0x1803ef882`
- name: `SampDsGetNextRid`
- size: `2834`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x18003da40`
- `0x1801675b0`
- `0x180167620`
- `0x180316564`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803e73a4`
- `0x1803e8be0`
- `0x1803ea620`
- `0x1803ebe24`
- `0x1803eed70`
- `0x1803ef888`
- `0x1803f0604`
- `0x1803f1830`
- `0x1803f286c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803eee1c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1803eee1c`
- `ntdll!RtlInitUnicodeString` at `0x1803ef31b`
- `ntdll!RtlInitUnicodeString` at `0x1803ef31b`
- `SAMSRV!SampReleaseSamLockExclusive` at `0x1803ef801`
- `SAMSRV!SampReleaseSamLockExclusive` at `0x1803ef801`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803eee2f`
- `SAMSRV!SampAcquireSamLockExclusive` at `0x1803eee2f`
- `SAMSRV!SampWriteEventLog` at `0x1803ef0f8`
- `SAMSRV!SampWriteEventLog` at `0x1803ef12f`
- `SAMSRV!SampWriteEventLog` at `0x1803ef26a`
- `SAMSRV!SampWriteEventLog` at `0x1803ef34b`
- `SAMSRV!SampWriteEventLog` at `0x1803ef858`
- `SAMSRV!SampWriteEventLog` at `0x1803ef0f8`
- `SAMSRV!SampWriteEventLog` at `0x1803ef12f`
- `SAMSRV!SampWriteEventLog` at `0x1803ef26a`
- `SAMSRV!SampWriteEventLog` at `0x1803ef34b`
- `SAMSRV!SampWriteEventLog` at `0x1803ef858`
- `SAMSRV!SampQueryCapabilities` at `0x1803eedcd`
- `SAMSRV!SampQueryCapabilities` at `0x1803eedcd`

## pseudocode

```c
__int64 __fastcall SampDsGetNextRid(__int64 a1, unsigned int *a2)
{
  unsigned int *v2; // rdi
  char v5; // r13
  int CachedRid; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r9
  BOOL v13; // ebx
  bool v14; // zf
  int v15; // eax
  char v16; // r15
  unsigned int v17; // r14d
  unsigned int v18; // eax
  unsigned int v19; // esi
  unsigned int v20; // r12d
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // r9
  BOOL v27; // ebx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned int *v31; // r14
  unsigned int v32; // ebx
  unsigned int v33; // edi
  unsigned int v34; // edx
  unsigned int v35; // ecx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // r8
  __int64 v41; // r9
  BOOL v42; // ebx
  int v43; // eax
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // r8
  __int64 v50; // r9
  BOOL v51; // ebx
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 v57; // r8
  __int64 v58; // r9
  BOOL v59; // ebx
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 v65; // r8
  __int64 v66; // r9
  BOOL v67; // ebx
  int v68; // eax
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  __int64 v74; // r8
  __int64 v75; // r9
  BOOL v76; // ebx
  int v77; // eax
  _DWORD *v78; // rcx
  int updated; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v80; // [rsp+58h] [rbp-A8h]
  unsigned int v81; // [rsp+60h] [rbp-A0h] BYREF
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *Value; // [rsp+80h] [rbp-80h]
  LPVOID lpTlsValue; // [rsp+88h] [rbp-78h]
  __int64 v86; // [rsp+90h] [rbp-70h]
  _BYTE v87[32]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v88; // [rsp+C0h] [rbp-40h]
  unsigned int v89; // [rsp+C4h] [rbp-3Ch]
  unsigned int v90; // [rsp+C8h] [rbp-38h]
  unsigned int v91; // [rsp+CCh] [rbp-34h]
  unsigned int v92; // [rsp+D8h] [rbp-28h]
  int v93; // [rsp+DCh] [rbp-24h]
  WCHAR SourceString[64]; // [rsp+E0h] [rbp-20h] BYREF

  v80 = a2;
  v2 = a2;
  v86 = a1;
  updated = 0;
  memset_0(v87, 0, 0x40u);
  Src = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v81 = 0;
  if ( (SampQueryCapabilities(0) & 5) == 1 )
    return 3221225659LL;
  v5 = 0;
  if ( SampRidManagerInitialized )
  {
    if ( *(char *)(a1 + 20) >= 0 )
    {
      lpTlsValue = 0;
      Value = 0;
    }
    else
    {
      Value = TlsGetValue(dwTSindex);
      lpTlsValue = (LPVOID)THSave();
      SampAcquireSamLockExclusive();
    }
    updated = SampMaybeBeginDsTransaction(1);
    if ( updated < 0 || (CachedRid = SampGetCachedRid(v2), updated = CachedRid, CachedRid >= 0) )
    {
      v31 = v2;
LABEL_158:
      if ( *(char *)(v86 + 20) < 0 )
      {
        SampMaybeEndDsTransaction((unsigned int)(updated >= 0) + 2);
        if ( updated >= 0 )
        {
          v78 = Value;
          Value[1540] = *v31;
        }
        SampReleaseSamLockExclusive(v78);
        if ( lpTlsValue )
          THRestore(lpTlsValue);
      }
      goto LABEL_163;
    }
    if ( CachedRid != -2147483622
      && ((unsigned int)IncrementWPPPerfCountersForLevel(2)
       || (unsigned int)THStateCheckForTraceOverride(v8, v7)
       || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
       || gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v8, v7)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v8, v7, v9, v10)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13))) )
    {
      v13 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v8, v7)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v8, v7, v11, v12)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride(v8, v7)
        || (v14 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v15 = 0, !v14) )
      {
        v15 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        521803095,
        2,
        13,
        v15,
        v13,
        127,
        (__int64)&WPP_d2048412e6703dba6ac9ed1f61d42af3_Traceguids);
      v2 = v80;
    }
    v93 = 45184;
    updated = SampObtainRidInfo(0, (struct _DSNAME **)&DestinationString, (struct _RIDINFO *)v87);
    if ( updated < 0 )
    {
LABEL_145:
      v31 = v80;
      goto LABEL_158;
    }
    v16 = 0;
    v17 = 0;
    SampDumpRidInfo(v87);
    v18 = v92;
    v19 = v91;
    v20 = v90;
    *v2 = v92;
    if ( v18 <= v19 && v18 <= SampMaximumDomainRid )
    {
      v17 = v18 + 1;
      *v2 = ++v18;
    }
    if ( v18 < SampMinimumDomainRid )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v22, v21)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v22, v21, v23, v24)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
      {
        v27 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v22, v21)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v22, v21, v25, v26)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v22, v21)
          || (v28 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)) != 0 )
        {
          v28 = 1;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521803156,
          3,
          13,
          v28,
          v27,
          128,
          &WPP_d2048412e6703dba6ac9ed1f61d42af3_Traceguids);
      }
      updated = -1073741145;
      SampWriteEventLog(SAMMSG_NO_RIDS_ASSIGNED, L"b", 4, &updated);
      v5 = 1;
      goto LABEL_83;
    }
    if ( v18 > SampMaximumDomainRid )
    {
      updated = -1073741144;
      SampWriteEventLog(SAMMSG_MAX_DOMAIN_RID, L"b", 4, &updated);
      v5 = 1;
      goto LABEL_53;
    }
    v32 = v89;
    v33 = v88;
    if ( v18 > v19 )
    {
      if ( v19 == v89 )
      {
        updated = -1073741144;
        SampWriteEventLog(SAMMSG_MAX_DC_RID, L"b", 4, &updated);
        v5 = 1;
        UnadvertiseDsa();
        goto LABEL_83;
      }
      v34 = v89;
      v35 = v88;
      v19 = v89;
      v20 = v88;
      v16 = 1;
      *v80 = v88;
      v17 = v33;
      SampWarnIfArtificialCeilingApproaching(v35, v34);
    }
    if ( *v80 < v20 && *v80 <= v19 )
    {
      DestinationString = 0;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v37, v36)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v38, v39)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v31 = v80;
        v42 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v40, v41)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v37, v36)
          || (v14 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v43 = 0, !v14) )
        {
          v43 = 1;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521803284,
          2,
          13,
          v43,
          v42,
          129,
          (__int64)&WPP_d2048412e6703dba6ac9ed1f61d42af3_Traceguids);
      }
      else
      {
        v31 = v80;
      }
      v44 = *v31;
      updated = -1073741595;
      if ( (int)RtlStringCbPrintfW(SourceString, 0x80u, L"%lu", v44) < 0 )
        SourceString[0] = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      v5 = 1;
      SampWriteEventLog(SAMMSG_INVALID_RID, L"ub", &DestinationString, 4);
      goto LABEL_158;
    }
    SampComputeRidThreshold(v33, v32, &v81);
    if ( *v80 <= v81 || v19 != v32 )
    {
LABEL_118:
      if ( updated >= 0 )
      {
        if ( v16 )
        {
          v91 = v19;
          v90 = v20;
        }
        v92 = v17;
        v93 = v16 != 0 ? 40960 : 0x8000;
        if ( (unsigned int)THStateCheckForTraceOverride(v30, v29)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v62, v61)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v62, v61, v63, v64)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v67 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v62, v61)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v62, v61, v65, v66)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v62, v61)
            || (v14 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13) == 0, v68 = 0, !v14) )
          {
            v68 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            521803408,
            4,
            13,
            v68,
            v67,
            132,
            &WPP_d2048412e6703dba6ac9ed1f61d42af3_Traceguids);
        }
        SampDumpRidInfo(v87);
        LOBYTE(v69) = 1;
        updated = SampUpdateRidObject(*(_QWORD *)&DestinationString.Length, v87, v69);
        if ( updated < 0 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride(v71, v70)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v72, v73)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
          {
            v76 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v74, v75)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
            if ( (unsigned int)THStateCheckForTraceOverride(v71, v70)
              || (v14 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v77 = 0, !v14) )
            {
              v77 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              521803420,
              2,
              13,
              v77,
              v76,
              133,
              (__int64)&WPP_d2048412e6703dba6ac9ed1f61d42af3_Traceguids);
          }
          goto LABEL_145;
        }
      }
LABEL_53:
      v31 = v80;
      goto LABEL_158;
    }
LABEL_83:
    if ( !SampDcRidRequestPending )
    {
      if ( (unsigned int)THStateCheckForTraceOverride(v30, v29)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v46, v45)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v46, v45, v47, v48)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
      {
        v51 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v46, v45)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v46, v45, v49, v50)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v46, v45)
          || (v52 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
        {
          v52 = 1;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521803339,
          4,
          13,
          v52,
          v51,
          130,
          (__int64)&WPP_d2048412e6703dba6ac9ed1f61d42af3_Traceguids);
      }
      if ( (int)SampFindRidManager(&Src) >= 0 )
      {
        if ( (unsigned int)THStateCheckForTraceOverride(v30, v29)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v54, v53)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v54, v53, v55, v56)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v59 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v54, v53)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v54, v53, v57, v58)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v54, v53)
            || (v60 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v60 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            521803355,
            4,
            13,
            v60,
            v59,
            131,
            &WPP_d2048412e6703dba6ac9ed1f61d42af3_Traceguids);
        }
        SampRequestRidPoolAsynchronously(Src);
      }
    }
    goto LABEL_118;
  }
  updated = SampRidPoolAllocationEnabled != 0 ? -1073741145 : -1073741126;
LABEL_163:
  if ( updated < 0 )
  {
    if ( (unsigned int)(updated + 1073741145) <= 1 && !SampRidPoolAllocationEnabled )
      updated = -1073741126;
    if ( !v5 )
      SampWriteEventLog(SAMMSG_GET_NEXT_RID_ERROR, L"b", 4, &updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1803eed70  push    rbp
0x1803eed72  push    rbx
0x1803eed73  push    rsi
0x1803eed74  push    rdi
0x1803eed75  push    r12
0x1803eed77  push    r13
0x1803eed79  push    r14
0x1803eed7b  push    r15
0x1803eed7d  lea     rbp, [rsp-78h]
0x1803eed82  sub     rsp, 178h
0x1803eed89  mov     rax, cs:__security_cookie
0x1803eed90  xor     rax, rsp
0x1803eed93  mov     [rbp+0B0h+var_50], rax
0x1803eed97  xor     esi, esi
0x1803eed99  mov     [rsp+1B0h+var_158], rdx
0x1803eed9e  mov     rdi, rdx
0x1803eeda1  mov     [rbp+0B0h+var_120], rcx
0x1803eeda5  mov     rbx, rcx
0x1803eeda8  mov     [rsp+1B0h+var_160], esi
0x1803eedac  xor     edx, edx; Val
0x1803eedae  lea     rcx, [rbp+0B0h+var_110]; void *
0x1803eedb2  lea     r8d, [rsi+40h]; Size
0x1803eedb6  call    memset_0
0x1803eedbb  xor     edx, edx
0x1803eedbd  mov     [rsp+1B0h+Src], rsi
0x1803eedc2  xor     ecx, ecx
0x1803eedc4  mov     qword ptr [rsp+1B0h+DestinationString.Length], rsi
0x1803eedc9  mov     [rsp+1B0h+var_150], esi
0x1803eedcd  call    cs:__imp_SampQueryCapabilities
0x1803eedd3  and     al, 5
0x1803eedd5  lea     r15d, [rsi+1]
0x1803eedd9  cmp     al, r15b
0x1803eeddc  jnz     short loc_1803EEDE8
0x1803eedde  mov     eax, 0C00000BBh
0x1803eede3  jmp     loc_1803EF862
0x1803eede8  cmp     cs:SampRidManagerInitialized, sil
0x1803eedef  mov     r13b, sil
0x1803eedf2  jnz     short loc_1803EEE10
0x1803eedf4  mov     eax, cs:?SampRidPoolAllocationEnabled@@3HA; int SampRidPoolAllocationEnabled
0x1803eedfa  neg     eax
0x1803eedfc  sbb     ecx, ecx
0x1803eedfe  and     ecx, 0FFFFFFEDh
0x1803eee01  add     ecx, 0C00002BAh
0x1803eee07  mov     [rsp+1B0h+var_160], ecx
0x1803eee0b  jmp     loc_1803EF818
0x1803eee10  cmp     [rbx+14h], sil
0x1803eee14  jge     short loc_1803EEE37
0x1803eee16  mov     ecx, cs:dwTSindex; dwTlsIndex
0x1803eee1c  call    cs:__imp_TlsGetValue
0x1803eee22  mov     [rbp+0B0h+var_130], rax
0x1803eee26  call    THSave
0x1803eee2b  mov     [rbp+0B0h+lpTlsValue], rax
0x1803eee2f  call    cs:__imp_SampAcquireSamLockExclusive
0x1803eee35  jmp     short loc_1803EEE3F
0x1803eee37  mov     [rbp+0B0h+lpTlsValue], rsi
0x1803eee3b  mov     [rbp+0B0h+var_130], rsi
0x1803eee3f  mov     ecx, r15d
0x1803eee42  call    SampMaybeBeginDsTransaction
0x1803eee47  mov     [rsp+1B0h+var_160], eax
0x1803eee4b  mov     r12d, 2
0x1803eee51  test    eax, eax
0x1803eee53  js      loc_1803EF7D0
0x1803eee59  mov     rcx, rdi; unsigned int *
0x1803eee5c  call    ?SampGetCachedRid@@YAJPEAK@Z; SampGetCachedRid(ulong *)
0x1803eee61  mov     [rsp+1B0h+var_160], eax
0x1803eee65  test    eax, eax
0x1803eee67  jns     loc_1803EF7D0
0x1803eee6d  lea     ebx, [r12+0Bh]
0x1803eee72  lea     r14, WPP_d2048412e6703dba6ac9ed1f61d42af3_Traceguids
0x1803eee79  cmp     eax, 8000001Ah
0x1803eee7e  jz      loc_1803EEF7A
0x1803eee84  mov     ecx, r12d
0x1803eee87  call    IncrementWPPPerfCountersForLevel
0x1803eee8c  test    eax, eax
0x1803eee8e  jnz     short loc_1803EEEE4
0x1803eee90  call    THStateCheckForTraceOverride
0x1803eee95  test    eax, eax
0x1803eee97  jnz     short loc_1803EEEE4
0x1803eee99  mov     r8d, ebx
0x1803eee9c  mov     edx, r12d
0x1803eee9f  xor     ecx, ecx
0x1803eeea1  call    CheckWPPLevelFlagsEnabledForProvider
0x1803eeea6  test    eax, eax
0x1803eeea8  jnz     short loc_1803EEEE4
0x1803eeeaa  mov     eax, cs:gfTraceToSecondProvider
0x1803eeeb0  test    eax, eax
0x1803eeeb2  jz      loc_1803EEF7A
0x1803eeeb8  call    THStateCheckForTraceOverride
0x1803eeebd  test    eax, eax
0x1803eeebf  jnz     short loc_1803EEEE4
0x1803eeec1  call    ThStateCheckIfTraceToSecondProvier
0x1803eeec6  test    eax, eax
0x1803eeec8  jz      loc_1803EEF7A
0x1803eeece  mov     r8d, ebx
0x1803eeed1  mov     edx, r12d
0x1803eeed4  mov     ecx, r15d
0x1803eeed7  call    CheckWPPLevelFlagsEnabledForProvider
0x1803eeedc  test    eax, eax
0x1803eeede  jz      loc_1803EEF7A
0x1803eeee4  mov     eax, cs:gfTraceToSecondProvider
0x1803eeeea  mov     edi, [rsp+1B0h+var_160]
0x1803eeeee  test    eax, eax
0x1803eeef0  jz      short loc_1803EEF1B
0x1803eeef2  call    THStateCheckForTraceOverride
0x1803eeef7  test    eax, eax
0x1803eeef9  jnz     short loc_1803EEF16
0x1803eeefb  call    ThStateCheckIfTraceToSecondProvier
0x1803eef00  test    eax, eax
0x1803eef02  jz      short loc_1803EEF1B
0x1803eef04  mov     r8d, ebx
0x1803eef07  mov     edx, r12d
0x1803eef0a  mov     ecx, r15d
0x1803eef0d  call    CheckWPPLevelFlagsEnabledForProvider
0x1803eef12  test    eax, eax
0x1803eef14  jz      short loc_1803EEF1B
0x1803eef16  mov     ebx, r15d
0x1803eef19  jmp     short loc_1803EEF1D
0x1803eef1b  mov     ebx, esi
0x1803eef1d  call    THStateCheckForTraceOverride
0x1803eef22  test    eax, eax
0x1803eef24  jnz     short loc_1803EEF3A
0x1803eef26  lea     r8d, [rax+0Dh]
0x1803eef2a  mov     edx, r12d
0x1803eef2d  xor     ecx, ecx
0x1803eef2f  call    CheckWPPLevelFlagsEnabledForProvider
0x1803eef34  test    eax, eax
0x1803eef36  mov     eax, esi
0x1803eef38  jz      short loc_1803EEF3D
0x1803eef3a  mov     eax, r15d
0x1803eef3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1803eef44  mov     r8d, r12d
0x1803eef47  mov     [rsp+1B0h+var_170], edi
0x1803eef4b  mov     edx, 1F1A1557h
0x1803eef50  mov     [rsp+1B0h+var_178], r14
0x1803eef55  mov     [rsp+1B0h+var_180], 7Fh
0x1803eef5c  mov     rcx, [rcx+10h]
0x1803eef60  mov     [rsp+1B0h+var_188], ebx
0x1803eef64  mov     ebx, 0Dh
0x1803eef69  mov     r9d, ebx
0x1803eef6c  mov     [rsp+1B0h+var_190], eax
0x1803eef70  call    WPP_SF__ATTRTYP_LOG_
0x1803eef75  mov     rdi, [rsp+1B0h+var_158]
0x1803eef7a  lea     r8, [rbp+0B0h+var_110]; struct _RIDINFO *
0x1803eef7e  mov     [rsp+1B0h+var_160], esi
0x1803eef82  lea     rdx, [rsp+1B0h+DestinationString]; struct _DSNAME **
0x1803eef87  mov     [rbp+0B0h+var_D4], 0B080h
0x1803eef8e  xor     ecx, ecx; struct _DSNAME *
0x1803eef90  call    ?SampObtainRidInfo@@YAHPEAU_DSNAME@@PEAPEAU1@PEAU_RIDINFO@@@Z; SampObtainRidInfo(_DSNAME *,_DSNAME * *,_RIDINFO *)
0x1803eef95  mov     [rsp+1B0h+var_160], eax
0x1803eef99  test    eax, eax
0x1803eef9b  js      loc_1803EF724
0x1803eefa1  lea     rcx, [rbp+0B0h+var_110]
0x1803eefa5  mov     r15b, sil
0x1803eefa8  mov     r14d, esi
0x1803eefab  call    SampDumpRidInfo
0x1803eefb0  mov     eax, [rbp+0B0h+var_D8]
0x1803eefb3  mov     esi, [rbp+0B0h+var_E4]
0x1803eefb6  mov     r12d, [rbp+0B0h+var_E8]
0x1803eefba  mov     [rdi], eax
0x1803eefbc  cmp     eax, esi
0x1803eefbe  ja      short loc_1803EEFD2
0x1803eefc0  cmp     eax, cs:?SampMaximumDomainRid@@3KA; ulong SampMaximumDomainRid
0x1803eefc6  ja      short loc_1803EEFD2
0x1803eefc8  lea     r14d, [rax+1]
0x1803eefcc  mov     [rdi], r14d
0x1803eefcf  mov     eax, r14d
0x1803eefd2  cmp     eax, cs:?SampMinimumDomainRid@@3KA; ulong SampMinimumDomainRid
0x1803eefd8  jnb     loc_1803EF106
0x1803eefde  mov     r13d, 3
0x1803eefe4  mov     ecx, r13d
0x1803eefe7  call    IncrementWPPPerfCountersForLevel
0x1803eefec  test    eax, eax
0x1803eefee  jnz     short loc_1803EF045
0x1803eeff0  call    THStateCheckForTraceOverride
0x1803eeff5  test    eax, eax
0x1803eeff7  jnz     short loc_1803EF045
0x1803eeff9  mov     r8d, ebx
0x1803eeffc  mov     edx, r13d
0x1803eefff  xor     ecx, ecx
0x1803ef001  call    CheckWPPLevelFlagsEnabledForProvider
0x1803ef006  test    eax, eax
0x1803ef008  jnz     short loc_1803EF045
0x1803ef00a  mov     eax, cs:gfTraceToSecondProvider
0x1803ef010  test    eax, eax
0x1803ef012  jz      loc_1803EF0D7
0x1803ef018  call    THStateCheckForTraceOverride
0x1803ef01d  test    eax, eax
0x1803ef01f  jnz     short loc_1803EF045
0x1803ef021  call    ThStateCheckIfTraceToSecondProvier
0x1803ef026  test    eax, eax
0x1803ef028  jz      loc_1803EF0D7
0x1803ef02e  mov     r8d, ebx
0x1803ef031  lea     ecx, [r13-2]
0x1803ef035  mov     edx, r13d
0x1803ef038  call    CheckWPPLevelFlagsEnabledForProvider
0x1803ef03d  test    eax, eax
0x1803ef03f  jz      loc_1803EF0D7
0x1803ef045  mov     eax, cs:gfTraceToSecondProvider
0x1803ef04b  test    eax, eax
0x1803ef04d  jz      short loc_1803EF07C
0x1803ef04f  call    THStateCheckForTraceOverride
0x1803ef054  test    eax, eax
0x1803ef056  jnz     short loc_1803EF075
0x1803ef058  call    ThStateCheckIfTraceToSecondProvier
0x1803ef05d  test    eax, eax
0x1803ef05f  jz      short loc_1803EF07C
0x1803ef061  mov     r8d, ebx
0x1803ef064  mov     edx, r13d
0x1803ef067  mov     ecx, 1
0x1803ef06c  call    CheckWPPLevelFlagsEnabledForProvider
0x1803ef071  test    eax, eax
0x1803ef073  jz      short loc_1803EF07C
0x1803ef075  mov     ebx, 1
0x1803ef07a  jmp     short loc_1803EF07E
0x1803ef07c  xor     ebx, ebx
0x1803ef07e  call    THStateCheckForTraceOverride
0x1803ef083  test    eax, eax
0x1803ef085  jnz     short loc_1803EF099
0x1803ef087  lea     r8d, [rax+0Dh]
0x1803ef08b  mov     edx, r13d
0x1803ef08e  xor     ecx, ecx
0x1803ef090  call    CheckWPPLevelFlagsEnabledForProvider
0x1803ef095  test    eax, eax
0x1803ef097  jz      short loc_1803EF09E
0x1803ef099  mov     eax, 1
0x1803ef09e  lea     rcx, WPP_d2048412e6703dba6ac9ed1f61d42af3_Traceguids
0x1803ef0a5  mov     r9d, 0Dh; int
0x1803ef0ab  mov     [rsp+1B0h+var_178], rcx; LPCGUID
0x1803ef0b0  mov     r8d, r13d; int
0x1803ef0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1803ef0ba  mov     edx, 1F1A1594h; int
0x1803ef0bf  mov     [rsp+1B0h+var_180], 80h; __int16
0x1803ef0c6  mov     [rsp+1B0h+var_188], ebx; int
0x1803ef0ca  mov     [rsp+1B0h+var_190], eax; int
0x1803ef0ce  mov     rcx, [rcx+10h]; int
0x1803ef0d2  call    WPP_SF_
0x1803ef0d7  lea     r9, [rsp+1B0h+var_160]
0x1803ef0dc  mov     [rsp+1B0h+var_160], 0C00002A7h
0x1803ef0e4  mov     r8d, 4
0x1803ef0ea  lea     rdx, aB_1; "b"
0x1803ef0f1  lea     rcx, SAMMSG_NO_RIDS_ASSIGNED
0x1803ef0f8  call    cs:__imp_SampWriteEventLog
0x1803ef0fe  mov     r13b, 1
0x1803ef101  jmp     loc_1803EF37D
0x1803ef106  cmp     eax, cs:?SampMaximumDomainRid@@3KA; ulong SampMaximumDomainRid
0x1803ef10c  jbe     short loc_1803EF150
0x1803ef10e  lea     r9, [rsp+1B0h+var_160]
0x1803ef113  mov     [rsp+1B0h+var_160], 0C00002A8h
0x1803ef11b  mov     r8d, 4
0x1803ef121  lea     rdx, aB_1; "b"
0x1803ef128  lea     rcx, SAMMSG_MAX_DOMAIN_RID
0x1803ef12f  call    cs:__imp_SampWriteEventLog
0x1803ef135  mov     r15d, 1
0x1803ef13b  mov     r13b, r15b
0x1803ef13e  xor     esi, esi
0x1803ef140  mov     r14, [rsp+1B0h+var_158]
0x1803ef145  mov     r12d, 2
0x1803ef14b  jmp     loc_1803EF7D3
0x1803ef150  mov     ebx, [rbp+0B0h+var_EC]
0x1803ef153  mov     edi, [rbp+0B0h+var_F0]
0x1803ef156  cmp     eax, esi
0x1803ef158  jbe     short loc_1803EF17E
0x1803ef15a  cmp     esi, ebx
0x1803ef15c  jz      loc_1803EF249
0x1803ef162  mov     r14, [rsp+1B0h+var_158]
0x1803ef167  mov     edx, ebx; unsigned int
0x1803ef169  mov     ecx, edi; unsigned int
0x1803ef16b  mov     esi, ebx
0x1803ef16d  mov     r12d, edi
0x1803ef170  mov     r15b, 1
0x1803ef173  mov     [r14], edi
0x1803ef176  mov     r14d, edi
0x1803ef179  call    ?SampWarnIfArtificialCeilingApproaching@@YAXKK@Z; SampWarnIfArtificialCeilingApproaching(ulong,ulong)
0x1803ef17e  mov     rax, [rsp+1B0h+var_158]
0x1803ef183  cmp     [rax], r12d
0x1803ef186  jnb     loc_1803EF356
0x1803ef18c  cmp     [rax], esi
0x1803ef18e  ja      loc_1803EF356
0x1803ef194  xorps   xmm0, xmm0
0x1803ef197  movups  xmmword ptr [rsp+1B0h+DestinationString.Length], xmm0
0x1803ef19c  mov     r12d, 2
0x1803ef1a2  mov     ecx, r12d
0x1803ef1a5  call    IncrementWPPPerfCountersForLevel
0x1803ef1aa  xor     esi, esi
0x1803ef1ac  test    eax, eax
0x1803ef1ae  jnz     short loc_1803EF208
0x1803ef1b0  call    THStateCheckForTraceOverride
0x1803ef1b5  test    eax, eax
0x1803ef1b7  jnz     short loc_1803EF208
0x1803ef1b9  lea     r8d, [r12+0Bh]
0x1803ef1be  mov     edx, r12d
0x1803ef1c1  xor     ecx, ecx
0x1803ef1c3  call    CheckWPPLevelFlagsEnabledForProvider
0x1803ef1c8  test    eax, eax
0x1803ef1ca  jnz     short loc_1803EF208
0x1803ef1cc  mov     eax, cs:gfTraceToSecondProvider
0x1803ef1d2  test    eax, eax
0x1803ef1d4  jz      loc_1803EF2E5
0x1803ef1da  call    THStateCheckForTraceOverride
0x1803ef1df  test    eax, eax
  ... truncated ...
```
