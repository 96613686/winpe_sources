# CipRefreshPolicies

- ea: `0x180058120`
- end: `0x180058a28`
- name: `CipRefreshPolicies`
- size: `2312`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180071ab8`

## callees

- `0x18001df88`
- `0x18001df98`
- `0x18001e940`
- `0x18002bf20`
- `0x180058120`
- `0x180058cc8`
- `0x180058d44`
- `0x180058da8`
- `0x180058e00`
- `0x180059128`
- `0x1800591f8`
- `0x1800592f0`
- `0x18005c354`
- `0x18005cc64`
- `0x18005ce38`
- `0x18005d13c`
- `0x180060af8`
- `0x180061ec8`
- `0x18006653c`
- `0x18006d56c`
- `0x18006d7bc`
- `0x18006d85c`
- `0x18006ff94`
- `0x1800701e4`
- `0x180070290`
- `0x180070834`
- `0x180070fa8`
- `0x1800713c0`
- `0x180071460`
- `0x180072d54`
- `0x1800744f8`
- `0x18007744c`
- `0x1800784e0`
- `0x180078590`
- `0x18007c2e0`
- `0x18007c450`
- `0x18007c51c`
- `0x18007c6d0`
- `0x18007ca24`
- `0x18007cafc`
- `0x18007d414`
- `0x18008d25c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800581ac`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180058976`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800581ac`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180058976`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800581c1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18005857a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800587c5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800588a7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800588fb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18005898b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800581c1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18005857a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800587c5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800588a7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800588fb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18005898b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005858f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800585c7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800587f3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800588d5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800589bb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180058a17`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005858f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800585c7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800587f3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800588d5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800589bb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180058a17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800582d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800582d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800585d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800589c7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800585d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800589c7`
- `ntoskrnl!EtwWrite` at `0x180058230`
- `ntoskrnl!EtwWrite` at `0x180058230`

## pseudocode

```c
__int64 __fastcall CipRefreshPolicies(unsigned int a1, unsigned int a2, __int64 a3)
{
  int v3; // r14d
  int v4; // r15d
  unsigned int v5; // r13d
  char v6; // r12
  __int64 v7; // rsi
  __int64 v8; // rcx
  __int64 ActiveState; // rbx
  __int64 v10; // rcx
  int TestsigningPolicy; // edi
  int v12; // eax
  int TenantIds; // eax
  __int64 k; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  void *Ptr; // rbx
  __int64 v18; // r12
  unsigned int i; // r15d
  __int64 v20; // rbx
  _QWORD *v21; // r14
  int v22; // edx
  int v23; // edx
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  unsigned __int64 v27; // rax
  __int64 v28; // rcx
  __int64 j; // rdx
  __int64 v30; // r9
  unsigned __int64 v31; // rax
  _QWORD *v32; // r8
  __int64 v33; // rcx
  __int64 *v34; // r8
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v43; // r14
  __int64 v44; // r13
  __int64 v45; // r15
  _QWORD *v46; // rbx
  __int64 v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  unsigned __int64 v50; // rax
  __int64 v51; // r9
  _QWORD *v52; // rbx
  __int64 v53; // rbx
  int v54; // edx
  int v55; // r8d
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  int v62; // ebx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 m; // rdx
  char v66; // [rsp+38h] [rbp-C8h]
  char v67; // [rsp+50h] [rbp-B0h]
  char v68; // [rsp+58h] [rbp-A8h]
  char v69; // [rsp+70h] [rbp-90h]
  char v70; // [rsp+71h] [rbp-8Fh] BYREF
  char v71; // [rsp+72h] [rbp-8Eh] BYREF
  char v72; // [rsp+73h] [rbp-8Dh] BYREF
  int v73; // [rsp+74h] [rbp-8Ch]
  int v74; // [rsp+78h] [rbp-88h]
  unsigned int v75; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v76; // [rsp+80h] [rbp-80h] BYREF
  int v77; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v78[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v79; // [rsp+94h] [rbp-6Ch]
  int v80; // [rsp+98h] [rbp-68h] BYREF
  __int64 v81; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v82; // [rsp+A8h] [rbp-58h]
  __int64 v83; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-48h]
  __int64 v85; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v86; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v87; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v88; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v89; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v90; // [rsp+E8h] [rbp-18h]
  _DWORD v91[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v92; // [rsp+F8h] [rbp-8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+100h] [rbp+0h] BYREF
  __int128 v94; // [rsp+110h] [rbp+10h] BYREF
  __int128 v95; // [rsp+120h] [rbp+20h]

  v5 = 0;
  v84 = a3;
  v79 = a2;
  LOBYTE(v4) = 0;
  v82 = a1;
  LOBYTE(v3) = 0;
  v74 = v4;
  v73 = v3;
  v6 = 0;
  v89 = 0;
  v7 = 0;
  v71 = 0;
  v91[1] = 0;
  v69 = 0;
  v83 = 0;
  v81 = 0;
  v88 = 0;
  v76 = 0;
  v86 = 0;
  v75 = 0;
  v85 = 0;
  v94 = 0;
  v72 = 0;
  v95 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&g_CipPolicyLock, 0);
  v8 = g_CiPolicyGenerationCounter + 1;
  if ( (unsigned __int64)g_CiPolicyGenerationCounter >= 0x3FFFFFFFFFFFFFFLL )
    v8 = g_CiPolicyGenerationCounter;
  v90 = v8;
  ActiveState = SIPolicyGetActiveState();
  v87 = (_QWORD *)ActiveState;
  v77 = g_NumberOfSiPolicies;
  UserData.Ptr = (ULONGLONG)&v77;
  *(_QWORD *)&UserData.Size = 4;
  EtwWrite(g_EtwEventHandle, &CiPolicyRefreshStarted, 0, 1u, &UserData);
  TestsigningPolicy = CiSetNightsWatchPolicyStateRegKeys();
  if ( TestsigningPolicy < 0 )
    goto LABEL_51;
  v12 = CipLoadAndValidateRevocationList(&v72);
  v80 = v12;
  v5 = v12;
  if ( v12 < 0 )
    CiLogStatusEventWithCorrelationId(v12, (const EVENT_DESCRIPTOR *)CiDriverStlRefreshFailed, 0);
  TestsigningPolicy = SIPolicyCloneState(ActiveState, &v81);
  if ( TestsigningPolicy < 0 )
    goto LABEL_51;
  TestsigningPolicy = SIPolicyGetTestsigningPolicy(v78, &v70);
  if ( TestsigningPolicy < 0 )
    goto LABEL_51;
  UserData.Ptr = 0;
  v77 = 0;
  TenantIds = CipGetTenantIds((GUID **)&UserData, (ULONG *)&v77);
  Ptr = (void *)UserData.Ptr;
  if ( TenantIds >= 0 )
    SIPolicyLoadAuthorizationTokens(v15, k, UserData.Ptr, (unsigned int)v77);
  if ( Ptr )
    ExFreePoolWithTag(Ptr, 0x63734943u);
  v18 = v81;
  for ( i = 0; i < v79; ++i )
  {
    v20 = 56LL * i;
    v21 = (_QWORD *)(v20 + v84 + 24);
    CiLogSIPolicyRefreshAttempt(v21);
    TestsigningPolicy = SIPolicyIsSignedPolicyRequired(*v87, v22, (_DWORD)v21, (unsigned int)&v71, (__int64)&v89);
    if ( TestsigningPolicy < 0 )
    {
      v6 = v69;
      goto LABEL_50;
    }
    LOBYTE(v24) = v71;
    v70 = 0;
    LOBYTE(v25) = *(_BYTE *)(v20 + v84 + 16);
    v91[0] = *(_DWORD *)(v20 + v84 + 48);
    v92 = *(_QWORD *)(v20 + v84 + 40);
    v26 = SIPolicyParsePolicyData(
            v18,
            v23,
            v24,
            v25,
            1,
            v89,
            (__int64)v21,
            v66,
            (__int64)v91,
            (__int64)&v70,
            v67,
            v68,
            (__int64)&v83);
    v7 = v83;
    TestsigningPolicy = v26;
    if ( v26 >= 0 && (v83 || v70) )
    {
      if ( !*(_BYTE *)(v20 + v84 + 19) )
        goto LABEL_25;
      v27 = -(__int64)(*(_DWORD *)(v83 + 40) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
      v28 = *(_QWORD *)(v27 + v83 + 720) - SiPolicyIDEndpointSec;
      if ( !v28 )
        v28 = *(_QWORD *)(v27 + v83 + 728) - 0x48F222A00D2EB091LL;
      if ( v28 || (unsigned __int8)SIPolicyIsBasePolicy(v83) )
      {
        CiLogSIPolicyRefreshIgnored(v21, (unsigned int)TestsigningPolicy);
      }
      else
      {
LABEL_25:
        if ( v7 )
          SIPolicyEnforceSupplementalPolicyOptions(v18, v7);
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          if ( (unsigned int)j >= g_NumberOfSiPolicies )
            goto LABEL_39;
          v30 = *((_QWORD *)g_SiPolicyHandles + j);
          v31 = -(__int64)(*(_DWORD *)(v30 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL;
          v32 = (_QWORD *)(v30 + v31 + 704);
          v33 = *v32 - *v21;
          if ( *v32 == *v21 )
            v33 = v32[1] - v21[1];
          if ( !v33 )
            break;
        }
        if ( (*(_DWORD *)(v30 + 44) & 0x10000000) == 0 )
        {
          v34 = CiPolicyRefreshNotAllowed;
          v35 = *((_QWORD *)g_SiPolicyHandles + j);
LABEL_44:
          CiLogSIPolicyRefresh(v35, j, v34);
          goto LABEL_24;
        }
        if ( v7 )
        {
          if ( (unsigned __int8)SIPolicyCompare(v7, *((_QWORD *)g_SiPolicyHandles + j)) )
          {
            SIPolicyUninitialize(v7);
            v7 = 0;
LABEL_39:
            if ( !v7
              || !(unsigned __int8)SIPolicyIsBasePolicy(v7)
              && !SIPolicyStateFindPolicy(
                    v18,
                    v7 + (-(__int64)(*(_DWORD *)(v7 + 40) < 6u) & 0xFFFFFFFFFFFFFD40uLL) + 720) )
            {
              goto LABEL_24;
            }
            if ( (*(_DWORD *)(v7 + 44) & 0x10000000) == 0 )
            {
              v34 = CiPolicyRefreshNonRebootless;
              v35 = v7;
              goto LABEL_44;
            }
          }
          SIPolicyStateAddPolicy(v18, v7);
          v7 = 0;
        }
        else
        {
          SIPolicyStateRemovePolicy(v18, v30 + v31 + 704, v32, v30);
        }
        v69 = 1;
      }
LABEL_24:
      SIPolicyUninitialize(v7);
      v7 = 0;
      v83 = 0;
      continue;
    }
    CiLogSIPolicyRefreshIgnored(v21, (unsigned int)v26);
    TestsigningPolicy = 0;
  }
  v43 = 0;
  if ( g_NumberOfSiPolicies )
  {
    v44 = SiPolicyIDEndpointSec;
    do
    {
      v45 = *((_QWORD *)g_SiPolicyHandles + v43);
      v46 = (_QWORD *)(v45 + (-(__int64)(*(_DWORD *)(v45 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL) + 704);
      if ( !(unsigned __int8)SIPolicyIsSystemPolicy(v46, k, v16) )
      {
        for ( k = 0; (unsigned int)k < v79; k = (unsigned int)(k + 1) )
        {
          v16 = 56LL * (unsigned int)k;
          v47 = *v46 - *(_QWORD *)(v16 + v84 + 24);
          if ( *v46 == *(_QWORD *)(v16 + v84 + 24) )
            v47 = v46[1] - *(_QWORD *)(v16 + v84 + 32);
          if ( !v47 )
            goto LABEL_82;
        }
        v48 = *(_DWORD *)(v45 + 44);
        if ( (v48 & 0x10000000) != 0 && (v48 & 0x80000) != 0 )
        {
          SIPolicyStateRemovePolicy(v81, v46, v16, v84);
          v44 = SiPolicyIDEndpointSec;
          v69 = 1;
        }
        v49 = *((_QWORD *)g_SiPolicyHandles + v43);
        v50 = -(__int64)(*(_DWORD *)(v49 + 40) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
        k = *(_QWORD *)(v50 + v49 + 720) - v44;
        if ( !k )
          k = *(_QWORD *)(v50 + v49 + 728) - 0x48F222A00D2EB091LL;
        if ( !k && !(unsigned __int8)SIPolicyIsBasePolicy(v49) )
        {
          SIPolicyStateRemovePolicy(v81, v46, v16, v51);
          v44 = SiPolicyIDEndpointSec;
          v69 = 1;
        }
      }
LABEL_82:
      v43 = (unsigned int)(v43 + 1);
    }
    while ( (unsigned int)v43 < g_NumberOfSiPolicies );
    v5 = v80;
  }
  v6 = v69;
  if ( !v69 )
  {
    v52 = v87;
    if ( (g_CiPolicyState & 0x200) != 0 )
    {
      TestsigningPolicy = CipPrepareStateSigners(v87, &v75, &v85);
      if ( TestsigningPolicy < 0 )
        goto LABEL_50;
      TestsigningPolicy = CipPrepareStateSigners(v52, &v76, &v86);
      if ( TestsigningPolicy < 0 )
        goto LABEL_50;
      ExAcquirePushLockExclusiveEx(&g_CipRuntimeSignersLock, 0);
      CipUnregisterPreparedSigners(v75, v85);
      CipRegisterPreparedSigners(v76, v86);
      ExReleasePushLockExclusiveEx(&g_CipRuntimeSignersLock, 0);
    }
    SIPolicyForEachPolicy2(v52);
LABEL_50:
    LOBYTE(v3) = v73;
    LOBYTE(v4) = v74;
    goto LABEL_51;
  }
  LOBYTE(k) = 1;
  TestsigningPolicy = SIPolicyFinalizeInternal(&v81, k, &v88);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  TestsigningPolicy = CipPrepareStateSigners(v87, &v75, &v85);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  v53 = v88;
  TestsigningPolicy = CipPrepareStateSigners(v88, &v76, &v86);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  v80 = 0;
  TestsigningPolicy = SIPolicyStatePreparePolicyHash(v53, v54, v55, (unsigned int)&v80, (__int64)&v94);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  TestsigningPolicy = CipHvciRefreshPolicy(v82, v79, v84);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  ExAcquirePushLockExclusiveEx(&g_CipRuntimeSignersLock, 0);
  CipUnregisterPreparedSigners(v75, v85);
  CipRegisterPreparedSigners(v76, v86);
  ExReleasePushLockExclusiveEx(&g_CipRuntimeSignersLock, 0);
  SIPolicyForEachPolicy2(v53);
  SIPolicyCommitState(&v88);
  ExAcquirePushLockExclusiveEx(&g_CipPolicyHashLock, 0);
  g_CiPolicyGenerationCounter = v90;
  g_SiPolicyHash = v94;
  xmmword_1800499E8 = v95;
  if ( (unsigned int)Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline(v57, v56, v58) )
    LOBYTE(v4) = (g_CiPolicyState & 0x20000) != 0;
  else
    LOBYTE(v4) = v74;
  CipUpdateCiSettingsFromPolicies();
  if ( (unsigned int)Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline(v60, v59, v61) )
    LOBYTE(v3) = (g_CiPolicyState & 0x20000) != 0;
  else
    LOBYTE(v3) = v73;
  CiSetRuntimeUmciSigningLevel();
  v62 = g_CiPolicyState;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&qword_180049778, 0);
  dword_1800496E8 = v62;
  CipBlackBoxUpdate(&dword_1800496E8, 88, 4);
  ExReleasePushLockExclusiveEx(&qword_180049778, 0);
  KeLeaveCriticalRegion();
  LOBYTE(v64) = 1;
  for ( m = 0; (unsigned int)m < g_NumberOfSiPolicies; m = (unsigned int)(m + 1) )
  {
    v63 = *((_QWORD *)g_SiPolicyHandles + m);
    if ( (*(_DWORD *)(v63 + 44) & 0x200) == 0 )
    {
      LOBYTE(v64) = 0;
      break;
    }
  }
  if ( (v82 & 0x1000000) == 0 || !(_BYTE)v64 )
    CipForceImageRevalidation(v63, m, v64);
  ExReleasePushLockExclusiveEx(&g_CipPolicyHashLock, 0);
LABEL_51:
  if ( TestsigningPolicy < 0 )
    v5 = TestsigningPolicy;
  CiLogSIPolicyRefreshFinished(v10, v5);
  if ( v6 || v72 )
  {
    LOBYTE(v37) = 1;
    CiInstrumentInitialize(v37);
  }
  if ( (unsigned int)Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline(v37, v36, v38)
    && (_BYTE)v4 != (_BYTE)v3 )
  {
    ExAcquirePushLockExclusiveEx(&g_CipPolicyRefreshDefenderSequencingLock, 0);
  }
  ExReleasePushLockExclusiveEx(&g_CipPolicyLock, 0);
  if ( (unsigned int)Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline(v40, v39, v41)
    && (_BYTE)v4 != (_BYTE)v3 )
  {
    if ( g_EtwEventHandle )
      CiCatDbMpSmartLockerEnable((unsigned __int8)v3);
    ExReleasePushLockExclusiveEx(&g_CipPolicyRefreshDefenderSequencingLock, 0);
  }
  KeLeaveCriticalRegion();
  CipFreeRuntimeSigners(v75, v85);
  CipFreeRuntimeSigners(v76, v86);
  SIPolicyReleaseState(&v87);
  SIPolicyReleaseState(&v88);
  SIPolicyReleaseMutableState(&v81);
  SIPolicyUninitialize(v7);
  return v5;
}

```

## disassembly

```asm
0x180058120  mov     [rsp-8+arg_18], rbx
0x180058125  push    rbp
0x180058126  push    rsi
0x180058127  push    rdi
0x180058128  push    r12
0x18005812a  push    r13
0x18005812c  push    r14
0x18005812e  push    r15
0x180058130  lea     rbp, [rsp-40h]
0x180058135  sub     rsp, 140h
0x18005813c  mov     rax, cs:__security_cookie
0x180058143  xor     rax, rsp
0x180058146  mov     [rbp+70h+var_40], rax
0x18005814a  xor     r13d, r13d
0x18005814d  mov     [rbp+70h+var_B8], r8
0x180058151  xorps   xmm0, xmm0
0x180058154  mov     [rbp+70h+var_DC], edx
0x180058157  mov     r15b, r13b
0x18005815a  mov     [rbp+70h+var_C8], ecx
0x18005815d  mov     r14b, r13b
0x180058160  mov     [rsp+170h+var_F8], r15d
0x180058165  mov     [rsp+170h+var_FC], r14d
0x18005816a  mov     r12b, r13b
0x18005816d  mov     [rbp+70h+var_90], r13
0x180058171  mov     esi, r13d
0x180058174  mov     [rsp+170h+var_FE], r13b
0x180058179  mov     [rbp+70h+var_7C], r13d
0x18005817d  mov     [rsp+170h+var_100], r13b
0x180058182  mov     [rbp+70h+var_C0], r13
0x180058186  mov     [rbp+70h+var_D0], r13
0x18005818a  mov     [rbp+70h+var_98], r13
0x18005818e  mov     [rbp+70h+var_F0], r13d
0x180058192  mov     [rbp+70h+var_A8], r13
0x180058196  mov     [rsp+170h+var_F4], r13d
0x18005819b  mov     [rbp+70h+var_B0], r13
0x18005819f  movups  [rbp+70h+var_60], xmm0
0x1800581a3  mov     [rsp+170h+var_FD], r13b
0x1800581a8  movups  [rbp+70h+var_50], xmm0
0x1800581ac  call    cs:__imp_KeEnterCriticalRegion
0x1800581b3  nop     dword ptr [rax+rax+00h]
0x1800581b8  xor     edx, edx
0x1800581ba  lea     rcx, g_CipPolicyLock
0x1800581c1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800581c8  nop     dword ptr [rax+rax+00h]
0x1800581cd  mov     rax, cs:g_CiPolicyGenerationCounter
0x1800581d4  mov     rdx, 3FFFFFFFFFFFFFFh
0x1800581de  cmp     rax, rdx
0x1800581e1  lea     rcx, [rax+1]
0x1800581e5  cmovnb  rcx, rax
0x1800581e9  mov     [rbp+70h+var_88], rcx
0x1800581ed  call    SIPolicyGetActiveState
0x1800581f2  mov     ecx, cs:g_NumberOfSiPolicies
0x1800581f8  lea     r9d, [r13+1]; UserDataCount
0x1800581fc  mov     rbx, rax
0x1800581ff  mov     [rbp+70h+var_A0], rax
0x180058203  lea     rax, [rbp+70h+var_E8]
0x180058207  mov     [rbp+70h+var_E8], ecx
0x18005820a  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180058211  lea     rdx, CiPolicyRefreshStarted; EventDescriptor
0x180058218  mov     [rbp+70h+var_70.Ptr], rax
0x18005821c  xor     r8d, r8d; ActivityId
0x18005821f  lea     rax, [rbp+70h+var_70]
0x180058223  mov     qword ptr [rbp+70h+var_70.Size], 4
0x18005822b  mov     [rsp+170h+UserData], rax; UserData
0x180058230  call    cs:__imp_EtwWrite
0x180058237  nop     dword ptr [rax+rax+00h]
0x18005823c  call    CiSetNightsWatchPolicyStateRegKeys
0x180058241  mov     edi, eax
0x180058243  test    eax, eax
0x180058245  js      loc_180058542
0x18005824b  lea     rcx, [rsp+170h+var_FD]
0x180058250  call    CipLoadAndValidateRevocationList
0x180058255  mov     [rbp+70h+var_D8], eax
0x180058258  mov     r13d, eax
0x18005825b  test    eax, eax
0x18005825d  jns     short loc_180058270
0x18005825f  xor     r8d, r8d
0x180058262  lea     rdx, CiDriverStlRefreshFailed
0x180058269  mov     ecx, eax
0x18005826b  call    CiLogStatusEventWithCorrelationId
0x180058270  lea     rdx, [rbp+70h+var_D0]
0x180058274  mov     rcx, rbx
0x180058277  call    SIPolicyCloneState
0x18005827c  mov     edi, eax
0x18005827e  test    eax, eax
0x180058280  js      loc_180058542
0x180058286  lea     rdx, [rsp+170h+var_FF]
0x18005828b  lea     rcx, [rbp+70h+var_E0]
0x18005828f  call    SIPolicyGetTestsigningPolicy
0x180058294  mov     edi, eax
0x180058296  test    eax, eax
0x180058298  js      loc_180058542
0x18005829e  lea     rdx, [rbp+70h+var_E8]
0x1800582a2  mov     [rbp+70h+var_70.Ptr], rsi
0x1800582a6  lea     rcx, [rbp+70h+var_70]
0x1800582aa  mov     [rbp+70h+var_E8], esi
0x1800582ad  call    CipGetTenantIds
0x1800582b2  mov     rbx, [rbp+70h+var_70.Ptr]
0x1800582b6  test    eax, eax
0x1800582b8  js      short loc_1800582C6
0x1800582ba  mov     r9d, [rbp+70h+var_E8]
0x1800582be  mov     r8, rbx
0x1800582c1  call    SIPolicyLoadAuthorizationTokens
0x1800582c6  test    rbx, rbx
0x1800582c9  jz      short loc_1800582DF
0x1800582cb  mov     edx, 63734943h; Tag
0x1800582d0  mov     rcx, rbx; P
0x1800582d3  call    cs:__imp_ExFreePoolWithTag
0x1800582da  nop     dword ptr [rax+rax+00h]
0x1800582df  mov     r12, [rbp+70h+var_D0]
0x1800582e3  xor     r15d, r15d
0x1800582e6  cmp     r15d, [rbp+70h+var_DC]
0x1800582ea  jnb     loc_180058646
0x1800582f0  mov     r14, [rbp+70h+var_B8]
0x1800582f4  mov     eax, r15d
0x1800582f7  add     r14, 18h
0x1800582fb  imul    rbx, rax, 38h ; '8'
0x1800582ff  add     r14, rbx
0x180058302  mov     rcx, r14
0x180058305  call    CiLogSIPolicyRefreshAttempt
0x18005830a  lea     rax, [rbp+70h+var_90]
0x18005830e  mov     r8, r14
0x180058311  mov     [rsp+170h+UserData], rax
0x180058316  lea     r9, [rsp+170h+var_FE]
0x18005831b  mov     rax, [rbp+70h+var_A0]
0x18005831f  mov     rcx, [rax]
0x180058322  call    SIPolicyIsSignedPolicyRequired
0x180058327  mov     edi, eax
0x180058329  test    eax, eax
0x18005832b  js      loc_180058533
0x180058331  mov     rcx, [rbp+70h+var_B8]
0x180058335  mov     r8b, [rsp+170h+var_FE]
0x18005833a  mov     [rsp+170h+var_FF], 0
0x18005833f  mov     eax, [rbx+rcx+30h]
0x180058343  mov     r9b, [rbx+rcx+10h]
0x180058348  mov     [rbp+70h+var_80], eax
0x18005834b  mov     rax, [rbx+rcx+28h]
0x180058350  mov     rcx, r12
0x180058353  mov     [rbp+70h+var_78], rax
0x180058357  lea     rax, [rbp+70h+var_C0]
0x18005835b  mov     [rsp+170h+var_110], rax
0x180058360  lea     rax, [rsp+170h+var_FF]
0x180058365  mov     [rsp+170h+var_128], rax
0x18005836a  lea     rax, [rbp+70h+var_80]
0x18005836e  mov     [rsp+170h+var_130], rax
0x180058373  mov     rax, [rbp+70h+var_90]
0x180058377  mov     [rsp+170h+var_140], r14
0x18005837c  mov     [rsp+170h+var_148], rax
0x180058381  mov     byte ptr [rsp+170h+UserData], 1
0x180058386  call    SIPolicyParsePolicyData
0x18005838b  mov     rsi, [rbp+70h+var_C0]
0x18005838f  mov     edi, eax
0x180058391  test    eax, eax
0x180058393  js      loc_18005851F
0x180058399  test    rsi, rsi
0x18005839c  jnz     short loc_1800583A9
0x18005839e  cmp     [rsp+170h+var_FF], sil
0x1800583a3  jz      loc_18005851F
0x1800583a9  mov     rax, [rbp+70h+var_B8]
0x1800583ad  cmp     byte ptr [rbx+rax+13h], 0
0x1800583b2  jz      short loc_18005840F
0x1800583b4  cmp     dword ptr [rsi+28h], 6
0x1800583b8  sbb     rax, rax
0x1800583bb  and     rax, 0FFFFFFFFFFFFFD40h
0x1800583c1  mov     rcx, [rax+rsi+2D0h]
0x1800583c9  sub     rcx, cs:SiPolicyIDEndpointSec
0x1800583d0  jnz     short loc_1800583E1
0x1800583d2  mov     rcx, [rax+rsi+2D8h]
0x1800583da  sub     rcx, cs:qword_180032C08
0x1800583e1  test    rcx, rcx
0x1800583e4  jnz     short loc_1800583F2
0x1800583e6  mov     rcx, rsi
0x1800583e9  call    SIPolicyIsBasePolicy
0x1800583ee  test    al, al
0x1800583f0  jz      short loc_18005840F
0x1800583f2  mov     edx, edi
0x1800583f4  mov     rcx, r14
0x1800583f7  call    CiLogSIPolicyRefreshIgnored
0x1800583fc  mov     rcx, rsi
0x1800583ff  call    SIPolicyUninitialize
0x180058404  xor     esi, esi
0x180058406  mov     [rbp+70h+var_C0], rsi
0x18005840a  jmp     loc_18005852B
0x18005840f  test    rsi, rsi
0x180058412  jz      short loc_18005841F
0x180058414  mov     rdx, rsi
0x180058417  mov     rcx, r12
0x18005841a  call    SIPolicyEnforceSupplementalPolicyOptions
0x18005841f  xor     edx, edx
0x180058421  cmp     edx, cs:g_NumberOfSiPolicies
0x180058427  jnb     loc_1800584AD
0x18005842d  mov     rax, cs:g_SiPolicyHandles
0x180058434  mov     r9, [rax+rdx*8]
0x180058438  cmp     dword ptr [r9+28h], 6
0x18005843d  sbb     rax, rax
0x180058440  and     rax, 0FFFFFFFFFFFFFD50h
0x180058446  lea     r8, [rax+2C0h]
0x18005844d  add     r8, r9
0x180058450  mov     rcx, [r8]
0x180058453  sub     rcx, [r14]
0x180058456  jnz     short loc_180058460
0x180058458  mov     rcx, [r8+8]
0x18005845c  sub     rcx, [r14+8]
0x180058460  test    rcx, rcx
0x180058463  jz      short loc_180058469
0x180058465  inc     edx
0x180058467  jmp     short loc_180058421
0x180058469  test    dword ptr [r9+2Ch], 10000000h
0x180058471  jnz     short loc_18005847F
0x180058473  lea     r8, CiPolicyRefreshNotAllowed
0x18005847a  mov     rcx, r9
0x18005847d  jmp     short loc_1800584FE
0x18005847f  test    rsi, rsi
0x180058482  jnz     short loc_180058494
0x180058484  mov     rdx, r8
0x180058487  mov     rcx, r12
0x18005848a  call    SIPolicyStateRemovePolicy
0x18005848f  jmp     loc_180058515
0x180058494  mov     rdx, r9
0x180058497  mov     rcx, rsi
0x18005849a  call    SIPolicyCompare
0x18005849f  test    al, al
0x1800584a1  jz      short loc_180058508
0x1800584a3  mov     rcx, rsi
0x1800584a6  call    SIPolicyUninitialize
0x1800584ab  xor     esi, esi
0x1800584ad  test    rsi, rsi
0x1800584b0  jz      loc_1800583FC
0x1800584b6  mov     rcx, rsi
0x1800584b9  call    SIPolicyIsBasePolicy
0x1800584be  test    al, al
0x1800584c0  jnz     short loc_1800584EB
0x1800584c2  cmp     dword ptr [rsi+28h], 6
0x1800584c6  mov     rcx, r12
0x1800584c9  sbb     rdx, rdx
0x1800584cc  and     rdx, 0FFFFFFFFFFFFFD40h
0x1800584d3  add     rdx, 2D0h
0x1800584da  add     rdx, rsi
0x1800584dd  call    SIPolicyStateFindPolicy
0x1800584e2  test    rax, rax
0x1800584e5  jz      loc_1800583FC
0x1800584eb  test    dword ptr [rsi+2Ch], 10000000h
0x1800584f2  jnz     short loc_180058508
0x1800584f4  lea     r8, CiPolicyRefreshNonRebootless
0x1800584fb  mov     rcx, rsi
0x1800584fe  call    CiLogSIPolicyRefresh
0x180058503  jmp     loc_1800583FC
0x180058508  mov     rdx, rsi
0x18005850b  mov     rcx, r12
0x18005850e  call    SIPolicyStateAddPolicy
0x180058513  xor     esi, esi
0x180058515  mov     [rsp+170h+var_100], 1
0x18005851a  jmp     loc_1800583FC
0x18005851f  mov     edx, edi
0x180058521  mov     rcx, r14
0x180058524  call    CiLogSIPolicyRefreshIgnored
0x180058529  xor     edi, edi
0x18005852b  inc     r15d
0x18005852e  jmp     loc_1800582E6
0x180058533  mov     r12b, [rsp+170h+var_100]
0x180058538  mov     r14d, [rsp+170h+var_FC]
0x18005853d  mov     r15d, [rsp+170h+var_F8]
0x180058542  test    edi, edi
0x180058544  cmovs   r13d, edi
0x180058548  mov     edx, r13d
0x18005854b  call    CiLogSIPolicyRefreshFinished
0x180058550  test    r12b, r12b
0x180058553  jnz     short loc_18005855C
0x180058555  cmp     [rsp+170h+var_FD], r12b
0x18005855a  jz      short loc_180058563
0x18005855c  mov     cl, 1
0x18005855e  call    CiInstrumentInitialize
0x180058563  call    Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline
0x180058568  test    eax, eax
0x18005856a  jz      short loc_180058586
0x18005856c  cmp     r15b, r14b
0x18005856f  jz      short loc_180058586
0x180058571  xor     edx, edx
0x180058573  lea     rcx, g_CipPolicyRefreshDefenderSequencingLock
0x18005857a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x180058581  nop     dword ptr [rax+rax+00h]
0x180058586  xor     edx, edx
0x180058588  lea     rcx, g_CipPolicyLock
0x18005858f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180058596  nop     dword ptr [rax+rax+00h]
0x18005859b  call    Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline
0x1800585a0  test    eax, eax
0x1800585a2  jz      short loc_1800585D3
0x1800585a4  cmp     r15b, r14b
0x1800585a7  jz      short loc_1800585D3
0x1800585a9  mov     rax, cs:g_EtwEventHandle
0x1800585b0  test    rax, rax
0x1800585b3  jz      short loc_1800585BE
0x1800585b5  movzx   ecx, r14b
0x1800585b9  call    CiCatDbMpSmartLockerEnable
0x1800585be  xor     edx, edx
0x1800585c0  lea     rcx, g_CipPolicyRefreshDefenderSequencingLock
0x1800585c7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800585ce  nop     dword ptr [rax+rax+00h]
0x1800585d3  call    cs:__imp_KeLeaveCriticalRegion
  ... truncated ...
```
