# CDDPDEV::InitInternalBitmaps(void)

- ea: `0x14002d4b4`
- end: `0x14002e615`
- name: `?InitInternalBitmaps@CDDPDEV@@QEAAJXZ`
- size: `4449`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140022c28`

## callees

- `0x140001cb4`
- `0x140001dcc`
- `0x14000f370`
- `0x140010c2c`
- `0x1400111c0`
- `0x140011220`
- `0x14001b448`
- `0x14001bff8`
- `0x14002d4b4`
- `0x14002e810`
- `0x14002ece0`
- `0x1400308cc`
- `0x140030a74`
- `0x1400371f0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14002d5bd`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14002d5bd`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002d5fc`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002d5fc`
- `ntoskrnl!DbgPrint` at `0x14002d510`
- `ntoskrnl!DbgPrint` at `0x14002d510`
- `ntoskrnl!KdDebuggerEnabled` at `0x14002d4fd`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002d721`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002e4b1`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002e56c`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002d721`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002e4b1`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002e56c`
- `watchdog!WdLogSingleEntry1` at `0x14002d569`
- `watchdog!WdLogSingleEntry1` at `0x14002e5b0`
- `watchdog!WdLogSingleEntry1` at `0x14002d569`
- `watchdog!WdLogSingleEntry1` at `0x14002e5b0`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002d535`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002d535`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002d81b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002d81b`
- `watchdog!WdLogSingleEntry0` at `0x14002d51e`
- `watchdog!WdLogSingleEntry0` at `0x14002d70a`
- `watchdog!WdLogSingleEntry0` at `0x14002d7b4`
- `watchdog!WdLogSingleEntry0` at `0x14002d804`
- `watchdog!WdLogSingleEntry0` at `0x14002d875`
- `watchdog!WdLogSingleEntry0` at `0x14002e49a`
- `watchdog!WdLogSingleEntry0` at `0x14002e4f5`
- `watchdog!WdLogSingleEntry0` at `0x14002e555`
- `watchdog!WdLogSingleEntry0` at `0x14002d51e`
- `watchdog!WdLogSingleEntry0` at `0x14002d70a`
- `watchdog!WdLogSingleEntry0` at `0x14002d7b4`
- `watchdog!WdLogSingleEntry0` at `0x14002d804`
- `watchdog!WdLogSingleEntry0` at `0x14002d875`
- `watchdog!WdLogSingleEntry0` at `0x14002e49a`
- `watchdog!WdLogSingleEntry0` at `0x14002e4f5`
- `watchdog!WdLogSingleEntry0` at `0x14002e555`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002d580`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002d7cb`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002d88c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002e50c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002e5c7`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002d580`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002d7cb`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002d88c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002e50c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002e5c7`
- `WIN32K!EngCTGetGammaTable` at `0x14002d8e6`
- `WIN32K!EngCTGetGammaTable` at `0x14002d9c5`
- `WIN32K!EngCTGetGammaTable` at `0x14002da9f`
- `WIN32K!EngCTGetGammaTable` at `0x14002db79`
- `WIN32K!EngCTGetGammaTable` at `0x14002dc53`
- `WIN32K!EngCTGetGammaTable` at `0x14002dd2d`
- `WIN32K!EngCTGetGammaTable` at `0x14002de07`
- `WIN32K!EngCTGetGammaTable` at `0x14002dee1`
- `WIN32K!EngCTGetGammaTable` at `0x14002dfbb`
- `WIN32K!EngCTGetGammaTable` at `0x14002e095`
- `WIN32K!EngCTGetGammaTable` at `0x14002e16f`
- `WIN32K!EngCTGetGammaTable` at `0x14002e249`
- `WIN32K!EngCTGetGammaTable` at `0x14002e323`
- `WIN32K!EngCTGetGammaTable` at `0x14002d8e6`
- `WIN32K!EngCTGetGammaTable` at `0x14002d9c5`
- `WIN32K!EngCTGetGammaTable` at `0x14002da9f`
- `WIN32K!EngCTGetGammaTable` at `0x14002db79`
- `WIN32K!EngCTGetGammaTable` at `0x14002dc53`
- `WIN32K!EngCTGetGammaTable` at `0x14002dd2d`
- `WIN32K!EngCTGetGammaTable` at `0x14002de07`
- `WIN32K!EngCTGetGammaTable` at `0x14002dee1`
- `WIN32K!EngCTGetGammaTable` at `0x14002dfbb`
- `WIN32K!EngCTGetGammaTable` at `0x14002e095`
- `WIN32K!EngCTGetGammaTable` at `0x14002e16f`
- `WIN32K!EngCTGetGammaTable` at `0x14002e249`
- `WIN32K!EngCTGetGammaTable` at `0x14002e323`
- `WIN32K!EngFreeMem` at `0x14002e542`
- `WIN32K!EngFreeMem` at `0x14002e542`

## string_xrefs

- `0x14002d509`: `InitInternalBitmaps is not called by the worker thread`

## pseudocode

```c
__int64 __fastcall CDDPDEV::InitInternalBitmaps(CDDPDEV *this)
{
  __int64 v2; // rsi
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  __int64 v5; // rcx
  __int64 result; // rax
  int CommandBuffer; // ebx
  int v8; // edi
  _QWORD *v9; // rax
  int v10; // edi
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  BYTE *v14; // rbx
  BYTE *v15; // rcx
  BYTE *v16; // rax
  __int64 v17; // rdx
  __int128 v18; // xmm1
  BYTE *v19; // rcx
  _OWORD *v20; // rax
  __int64 v21; // rdx
  __int128 v22; // xmm1
  BYTE *v23; // rbx
  BYTE *v24; // rcx
  BYTE *v25; // rax
  __int64 v26; // rdx
  __int128 v27; // xmm1
  BYTE *v28; // rcx
  _OWORD *v29; // rax
  __int64 v30; // rdx
  __int128 v31; // xmm1
  BYTE *v32; // rbx
  BYTE *v33; // rcx
  BYTE *v34; // rax
  __int64 v35; // rdx
  __int128 v36; // xmm1
  BYTE *v37; // rcx
  _OWORD *v38; // rax
  __int64 v39; // rdx
  __int128 v40; // xmm1
  BYTE *v41; // rbx
  BYTE *v42; // rcx
  BYTE *v43; // rax
  __int64 v44; // rdx
  __int128 v45; // xmm1
  BYTE *v46; // rcx
  _OWORD *v47; // rax
  __int64 v48; // rdx
  __int128 v49; // xmm1
  BYTE *v50; // rbx
  BYTE *v51; // rcx
  BYTE *v52; // rax
  __int64 v53; // rdx
  __int128 v54; // xmm1
  BYTE *v55; // rcx
  _OWORD *v56; // rax
  __int64 v57; // rdx
  __int128 v58; // xmm1
  BYTE *v59; // rbx
  BYTE *v60; // rcx
  BYTE *v61; // rax
  __int64 v62; // rdx
  __int128 v63; // xmm1
  BYTE *v64; // rcx
  _OWORD *v65; // rax
  __int64 v66; // rdx
  __int128 v67; // xmm1
  BYTE *v68; // rbx
  BYTE *v69; // rcx
  BYTE *v70; // rax
  __int64 v71; // rdx
  __int128 v72; // xmm1
  BYTE *v73; // rcx
  _OWORD *v74; // rax
  __int64 v75; // rdx
  __int128 v76; // xmm1
  BYTE *v77; // rbx
  BYTE *v78; // rcx
  BYTE *v79; // rax
  __int64 v80; // rdx
  __int128 v81; // xmm1
  BYTE *v82; // rcx
  _OWORD *v83; // rax
  __int64 v84; // rdx
  __int128 v85; // xmm1
  BYTE *v86; // rbx
  BYTE *v87; // rcx
  BYTE *v88; // rax
  __int64 v89; // rdx
  __int128 v90; // xmm1
  BYTE *v91; // rcx
  _OWORD *v92; // rax
  __int64 v93; // rdx
  __int128 v94; // xmm1
  BYTE *v95; // rbx
  BYTE *v96; // rcx
  _OWORD *v97; // rax
  __int64 v98; // rdx
  __int128 v99; // xmm1
  BYTE *v100; // rcx
  _OWORD *v101; // rax
  __int64 v102; // rdx
  __int128 v103; // xmm1
  _OWORD *v104; // rbx
  BYTE *v105; // rcx
  _OWORD *v106; // rax
  __int64 v107; // rdx
  __int128 v108; // xmm1
  BYTE *v109; // rcx
  _OWORD *v110; // rax
  __int64 v111; // rdx
  __int128 v112; // xmm1
  _OWORD *v113; // rbx
  BYTE *v114; // rcx
  _OWORD *v115; // rax
  __int64 v116; // rdx
  __int128 v117; // xmm1
  BYTE *v118; // rcx
  _OWORD *v119; // rax
  __int64 v120; // rdx
  __int128 v121; // xmm1
  _OWORD *v122; // rbx
  BYTE *v123; // rcx
  _OWORD *v124; // rax
  __int64 v125; // rdx
  __int128 v126; // xmm1
  BYTE *v127; // rax
  _OWORD *v128; // rbx
  __int128 v129; // xmm1
  int v130; // eax
  CHwCommandBuffer *v131; // rax
  CHwCommandBuffer *v132; // rdi
  int v133; // esi
  _QWORD *v134; // rax
  _QWORD *v135; // rax
  _QWORD *v136; // rax
  int v137; // [rsp+58h] [rbp-A8h]
  BYTE *pGammaTable; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *pInverseGammaTable; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v140; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v141; // [rsp+74h] [rbp-8Ch] BYREF
  int v142; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v143[6]; // [rsp+80h] [rbp-80h] BYREF
  char v144; // [rsp+B0h] [rbp-50h]
  CDDPDEV *v145; // [rsp+C8h] [rbp-38h]
  __int128 v146; // [rsp+D0h] [rbp-30h]
  unsigned int v147; // [rsp+E0h] [rbp-20h]
  int v148; // [rsp+E4h] [rbp-1Ch]
  int v149; // [rsp+E8h] [rbp-18h]
  unsigned int v150; // [rsp+ECh] [rbp-14h]
  int v151; // [rsp+F0h] [rbp-10h]
  char v152; // [rsp+F4h] [rbp-Ch]
  struct tagRECT si128; // [rsp+100h] [rbp+0h] BYREF

  v2 = 2;
  if ( KeGetCurrentThread() != *((struct _KTHREAD **)this + 321) && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("InitInternalBitmaps is not called by the worker thread");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 1669;
    v3 = (_QWORD *)WdLogNewEntry5_WdError();
    v3[3] = gCddImageInfo;
    v3[4] = (unsigned int)dword_14003E570;
    v3[5] = 215857758;
    WdLogGlobalForLineNumber = 1669;
    __debugbreak();
  }
  WdLogSingleEntry1(4, this);
  WdLogGlobalForLineNumber = 1671;
  v4 = (_QWORD *)WdLogNewEntry5_WdEvent();
  v4[3] = gCddImageInfo;
  v4[4] = (unsigned int)dword_14003E570;
  v4[5] = 215857758;
  WdLogGlobalForLineNumber = 1671;
  if ( (*((_DWORD *)this + 686) & 0x40) == 0 )
    goto LABEL_85;
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)this + 362));
  CHwCommandBuffer::ResetCommandBuffer((CDDPDEV *)((char *)this + 8392));
  CHwCommandBuffer::ResetCommandBuffer((CDDPDEV *)((char *)this + 10544));
  v5 = *((_QWORD *)this + 362);
  *((_QWORD *)this + 1587) = (char *)this + 8392;
  *((_QWORD *)this + 1588) = (char *)this + 10544;
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v5);
  result = CddBitmapStagingVidMem::InitStagingVidMem(
             *((CddBitmapStagingVidMem **)this + 687),
             *((_DWORD *)this + 1822),
             *((_DWORD *)this + 1823));
  if ( (int)result >= 0 )
  {
LABEL_85:
    result = CStagingPoolBase::InitStagingPool(
               (CDDPDEV *)((char *)this + 5504),
               *((_DWORD *)this + 1824),
               *((_DWORD *)this + 1825));
    CommandBuffer = result;
    if ( (int)result >= 0 )
    {
      if ( (*((_DWORD *)this + 475) & 0x20000000) == 0
        || (result = CStagingPoolBase::InitStagingPool(
                       (CDDPDEV *)((char *)this + 6320),
                       *((_DWORD *)this + 1824) >> 2,
                       *((_DWORD *)this + 1825) >> 2),
            CommandBuffer = result,
            (int)result >= 0) )
      {
        *((_DWORD *)this + 686) |= 0x100u;
        if ( (*((_DWORD *)this + 686) & 0x40) == 0 )
          return (unsigned int)CommandBuffer;
        v142 = 0;
        v140 = 0;
        v8 = CDDPDEV::CreateAllocation(this, 0, 512, 16, 4, 28, 0, (char *)this + 7224, &v142, 0, &v140, 1);
        if ( v8 < 0 )
        {
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 1740;
          v9 = (_QWORD *)WdLogNewEntry5_WdLowResource();
          v9[3] = gCddImageInfo;
          v9[4] = (unsigned int)dword_14003E570;
          v9[5] = 215857758;
          result = (unsigned int)v8;
          WdLogGlobalForLineNumber = 1740;
          return result;
        }
        LOBYTE(v137) = 1;
        v141 = 0;
        CommandBuffer = CDDPDEV::CreateAllocation(this, 0, 512, 16, 2, 28, 0, &v141, &v142, 0, &v140, v137);
        if ( CommandBuffer < 0 )
        {
          WdLogSingleEntry0(4);
          v10 = 1756;
          WdLogGlobalForLineNumber = 1756;
          v11 = (_QWORD *)WdLogNewEntry5_WdEvent();
          v11[3] = gCddImageInfo;
          v11[4] = (unsigned int)dword_14003E570;
          v11[5] = 215857758;
LABEL_81:
          WdLogGlobalForLineNumber = v10;
          return (unsigned int)CommandBuffer;
        }
        if ( v140 < 0x200 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 1760;
          v12 = (_QWORD *)WdLogNewEntry5_WdAssertion();
          v12[3] = gCddImageInfo;
          v12[4] = (unsigned int)dword_14003E570;
          v12[5] = 215857758;
          WdLogGlobalForLineNumber = 1760;
        }
        pGammaTable = 0;
        CommandBuffer = CDDPDEV::LockAllocation(this, v141, &pGammaTable);
        if ( CommandBuffer < 0 )
        {
          WdLogSingleEntry0(4);
          WdLogGlobalForLineNumber = 1768;
          v13 = (_QWORD *)WdLogNewEntry5_WdEvent();
          v13[3] = gCddImageInfo;
          v13[4] = (unsigned int)dword_14003E570;
          v13[5] = 215857758;
          WdLogGlobalForLineNumber = 1768;
          CDDPDEV::DestroyAllocation(this, v141);
          return (unsigned int)CommandBuffer;
        }
        v14 = pGammaTable;
        pGammaTable = 0;
        pInverseGammaTable = 0;
        EngCTGetGammaTable(0x3E8u, (const BYTE **)&pGammaTable, (const BYTE **)&pInverseGammaTable);
        v15 = pGammaTable;
        v16 = v14;
        v17 = 2;
        do
        {
          *(_OWORD *)v16 = *(_OWORD *)v15;
          *((_OWORD *)v16 + 1) = *((_OWORD *)v15 + 1);
          *((_OWORD *)v16 + 2) = *((_OWORD *)v15 + 2);
          *((_OWORD *)v16 + 3) = *((_OWORD *)v15 + 3);
          *((_OWORD *)v16 + 4) = *((_OWORD *)v15 + 4);
          *((_OWORD *)v16 + 5) = *((_OWORD *)v15 + 5);
          *((_OWORD *)v16 + 6) = *((_OWORD *)v15 + 6);
          v18 = *((_OWORD *)v15 + 7);
          v15 += 128;
          *((_OWORD *)v16 + 7) = v18;
          v16 += 128;
          --v17;
        }
        while ( v17 );
        v19 = pInverseGammaTable;
        v20 = v14 + 256;
        v21 = 2;
        do
        {
          *v20 = *(_OWORD *)v19;
          v20[1] = *((_OWORD *)v19 + 1);
          v20[2] = *((_OWORD *)v19 + 2);
          v20[3] = *((_OWORD *)v19 + 3);
          v20[4] = *((_OWORD *)v19 + 4);
          v20[5] = *((_OWORD *)v19 + 5);
          v20[6] = *((_OWORD *)v19 + 6);
          v22 = *((_OWORD *)v19 + 7);
          v19 += 128;
          v20[7] = v22;
          v20 += 8;
          --v21;
        }
        while ( v21 );
        v23 = &v14[v140];
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x44Cu, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v24 = pInverseGammaTable;
        v25 = v23;
        v26 = 2;
        do
        {
          *(_OWORD *)v25 = *(_OWORD *)v24;
          *((_OWORD *)v25 + 1) = *((_OWORD *)v24 + 1);
          *((_OWORD *)v25 + 2) = *((_OWORD *)v24 + 2);
          *((_OWORD *)v25 + 3) = *((_OWORD *)v24 + 3);
          *((_OWORD *)v25 + 4) = *((_OWORD *)v24 + 4);
          *((_OWORD *)v25 + 5) = *((_OWORD *)v24 + 5);
          *((_OWORD *)v25 + 6) = *((_OWORD *)v24 + 6);
          v27 = *((_OWORD *)v24 + 7);
          v24 += 128;
          *((_OWORD *)v25 + 7) = v27;
          v25 += 128;
          --v26;
        }
        while ( v26 );
        v28 = pGammaTable;
        v29 = v23 + 256;
        v30 = 2;
        do
        {
          *v29 = *(_OWORD *)v28;
          v29[1] = *((_OWORD *)v28 + 1);
          v29[2] = *((_OWORD *)v28 + 2);
          v29[3] = *((_OWORD *)v28 + 3);
          v29[4] = *((_OWORD *)v28 + 4);
          v29[5] = *((_OWORD *)v28 + 5);
          v29[6] = *((_OWORD *)v28 + 6);
          v31 = *((_OWORD *)v28 + 7);
          v28 += 128;
          v29[7] = v31;
          v29 += 8;
          --v30;
        }
        while ( v30 );
        v32 = &v23[v140];
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x4B0u, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v33 = pInverseGammaTable;
        v34 = v32;
        v35 = 2;
        do
        {
          *(_OWORD *)v34 = *(_OWORD *)v33;
          *((_OWORD *)v34 + 1) = *((_OWORD *)v33 + 1);
          *((_OWORD *)v34 + 2) = *((_OWORD *)v33 + 2);
          *((_OWORD *)v34 + 3) = *((_OWORD *)v33 + 3);
          *((_OWORD *)v34 + 4) = *((_OWORD *)v33 + 4);
          *((_OWORD *)v34 + 5) = *((_OWORD *)v33 + 5);
          *((_OWORD *)v34 + 6) = *((_OWORD *)v33 + 6);
          v36 = *((_OWORD *)v33 + 7);
          v33 += 128;
          *((_OWORD *)v34 + 7) = v36;
          v34 += 128;
          --v35;
        }
        while ( v35 );
        v37 = pGammaTable;
        v38 = v32 + 256;
        v39 = 2;
        do
        {
          *v38 = *(_OWORD *)v37;
          v38[1] = *((_OWORD *)v37 + 1);
          v38[2] = *((_OWORD *)v37 + 2);
          v38[3] = *((_OWORD *)v37 + 3);
          v38[4] = *((_OWORD *)v37 + 4);
          v38[5] = *((_OWORD *)v37 + 5);
          v38[6] = *((_OWORD *)v37 + 6);
          v40 = *((_OWORD *)v37 + 7);
          v37 += 128;
          v38[7] = v40;
          v38 += 8;
          --v39;
        }
        while ( v39 );
        v41 = &v32[v140];
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x514u, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v42 = pInverseGammaTable;
        v43 = v41;
        v44 = 2;
        do
        {
          *(_OWORD *)v43 = *(_OWORD *)v42;
          *((_OWORD *)v43 + 1) = *((_OWORD *)v42 + 1);
          *((_OWORD *)v43 + 2) = *((_OWORD *)v42 + 2);
          *((_OWORD *)v43 + 3) = *((_OWORD *)v42 + 3);
          *((_OWORD *)v43 + 4) = *((_OWORD *)v42 + 4);
          *((_OWORD *)v43 + 5) = *((_OWORD *)v42 + 5);
          *((_OWORD *)v43 + 6) = *((_OWORD *)v42 + 6);
          v45 = *((_OWORD *)v42 + 7);
          v42 += 128;
          *((_OWORD *)v43 + 7) = v45;
          v43 += 128;
          --v44;
        }
        while ( v44 );
        v46 = pGammaTable;
        v47 = v41 + 256;
        v48 = 2;
        do
        {
          *v47 = *(_OWORD *)v46;
          v47[1] = *((_OWORD *)v46 + 1);
          v47[2] = *((_OWORD *)v46 + 2);
          v47[3] = *((_OWORD *)v46 + 3);
          v47[4] = *((_OWORD *)v46 + 4);
          v47[5] = *((_OWORD *)v46 + 5);
          v47[6] = *((_OWORD *)v46 + 6);
          v49 = *((_OWORD *)v46 + 7);
          v46 += 128;
          v47[7] = v49;
          v47 += 8;
          --v48;
        }
        while ( v48 );
        v50 = &v41[v140];
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x578u, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v51 = pInverseGammaTable;
        v52 = v50;
        v53 = 2;
        do
        {
          *(_OWORD *)v52 = *(_OWORD *)v51;
          *((_OWORD *)v52 + 1) = *((_OWORD *)v51 + 1);
          *((_OWORD *)v52 + 2) = *((_OWORD *)v51 + 2);
          *((_OWORD *)v52 + 3) = *((_OWORD *)v51 + 3);
          *((_OWORD *)v52 + 4) = *((_OWORD *)v51 + 4);
          *((_OWORD *)v52 + 5) = *((_OWORD *)v51 + 5);
          *((_OWORD *)v52 + 6) = *((_OWORD *)v51 + 6);
          v54 = *((_OWORD *)v51 + 7);
          v51 += 128;
          *((_OWORD *)v52 + 7) = v54;
          v52 += 128;
          --v53;
        }
        while ( v53 );
        v55 = pGammaTable;
        v56 = v50 + 256;
        v57 = 2;
        do
        {
          *v56 = *(_OWORD *)v55;
          v56[1] = *((_OWORD *)v55 + 1);
          v56[2] = *((_OWORD *)v55 + 2);
          v56[3] = *((_OWORD *)v55 + 3);
          v56[4] = *((_OWORD *)v55 + 4);
          v56[5] = *((_OWORD *)v55 + 5);
          v56[6] = *((_OWORD *)v55 + 6);
          v58 = *((_OWORD *)v55 + 7);
          v55 += 128;
          v56[7] = v58;
          v56 += 8;
          --v57;
        }
        while ( v57 );
        v59 = &v50[v140];
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x5DCu, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v60 = pInverseGammaTable;
        v61 = v59;
        v62 = 2;
        do
        {
          *(_OWORD *)v61 = *(_OWORD *)v60;
          *((_OWORD *)v61 + 1) = *((_OWORD *)v60 + 1);
          *((_OWORD *)v61 + 2) = *((_OWORD *)v60 + 2);
          *((_OWORD *)v61 + 3) = *((_OWORD *)v60 + 3);
          *((_OWORD *)v61 + 4) = *((_OWORD *)v60 + 4);
          *((_OWORD *)v61 + 5) = *((_OWORD *)v60 + 5);
          *((_OWORD *)v61 + 6) = *((_OWORD *)v60 + 6);
          v63 = *((_OWORD *)v60 + 7);
          v60 += 128;
          *((_OWORD *)v61 + 7) = v63;
          v61 += 128;
          --v62;
        }
        while ( v62 );
        v64 = pGammaTable;
        v65 = v59 + 256;
        v66 = 2;
        do
        {
          *v65 = *(_OWORD *)v64;
          v65[1] = *((_OWORD *)v64 + 1);
          v65[2] = *((_OWORD *)v64 + 2);
          v65[3] = *((_OWORD *)v64 + 3);
          v65[4] = *((_OWORD *)v64 + 4);
          v65[5] = *((_OWORD *)v64 + 5);
          v65[6] = *((_OWORD *)v64 + 6);
          v67 = *((_OWORD *)v64 + 7);
          v64 += 128;
          v65[7] = v67;
          v65 += 8;
          --v66;
        }
        while ( v66 );
        v68 = &v59[v140];
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x640u, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v69 = pInverseGammaTable;
        v70 = v68;
        v71 = 2;
        do
        {
          *(_OWORD *)v70 = *(_OWORD *)v69;
          *((_OWORD *)v70 + 1) = *((_OWORD *)v69 + 1);
          *((_OWORD *)v70 + 2) = *((_OWORD *)v69 + 2);
          *((_OWORD *)v70 + 3) = *((_OWORD *)v69 + 3);
          *((_OWORD *)v70 + 4) = *((_OWORD *)v69 + 4);
          *((_OWORD *)v70 + 5) = *((_OWORD *)v69 + 5);
          *((_OWORD *)v70 + 6) = *((_OWORD *)v69 + 6);
          v72 = *((_OWORD *)v69 + 7);
          v69 += 128;
          *((_OWORD *)v70 + 7) = v72;
          v70 += 128;
          --v71;
        }
        while ( v71 );
        v73 = pGammaTable;
        v74 = v68 + 256;
        v75 = 2;
        do
        {
          *v74 = *(_OWORD *)v73;
          v74[1] = *((_OWORD *)v73 + 1);
          v74[2] = *((_OWORD *)v73 + 2);
          v74[3] = *((_OWORD *)v73 + 3);
          v74[4] = *((_OWORD *)v73 + 4);
          v74[5] = *((_OWORD *)v73 + 5);
          v74[6] = *((_OWORD *)v73 + 6);
          v76 = *((_OWORD *)v73 + 7);
          v73 += 128;
          v74[7] = v76;
          v74 += 8;
          --v75;
        }
        while ( v75 );
        v77 = &v68[v140];
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x6A4u, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v78 = pInverseGammaTable;
        v79 = v77;
        v80 = 2;
        do
        {
          *(_OWORD *)v79 = *(_OWORD *)v78;
          *((_OWORD *)v79 + 1) = *((_OWORD *)v78 + 1);
          *((_OWORD *)v79 + 2) = *((_OWORD *)v78 + 2);
          *((_OWORD *)v79 + 3) = *((_OWORD *)v78 + 3);
          *((_OWORD *)v79 + 4) = *((_OWORD *)v78 + 4);
          *((_OWORD *)v79 + 5) = *((_OWORD *)v78 + 5);
          *((_OWORD *)v79 + 6) = *((_OWORD *)v78 + 6);
          v81 = *((_OWORD *)v78 + 7);
          v78 += 128;
          *((_OWORD *)v79 + 7) = v81;
          v79 += 128;
          --v80;
        }
        while ( v80 );
        v82 = pGammaTable;
        v83 = v77 + 256;
        v84 = 2;
        do
        {
          *v83 = *(_OWORD *)v82;
          v83[1] = *((_OWORD *)v82 + 1);
          v83[2] = *((_OWORD *)v82 + 2);
          v83[3] = *((_OWORD *)v82 + 3);
          v83[4] = *((_OWORD *)v82 + 4);
          v83[5] = *((_OWORD *)v82 + 5);
          v83[6] = *((_OWORD *)v82 + 6);
          v85 = *((_OWORD *)v82 + 7);
          v82 += 128;
          v83[7] = v85;
          v83 += 8;
          --v84;
        }
        while ( v84 );
        v86 = &v77[v140];
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x708u, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v87 = pInverseGammaTable;
        v88 = v86;
        v89 = 2;
        do
        {
          *v88 = *(_OWORD *)v87;
          v88[1] = *((_OWORD *)v87 + 1);
          v88[2] = *((_OWORD *)v87 + 2);
          v88[3] = *((_OWORD *)v87 + 3);
          v88[4] = *((_OWORD *)v87 + 4);
          v88[5] = *((_OWORD *)v87 + 5);
          v88[6] = *((_OWORD *)v87 + 6);
          v90 = *((_OWORD *)v87 + 7);
          v87 += 128;
          v88[7] = v90;
          v88 += 8;
          --v89;
        }
        while ( v89 );
        v91 = pGammaTable;
        v92 = v86 + 256;
        v93 = 2;
        do
        {
          *v92 = *(_OWORD *)v91;
          v92[1] = *((_OWORD *)v91 + 1);
          v92[2] = *((_OWORD *)v91 + 2);
          v92[3] = *((_OWORD *)v91 + 3);
          v92[4] = *((_OWORD *)v91 + 4);
          v92[5] = *((_OWORD *)v91 + 5);
          v92[6] = *((_OWORD *)v91 + 6);
          v94 = *((_OWORD *)v91 + 7);
          v91 += 128;
          v92[7] = v94;
          v92 += 8;
          --v93;
        }
        while ( v93 );
        v95 = &v86[v140];
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x76Cu, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v96 = pInverseGammaTable;
        v97 = v95;
        v98 = 2;
        do
        {
          *v97 = *(_OWORD *)v96;
          v97[1] = *((_OWORD *)v96 + 1);
          v97[2] = *((_OWORD *)v96 + 2);
          v97[3] = *((_OWORD *)v96 + 3);
          v97[4] = *((_OWORD *)v96 + 4);
          v97[5] = *((_OWORD *)v96 + 5);
          v97[6] = *((_OWORD *)v96 + 6);
          v99 = *((_OWORD *)v96 + 7);
          v96 += 128;
          v97[7] = v99;
          v97 += 8;
          --v98;
        }
        while ( v98 );
        v100 = pGammaTable;
        v101 = v95 + 16;
        v102 = 2;
        do
        {
          *v101 = *(_OWORD *)v100;
          v101[1] = *((_OWORD *)v100 + 1);
          v101[2] = *((_OWORD *)v100 + 2);
          v101[3] = *((_OWORD *)v100 + 3);
          v101[4] = *((_OWORD *)v100 + 4);
          v101[5] = *((_OWORD *)v100 + 5);
          v101[6] = *((_OWORD *)v100 + 6);
          v103 = *((_OWORD *)v100 + 7);
          v100 += 128;
          v101[7] = v103;
          v101 += 8;
          --v102;
        }
        while ( v102 );
        v104 = (_OWORD *)((char *)v95 + v140);
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x7D0u, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v105 = pInverseGammaTable;
        v106 = v104;
        v107 = 2;
        do
        {
          *v106 = *(_OWORD *)v105;
          v106[1] = *((_OWORD *)v105 + 1);
          v106[2] = *((_OWORD *)v105 + 2);
          v106[3] = *((_OWORD *)v105 + 3);
          v106[4] = *((_OWORD *)v105 + 4);
          v106[5] = *((_OWORD *)v105 + 5);
          v106[6] = *((_OWORD *)v105 + 6);
          v108 = *((_OWORD *)v105 + 7);
          v105 += 128;
          v106[7] = v108;
          v106 += 8;
          --v107;
        }
        while ( v107 );
        v109 = pGammaTable;
        v110 = v104 + 16;
        v111 = 2;
        do
        {
          *v110 = *(_OWORD *)v109;
          v110[1] = *((_OWORD *)v109 + 1);
          v110[2] = *((_OWORD *)v109 + 2);
          v110[3] = *((_OWORD *)v109 + 3);
          v110[4] = *((_OWORD *)v109 + 4);
          v110[5] = *((_OWORD *)v109 + 5);
          v110[6] = *((_OWORD *)v109 + 6);
          v112 = *((_OWORD *)v109 + 7);
          v109 += 128;
          v110[7] = v112;
          v110 += 8;
          --v111;
        }
        while ( v111 );
        v113 = (_OWORD *)((char *)v104 + v140);
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x834u, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v114 = pInverseGammaTable;
        v115 = v113;
        v116 = 2;
        do
        {
          *v115 = *(_OWORD *)v114;
          v115[1] = *((_OWORD *)v114 + 1);
          v115[2] = *((_OWORD *)v114 + 2);
          v115[3] = *((_OWORD *)v114 + 3);
          v115[4] = *((_OWORD *)v114 + 4);
          v115[5] = *((_OWORD *)v114 + 5);
          v115[6] = *((_OWORD *)v114 + 6);
          v117 = *((_OWORD *)v114 + 7);
          v114 += 128;
          v115[7] = v117;
          v115 += 8;
          --v116;
        }
        while ( v116 );
        v118 = pGammaTable;
        v119 = v113 + 16;
        v120 = 2;
        do
        {
          *v119 = *(_OWORD *)v118;
          v119[1] = *((_OWORD *)v118 + 1);
          v119[2] = *((_OWORD *)v118 + 2);
          v119[3] = *((_OWORD *)v118 + 3);
          v119[4] = *((_OWORD *)v118 + 4);
          v119[5] = *((_OWORD *)v118 + 5);
          v119[6] = *((_OWORD *)v118 + 6);
          v121 = *((_OWORD *)v118 + 7);
          v118 += 128;
          v119[7] = v121;
          v119 += 8;
          --v120;
        }
        while ( v120 );
        v122 = (_OWORD *)((char *)v113 + v140);
        pInverseGammaTable = 0;
        pGammaTable = 0;
        EngCTGetGammaTable(0x898u, (const BYTE **)&pInverseGammaTable, (const BYTE **)&pGammaTable);
        v123 = pInverseGammaTable;
        v124 = v122;
        v125 = 2;
        do
        {
          *v124 = *(_OWORD *)v123;
          v124[1] = *((_OWORD *)v123 + 1);
          v124[2] = *((_OWORD *)v123 + 2);
          v124[3] = *((_OWORD *)v123 + 3);
          v124[4] = *((_OWORD *)v123 + 4);
          v124[5] = *((_OWORD *)v123 + 5);
          v124[6] = *((_OWORD *)v123 + 6);
          v126 = *((_OWORD *)v123 + 7);
          v123 += 128;
          v124[7] = v126;
          v124 += 8;
          --v125;
        }
        while ( v125 );
        v127 = pGammaTable;
        v128 = v122 + 16;
        do
        {
          *v128 = *(_OWORD *)v127;
          v128[1] = *((_OWORD *)v127 + 1);
          v128[2] = *((_OWORD *)v127 + 2);
          v128[3] = *((_OWORD *)v127 + 3);
          v128[4] = *((_OWORD *)v127 + 4);
          v128[5] = *((_OWORD *)v127 + 5);
          v128[6] = *((_OWORD *)v127 + 6);
          v129 = *((_OWORD *)v127 + 7);
          v127 += 128;
          v128[7] = v129;
          v128 += 8;
          --v2;
        }
        while ( v2 );
        CDDPDEV::UnlockAllocation(this, v141);
        v143[1] = &si128;
        v144 = 0;
        v143[2] = &si128;
        v152 = 0;
        v143[3] = &si128;
        v147 = v141;
        v130 = *((_DWORD *)this + 1806);
        si128 = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
        v148 = v130;
        v150 = v140;
        v143[0] = 0;
        v145 = this;
        v146 = 0;
        v149 = 1;
        v151 = 0;
        v143[5] = 0;
        v143[4] = 0;
        v131 = (CHwCommandBuffer *)operator new(0x868u);
        v132 = v131;
        if ( !v131 )
        {
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 1815;
          v135 = (_QWORD *)WdLogNewEntry5_WdLowResource();
          v135[3] = gCddImageInfo;
          v135[4] = (unsigned int)dword_14003E570;
          v135[5] = 215857758;
          WdLogGlobalForLineNumber = 1815;
          CommandBuffer = -1073741801;
          goto LABEL_80;
        }
        *(_QWORD *)v131 = 0;
        *((_QWORD *)v131 + 2) = 0;
        *((_DWORD *)v131 + 530) = 0;
        *((_QWORD *)v131 + 267) = 0;
        *((_QWORD *)v131 + 266) = 0;
        CommandBuffer = CHwCommandBuffer::CreateCommandBuffer(v131, this, 1u, 0x200u);
        if ( CommandBuffer < 0 )
        {
          WdLogSingleEntry0(6);
          v133 = 1823;
          WdLogGlobalForLineNumber = 1823;
          v134 = (_QWORD *)WdLogNewEntry5_WdLowResource();
LABEL_77:
          v134[3] = gCddImageInfo;
          v134[4] = (unsigned int)dword_14003E570;
          v134[5] = 215857758;
          WdLogGlobalForLineNumber = v133;
          goto LABEL_78;
        }
        if ( (unsigned int)CHwCommandBuffer::AddBitBltCommand(v132, (struct BITBLT_DATA *)v143, 1u, &si128, 0) )
        {
          CommandBuffer = CHwCommandBuffer::FlushGdiCommands(v132);
          if ( CommandBuffer < 0 )
          {
            WdLogSingleEntry0(4);
            v133 = 1837;
            WdLogGlobalForLineNumber = 1837;
            v134 = (_QWORD *)WdLogNewEntry5_WdEvent();
            goto LABEL_77;
          }
        }
        else
        {
          CommandBuffer = -1073741823;
        }
LABEL_78:
        CHwCommandBuffer::DestroyCommandBuffer(v132);
        EngFreeMem(v132);
LABEL_80:
        CDDPDEV::DestroyAllocation(this, v141);
        WdLogSingleEntry1(4, this);
        v10 = 1846;
        WdLogGlobalForLineNumber = 1846;
        v136 = (_QWORD *)WdLogNewEntry5_WdEvent();
        v136[3] = gCddImageInfo;
        v136[4] = (unsigned int)dword_14003E570;
        v136[5] = 215857758;
        goto LABEL_81;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002d4b4  push    rbp
0x14002d4b6  push    rbx
0x14002d4b7  push    rsi
0x14002d4b8  push    rdi
0x14002d4b9  push    r12
0x14002d4bb  push    r13
0x14002d4bd  push    r14
0x14002d4bf  push    r15
0x14002d4c1  lea     rbp, [rsp-28h]
0x14002d4c6  sub     rsp, 128h
0x14002d4cd  mov     rax, cs:__security_cookie
0x14002d4d4  xor     rax, rsp
0x14002d4d7  mov     [rbp+60h+var_50], rax
0x14002d4db  mov     rax, gs:188h
0x14002d4e4  xor     r12d, r12d
0x14002d4e7  mov     r14, rcx
0x14002d4ea  mov     edi, 0CDDBA5Eh
0x14002d4ef  lea     esi, [r12+2]
0x14002d4f4  cmp     rax, [rcx+0A08h]
0x14002d4fb  jz      short loc_14002D561
0x14002d4fd  mov     rax, cs:KdDebuggerEnabled
0x14002d504  cmp     [rax], r12b
0x14002d507  jz      short loc_14002D561
0x14002d509  lea     rcx, aInitinternalbi; "InitInternalBitmaps is not called by th"...
0x14002d510  call    cs:__imp_DbgPrint
0x14002d517  nop     dword ptr [rax+rax+00h]
0x14002d51c  mov     ecx, esi
0x14002d51e  call    cs:__imp_WdLogSingleEntry0
0x14002d525  nop     dword ptr [rax+rax+00h]
0x14002d52a  mov     ebx, 685h
0x14002d52f  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002d535  call    cs:__imp_WdLogNewEntry5_WdError
0x14002d53c  nop     dword ptr [rax+rax+00h]
0x14002d541  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d548  mov     [rax+18h], rcx
0x14002d54c  mov     ecx, cs:dword_14003E570
0x14002d552  mov     [rax+20h], rcx
0x14002d556  mov     [rax+28h], rdi
0x14002d55a  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002d560  int     3; Trap to Debugger
0x14002d561  mov     rdx, r14
0x14002d564  mov     ecx, 4
0x14002d569  call    cs:__imp_WdLogSingleEntry1
0x14002d570  nop     dword ptr [rax+rax+00h]
0x14002d575  mov     ebx, 687h
0x14002d57a  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002d580  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14002d587  nop     dword ptr [rax+rax+00h]
0x14002d58c  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d593  mov     [rax+18h], rcx
0x14002d597  mov     ecx, cs:dword_14003E570
0x14002d59d  mov     [rax+20h], rcx
0x14002d5a1  mov     [rax+28h], rdi
0x14002d5a5  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002d5ab  mov     eax, [r14+0AB8h]
0x14002d5b2  test    al, 40h
0x14002d5b4  jz      short loc_14002D62A
0x14002d5b6  mov     rcx, [r14+0B50h]
0x14002d5bd  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14002d5c4  nop     dword ptr [rax+rax+00h]
0x14002d5c9  lea     rdi, [r14+20C8h]
0x14002d5d0  mov     rcx, rdi; this
0x14002d5d3  call    ?ResetCommandBuffer@CHwCommandBuffer@@QEAAXXZ; CHwCommandBuffer::ResetCommandBuffer(void)
0x14002d5d8  lea     rbx, [r14+2930h]
0x14002d5df  mov     rcx, rbx; this
0x14002d5e2  call    ?ResetCommandBuffer@CHwCommandBuffer@@QEAAXXZ; CHwCommandBuffer::ResetCommandBuffer(void)
0x14002d5e7  mov     rcx, [r14+0B50h]
0x14002d5ee  mov     [r14+3198h], rdi
0x14002d5f5  mov     [r14+31A0h], rbx
0x14002d5fc  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14002d603  nop     dword ptr [rax+rax+00h]
0x14002d608  mov     r8d, [r14+1C7Ch]; unsigned int
0x14002d60f  mov     edx, [r14+1C78h]; unsigned int
0x14002d616  mov     rcx, [r14+1578h]; this
0x14002d61d  call    ?InitStagingVidMem@CddBitmapStagingVidMem@@QEAAJII@Z; CddBitmapStagingVidMem::InitStagingVidMem(uint,uint)
0x14002d622  test    eax, eax
0x14002d624  js      loc_14002E5F4
0x14002d62a  mov     r8d, [r14+1C84h]; unsigned int
0x14002d631  lea     rcx, [r14+1580h]; this
0x14002d638  mov     edx, [r14+1C80h]; unsigned int
0x14002d63f  call    ?InitStagingPool@CStagingPoolBase@@QEAAJII@Z; CStagingPoolBase::InitStagingPool(uint,uint)
0x14002d644  mov     ebx, eax
0x14002d646  test    eax, eax
0x14002d648  js      loc_14002E5F4
0x14002d64e  test    dword ptr [r14+76Ch], 20000000h
0x14002d659  jz      short loc_14002D686
0x14002d65b  mov     r8d, [r14+1C84h]
0x14002d662  lea     rcx, [r14+18B0h]; this
0x14002d669  mov     edx, [r14+1C80h]
0x14002d670  shr     r8d, 2; unsigned int
0x14002d674  shr     edx, 2; unsigned int
0x14002d677  call    ?InitStagingPool@CStagingPoolBase@@QEAAJII@Z; CStagingPoolBase::InitStagingPool(uint,uint)
0x14002d67c  mov     ebx, eax
0x14002d67e  test    eax, eax
0x14002d680  js      loc_14002E5F4
0x14002d686  bts     dword ptr [r14+0AB8h], 8
0x14002d68f  mov     eax, [r14+0AB8h]
0x14002d696  test    al, 40h
0x14002d698  jz      loc_14002E5F2
0x14002d69e  mov     [rsp+160h+var_108], 1
0x14002d6a3  lea     rax, [rsp+160h+var_F0]
0x14002d6a8  mov     [rsp+160h+var_110], rax
0x14002d6ad  lea     r15, [r14+1C38h]
0x14002d6b4  mov     [rsp+160h+var_118], r12
0x14002d6b9  lea     rax, [rsp+160h+var_E8]
0x14002d6be  mov     [rsp+160h+var_120], rax
0x14002d6c3  mov     r13d, 1Ch
0x14002d6c9  mov     [rsp+160h+var_128], r15
0x14002d6ce  mov     ebx, r12d
0x14002d6d1  mov     [rsp+160h+var_130], ebx
0x14002d6d5  xor     edx, edx
0x14002d6d7  mov     [rsp+160h+var_138], r13d
0x14002d6dc  mov     r8d, 200h
0x14002d6e2  lea     r9d, [r13-0Ch]
0x14002d6e6  mov     dword ptr [rsp+160h+var_140], 4
0x14002d6ee  mov     rcx, r14
0x14002d6f1  mov     [rsp+160h+var_E8], r12d
0x14002d6f6  mov     [rsp+160h+var_F0], r12d
0x14002d6fb  call    ?CreateAllocation@CDDPDEV@@QEAAJPEAVCddBitmap@@IIW4_D3DKMDT_GDISURFACETYPE@@W4_D3DDDIFORMAT@@U_DXGKCDD_CREATE_ALLOCATION_FLAGS@@PEAI4PEAPEAX4E@Z; CDDPDEV::CreateAllocation(CddBitmap *,uint,uint,_D3DKMDT_GDISURFACETYPE,_D3DDDIFORMAT,_DXGKCDD_CREATE_ALLOCATION_FLAGS,uint *,uint *,void * *,uint *,uchar)
0x14002d700  mov     edi, eax
0x14002d702  test    eax, eax
0x14002d704  jns     short loc_14002D757
0x14002d706  lea     ecx, [r13-16h]
0x14002d70a  call    cs:__imp_WdLogSingleEntry0
0x14002d711  nop     dword ptr [rax+rax+00h]
0x14002d716  mov     ebx, 6CCh
0x14002d71b  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002d721  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002d728  nop     dword ptr [rax+rax+00h]
0x14002d72d  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d734  mov     [rax+18h], rcx
0x14002d738  mov     ecx, cs:dword_14003E570
0x14002d73e  mov     [rax+20h], rcx
0x14002d742  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002d74a  mov     eax, edi
0x14002d74c  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002d752  jmp     loc_14002E5F4
0x14002d757  mov     [rsp+160h+var_108], 1
0x14002d75c  lea     rax, [rsp+160h+var_F0]
0x14002d761  mov     [rsp+160h+var_110], rax
0x14002d766  mov     edi, 200h
0x14002d76b  mov     [rsp+160h+var_118], r12
0x14002d770  lea     rax, [rsp+160h+var_E8]
0x14002d775  mov     [rsp+160h+var_120], rax
0x14002d77a  mov     r9d, 10h
0x14002d780  lea     rax, [rsp+160h+var_EC]
0x14002d785  mov     [rsp+160h+var_EC], r12d
0x14002d78a  mov     [rsp+160h+var_128], rax
0x14002d78f  mov     r8d, edi
0x14002d792  mov     [rsp+160h+var_130], ebx
0x14002d796  xor     edx, edx
0x14002d798  mov     [rsp+160h+var_138], r13d
0x14002d79d  mov     rcx, r14
0x14002d7a0  mov     dword ptr [rsp+160h+var_140], esi
0x14002d7a4  call    ?CreateAllocation@CDDPDEV@@QEAAJPEAVCddBitmap@@IIW4_D3DKMDT_GDISURFACETYPE@@W4_D3DDDIFORMAT@@U_DXGKCDD_CREATE_ALLOCATION_FLAGS@@PEAI4PEAPEAX4E@Z; CDDPDEV::CreateAllocation(CddBitmap *,uint,uint,_D3DKMDT_GDISURFACETYPE,_D3DDDIFORMAT,_DXGKCDD_CREATE_ALLOCATION_FLAGS,uint *,uint *,void * *,uint *,uchar)
0x14002d7a9  mov     ebx, eax
0x14002d7ab  test    eax, eax
0x14002d7ad  jns     short loc_14002D7F9
0x14002d7af  mov     ecx, 4
0x14002d7b4  call    cs:__imp_WdLogSingleEntry0
0x14002d7bb  nop     dword ptr [rax+rax+00h]
0x14002d7c0  mov     edi, 6DCh
0x14002d7c5  mov     cs:WdLogGlobalForLineNumber, edi
0x14002d7cb  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14002d7d2  nop     dword ptr [rax+rax+00h]
0x14002d7d7  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d7de  mov     [rax+18h], rcx
0x14002d7e2  mov     ecx, cs:dword_14003E570
0x14002d7e8  mov     [rax+20h], rcx
0x14002d7ec  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002d7f4  jmp     loc_14002E5EC
0x14002d7f9  cmp     [rsp+160h+var_F0], edi
0x14002d7fd  jnb     short loc_14002D84E
0x14002d7ff  mov     ecx, 1
0x14002d804  call    cs:__imp_WdLogSingleEntry0
0x14002d80b  nop     dword ptr [rax+rax+00h]
0x14002d810  mov     ebx, 6E0h
0x14002d815  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002d81b  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002d822  nop     dword ptr [rax+rax+00h]
0x14002d827  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d82e  mov     r13d, 0CDDBA5Eh
0x14002d834  mov     [rax+18h], rcx
0x14002d838  mov     ecx, cs:dword_14003E570
0x14002d83e  mov     [rax+20h], rcx
0x14002d842  mov     [rax+28h], r13
0x14002d846  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002d84c  jmp     short loc_14002D854
0x14002d84e  mov     r13d, 0CDDBA5Eh
0x14002d854  mov     edx, [rsp+160h+var_EC]; unsigned int
0x14002d858  lea     r8, [rsp+160h+pGammaTable]; unsigned __int8 **
0x14002d85d  mov     rcx, r14; this
0x14002d860  mov     [rsp+160h+pGammaTable], r12
0x14002d865  call    ?LockAllocation@CDDPDEV@@QEAAJIPEAPEAE@Z; CDDPDEV::LockAllocation(uint,uchar * *)
0x14002d86a  mov     ebx, eax
0x14002d86c  test    eax, eax
0x14002d86e  jns     short loc_14002D8C8
0x14002d870  mov     ecx, 4
0x14002d875  call    cs:__imp_WdLogSingleEntry0
0x14002d87c  nop     dword ptr [rax+rax+00h]
0x14002d881  mov     edi, 6E8h
0x14002d886  mov     cs:WdLogGlobalForLineNumber, edi
0x14002d88c  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14002d893  nop     dword ptr [rax+rax+00h]
0x14002d898  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002d89f  mov     rcx, r14; this
0x14002d8a2  mov     [rax+18h], rdx
0x14002d8a6  mov     edx, cs:dword_14003E570
0x14002d8ac  mov     [rax+20h], rdx
0x14002d8b0  mov     [rax+28h], r13
0x14002d8b4  mov     edx, [rsp+160h+var_EC]; unsigned int
0x14002d8b8  mov     cs:WdLogGlobalForLineNumber, edi
0x14002d8be  call    ?DestroyAllocation@CDDPDEV@@QEAAJI@Z; CDDPDEV::DestroyAllocation(uint)
0x14002d8c3  jmp     loc_14002E5F2
0x14002d8c8  mov     rbx, [rsp+160h+pGammaTable]
0x14002d8cd  lea     r8, [rsp+160h+pInverseGammaTable]; pInverseGammaTable
0x14002d8d2  lea     rdx, [rsp+160h+pGammaTable]; pGammaTable
0x14002d8d7  mov     [rsp+160h+pGammaTable], r12
0x14002d8dc  mov     ecx, 3E8h; ulGamma
0x14002d8e1  mov     [rsp+160h+pInverseGammaTable], r12
0x14002d8e6  call    cs:__imp_EngCTGetGammaTable
0x14002d8ed  nop     dword ptr [rax+rax+00h]
0x14002d8f2  mov     rcx, [rsp+160h+pGammaTable]
0x14002d8f7  mov     rax, rbx
0x14002d8fa  mov     rdx, rsi
0x14002d8fd  mov     edi, 80h
0x14002d902  movups  xmm0, xmmword ptr [rcx]
0x14002d905  movups  xmmword ptr [rax], xmm0
0x14002d908  movups  xmm1, xmmword ptr [rcx+10h]
0x14002d90c  movups  xmmword ptr [rax+10h], xmm1
0x14002d910  movups  xmm0, xmmword ptr [rcx+20h]
0x14002d914  movups  xmmword ptr [rax+20h], xmm0
0x14002d918  movups  xmm1, xmmword ptr [rcx+30h]
0x14002d91c  movups  xmmword ptr [rax+30h], xmm1
0x14002d920  movups  xmm0, xmmword ptr [rcx+40h]
0x14002d924  movups  xmmword ptr [rax+40h], xmm0
0x14002d928  movups  xmm1, xmmword ptr [rcx+50h]
0x14002d92c  movups  xmmword ptr [rax+50h], xmm1
0x14002d930  movups  xmm0, xmmword ptr [rcx+60h]
0x14002d934  movups  xmmword ptr [rax+60h], xmm0
0x14002d938  movups  xmm1, xmmword ptr [rcx+70h]
0x14002d93c  add     rcx, rdi
0x14002d93f  movups  xmmword ptr [rax+70h], xmm1
0x14002d943  add     rax, rdi
0x14002d946  sub     rdx, 1
0x14002d94a  jnz     short loc_14002D902
0x14002d94c  mov     rcx, [rsp+160h+pInverseGammaTable]
0x14002d951  lea     rax, [rbx+100h]
0x14002d958  mov     rdx, rsi
0x14002d95b  movups  xmm0, xmmword ptr [rcx]
0x14002d95e  movups  xmmword ptr [rax], xmm0
0x14002d961  movups  xmm1, xmmword ptr [rcx+10h]
0x14002d965  movups  xmmword ptr [rax+10h], xmm1
0x14002d969  movups  xmm0, xmmword ptr [rcx+20h]
0x14002d96d  movups  xmmword ptr [rax+20h], xmm0
0x14002d971  movups  xmm1, xmmword ptr [rcx+30h]
0x14002d975  movups  xmmword ptr [rax+30h], xmm1
0x14002d979  movups  xmm0, xmmword ptr [rcx+40h]
0x14002d97d  movups  xmmword ptr [rax+40h], xmm0
0x14002d981  movups  xmm1, xmmword ptr [rcx+50h]
0x14002d985  movups  xmmword ptr [rax+50h], xmm1
0x14002d989  movups  xmm0, xmmword ptr [rcx+60h]
0x14002d98d  movups  xmmword ptr [rax+60h], xmm0
0x14002d991  movups  xmm1, xmmword ptr [rcx+70h]
0x14002d995  add     rcx, rdi
0x14002d998  movups  xmmword ptr [rax+70h], xmm1
0x14002d99c  add     rax, rdi
0x14002d99f  sub     rdx, 1
0x14002d9a3  jnz     short loc_14002D95B
0x14002d9a5  mov     eax, [rsp+160h+var_F0]
0x14002d9a9  lea     r8, [rsp+160h+pGammaTable]; pInverseGammaTable
0x14002d9ae  add     rbx, rax
0x14002d9b1  mov     [rsp+160h+pInverseGammaTable], r12
0x14002d9b6  lea     rdx, [rsp+160h+pInverseGammaTable]; pGammaTable
0x14002d9bb  mov     [rsp+160h+pGammaTable], r12
0x14002d9c0  mov     ecx, 44Ch; ulGamma
0x14002d9c5  call    cs:__imp_EngCTGetGammaTable
0x14002d9cc  nop     dword ptr [rax+rax+00h]
0x14002d9d1  mov     rcx, [rsp+160h+pInverseGammaTable]
0x14002d9d6  mov     rax, rbx
0x14002d9d9  mov     rdx, rsi
0x14002d9dc  movups  xmm0, xmmword ptr [rcx]
0x14002d9df  movups  xmmword ptr [rax], xmm0
0x14002d9e2  movups  xmm1, xmmword ptr [rcx+10h]
0x14002d9e6  movups  xmmword ptr [rax+10h], xmm1
0x14002d9ea  movups  xmm0, xmmword ptr [rcx+20h]
0x14002d9ee  movups  xmmword ptr [rax+20h], xmm0
0x14002d9f2  movups  xmm1, xmmword ptr [rcx+30h]
0x14002d9f6  movups  xmmword ptr [rax+30h], xmm1
0x14002d9fa  movups  xmm0, xmmword ptr [rcx+40h]
0x14002d9fe  movups  xmmword ptr [rax+40h], xmm0
0x14002da02  movups  xmm1, xmmword ptr [rcx+50h]
0x14002da06  movups  xmmword ptr [rax+50h], xmm1
0x14002da0a  movups  xmm0, xmmword ptr [rcx+60h]
0x14002da0e  movups  xmmword ptr [rax+60h], xmm0
0x14002da12  movups  xmm1, xmmword ptr [rcx+70h]
0x14002da16  add     rcx, rdi
0x14002da19  movups  xmmword ptr [rax+70h], xmm1
0x14002da1d  add     rax, rdi
0x14002da20  sub     rdx, 1
  ... truncated ...
```
