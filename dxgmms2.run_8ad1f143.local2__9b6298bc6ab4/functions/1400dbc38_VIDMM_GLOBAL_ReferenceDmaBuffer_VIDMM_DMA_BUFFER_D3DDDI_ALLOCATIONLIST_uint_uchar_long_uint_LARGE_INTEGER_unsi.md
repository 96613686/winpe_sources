# VIDMM_GLOBAL::ReferenceDmaBuffer(VIDMM_DMA_BUFFER *,_D3DDDI_ALLOCATIONLIST *,uint,uchar,long,uint *,_LARGE_INTEGER *,unsigned __int64 *,VIDMM_ALLOC * *,VIDMM_PRIMARIES_REFERENCES *,DXGALLOCATION * *)

- ea: `0x1400dbc38`
- end: `0x1400dc8cc`
- name: `?ReferenceDmaBuffer@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_DMA_BUFFER@@PEAU_D3DDDI_ALLOCATIONLIST@@IEJPEAIPEAT_LARGE_INTEGER@@PEA_KPEAPEAUVIDMM_ALLOC@@PEAUVIDMM_PRIMARIES_REFERENCES@@PEAPEAVDXGALLOCATION@@@Z`
- size: `3220`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_DMA_BUFFER *@<rdx>, struct _D3DDDI_ALLOCATIONLIST *@<r8>, unsigned int@<r9d>, char, int, unsigned int *, union _LARGE_INTEGER *, unsigned __int64 *, struct VIDMM_ALLOC **, struct VIDMM_PRIMARIES_REFERENCES *, struct DXGALLOCATION **)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x140032930`

## callees

- `0x1400045ec`
- `0x1400204c0`
- `0x14002f510`
- `0x14002fbac`
- `0x14002fd94`
- `0x1400316d0`
- `0x140032b14`
- `0x140032dd8`
- `0x140033fa8`
- `0x140034428`
- `0x140034ad8`
- `0x140046580`
- `0x140058680`
- `0x140058760`
- `0x1400dbc38`
- `0x1400dc8d4`
- `0x140109dfc`
- `0x14010a208`
- `0x14010c9b8`
- `0x14010db5c`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x1400dbd20`
- `ntoskrnl!MmIsUserAddress` at `0x1400dbd20`
- `ntoskrnl!KeStackAttachProcess` at `0x1400dc48c`
- `ntoskrnl!KeStackAttachProcess` at `0x1400dc48c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400dc517`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400dc517`
- `watchdog!WdLogSingleEntry3` at `0x1400dbe6b`
- `watchdog!WdLogSingleEntry3` at `0x1400dbe6b`
- `watchdog!WdLogSingleEntry4` at `0x1400dc282`
- `watchdog!WdLogSingleEntry4` at `0x1400dc282`
- `watchdog!WdLogSingleEntry2` at `0x1400dc145`
- `watchdog!WdLogSingleEntry2` at `0x1400dc2d9`
- `watchdog!WdLogSingleEntry2` at `0x1400dc337`
- `watchdog!WdLogSingleEntry2` at `0x1400dc5df`
- `watchdog!WdLogSingleEntry2` at `0x1400dc626`
- `watchdog!WdLogSingleEntry2` at `0x1400dc145`
- `watchdog!WdLogSingleEntry2` at `0x1400dc2d9`
- `watchdog!WdLogSingleEntry2` at `0x1400dc337`
- `watchdog!WdLogSingleEntry2` at `0x1400dc5df`
- `watchdog!WdLogSingleEntry2` at `0x1400dc626`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dc1fe`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dc220`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dc1fe`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400dc220`
- `watchdog!WdLogSingleEntry5` at `0x1400dc696`
- `watchdog!WdLogSingleEntry5` at `0x1400dc696`
- `watchdog!WdLogSingleEntry0` at `0x1400dc127`
- `watchdog!WdLogSingleEntry0` at `0x1400dc127`
- `watchdog!WdLogSingleEntry1` at `0x1400dc4dd`
- `watchdog!WdLogSingleEntry1` at `0x1400dc559`
- `watchdog!WdLogSingleEntry1` at `0x1400dc6c1`
- `watchdog!WdLogSingleEntry1` at `0x1400dc4dd`
- `watchdog!WdLogSingleEntry1` at `0x1400dc559`
- `watchdog!WdLogSingleEntry1` at `0x1400dc6c1`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400dc66c`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400dc1f2`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400dc214`
- `dxgkrnl!DxgkVidMmAllowFailOnOfferReclaimErrors` at `0x1400dc2be`
- `dxgkrnl!DxgkVidMmAllowFailOnOfferReclaimErrors` at `0x1400dc2be`

## string_xrefs

- `0x1400dbea4`: `Driver must reference only a single, writeable history buffer. Alloc:%I64X, CurrentHistoryBuffer:%I64X, Writeable:%d\n`
- `0x1400dc583`: `Failed to reference DMA buffer: Allocation is not requested to be resident. Alloc=0x%p`
- `0x1400dc6fb`: `Exception occurred accessing user mode allocation list, returning Status=0x%I64x`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::ReferenceDmaBuffer(
        VIDMM_GLOBAL *this,
        union _LARGE_INTEGER *a2,
        struct _D3DDDI_ALLOCATIONLIST *a3,
        unsigned int a4,
        char a5,
        unsigned int a6,
        unsigned int *a7,
        union _LARGE_INTEGER *a8,
        union _LARGE_INTEGER *a9,
        struct VIDMM_ALLOC **a10,
        struct VIDMM_PRIMARIES_REFERENCES *a11,
        struct DXGALLOCATION **a12)
{
  __int64 *QuadPart; // r12
  union _LARGE_INTEGER v15; // rbx
  char IsUserAddress; // r8
  unsigned int v17; // edx
  union _LARGE_INTEGER v18; // rax
  __int64 v19; // r10
  unsigned int v20; // r13d
  _QWORD *v21; // rax
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // r8
  struct DXGALLOCATION *v24; // r15
  __int64 v25; // r15
  __int64 v26; // r12
  _DWORD *v27; // rcx
  __int64 v28; // rdx
  int v29; // ecx
  int v30; // r8d
  unsigned int v31; // ebx
  unsigned __int64 *v32; // rcx
  struct VIDMM_PRIMARIES_REFERENCES *v33; // rdx
  char v34; // dl
  unsigned __int64 *v35; // rax
  unsigned int v36; // eax
  union _LARGE_INTEGER v37; // rdx
  unsigned __int64 AllocGpuVirtualAddress; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // ecx
  int v43; // r8d
  int v44; // ebx
  __int64 v45; // rcx
  int v46; // ecx
  int v47; // r8d
  __int64 v48; // rbx
  int v49; // ecx
  int v50; // r8d
  union _LARGE_INTEGER v52; // rax
  unsigned int *v53; // rbx
  union _LARGE_INTEGER *v54; // r8
  union _LARGE_INTEGER v55; // rdx
  __int64 v56; // rcx
  signed __int32 v57[8]; // [rsp+0h] [rbp-188h] BYREF
  char v58; // [rsp+50h] [rbp-138h]
  char v59; // [rsp+51h] [rbp-137h]
  int v60; // [rsp+54h] [rbp-134h]
  unsigned __int64 *p_QuadPart; // [rsp+58h] [rbp-130h]
  __int64 *v62; // [rsp+60h] [rbp-128h]
  unsigned int v63; // [rsp+68h] [rbp-120h]
  unsigned __int64 v64; // [rsp+70h] [rbp-118h] BYREF
  int v65; // [rsp+78h] [rbp-110h] BYREF
  unsigned int v66; // [rsp+7Ch] [rbp-10Ch]
  struct VIDMM_PRIMARIES_REFERENCES *v67; // [rsp+80h] [rbp-108h]
  struct VIDMM_LOCAL_ALLOC *v68; // [rsp+88h] [rbp-100h]
  void *Src; // [rsp+90h] [rbp-F8h]
  __int64 v70; // [rsp+98h] [rbp-F0h]
  __int64 v71; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-E0h]
  DXGFASTMUTEX *v73; // [rsp+B0h] [rbp-D8h]
  union _LARGE_INTEGER v74; // [rsp+B8h] [rbp-D0h]
  struct VIDMM_ALLOC **v75; // [rsp+C0h] [rbp-C8h]
  union _LARGE_INTEGER *v76; // [rsp+C8h] [rbp-C0h]
  __int64 *v77; // [rsp+D0h] [rbp-B8h]
  struct DXGALLOCATION **v78; // [rsp+D8h] [rbp-B0h]
  __int64 v79; // [rsp+E0h] [rbp-A8h]
  struct DXGPROCESS *Current; // [rsp+E8h] [rbp-A0h]
  unsigned int *v81; // [rsp+F0h] [rbp-98h]
  unsigned __int64 *v82; // [rsp+F8h] [rbp-90h]
  _QWORD *v83; // [rsp+100h] [rbp-88h]
  union _LARGE_INTEGER v84; // [rsp+108h] [rbp-80h]
  struct _KAPC_STATE ApcState; // [rsp+110h] [rbp-78h] BYREF

  v66 = a4;
  Src = a3;
  v76 = a8;
  v67 = a11;
  v81 = a7;
  p_QuadPart = (unsigned __int64 *)&a9->QuadPart;
  v82 = (unsigned __int64 *)&a9->QuadPart;
  v75 = a10;
  v78 = a12;
  v63 = 0;
  QuadPart = (__int64 *)a2[12].QuadPart;
  v62 = QuadPart;
  v77 = QuadPart;
  v15 = a2[13];
  v74 = v15;
  Current = DXGPROCESS::GetCurrent();
  v79 = *(_QWORD *)(a2[16].QuadPart + 8);
  IsUserAddress = MmIsUserAddress(Src);
  v59 = IsUserAddress;
  if ( a9 )
    *a9 = a2[11];
  *v75 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 826);
  v17 = v66;
  _InterlockedAdd((volatile signed __int32 *)this + 827, v66);
  if ( v66 > *((_DWORD *)this + 828) )
    _InterlockedExchange((volatile __int32 *)this + 828, v66);
  a2[3].HighPart |= 4u;
  v18 = *(union _LARGE_INTEGER *)(*(_QWORD *)a2[16].QuadPart + 56LL);
  _InterlockedOr(v57, 0);
  a2[18] = v18;
  *(_DWORD *)a11 = 0;
  v72 = 0;
  v19 = 0;
  v70 = 0;
  v20 = 0;
  v63 = 0;
  v21 = Src;
  while ( v20 < v17 )
  {
    v64 = 0;
    if ( IsUserAddress )
    {
      RtlCopyFromUser(&v64, v21, 8u);
      v22 = v64;
      v19 = v70;
    }
    else
    {
      v22 = *v21;
      v64 = v22;
    }
    if ( (_DWORD)v22 )
    {
      v23 = v20;
      v24 = v78[v20];
      if ( !v24 )
      {
        WdLogSingleEntry2(2, (unsigned int)v22, v20);
        WdLogGlobalForLineNumber = 8958;
        v31 = -1071775468;
        v60 = -1071775468;
        v32 = p_QuadPart;
LABEL_90:
        if ( !v32 && v20 )
        {
          do
          {
            if ( *--QuadPart )
              RemoveDMAReferences(*QuadPart, a6);
            --v20;
          }
          while ( v20 );
        }
        return v31;
      }
      v25 = *((_QWORD *)v24 + 3);
      v26 = **(_QWORD **)v25;
      v68 = *(struct VIDMM_LOCAL_ALLOC **)v26;
      v73 = *(DXGFASTMUTEX **)(*((_QWORD *)this + 4560) + 8LL * ((*((_DWORD *)v68 + 15) >> 2) & 0x3F));
      v27 = *(_DWORD **)(v26 + 384);
      v28 = *v27 >> 14;
      if ( (*v27 & 0x4000) != 0 )
      {
        if ( v19 || (v27 = (_DWORD *)HIDWORD(v22), (v22 & 0x100000000LL) == 0) )
        {
          WdLogSingleEntry3(1, v25, v19, BYTE4(v22) & 1);
          WdLogGlobalForLineNumber = 9001;
          DxgkLogInternalTriageEvent(
            v29,
            0x40000,
            v30,
            (unsigned int)L"Driver must reference only a single, writeable history buffer. Alloc:%I64X, CurrentHistoryBuff"
                           "er:%I64X, Writeable:%d\n",
            v25,
            v70,
            BYTE4(v64) & 1,
            0);
          v31 = -1071775482;
          v60 = -1071775482;
          QuadPart = v62;
          v32 = p_QuadPart;
          goto LABEL_90;
        }
        v70 = v25;
      }
      if ( *(_BYTE *)(v26 + 41) )
      {
        if ( g_IsInternalReleaseOrDbg )
        {
          WdLogNewEntry5_WdTrace(v27, v28);
          WdLogGlobalForLineNumber = 9016;
          v41 = WdLogNewEntry5_WdTrace(v40, v39);
          *(_QWORD *)(v41 + 24) = a2;
          *(_QWORD *)(v41 + 32) = v25;
          WdLogGlobalForLineNumber = 9017;
        }
        v31 = -1071775482;
        v60 = -1071775482;
        QuadPart = v62;
        v32 = p_QuadPart;
        goto LABEL_90;
      }
      if ( *(_QWORD *)(v25 + 8) != v79 && (*((_DWORD *)Current + 102) & 0x100) == 0 )
      {
        WdLogSingleEntry4(2, v79, v25, v20, *(_QWORD *)(v25 + 8));
        WdLogGlobalForLineNumber = 9028;
        v31 = -1071775467;
        v60 = -1071775467;
        QuadPart = v62;
        v32 = p_QuadPart;
        goto LABEL_90;
      }
      if ( *(_WORD *)(*(_QWORD *)(v25 + 96) + 8LL) && a5 )
      {
        if ( DxgkVidMmAllowFailOnOfferReclaimErrors() )
        {
          WdLogSingleEntry2(1, a2, v25);
          WdLogGlobalForLineNumber = 9043;
          DxgkLogInternalTriageEvent(
            v42,
            0x40000,
            v43,
            (unsigned int)L"DMA buffer 0x%p references an allocation 0x%p that is offered.\n",
            (__int64)a2,
            v25,
            0,
            0);
          v31 = -1071775466;
          v60 = -1071775466;
          QuadPart = v62;
          v32 = p_QuadPart;
          goto LABEL_90;
        }
        WdLogSingleEntry2(2, a2, v25);
        WdLogGlobalForLineNumber = 9049;
      }
      *v62 = v25;
      *(_QWORD *)v15.QuadPart = *(_QWORD *)(*(_QWORD *)(v25 + 16) + 32LL);
      if ( (v64 & 0x100000000LL) != 0 && *(_BYTE *)(v25 + 24) && *(int *)(*((_QWORD *)this + 3) + 2848LL) >= 4608 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 9068;
        WdLogSingleEntry2(3, a2, v25);
        WdLogGlobalForLineNumber = 9069;
        v31 = -1073741790;
        v60 = -1073741790;
        QuadPart = v62;
        v32 = p_QuadPart;
        goto LABEL_90;
      }
      *(_DWORD *)(v15.QuadPart + 8) = BYTE4(v64) & 1 | *(_DWORD *)(v15.QuadPart + 8) & 0xFFFFFFFE;
      if ( (v64 & 0x100000000LL) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)this + 830);
      v33 = v67;
      if ( (*(_DWORD *)(v15.QuadPart + 8) & 1) != 0 && (**(_DWORD **)(v26 + 384) & 0x200000) != 0 )
        *((_DWORD *)v67 + 35) |= 1u;
      if ( (*(_DWORD *)(v15.QuadPart + 8) & 1) != 0
        && (**(_DWORD **)(v26 + 384) >> 23) & 0xFFFFFF00
         | ((unsigned __int16)**(_DWORD **)(v26 + 384)
          | (unsigned __int16)((unsigned int)(**(_DWORD **)(v26 + 384) | (**(_DWORD **)(v26 + 384) >> 11)) >> 11))
         & 0x100 )
      {
        if ( *(_DWORD *)v33 >= 0x10u )
        {
          _InterlockedIncrement((volatile signed __int32 *)this + 836);
        }
        else
        {
          InterlockedCounterWithHistoryRelease::Increment(
            (InterlockedCounterWithHistoryRelease *)(v25 + 104),
            (unsigned int *)v33 + 34,
            v23);
          v33 = v67;
          *((_QWORD *)v67 + *(unsigned int *)v67 + 1) = v25;
        }
        ++*(_DWORD *)v33;
      }
      v34 = 0;
      v58 = 0;
      v71 = 0;
      v65 = 0;
      v35 = p_QuadPart;
      if ( !p_QuadPart )
      {
        if ( (*((_DWORD *)this + 786) & 0x40) == 0 )
        {
          v34 = (*(__int64 (__fastcall **)(DXGFASTMUTEX *, struct VIDMM_LOCAL_ALLOC *, int *, __int64 *, _QWORD))(*(_QWORD *)v73 + 48LL))(
                  v73,
                  v68,
                  &v65,
                  &v71,
                  0);
          v58 = v34;
        }
        v35 = p_QuadPart;
      }
      if ( v34 )
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 833);
        *(_QWORD *)(v15.QuadPart + 16) = v71;
        *(_DWORD *)(v15.QuadPart + 8) = *(_DWORD *)(v15.QuadPart + 8) & 0xFFFFFFC1 | (2 * (v65 & 0x1F));
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 834);
        *(_DWORD *)(v15.QuadPart + 8) &= 0xFFFFFFC1;
        if ( v35 )
        {
          v37 = a2[16];
          if ( (*(_DWORD *)(v37.QuadPart + 36) & 0x20) != 0 )
            AllocGpuVirtualAddress = *(_QWORD *)(v25 + 680);
          else
            AllocGpuVirtualAddress = VidMmGetAllocGpuVirtualAddress(
                                       (const struct VIDMM_ALLOC *)v25,
                                       *(_DWORD *)(v37.QuadPart + 32));
          *(_QWORD *)(v15.QuadPart + 16) = AllocGpuVirtualAddress;
        }
        else
        {
          *(_QWORD *)(v15.QuadPart + 16) = 0;
        }
        a2[3].HighPart &= ~4u;
        if ( (VIDMM_GLOBAL::_Config & 1) == 0
          && (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 4) == 0
          && (*(_BYTE *)(v26 + 42) || (*(_DWORD *)(v26 + 24) & 0x10) != 0) )
        {
          v73 = (DXGFASTMUTEX *)(v26 + 136);
          DXGFASTMUTEX::Acquire((DXGFASTMUTEX *)(v26 + 136));
          v72 = v26;
          if ( !VidMmGetFullPfnArray((const struct VIDMM_GLOBAL_ALLOC *)v26)
            && (*((_DWORD *)v68 + 16) & 1) == 0
            && (**(_DWORD **)(v26 + 384) & 0x40000000) == 0
            && (int)VIDMM_GLOBAL::ChargePinnedBackingStore(this, *((_QWORD *)v68 + 2)) >= 0 )
          {
            v44 = 0;
            memset(&ApcState, 0, sizeof(ApcState));
            v45 = *(_QWORD *)(v26 + 48);
            if ( v45 )
            {
              KeStackAttachProcess(*(PRKPROCESS *)(*(_QWORD *)(v45 + 8) + 16LL), &ApcState);
              v44 = 1;
            }
            if ( (int)VIDMM_GLOBAL::ProbeAndLockAllocation(
                        this,
                        v68,
                        (struct VIDMM_GLOBAL_ALLOC *)v26,
                        0,
                        *((_QWORD *)v68 + 2),
                        0) < 0 )
            {
              WdLogSingleEntry1(2, v26);
              WdLogGlobalForLineNumber = 9242;
              VIDMM_GLOBAL::ReturnPinnedBackingStore(this, *((_QWORD *)v68 + 2));
            }
            else
            {
              VidMmiAddProbeAndLockReference((struct VIDMM_GLOBAL_ALLOC *)v26);
              *(_DWORD *)(v26 + 32) |= 2u;
            }
            if ( v44 )
              KeUnstackDetachProcess(&ApcState);
          }
          v72 = 0;
          DXGFASTMUTEX::Release(v73);
        }
      }
      if ( !p_QuadPart )
        AddDMAReferences(v25, a6, v23);
      if ( !*(_DWORD *)(v25 + 688)
        && (*(_BYTE *)(v25 + 25) & 1) == 0
        && ((*((_BYTE *)this + 37224) & 0x20) == 0 || (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 0x10) == 0) )
      {
        WdLogSingleEntry1(1, v25);
        WdLogGlobalForLineNumber = 9278;
        DxgkLogInternalTriageEvent(
          v46,
          0x40000,
          v47,
          (unsigned int)L"Failed to reference DMA buffer: Allocation is not requested to be resident. Alloc=0x%p",
          v25,
          0,
          0,
          0);
        v31 = -1073741823;
        v60 = -1073741823;
        VidSchMarkDeviceAsError(*(_QWORD *)(*(_QWORD *)(v25 + 8) + 32LL), 16);
        if ( !p_QuadPart )
          RemoveDMAReferences(v25, a6);
        QuadPart = v62;
        v32 = p_QuadPart;
        goto LABEL_90;
      }
      v36 = (HIDWORD(v64) >> 2) & 7;
      if ( v36 )
      {
        v48 = v36;
        WdLogSingleEntry2(1, v25, v36);
        WdLogGlobalForLineNumber = 9300;
        DxgkLogInternalTriageEvent(
          v49,
          0x40000,
          v50,
          (unsigned int)L"Driver should not specify an offer priority for allocation lists in WDDMv2. Alloc=0x%I64X, OfferPriority=%d",
          v25,
          v48,
          0,
          0);
      }
      v15 = v74;
      QuadPart = v62;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 829);
      *QuadPart = 0;
      *(_OWORD *)v15.QuadPart = 0;
      *(_QWORD *)(v15.QuadPart + 16) = 0;
    }
    v62 = ++QuadPart;
    v77 = QuadPart;
    v21 = (char *)Src + 8;
    Src = v21;
    v83 = v21;
    v15.QuadPart += 24LL;
    v74 = v15;
    v84 = v15;
    v63 = ++v20;
    v19 = v70;
    v17 = v66;
    IsUserAddress = v59;
  }
  *v75 = (struct VIDMM_ALLOC *)v19;
  v52 = a2[7];
  v53 = v81;
  *v81 = 0;
  v54 = v76;
  if ( v52.QuadPart )
  {
    v76->QuadPart = 0;
    v55 = a2[6];
    if ( (**(_DWORD **)(v55.QuadPart + 384) & 0x8000) != 0 )
    {
      if ( (*((_DWORD *)this + 786) & 0x40) == 0 )
      {
        v56 = *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * *(unsigned int *)(a2[16].QuadPart + 32));
        (*(void (__fastcall **)(__int64, _QWORD, unsigned int *, union _LARGE_INTEGER *, _QWORD))(*(_QWORD *)v56 + 48LL))(
          v56,
          *(_QWORD *)v55.QuadPart,
          v53,
          v54,
          0);
      }
      if ( *v53 )
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 833);
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 834);
        a2[3].HighPart &= ~4u;
      }
    }
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))AddDMAReferences)((union _LARGE_INTEGER)a2[7].QuadPart, a6, v54);
  }
  else
  {
    *v76 = a2[10];
  }
  _InterlockedAdd((volatile signed __int32 *)&a2[4], a6);
  if ( (int)a6 > 1 )
    a2[3].HighPart |= 2u;
  if ( !p_QuadPart )
    a2[17].LowPart = v20;
  a2[2].LowPart = a6;
  if ( VidMmIsDmaBufferPrepatched((const struct VIDMM_DMA_BUFFER *)a2) )
    _InterlockedIncrement((volatile signed __int32 *)this + 835);
  LogReferenceAllocations(*(_QWORD *)(a2[16].QuadPart + 24), (_DWORD)a2, v20, a2[12].QuadPart, a2[13].QuadPart);
  return 0;
}

```

## disassembly

```asm
0x1400dbc38  push    rbx
0x1400dbc3a  push    rsi
0x1400dbc3b  push    rdi
0x1400dbc3c  push    r12
0x1400dbc3e  push    r13
0x1400dbc40  push    r14
0x1400dbc42  push    r15
0x1400dbc44  sub     rsp, 150h
0x1400dbc4b  mov     rax, cs:__security_cookie
0x1400dbc52  xor     rax, rsp
0x1400dbc55  mov     [rsp+188h+var_48], rax
0x1400dbc5d  mov     [rsp+188h+var_10C], r9d
0x1400dbc62  mov     [rsp+188h+Src], r8
0x1400dbc6a  mov     rsi, rdx
0x1400dbc6d  mov     r14, rcx
0x1400dbc70  mov     rax, [rsp+188h+arg_38]
0x1400dbc78  mov     [rsp+188h+var_C0], rax
0x1400dbc80  mov     r13, [rsp+188h+arg_50]
0x1400dbc88  mov     [rsp+188h+var_108], r13
0x1400dbc90  mov     rax, [rsp+188h+arg_30]
0x1400dbc98  mov     [rsp+188h+var_98], rax
0x1400dbca0  mov     r15, [rsp+188h+arg_40]
0x1400dbca8  mov     [rsp+188h+var_130], r15
0x1400dbcad  mov     [rsp+188h+var_90], r15
0x1400dbcb5  mov     rax, [rsp+188h+arg_48]
0x1400dbcbd  mov     [rsp+188h+var_C8], rax
0x1400dbcc5  mov     rax, [rsp+188h+arg_58]
0x1400dbccd  mov     [rsp+188h+var_B0], rax
0x1400dbcd5  xor     edi, edi
0x1400dbcd7  mov     [rsp+188h+var_120], edi
0x1400dbcdb  mov     r12, [rdx+60h]
0x1400dbcdf  mov     [rsp+188h+var_128], r12
0x1400dbce4  mov     [rsp+188h+var_B8], r12
0x1400dbcec  mov     rbx, [rdx+68h]
0x1400dbcf0  mov     [rsp+188h+var_D0], rbx
0x1400dbcf8  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1400dbcfd  mov     [rsp+188h+var_A0], rax
0x1400dbd05  mov     rcx, [rsi+80h]
0x1400dbd0c  mov     rax, [rcx+8]
0x1400dbd10  mov     [rsp+188h+var_A8], rax
0x1400dbd18  mov     rcx, [rsp+188h+Src]
0x1400dbd20  call    cs:__imp_MmIsUserAddress
0x1400dbd27  nop     dword ptr [rax+rax+00h]
0x1400dbd2c  mov     r8b, al
0x1400dbd2f  mov     [rsp+188h+var_137], al
0x1400dbd33  test    r15, r15
0x1400dbd36  jnz     loc_1400DC7F6
0x1400dbd3c  mov     rcx, [rsp+188h+var_C8]
0x1400dbd44  mov     [rcx], rdi
0x1400dbd47  lock inc dword ptr [r14+0CE8h]
0x1400dbd4f  mov     edx, [rsp+188h+var_10C]
0x1400dbd53  lock add [r14+0CECh], edx
0x1400dbd5b  mov     eax, [r14+0CF0h]
0x1400dbd62  cmp     edx, eax
0x1400dbd64  ja      loc_1400DC802
0x1400dbd6a  or      dword ptr [rsi+1Ch], 4
0x1400dbd6e  mov     rax, [rsi+80h]
0x1400dbd75  mov     rcx, [rax]
0x1400dbd78  mov     rax, [rcx+38h]
0x1400dbd7c  lock or [rsp+188h+var_188], edi
0x1400dbd80  mov     [rsi+90h], rax
0x1400dbd87  mov     [r13+0], edi
0x1400dbd8b  mov     [rsp+188h+var_E0], rdi
0x1400dbd93  mov     r10, rdi
0x1400dbd96  mov     [rsp+188h+var_F0], rdi
0x1400dbd9e  mov     r13d, edi
0x1400dbda1  mov     [rsp+188h+var_120], edi
0x1400dbda5  mov     rax, [rsp+188h+Src]
0x1400dbdad  cmp     r13d, edx
0x1400dbdb0  jnb     loc_1400DC64F
0x1400dbdb6  mov     [rsp+188h+var_118], rdi
0x1400dbdbb  test    r8b, r8b
0x1400dbdbe  jz      loc_1400DBECD
0x1400dbdc4  mov     r8d, 8; Size
0x1400dbdca  mov     rdx, rax; Src
0x1400dbdcd  lea     rcx, [rsp+188h+var_118]; void *
0x1400dbdd2  call    RtlCopyFromUser
0x1400dbdd7  mov     rax, [rsp+188h+var_118]
0x1400dbddc  mov     r10, [rsp+188h+var_F0]
0x1400dbde4  test    eax, eax
0x1400dbde6  jz      loc_1400DC04E
0x1400dbdec  mov     r8d, r13d; unsigned __int64
0x1400dbdef  mov     rcx, [rsp+188h+var_B0]
0x1400dbdf7  mov     r15, [rcx+r8*8]
0x1400dbdfb  test    r15, r15
0x1400dbdfe  jz      loc_1400DC61F
0x1400dbe04  mov     r15, [r15+18h]
0x1400dbe08  mov     rcx, [r15]
0x1400dbe0b  mov     r12, [rcx]
0x1400dbe0e  mov     rcx, [r12]
0x1400dbe12  mov     [rsp+188h+var_100], rcx
0x1400dbe1a  mov     edx, [rcx+3Ch]
0x1400dbe1d  shr     rdx, 2
0x1400dbe21  and     edx, 3Fh
0x1400dbe24  mov     rcx, [r14+8E80h]
0x1400dbe2b  mov     r9, [rcx+rdx*8]
0x1400dbe2f  mov     [rsp+188h+var_D8], r9
0x1400dbe37  mov     rcx, [r12+180h]
0x1400dbe3f  mov     edx, [rcx]
0x1400dbe41  shr     edx, 0Eh
0x1400dbe44  test    dl, 1
0x1400dbe47  jz      loc_1400DBEDA
0x1400dbe4d  test    r10, r10
0x1400dbe50  jz      loc_1400DC1D5
0x1400dbe56  shr     rax, 20h
0x1400dbe5a  and     eax, 1
0x1400dbe5d  mov     r9d, eax
0x1400dbe60  mov     r8, r10
0x1400dbe63  mov     rdx, r15
0x1400dbe66  mov     ecx, 1
0x1400dbe6b  call    cs:__imp_WdLogSingleEntry3
0x1400dbe72  nop     dword ptr [rax+rax+00h]
0x1400dbe77  mov     cs:WdLogGlobalForLineNumber, 2329h
0x1400dbe81  mov     eax, dword ptr [rsp+188h+var_118+4]
0x1400dbe85  and     eax, 1
0x1400dbe88  mov     [rsp+188h+var_150], rdi
0x1400dbe8d  mov     [rsp+188h+var_158], rax
0x1400dbe92  mov     rax, [rsp+188h+var_F0]
0x1400dbe9a  mov     qword ptr [rsp+188h+var_160], rax
0x1400dbe9f  mov     [rsp+188h+var_168], r15
0x1400dbea4  lea     r9, aDriverMustRefe; "Driver must reference only a single, wr"...
0x1400dbeab  mov     edx, 40000h
0x1400dbeb0  call    DxgkLogInternalTriageEvent
0x1400dbeb5  mov     ebx, 0C01E0106h
0x1400dbeba  mov     [rsp+188h+var_134], ebx
0x1400dbebe  mov     r12, [rsp+188h+var_128]
0x1400dbec3  mov     rcx, [rsp+188h+var_130]
0x1400dbec8  jmp     loc_1400DC721
0x1400dbecd  mov     rax, [rax]
0x1400dbed0  mov     [rsp+188h+var_118], rax
0x1400dbed5  jmp     loc_1400DBDE4
0x1400dbeda  cmp     [r12+29h], dil
0x1400dbedf  jnz     loc_1400DC1F2
0x1400dbee5  mov     rdx, [r15+8]
0x1400dbee9  mov     rcx, [rsp+188h+var_A8]
0x1400dbef1  cmp     rdx, rcx
0x1400dbef4  jnz     loc_1400DC256
0x1400dbefa  mov     rax, [r15+60h]
0x1400dbefe  cmp     [rax+8], di
0x1400dbf02  jnz     loc_1400DC2B0
0x1400dbf08  mov     rax, [rsp+188h+var_128]
0x1400dbf0d  mov     [rax], r15
0x1400dbf10  mov     rax, [r15+10h]
0x1400dbf14  mov     rcx, [rax+20h]
0x1400dbf18  mov     [rbx], rcx
0x1400dbf1b  mov     ecx, dword ptr [rsp+188h+var_118+4]
0x1400dbf1f  and     ecx, 1
0x1400dbf22  jnz     loc_1400DC102
0x1400dbf28  mov     eax, [rbx+8]
0x1400dbf2b  and     eax, 0FFFFFFFEh
0x1400dbf2e  or      eax, ecx
0x1400dbf30  mov     [rbx+8], eax
0x1400dbf33  test    byte ptr [rsp+188h+var_118+4], 1
0x1400dbf38  jnz     loc_1400DC173
0x1400dbf3e  mov     eax, [rbx+8]
0x1400dbf41  mov     rdx, [rsp+188h+var_108]
0x1400dbf49  test    al, 1
0x1400dbf4b  jnz     loc_1400DC352
0x1400dbf51  mov     eax, [rbx+8]
0x1400dbf54  test    al, 1
0x1400dbf56  jnz     loc_1400DC372
0x1400dbf5c  mov     dl, dil
0x1400dbf5f  mov     [rsp+188h+var_138], dl
0x1400dbf63  mov     [rsp+188h+var_E8], rdi
0x1400dbf6b  mov     [rsp+188h+var_110], edi
0x1400dbf6f  mov     rax, [rsp+188h+var_130]
0x1400dbf74  test    rax, rax
0x1400dbf77  jz      loc_1400DC3D2
0x1400dbf7d  test    dl, dl
0x1400dbf7f  jnz     loc_1400DC180
0x1400dbf85  lock inc dword ptr [r14+0D08h]
0x1400dbf8d  and     dword ptr [rbx+8], 0FFFFFFC1h
0x1400dbf91  test    rax, rax
0x1400dbf94  jnz     loc_1400DC0E0
0x1400dbf9a  mov     [rbx+10h], rdi
0x1400dbf9e  and     dword ptr [rsi+1Ch], 0FFFFFFFBh
0x1400dbfa2  mov     eax, cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x1400dbfa8  test    al, 1
0x1400dbfaa  jz      loc_1400DC068
0x1400dbfb0  mov     r12d, [rsp+188h+arg_28]
0x1400dbfb8  cmp     [rsp+188h+var_130], rdi
0x1400dbfbd  jz      loc_1400DC528
0x1400dbfc3  mov     eax, [r15+2B0h]
0x1400dbfca  test    eax, eax
0x1400dbfcc  jz      loc_1400DC538
0x1400dbfd2  mov     eax, dword ptr [rsp+188h+var_118+4]
0x1400dbfd6  shr     eax, 2
0x1400dbfd9  and     eax, 7
0x1400dbfdc  jnz     loc_1400DC5D2
0x1400dbfe2  mov     rbx, [rsp+188h+var_D0]
0x1400dbfea  mov     r12, [rsp+188h+var_128]
0x1400dbfef  add     r12, 8
0x1400dbff3  mov     [rsp+188h+var_128], r12
0x1400dbff8  mov     [rsp+188h+var_B8], r12
0x1400dc000  mov     rax, [rsp+188h+Src]
0x1400dc008  add     rax, 8
0x1400dc00c  mov     [rsp+188h+Src], rax
0x1400dc014  mov     [rsp+188h+var_88], rax
0x1400dc01c  add     rbx, 18h
0x1400dc020  mov     [rsp+188h+var_D0], rbx
0x1400dc028  mov     [rsp+188h+var_80], rbx
0x1400dc030  inc     r13d
0x1400dc033  mov     [rsp+188h+var_120], r13d
0x1400dc038  mov     r10, [rsp+188h+var_F0]
0x1400dc040  mov     edx, [rsp+188h+var_10C]
0x1400dc044  mov     r8b, [rsp+188h+var_137]
0x1400dc049  jmp     loc_1400DBDAD
0x1400dc04e  lock inc dword ptr [r14+0CF4h]
0x1400dc056  mov     [r12], rdi
0x1400dc05a  xorps   xmm0, xmm0
0x1400dc05d  xor     eax, eax
0x1400dc05f  movups  xmmword ptr [rbx], xmm0
0x1400dc062  mov     [rbx+10h], rax
0x1400dc066  jmp     short loc_1400DBFEF
0x1400dc068  mov     rax, [r14+18h]
0x1400dc06c  mov     ecx, [rax+1BCh]
0x1400dc072  test    cl, 4
0x1400dc075  jnz     loc_1400DBFB0
0x1400dc07b  cmp     [r12+2Ah], dil
0x1400dc080  jz      loc_1400DC41B
0x1400dc086  lea     rax, [r12+88h]
0x1400dc08e  mov     [rsp+188h+var_D8], rax
0x1400dc096  mov     rcx, rax; this
0x1400dc099  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400dc09e  mov     [rsp+188h+var_E0], r12
0x1400dc0a6  mov     rcx, r12; struct VIDMM_GLOBAL_ALLOC *
0x1400dc0a9  call    ?VidMmGetFullPfnArray@@YAPEB_KPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetFullPfnArray(VIDMM_GLOBAL_ALLOC const *)
0x1400dc0ae  test    rax, rax
0x1400dc0b1  jnz     short loc_1400DC0C6
0x1400dc0b3  mov     rdx, [rsp+188h+var_100]
0x1400dc0bb  mov     eax, [rdx+40h]
0x1400dc0be  test    al, 1
0x1400dc0c0  jz      loc_1400DC42D
0x1400dc0c6  mov     [rsp+188h+var_E0], rdi
0x1400dc0ce  mov     rcx, [rsp+188h+var_D8]; this
0x1400dc0d6  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400dc0db  jmp     loc_1400DBFB0
0x1400dc0e0  mov     rdx, [rsi+80h]
0x1400dc0e7  mov     eax, [rdx+24h]
0x1400dc0ea  test    al, 20h
0x1400dc0ec  jz      loc_1400DC1AD
0x1400dc0f2  mov     rax, [r15+2A8h]
0x1400dc0f9  mov     [rbx+10h], rax
0x1400dc0fd  jmp     loc_1400DBF9E
0x1400dc102  cmp     [r15+18h], dil
0x1400dc106  jz      loc_1400DBF28
0x1400dc10c  mov     rax, [r14+18h]
0x1400dc110  cmp     dword ptr [rax+0B20h], 1200h
0x1400dc11a  jl      loc_1400DBF28
0x1400dc120  mov     ebx, 3
0x1400dc125  mov     ecx, ebx
0x1400dc127  call    cs:__imp_WdLogSingleEntry0
0x1400dc12e  nop     dword ptr [rax+rax+00h]
0x1400dc133  mov     cs:WdLogGlobalForLineNumber, 236Ch
0x1400dc13d  mov     r8, r15
0x1400dc140  mov     rdx, rsi
0x1400dc143  mov     ecx, ebx
0x1400dc145  call    cs:__imp_WdLogSingleEntry2
0x1400dc14c  nop     dword ptr [rax+rax+00h]
0x1400dc151  mov     cs:WdLogGlobalForLineNumber, 236Dh
0x1400dc15b  mov     ebx, 0C0000022h
0x1400dc160  mov     [rsp+188h+var_134], ebx
0x1400dc164  mov     r12, [rsp+188h+var_128]
0x1400dc169  mov     rcx, [rsp+188h+var_130]
0x1400dc16e  jmp     loc_1400DC721
0x1400dc173  lock inc dword ptr [r14+0CF8h]
0x1400dc17b  jmp     loc_1400DBF3E
0x1400dc180  lock inc dword ptr [r14+0D04h]
0x1400dc188  mov     rax, [rsp+188h+var_E8]
0x1400dc190  mov     [rbx+10h], rax
0x1400dc194  mov     ecx, [rsp+188h+var_110]
0x1400dc198  and     ecx, 1Fh
0x1400dc19b  add     ecx, ecx
0x1400dc19d  mov     eax, [rbx+8]
0x1400dc1a0  and     eax, 0FFFFFFC1h
0x1400dc1a3  or      ecx, eax
0x1400dc1a5  mov     [rbx+8], ecx
0x1400dc1a8  jmp     loc_1400DBFB0
0x1400dc1ad  mov     edx, [rdx+20h]; unsigned int
0x1400dc1b0  mov     rcx, r15; struct VIDMM_ALLOC *
0x1400dc1b3  call    ?VidMmGetAllocGpuVirtualAddress@@YA_KPEBUVIDMM_ALLOC@@I@Z; VidMmGetAllocGpuVirtualAddress(VIDMM_ALLOC const *,uint)
0x1400dc1b8  jmp     loc_1400DC0F9
0x1400dc1bd  mov     rax, [r14+18h]
0x1400dc1c1  mov     ecx, [rax+1BCh]
0x1400dc1c7  test    cl, 10h
0x1400dc1ca  jnz     loc_1400DBFD2
0x1400dc1d0  jmp     loc_1400DC551
0x1400dc1d5  mov     rcx, rax
0x1400dc1d8  shr     rcx, 20h
0x1400dc1dc  test    cl, 1
0x1400dc1df  jz      loc_1400DBE56
0x1400dc1e5  mov     [rsp+188h+var_F0], r15
0x1400dc1ed  jmp     loc_1400DBEDA
0x1400dc1f2  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400dc1f9  cmp     [rax], dil
0x1400dc1fc  jz      short loc_1400DC214
0x1400dc1fe  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400dc205  nop     dword ptr [rax+rax+00h]
0x1400dc20a  mov     cs:WdLogGlobalForLineNumber, 2338h
0x1400dc214  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
  ... truncated ...
```
