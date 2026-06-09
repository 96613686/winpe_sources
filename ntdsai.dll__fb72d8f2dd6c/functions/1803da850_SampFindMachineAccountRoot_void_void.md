# SampFindMachineAccountRoot(void *,void * *)

- ea: `0x1803da850`
- end: `0x1803db2b2`
- name: `?SampFindMachineAccountRoot@@YAJPEAXPEAPEAX@Z`
- size: `2658`
- prototype: `__int64 __fastcall(PSID pSid, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803d9158`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x180030af8`
- `0x18003dd78`
- `0x18003de48`
- `0x1803da850`
- `0x1803db2b8`
- `0x1803dc46c`
- `0x1803dc57c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803da986`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803da9bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803da9ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803da986`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803da9bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803da9ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803daa24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803daba7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803db15b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803db164`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803db16d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803db198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803daa24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803daba7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803db15b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803db164`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803db16d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803db198`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1803daa1c`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1803daa1c`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1803dab29`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1803dab29`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1803db17f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1803db17f`
- `ntdll!RtlCopySid` at `0x1803da9a9`
- `ntdll!RtlCopySid` at `0x1803da9d5`
- `ntdll!RtlCopySid` at `0x1803da9a9`
- `ntdll!RtlCopySid` at `0x1803da9d5`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1803dab82`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1803dab82`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1803db18a`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1803db18a`
- `ntdll!RtlLengthSid` at `0x1803da973`
- `ntdll!RtlLengthSid` at `0x1803da9b2`
- `ntdll!RtlLengthSid` at `0x1803dab12`
- `ntdll!RtlLengthSid` at `0x1803da973`
- `ntdll!RtlLengthSid` at `0x1803da9b2`
- `ntdll!RtlLengthSid` at `0x1803dab12`

## pseudocode

```c
__int64 __fastcall SampFindMachineAccountRoot(PSID pSid, void **a2)
{
  int v2; // ebp
  PVOID v4; // r12
  struct _RTL_AVL_TABLE *v5; // r15
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r9
  BOOL v13; // edi
  bool v14; // zf
  int v15; // eax
  ULONG v16; // edi
  HLOCAL v17; // rax
  void *v18; // r13
  void *v19; // r14
  ULONG v20; // edi
  HLOCAL v21; // rax
  struct _RTL_AVL_TABLE *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // r9
  BOOL v29; // esi
  int v30; // eax
  CLONG v31; // eax
  int AttributesForAccount; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  char v35; // si
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // r8
  __int64 v41; // r9
  BOOL v42; // esi
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // r8
  __int64 v49; // r9
  BOOL v50; // edi
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // r8
  __int64 v57; // r9
  BOOL v58; // edi
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // r8
  __int64 v65; // r9
  BOOL v66; // esi
  int v67; // eax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // r9
  __int64 v72; // r8
  __int64 v73; // r9
  BOOL v74; // edi
  int v75; // eax
  void **v76; // rsi
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // r8
  __int64 v82; // r9
  BOOL v83; // esi
  int v84; // eax
  __int64 v85; // rdx
  __int64 v86; // rcx
  BOOLEAN i; // dl
  PVOID v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  __int64 v92; // r9
  void *v93; // rsi
  __int64 v94; // r8
  __int64 v95; // r9
  BOOL v96; // edi
  int v98; // [rsp+30h] [rbp-68h]
  int v99; // [rsp+38h] [rbp-60h]
  char v100[4]; // [rsp+50h] [rbp-48h] BYREF
  PVOID Buffer; // [rsp+58h] [rbp-40h] BYREF
  unsigned __int8 NewElement; // [rsp+B0h] [rbp+18h] BYREF
  int v104; // [rsp+B8h] [rbp+20h]

  v2 = 0;
  v4 = 0;
  Buffer = 0;
  v104 = 0;
  v5 = 0;
  *(_DWORD *)v100 = 0;
  *a2 = 0;
  v8 = 1;
  if ( (unsigned int)THStateCheckForTraceOverride(pSid, a2)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v7, v6)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v7, v6, v9, v10)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
  {
    v13 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v7, v6)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v7, v6, v11, v12)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13));
    if ( (unsigned int)THStateCheckForTraceOverride(v7, v6)
      || (v14 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13) == 0, v15 = 0, !v14) )
    {
      v15 = 1;
    }
    WPP_SF__sid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      520488034,
      5,
      13,
      v15,
      v13,
      17,
      &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids,
      pSid);
  }
  v16 = RtlLengthSid(pSid);
  v17 = LocalAlloc(0x40u, v16);
  v18 = v17;
  if ( !v17 )
  {
    v19 = 0;
LABEL_19:
    v2 = -1073741801;
    goto LABEL_154;
  }
  RtlCopySid(v16, v17, pSid);
  v20 = RtlLengthSid(pSid);
  v21 = LocalAlloc(0x40u, v20);
  v19 = v21;
  if ( !v21 )
    goto LABEL_19;
  RtlCopySid(v20, v21, pSid);
  v104 = 0;
  v22 = (struct _RTL_AVL_TABLE *)LocalAlloc(0x40u, 0x68u);
  v5 = v22;
  if ( v22 )
    RtlInitializeGenericTableAvl(v22, SampSidTable_Compare, SampSidTable_Allocate, SampSidTable_Free, 0);
  else
    v2 = -1073741801;
  LocalFree(0);
  if ( v2 >= 0 )
  {
    while ( 1 )
    {
      NewElement = 0;
      v31 = RtlLengthSid(v19);
      if ( !RtlInsertElementGenericTableAvl(v5, v19, v31, &NewElement) )
      {
        v2 = -1073741801;
        goto LABEL_137;
      }
      if ( !NewElement )
      {
        v2 = -1073741595;
        goto LABEL_137;
      }
      AttributesForAccount = SampGetAttributesForAccount(v19, (unsigned int *)v100, &Buffer);
      v4 = Buffer;
      v2 = AttributesForAccount;
      if ( AttributesForAccount == -1073741772 )
      {
        v2 = 0;
        if ( (unsigned int)THStateCheckForTraceOverride(v34, v33)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v69, v68)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v69, v68, v70, v71)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
        {
          v74 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v69, v68)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v69, v68, v72, v73)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v69, v68)
            || (v75 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
          {
            v75 = 1;
          }
          WPP_SF__sid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            520488142,
            4,
            13,
            v75,
            v74,
            19,
            &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids,
            v19);
        }
        goto LABEL_134;
      }
      if ( AttributesForAccount < 0 )
        break;
      if ( Buffer && RtlLookupElementGenericTableAvl(v5, Buffer) )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v37, v36)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v38, v39)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v42 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v40, v41)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v37, v36)
            || (v43 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
          {
            v43 = 1;
          }
          WPP_SF__sid__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, v42, v98, v99, v19, v4);
        }
        v2 = -1073741081;
        goto LABEL_137;
      }
      v35 = v100[0];
      if ( (*(_WORD *)v100 & 0x1000) == 0 )
      {
        if ( (unsigned int)THStateCheckForTraceOverride(v34, v33)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v53, v52)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v53, v52, v54, v55)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
        {
          v58 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v53, v52)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v53, v52, v56, v57)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v53, v52)
            || (v59 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)) != 0 )
          {
            v59 = 1;
          }
          WPP_SF__sid_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            520488194,
            5,
            13,
            v59,
            v58,
            22,
            &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids,
            v19,
            v35);
        }
        goto LABEL_134;
      }
      if ( !v4 )
      {
        if ( (unsigned int)THStateCheckForTraceOverride(v34, v33)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v45, v44)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v45, v44, v46, v47)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
        {
          v50 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v45, v44)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v45, v44, v48, v49)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v45, v44)
            || (v51 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)) != 0 )
          {
            v51 = 1;
          }
          WPP_SF__sid_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            520488206,
            5,
            13,
            v51,
            v50,
            23,
            &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids,
            v19);
        }
LABEL_134:
        v76 = a2;
        *a2 = v18;
        v18 = 0;
        goto LABEL_155;
      }
      LocalFree(v18);
      v18 = v19;
      v19 = v4;
      v4 = 0;
      ++v104;
      Buffer = 0;
    }
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v61, v60)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v61, v60)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v61, v60, v62, v63)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v66 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v61, v60)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v61, v60, v64, v65)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride(v61, v60)
        || (v67 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
      {
        v67 = 1;
      }
      WPP_SF__sid_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520488155,
        2,
        13,
        v67,
        v66,
        20,
        &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids,
        v19,
        v2);
    }
LABEL_137:
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v78, v77)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v78, v77)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v78, v77, v79, v80)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v83 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v78, v77)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v78, v77, v81, v82)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride(v78, v77)
        || (v84 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
      {
        v84 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        520488235,
        2,
        13,
        v84,
        v83,
        24,
        (__int64)&WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids);
    }
  }
  else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
         || (unsigned int)THStateCheckForTraceOverride(v24, v23)
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
         || gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v24, v23)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v24, v23, v25, v26)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
  {
    v29 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v24, v23)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v24, v23, v27, v28)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
    if ( (unsigned int)THStateCheckForTraceOverride(v24, v23)
      || (v30 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
    {
      v30 = 1;
    }
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      520488083,
      2,
      13,
      v30,
      v29,
      18,
      (__int64)&WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids);
  }
LABEL_154:
  v76 = a2;
LABEL_155:
  LocalFree(v4);
  LocalFree(v19);
  LocalFree(v18);
  if ( v5 )
  {
    for ( i = 1; ; i = 0 )
    {
      v88 = RtlEnumerateGenericTableAvl(v5, i);
      if ( !v88 )
        break;
      RtlDeleteElementGenericTableAvl(v5, v88);
    }
    LocalFree(v5);
  }
  if ( v2 >= 0
    && ((unsigned int)THStateCheckForTraceOverride(v86, v85)
     || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)
     || gfTraceToSecondProvider
     && ((unsigned int)THStateCheckForTraceOverride(v90, v89)
      || (unsigned int)ThStateCheckIfTraceToSecondProvier(v90, v89, v91, v92)
      && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13))) )
  {
    v93 = *v76;
    v96 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v90, v89)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v90, v89, v94, v95)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13));
    if ( !(unsigned int)THStateCheckForTraceOverride(v90, v89)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13) )
    {
      v8 = 0;
    }
    WPP_SF__sid_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      520488259,
      5,
      v8,
      v96,
      25,
      &WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids,
      v93,
      v104);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1803da850  mov     rax, rsp
0x1803da853  mov     [rax+8], rbx
0x1803da857  mov     [rax+10h], rdx
0x1803da85b  push    rbp
0x1803da85c  push    rsi
0x1803da85d  push    rdi
0x1803da85e  push    r12
0x1803da860  push    r13
0x1803da862  push    r14
0x1803da864  push    r15
0x1803da866  sub     rsp, 60h
0x1803da86a  xor     ebp, ebp
0x1803da86c  mov     rsi, rcx
0x1803da86f  mov     r12d, ebp
0x1803da872  mov     [rax-40h], rbp
0x1803da876  mov     [rsp+98h+arg_18], ebp
0x1803da87d  mov     r15d, ebp
0x1803da880  mov     [rax-48h], ebp
0x1803da883  mov     [rdx], rbp
0x1803da886  call    THStateCheckForTraceOverride
0x1803da88b  lea     ebx, [rbp+1]
0x1803da88e  lea     r14d, [rbp+0Dh]
0x1803da892  lea     r13d, [rbp+5]
0x1803da896  test    eax, eax
0x1803da898  jnz     short loc_1803DA8E4
0x1803da89a  mov     r8d, r14d
0x1803da89d  mov     edx, r13d
0x1803da8a0  xor     ecx, ecx
0x1803da8a2  call    CheckWPPLevelFlagsEnabledForProvider
0x1803da8a7  test    eax, eax
0x1803da8a9  jnz     short loc_1803DA8E4
0x1803da8ab  mov     eax, cs:gfTraceToSecondProvider
0x1803da8b1  test    eax, eax
0x1803da8b3  jz      loc_1803DA970
0x1803da8b9  call    THStateCheckForTraceOverride
0x1803da8be  test    eax, eax
0x1803da8c0  jnz     short loc_1803DA8E4
0x1803da8c2  call    ThStateCheckIfTraceToSecondProvier
0x1803da8c7  test    eax, eax
0x1803da8c9  jz      loc_1803DA970
0x1803da8cf  mov     r8d, r14d
0x1803da8d2  mov     edx, r13d
0x1803da8d5  mov     ecx, ebx
0x1803da8d7  call    CheckWPPLevelFlagsEnabledForProvider
0x1803da8dc  test    eax, eax
0x1803da8de  jz      loc_1803DA970
0x1803da8e4  mov     eax, cs:gfTraceToSecondProvider
0x1803da8ea  test    eax, eax
0x1803da8ec  jz      short loc_1803DA915
0x1803da8ee  call    THStateCheckForTraceOverride
0x1803da8f3  test    eax, eax
0x1803da8f5  jnz     short loc_1803DA911
0x1803da8f7  call    ThStateCheckIfTraceToSecondProvier
0x1803da8fc  test    eax, eax
0x1803da8fe  jz      short loc_1803DA915
0x1803da900  mov     r8d, r14d
0x1803da903  mov     edx, r13d
0x1803da906  mov     ecx, ebx
0x1803da908  call    CheckWPPLevelFlagsEnabledForProvider
0x1803da90d  test    eax, eax
0x1803da90f  jz      short loc_1803DA915
0x1803da911  mov     edi, ebx
0x1803da913  jmp     short loc_1803DA917
0x1803da915  mov     edi, ebp
0x1803da917  call    THStateCheckForTraceOverride
0x1803da91c  test    eax, eax
0x1803da91e  jnz     short loc_1803DA933
0x1803da920  mov     r8d, r14d
0x1803da923  mov     edx, r13d
0x1803da926  xor     ecx, ecx
0x1803da928  call    CheckWPPLevelFlagsEnabledForProvider
0x1803da92d  test    eax, eax
0x1803da92f  mov     eax, ebp
0x1803da931  jz      short loc_1803DA935
0x1803da933  mov     eax, ebx
0x1803da935  mov     rcx, cs:WPP_GLOBAL_Control
0x1803da93c  lea     rdx, WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids
0x1803da943  mov     [rsp+98h+pSid], rsi; pSid
0x1803da948  mov     r9d, r14d; int
0x1803da94b  mov     [rsp+98h+var_60], rdx; int
0x1803da950  mov     r8d, r13d; int
0x1803da953  mov     [rsp+98h+var_68], 11h; int
0x1803da95a  mov     edx, 1F060462h; int
0x1803da95f  mov     rcx, [rcx+10h]; int
0x1803da963  mov     [rsp+98h+var_70], edi; int
0x1803da967  mov     dword ptr [rsp+98h+TableContext], eax; int
0x1803da96b  call    WPP_SF__sid_
0x1803da970  mov     rcx, rsi; Sid
0x1803da973  call    cs:__imp_RtlLengthSid
0x1803da979  mov     r14d, 40h ; '@'
0x1803da97f  mov     edx, eax; uBytes
0x1803da981  mov     ecx, r14d; uFlags
0x1803da984  mov     edi, eax
0x1803da986  call    cs:__imp_LocalAlloc
0x1803da98c  mov     r13, rax
0x1803da98f  test    rax, rax
0x1803da992  jnz     short loc_1803DA9A1
0x1803da994  mov     r14, rbp
0x1803da997  mov     ebp, 0C0000017h
0x1803da99c  jmp     loc_1803DB150
0x1803da9a1  mov     r8, rsi; SourceSid
0x1803da9a4  mov     rdx, rax; DestinationSid
0x1803da9a7  mov     ecx, edi; DestinationSidLength
0x1803da9a9  call    cs:__imp_RtlCopySid
0x1803da9af  mov     rcx, rsi; Sid
0x1803da9b2  call    cs:__imp_RtlLengthSid
0x1803da9b8  mov     edx, eax; uBytes
0x1803da9ba  mov     ecx, r14d; uFlags
0x1803da9bd  mov     edi, eax
0x1803da9bf  call    cs:__imp_LocalAlloc
0x1803da9c5  mov     r14, rax
0x1803da9c8  test    rax, rax
0x1803da9cb  jz      short loc_1803DA997
0x1803da9cd  mov     r8, rsi; SourceSid
0x1803da9d0  mov     rdx, rax; DestinationSid
0x1803da9d3  mov     ecx, edi; DestinationSidLength
0x1803da9d5  call    cs:__imp_RtlCopySid
0x1803da9db  mov     edx, 68h ; 'h'; uBytes
0x1803da9e0  mov     [rsp+98h+arg_18], ebp
0x1803da9e7  lea     ecx, [rdx-28h]; uFlags
0x1803da9ea  call    cs:__imp_LocalAlloc
0x1803da9f0  mov     r15, rax
0x1803da9f3  test    rax, rax
0x1803da9f6  jnz     short loc_1803DA9FF
0x1803da9f8  mov     ebp, 0C0000017h
0x1803da9fd  jmp     short loc_1803DAA22
0x1803da9ff  lea     r9, ?SampSidTable_Free@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1803daa06  mov     [rsp+98h+TableContext], rbp; TableContext
0x1803daa0b  lea     r8, ?SampSidTable_Allocate@@YAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1803daa12  mov     rcx, rax; Table
0x1803daa15  lea     rdx, ?SampSidTable_Compare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1803daa1c  call    cs:__imp_RtlInitializeGenericTableAvl
0x1803daa22  xor     ecx, ecx; hMem
0x1803daa24  call    cs:__imp_LocalFree
0x1803daa2a  test    ebp, ebp
0x1803daa2c  jns     loc_1803DAB07
0x1803daa32  mov     edi, 2
0x1803daa37  mov     ecx, edi
0x1803daa39  call    IncrementWPPPerfCountersForLevel
0x1803daa3e  test    eax, eax
0x1803daa40  jnz     short loc_1803DAA95
0x1803daa42  call    THStateCheckForTraceOverride
0x1803daa47  test    eax, eax
0x1803daa49  jnz     short loc_1803DAA95
0x1803daa4b  lea     r8d, [rdi+0Bh]
0x1803daa4f  mov     edx, edi
0x1803daa51  xor     ecx, ecx
0x1803daa53  call    CheckWPPLevelFlagsEnabledForProvider
0x1803daa58  test    eax, eax
0x1803daa5a  jnz     short loc_1803DAA95
0x1803daa5c  mov     eax, cs:gfTraceToSecondProvider
0x1803daa62  test    eax, eax
0x1803daa64  jz      loc_1803DB150
0x1803daa6a  call    THStateCheckForTraceOverride
0x1803daa6f  test    eax, eax
0x1803daa71  jnz     short loc_1803DAA95
0x1803daa73  call    ThStateCheckIfTraceToSecondProvier
0x1803daa78  test    eax, eax
0x1803daa7a  jz      loc_1803DB150
0x1803daa80  lea     r8d, [rdi+0Bh]
0x1803daa84  mov     edx, edi
0x1803daa86  mov     ecx, ebx
0x1803daa88  call    CheckWPPLevelFlagsEnabledForProvider
0x1803daa8d  test    eax, eax
0x1803daa8f  jz      loc_1803DB150
0x1803daa95  mov     eax, cs:gfTraceToSecondProvider
0x1803daa9b  test    eax, eax
0x1803daa9d  jz      short loc_1803DAAC8
0x1803daa9f  call    THStateCheckForTraceOverride
0x1803daaa4  test    eax, eax
0x1803daaa6  jnz     short loc_1803DAAC4
0x1803daaa8  call    ThStateCheckIfTraceToSecondProvier
0x1803daaad  test    eax, eax
0x1803daaaf  jz      short loc_1803DAAC8
0x1803daab1  mov     r8d, 0Dh
0x1803daab7  mov     edx, edi
0x1803daab9  mov     ecx, ebx
0x1803daabb  call    CheckWPPLevelFlagsEnabledForProvider
0x1803daac0  test    eax, eax
0x1803daac2  jz      short loc_1803DAAC8
0x1803daac4  mov     esi, ebx
0x1803daac6  jmp     short loc_1803DAACA
0x1803daac8  xor     esi, esi
0x1803daaca  call    THStateCheckForTraceOverride
0x1803daacf  test    eax, eax
0x1803daad1  jnz     short loc_1803DAAE4
0x1803daad3  lea     r8d, [rax+0Dh]
0x1803daad7  mov     edx, edi
0x1803daad9  xor     ecx, ecx
0x1803daadb  call    CheckWPPLevelFlagsEnabledForProvider
0x1803daae0  test    eax, eax
0x1803daae2  jz      short loc_1803DAAE6
0x1803daae4  mov     eax, ebx
0x1803daae6  lea     rdx, WPP_0aac7b318d5c34d26132c5e73fdefd70_Traceguids
0x1803daaed  mov     dword ptr [rsp+98h+pSid], ebp
0x1803daaf1  mov     [rsp+98h+var_60], rdx
0x1803daaf6  mov     edx, 1F060493h
0x1803daafb  mov     [rsp+98h+var_68], 12h
0x1803dab02  jmp     loc_1803DB12F
0x1803dab07  mov     rcx, r14; Sid
0x1803dab0a  mov     [rsp+98h+NewElement], 0
0x1803dab12  call    cs:__imp_RtlLengthSid
0x1803dab18  lea     r9, [rsp+98h+NewElement]; NewElement
0x1803dab20  mov     rdx, r14; Buffer
0x1803dab23  mov     r8d, eax; BufferSize
0x1803dab26  mov     rcx, r15; Table
0x1803dab29  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1803dab2f  mov     edi, 2
0x1803dab34  test    rax, rax
0x1803dab37  jz      loc_1803DB05D
0x1803dab3d  cmp     [rsp+98h+NewElement], 0
0x1803dab45  jz      loc_1803DB056
0x1803dab4b  lea     r8, [rsp+98h+Buffer]; void **
0x1803dab50  mov     rcx, r14; pSid
0x1803dab53  lea     rdx, [rsp+98h+var_48]; unsigned int *
0x1803dab58  call    ?SampGetAttributesForAccount@@YAJPEAXPEAKPEAPEAX@Z; SampGetAttributesForAccount(void *,ulong *,void * *)
0x1803dab5d  mov     r12, [rsp+98h+Buffer]
0x1803dab62  mov     ebp, eax
0x1803dab64  cmp     eax, 0C0000034h
0x1803dab69  jz      loc_1803DAF5C
0x1803dab6f  test    eax, eax
0x1803dab71  js      loc_1803DAE64
0x1803dab77  test    r12, r12
0x1803dab7a  jz      short loc_1803DAB8D
0x1803dab7c  mov     rdx, r12; Buffer
0x1803dab7f  mov     rcx, r15; Table
0x1803dab82  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1803dab88  test    rax, rax
0x1803dab8b  jnz     short loc_1803DABC7
0x1803dab8d  mov     esi, dword ptr [rsp+98h+var_48]
0x1803dab91  bt      esi, 0Ch
0x1803dab95  jnb     loc_1803DAD72
0x1803dab9b  test    r12, r12
0x1803dab9e  jz      loc_1803DACA0
0x1803daba4  mov     rcx, r13; hMem
0x1803daba7  call    cs:__imp_LocalFree
0x1803dabad  mov     r13, r14
0x1803dabb0  mov     r14, r12
0x1803dabb3  xor     r12d, r12d
0x1803dabb6  add     [rsp+98h+arg_18], ebx
0x1803dabbd  mov     [rsp+98h+Buffer], r12
0x1803dabc2  jmp     loc_1803DAB07
0x1803dabc7  mov     ecx, edi
0x1803dabc9  call    IncrementWPPPerfCountersForLevel
0x1803dabce  test    eax, eax
0x1803dabd0  jnz     short loc_1803DAC23
0x1803dabd2  call    THStateCheckForTraceOverride
0x1803dabd7  test    eax, eax
0x1803dabd9  jnz     short loc_1803DAC23
0x1803dabdb  lea     r8d, [rax+0Dh]
0x1803dabdf  mov     edx, edi
0x1803dabe1  xor     ecx, ecx
0x1803dabe3  call    CheckWPPLevelFlagsEnabledForProvider
0x1803dabe8  test    eax, eax
0x1803dabea  jnz     short loc_1803DAC23
0x1803dabec  mov     eax, cs:gfTraceToSecondProvider
0x1803dabf2  test    eax, eax
0x1803dabf4  jz      loc_1803DAC96
0x1803dabfa  call    THStateCheckForTraceOverride
0x1803dabff  test    eax, eax
0x1803dac01  jnz     short loc_1803DAC23
0x1803dac03  call    ThStateCheckIfTraceToSecondProvier
0x1803dac08  test    eax, eax
0x1803dac0a  jz      loc_1803DAC96
0x1803dac10  mov     r8d, 0Dh
0x1803dac16  mov     edx, edi
0x1803dac18  mov     ecx, ebx
0x1803dac1a  call    CheckWPPLevelFlagsEnabledForProvider
0x1803dac1f  test    eax, eax
0x1803dac21  jz      short loc_1803DAC96
0x1803dac23  mov     eax, cs:gfTraceToSecondProvider
0x1803dac29  test    eax, eax
0x1803dac2b  jz      short loc_1803DAC56
0x1803dac2d  call    THStateCheckForTraceOverride
0x1803dac32  test    eax, eax
0x1803dac34  jnz     short loc_1803DAC52
0x1803dac36  call    ThStateCheckIfTraceToSecondProvier
0x1803dac3b  test    eax, eax
0x1803dac3d  jz      short loc_1803DAC56
0x1803dac3f  mov     r8d, 0Dh
0x1803dac45  mov     edx, edi
0x1803dac47  mov     ecx, ebx
0x1803dac49  call    CheckWPPLevelFlagsEnabledForProvider
0x1803dac4e  test    eax, eax
0x1803dac50  jz      short loc_1803DAC56
0x1803dac52  mov     esi, ebx
0x1803dac54  jmp     short loc_1803DAC58
0x1803dac56  xor     esi, esi
0x1803dac58  call    THStateCheckForTraceOverride
0x1803dac5d  test    eax, eax
0x1803dac5f  jnz     short loc_1803DAC72
0x1803dac61  lea     r8d, [rax+0Dh]
0x1803dac65  mov     edx, edi
0x1803dac67  xor     ecx, ecx
0x1803dac69  call    CheckWPPLevelFlagsEnabledForProvider
0x1803dac6e  test    eax, eax
0x1803dac70  jz      short loc_1803DAC74
0x1803dac72  mov     eax, ebx
0x1803dac74  mov     rcx, cs:WPP_GLOBAL_Control
0x1803dac7b  mov     [rsp+98h+var_50], r12; pSid
  ... truncated ...
```
