# CmsVolumeContainer::RotateContainers(CmsTransactionContext *,unsigned __int64,unsigned __int64,_EMS_STORAGE_TIER_MEDIA_TYPE,uchar,long)

- ea: `0x1c00da6c4`
- end: `0x1c00dc5c4`
- name: `?RotateContainers@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_K1W4_EMS_STORAGE_TIER_MEDIA_TYPE@@EJ@Z`
- size: `7936`
- prototype: ``
- caller_count: `3`
- callee_count: `38`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c00c0590`
- `0x1c00d830c`
- `0x1c00e3438`

## callees

- `0x1c002313c`
- `0x1c0024964`
- `0x1c0025f98`
- `0x1c00274f4`
- `0x1c0029630`
- `0x1c002981c`
- `0x1c0029acc`
- `0x1c002a564`
- `0x1c002a87c`
- `0x1c002c7a0`
- `0x1c002cc80`
- `0x1c002d368`
- `0x1c0035848`
- `0x1c0047d84`
- `0x1c0050a94`
- `0x1c005a66c`
- `0x1c00646c8`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c00b1354`
- `0x1c00b2fcc`
- `0x1c00b5e18`
- `0x1c00b6854`
- `0x1c00b84b4`
- `0x1c00bf5d0`
- `0x1c00d749c`
- `0x1c00d7fbc`
- `0x1c00da6c4`
- `0x1c00dcb3c`
- `0x1c00dce64`
- `0x1c00dd328`
- `0x1c00dd6c0`
- `0x1c00eb754`
- `0x1c00eb8ec`
- `0x1c00ed1bc`
- `0x1c00ee110`
- `0x1c00fb424`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00dbe88`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00dc123`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00dbe88`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00dc123`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00da7e0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00da852`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00da8b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00da938`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00db302`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00da7e0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00da852`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00da8b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00da938`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00db302`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00da8db`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00da91c`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00dc0b0`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00dc0e3`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00dc2e9`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00dc33b`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00da8db`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00da91c`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00dc0b0`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00dc0e3`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00dc2e9`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00dc33b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00db379`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00db379`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00daab0`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dab23`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dab42`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db03a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db054`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db92d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db9a4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db9c1`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dbf14`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dc163`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dc502`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dc51e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00daab0`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dab23`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dab42`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db03a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db054`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db92d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db9a4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00db9c1`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dbf14`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dc163`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dc502`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00dc51e`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00db2d2`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00dc18c`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00dc282`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00dc4ab`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00dc18c`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00dc282`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c00dc4ab`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00dc1af`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00dc2a6`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00dc4d0`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00dc1af`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00dc2a6`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c00dc4d0`
- `ntoskrnl!RtlClearAllBits` at `0x1c00dc0f6`
- `ntoskrnl!RtlClearAllBits` at `0x1c00dc2fc`
- `ntoskrnl!RtlClearAllBits` at `0x1c00dc34e`
- `ntoskrnl!RtlClearAllBits` at `0x1c00dc0f6`
- `ntoskrnl!RtlClearAllBits` at `0x1c00dc2fc`
- `ntoskrnl!RtlClearAllBits` at `0x1c00dc34e`
- `ntoskrnl!RtlSetAllBits` at `0x1c00dc14a`
- `ntoskrnl!RtlSetAllBits` at `0x1c00dc14a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dab6b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00daba2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00db7e2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00db820`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00db9ea`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dba21`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dc063`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dc541`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dc571`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dab6b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00daba2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00db7e2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00db820`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00db9ea`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dba21`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dc063`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dc541`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00dc571`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db0ac`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db0c6`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db1c2`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db392`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db6a5`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db0ac`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db0c6`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db1c2`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db392`
- `HAL!KeQueryPerformanceCounter` at `0x1c00db6a5`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::RotateContainers(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5,
        char a6,
        int a7)
{
  int v7; // eax
  struct SmsContainer *v10; // r13
  struct SmsContainer *v11; // r15
  int updated; // esi
  unsigned int v13; // ebx
  __int64 v14; // rcx
  PVOID PoolWithTag; // rax
  unsigned __int64 StorageTierForRange; // rcx
  void *v17; // rax
  PVOID v18; // rax
  void *v19; // rax
  __int64 v20; // rax
  ULONG *v21; // rax
  __int64 v22; // rax
  ULONG *v23; // rdx
  char *v24; // rax
  CmsContainerRangeMap *v25; // rdi
  unsigned int v26; // edx
  CmsVolume *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rdx
  char v30; // di
  int ContainerReference; // eax
  struct CmsTransactionContext *v32; // rdx
  CmsVolumeContainer *v33; // rcx
  struct CmsTransactionContext *v34; // rdx
  CmsVolumeContainer *v35; // rcx
  int v36; // eax
  int v37; // eax
  __int64 v38; // rax
  int v39; // eax
  struct SmsAllocationRegionEx *v40; // rdi
  struct SmsAllocationRegionEx *v41; // rdi
  int v42; // eax
  int v43; // eax
  unsigned int v44; // edx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // r9
  LARGE_INTEGER v48; // rdi
  __int64 v49; // rax
  __int64 v50; // rdx
  int v51; // ecx
  unsigned __int64 v52; // r9
  unsigned __int64 v53; // r8
  LARGE_INTEGER v54; // rax
  __int64 v55; // rcx
  __int128 v56; // rax
  volatile signed __int32 *v57; // rcx
  LONGLONG v58; // rdx
  __int128 v59; // rtt
  void *v60; // rdi
  int v61; // eax
  unsigned __int8 v62; // r9
  _DWORD *v63; // rax
  void *v64; // rdi
  LARGE_INTEGER v65; // rax
  __int64 v66; // r9
  LARGE_INTEGER v67; // rdi
  unsigned int v68; // esi
  char v69; // cl
  int v70; // eax
  __int64 v71; // rcx
  unsigned int v72; // edx
  __int64 v73; // rcx
  unsigned __int64 v74; // rax
  unsigned __int64 v75; // rax
  LARGE_INTEGER v76; // rax
  __int64 v77; // rcx
  __int128 v78; // rax
  struct _IO_REMOVE_LOCK *v79; // rax
  __int64 v80; // rcx
  struct CmsTransactionContext *v81; // rdx
  CmsVolumeContainer *v82; // rcx
  int v83; // edi
  int v84; // eax
  struct CmsTransactionContext *v85; // rdx
  int v86; // eax
  char v88; // di
  int v89; // eax
  int v90; // eax
  int v91; // eax
  __int64 v92; // rcx
  unsigned int *v93; // rcx
  struct SmsAllocationRegionEx *v94; // rdi
  __int64 v95; // rcx
  __int64 v96; // rdx
  struct CmsRowWithBuffer *v97; // rdi
  unsigned int v98; // r10d
  char *v99; // rdi
  struct _CmsRow *v100; // r8
  __int128 v101; // xmm0
  struct _CmsRow *v102; // r8
  struct _CmsRow *v103; // r8
  SmsAllocationRegionEx *v104; // rdi
  unsigned __int64 v105; // rdx
  struct SmsAllocationRegionEx *v106; // rax
  char *v107; // r8
  char v108; // dl
  char v109; // r10
  char v110; // al
  int v111; // eax
  __int64 v112; // rdx
  struct SmsContainer *v113; // rax
  __int64 v114; // r9
  __int64 v115; // rdi
  __int64 v116; // rdi
  struct CmsAllocator *v117; // r8
  __int64 v118; // rax
  signed __int64 v119; // r9
  unsigned int v120; // r8d
  unsigned int v121; // eax
  __int64 v122; // rdx
  __int64 v123; // rdi
  struct SmsAllocationRegionEx *v124; // rdi
  struct SmsAllocationRegionEx *v125; // rdi
  __int128 v126; // xmm1
  __int128 v127; // xmm0
  __int128 v128; // xmm1
  __int128 v129; // xmm0
  __int128 v130; // xmm1
  __int128 v131; // xmm0
  __int128 v132; // xmm1
  __int128 v133; // xmm0
  CmsVolume *v134; // rcx
  __int64 v135; // rdi
  CmsContainerRangeMap *v136; // rbx
  unsigned int v137; // edx
  struct _RTL_BITMAP *v139; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v140; // [rsp+20h] [rbp-E0h]
  unsigned int v141; // [rsp+20h] [rbp-E0h]
  struct _RTL_BITMAP *v142; // [rsp+20h] [rbp-E0h]
  struct _RTL_BITMAP *v143; // [rsp+20h] [rbp-E0h]
  char *v144; // [rsp+28h] [rbp-D8h]
  int *v145; // [rsp+48h] [rbp-B8h]
  struct _SCRUB_PARITY_EXTENT_DATA *v146; // [rsp+50h] [rbp-B0h]
  char v147; // [rsp+60h] [rbp-A0h]
  char v148; // [rsp+61h] [rbp-9Fh]
  char v149; // [rsp+62h] [rbp-9Eh]
  char v150; // [rsp+63h] [rbp-9Dh]
  char v151; // [rsp+64h] [rbp-9Ch]
  int v152; // [rsp+68h] [rbp-98h]
  int v153; // [rsp+68h] [rbp-98h]
  unsigned int v154; // [rsp+68h] [rbp-98h]
  unsigned int v155; // [rsp+68h] [rbp-98h]
  struct SmsContainer *v156; // [rsp+70h] [rbp-90h] BYREF
  struct SmsContainer *v157; // [rsp+78h] [rbp-88h] BYREF
  bool v158; // [rsp+80h] [rbp-80h]
  struct SmsAllocationRegionEx *v159; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v160; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v161; // [rsp+98h] [rbp-68h]
  unsigned __int64 v162; // [rsp+A0h] [rbp-60h]
  SmsAllocationRegionEx *v163; // [rsp+A8h] [rbp-58h] BYREF
  void *v164; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v165; // [rsp+B8h] [rbp-48h] BYREF
  struct _CmsRow *v166; // [rsp+C0h] [rbp-40h]
  struct SmsAllocationRegionEx *v167; // [rsp+C8h] [rbp-38h] BYREF
  CmsContainerRangeMap *v168; // [rsp+D0h] [rbp-30h]
  unsigned int v169; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v170; // [rsp+DCh] [rbp-24h] BYREF
  int v171; // [rsp+E0h] [rbp-20h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+E8h] [rbp-18h] BYREF
  struct SmsAllocationRegionEx *v173; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v174; // [rsp+100h] [rbp+0h]
  void *v175; // [rsp+110h] [rbp+10h]
  unsigned __int64 v176; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v177; // [rsp+120h] [rbp+20h] BYREF
  size_t Size; // [rsp+128h] [rbp+28h]
  unsigned __int64 v179; // [rsp+130h] [rbp+30h]
  unsigned __int64 v180; // [rsp+138h] [rbp+38h]
  unsigned __int64 v181; // [rsp+140h] [rbp+40h]
  struct SmsContainer *v182; // [rsp+148h] [rbp+48h] BYREF
  __int64 v183; // [rsp+150h] [rbp+50h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+158h] [rbp+58h] BYREF
  __int128 v185; // [rsp+168h] [rbp+68h]
  __int128 v186; // [rsp+178h] [rbp+78h]
  __int128 v187; // [rsp+188h] [rbp+88h]
  __int64 v188; // [rsp+198h] [rbp+98h]
  struct _RTL_BITMAP *v189; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _RTL_BITMAP *p_BitMapHeader; // [rsp+1A8h] [rbp+A8h] BYREF
  LARGE_INTEGER PerformanceCounter; // [rsp+1B0h] [rbp+B0h]
  _QWORD v192[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  _QWORD v193[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  struct _RTL_BITMAP v194; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v195[2]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v196[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  struct _RTL_BITMAP v197; // [rsp+208h] [rbp+108h] BYREF
  struct _RTL_BITMAP v198; // [rsp+218h] [rbp+118h] BYREF
  struct _RTL_BITMAP v199; // [rsp+228h] [rbp+128h] BYREF
  int v200; // [rsp+238h] [rbp+138h] BYREF
  __int128 *v201; // [rsp+240h] [rbp+140h]
  int v202; // [rsp+248h] [rbp+148h]
  __int128 *v203; // [rsp+250h] [rbp+150h]
  LONGLONG v204; // [rsp+258h] [rbp+158h]
  __int128 v205; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v206[32]; // [rsp+270h] [rbp+170h] BYREF
  __int128 v207; // [rsp+290h] [rbp+190h]
  __int64 v208; // [rsp+2A0h] [rbp+1A0h]
  int v209; // [rsp+2A8h] [rbp+1A8h]
  __int128 v210; // [rsp+2B0h] [rbp+1B0h]
  __int64 v211; // [rsp+2C0h] [rbp+1C0h]
  int v212; // [rsp+2E0h] [rbp+1E0h]
  __int128 v213; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v214; // [rsp+300h] [rbp+200h] BYREF
  __int128 v215; // [rsp+310h] [rbp+210h] BYREF
  __int128 v216; // [rsp+320h] [rbp+220h] BYREF
  __int128 v217; // [rsp+330h] [rbp+230h] BYREF

  v165 = a3;
  v176 = a4;
  v211 = 0;
  v7 = *(_DWORD *)(a1 + 112);
  v157 = 0;
  v156 = 0;
  v10 = 0;
  v182 = 0;
  v11 = 0;
  v207 = 0;
  v208 = 0;
  v209 = 0;
  v212 = 0;
  v168 = 0;
  v159 = 0;
  v163 = 0;
  v167 = 0;
  v173 = 0;
  v149 = 0;
  v150 = 0;
  v151 = 0;
  v158 = 0;
  v166 = 0;
  v160 = 0;
  v214 = 0;
  v215 = 0;
  v210 = 0;
  v216 = 0;
  BitMapHeader = 0;
  if ( (v7 & 1) == 0 )
    return (unsigned int)-1073741637;
  LOWORD(v13) = 0;
  if ( a6 )
  {
    v17 = *(void **)(*(_QWORD *)(a1 + 216) + 8LL * a7);
  }
  else
  {
    if ( !*(_QWORD *)(a1 + 208) )
    {
      v14 = *(_QWORD *)(a1 + 8);
      if ( !*(_QWORD *)(v14 + 2888) )
      {
        PoolWithTag = ExAllocatePoolWithTag(
                        (POOL_TYPE)512,
                        (unsigned int)(*(_DWORD *)(v14 + 68) * *(_DWORD *)(v14 + 80)),
                        0x6F72534Du);
        *(_QWORD *)(a1 + 208) = PoolWithTag;
        if ( !PoolWithTag )
          goto LABEL_7;
      }
    }
    v17 = *(void **)(a1 + 208);
  }
  v164 = v17;
  if ( a6 )
  {
    v19 = *(void **)(*(_QWORD *)(a1 + 248) + 8LL * a7);
  }
  else
  {
    if ( !*(_QWORD *)(a1 + 240) && !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 2888LL) )
    {
      v18 = ExAllocatePoolWithTag(
              (POOL_TYPE)512,
              (unsigned int)(*(_DWORD *)(a1 + 228) * *(_DWORD *)(a1 + 232)),
              0x6372534Du);
      *(_QWORD *)(a1 + 240) = v18;
      if ( !v18 )
        goto LABEL_7;
    }
    v19 = *(void **)(a1 + 240);
  }
  v175 = v19;
  if ( !a6 && !*(_QWORD *)(a1 + 264) )
  {
    v20 = *(_QWORD *)(a1 + 8);
    if ( !*(_QWORD *)(v20 + 2888) )
    {
      v21 = (ULONG *)ExAllocatePoolWithTag((POOL_TYPE)512, *(_DWORD *)(v20 + 80) >> 3, 0x6972534Du);
      if ( v21 )
      {
        RtlInitializeBitMap((PRTL_BITMAP)(a1 + 256), v21, *(_DWORD *)(*(_QWORD *)(a1 + 8) + 80LL));
        goto LABEL_21;
      }
LABEL_7:
      updated = -1073741670;
      goto LABEL_252;
    }
  }
LABEL_21:
  v22 = *(_QWORD *)(a1 + 8);
  if ( !*(_QWORD *)(v22 + 2888) )
  {
    if ( a6 )
      v23 = *(ULONG **)(*(_QWORD *)(a1 + 272) + 16LL * a7 + 8);
    else
      v23 = *(ULONG **)(a1 + 264);
    RtlInitializeBitMap(&BitMapHeader, v23, *(_DWORD *)(v22 + 80));
  }
  v24 = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x40u, 0x6950534Du);
  v168 = (CmsContainerRangeMap *)v24;
  v25 = (CmsContainerRangeMap *)v24;
  if ( v24 )
  {
    LOBYTE(StorageTierForRange) = *(_BYTE *)(*(_QWORD *)(a1 + 8) + 76LL);
    *(_OWORD *)(v24 + 8) = 0;
    *(_OWORD *)(v24 + 24) = 0;
    *(_QWORD *)v24 = 0;
    v24[60] = StorageTierForRange;
    *((_DWORD *)v24 + 14) = 0;
    *(_WORD *)(v24 + 61) = 1;
    *((_QWORD *)v24 + 5) = 0;
    *((_QWORD *)v24 + 6) = 0;
  }
  else
  {
    v25 = 0;
    v168 = 0;
  }
  if ( !v25 )
    goto LABEL_7;
  updated = CmsContainerRangeMap::InitializeMapIfRequired(v25);
  if ( updated < 0 )
  {
    CmsContainerRangeMap::`scalar deleting destructor'(v25, v26);
    v168 = 0;
    goto LABEL_252;
  }
  CmsVolume::BeginTopLevelAction(v27, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v206, 0, 0);
  v149 = 1;
  v28 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 3032LL) + 16LL);
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v28 + 64LL))(v28, v29, 0);
  v30 = 0;
  v177 = v176;
  v152 = 10;
  v147 = 0;
  ContainerReference = CmsVolumeContainer::GetContainerReference(
                         (CmsVolumeContainer *)a1,
                         (struct CmsTransactionContext *)a2,
                         v165,
                         &v157,
                         0,
                         0,
                         0);
  v10 = v157;
  updated = ContainerReference;
  if ( ContainerReference >= 0 )
  {
    CmsVolumeContainer::IncrementExclusiveAcquirersCount((CmsVolumeContainer *)StorageTierForRange, v157);
    while ( 1 )
    {
      if ( CmsVolumeContainer::TryLockContainerExclusive(v33, v32, v10) )
      {
        v30 = 1;
        if ( !v11 )
        {
          v36 = CmsVolumeContainer::GetContainerReference(
                  (CmsVolumeContainer *)a1,
                  (struct CmsTransactionContext *)a2,
                  v177,
                  &v156,
                  0,
                  0,
                  0);
          v11 = v156;
          updated = v36;
          if ( v36 < 0 )
            goto LABEL_45;
          CmsVolumeContainer::IncrementExclusiveAcquirersCount((CmsVolumeContainer *)StorageTierForRange, v156);
        }
        if ( CmsVolumeContainer::TryLockContainerExclusive(v35, v34, v11) )
        {
          v147 = 1;
          goto LABEL_45;
        }
      }
      if ( v30 )
      {
        ExReleasePushLockEx((char *)v10 + 104, 2);
        v30 = 0;
      }
      v37 = v152;
      StorageTierForRange = (unsigned int)--v152;
      if ( !v37 )
        break;
      MsDelayExecutionThread(50);
    }
    updated = -1073741267;
  }
LABEL_45:
  if ( v10 )
    CmsVolumeContainer::DecrementExclusiveAcquirersCount((CmsVolumeContainer *)StorageTierForRange, v10);
  if ( v11 )
    CmsVolumeContainer::DecrementExclusiveAcquirersCount((CmsVolumeContainer *)StorageTierForRange, v11);
  if ( updated < 0 )
  {
    if ( v30 )
      ExReleasePushLockEx((char *)v10 + 104, 2);
    if ( v147 )
      ExReleasePushLockEx((char *)v11 + 104, 2);
    if ( v10 )
    {
      _InterlockedDecrement((volatile signed __int32 *)v10 + 22);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 328), 0, 0x20u);
      --*(_DWORD *)(a2 + 2824);
      v11 = v156;
      v10 = 0;
      v157 = 0;
    }
    if ( v11 )
    {
      _InterlockedDecrement((volatile signed __int32 *)v11 + 22);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 328), 0, 0x20u);
      --*(_DWORD *)(a2 + 2824);
      v10 = v157;
      v11 = 0;
      v156 = 0;
    }
    goto LABEL_252;
  }
  LOWORD(v13) = 3;
  v38 = (unsigned int)(*(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228));
  v151 = 1;
  v150 = 1;
  v214 = *(_OWORD *)((char *)v10 + v38 + 632);
  v215 = *(_OWORD *)((char *)v11 + v38 + 632);
  StorageTierForRange = *((unsigned int *)v10 + 143);
  if ( (StorageTierForRange & 1) != 0
    || (StorageTierForRange & 0x200) != 0
    || (StorageTierForRange & 0x100) != 0
    || (StorageTierForRange & 0x400) != 0
    || *((_DWORD *)v10 + 21)
    || *((int *)v10 + 24) > 0
    || (StorageTierForRange & 8) != 0
    || *((_BYTE *)v10 + 28) )
  {
    goto LABEL_248;
  }
  v39 = *((_DWORD *)v11 + 143);
  if ( (v39 & 1) != 0
    || (v39 & 0x200) != 0
    || (v39 & 0x400) != 0
    || *((_DWORD *)v11 + 21)
    || *((int *)v11 + 24) > 0
    || (v39 & 8) != 0
    || (v39 & 0x100) != 0 )
  {
LABEL_247:
    updated = -1073740759;
LABEL_249:
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 956LL));
LABEL_250:
    v10 = v157;
LABEL_251:
    v11 = v156;
    goto LABEL_252;
  }
  if ( (StorageTierForRange & 0x40) != 0 && (v39 & 0x40) != 0 )
    goto LABEL_76;
  if ( *((_QWORD *)&v214 + 1) != *((_QWORD *)&v215 + 1) )
  {
    updated = -1073741811;
    goto LABEL_252;
  }
  *(_QWORD *)(a2 + 16) |= 0x800000000uLL;
  LOWORD(v13) = 67;
  updated = CmsAllocator::PinBitmapRegion(
              *(CmsAllocator **)(*(_QWORD *)(a1 + 8) + 3032LL),
              (struct CmsTransactionContext *)a2,
              (const struct _RANGE *)&v214,
              &v159);
  if ( updated >= 0 )
  {
    updated = CmsAllocator::TryProtectRegion((CmsAllocator *)StorageTierForRange, v159, 1);
    if ( updated >= 0 )
    {
      LOWORD(v13) = 71;
      updated = CmsAllocator::PinBitmapRegion(
                  *(CmsAllocator **)(*(_QWORD *)(a1 + 8) + 3032LL),
                  (struct CmsTransactionContext *)a2,
                  (const struct _RANGE *)&v215,
                  &v163);
      if ( updated >= 0 )
      {
        v40 = v163;
        updated = CmsAllocator::TryProtectRegion((CmsAllocator *)StorageTierForRange, v163, 1);
        if ( updated >= 0 )
        {
          v13 = 79;
          if ( !CmsAllocator::IsRegionDurablyFree(
                  *(CmsAllocator **)(*(_QWORD *)(a1 + 8) + 3032LL),
                  (struct CmsTransactionContext *)a2,
                  v40) )
            goto LABEL_76;
          StorageTierForRange = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 3056LL);
          if ( *(_BYTE *)(StorageTierForRange + 16) )
          {
            updated = CmsAllocator::PinBitmapRegion(
                        *(CmsAllocator **)(StorageTierForRange + 8),
                        (struct CmsTransactionContext *)a2,
                        (const struct _RANGE *)&v214,
                        &v167);
            if ( updated < 0 )
              goto LABEL_252;
            updated = CmsAllocator::PinBitmapRegion(
                        *(CmsAllocator **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 3056LL) + 8LL),
                        (struct CmsTransactionContext *)a2,
                        (const struct _RANGE *)&v215,
                        &v173);
            if ( updated < 0 )
              goto LABEL_252;
            updated = CmsAllocator::TryProtectRegion((CmsAllocator *)StorageTierForRange, v167, 1);
            if ( updated < 0 )
              goto LABEL_252;
            v41 = v173;
            LOWORD(v13) = 95;
            updated = CmsAllocator::TryProtectRegion((CmsAllocator *)StorageTierForRange, v173, 1);
            if ( updated < 0 )
              goto LABEL_252;
            v13 = 127;
            if ( !CmsAllocator::IsRegionDurablyFree(
                    *(CmsAllocator **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 3056LL) + 8LL),
                    (struct CmsTransactionContext *)a2,
                    v41) )
            {
LABEL_76:
              updated = -1073740759;
              goto LABEL_252;
            }
          }
          v42 = *((_DWORD *)v10 + 143);
          if ( (v42 & 1) == 0 && (v42 & 0x200) == 0 && (v42 & 0x100) == 0 )
          {
            StorageTierForRange = 1024;
            if ( (v42 & 0x400) == 0
              && !*((_DWORD *)v10 + 21)
              && *((int *)v10 + 24) <= 0
              && (v42 & 8) == 0
              && !*((_BYTE *)v10 + 28) )
            {
              v43 = *((_DWORD *)v11 + 143);
              if ( (v43 & 1) == 0
                && (v43 & 0x200) == 0
                && (v43 & 0x400) == 0
                && !*((_DWORD *)v11 + 21)
                && *((int *)v11 + 24) <= 0
                && (v43 & 8) == 0
                && (v43 & 0x100) == 0 )
              {
                StorageTierForRange = *(_QWORD *)(a1 + 8);
                if ( !*(_QWORD *)(StorageTierForRange + 2888)
                  && (*(_DWORD *)(StorageTierForRange + 3116) & 0x800000) != 0
                  && (*((_BYTE *)v11 + 24) & 0x40) != 0
                  && *((_DWORD *)v11 + 153) )
                {
                  _InterlockedIncrement((volatile signed __int32 *)(StorageTierForRange + 956));
                  updated = -1073740759;
                  goto LABEL_250;
                }
                updated = CmsVolumeContainer::GetContainerReference(
                            (CmsVolumeContainer *)a1,
                            (struct CmsTransactionContext *)a2,
                            v165,
                            &v182,
                            0,
                            0,
                            0);
                if ( updated < 0 )
                  goto LABEL_252;
                *((_BYTE *)v10 + 24) |= 4u;
                v13 |= 0x800u;
                v44 = *(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228);
                v45 = *(_QWORD *)(a1 + 8);
                v171 = *((_DWORD *)v10 + 18);
                LODWORD(Size) = v44;
                if ( !*(_QWORD *)(v45 + 2888) )
                {
                  if ( *(_BYTE *)(*(_QWORD *)(v45 + 3056) + 16LL) )
                  {
                    memmove(v175, (char *)v10 + 632, v44);
                    v46 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 3056LL);
                    p_BitMapHeader = &BitMapHeader;
                    v195[0] = (__int64)&p_BitMapHeader;
                    v195[1] = (__int64)&v214;
                    updated = CmsAllocator::WalkAllocator__lambda_2620209cb2a5bbd199a311e9b14958f5___(
                                *(CmsAllocator **)(v46 + 8),
                                (struct CmsTransactionContext *)a2,
                                (__int64)v195);
                    if ( updated < 0 )
                      goto LABEL_252;
                  }
                }
                v150 = 0;
                ExReleasePushLockEx((char *)v10 + 104, 2);
                v151 = 0;
                ExReleasePushLockEx((char *)v11 + 104, 2);
                CmsVolume::CommitTopLevelAction(
                  *(CmsVolume **)(a1 + 8),
                  (struct CmsTransactionContext *)a2,
                  (struct _SmsTopLevelAction *)v206,
                  0);
                v149 = 0;
                while ( 1 )
                {
                  v47 = *(_QWORD *)(a1 + 8);
                  if ( *(_QWORD *)(v47 + 2888) )
                  {
                    if ( byte_1C0136968 )
                    {
                      if ( *((_QWORD *)v10 + 73) )
                      {
                        v217 = v215;
                        *(_QWORD *)&v217 = (_QWORD)v215 << *(_BYTE *)(v47 + 64);
                        *((_QWORD *)&v217 + 1) = *((_QWORD *)&v215 + 1) << *(_BYTE *)(v47 + 64);
                        StorageTierForRange = (int)CmsVolume::GetStorageTierForRange(v47, a2, &v217);
                        if ( *((_BYTE *)&CmsTierProperties::PropertyTable + 12 * StorageTierForRange + 9) )
                        {
                          updated = ((__int64 (__fastcall *)(_QWORD, __int128 *))qword_1C0136AA0)(
                                      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL),
                                      &v217);
                          if ( updated < 0 )
                            goto LABEL_252;
                        }
                      }
                    }
                  }
                  else if ( *((_QWORD *)v10 + 73) )
                  {
                    PerformanceFrequency = *(union _LARGE_INTEGER *)(v47 + 2888);
                    PerformanceCounter = KeQueryPerformanceCounter(0);
                    v48 = PerformanceCounter;
                    KeQueryPerformanceCounter(&PerformanceFrequency);
                    v49 = *(_QWORD *)(a1 + 8);
                    v50 = 0;
                    v174 = 0;
                    v51 = *(_DWORD *)(v49 + 64);
                    v52 = (_QWORD)v214 << v51;
                    v153 = 0;
                    v162 = (_QWORD)v214 << v51;
                    v181 = *((_QWORD *)&v214 + 1) << v51;
                    if ( *((_QWORD *)&v214 + 1) << v51 )
                    {
                      v53 = *((_QWORD *)&v214 + 1) << v51;
                      v179 = *((_QWORD *)&v214 + 1) << v51;
                      do
                      {
                        *(_QWORD *)&v174 = v52;
                        *((_QWORD *)&v174 + 1) = v53;
                        v161 = v53;
                        v180 = v53;
                        if ( v53 > (unsigned int)dword_1C0136964 )
                        {
                          v161 = v53;
                          v180 = v53;
                          if ( dword_1C0136964 )
                          {
                            v179 = (unsigned int)dword_1C0136964;
                            *((_QWORD *)&v174 + 1) = (unsigned int)dword_1C0136964;
                            v161 = (unsigned int)dword_1C0136964;
                            v180 = (unsigned int)dword_1C0136964;
                          }
                        }
                        v144 = (char *)v164 + v50;
                        updated = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))qword_1C0136A58)(
                                    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL),
                                    0,
                                    0);
                        if ( updated < 0 )
                          goto LABEL_252;
                        v50 = (unsigned int)(v179 + v153);
                        v52 = v180 + v162;
                        v153 += v179;
                        v181 -= v161;
                        v53 = v181;
                        v179 = v181;
                        v162 += v180;
                      }
                      while ( v181 );
                    }
                    v54 = KeQueryPerformanceCounter(0);
                    v55 = *(_QWORD *)(a1 + 8);
                    v204 = v54.QuadPart - v48.QuadPart;
                    v56 = 10000000 * (v54.QuadPart - v48.QuadPart);
                    if ( a5 == *(_DWORD *)(v55 + 3488) )
                    {
                      _InterlockedIncrement((volatile signed __int32 *)(v55 + 800));
                      v57 = (volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 796LL);
                    }
                    else
                    {
                      _InterlockedIncrement((volatile signed __int32 *)(v55 + 816));
                      v57 = (volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 812LL);
                    }
                    v59 = v56;
                    v58 = v56 % PerformanceFrequency.QuadPart;
                    _InterlockedExchangeAdd(v57, v59 / PerformanceFrequency.QuadPart);
                    v10 = v157;
                    v11 = v156;
                    if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 3056LL) + 16LL) )
                    {
                      v60 = v175;
                      updated = CmsVolumeContainer::ValidateContainerRotationBuffer(
                                  (CmsVolumeContainer *)a1,
                                  (struct CmsTransactionContext *)v58,
                                  v164,
                                  v175,
                                  &BitMapHeader);
                      if ( updated == -1073740688 )
                      {
                        v13 |= 0x1000u;
                        if ( (v13 & 0x400) == 0 )
                          goto LABEL_179;
                        v61 = CmsVolumeContainer::SmartIoReadAndRepair(
                                (CmsVolumeContainer *)a1,
                                (struct CmsTransactionContext *)a2,
                                v10,
                                v11,
                                (unsigned __int64)v139,
                                (unsigned __int64)v144,
                                v164,
                                v60,
                                &BitMapHeader,
                                (struct _SmsScrubIoOutput *)v145,
                                v146);
                        updated = v61;
                        if ( v61 >= 0 )
                        {
                          v13 &= ~0x1000u;
                        }
                        else if ( v61 == -1073740688 )
                        {
                          CmsVolumeContainer::SetContainerStationaryForChecksumMismatch(
                            (CmsVolumeContainer *)a1,
                            (struct CmsTransactionContext *)a2,
                            v165,
                            v62,
                            v140);
                          StorageTierForRange = *(unsigned int *)(*(_QWORD *)(a2 + 32) + 3116LL);
                          if ( (StorageTierForRange & 0x40) != 0 )
                          {
                            if ( (_BYTE)KdDebuggerEnabled )
                              __debugbreak();
                          }
                        }
                        if ( qword_1C0136BA0 )
                        {
                          v63 = ExAllocatePoolWithTag((POOL_TYPE)512, 0xC8u, 0x6950534Du);
                          v64 = v63;
                          if ( v63 )
                          {
                            *v63 = 8;
                            *((_QWORD *)v63 + 1) = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL);
                            v63[4] = updated;
                            *((_QWORD *)v63 + 3) = v214;
                            *((_BYTE *)v63 + 32) = a5 != *(_DWORD *)(*(_QWORD *)(a1 + 8) + 3488LL);
                            *((_BYTE *)v63 + 33) = (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 3116LL) & 0x40000000) != 0;
                            ((void (__fastcall *)(_DWORD *, _QWORD))qword_1C0136BA0)(v63, 0);
                            ExFreePoolWithTag(v64, 0);
                          }
                        }
                      }
                      if ( updated < 0 )
                      {
                        if ( updated == -1073740688 )
                          updated = -1073741267;
                        goto LABEL_252;
                      }
                    }
                    v65 = KeQueryPerformanceCounter(0);
                    v66 = *(_QWORD *)(a1 + 8);
                    v67 = v65;
                    v68 = dword_1C0136964;
                    v213 = v215;
                    PerformanceCounter = v65;
                    v170 = 0;
                    v69 = *(_BYTE *)(v66 + 64);
                    v183 = 0;
                    v177 = 0;
                    *(_QWORD *)&v213 = (_QWORD)v215 << v69;
                    *((_QWORD *)&v213 + 1) = *((_QWORD *)&v215 + 1) << *(_BYTE *)(v66 + 64);
                    v154 = dword_1C0136964;
                    if ( (*((_BYTE *)&CmsTierProperties::PropertyTable
                          + 12 * (int)CmsVolume::GetStorageTierForRange(v66, a2, &v213)
                          + 5)
                       || byte_1C0136992)
                      && !byte_1C0136968 )
                    {
                      LODWORD(v144) = 0;
                      ((void (__fastcall *)(_QWORD, _QWORD, __int64, __int128 *, char *))qword_1C0136B40)(
                        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL),
                        0,
                        1,
                        &v213,
                        (char *)&v213 + 8);
                    }
                    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 3116LL) & 0x800000) != 0 )
                    {
                      v205 = v213;
                      updated = MsAcquireContainerWriteHead(a2, &v205, &v183, &v177);
                      if ( updated < 0 )
                        goto LABEL_252;
                      v68 = v154;
                    }
                    v70 = CmsVolume::GetStorageTierForRange(*(_QWORD *)(a1 + 8), a2, &v213);
                    StorageTierForRange = (unsigned __int64)&CmsTierProperties::PropertyTable;
                    if ( *((_BYTE *)&CmsTierProperties::PropertyTable + 12 * v70 + 9) && v68 )
                    {
                      v71 = *(_QWORD *)(a1 + 8);
                      v169 = 0;
                      updated = ((__int64 (__fastcall *)(_QWORD, _QWORD, unsigned int *, unsigned int *))qword_1C0136AA8)(
                                  *(_QWORD *)(v71 + 48),
                                  v213,
                                  &v169,
                                  &v170);
                      if ( updated < 0 )
                        goto LABEL_252;
                      StorageTierForRange = v169;
                      v68 = v169 * ((v169 + v154 - 1) / v169);
                      v154 = v68;
                    }
                    v72 = 0;
                    v161 = 0;
                    if ( v68 && (StorageTierForRange = v170) != 0 )
                    {
                      v144 = (char *)v164;
                      v73 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL);
                      v161 = v68 - v170;
                      *((_QWORD *)&v174 + 1) = v161;
                      *(_QWORD *)&v174 = v213;
                      updated = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD))qword_1C0136A60)(v73, 0, 0);
                      if ( updated < 0 )
                        goto LABEL_252;
                      v72 = v161;
                      *(_QWORD *)&v213 = v161 + v213;
                      v68 = v154;
                      v74 = *((_QWORD *)&v213 + 1) - v161;
                      *((_QWORD *)&v213 + 1) -= v161;
                    }
                    else
                    {
                      v74 = *((_QWORD *)&v213 + 1);
                    }
                    if ( v74 )
                    {
                      StorageTierForRange = v68;
                      do
                      {
                        v174 = v213;
                        if ( v74 > StorageTierForRange )
                        {
                          v75 = *((_QWORD *)&v174 + 1);
                          if ( v68 )
                            v75 = StorageTierForRange;
                          *((_QWORD *)&v174 + 1) = v75;
                        }
                        v144 = (char *)v164 + v72;
                        updated = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))qword_1C0136A60)(
                                    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL),
                                    0,
                                    0,
                                    v174,
                                    DWORD2(v174));
                        if ( updated < 0 )
                          goto LABEL_252;
                        v74 = *((_QWORD *)&v213 + 1) - *((_QWORD *)&v174 + 1);
                        *(_QWORD *)&v213 = *((_QWORD *)&v174 + 1) + v213;
                        v72 = DWORD2(v174) + v161;
                        v68 = v154;
                        *((_QWORD *)&v213 + 1) = v74;
                        StorageTierForRange = v154;
                        v161 = (unsigned int)(DWORD2(v174) + v161);
                      }
                      while ( v74 );
                    }
                    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 3116LL) & 0x800000) != 0 && v183 )
                      MsReleaseContainerWriteHead(StorageTierForRange, v183, v177);
                    if ( !byte_1C0136968 )
                    {
                      updated = ((__int64 (__fastcall *)(_QWORD))qword_1C0136AB0)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL));
                      if ( updated < 0 )
                        goto LABEL_252;
                    }
                    v76 = KeQueryPerformanceCounter(0);
                    v77 = *(_QWORD *)(a1 + 8);
                    v78 = 10000000 * (v76.QuadPart - v67.QuadPart);
                    if ( a5 == *(_DWORD *)(v77 + 3488) )
                    {
                      _InterlockedIncrement((volatile signed __int32 *)(v77 + 808));
                      StorageTierForRange = *(_QWORD *)(a1 + 8) + 804LL;
                    }
                    else
                    {
                      _InterlockedIncrement((volatile signed __int32 *)(v77 + 824));
                      StorageTierForRange = *(_QWORD *)(a1 + 8) + 820LL;
                    }
                    _InterlockedExchangeAdd(
                      (volatile signed __int32 *)StorageTierForRange,
                      v78 / PerformanceFrequency.QuadPart);
                    v10 = v157;
                    v11 = v156;
                  }
                  if ( (v13 & 0x400) != 0 )
                    goto LABEL_229;
LABEL_179:
                  CmsVolume::BeginTopLevelAction(
                    (CmsVolume *)StorageTierForRange,
                    (struct CmsTransactionContext *)a2,
                    (struct _SmsTopLevelAction *)v206,
                    0,
                    1);
                  v149 = 1;
                  v79 = (struct _IO_REMOVE_LOCK *)(a1 + 328);
                  if ( (v13 & 1) != 0 )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)v10 + 22);
                    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 328), 0, 0x20u);
                    --*(_DWORD *)(a2 + 2824);
                    v79 = (struct _IO_REMOVE_LOCK *)(a1 + 328);
                    v11 = v156;
                    v10 = 0;
                    v157 = 0;
                    v13 &= ~1u;
                  }
                  if ( (v13 & 2) != 0 )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)v11 + 22);
                    IoReleaseRemoveLockEx(v79, 0, 0x20u);
                    --*(_DWORD *)(a2 + 2824);
                    v11 = 0;
                    v10 = v157;
                    v13 &= ~2u;
                    v156 = 0;
                  }
                  v80 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 3032LL) + 16LL);
                  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v80 + 64LL))(v80, a2, 0);
                  v162 = v176;
                  v148 = 0;
                  updated = 0;
                  v83 = 10;
                  if ( v10 )
                  {
                    while ( 1 )
                    {
LABEL_186:
                      if ( CmsVolumeContainer::TryLockContainerExclusive(v82, v81, v10) )
                      {
                        v148 = 1;
                        if ( !v11 )
                        {
                          v86 = CmsVolumeContainer::GetContainerReference(
                                  (CmsVolumeContainer *)a1,
                                  (struct CmsTransactionContext *)a2,
                                  v162,
                                  &v156,
                                  0,
                                  0,
                                  0);
                          v11 = v156;
                          updated = v86;
                          if ( v86 < 0 )
                            goto LABEL_195;
                          CmsVolumeContainer::IncrementExclusiveAcquirersCount(
                            (CmsVolumeContainer *)StorageTierForRange,
                            v156);
                        }
                        if ( CmsVolumeContainer::TryLockContainerExclusive(
                               (CmsVolumeContainer *)StorageTierForRange,
                               v85,
                               v11) )
                        {
                          v88 = 1;
                          goto LABEL_198;
                        }
                      }
                      if ( v148 )
                      {
                        ExReleasePushLockEx((char *)v10 + 104, 2);
                        v148 = 0;
                      }
                      if ( !v83-- )
                        break;
                      MsDelayExecutionThread(50);
                    }
                    v88 = 0;
                    updated = -1073741267;
                  }
                  else
                  {
                    v84 = CmsVolumeContainer::GetContainerReference(
                            (CmsVolumeContainer *)a1,
                            (struct CmsTransactionContext *)a2,
                            v165,
                            &v157,
                            0,
                            0,
                            0);
                    v10 = v157;
                    updated = v84;
                    if ( v84 >= 0 )
                    {
                      CmsVolumeContainer::IncrementExclusiveAcquirersCount(
                        (CmsVolumeContainer *)StorageTierForRange,
                        v157);
                      goto LABEL_186;
                    }
LABEL_195:
                    v88 = 0;
                  }
LABEL_198:
                  if ( v10 )
                    CmsVolumeContainer::DecrementExclusiveAcquirersCount((CmsVolumeContainer *)StorageTierForRange, v10);
                  if ( v11 )
                    CmsVolumeContainer::DecrementExclusiveAcquirersCount((CmsVolumeContainer *)StorageTierForRange, v11);
                  if ( updated < 0 )
                  {
                    if ( v148 )
                      ExReleasePushLockEx((char *)v10 + 104, 2);
                    if ( v88 )
                      ExReleasePushLockEx((char *)v11 + 104, 2);
                    if ( v10 )
                    {
                      _InterlockedDecrement((volatile signed __int32 *)v10 + 22);
                      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 328), 0, 0x20u);
                      --*(_DWORD *)(a2 + 2824);
                      v11 = v156;
                      v10 = 0;
                      v157 = 0;
                    }
                    if ( v11 )
                    {
                      _InterlockedDecrement((volatile signed __int32 *)v11 + 22);
                      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 328), 0, 0x20u);
                      --*(_DWORD *)(a2 + 2824);
                      v10 = v157;
                      v11 = 0;
                      v156 = 0;
                    }
                    goto LABEL_252;
                  }
                  v89 = *((_DWORD *)v10 + 143);
                  v13 |= 3u;
                  v151 = 1;
                  v150 = 1;
                  if ( (v89 & 1) != 0 )
                    goto LABEL_248;
                  StorageTierForRange = 512;
                  if ( (v89 & 0x200) != 0 )
                    goto LABEL_248;
                  if ( (v89 & 0x100) != 0 )
                    goto LABEL_248;
                  if ( *((_DWORD *)v10 + 21) )
                    goto LABEL_248;
                  if ( (v89 & 8) != 0 )
                    goto LABEL_248;
                  v90 = *((_DWORD *)v11 + 143);
                  if ( (v90 & 1) != 0
                    || (v90 & 0x200) != 0
                    || *((_DWORD *)v11 + 21)
                    || (v90 & 8) != 0
                    || (v90 & 0x100) != 0 )
                  {
                    goto LABEL_248;
                  }
                  if ( *((_DWORD *)v10 + 18) == v171 && (v13 & 0x1000) == 0 )
                  {
LABEL_229:
                    v93 = *(unsigned int **)(a1 + 8);
                    v162 = (unsigned __int64)v10 + 24;
                    v141 = (*((unsigned __int8 *)v10 + 24) >> 3) & 8;
                    *(_QWORD *)&v216 = v93[20];
                    updated = CmsVolume::ReserveForFailableOperation(
                                (CmsVolume *)v93,
                                (struct CmsTransactionContext *)a2,
                                v216,
                                (struct SmsReservationUndoRecord *)&v216,
                                v141);
                    if ( updated >= 0 )
                    {
                      v94 = v159;
                      updated = CmsContainerRangeMap::AddRange(
                                  v168,
                                  (struct CmsTransactionContext *)a2,
                                  v159,
                                  0,
                                  0,
                                  0,
                                  0,
                                  0,
                                  0,
                                  0);
                      if ( updated >= 0 )
                      {
                        CmsAllocator::MoveBitmapAndSwapState(
                          *(CmsAllocator **)(*(_QWORD *)(a1 + 8) + 3032LL),
                          (struct CmsTransactionContext *)a2,
                          v94,
                          v163);
                        LOWORD(v13) = v13 | 0x100;
                        v95 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 3056LL);
                        if ( *(_BYTE *)(v95 + 16) )
                        {
                          CmsAllocator::MoveBitmapAndSwapState(
                            *(CmsAllocator **)(v95 + 8),
                            (struct CmsTransactionContext *)a2,
                            v167,
                            v173);
                          LOWORD(v13) = v13 | 0x200;
                        }
                        if ( (*(_QWORD *)(a2 + 16) & 0x2000000000LL) != 0 )
                          goto LABEL_308;
                        v96 = *(_QWORD *)(a1 + 16);
                        v201 = &v214;
                        v200 = 16;
                        v203 = &v215;
                        v193[1] = &v165;
                        v192[1] = &v176;
                        v202 = 16;
                        v193[0] = 8;
                        v192[0] = 8;
                        updated = CmsTransactionContext::AddRedoRecord(a2, v96, 20, v193, v192, &v200, 2);
                        if ( updated >= 0 )
                        {
LABEL_308:
                          v97 = CmsTransactionContext::PopRow((CmsTransactionContext *)a2);
                          v166 = v97;
                          LOWORD(v13) = v13 | 0x80;
                          v155 = *(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228) + 96;
                          updated = CmsRowWithBuffer::NewLength(v97, 0, v155, 0x10u, v98);
                          if ( updated >= 0 )
                          {
                            v99 = (char *)*((_QWORD *)v97 + 3);
                            if ( *((_QWORD *)v10 + 69) >= *((_QWORD *)v11 + 69) )
                            {
                              memmove(v99, (char *)v11 + 552, v155);
                              v102 = v166;
                              *(_OWORD *)&v99[*(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228) + 80] = v214;
                              updated = CmsTable::UpdateRow(
                                          *(CmsTable **)(a1 + 16),
                                          (struct CmsTransactionContext *)a2,
                                          v102,
                                          &v160,
                                          (struct _SmsQuickIndex *)v142);
                              if ( updated < 0 )
                                goto LABEL_252;
                              memmove(v99, (char *)v10 + 552, v155);
                              v101 = v215;
                            }
                            else
                            {
                              memmove(v99, (char *)v10 + 552, v155);
                              v100 = v166;
                              *(_OWORD *)&v99[*(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228) + 80] = v215;
                              updated = CmsTable::UpdateRow(
                                          *(CmsTable **)(a1 + 16),
                                          (struct CmsTransactionContext *)a2,
                                          v100,
                                          &v160,
                                          (struct _SmsQuickIndex *)v142);
                              if ( updated < 0 )
                                goto LABEL_252;
                              memmove(v99, (char *)v11 + 552, v155);
                              v101 = v214;
                            }
                            v103 = v166;
                            *(_OWORD *)&v99[*(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228) + 80] = v101;
                            updated = CmsTable::UpdateRow(
                                        *(CmsTable **)(a1 + 16),
                                        (struct CmsTransactionContext *)a2,
                                        v103,
                                        &v160,
                                        (struct _SmsQuickIndex *)v143);
                            if ( updated >= 0 )
                            {
                              ExAcquirePushLockExclusiveEx(a1 + 40, 0);
                              *(_OWORD *)((char *)v10
                                        + (unsigned int)(*(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228))
                                        + 632) = v215;
                              *(_OWORD *)((char *)v11
                                        + (unsigned int)(*(_DWORD *)(a1 + 232) * *(_DWORD *)(a1 + 228))
                                        + 632) = v214;
                              *(_QWORD *)(*(_QWORD *)(a1 + 32)
                                        + 8 * ((unsigned __int64)v214 >> *(_DWORD *)(*(_QWORD *)(a1 + 8) + 76LL))) = v176;
                              *(_QWORD *)(*(_QWORD *)(a1 + 32)
                                        + 8 * ((unsigned __int64)v215 >> *(_DWORD *)(*(_QWORD *)(a1 + 8) + 76LL))) = v165;
                              ExReleasePushLockEx(a1 + 40, 0);
                              if ( !*(_QWORD *)(*(_QWORD *)(a2 + 32) + 2888LL) )
                              {
                                v104 = v163;
                                v105 = *((_QWORD *)v104 + 1) - SmsAllocationRegionEx::GetTotalFree(v163);
                                v106 = v159;
                                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 3064LL) + 3368LL) = v105;
                                StorageTierForRange = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 3064LL);
                                *(_BYTE *)(StorageTierForRange + 3401) = (*((_BYTE *)v106 + 24) & 4) != 0;
                              }
                              v107 = (char *)v11 + 24;
                              v108 = *((_BYTE *)v11 + 24);
                              if ( (v108 & 0x40) != 0 )
                              {
                                StorageTierForRange = _InterlockedExchangeAdd64(
                                                        (volatile signed __int64 *)(*(_QWORD *)(a1 + 8) + 3400LL),
                                                        (unsigned int)-*(_DWORD *)(*(_QWORD *)(a1 + 8) + 80LL));
                                _InterlockedDecrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 8) + 3384LL));
                                v108 = *v107;
                                v10 = v157;
                                v11 = v156;
                              }
                              v110 = *(_BYTE *)v162 ^ (v108 ^ *(_BYTE *)v162) & 0x40;
                              v158 = (*(_BYTE *)v162 & 0x40) != 0;
                              v109 = v158;
                              *(_BYTE *)v162 = v110;
                              LOBYTE(StorageTierForRange) = *v107 & 0xBF | (v109 << 6);
                              *v107 = StorageTierForRange;
                            }
                          }
                        }
                      }
                    }
                    goto LABEL_252;
                  }
                  v13 = v13 & 0xFFFFEBFF | 0x400;
                  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 952LL));
                  v91 = *((_DWORD *)v10 + 18);
                  v10 = v157;
                  v171 = v91;
                  StorageTierForRange = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 3056LL);
                  if ( *(_BYTE *)(StorageTierForRange + 16) )
                  {
                    memmove(v175, (char *)v157 + 632, (unsigned int)Size);
                    v92 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 3056LL);
                    v189 = &BitMapHeader;
                    v196[0] = (__int64)&v189;
                    v196[1] = (__int64)&v214;
                    updated = CmsAllocator::WalkAllocator__lambda_2620209cb2a5bbd199a311e9b14958f5___(
                                *(CmsAllocator **)(v92 + 8),
                                (struct CmsTransactionContext *)a2,
                                (__int64)v196);
                    if ( updated < 0 )
                      goto LABEL_251;
                  }
                  v11 = v156;
                }
              }
              goto LABEL_247;
            }
          }
LABEL_248:
          updated = -1073741267;
          goto LABEL_249;
        }
      }
    }
  }
LABEL_252:
  if ( (v13 & 0x80u) != 0 )
  {
    v111 = (int)v166;
    *(_DWORD *)v166 = 0;
    v112 = ((unsigned int)(v111 - a2 - 2888) * (unsigned __int128)0x2492492492492493uLL) >> 64;
    StorageTierForRange = (v112 + (((unsigned __int64)(unsigned int)(v111 - a2 - 2888) - v112) >> 1)) >> 6;
    *(_DWORD *)(a2 + 2836) &= ~(1 << StorageTierForRange);
    LOWORD(v13) = v13 & 0xFF7F;
  }
  if ( (v13 & 0x800) != 0 )
  {
    v113 = v182;
    *((_BYTE *)v182 + 24) &= ~4u;
    _InterlockedDecrement((volatile signed __int32 *)v113 + 22);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 328), 0, 0x20u);
    --*(_DWORD *)(a2 + 2824);
    v10 = v157;
    v11 = v156;
  }
  if ( updated < 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 964LL));
    v198 = 0;
    v199 = 0;
    if ( (v13 & 0x100) != 0 )
    {
      v124 = v163;
      RtlInitializeBitMap(&v198, *((PULONG *)v163 + 6), *((_DWORD *)v163 + 2));
      RtlClearAllBits(&v198);
      CmsAllocator::SwapBitmapRegionStates(
        *(CmsAllocator **)(*(_QWORD *)(a1 + 8) + 3032LL),
        (struct CmsTransactionContext *)a2,
        v159,
        v124);
    }
    if ( (v13 & 0x200) != 0 )
    {
      v125 = v173;
      RtlInitializeBitMap(&v199, *((PULONG *)v173 + 6), *((_DWORD *)v173 + 2));
      RtlClearAllBits(&v199);
      CmsAllocator::SwapBitmapRegionStates(
        *(CmsAllocator **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 3056LL) + 8LL),
        (struct CmsTransactionContext *)a2,
        v167,
        v125);
    }
    v11 = v156;
    v10 = v157;
  }
  else
  {
    v197 = 0;
    v194 = 0;
    RtlInitializeBitMap(&v197, *((PULONG *)v159 + 6), *((_DWORD *)v159 + 2));
    v114 = *(_QWORD *)(a1 + 8);
    v115 = v114;
    if ( *(_BYTE *)(*(_QWORD *)(v114 + 3056) + 16LL) )
    {
      RtlInitializeBitMap(&v194, *((PULONG *)v167 + 6), *((_DWORD *)v167 + 2));
      RtlClearAllBits(&v194);
      v114 = *(_QWORD *)(a1 + 8);
      v115 = v114;
    }
    if ( !v158 )
    {
      v116 = v114 + 1776;
      ExAcquirePushLockExclusiveEx(v114 + 3264, 0);
      CmsVolume::DeleteFromRecentlyDeallocatedOrTrim(
        *(CmsVolume **)(a1 + 8),
        v159,
        *(struct CmsAllocator **)(*(_QWORD *)(a1 + 8) + 3032LL));
      RtlSetAllBits(&v197);
      ExReleasePushLockEx(*(_QWORD *)(a1 + 8) + 3264LL, 0);
      CmsVolume::MergeIntoRecentlyDeallocated(*(CmsVolume **)(a1 + 8), (struct _SmsCheckpointState *)v116, v117, v168);
      v118 = ExAcquireAutoExpandPushLockShared(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 3424LL), 0);
      _InterlockedExchangeAdd64((volatile signed __int64 *)(v116 + 24), *((_QWORD *)v159 + 1));
      _InterlockedIncrement((volatile signed __int32 *)(v116 + 56));
      ExReleaseAutoExpandPushLockShared(v118, 0);
      v114 = *(_QWORD *)(a1 + 8);
      v10 = v157;
      v115 = v114;
      v11 = v156;
    }
    v162 = (unsigned __int64)v159;
    if ( (*((_BYTE *)v159 + 24) & 4) != 0
      && (unsigned int)CmsVolume::GetStorageTierForRange(v114, a2, v163) == *(_DWORD *)(v115 + 3488) )
    {
      v119 = *((_QWORD *)v11 + 69);
      if ( !*(_QWORD *)(v115 + 2888) )
      {
        v120 = *(_DWORD *)(a1 + 180);
        v121 = 0;
        if ( v120 )
        {
          v122 = *(_QWORD *)(a1 + 312);
          while ( v119 != *(_QWORD *)(v122 + 8LL * v121) )
          {
            if ( ++v121 >= v120 )
              goto LABEL_270;
          }
          _InterlockedCompareExchange64((volatile signed __int64 *)(v122 + 8LL * v121), 0, v119);
          v10 = v157;
          v11 = v156;
        }
      }
    }
LABEL_270:
    if ( (*(_BYTE *)(v162 + 24) & 4) != 0
      && (unsigned int)CmsVolume::GetStorageTierForRange(*(_QWORD *)(a1 + 8), a2, v159) == *(_DWORD *)(*(_QWORD *)(a1 + 8) + 3488LL) )
    {
      CmsVolumeContainer::AddContainerIdToReservedContainersOnFastTierList(
        (CmsVolumeContainer *)a1,
        *((_QWORD *)v11 + 69));
    }
    v123 = ExAcquireAutoExpandPushLockShared(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 3424LL), 0);
    CmsVolume::ProcessReservationUndo(*(CmsVolume **)(a1 + 8), &v216);
    ExReleaseAutoExpandPushLockShared(v123, 0);
  }
  if ( (v13 & 4) != 0 )
  {
    v126 = *((_OWORD *)v159 + 1);
    v185 = *(_OWORD *)v159;
    v127 = *((_OWORD *)v159 + 2);
    v186 = v126;
    *(_QWORD *)&v126 = *((_QWORD *)v159 + 6);
    v187 = v127;
    v188 = v126;
    CmsAllocator::TryProtectRegion((CmsAllocator *)StorageTierForRange, v159, 0);
  }
  if ( (v13 & 8) != 0 )
  {
    v128 = *((_OWORD *)v163 + 1);
    v185 = *(_OWORD *)v163;
    v129 = *((_OWORD *)v163 + 2);
    v186 = v128;
    *(_QWORD *)&v128 = *((_QWORD *)v163 + 6);
    v187 = v129;
    v188 = v128;
    CmsAllocator::TryProtectRegion((CmsAllocator *)StorageTierForRange, v163, 0);
  }
  if ( (v13 & 0x10) != 0 )
  {
    v130 = *((_OWORD *)v167 + 1);
    v185 = *(_OWORD *)v167;
    v131 = *((_OWORD *)v167 + 2);
    v186 = v130;
    *(_QWORD *)&v130 = *((_QWORD *)v167 + 6);
    v187 = v131;
    v188 = v130;
    CmsAllocator::TryProtectRegion((CmsAllocator *)StorageTierForRange, v167, 0);
  }
  if ( (v13 & 0x20) != 0 )
  {
    v132 = *((_OWORD *)v173 + 1);
    v185 = *(_OWORD *)v173;
    v133 = *((_OWORD *)v173 + 2);
    v186 = v132;
    *(_QWORD *)&v132 = *((_QWORD *)v173 + 6);
    v187 = v133;
    v188 = v132;
    CmsAllocator::TryProtectRegion((CmsAllocator *)StorageTierForRange, v173, 0);
  }
  if ( v149 )
  {
    v134 = *(CmsVolume **)(a1 + 8);
    if ( updated < 0 )
      CmsVolume::AbortTopLevelAction(v134, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v206);
    else
      CmsVolume::CommitTopLevelAction(v134, (struct CmsTransactionContext *)a2, (struct _SmsTopLevelAction *)v206, 1u);
  }
  if ( DWORD2(v216) )
  {
    v135 = ExAcquireAutoExpandPushLockShared(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 3424LL), 0);
    CmsVolume::ProcessReservationUndo(*(CmsVolume **)(a2 + 32), &v216);
    ExReleaseAutoExpandPushLockShared(v135, 0);
  }
  if ( (v13 & 0x40) != 0 )
    *(_QWORD *)(a2 + 16) &= ~0x800000000uLL;
  if ( v150 )
    ExReleasePushLockEx((char *)v10 + 104, 2);
  if ( v151 )
    ExReleasePushLockEx((char *)v11 + 104, 2);
  if ( (v13 & 1) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v10 + 22);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 328), 0, 0x20u);
    --*(_DWORD *)(a2 + 2824);
    v11 = v156;
  }
  if ( (v13 & 2) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v11 + 22);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 328), 0, 0x20u);
    --*(_DWORD *)(a2 + 2824);
  }
  v136 = v168;
  if ( v168 )
  {
    CmsContainerRangeMap::DeleteAll(v168);
    CmsContainerRangeMap::`scalar deleting destructor'(v136, v137);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1c00da6c4  push    rbp
0x1c00da6c6  push    rbx
0x1c00da6c7  push    rsi
0x1c00da6c8  push    rdi
0x1c00da6c9  push    r12
0x1c00da6cb  push    r13
0x1c00da6cd  push    r14
0x1c00da6cf  push    r15
0x1c00da6d1  lea     rbp, [rsp-258h]
0x1c00da6d9  sub     rsp, 358h
0x1c00da6e0  mov     rax, cs:__security_cookie
0x1c00da6e7  xor     rax, rsp
0x1c00da6ea  mov     [rbp+290h+var_50], rax
0x1c00da6f1  movsxd  rdi, [rbp+290h+arg_30]
0x1c00da6f8  xor     r10d, r10d
0x1c00da6fb  xorps   xmm0, xmm0
0x1c00da6fe  mov     [rbp+290h+var_2D8], r8
0x1c00da702  xor     eax, eax
0x1c00da704  mov     [rbp+290h+var_278], r9
0x1c00da708  xorps   xmm1, xmm1
0x1c00da70b  mov     [rbp+290h+var_D0], rax
0x1c00da712  mov     eax, [rcx+70h]
0x1c00da715  mov     r12, rdx
0x1c00da718  mov     [rsp+390h+var_318], r10
0x1c00da71d  mov     r14, rcx
0x1c00da720  mov     [rsp+390h+var_320], r10
0x1c00da725  mov     r13d, r10d
0x1c00da728  mov     [rbp+290h+var_248], r10
0x1c00da72c  mov     r15d, r10d
0x1c00da72f  movdqa  [rbp+290h+var_100], xmm0
0x1c00da737  mov     [rbp+290h+var_F0], r10
0x1c00da73e  mov     [rbp+290h+var_E8], r10d
0x1c00da745  mov     [rbp+290h+var_B0], r10d
0x1c00da74c  mov     [rbp+290h+var_2C0], r10
0x1c00da750  mov     [rbp+290h+var_308], r10
0x1c00da754  mov     [rbp+290h+var_2E8], r10
0x1c00da758  mov     [rbp+290h+var_2C8], r10
0x1c00da75c  mov     [rbp+290h+var_2A0], r10
0x1c00da760  mov     [rsp+390h+var_32E], r10b
0x1c00da765  mov     [rsp+390h+var_32D], r10b
0x1c00da76a  mov     [rsp+390h+var_32C], r10b
0x1c00da76f  mov     [rbp+290h+var_310], r10b
0x1c00da773  mov     [rbp+290h+var_2D0], r10
0x1c00da777  mov     [rbp+290h+var_300], r10d
0x1c00da77b  movups  [rbp+290h+var_90], xmm0
0x1c00da782  movups  [rbp+290h+var_80], xmm1
0x1c00da789  movups  [rbp+290h+var_E0], xmm1
0x1c00da790  movups  [rbp+290h+var_70], xmm0
0x1c00da797  movups  xmmword ptr [rbp+290h+BitMapHeader.SizeOfBitMap], xmm0
0x1c00da79b  test    al, 1
0x1c00da79d  jnz     short loc_1C00DA7A9
0x1c00da79f  mov     esi, 0C00000BBh
0x1c00da7a4  jmp     loc_1C00DC59E
0x1c00da7a9  mov     sil, [rbp+290h+arg_28]
0x1c00da7b0  mov     ebx, r10d
0x1c00da7b3  test    sil, sil
0x1c00da7b6  jnz     short loc_1C00DA80E
0x1c00da7b8  cmp     [rcx+0D0h], r10
0x1c00da7bf  jnz     short loc_1C00DA805
0x1c00da7c1  mov     rcx, [rcx+8]
0x1c00da7c5  cmp     [rcx+0B48h], r10
0x1c00da7cc  jnz     short loc_1C00DA805
0x1c00da7ce  mov     edx, [rcx+50h]
0x1c00da7d1  mov     r8d, 6F72534Dh; Tag
0x1c00da7d7  imul    edx, [rcx+44h]; NumberOfBytes
0x1c00da7db  mov     ecx, 200h; PoolType
0x1c00da7e0  call    cs:__imp_ExAllocatePoolWithTag
0x1c00da7e7  nop     dword ptr [rax+rax+00h]
0x1c00da7ec  xor     r10d, r10d
0x1c00da7ef  mov     [r14+0D0h], rax
0x1c00da7f6  test    rax, rax
0x1c00da7f9  jnz     short loc_1C00DA805
0x1c00da7fb  mov     esi, 0C000009Ah
0x1c00da800  jmp     loc_1C00DC001
0x1c00da805  mov     rax, [r14+0D0h]
0x1c00da80c  jmp     short loc_1C00DA819
0x1c00da80e  mov     rax, [rcx+0D8h]
0x1c00da815  mov     rax, [rax+rdi*8]
0x1c00da819  mov     [rbp+290h+var_2E0], rax
0x1c00da81d  test    sil, sil
0x1c00da820  jnz     short loc_1C00DA876
0x1c00da822  cmp     [r14+0F0h], r10
0x1c00da829  jnz     short loc_1C00DA86D
0x1c00da82b  mov     rax, [r14+8]
0x1c00da82f  cmp     [rax+0B48h], r10
0x1c00da836  jnz     short loc_1C00DA86D
0x1c00da838  mov     edx, [r14+0E8h]
0x1c00da83f  mov     ecx, 200h; PoolType
0x1c00da844  imul    edx, [r14+0E4h]; NumberOfBytes
0x1c00da84c  mov     r8d, 6372534Dh; Tag
0x1c00da852  call    cs:__imp_ExAllocatePoolWithTag
0x1c00da859  nop     dword ptr [rax+rax+00h]
0x1c00da85e  xor     r10d, r10d
0x1c00da861  mov     [r14+0F0h], rax
0x1c00da868  test    rax, rax
0x1c00da86b  jz      short loc_1C00DA7FB
0x1c00da86d  mov     rax, [r14+0F0h]
0x1c00da874  jmp     short loc_1C00DA881
0x1c00da876  mov     rax, [r14+0F8h]
0x1c00da87d  mov     rax, [rax+rdi*8]
0x1c00da881  mov     [rbp+290h+var_280], rax
0x1c00da885  test    sil, sil
0x1c00da888  jnz     short loc_1C00DA8EA
0x1c00da88a  cmp     [r14+108h], r10
0x1c00da891  jnz     short loc_1C00DA8EA
0x1c00da893  mov     rax, [r14+8]
0x1c00da897  cmp     [rax+0B48h], r10
0x1c00da89e  jnz     short loc_1C00DA8EA
0x1c00da8a0  mov     edx, [rax+50h]
0x1c00da8a3  mov     ecx, 200h; PoolType
0x1c00da8a8  shr     edx, 3; NumberOfBytes
0x1c00da8ab  mov     r8d, 6972534Dh; Tag
0x1c00da8b1  call    cs:__imp_ExAllocatePoolWithTag
0x1c00da8b8  nop     dword ptr [rax+rax+00h]
0x1c00da8bd  xor     r10d, r10d
0x1c00da8c0  mov     rdx, rax; BitMapBuffer
0x1c00da8c3  test    rax, rax
0x1c00da8c6  jz      loc_1C00DA7FB
0x1c00da8cc  mov     rax, [r14+8]
0x1c00da8d0  lea     rcx, [r14+100h]; BitMapHeader
0x1c00da8d7  mov     r8d, [rax+50h]; SizeOfBitMap
0x1c00da8db  call    cs:__imp_RtlInitializeBitMap
0x1c00da8e2  nop     dword ptr [rax+rax+00h]
0x1c00da8e7  xor     r10d, r10d
0x1c00da8ea  mov     rax, [r14+8]
0x1c00da8ee  cmp     [rax+0B48h], r10
0x1c00da8f5  jnz     short loc_1C00DA928
0x1c00da8f7  mov     r8d, [rax+50h]; SizeOfBitMap
0x1c00da8fb  test    sil, sil
0x1c00da8fe  jz      short loc_1C00DA911
0x1c00da900  mov     rax, [r14+110h]
0x1c00da907  add     rdi, rdi
0x1c00da90a  mov     rdx, [rax+rdi*8+8]
0x1c00da90f  jmp     short loc_1C00DA918
0x1c00da911  mov     rdx, [r14+108h]; BitMapBuffer
0x1c00da918  lea     rcx, [rbp+290h+BitMapHeader]; BitMapHeader
0x1c00da91c  call    cs:__imp_RtlInitializeBitMap
0x1c00da923  nop     dword ptr [rax+rax+00h]
0x1c00da928  mov     edx, 40h ; '@'; NumberOfBytes
0x1c00da92d  mov     ecx, 200h; PoolType
0x1c00da932  mov     r8d, 6950534Dh; Tag
0x1c00da938  call    cs:__imp_ExAllocatePoolWithTag
0x1c00da93f  nop     dword ptr [rax+rax+00h]
0x1c00da944  xor     r10d, r10d
0x1c00da947  mov     [rbp+290h+var_2C0], rax
0x1c00da94b  mov     rdi, rax
0x1c00da94e  test    rax, rax
0x1c00da951  jz      short loc_1C00DA97F
0x1c00da953  mov     rax, [r14+8]
0x1c00da957  xorps   xmm0, xmm0
0x1c00da95a  mov     cl, [rax+4Ch]
0x1c00da95d  movups  xmmword ptr [rdi+8], xmm0
0x1c00da961  movups  xmmword ptr [rdi+18h], xmm0
0x1c00da965  mov     [rdi], r10
0x1c00da968  mov     [rdi+3Ch], cl
0x1c00da96b  mov     [rdi+38h], r10d
0x1c00da96f  mov     word ptr [rdi+3Dh], 1
0x1c00da975  mov     [rdi+28h], r10
0x1c00da979  mov     [rdi+30h], r10
0x1c00da97d  jmp     short loc_1C00DA986
0x1c00da97f  mov     rdi, r10
0x1c00da982  mov     [rbp+290h+var_2C0], r10
0x1c00da986  test    rdi, rdi
0x1c00da989  jz      loc_1C00DA7FB
0x1c00da98f  mov     rcx, rdi; this
0x1c00da992  call    ?InitializeMapIfRequired@CmsContainerRangeMap@@AEAAJXZ; CmsContainerRangeMap::InitializeMapIfRequired(void)
0x1c00da997  mov     esi, eax
0x1c00da999  test    eax, eax
0x1c00da99b  jns     short loc_1C00DA9B1
0x1c00da99d  mov     rcx, rdi; this
0x1c00da9a0  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x1c00da9a5  xor     r10d, r10d
0x1c00da9a8  mov     [rbp+290h+var_2C0], r10
0x1c00da9ac  jmp     loc_1C00DC001
0x1c00da9b1  xor     esi, esi
0x1c00da9b3  lea     r8, [rbp+290h+var_120]; struct _SmsTopLevelAction *
0x1c00da9ba  xor     r9d, r9d; unsigned __int8
0x1c00da9bd  mov     byte ptr [rsp+390h+var_370], sil; char
0x1c00da9c2  mov     rdx, r12; struct CmsTransactionContext *
0x1c00da9c5  call    ?BeginTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EE@Z; CmsVolume::BeginTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar)
0x1c00da9ca  mov     rax, [r14+8]
0x1c00da9ce  xor     r8d, r8d
0x1c00da9d1  mov     [rsp+390h+var_32E], 1
0x1c00da9d6  mov     rcx, [rax+0BD8h]
0x1c00da9dd  mov     rcx, [rcx+10h]
0x1c00da9e1  mov     rax, [rcx]
0x1c00da9e4  mov     rax, [rax+40h]
0x1c00da9e8  call    cs:__guard_dispatch_icall_fptr
0x1c00da9ee  mov     rax, [rbp+290h+var_278]
0x1c00da9f2  lea     r9, [rsp+390h+var_318]; struct SmsContainer **
0x1c00da9f7  mov     r8, [rbp+290h+var_2D8]; unsigned __int64
0x1c00da9fb  mov     rdx, r12; struct CmsTransactionContext *
0x1c00da9fe  mov     byte ptr [rsp+390h+var_360], sil; unsigned __int8
0x1c00daa03  mov     rcx, r14; this
0x1c00daa06  mov     byte ptr [rsp+390h+var_368], sil; unsigned __int8
0x1c00daa0b  mov     dil, sil
0x1c00daa0e  mov     [rbp+290h+var_270], rax
0x1c00daa12  mov     dword ptr [rsp+390h+var_328], 0Ah
0x1c00daa1a  mov     [rsp+390h+var_330], sil
0x1c00daa1f  mov     byte ptr [rsp+390h+var_370], sil; unsigned __int8
0x1c00daa24  call    ?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EEE@Z; CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar,uchar)
0x1c00daa29  mov     r13, [rsp+390h+var_318]
0x1c00daa2e  xor     r10d, r10d
0x1c00daa31  mov     esi, eax
0x1c00daa33  test    eax, eax
0x1c00daa35  js      loc_1C00DAAED
0x1c00daa3b  mov     rdx, r13; struct SmsContainer *
0x1c00daa3e  call    ?IncrementExclusiveAcquirersCount@CmsVolumeContainer@@QEAAXPEAUSmsContainer@@@Z; CmsVolumeContainer::IncrementExclusiveAcquirersCount(SmsContainer *)
0x1c00daa43  mov     r8, r13; struct SmsContainer *
0x1c00daa46  call    ?TryLockContainerExclusive@CmsVolumeContainer@@AEAAEPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::TryLockContainerExclusive(CmsTransactionContext *,SmsContainer *)
0x1c00daa4b  xor     r10d, r10d
0x1c00daa4e  test    al, al
0x1c00daa50  jz      short loc_1C00DAAA2
0x1c00daa52  mov     dil, 1
0x1c00daa55  test    r15, r15
0x1c00daa58  jnz     short loc_1C00DAA93
0x1c00daa5a  mov     r8, [rbp+290h+var_270]; unsigned __int64
0x1c00daa5e  lea     r9, [rsp+390h+var_320]; struct SmsContainer **
0x1c00daa63  mov     byte ptr [rsp+390h+var_360], r10b; unsigned __int8
0x1c00daa68  mov     rdx, r12; struct CmsTransactionContext *
0x1c00daa6b  mov     byte ptr [rsp+390h+var_368], r10b; unsigned __int8
0x1c00daa70  mov     rcx, r14; this
0x1c00daa73  mov     byte ptr [rsp+390h+var_370], r10b; unsigned __int8
0x1c00daa78  call    ?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EEE@Z; CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar,uchar)
0x1c00daa7d  mov     r15, [rsp+390h+var_320]
0x1c00daa82  xor     r10d, r10d
0x1c00daa85  mov     esi, eax
0x1c00daa87  test    eax, eax
0x1c00daa89  js      short loc_1C00DAAED
0x1c00daa8b  mov     rdx, r15; struct SmsContainer *
0x1c00daa8e  call    ?IncrementExclusiveAcquirersCount@CmsVolumeContainer@@QEAAXPEAUSmsContainer@@@Z; CmsVolumeContainer::IncrementExclusiveAcquirersCount(SmsContainer *)
0x1c00daa93  mov     r8, r15; struct SmsContainer *
0x1c00daa96  call    ?TryLockContainerExclusive@CmsVolumeContainer@@AEAAEPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::TryLockContainerExclusive(CmsTransactionContext *,SmsContainer *)
0x1c00daa9b  xor     r10d, r10d
0x1c00daa9e  test    al, al
0x1c00daaa0  jnz     short loc_1C00DAAE1
0x1c00daaa2  test    dil, dil
0x1c00daaa5  jz      short loc_1C00DAAC2
0x1c00daaa7  lea     rcx, [r13+68h]
0x1c00daaab  mov     edx, 2
0x1c00daab0  call    cs:__imp_ExReleasePushLockEx
0x1c00daab7  nop     dword ptr [rax+rax+00h]
0x1c00daabc  xor     r10d, r10d
0x1c00daabf  mov     dil, r10b
0x1c00daac2  mov     ecx, dword ptr [rsp+390h+var_328]
0x1c00daac6  mov     eax, ecx
0x1c00daac8  dec     ecx; this
0x1c00daaca  mov     dword ptr [rsp+390h+var_328], ecx
0x1c00daace  test    eax, eax
0x1c00daad0  jz      short loc_1C00DAAE8
0x1c00daad2  mov     ecx, 32h ; '2'; int
0x1c00daad7  call    ?MsDelayExecutionThread@@YAXJ@Z; MsDelayExecutionThread(long)
0x1c00daadc  jmp     loc_1C00DAA43
0x1c00daae1  mov     [rsp+390h+var_330], dil
0x1c00daae6  jmp     short loc_1C00DAAED
0x1c00daae8  mov     esi, 0C000022Dh
0x1c00daaed  test    r13, r13
0x1c00daaf0  jz      short loc_1C00DAAFD
0x1c00daaf2  mov     rdx, r13; struct SmsContainer *
0x1c00daaf5  call    ?DecrementExclusiveAcquirersCount@CmsVolumeContainer@@QEAAXPEAUSmsContainer@@@Z; CmsVolumeContainer::DecrementExclusiveAcquirersCount(SmsContainer *)
0x1c00daafa  xor     r10d, r10d
0x1c00daafd  test    r15, r15
0x1c00dab00  jz      short loc_1C00DAB0D
0x1c00dab02  mov     rdx, r15; struct SmsContainer *
0x1c00dab05  call    ?DecrementExclusiveAcquirersCount@CmsVolumeContainer@@QEAAXPEAUSmsContainer@@@Z; CmsVolumeContainer::DecrementExclusiveAcquirersCount(SmsContainer *)
0x1c00dab0a  xor     r10d, r10d
0x1c00dab0d  test    esi, esi
0x1c00dab0f  jns     loc_1C00DABCE
0x1c00dab15  test    dil, dil
0x1c00dab18  jz      short loc_1C00DAB32
0x1c00dab1a  lea     rcx, [r13+68h]
0x1c00dab1e  mov     edx, 2
0x1c00dab23  call    cs:__imp_ExReleasePushLockEx
0x1c00dab2a  nop     dword ptr [rax+rax+00h]
0x1c00dab2f  xor     r10d, r10d
0x1c00dab32  cmp     [rsp+390h+var_330], r10b
0x1c00dab37  jz      short loc_1C00DAB51
0x1c00dab39  lea     rcx, [r15+68h]
0x1c00dab3d  mov     edx, 2
0x1c00dab42  call    cs:__imp_ExReleasePushLockEx
0x1c00dab49  nop     dword ptr [rax+rax+00h]
0x1c00dab4e  xor     r10d, r10d
0x1c00dab51  lea     rdi, [r14+148h]
0x1c00dab58  test    r13, r13
0x1c00dab5b  jz      short loc_1C00DAB8F
0x1c00dab5d  lock dec dword ptr [r13+58h]
0x1c00dab62  xor     edx, edx; Tag
0x1c00dab64  mov     rcx, rdi; RemoveLock
0x1c00dab67  lea     r8d, [rdx+20h]; RemlockSize
0x1c00dab6b  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00dab72  nop     dword ptr [rax+rax+00h]
0x1c00dab77  dec     dword ptr [r12+0B08h]
0x1c00dab7f  mov     r15, [rsp+390h+var_320]
0x1c00dab84  xor     r10d, r10d
0x1c00dab87  mov     r13d, r10d
0x1c00dab8a  mov     [rsp+390h+var_318], r10
0x1c00dab8f  test    r15, r15
0x1c00dab92  jz      short loc_1C00DABC6
0x1c00dab94  lock dec dword ptr [r15+58h]
0x1c00dab99  xor     edx, edx; Tag
  ... truncated ...
```
