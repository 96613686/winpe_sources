# CipRefreshPolicies

- ea: `0x180058048`
- end: `0x180058950`
- name: `CipRefreshPolicies`
- size: `2312`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180071d98`

## callees

- `0x18001e05c`
- `0x18001e06c`
- `0x18001ea10`
- `0x18002c0d0`
- `0x180058048`
- `0x180058bf0`
- `0x180058c6c`
- `0x180058cd0`
- `0x180058d28`
- `0x180059050`
- `0x180059120`
- `0x180059218`
- `0x18005c284`
- `0x18005cc04`
- `0x18005cdd8`
- `0x18005d0dc`
- `0x180060a98`
- `0x18006202c`
- `0x1800666ac`
- `0x18006d84c`
- `0x18006da9c`
- `0x18006db3c`
- `0x180070274`
- `0x1800704c4`
- `0x180070570`
- `0x180070b14`
- `0x180071288`
- `0x1800716a0`
- `0x180071740`
- `0x180073034`
- `0x1800747d8`
- `0x18007772c`
- `0x1800787c0`
- `0x180078870`
- `0x18007ca60`
- `0x18007cbd0`
- `0x18007cc9c`
- `0x18007ce50`
- `0x18007d1a4`
- `0x18007d27c`
- `0x18007de28`
- `0x18009257c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800580d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005889e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800580d4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005889e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800580e9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800584a2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800586ed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800587cf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180058823`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800588b3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800580e9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800584a2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800586ed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800587cf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x180058823`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800588b3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800584b7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800584ef`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005871b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800587fd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800588e3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005893f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800584b7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800584ef`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005871b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800587fd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1800588e3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005893f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800581fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800581fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800584fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800588ef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800584fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800588ef`
- `ntoskrnl!EtwWrite` at `0x180058158`
- `ntoskrnl!EtwWrite` at `0x180058158`

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
  char v66; // [rsp+70h] [rbp-90h]
  char v67; // [rsp+71h] [rbp-8Fh] BYREF
  char v68; // [rsp+72h] [rbp-8Eh] BYREF
  char v69; // [rsp+73h] [rbp-8Dh] BYREF
  int v70; // [rsp+74h] [rbp-8Ch]
  int v71; // [rsp+78h] [rbp-88h]
  unsigned int v72; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v73; // [rsp+80h] [rbp-80h] BYREF
  int v74; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v75[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v76; // [rsp+94h] [rbp-6Ch]
  int v77; // [rsp+98h] [rbp-68h] BYREF
  __int64 v78; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v79; // [rsp+A8h] [rbp-58h]
  __int64 v80; // [rsp+B0h] [rbp-50h]
  __int64 v81; // [rsp+B8h] [rbp-48h]
  __int64 v82; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v83; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v84; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v85; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v86; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v87; // [rsp+E8h] [rbp-18h]
  int v88; // [rsp+F0h] [rbp-10h]
  int v89; // [rsp+F4h] [rbp-Ch]
  __int64 v90; // [rsp+F8h] [rbp-8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+100h] [rbp+0h] BYREF
  __int128 v92; // [rsp+110h] [rbp+10h] BYREF
  __int128 v93; // [rsp+120h] [rbp+20h]

  v5 = 0;
  v81 = a3;
  v76 = a2;
  LOBYTE(v4) = 0;
  v79 = a1;
  LOBYTE(v3) = 0;
  v71 = v4;
  v70 = v3;
  v6 = 0;
  v86 = 0;
  v7 = 0;
  v68 = 0;
  v89 = 0;
  v66 = 0;
  v80 = 0;
  v78 = 0;
  v85 = 0;
  v73 = 0;
  v83 = 0;
  v72 = 0;
  v82 = 0;
  v92 = 0;
  v69 = 0;
  v93 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&g_CipPolicyLock, 0);
  v8 = g_CiPolicyGenerationCounter + 1;
  if ( (unsigned __int64)g_CiPolicyGenerationCounter >= 0x3FFFFFFFFFFFFFFLL )
    v8 = g_CiPolicyGenerationCounter;
  v87 = v8;
  ActiveState = SIPolicyGetActiveState();
  v84 = (_QWORD *)ActiveState;
  v74 = g_NumberOfSiPolicies;
  UserData.Ptr = (ULONGLONG)&v74;
  *(_QWORD *)&UserData.Size = 4;
  EtwWrite(g_EtwEventHandle, &CiPolicyRefreshStarted, 0, 1u, &UserData);
  TestsigningPolicy = CiSetNightsWatchPolicyStateRegKeys();
  if ( TestsigningPolicy < 0 )
    goto LABEL_51;
  v12 = CipLoadAndValidateRevocationList(&v69);
  v77 = v12;
  v5 = v12;
  if ( v12 < 0 )
    CiLogStatusEventWithCorrelationId(v12, (const EVENT_DESCRIPTOR *)CiDriverStlRefreshFailed, 0);
  TestsigningPolicy = SIPolicyCloneState(ActiveState, &v78);
  if ( TestsigningPolicy < 0 )
    goto LABEL_51;
  TestsigningPolicy = SIPolicyGetTestsigningPolicy(v75, &v67);
  if ( TestsigningPolicy < 0 )
    goto LABEL_51;
  UserData.Ptr = 0;
  v74 = 0;
  TenantIds = CipGetTenantIds((GUID **)&UserData, (ULONG *)&v74);
  Ptr = (void *)UserData.Ptr;
  if ( TenantIds >= 0 )
    SIPolicyLoadAuthorizationTokens(v15, k, UserData.Ptr, (unsigned int)v74);
  if ( Ptr )
    ExFreePoolWithTag(Ptr, 0x63734943u);
  v18 = v78;
  for ( i = 0; i < v76; ++i )
  {
    v20 = 56LL * i;
    v21 = (_QWORD *)(v20 + v81 + 24);
    CiLogSIPolicyRefreshAttempt(v21);
    TestsigningPolicy = SIPolicyIsSignedPolicyRequired(*v84, v22, (_DWORD)v21, (unsigned int)&v68, (__int64)&v86);
    if ( TestsigningPolicy < 0 )
    {
      v6 = v66;
      goto LABEL_50;
    }
    LOBYTE(v24) = v68;
    v67 = 0;
    LOBYTE(v25) = *(_BYTE *)(v20 + v81 + 16);
    v88 = *(_DWORD *)(v20 + v81 + 48);
    v90 = *(_QWORD *)(v20 + v81 + 40);
    v26 = SIPolicyParsePolicyData(v18, v23, v24, v25, 1, v86, (__int64)v21);
    v7 = v80;
    TestsigningPolicy = v26;
    if ( v26 >= 0 && (v80 || v67) )
    {
      if ( !*(_BYTE *)(v20 + v81 + 19) )
        goto LABEL_25;
      v27 = -(__int64)(*(_DWORD *)(v80 + 40) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
      v28 = *(_QWORD *)(v27 + v80 + 720) - SiPolicyIDEndpointSec;
      if ( !v28 )
        v28 = *(_QWORD *)(v27 + v80 + 728) - 0x48F222A00D2EB091LL;
      if ( v28 || (unsigned __int8)SIPolicyIsBasePolicy(v80) )
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
        v66 = 1;
      }
LABEL_24:
      SIPolicyUninitialize(v7);
      v7 = 0;
      v80 = 0;
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
        for ( k = 0; (unsigned int)k < v76; k = (unsigned int)(k + 1) )
        {
          v16 = 56LL * (unsigned int)k;
          v47 = *v46 - *(_QWORD *)(v16 + v81 + 24);
          if ( *v46 == *(_QWORD *)(v16 + v81 + 24) )
            v47 = v46[1] - *(_QWORD *)(v16 + v81 + 32);
          if ( !v47 )
            goto LABEL_82;
        }
        v48 = *(_DWORD *)(v45 + 44);
        if ( (v48 & 0x10000000) != 0 && (v48 & 0x80000) != 0 )
        {
          SIPolicyStateRemovePolicy(v78, v46, v16, v81);
          v44 = SiPolicyIDEndpointSec;
          v66 = 1;
        }
        v49 = *((_QWORD *)g_SiPolicyHandles + v43);
        v50 = -(__int64)(*(_DWORD *)(v49 + 40) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
        k = *(_QWORD *)(v50 + v49 + 720) - v44;
        if ( !k )
          k = *(_QWORD *)(v50 + v49 + 728) - 0x48F222A00D2EB091LL;
        if ( !k && !(unsigned __int8)SIPolicyIsBasePolicy(v49) )
        {
          SIPolicyStateRemovePolicy(v78, v46, v16, v51);
          v44 = SiPolicyIDEndpointSec;
          v66 = 1;
        }
      }
LABEL_82:
      v43 = (unsigned int)(v43 + 1);
    }
    while ( (unsigned int)v43 < g_NumberOfSiPolicies );
    v5 = v77;
  }
  v6 = v66;
  if ( !v66 )
  {
    v52 = v84;
    if ( (g_CiPolicyState & 0x200) != 0 )
    {
      TestsigningPolicy = CipPrepareStateSigners(v84, &v72, &v82);
      if ( TestsigningPolicy < 0 )
        goto LABEL_50;
      TestsigningPolicy = CipPrepareStateSigners(v52, &v73, &v83);
      if ( TestsigningPolicy < 0 )
        goto LABEL_50;
      ExAcquirePushLockExclusiveEx(&g_CipRuntimeSignersLock, 0);
      CipUnregisterPreparedSigners(v72, v82);
      CipRegisterPreparedSigners(v73, v83);
      ExReleasePushLockExclusiveEx(&g_CipRuntimeSignersLock, 0);
    }
    SIPolicyForEachPolicy2(v52);
LABEL_50:
    LOBYTE(v3) = v70;
    LOBYTE(v4) = v71;
    goto LABEL_51;
  }
  LOBYTE(k) = 1;
  TestsigningPolicy = SIPolicyFinalizeInternal(&v78, k, &v85);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  TestsigningPolicy = CipPrepareStateSigners(v84, &v72, &v82);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  v53 = v85;
  TestsigningPolicy = CipPrepareStateSigners(v85, &v73, &v83);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  v77 = 0;
  TestsigningPolicy = SIPolicyStatePreparePolicyHash(v53, v54, v55, (unsigned int)&v77, (__int64)&v92);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  TestsigningPolicy = CipHvciRefreshPolicy(v79, v76, v81);
  if ( TestsigningPolicy < 0 )
    goto LABEL_50;
  ExAcquirePushLockExclusiveEx(&g_CipRuntimeSignersLock, 0);
  CipUnregisterPreparedSigners(v72, v82);
  CipRegisterPreparedSigners(v73, v83);
  ExReleasePushLockExclusiveEx(&g_CipRuntimeSignersLock, 0);
  SIPolicyForEachPolicy2(v53);
  SIPolicyCommitState(&v85);
  ExAcquirePushLockExclusiveEx(&g_CipPolicyHashLock, 0);
  g_CiPolicyGenerationCounter = v87;
  g_SiPolicyHash = v92;
  xmmword_1800499F0 = v93;
  if ( (unsigned int)Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline(v57, v56, v58) )
    LOBYTE(v4) = (g_CiPolicyState & 0x20000) != 0;
  else
    LOBYTE(v4) = v71;
  CipUpdateCiSettingsFromPolicies();
  if ( (unsigned int)Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline(v60, v59, v61) )
    LOBYTE(v3) = (g_CiPolicyState & 0x20000) != 0;
  else
    LOBYTE(v3) = v70;
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
  if ( (v79 & 0x1000000) == 0 || !(_BYTE)v64 )
    CipForceImageRevalidation(v63, m, v64);
  ExReleasePushLockExclusiveEx(&g_CipPolicyHashLock, 0);
LABEL_51:
  if ( TestsigningPolicy < 0 )
    v5 = TestsigningPolicy;
  CiLogSIPolicyRefreshFinished(v10, v5);
  if ( v6 || v69 )
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
  CipFreeRuntimeSigners(v72, v82);
  CipFreeRuntimeSigners(v73, v83);
  SIPolicyReleaseState(&v84);
  SIPolicyReleaseState(&v85);
  SIPolicyReleaseMutableState(&v78);
  SIPolicyUninitialize(v7);
  return v5;
}

```

## disassembly

```asm
0x180058048  mov     [rsp-8+arg_18], rbx
0x18005804d  push    rbp
0x18005804e  push    rsi
0x18005804f  push    rdi
0x180058050  push    r12
0x180058052  push    r13
0x180058054  push    r14
0x180058056  push    r15
0x180058058  lea     rbp, [rsp-40h]
0x18005805d  sub     rsp, 140h
0x180058064  mov     rax, cs:__security_cookie
0x18005806b  xor     rax, rsp
0x18005806e  mov     [rbp+70h+var_40], rax
0x180058072  xor     r13d, r13d
0x180058075  mov     [rbp+70h+var_B8], r8
0x180058079  xorps   xmm0, xmm0
0x18005807c  mov     [rbp+70h+var_DC], edx
0x18005807f  mov     r15b, r13b
0x180058082  mov     [rbp+70h+var_C8], ecx
0x180058085  mov     r14b, r13b
0x180058088  mov     [rsp+170h+var_F8], r15d
0x18005808d  mov     [rsp+170h+var_FC], r14d
0x180058092  mov     r12b, r13b
0x180058095  mov     [rbp+70h+var_90], r13
0x180058099  mov     esi, r13d
0x18005809c  mov     [rsp+170h+var_FE], r13b
0x1800580a1  mov     [rbp+70h+var_7C], r13d
0x1800580a5  mov     [rsp+170h+var_100], r13b
0x1800580aa  mov     [rbp+70h+var_C0], r13
0x1800580ae  mov     [rbp+70h+var_D0], r13
0x1800580b2  mov     [rbp+70h+var_98], r13
0x1800580b6  mov     [rbp+70h+var_F0], r13d
0x1800580ba  mov     [rbp+70h+var_A8], r13
0x1800580be  mov     [rsp+170h+var_F4], r13d
0x1800580c3  mov     [rbp+70h+var_B0], r13
0x1800580c7  movups  [rbp+70h+var_60], xmm0
0x1800580cb  mov     [rsp+170h+var_FD], r13b
0x1800580d0  movups  [rbp+70h+var_50], xmm0
0x1800580d4  call    cs:__imp_KeEnterCriticalRegion
0x1800580db  nop     dword ptr [rax+rax+00h]
0x1800580e0  xor     edx, edx
0x1800580e2  lea     rcx, g_CipPolicyLock
0x1800580e9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800580f0  nop     dword ptr [rax+rax+00h]
0x1800580f5  mov     rax, cs:g_CiPolicyGenerationCounter
0x1800580fc  mov     rdx, 3FFFFFFFFFFFFFFh
0x180058106  cmp     rax, rdx
0x180058109  lea     rcx, [rax+1]
0x18005810d  cmovnb  rcx, rax
0x180058111  mov     [rbp+70h+var_88], rcx
0x180058115  call    SIPolicyGetActiveState
0x18005811a  mov     ecx, cs:g_NumberOfSiPolicies
0x180058120  lea     r9d, [r13+1]; UserDataCount
0x180058124  mov     rbx, rax
0x180058127  mov     [rbp+70h+var_A0], rax
0x18005812b  lea     rax, [rbp+70h+var_E8]
0x18005812f  mov     [rbp+70h+var_E8], ecx
0x180058132  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x180058139  lea     rdx, CiPolicyRefreshStarted; EventDescriptor
0x180058140  mov     [rbp+70h+var_70.Ptr], rax
0x180058144  xor     r8d, r8d; ActivityId
0x180058147  lea     rax, [rbp+70h+var_70]
0x18005814b  mov     qword ptr [rbp+70h+var_70.Size], 4
0x180058153  mov     [rsp+170h+UserData], rax; UserData
0x180058158  call    cs:__imp_EtwWrite
0x18005815f  nop     dword ptr [rax+rax+00h]
0x180058164  call    CiSetNightsWatchPolicyStateRegKeys
0x180058169  mov     edi, eax
0x18005816b  test    eax, eax
0x18005816d  js      loc_18005846A
0x180058173  lea     rcx, [rsp+170h+var_FD]
0x180058178  call    CipLoadAndValidateRevocationList
0x18005817d  mov     [rbp+70h+var_D8], eax
0x180058180  mov     r13d, eax
0x180058183  test    eax, eax
0x180058185  jns     short loc_180058198
0x180058187  xor     r8d, r8d
0x18005818a  lea     rdx, CiDriverStlRefreshFailed
0x180058191  mov     ecx, eax
0x180058193  call    CiLogStatusEventWithCorrelationId
0x180058198  lea     rdx, [rbp+70h+var_D0]
0x18005819c  mov     rcx, rbx
0x18005819f  call    SIPolicyCloneState
0x1800581a4  mov     edi, eax
0x1800581a6  test    eax, eax
0x1800581a8  js      loc_18005846A
0x1800581ae  lea     rdx, [rsp+170h+var_FF]
0x1800581b3  lea     rcx, [rbp+70h+var_E0]
0x1800581b7  call    SIPolicyGetTestsigningPolicy
0x1800581bc  mov     edi, eax
0x1800581be  test    eax, eax
0x1800581c0  js      loc_18005846A
0x1800581c6  lea     rdx, [rbp+70h+var_E8]
0x1800581ca  mov     [rbp+70h+var_70.Ptr], rsi
0x1800581ce  lea     rcx, [rbp+70h+var_70]
0x1800581d2  mov     [rbp+70h+var_E8], esi
0x1800581d5  call    CipGetTenantIds
0x1800581da  mov     rbx, [rbp+70h+var_70.Ptr]
0x1800581de  test    eax, eax
0x1800581e0  js      short loc_1800581EE
0x1800581e2  mov     r9d, [rbp+70h+var_E8]
0x1800581e6  mov     r8, rbx
0x1800581e9  call    SIPolicyLoadAuthorizationTokens
0x1800581ee  test    rbx, rbx
0x1800581f1  jz      short loc_180058207
0x1800581f3  mov     edx, 63734943h; Tag
0x1800581f8  mov     rcx, rbx; P
0x1800581fb  call    cs:__imp_ExFreePoolWithTag
0x180058202  nop     dword ptr [rax+rax+00h]
0x180058207  mov     r12, [rbp+70h+var_D0]
0x18005820b  xor     r15d, r15d
0x18005820e  cmp     r15d, [rbp+70h+var_DC]
0x180058212  jnb     loc_18005856E
0x180058218  mov     r14, [rbp+70h+var_B8]
0x18005821c  mov     eax, r15d
0x18005821f  add     r14, 18h
0x180058223  imul    rbx, rax, 38h ; '8'
0x180058227  add     r14, rbx
0x18005822a  mov     rcx, r14
0x18005822d  call    CiLogSIPolicyRefreshAttempt
0x180058232  lea     rax, [rbp+70h+var_90]
0x180058236  mov     r8, r14
0x180058239  mov     [rsp+170h+UserData], rax
0x18005823e  lea     r9, [rsp+170h+var_FE]
0x180058243  mov     rax, [rbp+70h+var_A0]
0x180058247  mov     rcx, [rax]
0x18005824a  call    SIPolicyIsSignedPolicyRequired
0x18005824f  mov     edi, eax
0x180058251  test    eax, eax
0x180058253  js      loc_18005845B
0x180058259  mov     rcx, [rbp+70h+var_B8]
0x18005825d  mov     r8b, [rsp+170h+var_FE]
0x180058262  mov     [rsp+170h+var_FF], 0
0x180058267  mov     eax, [rbx+rcx+30h]
0x18005826b  mov     r9b, [rbx+rcx+10h]
0x180058270  mov     [rbp+70h+var_80], eax
0x180058273  mov     rax, [rbx+rcx+28h]
0x180058278  mov     rcx, r12
0x18005827b  mov     [rbp+70h+var_78], rax
0x18005827f  lea     rax, [rbp+70h+var_C0]
0x180058283  mov     [rsp+170h+var_110], rax
0x180058288  lea     rax, [rsp+170h+var_FF]
0x18005828d  mov     [rsp+170h+var_128], rax
0x180058292  lea     rax, [rbp+70h+var_80]
0x180058296  mov     [rsp+170h+var_130], rax
0x18005829b  mov     rax, [rbp+70h+var_90]
0x18005829f  mov     [rsp+170h+var_140], r14
0x1800582a4  mov     [rsp+170h+var_148], rax
0x1800582a9  mov     byte ptr [rsp+170h+UserData], 1
0x1800582ae  call    SIPolicyParsePolicyData
0x1800582b3  mov     rsi, [rbp+70h+var_C0]
0x1800582b7  mov     edi, eax
0x1800582b9  test    eax, eax
0x1800582bb  js      loc_180058447
0x1800582c1  test    rsi, rsi
0x1800582c4  jnz     short loc_1800582D1
0x1800582c6  cmp     [rsp+170h+var_FF], sil
0x1800582cb  jz      loc_180058447
0x1800582d1  mov     rax, [rbp+70h+var_B8]
0x1800582d5  cmp     byte ptr [rbx+rax+13h], 0
0x1800582da  jz      short loc_180058337
0x1800582dc  cmp     dword ptr [rsi+28h], 6
0x1800582e0  sbb     rax, rax
0x1800582e3  and     rax, 0FFFFFFFFFFFFFD40h
0x1800582e9  mov     rcx, [rax+rsi+2D0h]
0x1800582f1  sub     rcx, cs:SiPolicyIDEndpointSec
0x1800582f8  jnz     short loc_180058309
0x1800582fa  mov     rcx, [rax+rsi+2D8h]
0x180058302  sub     rcx, cs:qword_180032A38
0x180058309  test    rcx, rcx
0x18005830c  jnz     short loc_18005831A
0x18005830e  mov     rcx, rsi
0x180058311  call    SIPolicyIsBasePolicy
0x180058316  test    al, al
0x180058318  jz      short loc_180058337
0x18005831a  mov     edx, edi
0x18005831c  mov     rcx, r14
0x18005831f  call    CiLogSIPolicyRefreshIgnored
0x180058324  mov     rcx, rsi
0x180058327  call    SIPolicyUninitialize
0x18005832c  xor     esi, esi
0x18005832e  mov     [rbp+70h+var_C0], rsi
0x180058332  jmp     loc_180058453
0x180058337  test    rsi, rsi
0x18005833a  jz      short loc_180058347
0x18005833c  mov     rdx, rsi
0x18005833f  mov     rcx, r12
0x180058342  call    SIPolicyEnforceSupplementalPolicyOptions
0x180058347  xor     edx, edx
0x180058349  cmp     edx, cs:g_NumberOfSiPolicies
0x18005834f  jnb     loc_1800583D5
0x180058355  mov     rax, cs:g_SiPolicyHandles
0x18005835c  mov     r9, [rax+rdx*8]
0x180058360  cmp     dword ptr [r9+28h], 6
0x180058365  sbb     rax, rax
0x180058368  and     rax, 0FFFFFFFFFFFFFD50h
0x18005836e  lea     r8, [rax+2C0h]
0x180058375  add     r8, r9
0x180058378  mov     rcx, [r8]
0x18005837b  sub     rcx, [r14]
0x18005837e  jnz     short loc_180058388
0x180058380  mov     rcx, [r8+8]
0x180058384  sub     rcx, [r14+8]
0x180058388  test    rcx, rcx
0x18005838b  jz      short loc_180058391
0x18005838d  inc     edx
0x18005838f  jmp     short loc_180058349
0x180058391  test    dword ptr [r9+2Ch], 10000000h
0x180058399  jnz     short loc_1800583A7
0x18005839b  lea     r8, CiPolicyRefreshNotAllowed
0x1800583a2  mov     rcx, r9
0x1800583a5  jmp     short loc_180058426
0x1800583a7  test    rsi, rsi
0x1800583aa  jnz     short loc_1800583BC
0x1800583ac  mov     rdx, r8
0x1800583af  mov     rcx, r12
0x1800583b2  call    SIPolicyStateRemovePolicy
0x1800583b7  jmp     loc_18005843D
0x1800583bc  mov     rdx, r9
0x1800583bf  mov     rcx, rsi
0x1800583c2  call    SIPolicyCompare
0x1800583c7  test    al, al
0x1800583c9  jz      short loc_180058430
0x1800583cb  mov     rcx, rsi
0x1800583ce  call    SIPolicyUninitialize
0x1800583d3  xor     esi, esi
0x1800583d5  test    rsi, rsi
0x1800583d8  jz      loc_180058324
0x1800583de  mov     rcx, rsi
0x1800583e1  call    SIPolicyIsBasePolicy
0x1800583e6  test    al, al
0x1800583e8  jnz     short loc_180058413
0x1800583ea  cmp     dword ptr [rsi+28h], 6
0x1800583ee  mov     rcx, r12
0x1800583f1  sbb     rdx, rdx
0x1800583f4  and     rdx, 0FFFFFFFFFFFFFD40h
0x1800583fb  add     rdx, 2D0h
0x180058402  add     rdx, rsi
0x180058405  call    SIPolicyStateFindPolicy
0x18005840a  test    rax, rax
0x18005840d  jz      loc_180058324
0x180058413  test    dword ptr [rsi+2Ch], 10000000h
0x18005841a  jnz     short loc_180058430
0x18005841c  lea     r8, CiPolicyRefreshNonRebootless
0x180058423  mov     rcx, rsi
0x180058426  call    CiLogSIPolicyRefresh
0x18005842b  jmp     loc_180058324
0x180058430  mov     rdx, rsi
0x180058433  mov     rcx, r12
0x180058436  call    SIPolicyStateAddPolicy
0x18005843b  xor     esi, esi
0x18005843d  mov     [rsp+170h+var_100], 1
0x180058442  jmp     loc_180058324
0x180058447  mov     edx, edi
0x180058449  mov     rcx, r14
0x18005844c  call    CiLogSIPolicyRefreshIgnored
0x180058451  xor     edi, edi
0x180058453  inc     r15d
0x180058456  jmp     loc_18005820E
0x18005845b  mov     r12b, [rsp+170h+var_100]
0x180058460  mov     r14d, [rsp+170h+var_FC]
0x180058465  mov     r15d, [rsp+170h+var_F8]
0x18005846a  test    edi, edi
0x18005846c  cmovs   r13d, edi
0x180058470  mov     edx, r13d
0x180058473  call    CiLogSIPolicyRefreshFinished
0x180058478  test    r12b, r12b
0x18005847b  jnz     short loc_180058484
0x18005847d  cmp     [rsp+170h+var_FD], r12b
0x180058482  jz      short loc_18005848B
0x180058484  mov     cl, 1
0x180058486  call    CiInstrumentInitialize
0x18005848b  call    Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline
0x180058490  test    eax, eax
0x180058492  jz      short loc_1800584AE
0x180058494  cmp     r15b, r14b
0x180058497  jz      short loc_1800584AE
0x180058499  xor     edx, edx
0x18005849b  lea     rcx, g_CipPolicyRefreshDefenderSequencingLock
0x1800584a2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800584a9  nop     dword ptr [rax+rax+00h]
0x1800584ae  xor     edx, edx
0x1800584b0  lea     rcx, g_CipPolicyLock
0x1800584b7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800584be  nop     dword ptr [rax+rax+00h]
0x1800584c3  call    Feature_Servicing_CIRefreshBlocks8s__private_IsEnabledDeviceUsageNoInline
0x1800584c8  test    eax, eax
0x1800584ca  jz      short loc_1800584FB
0x1800584cc  cmp     r15b, r14b
0x1800584cf  jz      short loc_1800584FB
0x1800584d1  mov     rax, cs:g_EtwEventHandle
0x1800584d8  test    rax, rax
0x1800584db  jz      short loc_1800584E6
0x1800584dd  movzx   ecx, r14b
0x1800584e1  call    CiCatDbMpSmartLockerEnable
0x1800584e6  xor     edx, edx
0x1800584e8  lea     rcx, g_CipPolicyRefreshDefenderSequencingLock
0x1800584ef  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800584f6  nop     dword ptr [rax+rax+00h]
0x1800584fb  call    cs:__imp_KeLeaveCriticalRegion
  ... truncated ...
```
