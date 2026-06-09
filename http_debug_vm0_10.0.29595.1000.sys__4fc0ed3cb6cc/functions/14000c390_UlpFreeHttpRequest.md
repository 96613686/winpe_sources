# UlpFreeHttpRequest

- ea: `0x14000c390`
- end: `0x14000dccf`
- name: `UlpFreeHttpRequest`
- size: `6463`
- prototype: ``
- caller_count: `6`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000a520`
- `0x14000bfb0`
- `0x140033830`
- `0x1400384e0`
- `0x14005e0d0`
- `0x14006ce20`

## callees

- `0x14000a350`
- `0x14000c390`
- `0x14000dce0`
- `0x14000e420`
- `0x140022610`
- `0x140035a50`
- `0x140049d08`
- `0x14005dfd0`
- `0x14005e030`
- `0x140062bd0`
- `0x14006e4ec`
- `0x14009620c`
- `0x1400984a0`
- `0x1400a031c`
- `0x1400c91f0`
- `0x1400d91d0`
- `0x14013dd68`
- `0x140140ea8`
- `0x1401458f0`
- `0x140145a80`
- `0x140148034`
- `0x140148cf4`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9c5c`
- `0x1401d9e44`
- `0x1401d9f54`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000d0df`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d2b2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d7ae`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d0df`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d2b2`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d7ae`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000d20a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000d3d9`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000d20a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000d3d9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000c54a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000c7cb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cc43`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cce3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ce1e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000c54a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000c7cb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cc43`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cce3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ce1e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000d165`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000d338`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000d165`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000d338`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000d1bc`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000d38f`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000d1bc`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000d38f`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14000da6d`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14000dc47`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14000da6d`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14000dc47`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000d106`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000d2d9`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000d106`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000d2d9`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000d143`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000d316`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000d143`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000d316`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000d284`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000d284`
- `ntoskrnl!KeSetEvent` at `0x14000d228`
- `ntoskrnl!KeSetEvent` at `0x14000d3f7`
- `ntoskrnl!KeSetEvent` at `0x14000d228`
- `ntoskrnl!KeSetEvent` at `0x14000d3f7`
- `ntoskrnl!ZwClose` at `0x14000daf7`
- `ntoskrnl!ZwClose` at `0x14000daf7`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000d18f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000d362`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000d18f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000d362`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000d06b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000d092`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000d06b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000d092`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000d267`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000d267`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000ca4e`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000ca4e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c67d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c9fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ca22`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cb6c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cb91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c67d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c9fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ca22`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cb6c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cb91`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c586`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cdd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce77`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d4ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d738`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d922`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d93c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d94f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d971`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da22`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dadf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170a59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170a81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170ada`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c586`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cdd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce77`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d4ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d738`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d922`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d93c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d94f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d971`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da22`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dadf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170a59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170a81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170ada`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170b08`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c671`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c9ee`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ca16`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cb60`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cb85`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c671`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c9ee`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000ca16`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cb60`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cb85`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000cecf`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000cf24`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000cecf`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000cf24`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c5d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c97e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c9a8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cad9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000caf6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c5d7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c97e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c9a8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cad9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000caf6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c5c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c969`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c996`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cac0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cae5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c5c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c969`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c996`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cac0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cae5`
- `ksecdd!FreeContextBuffer` at `0x14000db0f`
- `ksecdd!FreeContextBuffer` at `0x14000db0f`

## pseudocode

```c
void __fastcall UlpFreeHttpRequest(__int64 a1)
{
  __int64 v2; // rdi
  unsigned __int16 *v3; // rbx
  __int64 v4; // rdi
  void *v5; // rcx
  void *v6; // rcx
  unsigned int v7; // edi
  void *v8; // rcx
  _QWORD **v9; // rdi
  _QWORD *v10; // rcx
  __int64 v11; // rax
  _QWORD *v12; // rdx
  void *v13; // rdi
  unsigned __int64 v14; // rsi
  void *v15; // rdi
  volatile signed __int32 ***v16; // r8
  volatile signed __int32 **v17; // rdx
  volatile signed __int32 *v18; // rax
  volatile signed __int32 *v19; // rax
  unsigned int k; // r15d
  __int64 v21; // rdi
  volatile signed __int32 *v22; // rdx
  int v23; // eax
  __int64 v24; // rsi
  _DWORD *v25; // rdi
  int v26; // eax
  char *v27; // rax
  __int64 (__fastcall **v28)(); // rcx
  __int64 *v29; // r8
  bool v30; // zf
  __int64 v31; // r8
  unsigned __int64 v32; // rsi
  void *v33; // rcx
  void *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdi
  int v37; // eax
  volatile signed __int32 *v38; // rdx
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  __int64 v43; // rdx
  void *v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  char *v47; // rsi
  _QWORD *v48; // rax
  __int64 v49; // rdx
  _QWORD *v50; // r8
  volatile signed __int32 *v51; // rdx
  int v52; // eax
  __int64 v53; // rdi
  __int64 v54; // rdx
  _QWORD *v55; // rax
  _QWORD *v56; // rcx
  _QWORD *v57; // rax
  __int64 v58; // r8
  _QWORD *v59; // rdx
  volatile signed __int32 *v60; // rdx
  volatile signed __int32 *v61; // rdx
  int v62; // eax
  __int64 v63; // rdi
  int v64; // r14d
  unsigned __int64 v65; // rdi
  unsigned __int16 *v66; // rcx
  unsigned __int16 *v67; // rcx
  void *v68; // rcx
  unsigned __int64 v69; // rdi
  __int64 *v70; // rcx
  volatile signed __int32 *v71; // rdx
  int v72; // eax
  unsigned __int64 v73; // rsi
  int v74; // eax
  int v75; // eax
  ULONG_PTR v76; // rsi
  struct _KPROCESS *CurrentProcess; // rax
  void *CurrentServerSilo; // rdi
  __int64 v79; // rcx
  ULONG_PTR v80; // r14
  struct _KPROCESS *v81; // rax
  void *v82; // rdi
  __int64 v83; // rcx
  __int64 v84; // rdi
  USHORT v85; // ax
  __int64 v86; // rdi
  USHORT CurrentNodeNumber; // ax
  char v88; // r15
  __int64 v89; // rax
  __int64 v90; // r12
  ULONG v91; // r15d
  ULONG_PTR v92; // rdx
  int v93; // eax
  __int64 v94; // rdi
  char v95; // r15
  __int64 v96; // rax
  __int64 v97; // r12
  ULONG v98; // r15d
  ULONG_PTR v99; // rdx
  int v100; // r13d
  __int64 v101; // rdi
  __int64 v102; // rax
  _BYTE *v103; // rsi
  __int64 v104; // rax
  __int64 v105; // rsi
  int v106; // eax
  __int64 v107; // rdi
  __int64 v108; // r9
  int v109; // eax
  int v110; // eax
  ULONG_PTR v111; // rdx
  int v112; // eax
  unsigned int v113; // r14d
  unsigned int v114; // esi
  unsigned int i; // esi
  unsigned int j; // esi
  volatile signed __int32 *v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // rcx
  _BYTE **v120; // r14
  volatile signed __int32 *v121; // [rsp+30h] [rbp-59h] BYREF
  volatile signed __int32 ***v122; // [rsp+38h] [rbp-51h]
  __int128 v123; // [rsp+40h] [rbp-49h] BYREF
  _OWORD v124[6]; // [rsp+50h] [rbp-39h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 46, WPP_682cf469470432b235cb9a4961616e40_Traceguids, a1);
  v2 = *(_QWORD *)(a1 + 1320);
  v3 = (unsigned __int16 *)(a1 - 1248);
  if ( v2 )
  {
    v113 = 30;
    v114 = 0;
    if ( (*((_DWORD *)v3 + 636) & 8) == 0 )
      v113 = 41;
    do
    {
      if ( (*(_BYTE *)v2 & 2) != 0 )
        ExFreePoolWithTag(*(PVOID *)(v2 + 8), 0);
      v2 += 16;
      ++v114;
    }
    while ( v114 < v113 );
  }
  v4 = *((_QWORD *)v3 + 320);
  if ( v4 )
  {
    for ( i = 0; i < v3[1274]; ++i )
    {
      if ( (*(_BYTE *)(v4 + 2) & 2) != 0 )
        ExFreePoolWithTag(*(PVOID *)(v4 + 8), 0);
      v4 += 24;
    }
  }
  if ( (*((_DWORD *)v3 + 636) & 8) == 0 )
  {
    v5 = (void *)*((_QWORD *)v3 + 321);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
  }
  if ( (*((_DWORD *)v3 + 636) & 0x10) != 0 )
    ExFreePoolWithTag(*((PVOID *)v3 + 322), 0);
  *((_OWORD *)v3 + 159) = 0;
  *((_OWORD *)v3 + 160) = 0;
  *((_OWORD *)v3 + 161) = 0;
  v6 = (void *)*((_QWORD *)v3 + 391);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    *((_QWORD *)v3 + 391) = 0;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    if ( v3 )
      v102 = *((_QWORD *)v3 + 8);
    else
      v102 = 0;
    WPP_SF_qqD(1032, 42, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v3, v102, 0);
  }
  v7 = 0;
  if ( (*((_DWORD *)v3 + 550) & 0x10) != 0 )
  {
    for ( j = 0; j < 0x29; ++j )
    {
      v118 = *((unsigned __int8 *)v3 + j + 544);
      if ( (_BYTE)v118 == 41 )
        break;
      v119 = 2 * v118;
      v7 += v3[4 * v119 + 300] + 1;
      if ( (v3[4 * v119 + 301] & 1) != 0 )
        ExFreePoolWithTag(*(PVOID *)&v3[8 * *((unsigned __int8 *)v3 + j + 544) + 296], 0);
    }
    v120 = (_BYTE **)(v3 + 260);
    while ( 1 )
    {
      v103 = *v120;
      if ( *v120 == (_BYTE *)v120 )
        break;
      if ( *((_BYTE ***)v103 + 1) != v120 )
        goto LABEL_141;
      v104 = *(_QWORD *)v103;
      if ( *(_BYTE **)(*(_QWORD *)v103 + 8LL) != v103 )
        goto LABEL_141;
      *v120 = (_BYTE *)v104;
      *(_QWORD *)(v104 + 8) = v120;
      v7 += *((unsigned __int16 *)v103 + 10) + *((unsigned __int16 *)v103 + 20) + 2;
      if ( (v103[42] & 1) != 0 )
        ExFreePoolWithTag(*((PVOID *)v103 + 4), 0);
      if ( (v103[42] & 2) != 0 )
        ExFreePoolWithTag(v103, 0);
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 43, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v7);
  v8 = (void *)*((_QWORD *)v3 + 345);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0);
    *((_QWORD *)v3 + 345) = 0;
  }
  v9 = (_QWORD **)(v3 + 1232);
  if ( *v9 != v9 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
      WPP_SF_q(1038, 194, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, v3 + 1232);
    while ( 1 )
    {
      v10 = *v9;
      if ( *v9 == v9 )
        break;
      v11 = *v10;
      if ( *(_QWORD **)(*v10 + 8LL) != v10 )
        goto LABEL_141;
      v12 = (_QWORD *)v10[1];
      if ( (_QWORD *)*v12 != v10 )
        goto LABEL_141;
      *v12 = v11;
      *(_QWORD *)(v11 + 8) = v12;
      ExFreePoolWithTag(v10 - 2, 0);
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
      WPP_SF_(1038, 195, WPP_3bc569ebedc33674d1577199996181a5_Traceguids);
  }
  v13 = (void *)*((_QWORD *)v3 + 236);
  if ( v13 )
  {
    if ( *((_BYTE *)v3 + 1896) )
    {
      if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A0490, *((_QWORD *)v3 + 236));
      }
      else
      {
        v14 = qword_1401A0490 + ((unsigned __int64)(unsigned int)(*((_DWORD *)v3 + 475) + 1) << 7);
        if ( !*(_BYTE *)(v14 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0490, v14 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 64), v13);
      }
    }
    else
    {
      ExFreePoolWithTag(*((PVOID *)v3 + 236), 0);
    }
  }
  *(_OWORD *)(v3 + 940) = 0;
  *((_QWORD *)v3 + 237) = 0;
  v15 = (void *)*((_QWORD *)v3 + 239);
  if ( v15 )
  {
    if ( *((_BYTE *)v3 + 1920) )
    {
      if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A0490, *((_QWORD *)v3 + 239));
      }
      else
      {
        v73 = qword_1401A0490 + ((unsigned __int64)(unsigned int)(*((_DWORD *)v3 + 481) + 1) << 7);
        if ( !*(_BYTE *)(v73 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0490, v73 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v73 + 64), v15);
      }
    }
    else
    {
      ExFreePoolWithTag(*((PVOID *)v3 + 239), 0);
    }
  }
  *((_OWORD *)v3 + 119) = 0;
  *((_QWORD *)v3 + 240) = 0;
  v121 = (volatile signed __int32 *)&v121;
  v122 = (volatile signed __int32 ***)&v121;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qqP(1032, 44, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v3, *((_QWORD *)v3 + 8), 0);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v3 + 1404, 0);
  if ( *((volatile signed __int32 ***)v121 + 1) != &v121 )
    goto LABEL_141;
  v16 = v122;
  if ( *v122 != &v121 )
    goto LABEL_141;
  v17 = (volatile signed __int32 **)(v3 + 1396);
  if ( *(unsigned __int16 **)(*((_QWORD *)v3 + 349) + 8LL) != v3 + 1396 )
    goto LABEL_141;
  if ( **((volatile signed __int32 ****)v3 + 350) != v17 )
    goto LABEL_141;
  *v122 = v17;
  v122 = (volatile signed __int32 ***)*((_QWORD *)v3 + 350);
  *v122 = &v121;
  v18 = *v17;
  *((_QWORD *)v3 + 350) = v16;
  if ( *((volatile signed __int32 ***)v18 + 1) != v17 || *v16 != v17 )
    goto LABEL_141;
  *v16 = (volatile signed __int32 **)v18;
  *((_QWORD *)v18 + 1) = v16;
  *((_QWORD *)v3 + 350) = v3 + 1396;
  *v17 = (volatile signed __int32 *)v17;
  *((_BYTE *)v3 + 2816) = 1;
  ExReleasePushLockExclusiveEx(v3 + 1404, 0);
  KeLeaveCriticalRegion();
  while ( 1 )
  {
    v19 = v121;
    if ( v121 == (volatile signed __int32 *)&v121 )
      break;
    if ( *((volatile signed __int32 ***)v121 + 1) != &v121 )
      goto LABEL_141;
    v70 = *(__int64 **)v121;
    if ( *(volatile signed __int32 **)(*(_QWORD *)v121 + 8LL) != v121 )
      goto LABEL_141;
    v121 = *(volatile signed __int32 **)v121;
    v70[1] = (__int64)&v121;
    v71 = v19 - 6;
    *(_QWORD *)v19 = 0;
    *((_QWORD *)v19 + 1) = 0;
    v72 = _InterlockedDecrement(v19 - 6);
    if ( UxDebugCheckRefcount && v72 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v71, 0x28u, v72);
    if ( !v72 )
      UxDuoFreeDeclarePushParameters((PVOID)v71);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 45, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
  for ( k = 0; k < v3[801]; ++k )
  {
    v21 = 8LL * k;
    v22 = (volatile signed __int32 *)(*(_QWORD *)(v21 + *((_QWORD *)v3 + 201)) + 32LL);
    v23 = _InterlockedDecrement(v22);
    if ( UxDebugCheckRefcount && v23 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v22, 0xAu, v23);
    if ( !v23 )
    {
      v24 = *((_QWORD *)v3 + 3);
      v25 = *(_DWORD **)(v21 + *((_QWORD *)v3 + 201));
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_q(1032, 53, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v25);
      if ( *((_QWORD *)v25 + 19) )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(v24 + 504) + 128LL))(*(_QWORD *)(v24 + 496));
        *((_QWORD *)v25 + 19) = 0;
      }
      v26 = v25[35];
      if ( v26 == 4 )
      {
        v25[4] = 1886538869;
        ExFreePoolWithTag(v25, 0);
      }
      else
      {
        if ( v26 )
        {
          if ( v26 == 1 )
          {
            v27 = aUlrp_0;
            v28 = &off_1401A0128;
            v29 = &qword_1401A0100;
          }
          else if ( v26 == 2 )
          {
            v27 = aUlrp_1;
            v28 = &off_1401A00F8;
            v29 = &qword_1401A00D0;
          }
          else
          {
            v27 = aUlrp_2;
            v28 = &funcs_140069427;
            v29 = &UlLookaside;
          }
        }
        else
        {
          v27 = aUlrp;
          v28 = &off_1401A0158;
          v29 = &qword_1401A0130;
        }
        v30 = UxDebugDisableLookaside == 0;
        v124[0] = 0;
        v25[4] = 1347570805;
        memset(&v124[1], 0, 80);
        if ( v30 )
        {
          v31 = *v29;
          if ( UxCompactMode )
          {
            PnlFreeToLookasideList(v31, v25);
          }
          else
          {
            v32 = v31 + ((unsigned __int64)(unsigned int)(*v25 + 1) << 7);
            if ( !*(_BYTE *)(v32 + 176) )
              PplpLazyInitializeLookasideList(v31, v32 + 64);
            ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v32 + 64), v25);
          }
        }
        else
        {
          DWORD2(v124[2]) = *(_DWORD *)v27;
          ((void (__fastcall *)(_DWORD *, _OWORD *, __int64 *))*v28)(v25, v124, v29);
        }
      }
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_(1032, 54, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
    }
  }
  if ( v3[800] > 1u )
    ExFreePoolWithTag(*((PVOID *)v3 + 201), 0);
  v33 = (void *)*((_QWORD *)v3 + 254);
  if ( v33 && v33 != *((void **)v3 + 67) )
    ExFreePoolWithTag(v33, 0);
  v34 = (void *)*((_QWORD *)v3 + 260);
  if ( v34 )
    ExFreePoolWithTag(v34, 0);
  v35 = *((_QWORD *)v3 + 310);
  if ( v35 )
  {
    v105 = *(_QWORD *)(*((_QWORD *)v3 + 3) + 1088LL);
    v106 = _InterlockedDecrement((volatile signed __int32 *)(v35 + 24));
    if ( UxDebugCheckRefcount && v106 <= -1 )
      UlBugCheckEx(3u, v35 + 24, 1u, v106);
    if ( !v106 )
    {
      v107 = v35 + 32;
      v123 = 0;
      if ( *(_QWORD *)(v35 + 32) || *(_QWORD *)(v35 + 48) || *(_QWORD *)(v35 + 64) )
        UlBugCheckEx(1u, v35 + 32, (ULONG_PTR)"minio\\http\\sys\\flowrate.h", 0x76u);
      if ( KeGetCurrentIrql() )
      {
        LOBYTE(v108) = 1;
        UlThreadPoolEnqueueWorkItem(0, v107, UlpFlCleanupFlowRateInfoWorker, v108, v105, -1);
        *((_QWORD *)v3 + 310) = 0;
        goto LABEL_74;
      }
      UxPodAttachThread(v105, &v123);
      UlpFlCleanupFlowRateInfoWorker(v107);
      UxPodDetachThread(&v123);
    }
    *((_QWORD *)v3 + 310) = 0;
  }
LABEL_74:
  v36 = *((_QWORD *)v3 + 3);
  v37 = _InterlockedDecrement((volatile signed __int32 *)(v36 + 40));
  if ( UxDebugCheckRefcount && v37 <= -1 )
    UlBugCheckEx(3u, v36 + 40, 0x11u, v37);
  if ( !v37 )
  {
    v76 = v36 + 64;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(void **)(v36 + 1088);
    v79 = *(_QWORD *)v76;
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v79 || *(_QWORD *)(v76 + 16) || *(_QWORD *)(v76 + 32) )
        UlBugCheckEx(1u, v76, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      UlThreadPoolEnqueueWorkItem(0, v76, UlFreeHttpConnection, 1, CurrentServerSilo, -1);
      goto LABEL_76;
    }
    if ( v79 || *(_QWORD *)(v76 + 16) || *(_QWORD *)(v76 + 32) )
      UlBugCheckEx(1u, v76, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v91 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v91 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v91 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v76 + 32) = CurrentServerSilo;
      *(_QWORD *)&v123 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v123);
      v92 = v123 + 24;
      v93 = _InterlockedIncrement((volatile signed __int32 *)(v123 + 24));
      if ( UxDebugCheckRefcount && v93 <= -1 )
        UlBugCheckEx(3u, v92, 0xDu, v93);
      *(_BYTE *)(v76 + 24) = 1;
      v94 = *(_QWORD *)(qword_1401A3F50 + 8LL * v91);
      *(_QWORD *)(v76 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v94 + 16), (PSLIST_ENTRY)v76) )
      {
        KeSetEvent((PRKEVENT)(v94 + 32), 0, 0);
        if ( *(_BYTE *)(*(_QWORD *)v94 + 33LL) )
        {
          if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v94 + 68), 1, 0) )
          {
            if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
              WPP_SF_Dd(
                1304,
                18,
                WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
                *(unsigned int *)(v94 + 8),
                **(_DWORD **)v94);
            _InterlockedIncrement((volatile signed __int32 *)(v94 + 64));
            ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
            IoQueueWorkItemEx(*(PIO_WORKITEM *)(v94 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v94);
          }
        }
      }
      goto LABEL_76;
    }
    v88 = 0;
    v123 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v90 = *((_QWORD *)&v123 + 1);
    }
    else
    {
      v89 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v90 = v89;
      v88 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v89, CurrentServerSilo);
        UlFreeHttpConnection(v76);
LABEL_201:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v90);
        PsDetachSiloFromCurrentThread(v90);
        goto LABEL_76;
      }
    }
    UlFreeHttpConnection(v76);
    if ( !v88 )
      goto LABEL_76;
    goto LABEL_201;
  }
LABEL_76:
  v30 = *((_BYTE *)v3 + 1312) == 0;
  *((_QWORD *)v3 + 3) = 0;
  if ( !v30 )
    UlCleanupConfigGroupInfo(v3 + 648, 1);
  if ( (*((_DWORD *)v3 + 600) & 1) != 0 )
  {
    v117 = (volatile signed __int32 *)*((_QWORD *)v3 + 302);
    if ( v117 )
    {
      v109 = _InterlockedDecrement(v117);
      if ( UxDebugCheckRefcount && v109 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v117, 0xAu, v109);
      if ( !v109 )
        UlFreeServiceNameContainer(*((PVOID *)v3 + 302));
    }
    *((_DWORD *)v3 + 600) &= ~1u;
  }
  v38 = (volatile signed __int32 *)*((_QWORD *)v3 + 303);
  if ( v38 )
  {
    v110 = _InterlockedDecrement(v38);
    if ( UxDebugCheckRefcount && v110 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v38, 0x26u, v110);
    if ( !v110 )
      UlFreeChannelBindToken(*((PVOID *)v3 + 303));
    *((_QWORD *)v3 + 303) = 0;
  }
  v39 = (void *)*((_QWORD *)v3 + 304);
  if ( v39 )
  {
    ExFreePoolWithTag(v39, 0);
    *((_QWORD *)v3 + 304) = 0;
  }
  v40 = (void *)*((_QWORD *)v3 + 286);
  if ( v40 )
  {
    ZwClose(v40);
    *((_QWORD *)v3 + 286) = 0;
  }
  *((_DWORD *)v3 + 566) |= 4u;
  v41 = (void *)*((_QWORD *)v3 + 291);
  if ( v41 )
  {
    FreeContextBuffer(v41);
    *((_QWORD *)v3 + 291) = 0;
    *((_DWORD *)v3 + 580) = 0;
  }
  v42 = (void *)*((_QWORD *)v3 + 292);
  if ( v42 )
  {
    ExFreePoolWithTag(v42, 0);
    *((_QWORD *)v3 + 292) = 0;
    v3[1172] = 0;
  }
  if ( (*((_DWORD *)v3 + 566) & 4) != 0 )
  {
    v43 = *((_QWORD *)v3 + 294);
    if ( v43 )
    {
      UlpFreeAuthToken(*((_QWORD *)v3 + 284), v43, *((unsigned int *)v3 + 591));
      *((_QWORD *)v3 + 294) = 0;
      *((_QWORD *)v3 + 295) = 0;
    }
  }
  v44 = (void *)*((_QWORD *)v3 + 288);
  if ( v44 )
  {
    UlpDeleteAuthCacheKey(v44);
    *((_QWORD *)v3 + 288) = 0;
  }
  *((_DWORD *)v3 + 566) |= 2u;
  v45 = *((_QWORD *)v3 + 289);
  if ( v45 )
  {
    v111 = v45 + 20;
    v112 = _InterlockedDecrement((volatile signed __int32 *)(v45 + 20));
    if ( UxDebugCheckRefcount && v112 <= -1 )
      UlBugCheckEx(3u, v111, 0xAu, v112);
    if ( !v112 )
      UlpFreeAuthCacheEntry(*((_QWORD *)v3 + 289));
    *((_QWORD *)v3 + 289) = 0;
  }
  v46 = *((_QWORD *)v3 + 284);
  if ( v46 && *(_BYTE *)(v46 + 109) )
    UlDereferenceAlternateCredential((PVOID)(v46 - 16), 0x20u);
  *((_QWORD *)v3 + 284) = 0;
  v47 = 0;
  *((_DWORD *)v3 + 566) &= ~1u;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 237, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v3, *((_QWORD *)v3 + 8));
  if ( *((_BYTE *)v3 + 1852) )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v3 + 852, 0);
    v47 = (char *)*((_QWORD *)v3 + 214);
    if ( v47 )
    {
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v47 + 72, 0);
      v48 = v3 + 908;
      v49 = *((_QWORD *)v3 + 227);
      if ( v49 )
      {
        if ( *(_QWORD **)(v49 + 8) != v48 )
          goto LABEL_141;
        v50 = (_QWORD *)*((_QWORD *)v3 + 228);
        if ( (_QWORD *)*v50 != v48 )
          goto LABEL_141;
        *v50 = v49;
        *(_QWORD *)(v49 + 8) = v50;
        *v48 = 0;
        *((_QWORD *)v3 + 228) = 0;
      }
      ExReleasePushLockExclusiveEx(v47 + 72, 0);
      KeLeaveCriticalRegion();
      *((_QWORD *)v3 + 214) = 0;
    }
    ExReleasePushLockExclusiveEx(v3 + 852, 0);
    KeLeaveCriticalRegion();
  }
  if ( *((_BYTE *)v3 + 1850) )
  {
    PsReturnPoolQuota(*(PEPROCESS *)(*((_QWORD *)v3 + 218) + 72LL), (POOL_TYPE)512, *((unsigned int *)v3 + 411));
    *((_BYTE *)v3 + 1850) = 0;
  }
  v51 = (volatile signed __int32 *)*((_QWORD *)v3 + 218);
  if ( v51 )
  {
    v74 = _InterlockedDecrement(v51);
    if ( UxDebugCheckRefcount && v74 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v51, 9u, v74);
    if ( !v74 )
      UlConsumerCleanupCompletion(*((_QWORD *)v3 + 218));
    *((_QWORD *)v3 + 218) = 0;
  }
  if ( !v47 )
    goto LABEL_148;
  v52 = _InterlockedDecrement((volatile signed __int32 *)v47 + 5);
  if ( UxDebugCheckRefcount && v52 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v47 + 20), 0x26u, v52);
  if ( v52 )
    goto LABEL_148;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v47, 0);
  v53 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v47 + 8) + 264LL) + 8LL * *(unsigned __int16 *)(*((_QWORD *)v47 + 7) + 56LL));
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*((_QWORD *)v47 + 7) + 944LL, 0);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v53, 0);
  v54 = *((_QWORD *)v47 + 3);
  v55 = v47 + 24;
  if ( *(char **)(v54 + 8) != v47 + 24 )
    goto LABEL_141;
  v56 = (_QWORD *)*((_QWORD *)v47 + 4);
  if ( (_QWORD *)*v56 != v55
    || (*v56 = v54,
        *(_QWORD *)(v54 + 8) = v56,
        *v55 = 0,
        *((_QWORD *)v47 + 4) = 0,
        v57 = v47 + 40,
        v58 = *((_QWORD *)v47 + 5),
        *(char **)(v58 + 8) != v47 + 40)
    || (v59 = (_QWORD *)*((_QWORD *)v47 + 6), (_QWORD *)*v59 != v57) )
  {
LABEL_141:
    __fastfail(3u);
  }
  *v59 = v58;
  *(_QWORD *)(v58 + 8) = v59;
  *v57 = 0;
  *((_QWORD *)v47 + 6) = 0;
  ExReleasePushLockExclusiveEx(v53, 0);
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*((_QWORD *)v47 + 7) + 944LL, 0);
  KeLeaveCriticalRegion();
  v60 = (volatile signed __int32 *)*((_QWORD *)v47 + 11);
  if ( v60 )
  {
    v75 = _InterlockedDecrement(v60);
    if ( UxDebugCheckRefcount && v75 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v60, 0xEu, v75);
    if ( !v75 )
      UlConsumerCleanupCompletion(*((_QWORD *)v47 + 11));
    *((_QWORD *)v47 + 11) = 0;
  }
  v61 = (volatile signed __int32 *)*((_QWORD *)v47 + 8);
  v62 = _InterlockedDecrement(v61);
  if ( UxDebugCheckRefcount && v62 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v61, 0xEu, v62);
  if ( !v62 )
    UlFreeRequestQueue(*((PVOID *)v47 + 8));
  v63 = *((_QWORD *)v47 + 7);
  *((_QWORD *)v47 + 8) = 0;
  v64 = _InterlockedDecrement((volatile signed __int32 *)(v63 + 40));
  if ( UxDebugCheckRefcount && v64 <= -1 )
    UlBugCheckEx(3u, v63 + 40, 0xEu, v64);
  if ( !v64 )
  {
    v80 = v63 + 64;
    v81 = IoGetCurrentProcess();
    v82 = *(void **)(v63 + 1088);
    v83 = *(_QWORD *)v80;
    if ( UxSystemProcess != v81 )
    {
      if ( v83 || *(_QWORD *)(v80 + 16) || *(_QWORD *)(v80 + 32) )
        UlBugCheckEx(1u, v80, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      UlThreadPoolEnqueueWorkItem(0, v80, UlFreeHttpConnection, 1, v82, -1);
      goto LABEL_123;
    }
    if ( v83 || *(_QWORD *)(v80 + 16) || *(_QWORD *)(v80 + 32) )
      UlBugCheckEx(1u, v80, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v98 = 0;
      if ( (unsigned int)dword_1401A3F48 > 1 )
      {
        v98 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F60 )
          v98 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( v82 == (void *)-1LL )
        v82 = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v80 + 32) = v82;
      *(_QWORD *)&v123 = 0;
      if ( v82 )
        ObfReferenceObjectWithTag(v82, 0x49576C55u);
      PsGetPermanentSiloContext(v82, (unsigned int)UxPodMonitorSlot, &v123);
      v99 = v123 + 24;
      v100 = _InterlockedIncrement((volatile signed __int32 *)(v123 + 24));
      if ( UxDebugCheckRefcount && v100 <= -1 )
        UlBugCheckEx(3u, v99, 0xDu, v100);
      *(_BYTE *)(v80 + 24) = 1;
      v101 = *(_QWORD *)(qword_1401A3F50 + 8LL * v98);
      *(_QWORD *)(v80 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v101 + 16), (PSLIST_ENTRY)v80) )
      {
        KeSetEvent((PRKEVENT)(v101 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v101);
      }
      goto LABEL_123;
    }
    v95 = 0;
    v123 = 0;
    if ( v82 == (void *)-1LL )
    {
      v97 = *((_QWORD *)&v123 + 1);
    }
    else
    {
      v96 = PsAttachSiloToCurrentThread(v82);
      v97 = v96;
      v95 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v96, v82);
        UlFreeHttpConnection(v80);
LABEL_225:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v97);
        PsDetachSiloFromCurrentThread(v97);
        goto LABEL_123;
      }
    }
    UlFreeHttpConnection(v80);
    if ( !v95 )
      goto LABEL_123;
    goto LABEL_225;
  }
LABEL_123:
  v30 = UxDebugDisableLookaside == 0;
  *((_QWORD *)v47 + 7) = 0;
  *((_DWORD *)v47 + 4) = 1969441909;
  if ( v30 )
  {
    if ( UxCompactMode )
    {
      v86 = qword_1401A0910;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v86, v47, CurrentNodeNumber);
    }
    else
    {
      v65 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v47 + 1) << 7);
      if ( !*(_BYTE *)(v65 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0910, v65 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v65 + 64), v47);
    }
  }
  else
  {
    memset(v124, 0, sizeof(v124));
    DWORD2(v124[2]) = dword_1401A0928;
    ((void (__fastcall *)(char *, _OWORD *))off_1401A0938)(v47, v124);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
LABEL_148:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 238, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  }
  v66 = (unsigned __int16 *)*((_QWORD *)v3 + 335);
  if ( v66 != v3 + 1344 && v66 )
    ExFreePoolWithTag(v66, 0);
  v67 = (unsigned __int16 *)*((_QWORD *)v3 + 340);
  if ( v67 != v3 + 1364 && v67 )
    ExFreePoolWithTag(v67, 0);
  v68 = (void *)*((_QWORD *)v3 + 343);
  if ( v68 )
    ExFreePoolWithTag(v68, 0);
  v30 = UxDebugDisableLookaside == 0;
  *((_DWORD *)v3 + 4) = 1380469877;
  if ( v30 )
  {
    if ( UxCompactMode )
    {
      v84 = qword_1401A0160;
      v85 = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v84, v3, v85);
    }
    else
    {
      v69 = qword_1401A0160 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v3 + 1) << 7);
      if ( !*(_BYTE *)(v69 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0160, v69 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v69 + 64), v3);
    }
  }
  else
  {
    memset(v124, 0, sizeof(v124));
    DWORD2(v124[2]) = dword_1401A0178;
    ((void (__fastcall *)(unsigned __int16 *, _OWORD *))off_1401A0188)(v3, v124);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 47, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
}

```

## disassembly

```asm
0x14000c390  push    rbp
0x14000c392  push    rbx
0x14000c393  push    rdi
0x14000c394  push    r12
0x14000c396  lea     rbp, [rsp-3Fh]
0x14000c39b  sub     rsp, 0C8h
0x14000c3a2  mov     rax, cs:__security_cookie
0x14000c3a9  xor     rax, rsp
0x14000c3ac  mov     [rbp+57h+var_30], rax
0x14000c3b0  mov     rbx, rcx
0x14000c3b3  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000c3ba  jnz     loc_14000D8CD
0x14000c3c0  mov     rdi, [rbx+528h]
0x14000c3c7  add     rbx, 0FFFFFFFFFFFFFB20h
0x14000c3ce  xor     r12d, r12d
0x14000c3d1  mov     [rsp+0E0h+arg_8], rsi
0x14000c3d9  mov     [rsp+0E0h+arg_18], r14
0x14000c3e1  test    rdi, rdi
0x14000c3e4  jnz     loc_14000D8EB
0x14000c3ea  mov     rdi, [rbx+0A00h]
0x14000c3f1  test    rdi, rdi
0x14000c3f4  jnz     loc_14000D90A
0x14000c3fa  mov     eax, [rbx+9F0h]
0x14000c400  test    al, 8
0x14000c402  jnz     short loc_14000C414
0x14000c404  mov     rcx, [rbx+0A08h]; P
0x14000c40b  test    rcx, rcx
0x14000c40e  jnz     loc_14000D920
0x14000c414  mov     eax, [rbx+9F0h]
0x14000c41a  test    al, 10h
0x14000c41c  jnz     loc_14000D933
0x14000c422  xorps   xmm0, xmm0
0x14000c425  movups  xmmword ptr [rbx+9F0h], xmm0
0x14000c42c  movups  xmmword ptr [rbx+0A00h], xmm0
0x14000c433  movups  xmmword ptr [rbx+0A10h], xmm0
0x14000c43a  mov     rcx, [rbx+0C38h]; P
0x14000c441  test    rcx, rcx
0x14000c444  jnz     loc_14000D94D
0x14000c44a  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000c451  jnz     loc_14000D5EC
0x14000c457  mov     eax, [rbx+898h]
0x14000c45d  mov     edi, r12d
0x14000c460  mov     [rsp+0E0h+arg_10], r13
0x14000c468  mov     [rsp+0E0h+var_20], r15
0x14000c470  test    al, 10h
0x14000c472  jnz     loc_14000D967
0x14000c478  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000c47f  jnz     loc_14000D550
0x14000c485  mov     rcx, [rbx+0AC8h]; P
0x14000c48c  test    rcx, rcx
0x14000c48f  jnz     loc_14000D96F
0x14000c495  lea     rdi, [rbx+9A0h]
0x14000c49c  cmp     [rdi], rdi
0x14000c49f  jz      short loc_14000C4F8
0x14000c4a1  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14000c4a8  jnz     loc_14000D447
0x14000c4ae  mov     rcx, [rdi]
0x14000c4b1  cmp     rcx, rdi
0x14000c4b4  jz      short loc_14000C4EB
0x14000c4b6  mov     rax, [rcx]
0x14000c4b9  cmp     [rax+8], rcx
0x14000c4bd  jnz     loc_14000CD36
0x14000c4c3  mov     rdx, [rcx+8]
0x14000c4c7  cmp     [rdx], rcx
0x14000c4ca  jnz     loc_14000CD36
0x14000c4d0  mov     [rdx], rax
0x14000c4d3  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14000c4d7  mov     [rax+8], rdx
0x14000c4db  xor     edx, edx; Tag
0x14000c4dd  call    cs:__imp_ExFreePoolWithTag
0x14000c4e4  nop     dword ptr [rax+rax+00h]
0x14000c4e9  jmp     short loc_14000C4AE
0x14000c4eb  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14000c4f2  jnz     loc_14000D989
0x14000c4f8  mov     rdi, [rbx+760h]
0x14000c4ff  test    rdi, rdi
0x14000c502  jz      short loc_14000C556
0x14000c504  cmp     [rbx+768h], r12b
0x14000c50b  jz      loc_14000CDD0
0x14000c511  cmp     cs:UxCompactMode, r12b
0x14000c518  mov     rcx, cs:qword_1401A0490
0x14000c51f  jnz     loc_14000D4E0
0x14000c525  mov     esi, [rbx+76Ch]
0x14000c52b  inc     esi
0x14000c52d  shl     rsi, 7
0x14000c531  add     rsi, rcx
0x14000c534  movzx   eax, byte ptr [rsi+0B0h]
0x14000c53b  test    al, al
0x14000c53d  jz      loc_14000D5A4
0x14000c543  mov     rdx, rdi; Entry
0x14000c546  lea     rcx, [rsi+40h]; Lookaside
0x14000c54a  call    cs:__imp_ExFreeToLookasideListEx
0x14000c551  nop     dword ptr [rax+rax+00h]
0x14000c556  xor     eax, eax
0x14000c558  xorps   xmm0, xmm0
0x14000c55b  movups  xmmword ptr [rbx+758h], xmm0
0x14000c562  mov     [rbx+768h], rax
0x14000c569  mov     rdi, [rbx+778h]
0x14000c570  test    rdi, rdi
0x14000c573  jz      short loc_14000C592
0x14000c575  cmp     [rbx+780h], al
0x14000c57b  jnz     loc_14000CDE6
0x14000c581  xor     edx, edx; Tag
0x14000c583  mov     rcx, rdi; P
0x14000c586  call    cs:__imp_ExFreePoolWithTag
0x14000c58d  nop     dword ptr [rax+rax+00h]
0x14000c592  xor     eax, eax
0x14000c594  xorps   xmm0, xmm0
0x14000c597  movups  xmmword ptr [rbx+770h], xmm0
0x14000c59e  mov     [rbx+780h], rax
0x14000c5a5  lea     rax, [rbp+57h+var_B0]
0x14000c5a9  mov     [rbp+57h+var_B0], rax
0x14000c5ad  lea     rax, [rbp+57h+var_B0]
0x14000c5b1  mov     [rbp+57h+var_A8], rax
0x14000c5b5  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000c5bc  jnz     loc_14000D5C0
0x14000c5c2  call    cs:__imp_KeEnterCriticalRegion
0x14000c5c9  nop     dword ptr [rax+rax+00h]
0x14000c5ce  xor     edx, edx
0x14000c5d0  lea     rcx, [rbx+0AF8h]
0x14000c5d7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c5de  nop     dword ptr [rax+rax+00h]
0x14000c5e3  mov     rax, [rbp+57h+var_B0]
0x14000c5e7  lea     rcx, [rbp+57h+var_B0]
0x14000c5eb  cmp     [rax+8], rcx
0x14000c5ef  jnz     loc_14000CD36
0x14000c5f5  mov     r8, [rbp+57h+var_A8]
0x14000c5f9  lea     rax, [rbp+57h+var_B0]
0x14000c5fd  cmp     [r8], rax
0x14000c600  jnz     loc_14000CD36
0x14000c606  lea     rdx, [rbx+0AE8h]
0x14000c60d  mov     rax, [rdx]
0x14000c610  cmp     [rax+8], rdx
0x14000c614  jnz     loc_14000CD36
0x14000c61a  mov     rax, [rdx+8]
0x14000c61e  cmp     [rax], rdx
0x14000c621  jnz     loc_14000CD36
0x14000c627  mov     [r8], rdx
0x14000c62a  lea     rcx, [rbp+57h+var_B0]
0x14000c62e  mov     rax, [rdx+8]
0x14000c632  mov     [rbp+57h+var_A8], rax
0x14000c636  mov     [rax], rcx
0x14000c639  mov     rax, [rdx]
0x14000c63c  mov     [rdx+8], r8
0x14000c640  cmp     [rax+8], rdx
0x14000c644  jnz     loc_14000CD36
0x14000c64a  cmp     [r8], rdx
0x14000c64d  jnz     loc_14000CD36
0x14000c653  mov     [r8], rax
0x14000c656  lea     rcx, [rbx+0AF8h]
0x14000c65d  mov     [rax+8], r8
0x14000c661  mov     [rdx+8], rdx
0x14000c665  mov     [rdx], rdx
0x14000c668  xor     edx, edx
0x14000c66a  mov     byte ptr [rbx+0B00h], 1
0x14000c671  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c678  nop     dword ptr [rax+rax+00h]
0x14000c67d  call    cs:__imp_KeLeaveCriticalRegion
0x14000c684  nop     dword ptr [rax+rax+00h]
0x14000c689  mov     r14d, 0FFFFFFFFh
0x14000c68f  mov     rax, [rbp+57h+var_B0]
0x14000c693  lea     rcx, [rbp+57h+var_B0]
0x14000c697  cmp     rax, rcx
0x14000c69a  jnz     loc_14000CD3D
0x14000c6a0  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000c6a7  jnz     loc_14000D56E
0x14000c6ad  mov     r15d, r12d
0x14000c6b0  cmp     r12w, [rbx+642h]
0x14000c6b8  jnb     loc_14000C7F7
0x14000c6be  mov     eax, r15d
0x14000c6c1  lea     rdi, ds:0[rax*8]
0x14000c6c9  mov     rax, [rbx+648h]
0x14000c6d0  mov     rdx, [rdi+rax]
0x14000c6d4  mov     eax, r14d
0x14000c6d7  add     rdx, 20h ; ' '; BugCheckParameter2
0x14000c6db  lock xadd [rdx], eax
0x14000c6df  dec     eax
0x14000c6e1  cmp     cs:UxDebugCheckRefcount, r12b
0x14000c6e8  jnz     loc_14000CFEA
0x14000c6ee  test    eax, eax
0x14000c6f0  jnz     loc_14000C7E4
0x14000c6f6  mov     rax, [rbx+648h]
0x14000c6fd  mov     rsi, [rbx+18h]
0x14000c701  mov     rdi, [rdi+rax]
0x14000c705  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000c70c  jnz     loc_14000D9A4
0x14000c712  mov     rdx, [rdi+98h]
0x14000c719  test    rdx, rdx
0x14000c71c  jz      short loc_14000C73F
0x14000c71e  mov     rax, [rsi+1F8h]
0x14000c725  mov     rcx, [rsi+1F0h]
0x14000c72c  mov     rax, [rax+80h]
0x14000c733  call    _guard_dispatch_icall
0x14000c738  mov     [rdi+98h], r12
0x14000c73f  mov     eax, [rdi+8Ch]
0x14000c745  cmp     eax, 4
0x14000c748  jz      loc_14000D0C2
0x14000c74e  test    eax, eax
0x14000c750  jnz     loc_14000D007
0x14000c756  lea     rax, aUlrp; "UlRP"
0x14000c75d  lea     rcx, off_1401A0158
0x14000c764  lea     r8, qword_1401A0130
0x14000c76b  cmp     cs:UxDebugDisableLookaside, r12b
0x14000c772  xorps   xmm0, xmm0
0x14000c775  movups  [rbp+57h+var_90], xmm0
0x14000c779  mov     dword ptr [rdi+10h], 50524C75h
0x14000c780  movups  [rbp+57h+var_80], xmm0
0x14000c784  movups  [rbp+57h+var_70], xmm0
0x14000c788  movups  [rbp+57h+var_60], xmm0
0x14000c78c  movups  [rbp+57h+var_50], xmm0
0x14000c790  movups  [rbp+57h+var_40], xmm0
0x14000c794  jnz     loc_14000D9E5
0x14000c79a  cmp     cs:UxCompactMode, r12b
0x14000c7a1  mov     r8, [r8]
0x14000c7a4  jnz     loc_14000D0B2
0x14000c7aa  mov     esi, [rdi]
0x14000c7ac  inc     esi
0x14000c7ae  shl     rsi, 7
0x14000c7b2  add     rsi, r8
0x14000c7b5  movzx   eax, byte ptr [rsi+0B0h]
0x14000c7bc  test    al, al
0x14000c7be  jz      loc_14000D53F
0x14000c7c4  mov     rdx, rdi; Entry
0x14000c7c7  lea     rcx, [rsi+40h]; Lookaside
0x14000c7cb  call    cs:__imp_ExFreeToLookasideListEx
0x14000c7d2  nop     dword ptr [rax+rax+00h]
0x14000c7d7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000c7de  jnz     loc_14000D9FE
0x14000c7e4  movzx   eax, word ptr [rbx+642h]
0x14000c7eb  inc     r15d
0x14000c7ee  cmp     r15d, eax
0x14000c7f1  jb      loc_14000C6BE
0x14000c7f7  cmp     word ptr [rbx+640h], 1
0x14000c7ff  ja      loc_14000DA19
0x14000c805  mov     rcx, [rbx+7F0h]; P
0x14000c80c  test    rcx, rcx
0x14000c80f  jz      short loc_14000C81E
0x14000c811  cmp     rcx, [rbx+218h]
0x14000c818  jnz     loc_14000D4ED
0x14000c81e  mov     rcx, [rbx+820h]; P
0x14000c825  test    rcx, rcx
0x14000c828  jnz     loc_14000CE59
0x14000c82e  mov     rcx, [rbx+9B0h]
0x14000c835  test    rcx, rcx
0x14000c838  jnz     loc_14000D74A
0x14000c83e  mov     rdi, [rbx+18h]
0x14000c842  mov     eax, r14d
0x14000c845  lea     rdx, [rdi+28h]; BugCheckParameter2
0x14000c849  lock xadd [rdx], eax
0x14000c84d  dec     eax
0x14000c84f  cmp     cs:UxDebugCheckRefcount, r12b
0x14000c856  jnz     loc_14000CF75
0x14000c85c  mov     r13d, 1
0x14000c862  test    eax, eax
0x14000c864  jz      loc_14000CECB
0x14000c86a  cmp     byte ptr [rbx+520h], 0
0x14000c871  mov     [rbx+18h], r12
0x14000c875  jz      short loc_14000C887
0x14000c877  lea     rcx, [rbx+510h]
0x14000c87e  movzx   edx, r13b
0x14000c882  call    UlCleanupConfigGroupInfo
0x14000c887  mov     eax, [rbx+960h]
0x14000c88d  test    r13b, al
0x14000c890  jnz     loc_14000DAA6
0x14000c896  mov     rdx, [rbx+978h]; BugCheckParameter2
0x14000c89d  test    rdx, rdx
0x14000c8a0  jnz     loc_14000D84B
0x14000c8a6  mov     rcx, [rbx+980h]; P
0x14000c8ad  test    rcx, rcx
0x14000c8b0  jnz     loc_14000DADD
0x14000c8b6  mov     rcx, [rbx+8F0h]; Handle
0x14000c8bd  test    rcx, rcx
0x14000c8c0  jnz     loc_14000DAF7
0x14000c8c6  or      dword ptr [rbx+8D8h], 4
0x14000c8cd  mov     rcx, [rbx+918h]; pvContextBuffer
0x14000c8d4  test    rcx, rcx
0x14000c8d7  jnz     loc_14000DB0F
0x14000c8dd  mov     rcx, [rbx+920h]; P
0x14000c8e4  test    rcx, rcx
0x14000c8e7  jnz     loc_14000DB2E
0x14000c8ed  mov     eax, [rbx+8D8h]
0x14000c8f3  test    al, 4
0x14000c8f5  jz      short loc_14000C907
0x14000c8f7  mov     rdx, [rbx+930h]
0x14000c8fe  test    rdx, rdx
0x14000c901  jnz     loc_14000DB50
0x14000c907  mov     rcx, [rbx+900h]; P
0x14000c90e  test    rcx, rcx
0x14000c911  jnz     loc_14000DB7A
0x14000c917  or      dword ptr [rbx+8D8h], 2
0x14000c91e  mov     rax, [rbx+908h]
0x14000c925  test    rax, rax
0x14000c928  jnz     loc_14000D88A
0x14000c92e  mov     rcx, [rbx+8E0h]
0x14000c935  test    rcx, rcx
0x14000c938  jnz     loc_14000DB9C
0x14000c93e  mov     [rbx+8E0h], r12
0x14000c945  mov     rsi, r12
0x14000c948  and     dword ptr [rbx+8D8h], 0FFFFFFFEh
0x14000c94f  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
  ... truncated ...
```
