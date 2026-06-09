# SampDSEnforceROCAValidationPolicy(_DSNAME *,_NGCKEY_INFO *)

- ea: `0x18042456c`
- end: `0x180424e85`
- name: `?SampDSEnforceROCAValidationPolicy@@YAJPEAU_DSNAME@@PEAU_NGCKEY_INFO@@@Z`
- size: `2329`
- prototype: `__int64 __fastcall(struct _DSNAME *, struct _NGCKEY_INFO *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1803c34b0`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x180048664`
- `0x180423f8c`
- `0x1804243a4`
- `0x18042456c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1804249a6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1804249a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180424d7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180424d7a`
- `ntdll!RtlInitUnicodeString` at `0x180424a37`
- `ntdll!RtlInitUnicodeString` at `0x180424a44`
- `ntdll!RtlInitUnicodeString` at `0x180424a53`
- `ntdll!RtlInitUnicodeString` at `0x180424a37`
- `ntdll!RtlInitUnicodeString` at `0x180424a44`
- `ntdll!RtlInitUnicodeString` at `0x180424a53`
- `SAMSRV!SampQueryPolicyValue` at `0x1804246ba`
- `SAMSRV!SampQueryPolicyValue` at `0x1804246ba`
- `SAMSRV!SampWriteEventLog` at `0x180424ae3`
- `SAMSRV!SampWriteEventLog` at `0x180424c01`
- `SAMSRV!SampWriteEventLog` at `0x180424ae3`
- `SAMSRV!SampWriteEventLog` at `0x180424c01`

## pseudocode

```c
__int64 __fastcall SampDSEnforceROCAValidationPolicy(const WCHAR *a1, struct _NGCKEY_INFO *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // r9
  BOOL v11; // edi
  int v12; // eax
  int v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r9
  BOOL v20; // r14d
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // r8
  __int64 v26; // r9
  BOOL v27; // esi
  int v28; // eax
  BOOL v29; // r15d
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // r9
  BOOL v37; // r14d
  int v38; // eax
  const WCHAR *v39; // r12
  __int64 v40; // rsi
  wchar_t *v41; // rcx
  unsigned __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // r8
  __int64 v48; // r9
  BOOL v49; // esi
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // r8
  __int64 v56; // r9
  BOOL v57; // esi
  int v58; // eax
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // r8
  __int64 v63; // r9
  BOOL v64; // edi
  int v65; // eax
  LPWSTR v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 v71; // r8
  __int64 v72; // r9
  BOOL v73; // edi
  __int64 v75; // [rsp+30h] [rbp-D0h]
  int v76; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v77; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v79; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v80; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v81; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SourceString[72]; // [rsp+A0h] [rbp-60h] BYREF

  LODWORD(v77) = 0;
  v76 = 0;
  DestinationString = 0;
  v81 = 0;
  StringSid = 0;
  v80 = 0;
  v6 = 1;
  if ( (unsigned int)THStateCheckForTraceOverride(a1, a2)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v5, v4)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v5, v4, v7, v8)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
  {
    v11 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v5, v4)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v5, v4, v9, v10)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
    if ( (unsigned int)THStateCheckForTraceOverride(v5, v4)
      || (v12 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)) != 0 )
    {
      v12 = 1;
    }
    WPP_SF__DS_NAME_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      521863630,
      4,
      13,
      v12,
      v11,
      15,
      &WPP_988f817caf2f3378b058edcee6d1eefc_Traceguids,
      (__int64)a1);
  }
  v13 = SampQueryPolicyValue(0, &v76);
  if ( v13 < 0 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v15, v14)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v15, v14)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v15, v14, v16, v17)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v20 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v15, v14)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v15, v14, v18, v19)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride(v15, v14)
        || (v21 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
      {
        v21 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        521863643,
        2,
        13,
        v21,
        v20,
        16,
        (__int64)&WPP_988f817caf2f3378b058edcee6d1eefc_Traceguids);
    }
    goto LABEL_133;
  }
  if ( !v76 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
      || (unsigned int)THStateCheckForTraceOverride(v22, v14)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v22, v14)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v22, v14, v23, v24)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
    {
      v27 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v22, v14)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v22, v14, v25, v26)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
      if ( (unsigned int)THStateCheckForTraceOverride(v22, v14)
        || (v28 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)) != 0 )
      {
        v28 = 1;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        521863653,
        3,
        13,
        v28,
        v27,
        17,
        &WPP_988f817caf2f3378b058edcee6d1eefc_Traceguids);
    }
LABEL_53:
    v13 = 0;
    goto LABEL_133;
  }
  v29 = v76 == 2;
  v13 = RiemannTestBCryptPublicKey(*((unsigned __int8 **)a2 + 3), *((_DWORD *)a2 + 4), (int *)&v77);
  if ( v13 >= 0 )
  {
    if ( !(_DWORD)v77 )
    {
      if ( (unsigned int)THStateCheckForTraceOverride(v31, v30)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v59, v14)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v59, v14, v60, v61)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13)) )
      {
        v64 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v59, v14)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v59, v14, v62, v63)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v59, v14)
          || (v65 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 13)) != 0 )
        {
          v65 = 1;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521863769,
          5,
          13,
          v65,
          v64,
          21,
          &WPP_988f817caf2f3378b058edcee6d1eefc_Traceguids);
      }
      goto LABEL_53;
    }
    v39 = L"<unable to convert>";
    if ( ConvertSidToStringSidW((PSID)(a1 + 12), &StringSid) )
      v39 = StringSid;
    memset_0(SourceString, 0, 0x82u);
    v40 = 0;
    v41 = SourceString;
    v42 = 65;
    v79 = SourceString;
    v77 = 65;
    if ( *(_DWORD *)a2 )
    {
      while ( 1 )
      {
        LODWORD(v75) = *(unsigned __int8 *)(v40 + *((_QWORD *)a2 + 1));
        if ( (int)RtlStringCchPrintfExW(v41, v42, &v79, &v77, 0, L"%02x", v75) < 0 )
          break;
        v40 = (unsigned int)(v40 + 1);
        if ( (unsigned int)v40 >= *(_DWORD *)a2 )
          break;
        v42 = v77;
        v41 = v79;
      }
    }
    RtlInitUnicodeString(&DestinationString, a1 + 28);
    RtlInitUnicodeString(&v81, v39);
    RtlInitUnicodeString(&v80, SourceString);
    if ( !v29 )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v52, v51)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v52, v51)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v52, v51, v53, v54)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13)) )
      {
        v57 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v52, v51)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v52, v51, v55, v56)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v52, v51)
          || (v58 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)) != 0 )
        {
          v58 = 1;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521863749,
          3,
          13,
          v58,
          v57,
          20,
          &WPP_988f817caf2f3378b058edcee6d1eefc_Traceguids);
      }
      SampWriteEventLog(SAMMSG_WHFB_KEY_ROCA_AUDIT, L"uuu", &DestinationString, &v81);
      goto LABEL_53;
    }
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v44, v43)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v44, v43)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v44, v43, v45, v46)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v49 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v44, v43)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v44, v43, v47, v48)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride(v44, v43)
        || (v50 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
      {
        v50 = 1;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        521863729,
        2,
        13,
        v50,
        v49,
        19,
        &WPP_988f817caf2f3378b058edcee6d1eefc_Traceguids);
    }
    SampWriteEventLog(SAMMSG_WHFB_KEY_ROCA_BLOCK, L"uuu", &DestinationString, &v81);
    v13 = -1073741389;
  }
  else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
         || (unsigned int)THStateCheckForTraceOverride(v32, v14)
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
         || gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v32, v14)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v32, v14, v33, v34)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
  {
    v37 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v32, v14)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v32, v14, v35, v36)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
    if ( (unsigned int)THStateCheckForTraceOverride(v32, v14)
      || (v38 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
    {
      v38 = 1;
    }
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      521863673,
      2,
      13,
      v38,
      v37,
      18,
      (__int64)&WPP_988f817caf2f3378b058edcee6d1eefc_Traceguids);
  }
LABEL_133:
  v66 = StringSid;
  if ( StringSid )
    LocalFree(StringSid);
  if ( (unsigned int)THStateCheckForTraceOverride(v66, v14)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v68, v67)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v68, v67, v69, v70)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13)) )
  {
    v73 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v68, v67)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v68, v67, v71, v72)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 13));
    if ( !(unsigned int)THStateCheckForTraceOverride(v68, v67)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 13) )
    {
      v6 = 0;
    }
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      521863784,
      4,
      13,
      v6,
      v73,
      22,
      (__int64)&WPP_988f817caf2f3378b058edcee6d1eefc_Traceguids);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18042456c  mov     [rsp-8+arg_10], rbx
0x180424571  push    rbp
0x180424572  push    rsi
0x180424573  push    rdi
0x180424574  push    r12
0x180424576  push    r13
0x180424578  push    r14
0x18042457a  push    r15
0x18042457c  lea     rbp, [rsp-40h]
0x180424581  sub     rsp, 140h
0x180424588  mov     rax, cs:__security_cookie
0x18042458f  xor     rax, rsp
0x180424592  mov     [rbp+70h+var_40], rax
0x180424596  xorps   xmm0, xmm0
0x180424599  mov     dword ptr [rsp+170h+var_118], 0
0x1804245a1  xorps   xmm1, xmm1
0x1804245a4  mov     [rsp+170h+var_120], 0
0x1804245ac  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x1804245b0  mov     r14, rdx
0x1804245b3  mov     r13, rcx
0x1804245b6  movups  xmmword ptr [rbp+70h+var_F0.Length], xmm1
0x1804245ba  mov     [rsp+170h+StringSid], 0
0x1804245c3  movups  xmmword ptr [rsp+170h+var_100.Length], xmm0
0x1804245c8  call    THStateCheckForTraceOverride
0x1804245cd  lea     r15, WPP_988f817caf2f3378b058edcee6d1eefc_Traceguids
0x1804245d4  mov     ebx, 1
0x1804245d9  lea     r12d, [rbx+0Ch]
0x1804245dd  test    eax, eax
0x1804245df  jnz     short loc_18042462B
0x1804245e1  mov     r8d, r12d
0x1804245e4  lea     edx, [rbx+3]
0x1804245e7  xor     ecx, ecx
0x1804245e9  call    CheckWPPLevelFlagsEnabledForProvider
0x1804245ee  test    eax, eax
0x1804245f0  jnz     short loc_18042462B
0x1804245f2  mov     eax, cs:gfTraceToSecondProvider
0x1804245f8  test    eax, eax
0x1804245fa  jz      loc_1804246B3
0x180424600  call    THStateCheckForTraceOverride
0x180424605  test    eax, eax
0x180424607  jnz     short loc_18042462B
0x180424609  call    ThStateCheckIfTraceToSecondProvier
0x18042460e  test    eax, eax
0x180424610  jz      loc_1804246B3
0x180424616  mov     r8d, r12d
0x180424619  lea     edx, [rbx+3]
0x18042461c  mov     ecx, ebx
0x18042461e  call    CheckWPPLevelFlagsEnabledForProvider
0x180424623  test    eax, eax
0x180424625  jz      loc_1804246B3
0x18042462b  mov     eax, cs:gfTraceToSecondProvider
0x180424631  test    eax, eax
0x180424633  jz      short loc_18042465E
0x180424635  call    THStateCheckForTraceOverride
0x18042463a  test    eax, eax
0x18042463c  jnz     short loc_18042465A
0x18042463e  call    ThStateCheckIfTraceToSecondProvier
0x180424643  test    eax, eax
0x180424645  jz      short loc_18042465E
0x180424647  mov     r8d, r12d
0x18042464a  mov     edx, 4
0x18042464f  mov     ecx, ebx
0x180424651  call    CheckWPPLevelFlagsEnabledForProvider
0x180424656  test    eax, eax
0x180424658  jz      short loc_18042465E
0x18042465a  mov     edi, ebx
0x18042465c  jmp     short loc_180424660
0x18042465e  xor     edi, edi
0x180424660  call    THStateCheckForTraceOverride
0x180424665  test    eax, eax
0x180424667  jnz     short loc_18042467A
0x180424669  mov     r8d, r12d
0x18042466c  lea     edx, [rax+4]
0x18042466f  xor     ecx, ecx
0x180424671  call    CheckWPPLevelFlagsEnabledForProvider
0x180424676  test    eax, eax
0x180424678  jz      short loc_18042467C
0x18042467a  mov     eax, ebx
0x18042467c  mov     rcx, cs:WPP_GLOBAL_Control
0x180424683  mov     r9d, r12d; int
0x180424686  mov     [rsp+170h+var_130], r13; __int64
0x18042468b  mov     edx, 1F1B01CEh; int
0x180424690  mov     [rsp+170h+var_138], r15; LPCGUID
0x180424695  mov     r8d, 4; int
0x18042469b  mov     [rsp+170h+var_140], 0Fh; __int16
0x1804246a2  mov     rcx, [rcx+10h]; int
0x1804246a6  mov     dword ptr [rsp+170h+var_148], edi; int
0x1804246aa  mov     [rsp+170h+var_150], eax; int
0x1804246ae  call    WPP_SF__DS_NAME_
0x1804246b3  lea     rdx, [rsp+170h+var_120]
0x1804246b8  xor     ecx, ecx
0x1804246ba  call    cs:__imp_SampQueryPolicyValue
0x1804246c0  mov     esi, eax
0x1804246c2  test    eax, eax
0x1804246c4  jns     loc_1804247B3
0x1804246ca  mov     edi, 2
0x1804246cf  mov     ecx, edi
0x1804246d1  call    IncrementWPPPerfCountersForLevel
0x1804246d6  test    eax, eax
0x1804246d8  jnz     short loc_18042472B
0x1804246da  call    THStateCheckForTraceOverride
0x1804246df  test    eax, eax
0x1804246e1  jnz     short loc_18042472B
0x1804246e3  mov     r8d, r12d
0x1804246e6  mov     edx, edi
0x1804246e8  xor     ecx, ecx
0x1804246ea  call    CheckWPPLevelFlagsEnabledForProvider
0x1804246ef  test    eax, eax
0x1804246f1  jnz     short loc_18042472B
0x1804246f3  mov     eax, cs:gfTraceToSecondProvider
0x1804246f9  test    eax, eax
0x1804246fb  jz      loc_180424D70
0x180424701  call    THStateCheckForTraceOverride
0x180424706  test    eax, eax
0x180424708  jnz     short loc_18042472B
0x18042470a  call    ThStateCheckIfTraceToSecondProvier
0x18042470f  test    eax, eax
0x180424711  jz      loc_180424D70
0x180424717  mov     r8d, r12d
0x18042471a  mov     edx, edi
0x18042471c  mov     ecx, ebx
0x18042471e  call    CheckWPPLevelFlagsEnabledForProvider
0x180424723  test    eax, eax
0x180424725  jz      loc_180424D70
0x18042472b  mov     eax, cs:gfTraceToSecondProvider
0x180424731  test    eax, eax
0x180424733  jz      short loc_18042475C
0x180424735  call    THStateCheckForTraceOverride
0x18042473a  test    eax, eax
0x18042473c  jnz     short loc_180424757
0x18042473e  call    ThStateCheckIfTraceToSecondProvier
0x180424743  test    eax, eax
0x180424745  jz      short loc_18042475C
0x180424747  mov     r8d, r12d
0x18042474a  mov     edx, edi
0x18042474c  mov     ecx, ebx
0x18042474e  call    CheckWPPLevelFlagsEnabledForProvider
0x180424753  test    eax, eax
0x180424755  jz      short loc_18042475C
0x180424757  mov     r14d, ebx
0x18042475a  jmp     short loc_18042475F
0x18042475c  xor     r14d, r14d
0x18042475f  call    THStateCheckForTraceOverride
0x180424764  test    eax, eax
0x180424766  jnz     short loc_180424778
0x180424768  mov     r8d, r12d
0x18042476b  mov     edx, edi
0x18042476d  xor     ecx, ecx
0x18042476f  call    CheckWPPLevelFlagsEnabledForProvider
0x180424774  test    eax, eax
0x180424776  jz      short loc_18042477A
0x180424778  mov     eax, ebx
0x18042477a  mov     dword ptr [rsp+170h+var_130], esi
0x18042477e  mov     edx, 1F1B01DBh
0x180424783  mov     [rsp+170h+var_138], r15
0x180424788  mov     [rsp+170h+var_140], 10h
0x18042478f  mov     rcx, cs:WPP_GLOBAL_Control
0x180424796  mov     r8d, edi
0x180424799  mov     dword ptr [rsp+170h+var_148], r14d
0x18042479e  mov     r9d, r12d
0x1804247a1  mov     [rsp+170h+var_150], eax
0x1804247a5  mov     rcx, [rcx+10h]
0x1804247a9  call    WPP_SF__ATTRTYP_LOG_
0x1804247ae  jmp     loc_180424D70
0x1804247b3  mov     eax, [rsp+170h+var_120]
0x1804247b7  test    eax, eax
0x1804247b9  jnz     loc_18042489D
0x1804247bf  lea     edi, [rax+3]
0x1804247c2  mov     ecx, edi
0x1804247c4  call    IncrementWPPPerfCountersForLevel
0x1804247c9  test    eax, eax
0x1804247cb  jnz     short loc_18042481A
0x1804247cd  call    THStateCheckForTraceOverride
0x1804247d2  test    eax, eax
0x1804247d4  jnz     short loc_18042481A
0x1804247d6  mov     r8d, r12d
0x1804247d9  mov     edx, edi
0x1804247db  xor     ecx, ecx
0x1804247dd  call    CheckWPPLevelFlagsEnabledForProvider
0x1804247e2  test    eax, eax
0x1804247e4  jnz     short loc_18042481A
0x1804247e6  mov     eax, cs:gfTraceToSecondProvider
0x1804247ec  test    eax, eax
0x1804247ee  jz      loc_180424896
0x1804247f4  call    THStateCheckForTraceOverride
0x1804247f9  test    eax, eax
0x1804247fb  jnz     short loc_18042481A
0x1804247fd  call    ThStateCheckIfTraceToSecondProvier
0x180424802  test    eax, eax
0x180424804  jz      loc_180424896
0x18042480a  mov     r8d, r12d
0x18042480d  mov     edx, edi
0x18042480f  mov     ecx, ebx
0x180424811  call    CheckWPPLevelFlagsEnabledForProvider
0x180424816  test    eax, eax
0x180424818  jz      short loc_180424896
0x18042481a  mov     eax, cs:gfTraceToSecondProvider
0x180424820  test    eax, eax
0x180424822  jz      short loc_18042484A
0x180424824  call    THStateCheckForTraceOverride
0x180424829  test    eax, eax
0x18042482b  jnz     short loc_180424846
0x18042482d  call    ThStateCheckIfTraceToSecondProvier
0x180424832  test    eax, eax
0x180424834  jz      short loc_18042484A
0x180424836  mov     r8d, r12d
0x180424839  mov     edx, edi
0x18042483b  mov     ecx, ebx
0x18042483d  call    CheckWPPLevelFlagsEnabledForProvider
0x180424842  test    eax, eax
0x180424844  jz      short loc_18042484A
0x180424846  mov     esi, ebx
0x180424848  jmp     short loc_18042484C
0x18042484a  xor     esi, esi
0x18042484c  call    THStateCheckForTraceOverride
0x180424851  test    eax, eax
0x180424853  jnz     short loc_180424865
0x180424855  mov     r8d, r12d
0x180424858  mov     edx, edi
0x18042485a  xor     ecx, ecx
0x18042485c  call    CheckWPPLevelFlagsEnabledForProvider
0x180424861  test    eax, eax
0x180424863  jz      short loc_180424867
0x180424865  mov     eax, ebx
0x180424867  mov     [rsp+170h+var_138], r15; LPCGUID
0x18042486c  mov     r8d, edi; int
0x18042486f  mov     [rsp+170h+var_140], 11h; __int16
0x180424876  mov     edx, 1F1B01E5h; int
0x18042487b  mov     dword ptr [rsp+170h+var_148], esi; int
0x18042487f  mov     rcx, cs:WPP_GLOBAL_Control
0x180424886  mov     r9d, r12d; int
0x180424889  mov     [rsp+170h+var_150], eax; int
0x18042488d  mov     rcx, [rcx+10h]; int
0x180424891  call    WPP_SF_
0x180424896  xor     esi, esi
0x180424898  jmp     loc_180424D70
0x18042489d  mov     edx, [r14+10h]; unsigned int
0x1804248a1  lea     r8, [rsp+170h+var_118]; int *
0x1804248a6  mov     rcx, [r14+18h]; unsigned __int8 *
0x1804248aa  xor     r15d, r15d
0x1804248ad  lea     edi, [r15+2]
0x1804248b1  cmp     eax, edi
0x1804248b3  setz    r15b
0x1804248b7  call    ?RiemannTestBCryptPublicKey@@YAJPEAEKPEAH@Z; RiemannTestBCryptPublicKey(uchar *,ulong,int *)
0x1804248bc  mov     esi, eax
0x1804248be  test    eax, eax
0x1804248c0  jns     loc_180424992
0x1804248c6  mov     ecx, edi
0x1804248c8  call    IncrementWPPPerfCountersForLevel
0x1804248cd  test    eax, eax
0x1804248cf  jnz     short loc_180424922
0x1804248d1  call    THStateCheckForTraceOverride
0x1804248d6  test    eax, eax
0x1804248d8  jnz     short loc_180424922
0x1804248da  mov     r8d, r12d
0x1804248dd  mov     edx, edi
0x1804248df  xor     ecx, ecx
0x1804248e1  call    CheckWPPLevelFlagsEnabledForProvider
0x1804248e6  test    eax, eax
0x1804248e8  jnz     short loc_180424922
0x1804248ea  mov     eax, cs:gfTraceToSecondProvider
0x1804248f0  test    eax, eax
0x1804248f2  jz      loc_180424D69
0x1804248f8  call    THStateCheckForTraceOverride
0x1804248fd  test    eax, eax
0x1804248ff  jnz     short loc_180424922
0x180424901  call    ThStateCheckIfTraceToSecondProvier
0x180424906  test    eax, eax
0x180424908  jz      loc_180424D69
0x18042490e  mov     r8d, r12d
0x180424911  mov     edx, edi
0x180424913  mov     ecx, ebx
0x180424915  call    CheckWPPLevelFlagsEnabledForProvider
0x18042491a  test    eax, eax
0x18042491c  jz      loc_180424D69
0x180424922  mov     eax, cs:gfTraceToSecondProvider
0x180424928  test    eax, eax
0x18042492a  jz      short loc_180424953
0x18042492c  call    THStateCheckForTraceOverride
0x180424931  test    eax, eax
0x180424933  jnz     short loc_18042494E
0x180424935  call    ThStateCheckIfTraceToSecondProvier
0x18042493a  test    eax, eax
0x18042493c  jz      short loc_180424953
0x18042493e  mov     r8d, r12d
0x180424941  mov     edx, edi
0x180424943  mov     ecx, ebx
0x180424945  call    CheckWPPLevelFlagsEnabledForProvider
0x18042494a  test    eax, eax
0x18042494c  jz      short loc_180424953
0x18042494e  mov     r14d, ebx
0x180424951  jmp     short loc_180424956
0x180424953  xor     r14d, r14d
0x180424956  call    THStateCheckForTraceOverride
0x18042495b  test    eax, eax
0x18042495d  jnz     short loc_18042496F
0x18042495f  mov     r8d, r12d
0x180424962  mov     edx, edi
0x180424964  xor     ecx, ecx
0x180424966  call    CheckWPPLevelFlagsEnabledForProvider
  ... truncated ...
```
