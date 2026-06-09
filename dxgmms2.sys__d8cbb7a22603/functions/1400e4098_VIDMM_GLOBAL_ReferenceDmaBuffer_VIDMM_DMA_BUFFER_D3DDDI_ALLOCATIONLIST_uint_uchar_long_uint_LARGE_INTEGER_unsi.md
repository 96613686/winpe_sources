# VIDMM_GLOBAL::ReferenceDmaBuffer(VIDMM_DMA_BUFFER *,_D3DDDI_ALLOCATIONLIST *,uint,uchar,long,uint *,_LARGE_INTEGER *,unsigned __int64 *,VIDMM_ALLOC * *,VIDMM_PRIMARIES_REFERENCES *,DXGALLOCATION * *)

- ea: `0x1400e4098`
- end: `0x1400e4d2c`
- name: `?ReferenceDmaBuffer@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_DMA_BUFFER@@PEAU_D3DDDI_ALLOCATIONLIST@@IEJPEAIPEAT_LARGE_INTEGER@@PEA_KPEAPEAUVIDMM_ALLOC@@PEAUVIDMM_PRIMARIES_REFERENCES@@PEAPEAVDXGALLOCATION@@@Z`
- size: `3220`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_DMA_BUFFER *@<rdx>, struct _D3DDDI_ALLOCATIONLIST *@<r8>, unsigned int@<r9d>, char, int, unsigned int *, union _LARGE_INTEGER *, unsigned __int64 *, struct VIDMM_ALLOC **, struct VIDMM_PRIMARIES_REFERENCES *, struct DXGALLOCATION **)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x140030780`

## callees

- `0x140004268`
- `0x14001e960`
- `0x14002c5d0`
- `0x14002d8cc`
- `0x14002dab4`
- `0x14002f54c`
- `0x140030938`
- `0x140030c48`
- `0x140032488`
- `0x140032d18`
- `0x1400333c8`
- `0x140046890`
- `0x140058f50`
- `0x140059030`
- `0x1400e4098`
- `0x1400e4d34`
- `0x14010dbac`
- `0x14010dfb8`
- `0x1401105c8`
- `0x1401114dc`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x1400e4180`
- `ntoskrnl!MmIsUserAddress` at `0x1400e4180`
- `ntoskrnl!KeStackAttachProcess` at `0x1400e48ec`
- `ntoskrnl!KeStackAttachProcess` at `0x1400e48ec`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400e4977`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400e4977`
- `watchdog!WdLogSingleEntry3` at `0x1400e42cb`
- `watchdog!WdLogSingleEntry3` at `0x1400e42cb`
- `watchdog!WdLogSingleEntry4` at `0x1400e46e2`
- `watchdog!WdLogSingleEntry4` at `0x1400e46e2`
- `watchdog!WdLogSingleEntry2` at `0x1400e45a5`
- `watchdog!WdLogSingleEntry2` at `0x1400e4739`
- `watchdog!WdLogSingleEntry2` at `0x1400e4797`
- `watchdog!WdLogSingleEntry2` at `0x1400e4a3f`
- `watchdog!WdLogSingleEntry2` at `0x1400e4a86`
- `watchdog!WdLogSingleEntry2` at `0x1400e45a5`
- `watchdog!WdLogSingleEntry2` at `0x1400e4739`
- `watchdog!WdLogSingleEntry2` at `0x1400e4797`
- `watchdog!WdLogSingleEntry2` at `0x1400e4a3f`
- `watchdog!WdLogSingleEntry2` at `0x1400e4a86`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e465e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e4680`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e465e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e4680`
- `watchdog!WdLogSingleEntry5` at `0x1400e4af6`
- `watchdog!WdLogSingleEntry5` at `0x1400e4af6`
- `watchdog!WdLogSingleEntry0` at `0x1400e4587`
- `watchdog!WdLogSingleEntry0` at `0x1400e4587`
- `watchdog!WdLogSingleEntry1` at `0x1400e493d`
- `watchdog!WdLogSingleEntry1` at `0x1400e49b9`
- `watchdog!WdLogSingleEntry1` at `0x1400e4b21`
- `watchdog!WdLogSingleEntry1` at `0x1400e493d`
- `watchdog!WdLogSingleEntry1` at `0x1400e49b9`
- `watchdog!WdLogSingleEntry1` at `0x1400e4b21`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400e4acc`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e4652`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e4674`
- `dxgkrnl!DxgkVidMmAllowFailOnOfferReclaimErrors` at `0x1400e471e`
- `dxgkrnl!DxgkVidMmAllowFailOnOfferReclaimErrors` at `0x1400e471e`

## string_xrefs

- `0x1400e4304`: `Driver must reference only a single, writeable history buffer. Alloc:%I64X, CurrentHistoryBuffer:%I64X, Writeable:%d\n`
- `0x1400e49e3`: `Failed to reference DMA buffer: Allocation is not requested to be resident. Alloc=0x%p`
- `0x1400e4b5b`: `Exception occurred accessing user mode allocation list, returning Status=0x%I64x`

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
  int v28; // ecx
  int v29; // r8d
  unsigned int v30; // ebx
  unsigned __int64 *v31; // rcx
  struct VIDMM_PRIMARIES_REFERENCES *v32; // rdx
  char v33; // dl
  unsigned __int64 *v34; // rax
  unsigned int v35; // eax
  union _LARGE_INTEGER v36; // rdx
  unsigned __int64 AllocGpuVirtualAddress; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  int v40; // ecx
  int v41; // r8d
  int v42; // ebx
  __int64 v43; // rcx
  int v44; // ecx
  int v45; // r8d
  __int64 v46; // rbx
  int v47; // ecx
  int v48; // r8d
  union _LARGE_INTEGER v50; // rax
  unsigned int *v51; // rbx
  union _LARGE_INTEGER *v52; // r8
  union _LARGE_INTEGER v53; // rdx
  __int64 v54; // rcx
  signed __int32 v55[8]; // [rsp+0h] [rbp-188h] BYREF
  char v56; // [rsp+50h] [rbp-138h]
  char v57; // [rsp+51h] [rbp-137h]
  int v58; // [rsp+54h] [rbp-134h]
  unsigned __int64 *p_QuadPart; // [rsp+58h] [rbp-130h]
  __int64 *v60; // [rsp+60h] [rbp-128h]
  unsigned int v61; // [rsp+68h] [rbp-120h]
  unsigned __int64 v62; // [rsp+70h] [rbp-118h] BYREF
  int v63; // [rsp+78h] [rbp-110h] BYREF
  unsigned int v64; // [rsp+7Ch] [rbp-10Ch]
  struct VIDMM_PRIMARIES_REFERENCES *v65; // [rsp+80h] [rbp-108h]
  struct VIDMM_LOCAL_ALLOC *v66; // [rsp+88h] [rbp-100h]
  void *Src; // [rsp+90h] [rbp-F8h]
  __int64 v68; // [rsp+98h] [rbp-F0h]
  __int64 v69; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-E0h]
  DXGFASTMUTEX *v71; // [rsp+B0h] [rbp-D8h]
  union _LARGE_INTEGER v72; // [rsp+B8h] [rbp-D0h]
  struct VIDMM_ALLOC **v73; // [rsp+C0h] [rbp-C8h]
  union _LARGE_INTEGER *v74; // [rsp+C8h] [rbp-C0h]
  __int64 *v75; // [rsp+D0h] [rbp-B8h]
  struct DXGALLOCATION **v76; // [rsp+D8h] [rbp-B0h]
  __int64 v77; // [rsp+E0h] [rbp-A8h]
  struct DXGPROCESS *Current; // [rsp+E8h] [rbp-A0h]
  unsigned int *v79; // [rsp+F0h] [rbp-98h]
  unsigned __int64 *v80; // [rsp+F8h] [rbp-90h]
  _QWORD *v81; // [rsp+100h] [rbp-88h]
  union _LARGE_INTEGER v82; // [rsp+108h] [rbp-80h]
  struct _KAPC_STATE ApcState; // [rsp+110h] [rbp-78h] BYREF

  v64 = a4;
  Src = a3;
  v74 = a8;
  v65 = a11;
  v79 = a7;
  p_QuadPart = (unsigned __int64 *)&a9->QuadPart;
  v80 = (unsigned __int64 *)&a9->QuadPart;
  v73 = a10;
  v76 = a12;
  v61 = 0;
  QuadPart = (__int64 *)a2[12].QuadPart;
  v60 = QuadPart;
  v75 = QuadPart;
  v15 = a2[13];
  v72 = v15;
  Current = DXGPROCESS::GetCurrent();
  v77 = *(_QWORD *)(a2[16].QuadPart + 8);
  IsUserAddress = MmIsUserAddress(Src);
  v57 = IsUserAddress;
  if ( a9 )
    *a9 = a2[11];
  *v73 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 826);
  v17 = v64;
  _InterlockedAdd((volatile signed __int32 *)this + 827, v64);
  if ( v64 > *((_DWORD *)this + 828) )
    _InterlockedExchange((volatile __int32 *)this + 828, v64);
  a2[3].HighPart |= 4u;
  v18 = *(union _LARGE_INTEGER *)(*(_QWORD *)a2[16].QuadPart + 56LL);
  _InterlockedOr(v55, 0);
  a2[18] = v18;
  *(_DWORD *)a11 = 0;
  v70 = 0;
  v19 = 0;
  v68 = 0;
  v20 = 0;
  v61 = 0;
  v21 = Src;
  while ( v20 < v17 )
  {
    v62 = 0;
    if ( IsUserAddress )
    {
      RtlCopyFromUser(&v62, v21, 8u);
      v22 = v62;
      v19 = v68;
    }
    else
    {
      v22 = *v21;
      v62 = v22;
    }
    if ( (_DWORD)v22 )
    {
      v23 = v20;
      v24 = v76[v20];
      if ( !v24 )
      {
        WdLogSingleEntry2(2, (unsigned int)v22, v20);
        WdLogGlobalForLineNumber = 9099;
        v30 = -1071775468;
        v58 = -1071775468;
        v31 = p_QuadPart;
LABEL_90:
        if ( !v31 && v20 )
        {
          do
          {
            if ( *--QuadPart )
              RemoveDMAReferences(*QuadPart, a6);
            --v20;
          }
          while ( v20 );
        }
        return v30;
      }
      v25 = *((_QWORD *)v24 + 3);
      v26 = **(_QWORD **)v25;
      v66 = *(struct VIDMM_LOCAL_ALLOC **)v26;
      v71 = *(DXGFASTMUTEX **)(*((_QWORD *)this + 4560) + 8LL * ((*((_DWORD *)v66 + 15) >> 2) & 0x3F));
      v27 = *(_DWORD **)(v26 + 392);
      if ( (*v27 & 0x4000) != 0 )
      {
        if ( v19 || (v27 = (_DWORD *)HIDWORD(v22), (v22 & 0x100000000LL) == 0) )
        {
          WdLogSingleEntry3(1, v25, v19, BYTE4(v22) & 1);
          WdLogGlobalForLineNumber = 9142;
          DxgkLogInternalTriageEvent(
            v28,
            0x40000,
            v29,
            (unsigned int)L"Driver must reference only a single, writeable history buffer. Alloc:%I64X, CurrentHistoryBuff"
                           "er:%I64X, Writeable:%d\n",
            v25,
            v68,
            BYTE4(v62) & 1,
            0);
          v30 = -1071775482;
          v58 = -1071775482;
          QuadPart = v60;
          v31 = p_QuadPart;
          goto LABEL_90;
        }
        v68 = v25;
      }
      if ( *(_BYTE *)(v26 + 41) )
      {
        if ( g_IsInternalReleaseOrDbg )
        {
          WdLogNewEntry5_WdTrace(v27);
          WdLogGlobalForLineNumber = 9157;
          v39 = WdLogNewEntry5_WdTrace(v38);
          *(_QWORD *)(v39 + 24) = a2;
          *(_QWORD *)(v39 + 32) = v25;
          WdLogGlobalForLineNumber = 9158;
        }
        v30 = -1071775482;
        v58 = -1071775482;
        QuadPart = v60;
        v31 = p_QuadPart;
        goto LABEL_90;
      }
      if ( *(_QWORD *)(v25 + 8) != v77 && (*((_DWORD *)Current + 102) & 0x100) == 0 )
      {
        WdLogSingleEntry4(2, v77, v25, v20, *(_QWORD *)(v25 + 8));
        WdLogGlobalForLineNumber = 9169;
        v30 = -1071775467;
        v58 = -1071775467;
        QuadPart = v60;
        v31 = p_QuadPart;
        goto LABEL_90;
      }
      if ( *(_WORD *)(*(_QWORD *)(v25 + 96) + 8LL) && a5 )
      {
        if ( DxgkVidMmAllowFailOnOfferReclaimErrors() )
        {
          WdLogSingleEntry2(1, a2, v25);
          WdLogGlobalForLineNumber = 9184;
          DxgkLogInternalTriageEvent(
            v40,
            0x40000,
            v41,
            (unsigned int)L"DMA buffer 0x%p references an allocation 0x%p that is offered.\n",
            (__int64)a2,
            v25,
            0,
            0);
          v30 = -1071775466;
          v58 = -1071775466;
          QuadPart = v60;
          v31 = p_QuadPart;
          goto LABEL_90;
        }
        WdLogSingleEntry2(2, a2, v25);
        WdLogGlobalForLineNumber = 9190;
      }
      *v60 = v25;
      *(_QWORD *)v15.QuadPart = *(_QWORD *)(*(_QWORD *)(v25 + 16) + 32LL);
      if ( (v62 & 0x100000000LL) != 0 && *(_BYTE *)(v25 + 24) && *(int *)(*((_QWORD *)this + 3) + 2864LL) >= 4608 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 9209;
        WdLogSingleEntry2(3, a2, v25);
        WdLogGlobalForLineNumber = 9210;
        v30 = -1073741790;
        v58 = -1073741790;
        QuadPart = v60;
        v31 = p_QuadPart;
        goto LABEL_90;
      }
      *(_DWORD *)(v15.QuadPart + 8) = BYTE4(v62) & 1 | *(_DWORD *)(v15.QuadPart + 8) & 0xFFFFFFFE;
      if ( (v62 & 0x100000000LL) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)this + 830);
      v32 = v65;
      if ( (*(_DWORD *)(v15.QuadPart + 8) & 1) != 0 && (**(_DWORD **)(v26 + 392) & 0x200000) != 0 )
        *((_DWORD *)v65 + 35) |= 1u;
      if ( (*(_DWORD *)(v15.QuadPart + 8) & 1) != 0
        && (**(_DWORD **)(v26 + 392) >> 23) & 0xFFFFFF00
         | ((unsigned __int16)**(_DWORD **)(v26 + 392)
          | (unsigned __int16)((unsigned int)(**(_DWORD **)(v26 + 392) | (**(_DWORD **)(v26 + 392) >> 11)) >> 11))
         & 0x100 )
      {
        if ( *(_DWORD *)v32 >= 0x10u )
        {
          _InterlockedIncrement((volatile signed __int32 *)this + 836);
        }
        else
        {
          InterlockedCounterWithHistoryRelease::Increment(
            (InterlockedCounterWithHistoryRelease *)(v25 + 104),
            (unsigned int *)v32 + 34,
            v23);
          v32 = v65;
          *((_QWORD *)v65 + *(unsigned int *)v65 + 1) = v25;
        }
        ++*(_DWORD *)v32;
      }
      v33 = 0;
      v56 = 0;
      v69 = 0;
      v63 = 0;
      v34 = p_QuadPart;
      if ( !p_QuadPart )
      {
        if ( (*((_DWORD *)this + 786) & 0x40) == 0 )
        {
          v33 = (*(__int64 (__fastcall **)(DXGFASTMUTEX *, struct VIDMM_LOCAL_ALLOC *, int *, __int64 *, _QWORD))(*(_QWORD *)v71 + 48LL))(
                  v71,
                  v66,
                  &v63,
                  &v69,
                  0);
          v56 = v33;
        }
        v34 = p_QuadPart;
      }
      if ( v33 )
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 833);
        *(_QWORD *)(v15.QuadPart + 16) = v69;
        *(_DWORD *)(v15.QuadPart + 8) = *(_DWORD *)(v15.QuadPart + 8) & 0xFFFFFFC1 | (2 * (v63 & 0x1F));
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 834);
        *(_DWORD *)(v15.QuadPart + 8) &= 0xFFFFFFC1;
        if ( v34 )
        {
          v36 = a2[16];
          if ( (*(_DWORD *)(v36.QuadPart + 36) & 0x20) != 0 )
            AllocGpuVirtualAddress = *(_QWORD *)(v25 + 680);
          else
            AllocGpuVirtualAddress = VidMmGetAllocGpuVirtualAddress(
                                       (const struct VIDMM_ALLOC *)v25,
                                       *(_DWORD *)(v36.QuadPart + 32));
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
          v71 = (DXGFASTMUTEX *)(v26 + 136);
          DXGFASTMUTEX::Acquire((DXGFASTMUTEX *)(v26 + 136));
          v70 = v26;
          if ( !VidMmGetFullPfnArray((const struct VIDMM_GLOBAL_ALLOC *)v26)
            && (*((_DWORD *)v66 + 16) & 1) == 0
            && (**(_DWORD **)(v26 + 392) & 0x40000000) == 0
            && (int)VIDMM_GLOBAL::ChargePinnedBackingStore(this, *((_QWORD *)v66 + 2)) >= 0 )
          {
            v42 = 0;
            memset(&ApcState, 0, sizeof(ApcState));
            v43 = *(_QWORD *)(v26 + 48);
            if ( v43 )
            {
              KeStackAttachProcess(*(PRKPROCESS *)(*(_QWORD *)(v43 + 8) + 16LL), &ApcState);
              v42 = 1;
            }
            if ( (int)VIDMM_GLOBAL::ProbeAndLockAllocation(
                        this,
                        v66,
                        (struct VIDMM_GLOBAL_ALLOC *)v26,
                        0,
                        *((_QWORD *)v66 + 2),
                        0) < 0 )
            {
              WdLogSingleEntry1(2, v26);
              WdLogGlobalForLineNumber = 9383;
              VIDMM_GLOBAL::ReturnPinnedBackingStore(this, *((_QWORD *)v66 + 2));
            }
            else
            {
              VidMmiAddProbeAndLockReference((struct VIDMM_GLOBAL_ALLOC *)v26);
              *(_DWORD *)(v26 + 32) |= 2u;
            }
            if ( v42 )
              KeUnstackDetachProcess(&ApcState);
          }
          v70 = 0;
          DXGFASTMUTEX::Release(v71);
        }
      }
      if ( !p_QuadPart )
        AddDMAReferences(v25, a6, v23);
      if ( !*(_DWORD *)(v25 + 688)
        && (*(_BYTE *)(v25 + 25) & 1) == 0
        && ((*((_BYTE *)this + 37224) & 0x20) == 0 || (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 0x10) == 0) )
      {
        WdLogSingleEntry1(1, v25);
        WdLogGlobalForLineNumber = 9419;
        DxgkLogInternalTriageEvent(
          v44,
          0x40000,
          v45,
          (unsigned int)L"Failed to reference DMA buffer: Allocation is not requested to be resident. Alloc=0x%p",
          v25,
          0,
          0,
          0);
        v30 = -1073741823;
        v58 = -1073741823;
        VidSchMarkDeviceAsError(*(_QWORD *)(*(_QWORD *)(v25 + 8) + 32LL), 16);
        if ( !p_QuadPart )
          RemoveDMAReferences(v25, a6);
        QuadPart = v60;
        v31 = p_QuadPart;
        goto LABEL_90;
      }
      v35 = (HIDWORD(v62) >> 2) & 7;
      if ( v35 )
      {
        v46 = v35;
        WdLogSingleEntry2(1, v25, v35);
        WdLogGlobalForLineNumber = 9441;
        DxgkLogInternalTriageEvent(
          v47,
          0x40000,
          v48,
          (unsigned int)L"Driver should not specify an offer priority for allocation lists in WDDMv2. Alloc=0x%I64X, OfferPriority=%d",
          v25,
          v46,
          0,
          0);
      }
      v15 = v72;
      QuadPart = v60;
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 829);
      *QuadPart = 0;
      *(_OWORD *)v15.QuadPart = 0;
      *(_QWORD *)(v15.QuadPart + 16) = 0;
    }
    v60 = ++QuadPart;
    v75 = QuadPart;
    v21 = (char *)Src + 8;
    Src = v21;
    v81 = v21;
    v15.QuadPart += 24LL;
    v72 = v15;
    v82 = v15;
    v61 = ++v20;
    v19 = v68;
    v17 = v64;
    IsUserAddress = v57;
  }
  *v73 = (struct VIDMM_ALLOC *)v19;
  v50 = a2[7];
  v51 = v79;
  *v79 = 0;
  v52 = v74;
  if ( v50.QuadPart )
  {
    v74->QuadPart = 0;
    v53 = a2[6];
    if ( (**(_DWORD **)(v53.QuadPart + 392) & 0x8000) != 0 )
    {
      if ( (*((_DWORD *)this + 786) & 0x40) == 0 )
      {
        v54 = *(_QWORD *)(*((_QWORD *)this + 4560) + 8LL * *(unsigned int *)(a2[16].QuadPart + 32));
        (*(void (__fastcall **)(__int64, _QWORD, unsigned int *, union _LARGE_INTEGER *, _QWORD))(*(_QWORD *)v54 + 48LL))(
          v54,
          *(_QWORD *)v53.QuadPart,
          v51,
          v52,
          0);
      }
      if ( *v51 )
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 833);
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)this + 834);
        a2[3].HighPart &= ~4u;
      }
    }
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))AddDMAReferences)((union _LARGE_INTEGER)a2[7].QuadPart, a6, v52);
  }
  else
  {
    *v74 = a2[10];
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
0x1400e4098  push    rbx
0x1400e409a  push    rsi
0x1400e409b  push    rdi
0x1400e409c  push    r12
0x1400e409e  push    r13
0x1400e40a0  push    r14
0x1400e40a2  push    r15
0x1400e40a4  sub     rsp, 150h
0x1400e40ab  mov     rax, cs:__security_cookie
0x1400e40b2  xor     rax, rsp
0x1400e40b5  mov     [rsp+188h+var_48], rax
0x1400e40bd  mov     [rsp+188h+var_10C], r9d
0x1400e40c2  mov     [rsp+188h+Src], r8
0x1400e40ca  mov     rsi, rdx
0x1400e40cd  mov     r14, rcx
0x1400e40d0  mov     rax, [rsp+188h+arg_38]
0x1400e40d8  mov     [rsp+188h+var_C0], rax
0x1400e40e0  mov     r13, [rsp+188h+arg_50]
0x1400e40e8  mov     [rsp+188h+var_108], r13
0x1400e40f0  mov     rax, [rsp+188h+arg_30]
0x1400e40f8  mov     [rsp+188h+var_98], rax
0x1400e4100  mov     r15, [rsp+188h+arg_40]
0x1400e4108  mov     [rsp+188h+var_130], r15
0x1400e410d  mov     [rsp+188h+var_90], r15
0x1400e4115  mov     rax, [rsp+188h+arg_48]
0x1400e411d  mov     [rsp+188h+var_C8], rax
0x1400e4125  mov     rax, [rsp+188h+arg_58]
0x1400e412d  mov     [rsp+188h+var_B0], rax
0x1400e4135  xor     edi, edi
0x1400e4137  mov     [rsp+188h+var_120], edi
0x1400e413b  mov     r12, [rdx+60h]
0x1400e413f  mov     [rsp+188h+var_128], r12
0x1400e4144  mov     [rsp+188h+var_B8], r12
0x1400e414c  mov     rbx, [rdx+68h]
0x1400e4150  mov     [rsp+188h+var_D0], rbx
0x1400e4158  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1400e415d  mov     [rsp+188h+var_A0], rax
0x1400e4165  mov     rcx, [rsi+80h]
0x1400e416c  mov     rax, [rcx+8]
0x1400e4170  mov     [rsp+188h+var_A8], rax
0x1400e4178  mov     rcx, [rsp+188h+Src]
0x1400e4180  call    cs:__imp_MmIsUserAddress
0x1400e4187  nop     dword ptr [rax+rax+00h]
0x1400e418c  mov     r8b, al
0x1400e418f  mov     [rsp+188h+var_137], al
0x1400e4193  test    r15, r15
0x1400e4196  jnz     loc_1400E4C56
0x1400e419c  mov     rcx, [rsp+188h+var_C8]
0x1400e41a4  mov     [rcx], rdi
0x1400e41a7  lock inc dword ptr [r14+0CE8h]
0x1400e41af  mov     edx, [rsp+188h+var_10C]
0x1400e41b3  lock add [r14+0CECh], edx
0x1400e41bb  mov     eax, [r14+0CF0h]
0x1400e41c2  cmp     edx, eax
0x1400e41c4  ja      loc_1400E4C62
0x1400e41ca  or      dword ptr [rsi+1Ch], 4
0x1400e41ce  mov     rax, [rsi+80h]
0x1400e41d5  mov     rcx, [rax]
0x1400e41d8  mov     rax, [rcx+38h]
0x1400e41dc  lock or [rsp+188h+var_188], edi
0x1400e41e0  mov     [rsi+90h], rax
0x1400e41e7  mov     [r13+0], edi
0x1400e41eb  mov     [rsp+188h+var_E0], rdi
0x1400e41f3  mov     r10, rdi
0x1400e41f6  mov     [rsp+188h+var_F0], rdi
0x1400e41fe  mov     r13d, edi
0x1400e4201  mov     [rsp+188h+var_120], edi
0x1400e4205  mov     rax, [rsp+188h+Src]
0x1400e420d  cmp     r13d, edx
0x1400e4210  jnb     loc_1400E4AAF
0x1400e4216  mov     [rsp+188h+var_118], rdi
0x1400e421b  test    r8b, r8b
0x1400e421e  jz      loc_1400E432D
0x1400e4224  mov     r8d, 8; Size
0x1400e422a  mov     rdx, rax; Src
0x1400e422d  lea     rcx, [rsp+188h+var_118]; void *
0x1400e4232  call    RtlCopyFromUser
0x1400e4237  mov     rax, [rsp+188h+var_118]
0x1400e423c  mov     r10, [rsp+188h+var_F0]
0x1400e4244  test    eax, eax
0x1400e4246  jz      loc_1400E44AE
0x1400e424c  mov     r8d, r13d; unsigned __int64
0x1400e424f  mov     rcx, [rsp+188h+var_B0]
0x1400e4257  mov     r15, [rcx+r8*8]
0x1400e425b  test    r15, r15
0x1400e425e  jz      loc_1400E4A7F
0x1400e4264  mov     r15, [r15+18h]
0x1400e4268  mov     rcx, [r15]
0x1400e426b  mov     r12, [rcx]
0x1400e426e  mov     rcx, [r12]
0x1400e4272  mov     [rsp+188h+var_100], rcx
0x1400e427a  mov     edx, [rcx+3Ch]
0x1400e427d  shr     rdx, 2
0x1400e4281  and     edx, 3Fh
0x1400e4284  mov     rcx, [r14+8E80h]
0x1400e428b  mov     r9, [rcx+rdx*8]
0x1400e428f  mov     [rsp+188h+var_D8], r9
0x1400e4297  mov     rcx, [r12+188h]
0x1400e429f  mov     edx, [rcx]
0x1400e42a1  shr     edx, 0Eh
0x1400e42a4  test    dl, 1
0x1400e42a7  jz      loc_1400E433A
0x1400e42ad  test    r10, r10
0x1400e42b0  jz      loc_1400E4635
0x1400e42b6  shr     rax, 20h
0x1400e42ba  and     eax, 1
0x1400e42bd  mov     r9d, eax
0x1400e42c0  mov     r8, r10
0x1400e42c3  mov     rdx, r15
0x1400e42c6  mov     ecx, 1
0x1400e42cb  call    cs:__imp_WdLogSingleEntry3
0x1400e42d2  nop     dword ptr [rax+rax+00h]
0x1400e42d7  mov     cs:WdLogGlobalForLineNumber, 23B6h
0x1400e42e1  mov     eax, dword ptr [rsp+188h+var_118+4]
0x1400e42e5  and     eax, 1
0x1400e42e8  mov     [rsp+188h+var_150], rdi
0x1400e42ed  mov     [rsp+188h+var_158], rax
0x1400e42f2  mov     rax, [rsp+188h+var_F0]
0x1400e42fa  mov     qword ptr [rsp+188h+var_160], rax
0x1400e42ff  mov     [rsp+188h+var_168], r15
0x1400e4304  lea     r9, aDriverMustRefe; "Driver must reference only a single, wr"...
0x1400e430b  mov     edx, 40000h
0x1400e4310  call    DxgkLogInternalTriageEvent
0x1400e4315  mov     ebx, 0C01E0106h
0x1400e431a  mov     [rsp+188h+var_134], ebx
0x1400e431e  mov     r12, [rsp+188h+var_128]
0x1400e4323  mov     rcx, [rsp+188h+var_130]
0x1400e4328  jmp     loc_1400E4B81
0x1400e432d  mov     rax, [rax]
0x1400e4330  mov     [rsp+188h+var_118], rax
0x1400e4335  jmp     loc_1400E4244
0x1400e433a  cmp     [r12+29h], dil
0x1400e433f  jnz     loc_1400E4652
0x1400e4345  mov     rdx, [r15+8]
0x1400e4349  mov     rcx, [rsp+188h+var_A8]
0x1400e4351  cmp     rdx, rcx
0x1400e4354  jnz     loc_1400E46B6
0x1400e435a  mov     rax, [r15+60h]
0x1400e435e  cmp     [rax+8], di
0x1400e4362  jnz     loc_1400E4710
0x1400e4368  mov     rax, [rsp+188h+var_128]
0x1400e436d  mov     [rax], r15
0x1400e4370  mov     rax, [r15+10h]
0x1400e4374  mov     rcx, [rax+20h]
0x1400e4378  mov     [rbx], rcx
0x1400e437b  mov     ecx, dword ptr [rsp+188h+var_118+4]
0x1400e437f  and     ecx, 1
0x1400e4382  jnz     loc_1400E4562
0x1400e4388  mov     eax, [rbx+8]
0x1400e438b  and     eax, 0FFFFFFFEh
0x1400e438e  or      eax, ecx
0x1400e4390  mov     [rbx+8], eax
0x1400e4393  test    byte ptr [rsp+188h+var_118+4], 1
0x1400e4398  jnz     loc_1400E45D3
0x1400e439e  mov     eax, [rbx+8]
0x1400e43a1  mov     rdx, [rsp+188h+var_108]
0x1400e43a9  test    al, 1
0x1400e43ab  jnz     loc_1400E47B2
0x1400e43b1  mov     eax, [rbx+8]
0x1400e43b4  test    al, 1
0x1400e43b6  jnz     loc_1400E47D2
0x1400e43bc  mov     dl, dil
0x1400e43bf  mov     [rsp+188h+var_138], dl
0x1400e43c3  mov     [rsp+188h+var_E8], rdi
0x1400e43cb  mov     [rsp+188h+var_110], edi
0x1400e43cf  mov     rax, [rsp+188h+var_130]
0x1400e43d4  test    rax, rax
0x1400e43d7  jz      loc_1400E4832
0x1400e43dd  test    dl, dl
0x1400e43df  jnz     loc_1400E45E0
0x1400e43e5  lock inc dword ptr [r14+0D08h]
0x1400e43ed  and     dword ptr [rbx+8], 0FFFFFFC1h
0x1400e43f1  test    rax, rax
0x1400e43f4  jnz     loc_1400E4540
0x1400e43fa  mov     [rbx+10h], rdi
0x1400e43fe  and     dword ptr [rsi+1Ch], 0FFFFFFFBh
0x1400e4402  mov     eax, cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x1400e4408  test    al, 1
0x1400e440a  jz      loc_1400E44C8
0x1400e4410  mov     r12d, [rsp+188h+arg_28]
0x1400e4418  cmp     [rsp+188h+var_130], rdi
0x1400e441d  jz      loc_1400E4988
0x1400e4423  mov     eax, [r15+2B0h]
0x1400e442a  test    eax, eax
0x1400e442c  jz      loc_1400E4998
0x1400e4432  mov     eax, dword ptr [rsp+188h+var_118+4]
0x1400e4436  shr     eax, 2
0x1400e4439  and     eax, 7
0x1400e443c  jnz     loc_1400E4A32
0x1400e4442  mov     rbx, [rsp+188h+var_D0]
0x1400e444a  mov     r12, [rsp+188h+var_128]
0x1400e444f  add     r12, 8
0x1400e4453  mov     [rsp+188h+var_128], r12
0x1400e4458  mov     [rsp+188h+var_B8], r12
0x1400e4460  mov     rax, [rsp+188h+Src]
0x1400e4468  add     rax, 8
0x1400e446c  mov     [rsp+188h+Src], rax
0x1400e4474  mov     [rsp+188h+var_88], rax
0x1400e447c  add     rbx, 18h
0x1400e4480  mov     [rsp+188h+var_D0], rbx
0x1400e4488  mov     [rsp+188h+var_80], rbx
0x1400e4490  inc     r13d
0x1400e4493  mov     [rsp+188h+var_120], r13d
0x1400e4498  mov     r10, [rsp+188h+var_F0]
0x1400e44a0  mov     edx, [rsp+188h+var_10C]
0x1400e44a4  mov     r8b, [rsp+188h+var_137]
0x1400e44a9  jmp     loc_1400E420D
0x1400e44ae  lock inc dword ptr [r14+0CF4h]
0x1400e44b6  mov     [r12], rdi
0x1400e44ba  xorps   xmm0, xmm0
0x1400e44bd  xor     eax, eax
0x1400e44bf  movups  xmmword ptr [rbx], xmm0
0x1400e44c2  mov     [rbx+10h], rax
0x1400e44c6  jmp     short loc_1400E444F
0x1400e44c8  mov     rax, [r14+18h]
0x1400e44cc  mov     ecx, [rax+1BCh]
0x1400e44d2  test    cl, 4
0x1400e44d5  jnz     loc_1400E4410
0x1400e44db  cmp     [r12+2Ah], dil
0x1400e44e0  jz      loc_1400E487B
0x1400e44e6  lea     rax, [r12+88h]
0x1400e44ee  mov     [rsp+188h+var_D8], rax
0x1400e44f6  mov     rcx, rax; this
0x1400e44f9  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400e44fe  mov     [rsp+188h+var_E0], r12
0x1400e4506  mov     rcx, r12; struct VIDMM_GLOBAL_ALLOC *
0x1400e4509  call    ?VidMmGetFullPfnArray@@YAPEB_KPEBUVIDMM_GLOBAL_ALLOC@@@Z; VidMmGetFullPfnArray(VIDMM_GLOBAL_ALLOC const *)
0x1400e450e  test    rax, rax
0x1400e4511  jnz     short loc_1400E4526
0x1400e4513  mov     rdx, [rsp+188h+var_100]
0x1400e451b  mov     eax, [rdx+40h]
0x1400e451e  test    al, 1
0x1400e4520  jz      loc_1400E488D
0x1400e4526  mov     [rsp+188h+var_E0], rdi
0x1400e452e  mov     rcx, [rsp+188h+var_D8]; this
0x1400e4536  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400e453b  jmp     loc_1400E4410
0x1400e4540  mov     rdx, [rsi+80h]
0x1400e4547  mov     eax, [rdx+24h]
0x1400e454a  test    al, 20h
0x1400e454c  jz      loc_1400E460D
0x1400e4552  mov     rax, [r15+2A8h]
0x1400e4559  mov     [rbx+10h], rax
0x1400e455d  jmp     loc_1400E43FE
0x1400e4562  cmp     [r15+18h], dil
0x1400e4566  jz      loc_1400E4388
0x1400e456c  mov     rax, [r14+18h]
0x1400e4570  cmp     dword ptr [rax+0B30h], 1200h
0x1400e457a  jl      loc_1400E4388
0x1400e4580  mov     ebx, 3
0x1400e4585  mov     ecx, ebx
0x1400e4587  call    cs:__imp_WdLogSingleEntry0
0x1400e458e  nop     dword ptr [rax+rax+00h]
0x1400e4593  mov     cs:WdLogGlobalForLineNumber, 23F9h
0x1400e459d  mov     r8, r15
0x1400e45a0  mov     rdx, rsi
0x1400e45a3  mov     ecx, ebx
0x1400e45a5  call    cs:__imp_WdLogSingleEntry2
0x1400e45ac  nop     dword ptr [rax+rax+00h]
0x1400e45b1  mov     cs:WdLogGlobalForLineNumber, 23FAh
0x1400e45bb  mov     ebx, 0C0000022h
0x1400e45c0  mov     [rsp+188h+var_134], ebx
0x1400e45c4  mov     r12, [rsp+188h+var_128]
0x1400e45c9  mov     rcx, [rsp+188h+var_130]
0x1400e45ce  jmp     loc_1400E4B81
0x1400e45d3  lock inc dword ptr [r14+0CF8h]
0x1400e45db  jmp     loc_1400E439E
0x1400e45e0  lock inc dword ptr [r14+0D04h]
0x1400e45e8  mov     rax, [rsp+188h+var_E8]
0x1400e45f0  mov     [rbx+10h], rax
0x1400e45f4  mov     ecx, [rsp+188h+var_110]
0x1400e45f8  and     ecx, 1Fh
0x1400e45fb  add     ecx, ecx
0x1400e45fd  mov     eax, [rbx+8]
0x1400e4600  and     eax, 0FFFFFFC1h
0x1400e4603  or      ecx, eax
0x1400e4605  mov     [rbx+8], ecx
0x1400e4608  jmp     loc_1400E4410
0x1400e460d  mov     edx, [rdx+20h]; unsigned int
0x1400e4610  mov     rcx, r15; struct VIDMM_ALLOC *
0x1400e4613  call    ?VidMmGetAllocGpuVirtualAddress@@YA_KPEBUVIDMM_ALLOC@@I@Z; VidMmGetAllocGpuVirtualAddress(VIDMM_ALLOC const *,uint)
0x1400e4618  jmp     loc_1400E4559
0x1400e461d  mov     rax, [r14+18h]
0x1400e4621  mov     ecx, [rax+1BCh]
0x1400e4627  test    cl, 10h
0x1400e462a  jnz     loc_1400E4432
0x1400e4630  jmp     loc_1400E49B1
0x1400e4635  mov     rcx, rax
0x1400e4638  shr     rcx, 20h
0x1400e463c  test    cl, 1
0x1400e463f  jz      loc_1400E42B6
0x1400e4645  mov     [rsp+188h+var_F0], r15
0x1400e464d  jmp     loc_1400E433A
0x1400e4652  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400e4659  cmp     [rax], dil
0x1400e465c  jz      short loc_1400E4674
0x1400e465e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400e4665  nop     dword ptr [rax+rax+00h]
0x1400e466a  mov     cs:WdLogGlobalForLineNumber, 23C5h
0x1400e4674  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
  ... truncated ...
```
