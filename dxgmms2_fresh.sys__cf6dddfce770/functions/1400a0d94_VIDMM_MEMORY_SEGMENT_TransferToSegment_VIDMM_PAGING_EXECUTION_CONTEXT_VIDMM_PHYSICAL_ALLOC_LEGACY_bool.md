# VIDMM_MEMORY_SEGMENT::TransferToSegment(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool)

- ea: `0x1400a0d94`
- end: `0x1400a1bf1`
- name: `?TransferToSegment@VIDMM_MEMORY_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_N@Z`
- size: `3677`
- prototype: `__int64 __fastcall(VIDMM_MEMORY_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool)`
- caller_count: `2`
- callee_count: `36`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400a0c50`
- `0x1400d6710`

## callees

- `0x140004268`
- `0x1400128c8`
- `0x14002eae8`
- `0x14002ed18`
- `0x140030bac`
- `0x14003e344`
- `0x140048084`
- `0x140048308`
- `0x1400499f0`
- `0x140058f50`
- `0x140059030`
- `0x140059080`
- `0x140059380`
- `0x140096800`
- `0x140097b0c`
- `0x14009ecf4`
- `0x1400a093c`
- `0x1400a0d94`
- `0x1400a1bf8`
- `0x1400a1ef0`
- `0x1400a2918`
- `0x1400a302c`
- `0x1400a7410`
- `0x1400adf2c`
- `0x1400af314`
- `0x1400d5498`
- `0x1400ef500`
- `0x140104610`
- `0x14010d018`
- `0x14010d198`
- `0x14010e858`
- `0x1401104dc`
- `0x140110ae0`
- `0x1401114dc`
- `0x14011ac38`
- `0x140122d88`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x1400a0f44`
- `ntoskrnl!KeStackAttachProcess` at `0x1400a128d`
- `ntoskrnl!KeStackAttachProcess` at `0x1400a0f44`
- `ntoskrnl!KeStackAttachProcess` at `0x1400a128d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a0fa1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a158a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a0fa1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a158a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a1646`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a17c8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a1646`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a17c8`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a122e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a19f6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a122e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a19f6`
- `watchdog!WdLogSingleEntry5` at `0x1400a16ea`
- `watchdog!WdLogSingleEntry5` at `0x1400a1965`
- `watchdog!WdLogSingleEntry5` at `0x1400a16ea`
- `watchdog!WdLogSingleEntry5` at `0x1400a1965`
- `watchdog!WdLogSingleEntry0` at `0x1400a1368`
- `watchdog!WdLogSingleEntry0` at `0x1400a1a30`
- `watchdog!WdLogSingleEntry0` at `0x1400a1368`
- `watchdog!WdLogSingleEntry0` at `0x1400a1a30`
- `watchdog!WdLogSingleEntry1` at `0x1400a0e6f`
- `watchdog!WdLogSingleEntry1` at `0x1400a101b`
- `watchdog!WdLogSingleEntry1` at `0x1400a0e6f`
- `watchdog!WdLogSingleEntry1` at `0x1400a101b`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400a16c8`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400a1943`
- `dxgkrnl!g_IsInternalRelease` at `0x1400a16bc`
- `dxgkrnl!g_IsInternalRelease` at `0x1400a1937`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a1222`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a19ea`

## string_xrefs

- `0x1400a13a2`: `Exception occured while accessing allocation user mode page.\n`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_MEMORY_SEGMENT::TransferToSegment(
        VIDMM_MEMORY_SEGMENT *this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        struct VIDMM_PHYSICAL_ALLOC_LEGACY *a3,
        bool a4)
{
  struct VIDMM_GLOBAL_ALLOC *v7; // rsi
  VIDMM_GLOBAL **v8; // rbx
  VIDMM_GLOBAL *v9; // rcx
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v10; // r14
  int v11; // ecx
  int v12; // r8d
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v13; // rdx
  VIDMM_SEGMENT *v14; // rcx
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v15; // rdx
  int v16; // eax
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  VIDMM_GLOBAL **v21; // r14
  char v22; // al
  unsigned __int64 v23; // r8
  __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // r8
  __int64 v27; // rax
  const void *v28; // rax
  unsigned __int64 LogicalAddress; // rax
  VIDMM_GLOBAL *v30; // r10
  size_t v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rdx
  unsigned __int64 v40; // r11
  SIZE_T v41; // r10
  __int64 v42; // rax
  _DWORD **v43; // rdx
  _DWORD **v44; // rax
  _DWORD **v45; // rbx
  unsigned __int64 v46; // r9
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  VIDMM_MEMORY_SEGMENT *v50; // rbx
  _QWORD *v51; // rax
  int v52; // ecx
  int v53; // r8d
  VIDMM_GLOBAL *v54; // r10
  unsigned __int16 v55; // ax
  VIDMM_GLOBAL *v56; // r10
  unsigned __int16 v57; // ax
  __int64 v58; // r10
  struct VIDMM_TRANSFER_PARAMETER *v60; // [rsp+28h] [rbp-1D0h]
  bool v61; // [rsp+60h] [rbp-198h] BYREF
  bool v62; // [rsp+61h] [rbp-197h] BYREF
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v63; // [rsp+68h] [rbp-190h]
  size_t Size; // [rsp+70h] [rbp-188h]
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v65; // [rsp+78h] [rbp-180h]
  int v66; // [rsp+80h] [rbp-178h]
  VIDMM_GLOBAL **v67; // [rsp+88h] [rbp-170h]
  unsigned __int64 v68; // [rsp+90h] [rbp-168h]
  _DWORD **v69; // [rsp+98h] [rbp-160h]
  int v70; // [rsp+A0h] [rbp-158h]
  int v71; // [rsp+A4h] [rbp-154h]
  VIDMM_MEMORY_SEGMENT *v72; // [rsp+A8h] [rbp-150h]
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v73; // [rsp+B0h] [rbp-148h]
  __int64 v74; // [rsp+B8h] [rbp-140h]
  SIZE_T v75; // [rsp+C0h] [rbp-138h]
  void *v76; // [rsp+C8h] [rbp-130h] BYREF
  __int64 v77; // [rsp+D0h] [rbp-128h]
  unsigned __int64 v78; // [rsp+D8h] [rbp-120h]
  __int64 v79; // [rsp+E0h] [rbp-118h] BYREF
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v80; // [rsp+E8h] [rbp-110h]
  VIDMM_GLOBAL **v81; // [rsp+F0h] [rbp-108h]
  __int64 v82; // [rsp+F8h] [rbp-100h]
  __int128 v83; // [rsp+100h] [rbp-F8h]
  __int64 v84; // [rsp+110h] [rbp-E8h]
  __int64 v85; // [rsp+118h] [rbp-E0h]
  __int64 v86; // [rsp+120h] [rbp-D8h]
  __int64 v87; // [rsp+128h] [rbp-D0h]
  VIDMM_MEMORY_SEGMENT *v88; // [rsp+130h] [rbp-C8h]
  size_t *v89; // [rsp+138h] [rbp-C0h]
  __int64 v90; // [rsp+140h] [rbp-B8h]
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v91; // [rsp+148h] [rbp-B0h]
  struct _KAPC_STATE ApcState; // [rsp+150h] [rbp-A8h] BYREF
  struct _DXGKARG_SETVIDEOPROTECTEDREGION v93; // [rsp+180h] [rbp-78h] BYREF

  v61 = a4;
  v63 = a2;
  v88 = this;
  v72 = this;
  v91 = a2;
  v73 = a3;
  v65 = a3;
  v89 = *(size_t **)a3;
  v7 = (struct VIDMM_GLOBAL_ALLOC *)v89;
  v62 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  Size = v89[6];
  v8 = (VIDMM_GLOBAL **)((char *)this + 8);
  v67 = (VIDMM_GLOBAL **)((char *)this + 8);
  VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(
    *((VIDMM_GLOBAL **)this + 1),
    (struct VIDMM_GLOBAL_ALLOC *)v89,
    1u);
  if ( !VIDMM_GLOBAL::IsTdrPending(*v8) )
  {
    if ( *((_BYTE *)v89 + 40) )
    {
      if ( *((int *)v89 + 47) > 0 )
      {
        VIDMM_GLOBAL::UnlockAllocation(v9, (struct VIDMM_LOCAL_ALLOC *)Size, 0, *((_QWORD *)a3 + 2), 0, 0);
        VIDMM_GLOBAL::ReturnPinnedBackingStore(*v8, *((_QWORD *)a3 + 2));
        *((_DWORD *)v89 + 8) &= ~2u;
        VidMmiRemoveProbeAndLockReference(v7);
      }
      v82 = 0;
      v83 = (unsigned __int64)a2;
      v84 = 0;
      v86 = 0;
      v81 = v8;
      v87 = *((_QWORD *)a3 + 14);
      v79 = *((_QWORD *)this + 2);
      v80 = a3;
      v85 = *((_QWORD *)a3 + 2);
      KeStackAttachProcess(*(PRKPROCESS *)(*(_QWORD *)(Size + 8) + 16LL), &ApcState);
      (*(void (__fastcall **)(_QWORD, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *))(**((_QWORD **)this + 2) + 216LL))(
        *((_QWORD *)this + 2),
        a2,
        a3);
      LODWORD(v60) = 2 * v61;
      v10 = (struct VIDMM_PAGING_EXECUTION_CONTEXT *)(int)VidMmRotateLegacyAllocation(
                                                            *v8,
                                                            a3,
                                                            0,
                                                            VidMmRotateCopyCallback,
                                                            &v79,
                                                            v60);
      KeUnstackDetachProcess(&ApcState);
      if ( v61 )
      {
        if ( (int)v10 >= 0 )
          goto LABEL_15;
        *((_DWORD *)v7 + 6) |= 0x10000u;
        VIDMM_GLOBAL::FillAllocation(
          *v8,
          v63,
          v7,
          0,
          *((_QWORD *)a3 + 2),
          *((_DWORD *)*v8 + 798),
          (const struct VIDMM_SEGMENT_BASE *)((*((_QWORD *)a3 + 15) + 8LL) & -(__int64)(*((_QWORD *)a3 + 15) != 0)),
          *((_QWORD *)a3 + 14));
      }
      else
      {
        if ( (int)v10 < 0 )
        {
          WdLogSingleEntry1(1, v10);
          WdLogGlobalForLineNumber = 928;
          DxgkLogInternalTriageEvent(
            v11,
            0x40000,
            v12,
            (unsigned int)L"Failed to rotate VAD to CpuHostAperture. Status=%x\n",
            (__int64)v10,
            0,
            0,
            0);
          return (unsigned int)v10;
        }
        LODWORD(v10) = 0;
      }
      if ( (int)v10 < 0 )
      {
LABEL_16:
        *((_BYTE *)v7 + 43) = 1;
        v62 = 1;
        goto LABEL_17;
      }
LABEL_15:
      ++*((_DWORD *)v7 + 9);
      goto LABEL_16;
    }
    LODWORD(v10) = -1073741823;
    if ( !*((_BYTE *)v89 + 42) )
    {
      if ( v89[30] )
        (*(void (__fastcall **)(size_t))(*(_QWORD *)v89[29] + 96LL))(v89[29]);
      if ( (v89[3] & 4) == 0 && (*((_DWORD *)v89 + 7) & 4) == 0 )
        VIDMM_GLOBAL::FillAllocation(
          *v8,
          v63,
          (struct VIDMM_GLOBAL_ALLOC *)v89,
          0,
          *((_QWORD *)a3 + 2),
          *((_DWORD *)*v8 + 798),
          (const struct VIDMM_SEGMENT_BASE *)v8,
          *((_QWORD *)a3 + 14));
      LODWORD(v10) = 0;
      v62 = 1;
    }
    if ( (int)v10 < 0 )
    {
      v61 = 0;
      LODWORD(v10) = VIDMM_MEMORY_SEGMENT::TransferMemory(
                       this,
                       v63,
                       a3,
                       DXGK_MEMORY_TRANSFER_SYSTEM_TO_LOCAL,
                       *((_QWORD *)a3 + 14),
                       &v61,
                       &v62);
      if ( v61 )
        VidMmReleaseTemporaryResourcesForLegacyAllocation(
          *((struct VIDMM_PHYSICAL_ADAPTER_LEGACY **)this + 2),
          v63,
          a3,
          1);
      if ( (int)v10 < 0 )
      {
        v70 = 0;
        v21 = v67;
        v75 = (SIZE_T)v67;
        if ( g_IsInternalReleaseOrDbg )
        {
          WdLogNewEntry5_WdTrace(v19, v18);
          WdLogGlobalForLineNumber = 1037;
        }
        if ( (byte_140087201 & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v19, &EventPerformanceWarning, v20, 2);
        v69 = (_DWORD **)((char *)v7 + 392);
        if ( (**((_DWORD **)v7 + 49) & 8) == 0 )
          KeStackAttachProcess(*(PRKPROCESS *)(*(_QWORD *)(Size + 8) + 16LL), &ApcState);
        v22 = Use64KbPagesForTransfer(a3, *((_QWORD *)a3 + 15));
        v23 = *((_QWORD *)a3 + 2);
        v24 = v22 != 0 ? 0x10000LL : 4096LL;
        Size = v24;
        v25 = v23 >> 12;
        v26 = v23 >> 16;
        if ( !v22 )
          v26 = (unsigned int)v25;
        v68 = v26;
        v71 = v26;
        v77 = *((_QWORD *)a3 + 14);
        v90 = v77;
        v27 = 0;
        while ( 1 )
        {
          v66 = v27;
          if ( (unsigned int)v27 >= (unsigned int)v26 )
            break;
          v76 = 0;
          v78 = v24 * v27;
          v74 = v24 * v27;
          v28 = VidMmMapViewOfAllocation(v7, v24 * v27, v24, &v76);
          if ( v28 )
          {
            memmove(*((void **)*v21 + 5178), v28, Size);
            VidMmUnmapViewOfAllocation(v7, v76);
          }
          else
          {
            *((_DWORD *)v7 + 6) |= 0x10000u;
          }
          v79 = 0;
          v80 = 0;
          v81 = 0;
          v82 = 0;
          v83 = 0;
          memset(&v93, 0, sizeof(v93));
          LogicalAddress = SysMmGetLogicalAddress(*((void *const *)*v21 + 5180));
          v30 = *v21;
          *(_QWORD *)&v83 = *((_QWORD *)*v21 + 5179);
          *((_QWORD *)&v83 + 1) = v83 + 48;
          v80 = (struct VIDMM_PHYSICAL_ALLOC_LEGACY *)LogicalAddress;
          *(_QWORD *)&v93.PhysicalAdapterIndex = v77;
          v93.CurrentStartOffset = v75;
          v93.CurrentSize = v78;
          VIDMM_GLOBAL::MemoryTransfer(
            v30,
            v63,
            v7,
            Size,
            v78,
            (struct VIDMM_TRANSFER_PARAMETER *)&v79,
            (struct VIDMM_TRANSFER_PARAMETER *)&v93,
            0);
          VIDMM_GLOBAL::WaitForAllPagingEngines(*v21, v63, v7);
          v27 = (unsigned int)(v66 + 1);
          v24 = Size;
          LODWORD(v26) = v68;
        }
        LODWORD(v10) = 0;
        v62 = 1;
        if ( (**v69 & 8) == 0 )
          KeUnstackDetachProcess(&ApcState);
        v8 = v67;
      }
    }
    if ( (**((_DWORD **)v7 + 49) & 0x20000) == 0 )
      goto LABEL_17;
    Size = *((_QWORD *)a3 + 2);
    memset(&v93, 0, sizeof(v93));
    v93.PhysicalAdapterIndex = *((unsigned __int16 *)this + 34);
    v93.SegmentIndex = VIDMM_SEGMENT::DriverId(this);
    if ( *((_DWORD *)this + 105) )
    {
      v36 = v65;
      v73 = (struct VIDMM_PHYSICAL_ALLOC_LEGACY *)(*((_QWORD *)v65 + 14) & ~*((_QWORD *)this + 51));
      if ( (unsigned __int64)v73 < *((_QWORD *)this + 53) )
      {
        if ( (unsigned int)DXG_DEFERRED_WORK_QUEUE::GetNumWorkItems((VIDMM_GLOBAL *)((char *)*v8 + 37440)) )
        {
          if ( (byte_140087201 & 1) != 0 )
            McTemplateK0q_EtwWriteTransfer(v37, &EventPerformanceWarning, v38, 24);
          KeWaitForSingleObject((char *)*v8 + 37488, Executive, 0, 0, 0);
        }
        v10 = v63;
        VIDMM_MEMORY_SEGMENT::SuspendPurgeForVPRGrow(this, v63, v7);
        v39 = *((_QWORD *)this + 51);
        v40 = *((_QWORD *)this + 53);
        v74 = v40;
        v41 = v40 - (~v39 & (v39 + *((_QWORD *)a3 + 2)));
        v75 = v41;
        v42 = *((_QWORD *)this + 32);
        v43 = *(_DWORD ***)(v42 + 88);
        v44 = (_DWORD **)(v42 + 80);
        if ( v43 != v44 )
        {
          v45 = v44;
          do
          {
            v69 = (_DWORD **)v43[1];
            v46 = (unsigned __int64)*(v43 - 5);
            if ( v46 >= v40 || (unsigned __int64)*(v43 - 4) + v46 <= v41 )
            {
              if ( (unsigned __int64)*(v43 - 4) + v46 <= v41 )
                break;
            }
            else if ( *((_BYTE *)v43 + 16) == 4 )
            {
              if ( !(unsigned __int8)ReclaimAllocationForVPRCallback(0, *(v43 - 3)) )
                break;
              v41 = v75;
              v40 = v74;
            }
            v43 = v69;
          }
          while ( v69 != v45 );
          v8 = v67;
        }
        (*(void (__fastcall **)(_QWORD, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(**((_QWORD **)this + 2) + 200LL))(
          *((_QWORD *)this + 2),
          v10);
        VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(*v8, v10, *((unsigned __int16 *)this + 34));
        v93.CurrentStartOffset = *((_QWORD *)this + 53);
        v93.CurrentSize = *((_QWORD *)v72 + 55);
        v47 = v73;
        v93.NewStartOffset = (SIZE_T)v73;
        v93.NewSize = *((_QWORD *)v72 + 54) - (_QWORD)v73;
        *((_QWORD *)v72 + 55) = v93.NewSize;
        *((_QWORD *)this + 53) = v47;
        LODWORD(v10) = ADAPTER_RENDER::DdiSetVideoProtectedRegion(
                         *(ADAPTER_RENDER **)(*((_QWORD *)*v8 + 3) + 3256LL),
                         &v93);
        if ( (int)v10 < 0 && g_IsInternalRelease )
        {
          g_DxgMmsBugcheckExportIndex = 1;
          WdLogSingleEntry5(0, 270, 9, 0, 0, 0);
          WdLogGlobalForLineNumber = 227;
        }
        if ( (byte_140087201 & 1) != 0 )
          McTemplateK0qqqxxp_EtwWriteTransfer(
            *((_QWORD *)*v8 + 3),
            v48,
            v49,
            v93.PhysicalAdapterIndex,
            v93.SegmentIndex,
            v93.VprIndex,
            v93.NewStartOffset,
            v93.NewSize,
            *((_QWORD *)*v8 + 3));
        v31 = Size;
      }
      if ( (int)v10 < 0 )
        goto LABEL_87;
      *((_DWORD *)v7 + 7) |= 1u;
      v50 = v72;
      *((_QWORD *)v72 + 56) += v31;
      if ( g_IsInternalReleaseOrDbg )
      {
        v51 = (_QWORD *)WdLogNewEntry5_WdTrace(v36, v31);
        v51[3] = Size;
        v51[4] = *((_QWORD *)v50 + 56);
        v51[5] = v7;
        WdLogGlobalForLineNumber = 1293;
      }
    }
    else
    {
      if ( (unsigned int)DXG_DEFERRED_WORK_QUEUE::GetNumWorkItems((VIDMM_GLOBAL *)((char *)*v8 + 37440)) )
      {
        if ( (byte_140087201 & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v32, &EventPerformanceWarning, v33, 24);
        KeWaitForSingleObject((char *)*v8 + 37488, Executive, 0, 0, 0);
      }
      (*(void (__fastcall **)(_QWORD, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(**((_QWORD **)this + 2) + 200LL))(
        *((_QWORD *)this + 2),
        v63);
      VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(*v8, v63, *((unsigned __int16 *)this + 34));
      v93.NewStartOffset = *((_QWORD *)v65 + 14);
      v93.NewSize = Size;
      LODWORD(v10) = ADAPTER_RENDER::DdiSetVideoProtectedRegion(
                       *(ADAPTER_RENDER **)(*((_QWORD *)*v8 + 3) + 3256LL),
                       &v93);
      if ( (int)v10 < 0 && g_IsInternalRelease )
      {
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 270, 9, 0, 0, 0);
        WdLogGlobalForLineNumber = 227;
      }
      if ( (byte_140087201 & 1) != 0 )
        McTemplateK0qqqxxp_EtwWriteTransfer(
          *((_QWORD *)*v8 + 3),
          v34,
          v35,
          v93.PhysicalAdapterIndex,
          v93.SegmentIndex,
          v93.VprIndex,
          v93.NewStartOffset,
          v93.NewSize,
          *((_QWORD *)*v8 + 3));
    }
    if ( (int)v10 >= 0 )
      goto LABEL_17;
LABEL_87:
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1299;
    DxgkLogInternalTriageEvent(v52, 0x40000, v53, (unsigned int)L"Failed to set video protected region", 1299, 0, 0, 0);
    return (unsigned int)v10;
  }
  LODWORD(v10) = -1073741130;
  if ( !v61 )
  {
    WdLogSingleEntry1(4, v89);
    WdLogGlobalForLineNumber = 801;
    return (unsigned int)v10;
  }
LABEL_17:
  v13 = v65;
  v14 = (VIDMM_SEGMENT *)*((_QWORD *)v65 + 15);
  *((_QWORD *)a3 + 17) = v14;
  *((_QWORD *)a3 + 18) = *((_QWORD *)v13 + 14);
  *(_WORD *)(*((_QWORD *)v7 + 49) + 10LL) = VIDMM_SEGMENT::DriverId(v14);
  *(_QWORD *)(*((_QWORD *)v7 + 49) + 40LL) = *((_QWORD *)a3 + 18) + *(_QWORD *)(*((_QWORD *)a3 + 17) + 24LL);
  *((_QWORD *)v15 + 15) = 0;
  v16 = *((_DWORD *)v7 + 8);
  if ( (v16 & 2) != 0 )
  {
    VIDMM_SEGMENT::UnlockAllocationBackingStore(*((struct VIDMM_GLOBAL **)this + 1), v7, 0);
    VIDMM_GLOBAL::ReturnPinnedBackingStore(*((VIDMM_GLOBAL **)this + 1), *((_QWORD *)a3 + 2));
    *((_DWORD *)v7 + 8) &= ~2u;
    v16 = *((_DWORD *)v7 + 8);
    v15 = v65;
  }
  if ( !v62 || (v16 & 8) != 0 )
  {
    v17 = v63;
  }
  else
  {
    v17 = v63;
    if ( !*((_QWORD *)v15 + 29) )
      VIDMM_GLOBAL::ResetBackingStore(*((_QWORD *)this + 1), v63, v7, 0);
  }
  if ( (**((_DWORD **)v7 + 49) & 0x10000) != 0 )
  {
    v68 = (unsigned int)Feature_NotifyResidency2__private_featureState;
    if ( (Feature_NotifyResidency2__private_featureState & 0x10) == 0 )
    {
      v65 = (struct VIDMM_PHYSICAL_ALLOC_LEGACY *)__PAIR64__(
                                                    HIDWORD(v68),
                                                    Feature_NotifyResidency2__private_featureState | 1u);
      wil_details_FeatureReporting_ReportUsageToService(
        &Feature_NotifyResidency2__private_descriptor,
        __PAIR64__(HIDWORD(v68), Feature_NotifyResidency2__private_featureState | 1u),
        3);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v65, 3, &Feature_NotifyResidency2__private_descriptor);
    }
    v54 = (VIDMM_GLOBAL *)*((_QWORD *)this + 1);
    if ( *(_QWORD *)(*((_QWORD *)v54 + 3) + 1776LL) )
    {
      VIDMM_GLOBAL::NotifyResidency2(
        v54,
        v17,
        *((struct VIDMM_PHYSICAL_ADAPTER **)this + 2),
        a3,
        1,
        1,
        0,
        (*((_QWORD *)a3 + 2) >> 12) + ((*((_QWORD *)a3 + 2) & 0xFFFLL) != 0),
        *((unsigned __int16 *)v72 + 35),
        *((_QWORD *)a3 + 18) >> 12,
        0);
    }
    else
    {
      v55 = VIDMM_SEGMENT::DriverId(this);
      VIDMM_GLOBAL::NotifyResidency(v56, v17, v7, 1, v55, *((_QWORD *)a3 + 18));
    }
  }
  if ( *(_QWORD *)(*((_QWORD *)this + 1) + 37360LL) )
  {
    v57 = VIDMM_SEGMENT::DriverId(this);
    VIDMM_GLOBAL::RecordPageMappingHistory(v58, v57);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400a0d94  mov     r11, rsp
0x1400a0d97  push    rbx
0x1400a0d98  push    rsi
0x1400a0d99  push    rdi
0x1400a0d9a  push    r12
0x1400a0d9c  push    r13
0x1400a0d9e  push    r14
0x1400a0da0  push    r15
0x1400a0da2  sub     rsp, 1C0h
0x1400a0da9  mov     rax, cs:__security_cookie
0x1400a0db0  xor     rax, rsp
0x1400a0db3  mov     [rsp+1F8h+var_48], rax
0x1400a0dbb  mov     [rsp+1F8h+var_198], r9b
0x1400a0dc0  mov     r12, r8
0x1400a0dc3  mov     r14, rdx
0x1400a0dc6  mov     [rsp+1F8h+var_190], rdx
0x1400a0dcb  mov     r13, rcx
0x1400a0dce  mov     [rsp+1F8h+var_C8], rcx
0x1400a0dd6  mov     [rsp+1F8h+var_150], rcx
0x1400a0dde  mov     [rsp+1F8h+var_B0], rdx
0x1400a0de6  mov     [rsp+1F8h+var_148], r8
0x1400a0dee  mov     [rsp+1F8h+var_180], r8
0x1400a0df3  mov     rsi, [r8]
0x1400a0df6  mov     [rsp+1F8h+var_C0], rsi
0x1400a0dfe  xor     edi, edi
0x1400a0e00  mov     [rsp+1F8h+var_197], dil
0x1400a0e05  mov     [r11-0A8h], rdi
0x1400a0e0c  xorps   xmm0, xmm0
0x1400a0e0f  xor     eax, eax
0x1400a0e11  movups  xmmword ptr [rsp+1F8h+ApcState.ApcListHead.Blink], xmm0
0x1400a0e19  movups  xmmword ptr [rsp+1F8h+ApcState.ApcListHead.Blink+10h], xmm0
0x1400a0e21  mov     [r11-80h], rax
0x1400a0e25  mov     rax, [rsi+30h]
0x1400a0e29  mov     [rsp+1F8h+Size], rax
0x1400a0e2e  lea     rbx, [rcx+8]
0x1400a0e32  mov     [rsp+1F8h+var_170], rbx
0x1400a0e3a  lea     r15d, [rdi+1]
0x1400a0e3e  mov     r8b, r15b; unsigned __int8
0x1400a0e41  mov     rdx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400a0e44  mov     rcx, [rbx]; this
0x1400a0e47  call    ?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z; VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)
0x1400a0e4c  mov     rcx, [rbx]; this
0x1400a0e4f  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400a0e54  test    al, al
0x1400a0e56  jz      short loc_1400A0E8A
0x1400a0e58  mov     r14d, 0C00002B6h
0x1400a0e5e  cmp     [rsp+1F8h+var_198], dil
0x1400a0e63  jnz     loc_1400A1070
0x1400a0e69  mov     rdx, rsi
0x1400a0e6c  lea     ecx, [rdi+4]
0x1400a0e6f  call    cs:__imp_WdLogSingleEntry1
0x1400a0e76  nop     dword ptr [rax+rax+00h]
0x1400a0e7b  mov     cs:WdLogGlobalForLineNumber, 321h
0x1400a0e85  jmp     loc_1400A1BCA
0x1400a0e8a  cmp     [rsi+28h], dil
0x1400a0e8e  jz      loc_1400A112C
0x1400a0e94  cmp     [rsi+0BCh], edi
0x1400a0e9a  jle     short loc_1400A0ED1
0x1400a0e9c  mov     byte ptr [rsp+1F8h+var_1D0], dil; bool
0x1400a0ea1  mov     byte ptr [rsp+1F8h+Timeout], dil; bool
0x1400a0ea6  mov     r9, [r12+10h]; unsigned __int64
0x1400a0eab  xor     r8d, r8d; unsigned __int64
0x1400a0eae  mov     rdx, [rsp+1F8h+Size]; struct VIDMM_LOCAL_ALLOC *
0x1400a0eb3  call    ?UnlockAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_K1_N2@Z; VIDMM_GLOBAL::UnlockAllocation(VIDMM_LOCAL_ALLOC *,unsigned __int64,unsigned __int64,bool,bool)
0x1400a0eb8  mov     rdx, [r12+10h]; unsigned __int64
0x1400a0ebd  mov     rcx, [rbx]; this
0x1400a0ec0  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x1400a0ec5  and     dword ptr [rsi+20h], 0FFFFFFFDh
0x1400a0ec9  mov     rcx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400a0ecc  call    ?VidMmiRemoveProbeAndLockReference@@YAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VidMmiRemoveProbeAndLockReference(VIDMM_GLOBAL_ALLOC *)
0x1400a0ed1  mov     [rsp+1F8h+var_100], rdi
0x1400a0ed9  mov     qword ptr [rsp+1F8h+var_F8+8], rdi
0x1400a0ee1  mov     qword ptr [rsp+1F8h+var_F8], r14
0x1400a0ee9  mov     [rsp+1F8h+var_E8], rdi
0x1400a0ef1  mov     [rsp+1F8h+var_D8], rdi
0x1400a0ef9  mov     [rsp+1F8h+var_108], rbx
0x1400a0f01  mov     rax, [r12+70h]
0x1400a0f06  mov     [rsp+1F8h+var_D0], rax
0x1400a0f0e  mov     rax, [r13+10h]
0x1400a0f12  mov     [rsp+1F8h+var_118], rax
0x1400a0f1a  mov     [rsp+1F8h+var_110], r12
0x1400a0f22  mov     rax, [r12+10h]
0x1400a0f27  mov     [rsp+1F8h+var_E0], rax
0x1400a0f2f  mov     rax, [rsp+1F8h+Size]
0x1400a0f34  mov     rcx, [rax+8]
0x1400a0f38  lea     rdx, [rsp+1F8h+ApcState]; ApcState
0x1400a0f40  mov     rcx, [rcx+10h]; PROCESS
0x1400a0f44  call    cs:__imp_KeStackAttachProcess
0x1400a0f4b  nop     dword ptr [rax+rax+00h]
0x1400a0f50  mov     rcx, [r13+10h]
0x1400a0f54  mov     rax, [rcx]
0x1400a0f57  mov     rax, [rax+0D8h]
0x1400a0f5e  mov     r8, r12
0x1400a0f61  mov     rdx, r14
0x1400a0f64  call    _guard_dispatch_icall
0x1400a0f69  movzx   eax, [rsp+1F8h+var_198]
0x1400a0f6e  add     eax, eax
0x1400a0f70  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x1400a0f74  lea     rax, [rsp+1F8h+var_118]
0x1400a0f7c  mov     [rsp+1F8h+Timeout], rax
0x1400a0f81  lea     r9, ?VidMmRotateCopyCallback@@YAJPEAU_MDL@@0PEAX@Z; VidMmRotateCopyCallback(_MDL *,_MDL *,void *)
0x1400a0f88  xor     r8d, r8d
0x1400a0f8b  mov     rdx, r12
0x1400a0f8e  mov     rcx, [rbx]
0x1400a0f91  call    ?VidMmRotateLegacyAllocation@@YAJPEAVVIDMM_GLOBAL@@PEAUVIDMM_PHYSICAL_ALLOC@@W4_MM_ROTATE_DIRECTION@@P6AJPEAU_MDL@@3PEAX@ZPEAUVIDMM_ROTATE_COPY_CONTEXT@@TVIDMM_ROTATE_FLAGS@@@Z; VidMmRotateLegacyAllocation(VIDMM_GLOBAL *,VIDMM_PHYSICAL_ALLOC *,_MM_ROTATE_DIRECTION,long (*)(_MDL *,_MDL *,void *),VIDMM_ROTATE_COPY_CONTEXT *,VIDMM_ROTATE_FLAGS)
0x1400a0f96  movsxd  r14, eax
0x1400a0f99  lea     rcx, [rsp+1F8h+ApcState]; ApcState
0x1400a0fa1  call    cs:__imp_KeUnstackDetachProcess
0x1400a0fa8  nop     dword ptr [rax+rax+00h]
0x1400a0fad  cmp     [rsp+1F8h+var_198], dil
0x1400a0fb2  jz      short loc_1400A1010
0x1400a0fb4  test    r14d, r14d
0x1400a0fb7  jns     loc_1400A1063
0x1400a0fbd  bts     dword ptr [rsi+18h], 10h
0x1400a0fc2  mov     r10, [rbx]
0x1400a0fc5  mov     rcx, [r12+78h]
0x1400a0fca  lea     rax, [rcx+8]
0x1400a0fce  neg     rcx
0x1400a0fd1  sbb     rdx, rdx
0x1400a0fd4  and     rdx, rax
0x1400a0fd7  mov     rax, [r12+70h]
0x1400a0fdc  mov     qword ptr [rsp+1F8h+var_1C0], rax; unsigned __int64
0x1400a0fe1  mov     [rsp+1F8h+var_1C8], rdx; struct VIDMM_SEGMENT_BASE *
0x1400a0fe6  mov     eax, [r10+0C78h]
0x1400a0fed  mov     dword ptr [rsp+1F8h+var_1D0], eax; unsigned int
0x1400a0ff1  mov     rax, [r12+10h]
0x1400a0ff6  mov     [rsp+1F8h+Timeout], rax; unsigned __int64
0x1400a0ffb  xor     r9d, r9d; unsigned __int64
0x1400a0ffe  mov     r8, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400a1001  mov     rdx, [rsp+1F8h+var_190]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a1006  mov     rcx, r10; this
0x1400a1009  call    ?FillAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@_K2IPEBUVIDMM_SEGMENT_BASE@@2@Z; VIDMM_GLOBAL::FillAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,uint,VIDMM_SEGMENT_BASE const *,unsigned __int64)
0x1400a100e  jmp     short loc_1400A105E
0x1400a1010  test    r14d, r14d
0x1400a1013  jns     short loc_1400A105B
0x1400a1015  mov     rdx, r14
0x1400a1018  mov     ecx, r15d
0x1400a101b  call    cs:__imp_WdLogSingleEntry1
0x1400a1022  nop     dword ptr [rax+rax+00h]
0x1400a1027  mov     cs:WdLogGlobalForLineNumber, 3A0h
0x1400a1031  mov     qword ptr [rsp+1F8h+var_1C0], rdi
0x1400a1036  mov     [rsp+1F8h+var_1C8], rdi
0x1400a103b  mov     [rsp+1F8h+var_1D0], rdi
0x1400a1040  mov     [rsp+1F8h+Timeout], r14
0x1400a1045  lea     r9, aFailedToRotate; "Failed to rotate VAD to CpuHostAperture"...
0x1400a104c  mov     edx, 40000h
0x1400a1051  call    DxgkLogInternalTriageEvent
0x1400a1056  jmp     loc_1400A1BCA
0x1400a105b  mov     r14d, edi
0x1400a105e  test    r14d, r14d
0x1400a1061  js      short loc_1400A1067
0x1400a1063  add     [rsi+24h], r15d
0x1400a1067  mov     [rsi+2Bh], r15b
0x1400a106b  mov     [rsp+1F8h+var_197], r15b
0x1400a1070  mov     rdx, [rsp+1F8h+var_180]
0x1400a1075  mov     rcx, [rdx+78h]; this
0x1400a1079  mov     [r12+88h], rcx
0x1400a1081  mov     rax, [rdx+70h]
0x1400a1085  mov     [r12+90h], rax
0x1400a108d  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x1400a1092  mov     rcx, [rsi+188h]
0x1400a1099  mov     [rcx+0Ah], ax
0x1400a109d  mov     rax, [r12+88h]
0x1400a10a5  mov     rcx, [rax+18h]
0x1400a10a9  add     rcx, [r12+90h]
0x1400a10b1  mov     rax, [rsi+188h]
0x1400a10b8  mov     [rax+28h], rcx
0x1400a10bc  mov     [rdx+78h], rdi
0x1400a10c0  mov     eax, [rsi+20h]
0x1400a10c3  test    al, 2
0x1400a10c5  jz      short loc_1400A10F0
0x1400a10c7  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC *
0x1400a10ca  mov     rdx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400a10cd  mov     rcx, [r13+8]; this
0x1400a10d1  call    ?UnlockAllocationBackingStore@VIDMM_SEGMENT@@SAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_SEGMENT::UnlockAllocationBackingStore(VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x1400a10d6  mov     rdx, [r12+10h]; unsigned __int64
0x1400a10db  mov     rcx, [r13+8]; this
0x1400a10df  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x1400a10e4  and     dword ptr [rsi+20h], 0FFFFFFFDh
0x1400a10e8  mov     eax, [rsi+20h]
0x1400a10eb  mov     rdx, [rsp+1F8h+var_180]
0x1400a10f0  cmp     [rsp+1F8h+var_197], dil
0x1400a10f5  jz      loc_1400A1A67
0x1400a10fb  test    al, 8
0x1400a10fd  jnz     loc_1400A1A67
0x1400a1103  mov     rbx, [rsp+1F8h+var_190]
0x1400a1108  cmp     [rdx+0E8h], rdi
0x1400a110f  jnz     loc_1400A1A6C
0x1400a1115  xor     r9d, r9d
0x1400a1118  mov     r8, rsi
0x1400a111b  mov     rdx, rbx
0x1400a111e  mov     rcx, [r13+8]
0x1400a1122  call    ?ResetBackingStore@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_RESET_BACKING_STORE_REASON@@@Z; VIDMM_GLOBAL::ResetBackingStore(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,VIDMM_RESET_BACKING_STORE_REASON)
0x1400a1127  jmp     loc_1400A1A6C
0x1400a112c  mov     r14d, 0C0000001h
0x1400a1132  cmp     [rsi+2Ah], dil
0x1400a1136  jnz     short loc_1400A11A3
0x1400a1138  mov     rdx, [rsi+0F0h]
0x1400a113f  test    rdx, rdx
0x1400a1142  jz      short loc_1400A1157
0x1400a1144  mov     rcx, [rsi+0E8h]
0x1400a114b  mov     rax, [rcx]
0x1400a114e  mov     rax, [rax+60h]
0x1400a1152  call    _guard_dispatch_icall
0x1400a1157  mov     eax, [rsi+18h]
0x1400a115a  test    al, 4
0x1400a115c  jnz     short loc_1400A119B
0x1400a115e  mov     eax, [rsi+1Ch]
0x1400a1161  test    al, 4
0x1400a1163  jnz     short loc_1400A119B
0x1400a1165  mov     rcx, [rbx]; this
0x1400a1168  mov     rax, [r12+70h]
0x1400a116d  mov     qword ptr [rsp+1F8h+var_1C0], rax; unsigned __int64
0x1400a1172  mov     [rsp+1F8h+var_1C8], rbx; struct VIDMM_SEGMENT_BASE *
0x1400a1177  mov     eax, [rcx+0C78h]
0x1400a117d  mov     dword ptr [rsp+1F8h+var_1D0], eax; unsigned int
0x1400a1181  mov     rax, [r12+10h]
0x1400a1186  mov     [rsp+1F8h+Timeout], rax; unsigned __int64
0x1400a118b  xor     r9d, r9d; unsigned __int64
0x1400a118e  mov     r8, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400a1191  mov     rdx, [rsp+1F8h+var_190]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a1196  call    ?FillAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@_K2IPEBUVIDMM_SEGMENT_BASE@@2@Z; VIDMM_GLOBAL::FillAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,uint,VIDMM_SEGMENT_BASE const *,unsigned __int64)
0x1400a119b  mov     r14d, edi
0x1400a119e  mov     [rsp+1F8h+var_197], r15b
0x1400a11a3  test    r14d, r14d
0x1400a11a6  jns     loc_1400A159E
0x1400a11ac  mov     [rsp+1F8h+var_198], dil
0x1400a11b1  lea     rax, [rsp+1F8h+var_197]
0x1400a11b6  mov     [rsp+1F8h+var_1C8], rax; bool *
0x1400a11bb  lea     rax, [rsp+1F8h+var_198]
0x1400a11c0  mov     [rsp+1F8h+var_1D0], rax; bool *
0x1400a11c5  mov     rax, [r12+70h]
0x1400a11ca  mov     [rsp+1F8h+Timeout], rax; unsigned __int64
0x1400a11cf  mov     r9d, r15d; enum _DXGK_MEMORY_TRANSFER_DIRECTION
0x1400a11d2  mov     r8, r12; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a11d5  mov     rdx, [rsp+1F8h+var_190]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a11da  mov     rcx, r13; this
0x1400a11dd  call    ?TransferMemory@VIDMM_MEMORY_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@W4_DXGK_MEMORY_TRANSFER_DIRECTION@@_KPEA_N4@Z; VIDMM_MEMORY_SEGMENT::TransferMemory(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,_DXGK_MEMORY_TRANSFER_DIRECTION,unsigned __int64,bool *,bool *)
0x1400a11e2  mov     r14d, eax
0x1400a11e5  cmp     [rsp+1F8h+var_198], dil
0x1400a11ea  jz      short loc_1400A1200
0x1400a11ec  mov     r9b, r15b; bool
0x1400a11ef  mov     r8, r12; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a11f2  mov     rdx, [rsp+1F8h+var_190]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a11f7  mov     rcx, [r13+10h]; struct VIDMM_PHYSICAL_ADAPTER_LEGACY *
0x1400a11fb  call    ?VidMmReleaseTemporaryResourcesForLegacyAllocation@@YAXPEAUVIDMM_PHYSICAL_ADAPTER_LEGACY@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_N@Z; VidMmReleaseTemporaryResourcesForLegacyAllocation(VIDMM_PHYSICAL_ADAPTER_LEGACY *,VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool)
0x1400a1200  test    r14d, r14d
0x1400a1203  jns     loc_1400A159E
0x1400a1209  mov     ebx, edi
0x1400a120b  mov     [rsp+1F8h+var_158], ebx
0x1400a1212  mov     r14, [rsp+1F8h+var_170]
0x1400a121a  mov     [rsp+1F8h+var_138], r14
0x1400a1222  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a1229  cmp     [rax], dil
0x1400a122c  jz      short loc_1400A1244
0x1400a122e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a1235  nop     dword ptr [rax+rax+00h]
0x1400a123a  mov     cs:WdLogGlobalForLineNumber, 40Dh
0x1400a1244  test    cs:byte_140087201, r15b
0x1400a124b  jz      short loc_1400A125F
0x1400a124d  mov     r9d, 2
0x1400a1253  lea     rdx, EventPerformanceWarning
0x1400a125a  call    McTemplateK0q_EtwWriteTransfer
0x1400a125f  lea     r9, [rsi+188h]
0x1400a1266  mov     [rsp+1F8h+var_160], r9
0x1400a126e  mov     rax, [r9]
0x1400a1271  mov     ecx, [rax]
0x1400a1273  test    cl, 8
0x1400a1276  jnz     short loc_1400A1299
0x1400a1278  mov     rax, [rsp+1F8h+Size]
0x1400a127d  mov     rcx, [rax+8]
0x1400a1281  lea     rdx, [rsp+1F8h+ApcState]; ApcState
0x1400a1289  mov     rcx, [rcx+10h]; PROCESS
0x1400a128d  call    cs:__imp_KeStackAttachProcess
0x1400a1294  nop     dword ptr [rax+rax+00h]
0x1400a1299  mov     rdx, [r12+78h]
0x1400a129e  mov     rcx, r12
0x1400a12a1  call    Use64KbPagesForTransfer
0x1400a12a6  mov     r8, [r12+10h]
0x1400a12ab  mov     cl, al
0x1400a12ad  neg     cl
0x1400a12af  sbb     rdx, rdx
0x1400a12b2  and     edx, 0F000h
0x1400a12b8  add     rdx, 1000h
0x1400a12bf  mov     [rsp+1F8h+Size], rdx
0x1400a12c4  mov     rcx, r8
0x1400a12c7  shr     rcx, 0Ch
0x1400a12cb  shr     r8, 10h
0x1400a12cf  test    al, al
0x1400a12d1  cmovz   r8d, ecx
0x1400a12d5  mov     [rsp+1F8h+var_168], r8
0x1400a12dd  mov     [rsp+1F8h+var_154], r8d
0x1400a12e5  mov     rax, [r12+70h]
0x1400a12ea  mov     [rsp+1F8h+var_128], rax
0x1400a12f2  mov     [rsp+1F8h+var_B8], rax
0x1400a12fa  mov     eax, edi
0x1400a12fc  mov     [rsp+1F8h+var_178], eax
0x1400a1303  cmp     eax, r8d
0x1400a1306  jnb     loc_1400A1568
0x1400a130c  mov     [rsp+1F8h+var_130], rdi
  ... truncated ...
```
