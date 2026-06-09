# SampDsSyncDSRMPasswordFromAccount

- ea: `0x1804099c0`
- end: `0x18040a525`
- name: `SampDsSyncDSRMPasswordFromAccount`
- size: `2917`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x180030b60`
- `0x18003e1ac`
- `0x1800deda4`
- `0x1803af8ac`
- `0x1803aff80`
- `0x1803b0070`
- `0x1803c4868`
- `0x1804099c0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180409f01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180409f01`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18040a344`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18040a344`
- `CRYPTSP!SystemFunction026` at `0x18040a362`
- `CRYPTSP!SystemFunction026` at `0x18040a362`
- `SAMSRV!SampGetUserAccountSettings` at `0x180409d02`
- `SAMSRV!SampGetUserAccountSettings` at `0x180409d02`
- `SAMSRV!SampSetTransactionDomain` at `0x180409a7a`
- `SAMSRV!SampSetTransactionDomain` at `0x18040a0ab`
- `SAMSRV!SampSetTransactionDomain` at `0x180409a7a`
- `SAMSRV!SampSetTransactionDomain` at `0x18040a0ab`
- `SAMSRV!SampCreateAccountContext2` at `0x180409ac7`
- `SAMSRV!SampCreateAccountContext2` at `0x18040a0fc`
- `SAMSRV!SampCreateAccountContext2` at `0x180409ac7`
- `SAMSRV!SampCreateAccountContext2` at `0x18040a0fc`
- `SAMSRV!SampCheckForAccountLockout` at `0x180409dff`
- `SAMSRV!SampCheckForAccountLockout` at `0x180409dff`
- `SAMSRV!SampRetrieveUserPasswords` at `0x180409f6c`
- `SAMSRV!SampRetrieveUserPasswords` at `0x18040a212`
- `SAMSRV!SampRetrieveUserPasswords` at `0x180409f6c`
- `SAMSRV!SampRetrieveUserPasswords` at `0x18040a212`
- `SAMSRV!SampSetTransactionWithinDomain` at `0x18040a0a2`
- `SAMSRV!SampSetTransactionWithinDomain` at `0x18040a0a2`
- `SAMSRV!SampSetDSRMPasswordWorker` at `0x18040a378`
- `SAMSRV!SampSetDSRMPasswordWorker` at `0x18040a378`
- `SAMSRV!SampUsingDsData` at `0x180409a6a`
- `SAMSRV!SampUsingDsData` at `0x180409a6a`
- `SAMSRV!SampDeleteContext` at `0x18040a4d1`
- `SAMSRV!SampDeleteContext` at `0x18040a4e0`
- `SAMSRV!SampDeleteContext` at `0x18040a4d1`
- `SAMSRV!SampDeleteContext` at `0x18040a4e0`
- `SAMSRV!SampQueryCapabilities` at `0x180409bdc`
- `SAMSRV!SampQueryCapabilities` at `0x180409bdc`

## pseudocode

```c
__int64 __fastcall SampDsSyncDSRMPasswordFromAccount(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // r12
  int UserAccountSettings; // edi
  char v8; // al
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // r9
  BOOL v16; // esi
  int v17; // eax
  int v18; // ecx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // r8
  __int64 v24; // r9
  BOOL v25; // esi
  int v26; // eax
  int v27; // ecx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // r8
  __int64 v33; // r9
  BOOL v34; // esi
  int v35; // eax
  int v36; // ecx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // r8
  __int64 v42; // r9
  BOOL v43; // esi
  int v44; // eax
  int v45; // ecx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // r8
  __int64 v51; // r9
  BOOL v52; // esi
  BOOL v53; // ecx
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // r8
  __int64 v59; // r9
  BOOL v60; // esi
  int v61; // eax
  int v62; // ecx
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 v67; // r8
  __int64 v68; // r9
  BOOL v69; // esi
  int v70; // r8d
  BOOL v71; // ecx
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // r8
  __int64 v77; // r9
  BOOL v78; // esi
  int v79; // eax
  int v80; // ecx
  __int64 v81; // rcx
  __int128 *p_Source2; // rax
  __int64 v83; // rcx
  __int128 *p_Source1; // rax
  __int64 v85; // rcx
  __int128 *v86; // rax
  __int128 *v87; // rax
  int v89; // [rsp+30h] [rbp-D0h]
  int v90; // [rsp+38h] [rbp-C8h]
  int v91; // [rsp+40h] [rbp-C0h]
  int v92; // [rsp+48h] [rbp-B8h]
  int v93; // [rsp+50h] [rbp-B0h]
  int v94; // [rsp+58h] [rbp-A8h]
  char v95; // [rsp+70h] [rbp-90h] BYREF
  char v96; // [rsp+71h] [rbp-8Fh] BYREF
  char v97; // [rsp+72h] [rbp-8Eh] BYREF
  char v98; // [rsp+73h] [rbp-8Dh] BYREF
  _BYTE v99[4]; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v100; // [rsp+78h] [rbp-88h] BYREF
  int v101; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-78h] BYREF
  __int64 v103; // [rsp+90h] [rbp-70h] BYREF
  __int128 Source2; // [rsp+98h] [rbp-68h] BYREF
  __int128 Source1; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v106; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v107; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v108[3]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v109[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v110; // [rsp+130h] [rbp+30h]
  int v111; // [rsp+148h] [rbp+48h]

  v100 = 0;
  v103 = 0;
  memset_0(v109, 0, 0x50u);
  v97 = 0;
  v99[0] = 0;
  v98 = 0;
  v107 = 0;
  v96 = 0;
  Source2 = 0;
  v95 = 0;
  Source1 = 0;
  v101 = 0;
  v106 = 0;
  SystemTimeAsFileTime = 0;
  memset(v108, 0, sizeof(v108));
  v6 = 16;
  UserAccountSettings = SampMaybeBeginDsTransaction(0);
  if ( UserAccountSettings >= 0 )
  {
    v8 = SampUsingDsData();
    SampSetTransactionDomain(v8 != 0 ? 3 : 1);
    UserAccountSettings = SampCreateAccountContext2(a1, 4, a3, 0, 0, 3, 1, 0, 0, 1, 0, 1, 0, &v100);
    if ( UserAccountSettings >= 0 )
    {
      LOBYTE(v9) = 1;
      if ( (SampQueryCapabilities(v9) & 5) == 1
        && (UserAccountSettings = SampValidateSecrets(*(_QWORD *)(v100 + 176), 0), UserAccountSettings < 0) )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v20, v19)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v20, v19)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v20, v19, v21, v22)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v25 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v20, v19)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v20, v19, v23, v24)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v20, v19)
            || (v26 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v27 = 0, v26) )
          {
            v27 = 1;
          }
          WPP_SF__ATTRTYP_LOG_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            521011318,
            2,
            13,
            v27,
            v25,
            11,
            (__int64)WPP_32f5d0670c583c677716e2381a9d353b_Traceguids);
        }
      }
      else
      {
        UserAccountSettings = SampGetUserAccountSettings(v100, v108);
        if ( UserAccountSettings >= 0 )
        {
          UserAccountSettings = SampCheckForAccountLockout(v100, v108, v109);
          if ( UserAccountSettings >= 0 )
          {
            if ( (v111 & 0x10) != 0 )
            {
              GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
              if ( v110 && v110 < *(_QWORD *)&SystemTimeAsFileTime )
              {
                UserAccountSettings = -1073741421;
              }
              else if ( (v111 & 0x20000) != 0 )
              {
                UserAccountSettings = -1073741711;
              }
              else if ( (v111 & 0x1000) != 0 )
              {
                UserAccountSettings = -1073741716;
              }
              else
              {
                UserAccountSettings = SampRetrieveUserPasswords(v100, &v107, &v97, &Source2, &v96, &v95);
                if ( UserAccountSettings >= 0 )
                {
                  SampSetTransactionWithinDomain(0);
                  SampSetTransactionDomain(1);
                  LOBYTE(v94) = 1;
                  LOBYTE(v93) = 0;
                  LOBYTE(v92) = 1;
                  LOBYTE(v91) = 0;
                  LOBYTE(v90) = 0;
                  LOBYTE(v89) = 1;
                  UserAccountSettings = SampCreateAccountContext2(
                                          a2,
                                          4,
                                          500,
                                          0,
                                          0,
                                          3,
                                          v89,
                                          v90,
                                          v91,
                                          v92,
                                          v93,
                                          v94,
                                          0,
                                          &v103);
                  if ( UserAccountSettings >= 0 )
                  {
                    UserAccountSettings = SampRetrieveUserPasswords(v103, &v107, &v97, &Source1, v99, &v98);
                    if ( UserAccountSettings >= 0 )
                    {
                      if ( RtlCompareMemory(&Source1, &Source2, 0x10u) != 16 )
                      {
                        v101 = 500;
                        UserAccountSettings = SystemFunction026(&Source2, &v101, &v106);
                        if ( UserAccountSettings >= 0 )
                        {
                          UserAccountSettings = SampSetDSRMPasswordWorker(500, &v106);
                          if ( UserAccountSettings < 0
                            && ((unsigned int)IncrementWPPPerfCountersForLevel(2)
                             || (unsigned int)THStateCheckForTraceOverride(v73, v72)
                             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
                             || gfTraceToSecondProvider
                             && ((unsigned int)THStateCheckForTraceOverride(v73, v72)
                              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v73, v72, v74, v75)
                              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13))) )
                          {
                            v78 = gfTraceToSecondProvider
                               && ((unsigned int)THStateCheckForTraceOverride(v73, v72)
                                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v73, v72, v76, v77)
                                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
                            if ( (unsigned int)THStateCheckForTraceOverride(v73, v72)
                              || (v79 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v80 = 0, v79) )
                            {
                              v80 = 1;
                            }
                            WPP_SF__ATTRTYP_LOG_(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              521011503,
                              2,
                              13,
                              v80,
                              v78,
                              17,
                              (__int64)WPP_32f5d0670c583c677716e2381a9d353b_Traceguids);
                          }
                        }
                      }
                    }
                    else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                           || (unsigned int)THStateCheckForTraceOverride(v64, v63)
                           || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
                           || gfTraceToSecondProvider
                           && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
                            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v64, v63, v65, v66)
                            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
                    {
                      v69 = gfTraceToSecondProvider
                         && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
                          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v64, v63, v67, v68)
                          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
                      v71 = (unsigned int)THStateCheckForTraceOverride(v64, v63)
                         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13);
                      WPP_SF_ddD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        521011459,
                        v70,
                        13,
                        v71,
                        v69,
                        16,
                        (__int64)WPP_32f5d0670c583c677716e2381a9d353b_Traceguids);
                    }
                  }
                  else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                         || (unsigned int)THStateCheckForTraceOverride(v55, v54)
                         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
                         || gfTraceToSecondProvider
                         && ((unsigned int)THStateCheckForTraceOverride(v55, v54)
                          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v55, v54, v56, v57)
                          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
                  {
                    v60 = gfTraceToSecondProvider
                       && ((unsigned int)THStateCheckForTraceOverride(v55, v54)
                        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v55, v54, v58, v59)
                        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
                    if ( (unsigned int)THStateCheckForTraceOverride(v55, v54)
                      || (v61 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v62 = 0, v61) )
                    {
                      v62 = 1;
                    }
                    WPP_SF__ATTRTYP_LOG_(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      521011436,
                      2,
                      13,
                      v62,
                      v60,
                      15,
                      (__int64)WPP_32f5d0670c583c677716e2381a9d353b_Traceguids);
                  }
                }
                else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                       || (unsigned int)THStateCheckForTraceOverride(v47, v46)
                       || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
                       || gfTraceToSecondProvider
                       && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
                        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v47, v46, v48, v49)
                        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
                {
                  v52 = gfTraceToSecondProvider
                     && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
                      || (unsigned int)ThStateCheckIfTraceToSecondProvier(v47, v46, v50, v51)
                      && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
                  v53 = (unsigned int)THStateCheckForTraceOverride(v47, v46)
                     || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13);
                  WPP_SF_dddd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    521011401,
                    2,
                    13,
                    v53,
                    v52,
                    14,
                    (__int64)WPP_32f5d0670c583c677716e2381a9d353b_Traceguids);
                }
              }
            }
            else
            {
              UserAccountSettings = -1073741724;
            }
          }
          else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                 || (unsigned int)THStateCheckForTraceOverride(v38, v37)
                 || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
                 || gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier(v38, v37, v39, v40)
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
          {
            v43 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v38, v37, v41, v42)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
            if ( (unsigned int)THStateCheckForTraceOverride(v38, v37)
              || (v44 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v45 = 0, v44) )
            {
              v45 = 1;
            }
            WPP_SF__ATTRTYP_LOG_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              521011348,
              2,
              13,
              v45,
              v43,
              13,
              (__int64)WPP_32f5d0670c583c677716e2381a9d353b_Traceguids);
          }
        }
        else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
               || (unsigned int)THStateCheckForTraceOverride(v29, v28)
               || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
               || gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v29, v28)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v29, v28, v30, v31)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v34 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v29, v28)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v29, v28, v32, v33)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v29, v28)
            || (v35 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v36 = 0, v35) )
          {
            v36 = 1;
          }
          WPP_SF__ATTRTYP_LOG_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            521011333,
            2,
            13,
            v36,
            v34,
            12,
            (__int64)WPP_32f5d0670c583c677716e2381a9d353b_Traceguids);
        }
      }
    }
    else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
           || (unsigned int)THStateCheckForTraceOverride(v11, v10)
           || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
           || gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v11, v10)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v11, v10, v12, v13)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      v16 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v11, v10)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v11, v10, v14, v15)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride(v11, v10)
        || (v17 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v18 = 0, v17) )
      {
        v18 = 1;
      }
      WPP_SF__ATTRTYP_LOG_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        521011303,
        2,
        13,
        v18,
        v16,
        10,
        (__int64)WPP_32f5d0670c583c677716e2381a9d353b_Traceguids);
    }
  }
  v81 = 16;
  p_Source2 = &Source2;
  do
  {
    *(_BYTE *)p_Source2 = 0;
    p_Source2 = (__int128 *)((char *)p_Source2 + 1);
    --v81;
  }
  while ( v81 );
  v83 = 16;
  p_Source1 = &Source1;
  do
  {
    *(_BYTE *)p_Source1 = 0;
    p_Source1 = (__int128 *)((char *)p_Source1 + 1);
    --v83;
  }
  while ( v83 );
  v85 = 16;
  v86 = &v106;
  do
  {
    *(_BYTE *)v86 = 0;
    v86 = (__int128 *)((char *)v86 + 1);
    --v85;
  }
  while ( v85 );
  v87 = &v107;
  do
  {
    *(_BYTE *)v87 = 0;
    v87 = (__int128 *)((char *)v87 + 1);
    --v6;
  }
  while ( v6 );
  if ( v100 )
    SampDeleteContext(v100);
  if ( v103 )
    SampDeleteContext(v103);
  if ( (unsigned int)SampExistsDsTransaction() )
    SampMaybeEndDsTransaction((unsigned int)((UserAccountSettings >> 31) + 3));
  return (unsigned int)UserAccountSettings;
}

```

## disassembly

```asm
0x1804099c0  mov     [rsp-8+arg_18], rbx
0x1804099c5  push    rbp
0x1804099c6  push    rsi
0x1804099c7  push    rdi
0x1804099c8  push    r12
0x1804099ca  push    r13
0x1804099cc  push    r14
0x1804099ce  push    r15
0x1804099d0  lea     rbp, [rsp-70h]
0x1804099d5  sub     rsp, 170h
0x1804099dc  mov     rax, cs:__security_cookie
0x1804099e3  xor     rax, rsp
0x1804099e6  mov     [rbp+0A0h+var_40], rax
0x1804099ea  xor     r14d, r14d
0x1804099ed  mov     r13d, r8d
0x1804099f0  mov     rsi, rdx
0x1804099f3  mov     [rsp+1A0h+var_128], r14
0x1804099f8  mov     rbx, rcx
0x1804099fb  mov     [rbp+0A0h+var_110], r14
0x1804099ff  xor     edx, edx; Val
0x180409a01  lea     rcx, [rbp+0A0h+var_90]; void *
0x180409a05  lea     r8d, [r14+50h]; Size
0x180409a09  call    memset_0
0x180409a0e  xorps   xmm1, xmm1
0x180409a11  mov     [rsp+1A0h+var_12E], r14b
0x180409a16  xorps   xmm0, xmm0
0x180409a19  mov     [rsp+1A0h+var_12C], r14b
0x180409a1e  xor     ecx, ecx
0x180409a20  mov     [rsp+1A0h+var_12D], r14b
0x180409a25  movups  [rbp+0A0h+var_D8], xmm0
0x180409a29  mov     [rsp+1A0h+var_12F], r14b
0x180409a2e  movups  [rbp+0A0h+Source2], xmm1
0x180409a32  mov     [rsp+1A0h+var_130], r14b
0x180409a37  movups  [rbp+0A0h+Source1], xmm0
0x180409a3b  mov     [rbp+0A0h+var_120], r14d
0x180409a3f  movups  [rbp+0A0h+var_E8], xmm0
0x180409a43  mov     qword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180409a47  movups  [rbp+0A0h+var_C8], xmm1
0x180409a4b  movups  [rbp+0A0h+var_B8], xmm1
0x180409a4f  movups  [rbp+0A0h+var_A8], xmm1
0x180409a53  call    SampMaybeBeginDsTransaction
0x180409a58  lea     r12d, [r14+10h]
0x180409a5c  mov     edi, eax
0x180409a5e  lea     r15d, [r14+1]
0x180409a62  test    eax, eax
0x180409a64  js      loc_18040A482
0x180409a6a  call    cs:__imp_SampUsingDsData
0x180409a70  neg     al
0x180409a72  sbb     ecx, ecx
0x180409a74  and     ecx, 2
0x180409a77  add     ecx, r15d
0x180409a7a  call    cs:__imp_SampSetTransactionDomain
0x180409a80  lea     rax, [rsp+1A0h+var_128]
0x180409a85  xor     r9d, r9d
0x180409a88  mov     [rsp+1A0h+var_138], rax
0x180409a8d  lea     edx, [r14+4]
0x180409a91  mov     [rsp+1A0h+var_140], r14
0x180409a96  mov     r8d, r13d
0x180409a99  mov     byte ptr [rsp+1A0h+var_148], r15b
0x180409a9e  mov     rcx, rbx
0x180409aa1  mov     byte ptr [rsp+1A0h+var_150], r14b
0x180409aa6  mov     byte ptr [rsp+1A0h+var_158], r15b
0x180409aab  mov     byte ptr [rsp+1A0h+var_160], r14b
0x180409ab0  mov     byte ptr [rsp+1A0h+var_168], r14b
0x180409ab5  mov     byte ptr [rsp+1A0h+var_170], r15b
0x180409aba  mov     dword ptr [rsp+1A0h+var_178], 3
0x180409ac2  mov     qword ptr [rsp+1A0h+var_180], r14
0x180409ac7  call    cs:__imp_SampCreateAccountContext2
0x180409acd  mov     edi, eax
0x180409acf  test    eax, eax
0x180409ad1  jns     loc_180409BD7
0x180409ad7  lea     esi, [r14+2]
0x180409adb  mov     ecx, esi
0x180409add  call    IncrementWPPPerfCountersForLevel
0x180409ae2  lea     ebx, [rsi+0Bh]
0x180409ae5  test    eax, eax
0x180409ae7  jnz     short loc_180409B3B
0x180409ae9  call    THStateCheckForTraceOverride
0x180409aee  test    eax, eax
0x180409af0  jnz     short loc_180409B3B
0x180409af2  mov     r8d, ebx
0x180409af5  mov     edx, esi
0x180409af7  xor     ecx, ecx
0x180409af9  call    CheckWPPLevelFlagsEnabledForProvider
0x180409afe  test    eax, eax
0x180409b00  jnz     short loc_180409B3B
0x180409b02  mov     eax, cs:gfTraceToSecondProvider
0x180409b08  test    eax, eax
0x180409b0a  jz      loc_18040A482
0x180409b10  call    THStateCheckForTraceOverride
0x180409b15  test    eax, eax
0x180409b17  jnz     short loc_180409B3B
0x180409b19  call    ThStateCheckIfTraceToSecondProvier
0x180409b1e  test    eax, eax
0x180409b20  jz      loc_18040A482
0x180409b26  mov     r8d, ebx
0x180409b29  mov     edx, esi
0x180409b2b  mov     ecx, r15d
0x180409b2e  call    CheckWPPLevelFlagsEnabledForProvider
0x180409b33  test    eax, eax
0x180409b35  jz      loc_18040A482
0x180409b3b  mov     eax, cs:gfTraceToSecondProvider
0x180409b41  test    eax, eax
0x180409b43  jz      short loc_180409B6D
0x180409b45  call    THStateCheckForTraceOverride
0x180409b4a  test    eax, eax
0x180409b4c  jnz     short loc_180409B68
0x180409b4e  call    ThStateCheckIfTraceToSecondProvier
0x180409b53  test    eax, eax
0x180409b55  jz      short loc_180409B6D
0x180409b57  mov     r8d, ebx
0x180409b5a  mov     edx, esi
0x180409b5c  mov     ecx, r15d
0x180409b5f  call    CheckWPPLevelFlagsEnabledForProvider
0x180409b64  test    eax, eax
0x180409b66  jz      short loc_180409B6D
0x180409b68  mov     esi, r15d
0x180409b6b  jmp     short loc_180409B70
0x180409b6d  mov     esi, r14d
0x180409b70  call    THStateCheckForTraceOverride
0x180409b75  test    eax, eax
0x180409b77  jnz     short loc_180409B8D
0x180409b79  mov     r8d, ebx
0x180409b7c  lea     edx, [rax+2]
0x180409b7f  xor     ecx, ecx
0x180409b81  call    CheckWPPLevelFlagsEnabledForProvider
0x180409b86  mov     ecx, r14d
0x180409b89  test    eax, eax
0x180409b8b  jz      short loc_180409B90
0x180409b8d  mov     ecx, r15d
0x180409b90  mov     [rsp+1A0h+var_158], edi
0x180409b94  lea     rax, WPP_32f5d0670c583c677716e2381a9d353b_Traceguids
0x180409b9b  mov     [rsp+1A0h+var_160], r13d
0x180409ba0  mov     edx, 1F0E0067h
0x180409ba5  mov     [rsp+1A0h+var_168], rax
0x180409baa  mov     [rsp+1A0h+var_170], 0Ah
0x180409bb1  mov     dword ptr [rsp+1A0h+var_178], esi
0x180409bb5  mov     r9d, ebx
0x180409bb8  mov     [rsp+1A0h+var_180], ecx
0x180409bbc  mov     r8d, 2
0x180409bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180409bc9  mov     rcx, [rcx+10h]
0x180409bcd  call    WPP_SF__ATTRTYP_LOG_d
0x180409bd2  jmp     loc_18040A482
0x180409bd7  xor     edx, edx
0x180409bd9  mov     cl, r15b
0x180409bdc  call    cs:__imp_SampQueryCapabilities
0x180409be2  and     al, 5
0x180409be4  cmp     al, r15b
0x180409be7  jnz     loc_180409CF9
0x180409bed  mov     rcx, [rsp+1A0h+var_128]
0x180409bf2  xor     r9d, r9d
0x180409bf5  mov     r8d, 1000000h
0x180409bfb  mov     [rsp+1A0h+var_180], r14d; int
0x180409c00  mov     dl, r15b
0x180409c03  mov     rcx, [rcx+0B0h]; __int64
0x180409c0a  call    SampValidateSecrets
0x180409c0f  mov     edi, eax
0x180409c11  test    eax, eax
0x180409c13  jns     loc_180409CF9
0x180409c19  mov     esi, 2
0x180409c1e  mov     ecx, esi
0x180409c20  call    IncrementWPPPerfCountersForLevel
0x180409c25  lea     ebx, [rsi+0Bh]
0x180409c28  test    eax, eax
0x180409c2a  jnz     short loc_180409C7E
0x180409c2c  call    THStateCheckForTraceOverride
0x180409c31  test    eax, eax
0x180409c33  jnz     short loc_180409C7E
0x180409c35  mov     r8d, ebx
0x180409c38  mov     edx, esi
0x180409c3a  xor     ecx, ecx
0x180409c3c  call    CheckWPPLevelFlagsEnabledForProvider
0x180409c41  test    eax, eax
0x180409c43  jnz     short loc_180409C7E
0x180409c45  mov     eax, cs:gfTraceToSecondProvider
0x180409c4b  test    eax, eax
0x180409c4d  jz      loc_18040A482
0x180409c53  call    THStateCheckForTraceOverride
0x180409c58  test    eax, eax
0x180409c5a  jnz     short loc_180409C7E
0x180409c5c  call    ThStateCheckIfTraceToSecondProvier
0x180409c61  test    eax, eax
0x180409c63  jz      loc_18040A482
0x180409c69  mov     r8d, ebx
0x180409c6c  mov     edx, esi
0x180409c6e  mov     ecx, r15d
0x180409c71  call    CheckWPPLevelFlagsEnabledForProvider
0x180409c76  test    eax, eax
0x180409c78  jz      loc_18040A482
0x180409c7e  mov     eax, cs:gfTraceToSecondProvider
0x180409c84  test    eax, eax
0x180409c86  jz      short loc_180409CB0
0x180409c88  call    THStateCheckForTraceOverride
0x180409c8d  test    eax, eax
0x180409c8f  jnz     short loc_180409CAB
0x180409c91  call    ThStateCheckIfTraceToSecondProvier
0x180409c96  test    eax, eax
0x180409c98  jz      short loc_180409CB0
0x180409c9a  mov     r8d, ebx
0x180409c9d  mov     edx, esi
0x180409c9f  mov     ecx, r15d
0x180409ca2  call    CheckWPPLevelFlagsEnabledForProvider
0x180409ca7  test    eax, eax
0x180409ca9  jz      short loc_180409CB0
0x180409cab  mov     esi, r15d
0x180409cae  jmp     short loc_180409CB3
0x180409cb0  mov     esi, r14d
0x180409cb3  call    THStateCheckForTraceOverride
0x180409cb8  test    eax, eax
0x180409cba  jnz     short loc_180409CD0
0x180409cbc  mov     r8d, ebx
0x180409cbf  lea     edx, [rax+2]
0x180409cc2  xor     ecx, ecx
0x180409cc4  call    CheckWPPLevelFlagsEnabledForProvider
0x180409cc9  mov     ecx, r14d
0x180409ccc  test    eax, eax
0x180409cce  jz      short loc_180409CD3
0x180409cd0  mov     ecx, r15d
0x180409cd3  mov     [rsp+1A0h+var_158], edi
0x180409cd7  lea     rax, WPP_32f5d0670c583c677716e2381a9d353b_Traceguids
0x180409cde  mov     [rsp+1A0h+var_160], r13d
0x180409ce3  mov     edx, 1F0E0076h
0x180409ce8  mov     [rsp+1A0h+var_168], rax
0x180409ced  mov     [rsp+1A0h+var_170], 0Bh
0x180409cf4  jmp     loc_180409BB1
0x180409cf9  mov     rcx, [rsp+1A0h+var_128]
0x180409cfe  lea     rdx, [rbp+0A0h+var_C8]
0x180409d02  call    cs:__imp_SampGetUserAccountSettings
0x180409d08  mov     edi, eax
0x180409d0a  test    eax, eax
0x180409d0c  jns     loc_180409DF2
0x180409d12  mov     esi, 2
0x180409d17  mov     ecx, esi
0x180409d19  call    IncrementWPPPerfCountersForLevel
0x180409d1e  lea     ebx, [rsi+0Bh]
0x180409d21  test    eax, eax
0x180409d23  jnz     short loc_180409D77
0x180409d25  call    THStateCheckForTraceOverride
0x180409d2a  test    eax, eax
0x180409d2c  jnz     short loc_180409D77
0x180409d2e  mov     r8d, ebx
0x180409d31  mov     edx, esi
0x180409d33  xor     ecx, ecx
0x180409d35  call    CheckWPPLevelFlagsEnabledForProvider
0x180409d3a  test    eax, eax
0x180409d3c  jnz     short loc_180409D77
0x180409d3e  mov     eax, cs:gfTraceToSecondProvider
0x180409d44  test    eax, eax
0x180409d46  jz      loc_18040A482
0x180409d4c  call    THStateCheckForTraceOverride
0x180409d51  test    eax, eax
0x180409d53  jnz     short loc_180409D77
0x180409d55  call    ThStateCheckIfTraceToSecondProvier
0x180409d5a  test    eax, eax
0x180409d5c  jz      loc_18040A482
0x180409d62  mov     r8d, ebx
0x180409d65  mov     edx, esi
0x180409d67  mov     ecx, r15d
0x180409d6a  call    CheckWPPLevelFlagsEnabledForProvider
0x180409d6f  test    eax, eax
0x180409d71  jz      loc_18040A482
0x180409d77  mov     eax, cs:gfTraceToSecondProvider
0x180409d7d  test    eax, eax
0x180409d7f  jz      short loc_180409DA9
0x180409d81  call    THStateCheckForTraceOverride
0x180409d86  test    eax, eax
0x180409d88  jnz     short loc_180409DA4
0x180409d8a  call    ThStateCheckIfTraceToSecondProvier
0x180409d8f  test    eax, eax
0x180409d91  jz      short loc_180409DA9
0x180409d93  mov     r8d, ebx
0x180409d96  mov     edx, esi
0x180409d98  mov     ecx, r15d
0x180409d9b  call    CheckWPPLevelFlagsEnabledForProvider
0x180409da0  test    eax, eax
0x180409da2  jz      short loc_180409DA9
0x180409da4  mov     esi, r15d
0x180409da7  jmp     short loc_180409DAC
0x180409da9  mov     esi, r14d
0x180409dac  call    THStateCheckForTraceOverride
0x180409db1  test    eax, eax
0x180409db3  jnz     short loc_180409DC9
0x180409db5  mov     r8d, ebx
0x180409db8  lea     edx, [rax+2]
0x180409dbb  xor     ecx, ecx
0x180409dbd  call    CheckWPPLevelFlagsEnabledForProvider
0x180409dc2  mov     ecx, r14d
0x180409dc5  test    eax, eax
0x180409dc7  jz      short loc_180409DCC
0x180409dc9  mov     ecx, r15d
0x180409dcc  mov     [rsp+1A0h+var_158], edi
0x180409dd0  lea     rax, WPP_32f5d0670c583c677716e2381a9d353b_Traceguids
0x180409dd7  mov     [rsp+1A0h+var_160], r13d
0x180409ddc  mov     edx, 1F0E0085h
0x180409de1  mov     [rsp+1A0h+var_168], rax
0x180409de6  mov     [rsp+1A0h+var_170], 0Ch
0x180409ded  jmp     loc_180409BB1
0x180409df2  mov     rcx, [rsp+1A0h+var_128]
0x180409df7  lea     r8, [rbp+0A0h+var_90]
  ... truncated ...
```
