# CipRefreshPolicies

- ea: `0x180057408`
- end: `0x180057d10`
- name: `CipRefreshPolicies`
- size: `2312`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180070808`

## callees

- `0x18001e044`
- `0x18001e054`
- `0x18001ea00`
- `0x18002bef0`
- `0x180057408`
- `0x180057fb0`
- `0x18005802c`
- `0x180058090`
- `0x1800580e8`
- `0x180058410`
- `0x1800584e0`
- `0x1800585d8`
- `0x18005b644`
- `0x18005c5fc`
- `0x18005c7d0`
- `0x18005cad4`
- `0x180060344`
- `0x180061684`
- `0x180065c48`
- `0x18006c798`
- `0x18006c9e8`
- `0x18006ca88`
- `0x18006ece4`
- `0x18006ef34`
- `0x18006efe0`
- `0x18006f584`
- `0x18006fcf8`
- `0x180070110`
- `0x1800701b0`
- `0x180071aa4`
- `0x180073248`
- `0x180075e9c`
- `0x180076f30`
- `0x180076fe0`
- `0x18007ad30`
- `0x18007aea0`
- `0x18007af6c`
- `0x18007b120`
- `0x18007b474`
- `0x18007b54c`
- `0x18007be64`
- `0x18008bc2c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180057494`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180057c5e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180057494`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180057c5e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800574a9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057862`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057aad`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057b8f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057be3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057c73`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800574a9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057862`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057aad`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057b8f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057be3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180057c73`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057877`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800578af`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057adb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057bbd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057ca3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057cff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057877`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800578af`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057adb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057bbd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057ca3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180057cff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800575bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800575bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800578bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180057caf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800578bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180057caf`
- `ntoskrnl!EtwWrite` at `0x180057518`
- `ntoskrnl!EtwWrite` at `0x180057518`

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
  xmmword_180048A08 = v95;
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
  ExAcquirePushLockExclusiveEx(&qword_180048778, 0);
  dword_1800486E8 = v62;
  CipBlackBoxUpdate(&dword_1800486E8, 88, 4);
  ExReleasePushLockExclusiveEx(&qword_180048778, 0);
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
0x180057408  mov     [rsp-8+arg_18], rbx
0x18005740d  push    rbp
0x18005740e  push    rsi
0x18005740f  push    rdi
0x180057410  push    r12
0x180057412  push    r13
0x180057414  push    r14
0x180057416  push    r15
0x180057418  lea     rbp, [rsp-40h]
0x18005741d  sub     rsp, 140h
0x180057424  mov     rax, cs:__security_cookie
0x18005742b  xor     rax, rsp
0x18005742e  mov     [rbp+70h+var_40], rax
0x180057432  xor     r13d, r13d
0x180057435  mov     [rbp+70h+var_B8], r8
0x180057439  xorps   xmm0, xmm0
0x18005743c  mov     [rbp+70h+var_DC], edx
0x18005743f  mov     r15b, r13b
0x180057442  mov     [rbp+70h+var_C8], ecx
0x180057445  mov     r14b, r13b
0x180057448  mov     [rsp+170h+var_F8], r15d
0x18005744d  mov     [rsp+170h+var_FC], r14d
0x180057452  mov     r12b, r13b
0x180057455  mov     [rbp+70h+var_90], r13
0x180057459  mov     esi, r13d
0x18005745c  mov     [rsp+170h+var_FE], r13b
0x180057461  mov     [rbp+70h+var_7C], r13d
0x180057465  mov     [rsp+170h+var_100], r13b
0x18005746a  mov     [rbp+70h+var_C0], r13
0x18005746e  mov     [rbp+70h+var_D0], r13
0x180057472  mov     [rbp+70h+var_98], r13
0x180057476  mov     [rbp+70h+var_F0], r13d
0x18005747a  mov     [rbp+70h+var_A8], r13
0x18005747e  mov     [rsp+170h+var_F4], r13d
0x180057483  mov     [rbp+70h+var_B0], r13
0x180057487  movups  [rbp+70h+var_60], xmm0
0x18005748b  mov     [rsp+170h+var_FD], r13b
0x180057490  movups  [rbp+70h+var_50], xmm0
0x180057494  call    cs:__imp_KeEnterCriticalRegion
0x18005749b  nop     dword ptr [rax+rax+00h]
0x1800574a0  xor     edx, edx
0x1800574a2  lea     rcx, g_CipPolicyLock
0x1800574a9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800574b0  nop     dword ptr [rax+rax+00h]
0x1800574b5  mov     rax, cs:g_CiPolicyGenerationCounter
0x1800574bc  mov     rdx, 3FFFFFFFFFFFFFFh
0x1800574c6  cmp     rax, rdx
0x1800574c9  lea     rcx, [rax+1]
0x1800574cd  cmovnb  rcx, rax
0x1800574d1  mov     [rbp+70h+var_88], rcx
0x1800574d5  call    SIPolicyGetActiveState
0x1800574da  mov     ecx, cs:g_NumberOfSiPolicies
0x1800574e0  lea     r9d, [r13+1]; UserDataCount
0x1800574e4  mov     rbx, rax
0x1800574e7  mov     [rbp+70h+var_A0], rax
0x1800574eb  lea     rax, [rbp+70h+var_E8]
0x1800574ef  mov     [rbp+70h+var_E8], ecx
0x1800574f2  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x1800574f9  lea     rdx, CiPolicyRefreshStarted; EventDescriptor
0x180057500  mov     [rbp+70h+var_70.Ptr], rax
0x180057504  xor     r8d, r8d; ActivityId
0x180057507  lea     rax, [rbp+70h+var_70]
0x18005750b  mov     qword ptr [rbp+70h+var_70.Size], 4
0x180057513  mov     [rsp+170h+UserData], rax; UserData
0x180057518  call    cs:__imp_EtwWrite
0x18005751f  nop     dword ptr [rax+rax+00h]
0x180057524  call    CiSetNightsWatchPolicyStateRegKeys
0x180057529  mov     edi, eax
0x18005752b  test    eax, eax
0x18005752d  js      loc_18005782A
0x180057533  lea     rcx, [rsp+170h+var_FD]
0x180057538  call    CipLoadAndValidateRevocationList
0x18005753d  mov     [rbp+70h+var_D8], eax
0x180057540  mov     r13d, eax
0x180057543  test    eax, eax
0x180057545  jns     short loc_180057558
0x180057547  xor     r8d, r8d
0x18005754a  lea     rdx, CiDriverStlRefreshFailed
0x180057551  mov     ecx, eax
0x180057553  call    CiLogStatusEventWithCorrelationId
0x180057558  lea     rdx, [rbp+70h+var_D0]
0x18005755c  mov     rcx, rbx
0x18005755f  call    SIPolicyCloneState
0x180057564  mov     edi, eax
0x180057566  test    eax, eax
0x180057568  js      loc_18005782A
0x18005756e  lea     rdx, [rsp+170h+var_FF]
0x180057573  lea     rcx, [rbp+70h+var_E0]
0x180057577  call    SIPolicyGetTestsigningPolicy
0x18005757c  mov     edi, eax
0x18005757e  test    eax, eax
0x180057580  js      loc_18005782A
0x180057586  lea     rdx, [rbp+70h+var_E8]
0x18005758a  mov     [rbp+70h+var_70.Ptr], rsi
0x18005758e  lea     rcx, [rbp+70h+var_70]
0x180057592  mov     [rbp+70h+var_E8], esi
0x180057595  call    CipGetTenantIds
0x18005759a  mov     rbx, [rbp+70h+var_70.Ptr]
0x18005759e  test    eax, eax
0x1800575a0  js      short loc_1800575AE
0x1800575a2  mov     r9d, [rbp+70h+var_E8]
0x1800575a6  mov     r8, rbx
0x1800575a9  call    SIPolicyLoadAuthorizationTokens
0x1800575ae  test    rbx, rbx
0x1800575b1  jz      short loc_1800575C7
0x1800575b3  mov     edx, 63734943h; Tag
0x1800575b8  mov     rcx, rbx; P
0x1800575bb  call    cs:__imp_ExFreePoolWithTag
0x1800575c2  nop     dword ptr [rax+rax+00h]
0x1800575c7  mov     r12, [rbp+70h+var_D0]
0x1800575cb  xor     r15d, r15d
0x1800575ce  cmp     r15d, [rbp+70h+var_DC]
0x1800575d2  jnb     loc_18005792E
0x1800575d8  mov     r14, [rbp+70h+var_B8]
0x1800575dc  mov     eax, r15d
0x1800575df  add     r14, 18h
0x1800575e3  imul    rbx, rax, 38h ; '8'
0x1800575e7  add     r14, rbx
0x1800575ea  mov     rcx, r14
0x1800575ed  call    CiLogSIPolicyRefreshAttempt
0x1800575f2  lea     rax, [rbp+70h+var_90]
0x1800575f6  mov     r8, r14
0x1800575f9  mov     [rsp+170h+UserData], rax
0x1800575fe  lea     r9, [rsp+170h+var_FE]
0x180057603  mov     rax, [rbp+70h+var_A0]
0x180057607  mov     rcx, [rax]
0x18005760a  call    SIPolicyIsSignedPolicyRequired
0x18005760f  mov     edi, eax
0x180057611  test    eax, eax
0x180057613  js      loc_18005781B
0x180057619  mov     rcx, [rbp+70h+var_B8]
0x18005761d  mov     r8b, [rsp+170h+var_FE]
0x180057622  mov     [rsp+170h+var_FF], 0
0x180057627  mov     eax, [rbx+rcx+30h]
0x18005762b  mov     r9b, [rbx+rcx+10h]
0x180057630  mov     [rbp+70h+var_80], eax
0x180057633  mov     rax, [rbx+rcx+28h]
0x180057638  mov     rcx, r12
0x18005763b  mov     [rbp+70h+var_78], rax
0x18005763f  lea     rax, [rbp+70h+var_C0]
0x180057643  mov     [rsp+170h+var_110], rax
0x180057648  lea     rax, [rsp+170h+var_FF]
0x18005764d  mov     [rsp+170h+var_128], rax
0x180057652  lea     rax, [rbp+70h+var_80]
0x180057656  mov     [rsp+170h+var_130], rax
0x18005765b  mov     rax, [rbp+70h+var_90]
0x18005765f  mov     [rsp+170h+var_140], r14
0x180057664  mov     [rsp+170h+var_148], rax
0x180057669  mov     byte ptr [rsp+170h+UserData], 1
0x18005766e  call    SIPolicyParsePolicyData
0x180057673  mov     rsi, [rbp+70h+var_C0]
0x180057677  mov     edi, eax
0x180057679  test    eax, eax
0x18005767b  js      loc_180057807
0x180057681  test    rsi, rsi
0x180057684  jnz     short loc_180057691
0x180057686  cmp     [rsp+170h+var_FF], sil
0x18005768b  jz      loc_180057807
0x180057691  mov     rax, [rbp+70h+var_B8]
0x180057695  cmp     byte ptr [rbx+rax+13h], 0
0x18005769a  jz      short loc_1800576F7
0x18005769c  cmp     dword ptr [rsi+28h], 6
0x1800576a0  sbb     rax, rax
0x1800576a3  and     rax, 0FFFFFFFFFFFFFD40h
0x1800576a9  mov     rcx, [rax+rsi+2D0h]
0x1800576b1  sub     rcx, cs:SiPolicyIDEndpointSec
0x1800576b8  jnz     short loc_1800576C9
0x1800576ba  mov     rcx, [rax+rsi+2D8h]
0x1800576c2  sub     rcx, cs:qword_180032B98
0x1800576c9  test    rcx, rcx
0x1800576cc  jnz     short loc_1800576DA
0x1800576ce  mov     rcx, rsi
0x1800576d1  call    SIPolicyIsBasePolicy
0x1800576d6  test    al, al
0x1800576d8  jz      short loc_1800576F7
0x1800576da  mov     edx, edi
0x1800576dc  mov     rcx, r14
0x1800576df  call    CiLogSIPolicyRefreshIgnored
0x1800576e4  mov     rcx, rsi
0x1800576e7  call    SIPolicyUninitialize
0x1800576ec  xor     esi, esi
0x1800576ee  mov     [rbp+70h+var_C0], rsi
0x1800576f2  jmp     loc_180057813
0x1800576f7  test    rsi, rsi
0x1800576fa  jz      short loc_180057707
0x1800576fc  mov     rdx, rsi
0x1800576ff  mov     rcx, r12
0x180057702  call    SIPolicyEnforceSupplementalPolicyOptions
0x180057707  xor     edx, edx
0x180057709  cmp     edx, cs:g_NumberOfSiPolicies
0x18005770f  jnb     loc_180057795
0x180057715  mov     rax, cs:g_SiPolicyHandles
0x18005771c  mov     r9, [rax+rdx*8]
0x180057720  cmp     dword ptr [r9+28h], 6
0x180057725  sbb     rax, rax
0x180057728  and     rax, 0FFFFFFFFFFFFFD50h
0x18005772e  lea     r8, [rax+2C0h]
0x180057735  add     r8, r9
0x180057738  mov     rcx, [r8]
0x18005773b  sub     rcx, [r14]
0x18005773e  jnz     short loc_180057748
0x180057740  mov     rcx, [r8+8]
0x180057744  sub     rcx, [r14+8]
0x180057748  test    rcx, rcx
0x18005774b  jz      short loc_180057751
0x18005774d  inc     edx
0x18005774f  jmp     short loc_180057709
0x180057751  test    dword ptr [r9+2Ch], 10000000h
0x180057759  jnz     short loc_180057767
0x18005775b  lea     r8, CiPolicyRefreshNotAllowed
0x180057762  mov     rcx, r9
0x180057765  jmp     short loc_1800577E6
0x180057767  test    rsi, rsi
0x18005776a  jnz     short loc_18005777C
0x18005776c  mov     rdx, r8
0x18005776f  mov     rcx, r12
0x180057772  call    SIPolicyStateRemovePolicy
0x180057777  jmp     loc_1800577FD
0x18005777c  mov     rdx, r9
0x18005777f  mov     rcx, rsi
0x180057782  call    SIPolicyCompare
0x180057787  test    al, al
0x180057789  jz      short loc_1800577F0
0x18005778b  mov     rcx, rsi
0x18005778e  call    SIPolicyUninitialize
0x180057793  xor     esi, esi
0x180057795  test    rsi, rsi
0x180057798  jz      loc_1800576E4
0x18005779e  mov     rcx, rsi
0x1800577a1  call    SIPolicyIsBasePolicy
0x1800577a6  test    al, al
0x1800577a8  jnz     short loc_1800577D3
0x1800577aa  cmp     dword ptr [rsi+28h], 6
0x1800577ae  mov     rcx, r12
0x1800577b1  sbb     rdx, rdx
0x1800577b4  and     rdx, 0FFFFFFFFFFFFFD40h
0x1800577bb  add     rdx, 2D0h
0x1800577c2  add     rdx, rsi
0x1800577c5  call    SIPolicyStateFindPolicy
0x1800577ca  test    rax, rax
0x1800577cd  jz      loc_1800576E4
0x1800577d3  test    dword ptr [rsi+2Ch], 10000000h
0x1800577da  jnz     short loc_1800577F0
0x1800577dc  lea     r8, CiPolicyRefreshNonRebootless
0x1800577e3  mov     rcx, rsi
0x1800577e6  call    CiLogSIPolicyRefresh
0x1800577eb  jmp     loc_1800576E4
0x1800577f0  mov     rdx, rsi
0x1800577f3  mov     rcx, r12
0x1800577f6  call    SIPolicyStateAddPolicy
0x1800577fb  xor     esi, esi
0x1800577fd  mov     [rsp+170h+var_100], 1
0x180057802  jmp     loc_1800576E4
0x180057807  mov     edx, edi
0x180057809  mov     rcx, r14
0x18005780c  call    CiLogSIPolicyRefreshIgnored
0x180057811  xor     edi, edi
0x180057813  inc     r15d
0x180057816  jmp     loc_1800575CE
0x18005781b  mov     r12b, [rsp+170h+var_100]
0x180057820  mov     r14d, [rsp+170h+var_FC]
0x180057825  mov     r15d, [rsp+170h+var_F8]
0x18005782a  test    edi, edi
0x18005782c  cmovs   r13d, edi
0x180057830  mov     edx, r13d
0x180057833  call    CiLogSIPolicyRefreshFinished
0x180057838  test    r12b, r12b
0x18005783b  jnz     short loc_180057844
0x18005783d  cmp     [rsp+170h+var_FD], r12b
0x180057842  jz      short loc_18005784B
0x180057844  mov     cl, 1
0x180057846  call    CiInstrumentInitialize
0x18005784b  call    Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline
0x180057850  test    eax, eax
0x180057852  jz      short loc_18005786E
0x180057854  cmp     r15b, r14b
0x180057857  jz      short loc_18005786E
0x180057859  xor     edx, edx
0x18005785b  lea     rcx, g_CipPolicyRefreshDefenderSequencingLock
0x180057862  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x180057869  nop     dword ptr [rax+rax+00h]
0x18005786e  xor     edx, edx
0x180057870  lea     rcx, g_CipPolicyLock
0x180057877  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18005787e  nop     dword ptr [rax+rax+00h]
0x180057883  call    Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline
0x180057888  test    eax, eax
0x18005788a  jz      short loc_1800578BB
0x18005788c  cmp     r15b, r14b
0x18005788f  jz      short loc_1800578BB
0x180057891  mov     rax, cs:g_EtwEventHandle
0x180057898  test    rax, rax
0x18005789b  jz      short loc_1800578A6
0x18005789d  movzx   ecx, r14b
0x1800578a1  call    CiCatDbMpSmartLockerEnable
0x1800578a6  xor     edx, edx
0x1800578a8  lea     rcx, g_CipPolicyRefreshDefenderSequencingLock
0x1800578af  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800578b6  nop     dword ptr [rax+rax+00h]
0x1800578bb  call    cs:__imp_KeLeaveCriticalRegion
  ... truncated ...
```
