# DsSamExtPerformPromotePhase2

- ea: `0x1803aaa50`
- end: `0x1803ab64b`
- name: `DsSamExtPerformPromotePhase2`
- size: `3067`
- prototype: `__int64 __fastcall(unsigned int, char)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180021aa3`
- `0x180030af8`
- `0x1800a1694`
- `0x1803a8168`
- `0x1803a831c`
- `0x1803a87f0`
- `0x1803aaa50`
- `0x1803abd40`
- `0x1803b2e90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803ab35c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803ab35c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1803ab347`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1803ab347`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1803ab2a2`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1803ab2a2`
- `ntdll!RtlInitUnicodeString` at `0x1803ab46f`
- `ntdll!RtlInitUnicodeString` at `0x1803ab46f`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1803ab4fe`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1803ab4fe`
- `SAMSRV!SampUsingDsData` at `0x1803aaaac`
- `SAMSRV!SampUsingDsData` at `0x1803ab237`
- `SAMSRV!SampUsingDsData` at `0x1803aaaac`
- `SAMSRV!SampUsingDsData` at `0x1803ab237`
- `SAMSRV!SampWriteEventLog` at `0x1803ab497`
- `SAMSRV!SampWriteEventLog` at `0x1803ab497`
- `SAMSRV!SampRecordSystemSchemaVerisonInRegistry` at `0x1803aaab6`
- `SAMSRV!SampRecordSystemSchemaVerisonInRegistry` at `0x1803aaab6`
- `SAMSRV!SampConnect` at `0x1803aaaeb`
- `SAMSRV!SampConnect` at `0x1803aaaeb`
- `SAMSRV!SamrOpenDomain` at `0x1803aad21`
- `SAMSRV!SamrOpenDomain` at `0x1803aae24`
- `SAMSRV!SamrOpenDomain` at `0x1803aad21`
- `SAMSRV!SamrOpenDomain` at `0x1803aae24`
- `SAMSRV!SamrCloseHandle` at `0x1803ab4c7`
- `SAMSRV!SamrCloseHandle` at `0x1803ab4d9`
- `SAMSRV!SamrCloseHandle` at `0x1803ab4eb`
- `SAMSRV!SamrCloseHandle` at `0x1803ab4c7`
- `SAMSRV!SamrCloseHandle` at `0x1803ab4d9`
- `SAMSRV!SamrCloseHandle` at `0x1803ab4eb`
- `SAMSRV!SampDeleteKeyForPostBootPromote` at `0x1803ab517`
- `SAMSRV!SampDeleteKeyForPostBootPromote` at `0x1803ab517`

## string_xrefs

- `0x1803ab2d0`: `\system32\config`

## pseudocode

```c
__int64 __fastcall DsSamExtPerformPromotePhase2(unsigned int a1, char a2)
{
  unsigned int v3; // r12d
  __int64 v4; // r15
  int v5; // r14d
  int v6; // edi
  __int64 v7; // rcx
  int LSAAccountDomainInfo; // esi
  BOOL v9; // r14d
  bool v10; // zf
  int v11; // eax
  int v12; // edx
  BOOL v13; // r14d
  int v14; // eax
  BOOL v15; // r14d
  int v16; // eax
  BOOL v17; // esi
  int v18; // eax
  __int64 v19; // rcx
  WCHAR *v20; // rax
  DWORD EnvironmentVariableW; // eax
  __int64 v22; // rax
  int v23; // r14d
  __int64 v24; // r15
  WCHAR *v25; // r13
  _WORD *v26; // rdx
  __int64 v27; // r8
  char v28; // r12
  int v29; // eax
  BOOL v30; // esi
  __int16 v32; // [rsp+30h] [rbp-D0h]
  int DcPromotePhase2; // [rsp+50h] [rbp-B0h]
  char v34[4]; // [rsp+54h] [rbp-ACh] BYREF
  void *v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  void *v38; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v39; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  void *Src[4]; // [rsp+90h] [rbp-70h]
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v39 = a1;
  v37 = 0;
  v35 = 0;
  v38 = 0;
  v3 = a1;
  v36 = 0;
  v4 = 0;
  v5 = a1 & 8;
  if ( (a1 & 8) != 0 && (unsigned __int8)SampUsingDsData() )
    SampRecordSystemSchemaVerisonInRegistry();
  v6 = 1;
  LSAAccountDomainInfo = SampConnect(0, &v37, 3, 0x10000000, 1, 0, 0, 1, 0);
  if ( LSAAccountDomainInfo < 0 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride()
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride()
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v9 = gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride()
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride()
        || (v10 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v11 = 0, !v10) )
      {
        v11 = 1;
      }
      v12 = 521733946;
      v32 = 11;
LABEL_22:
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        2,
        13,
        v11,
        v9,
        v32,
        (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
      goto LABEL_172;
    }
    goto LABEL_172;
  }
  LOBYTE(v7) = a2;
  LSAAccountDomainInfo = DsSamGetLSAAccountDomainInfo(v7, &v36);
  if ( LSAAccountDomainInfo < 0 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride()
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride()
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v13 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride()
        || (v10 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v14 = 0, !v10) )
      {
        v14 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        521733962,
        2,
        13,
        v14,
        v13,
        12,
        (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
    }
    goto LABEL_171;
  }
  v4 = v36;
  LSAAccountDomainInfo = SamrOpenDomain(v37, 0x10000000, *(_QWORD *)(v36 + 16), &v35);
  if ( LSAAccountDomainInfo < 0 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride()
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride()
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v15 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride()
        || (v10 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v16 = 0, !v10) )
      {
        v16 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        521733981,
        2,
        13,
        v16,
        v15,
        13,
        (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
    }
    goto LABEL_172;
  }
  DcPromotePhase2 = SamrOpenDomain(v37, 0x10000000, SampBuiltinDomainSid, &v38);
  LSAAccountDomainInfo = DcPromotePhase2;
  if ( DcPromotePhase2 >= 0 )
  {
    if ( (v3 & 4) != 0 )
    {
      if ( (v3 & 0x800) == 0 )
      {
        DcPromotePhase2 = DsSamPerformReplicaDcPromotePhase2(v35);
        LSAAccountDomainInfo = DcPromotePhase2;
        if ( DcPromotePhase2 < 0 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride()
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
          {
            v9 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride()
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
            if ( (unsigned int)THStateCheckForTraceOverride()
              || (v10 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v11 = 0, !v10) )
            {
              v11 = 1;
            }
            v12 = 521734011;
            v32 = 15;
            goto LABEL_22;
          }
          goto LABEL_172;
        }
      }
    }
    else if ( (v3 & 2) != 0 )
    {
      DcPromotePhase2 = DsSamPerformFirstDcPromotePhase2(v35, v38, v3);
      LSAAccountDomainInfo = DcPromotePhase2;
      if ( DcPromotePhase2 < 0 )
        goto LABEL_172;
    }
    else if ( (v3 & 0x200) != 0 )
    {
      DcPromotePhase2 = DsSamPerformTempUpgradeWork(v35);
      LSAAccountDomainInfo = DcPromotePhase2;
      if ( DcPromotePhase2 < 0 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride()
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v9 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( (unsigned int)THStateCheckForTraceOverride()
            || (v10 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v11 = 0, !v10) )
          {
            v11 = 1;
          }
          v12 = 521734028;
          v32 = 16;
          goto LABEL_22;
        }
        goto LABEL_172;
      }
    }
    else
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride()
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride()
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v17 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride()
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( (unsigned int)THStateCheckForTraceOverride()
          || (v10 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v18 = 0, !v10) )
        {
          v18 = 1;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521734035,
          2,
          13,
          v18,
          v17,
          17,
          &WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
      }
      LSAAccountDomainInfo = 0;
      DcPromotePhase2 = 0;
    }
    if ( (unsigned __int8)SampUsingDsData() && (v3 & 6) != 0 )
      DsSamExtSecureLocalMachineAccount(0);
    if ( !v5 )
      goto LABEL_172;
    *(_DWORD *)v34 = 0;
    Src[0] = L"\\SAM.UPG";
    v19 = 522;
    Src[1] = L"\\SAM.TMP";
    Src[2] = L"\\SAM.SAV";
    v20 = Buffer;
    do
    {
      *(_BYTE *)v20 = 0;
      v20 = (WCHAR *)((char *)v20 + 1);
      --v19;
    }
    while ( v19 );
    EnvironmentVariableW = GetEnvironmentVariableW(L"systemroot", Buffer, 0x105u);
    if ( EnvironmentVariableW - 1 > 0x81 )
    {
      EnvironmentVariableW = 10;
      wcscpy(Buffer, L"c:\\winows");
    }
    *(_OWORD *)&Buffer[EnvironmentVariableW] = *(_OWORD *)L"\\system32\\config";
    *(_OWORD *)&Buffer[EnvironmentVariableW + 8] = *(_OWORD *)L"2\\config";
    Buffer[EnvironmentVariableW + 16] = aSystem32Config_0[16];
    v22 = -1;
    do
      ++v22;
    while ( Buffer[v22] );
    v23 = 0;
    v24 = 0;
    v25 = &Buffer[(unsigned int)v22];
    do
    {
      v26 = Src[v24];
      v27 = -1;
      do
        ++v27;
      while ( v26[v27] );
      memcpy_0(v25, v26, 2 * v27 + 2);
      if ( !DeleteFileW(FileName) )
      {
        DestinationString = 0;
        *(_DWORD *)v34 = GetLastError();
        if ( *(_DWORD *)v34 != 2 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
            || (unsigned int)THStateCheckForTraceOverride()
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride()
             || (unsigned int)ThStateCheckIfTraceToSecondProvier()
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
          {
            v28 = v34[0];
            if ( gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride()
               || (unsigned int)ThStateCheckIfTraceToSecondProvier()
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
            {
              v23 = 1;
            }
            if ( (unsigned int)THStateCheckForTraceOverride()
              || (v29 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)) != 0 )
            {
              v29 = 1;
            }
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              521734138,
              2,
              13,
              v29,
              v23,
              18,
              &WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids,
              (__int64)FileName,
              v28);
            v23 = 0;
          }
          RtlInitUnicodeString(&DestinationString, FileName);
          SampWriteEventLog(SAMMSG_DATABASE_FILE_NOT_DELETED, L"ub", &DestinationString, 4, v34);
        }
      }
      ++v24;
    }
    while ( v24 != 3 );
    LSAAccountDomainInfo = DcPromotePhase2;
    LOWORD(v3) = v39;
LABEL_171:
    v4 = v36;
    goto LABEL_172;
  }
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
    || (unsigned int)THStateCheckForTraceOverride()
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride()
     || (unsigned int)ThStateCheckIfTraceToSecondProvier()
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
  {
    v9 = gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride()
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
    if ( (unsigned int)THStateCheckForTraceOverride()
      || (v10 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) == 0, v11 = 0, !v10) )
    {
      v11 = 1;
    }
    v12 = 521733998;
    v32 = 14;
    goto LABEL_22;
  }
LABEL_172:
  if ( v37 )
    SamrCloseHandle(&v37);
  if ( v35 )
    SamrCloseHandle(&v35);
  if ( v38 )
    SamrCloseHandle(&v38);
  if ( v4 )
    LsaIFree_LSAPR_POLICY_INFORMATION(5, v4);
  if ( LSAAccountDomainInfo >= 0 && (v3 & 0x400) == 0 )
  {
    if ( (int)SampDeleteKeyForPostBootPromote() < 0
      && ((unsigned int)IncrementWPPPerfCountersForLevel(2)
       || (unsigned int)THStateCheckForTraceOverride()
       || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
       || gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride()
        || (unsigned int)ThStateCheckIfTraceToSecondProvier()
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13))) )
    {
      v30 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride()
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( !(unsigned int)THStateCheckForTraceOverride()
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13) )
      {
        v6 = 0;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        521734188,
        2,
        13,
        v6,
        v30,
        19,
        (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
    }
    return 0;
  }
  return (unsigned int)LSAAccountDomainInfo;
}

```

## disassembly

```asm
0x1803aaa50  mov     [rsp-8+arg_10], rbx
0x1803aaa55  push    rbp
0x1803aaa56  push    rsi
0x1803aaa57  push    rdi
0x1803aaa58  push    r12
0x1803aaa5a  push    r13
0x1803aaa5c  push    r14
0x1803aaa5e  push    r15
0x1803aaa60  lea     rbp, [rsp-3E0h]
0x1803aaa68  sub     rsp, 4E0h
0x1803aaa6f  mov     rax, cs:__security_cookie
0x1803aaa76  xor     rax, rsp
0x1803aaa79  mov     [rbp+410h+var_40], rax
0x1803aaa80  xor     r13d, r13d
0x1803aaa83  mov     [rsp+510h+var_498], ecx
0x1803aaa87  mov     r14d, ecx
0x1803aaa8a  mov     [rsp+510h+var_4A8], r13
0x1803aaa8f  mov     [rsp+510h+var_4B8], r13
0x1803aaa94  mov     bl, dl
0x1803aaa96  mov     [rsp+510h+var_4A0], r13
0x1803aaa9b  mov     r12d, ecx
0x1803aaa9e  mov     [rsp+510h+var_4B0], r13
0x1803aaaa3  mov     r15d, r13d
0x1803aaaa6  and     r14d, 8
0x1803aaaaa  jz      short loc_1803AAABC
0x1803aaaac  call    cs:__imp_SampUsingDsData
0x1803aaab2  test    al, al
0x1803aaab4  jz      short loc_1803AAABC
0x1803aaab6  call    cs:__imp_SampRecordSystemSchemaVerisonInRegistry
0x1803aaabc  mov     byte ptr [rsp+510h+var_4D0], r13b
0x1803aaac1  lea     rdx, [rsp+510h+var_4A8]
0x1803aaac6  mov     edi, 1
0x1803aaacb  mov     r9d, 10000000h
0x1803aaad1  mov     byte ptr [rsp+510h+var_4D8], dil
0x1803aaad6  xor     ecx, ecx
0x1803aaad8  mov     byte ptr [rsp+510h+var_4E0], r13b
0x1803aaadd  mov     byte ptr [rsp+510h+var_4E8], r13b
0x1803aaae2  lea     r8d, [rdi+2]
0x1803aaae6  mov     byte ptr [rsp+510h+var_4F0], dil
0x1803aaaeb  call    cs:__imp_SampConnect
0x1803aaaf1  mov     esi, eax
0x1803aaaf3  test    eax, eax
0x1803aaaf5  jns     loc_1803AABF5
0x1803aaafb  lea     ebx, [rdi+1]
0x1803aaafe  mov     ecx, ebx
0x1803aab00  call    IncrementWPPPerfCountersForLevel
0x1803aab05  test    eax, eax
0x1803aab07  jnz     short loc_1803AAB5C
0x1803aab09  call    THStateCheckForTraceOverride
0x1803aab0e  test    eax, eax
0x1803aab10  jnz     short loc_1803AAB5C
0x1803aab12  lea     r8d, [rdi+0Ch]
0x1803aab16  mov     edx, ebx
0x1803aab18  xor     ecx, ecx
0x1803aab1a  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aab1f  test    eax, eax
0x1803aab21  jnz     short loc_1803AAB5C
0x1803aab23  mov     eax, cs:gfTraceToSecondProvider
0x1803aab29  test    eax, eax
0x1803aab2b  jz      loc_1803AB4BB
0x1803aab31  call    THStateCheckForTraceOverride
0x1803aab36  test    eax, eax
0x1803aab38  jnz     short loc_1803AAB5C
0x1803aab3a  call    ThStateCheckIfTraceToSecondProvier
0x1803aab3f  test    eax, eax
0x1803aab41  jz      loc_1803AB4BB
0x1803aab47  lea     r8d, [rdi+0Ch]
0x1803aab4b  mov     edx, ebx
0x1803aab4d  mov     ecx, edi
0x1803aab4f  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aab54  test    eax, eax
0x1803aab56  jz      loc_1803AB4BB
0x1803aab5c  mov     eax, cs:gfTraceToSecondProvider
0x1803aab62  test    eax, eax
0x1803aab64  jz      short loc_1803AAB90
0x1803aab66  call    THStateCheckForTraceOverride
0x1803aab6b  test    eax, eax
0x1803aab6d  jnz     short loc_1803AAB8B
0x1803aab6f  call    ThStateCheckIfTraceToSecondProvier
0x1803aab74  test    eax, eax
0x1803aab76  jz      short loc_1803AAB90
0x1803aab78  mov     r8d, 0Dh
0x1803aab7e  mov     edx, ebx
0x1803aab80  mov     ecx, edi
0x1803aab82  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aab87  test    eax, eax
0x1803aab89  jz      short loc_1803AAB90
0x1803aab8b  mov     r14d, edi
0x1803aab8e  jmp     short loc_1803AAB93
0x1803aab90  mov     r14d, r13d
0x1803aab93  call    THStateCheckForTraceOverride
0x1803aab98  test    eax, eax
0x1803aab9a  jnz     short loc_1803AABB0
0x1803aab9c  lea     r8d, [rax+0Dh]
0x1803aaba0  mov     edx, ebx
0x1803aaba2  xor     ecx, ecx
0x1803aaba4  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aaba9  test    eax, eax
0x1803aabab  mov     eax, r13d
0x1803aabae  jz      short loc_1803AABB2
0x1803aabb0  mov     eax, edi
0x1803aabb2  lea     rdx, WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids
0x1803aabb9  mov     dword ptr [rsp+510h+var_4D0], esi
0x1803aabbd  mov     [rsp+510h+var_4D8], rdx
0x1803aabc2  mov     edx, 1F19073Ah
0x1803aabc7  mov     [rsp+510h+var_4E0], 0Bh
0x1803aabce  mov     r9d, 0Dh
0x1803aabd4  mov     rcx, cs:WPP_GLOBAL_Control
0x1803aabdb  mov     r8d, ebx
0x1803aabde  mov     [rsp+510h+var_4E8], r14d
0x1803aabe3  mov     [rsp+510h+var_4F0], eax
0x1803aabe7  mov     rcx, [rcx+10h]
0x1803aabeb  call    WPP_SF__ATTRTYP_LOG_
0x1803aabf0  jmp     loc_1803AB4BB
0x1803aabf5  lea     rdx, [rsp+510h+var_4B0]
0x1803aabfa  mov     cl, bl
0x1803aabfc  call    DsSamGetLSAAccountDomainInfo
0x1803aac01  mov     esi, eax
0x1803aac03  test    eax, eax
0x1803aac05  jns     loc_1803AAD07
0x1803aac0b  mov     ebx, 2
0x1803aac10  mov     ecx, ebx
0x1803aac12  call    IncrementWPPPerfCountersForLevel
0x1803aac17  test    eax, eax
0x1803aac19  jnz     short loc_1803AAC6E
0x1803aac1b  call    THStateCheckForTraceOverride
0x1803aac20  test    eax, eax
0x1803aac22  jnz     short loc_1803AAC6E
0x1803aac24  lea     r8d, [rbx+0Bh]
0x1803aac28  mov     edx, ebx
0x1803aac2a  xor     ecx, ecx
0x1803aac2c  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aac31  test    eax, eax
0x1803aac33  jnz     short loc_1803AAC6E
0x1803aac35  mov     eax, cs:gfTraceToSecondProvider
0x1803aac3b  test    eax, eax
0x1803aac3d  jz      loc_1803AB4B6
0x1803aac43  call    THStateCheckForTraceOverride
0x1803aac48  test    eax, eax
0x1803aac4a  jnz     short loc_1803AAC6E
0x1803aac4c  call    ThStateCheckIfTraceToSecondProvier
0x1803aac51  test    eax, eax
0x1803aac53  jz      loc_1803AB4B6
0x1803aac59  lea     r8d, [rbx+0Bh]
0x1803aac5d  mov     edx, ebx
0x1803aac5f  mov     ecx, edi
0x1803aac61  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aac66  test    eax, eax
0x1803aac68  jz      loc_1803AB4B6
0x1803aac6e  mov     eax, cs:gfTraceToSecondProvider
0x1803aac74  test    eax, eax
0x1803aac76  jz      short loc_1803AACA2
0x1803aac78  call    THStateCheckForTraceOverride
0x1803aac7d  test    eax, eax
0x1803aac7f  jnz     short loc_1803AAC9D
0x1803aac81  call    ThStateCheckIfTraceToSecondProvier
0x1803aac86  test    eax, eax
0x1803aac88  jz      short loc_1803AACA2
0x1803aac8a  mov     r8d, 0Dh
0x1803aac90  mov     edx, ebx
0x1803aac92  mov     ecx, edi
0x1803aac94  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aac99  test    eax, eax
0x1803aac9b  jz      short loc_1803AACA2
0x1803aac9d  mov     r14d, edi
0x1803aaca0  jmp     short loc_1803AACA5
0x1803aaca2  mov     r14d, r13d
0x1803aaca5  call    THStateCheckForTraceOverride
0x1803aacaa  test    eax, eax
0x1803aacac  jnz     short loc_1803AACC2
0x1803aacae  lea     r8d, [rax+0Dh]
0x1803aacb2  mov     edx, ebx
0x1803aacb4  xor     ecx, ecx
0x1803aacb6  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aacbb  test    eax, eax
0x1803aacbd  mov     eax, r13d
0x1803aacc0  jz      short loc_1803AACC4
0x1803aacc2  mov     eax, edi
0x1803aacc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1803aaccb  lea     rdx, WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids
0x1803aacd2  mov     dword ptr [rsp+510h+var_4D0], esi
0x1803aacd6  mov     r9d, 0Dh
0x1803aacdc  mov     [rsp+510h+var_4D8], rdx
0x1803aace1  mov     r8d, ebx
0x1803aace4  mov     [rsp+510h+var_4E0], 0Ch
0x1803aaceb  mov     edx, 1F19074Ah
0x1803aacf0  mov     rcx, [rcx+10h]
0x1803aacf4  mov     [rsp+510h+var_4E8], r14d
0x1803aacf9  mov     [rsp+510h+var_4F0], eax
0x1803aacfd  call    WPP_SF__ATTRTYP_LOG_
0x1803aad02  jmp     loc_1803AB4B6
0x1803aad07  mov     r15, [rsp+510h+var_4B0]
0x1803aad0c  lea     r9, [rsp+510h+var_4B8]
0x1803aad11  mov     rcx, [rsp+510h+var_4A8]
0x1803aad16  mov     ebx, 10000000h
0x1803aad1b  mov     edx, ebx
0x1803aad1d  mov     r8, [r15+10h]
0x1803aad21  call    cs:__imp_SamrOpenDomain
0x1803aad27  mov     esi, eax
0x1803aad29  test    eax, eax
0x1803aad2b  jns     loc_1803AAE11
0x1803aad31  mov     ebx, 2
0x1803aad36  mov     ecx, ebx
0x1803aad38  call    IncrementWPPPerfCountersForLevel
0x1803aad3d  test    eax, eax
0x1803aad3f  jnz     short loc_1803AAD94
0x1803aad41  call    THStateCheckForTraceOverride
0x1803aad46  test    eax, eax
0x1803aad48  jnz     short loc_1803AAD94
0x1803aad4a  lea     r8d, [rbx+0Bh]
0x1803aad4e  mov     edx, ebx
0x1803aad50  xor     ecx, ecx
0x1803aad52  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aad57  test    eax, eax
0x1803aad59  jnz     short loc_1803AAD94
0x1803aad5b  mov     eax, cs:gfTraceToSecondProvider
0x1803aad61  test    eax, eax
0x1803aad63  jz      loc_1803AB4BB
0x1803aad69  call    THStateCheckForTraceOverride
0x1803aad6e  test    eax, eax
0x1803aad70  jnz     short loc_1803AAD94
0x1803aad72  call    ThStateCheckIfTraceToSecondProvier
0x1803aad77  test    eax, eax
0x1803aad79  jz      loc_1803AB4BB
0x1803aad7f  lea     r8d, [rbx+0Bh]
0x1803aad83  mov     edx, ebx
0x1803aad85  mov     ecx, edi
0x1803aad87  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aad8c  test    eax, eax
0x1803aad8e  jz      loc_1803AB4BB
0x1803aad94  mov     eax, cs:gfTraceToSecondProvider
0x1803aad9a  test    eax, eax
0x1803aad9c  jz      short loc_1803AADC8
0x1803aad9e  call    THStateCheckForTraceOverride
0x1803aada3  test    eax, eax
0x1803aada5  jnz     short loc_1803AADC3
0x1803aada7  call    ThStateCheckIfTraceToSecondProvier
0x1803aadac  test    eax, eax
0x1803aadae  jz      short loc_1803AADC8
0x1803aadb0  mov     r8d, 0Dh
0x1803aadb6  mov     edx, ebx
0x1803aadb8  mov     ecx, edi
0x1803aadba  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aadbf  test    eax, eax
0x1803aadc1  jz      short loc_1803AADC8
0x1803aadc3  mov     r14d, edi
0x1803aadc6  jmp     short loc_1803AADCB
0x1803aadc8  mov     r14d, r13d
0x1803aadcb  call    THStateCheckForTraceOverride
0x1803aadd0  test    eax, eax
0x1803aadd2  jnz     short loc_1803AADE8
0x1803aadd4  lea     r8d, [rax+0Dh]
0x1803aadd8  mov     edx, ebx
0x1803aadda  xor     ecx, ecx
0x1803aaddc  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aade1  test    eax, eax
0x1803aade3  mov     eax, r13d
0x1803aade6  jz      short loc_1803AADEA
0x1803aade8  mov     eax, edi
0x1803aadea  lea     rdx, WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids
0x1803aadf1  mov     dword ptr [rsp+510h+var_4D0], esi
0x1803aadf5  mov     ecx, 0Dh
0x1803aadfa  mov     [rsp+510h+var_4D8], rdx
0x1803aadff  mov     [rsp+510h+var_4E0], cx
0x1803aae04  mov     edx, 1F19075Dh
0x1803aae09  mov     r9d, ecx
0x1803aae0c  jmp     loc_1803AABD4
0x1803aae11  mov     r8, cs:SampBuiltinDomainSid
0x1803aae18  lea     r9, [rsp+510h+var_4A0]
0x1803aae1d  mov     rcx, [rsp+510h+var_4A8]
0x1803aae22  mov     edx, ebx
0x1803aae24  call    cs:__imp_SamrOpenDomain
0x1803aae2a  mov     [rsp+510h+var_4C0], eax
0x1803aae2e  mov     esi, eax
0x1803aae30  test    eax, eax
0x1803aae32  jns     loc_1803AAF12
0x1803aae38  mov     ebx, 2
0x1803aae3d  mov     ecx, ebx
0x1803aae3f  call    IncrementWPPPerfCountersForLevel
0x1803aae44  test    eax, eax
0x1803aae46  jnz     short loc_1803AAE9B
0x1803aae48  call    THStateCheckForTraceOverride
0x1803aae4d  test    eax, eax
0x1803aae4f  jnz     short loc_1803AAE9B
0x1803aae51  lea     r8d, [rbx+0Bh]
0x1803aae55  mov     edx, ebx
0x1803aae57  xor     ecx, ecx
0x1803aae59  call    CheckWPPLevelFlagsEnabledForProvider
0x1803aae5e  test    eax, eax
0x1803aae60  jnz     short loc_1803AAE9B
0x1803aae62  mov     eax, cs:gfTraceToSecondProvider
0x1803aae68  test    eax, eax
0x1803aae6a  jz      loc_1803AB4BB
0x1803aae70  call    THStateCheckForTraceOverride
0x1803aae75  test    eax, eax
0x1803aae77  jnz     short loc_1803AAE9B
0x1803aae79  call    ThStateCheckIfTraceToSecondProvier
0x1803aae7e  test    eax, eax
0x1803aae80  jz      loc_1803AB4BB
0x1803aae86  lea     r8d, [rbx+0Bh]
  ... truncated ...
```
