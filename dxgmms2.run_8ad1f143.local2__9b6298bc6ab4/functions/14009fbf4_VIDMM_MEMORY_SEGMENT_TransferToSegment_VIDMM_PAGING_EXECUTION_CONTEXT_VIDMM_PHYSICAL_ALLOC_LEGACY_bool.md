# VIDMM_MEMORY_SEGMENT::TransferToSegment(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool)

- ea: `0x14009fbf4`
- end: `0x1400a0a51`
- name: `?TransferToSegment@VIDMM_MEMORY_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_N@Z`
- size: `3677`
- prototype: `__int64 __fastcall(VIDMM_MEMORY_SEGMENT *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool)`
- caller_count: `2`
- callee_count: `36`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14009fab0`
- `0x1400cf980`

## callees

- `0x1400045ec`
- `0x140012e28`
- `0x140030f08`
- `0x140031138`
- `0x140032d3c`
- `0x14003f9c4`
- `0x140047e0c`
- `0x140048090`
- `0x140049320`
- `0x140058680`
- `0x140058760`
- `0x1400587c0`
- `0x140058ac0`
- `0x140095494`
- `0x14009b1ac`
- `0x14009c5f8`
- `0x14009d45c`
- `0x14009f7a0`
- `0x14009fbf4`
- `0x1400a0a58`
- `0x1400a0d50`
- `0x1400a1778`
- `0x1400a1e8c`
- `0x1400a6bac`
- `0x1400addc4`
- `0x1400cf278`
- `0x1400e6a00`
- `0x1400ed9e0`
- `0x1400f9d10`
- `0x140108cd8`
- `0x140108e58`
- `0x14010ad3c`
- `0x14010c8cc`
- `0x14010db5c`
- `0x140117138`
- `0x14011f5a8`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x14009fda4`
- `ntoskrnl!KeStackAttachProcess` at `0x1400a00ed`
- `ntoskrnl!KeStackAttachProcess` at `0x14009fda4`
- `ntoskrnl!KeStackAttachProcess` at `0x1400a00ed`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14009fe01`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a03ea`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14009fe01`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400a03ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a04a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a0628`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a04a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a0628`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a008e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a0856`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a008e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400a0856`
- `watchdog!WdLogSingleEntry5` at `0x1400a054a`
- `watchdog!WdLogSingleEntry5` at `0x1400a07c5`
- `watchdog!WdLogSingleEntry5` at `0x1400a054a`
- `watchdog!WdLogSingleEntry5` at `0x1400a07c5`
- `watchdog!WdLogSingleEntry0` at `0x1400a01c8`
- `watchdog!WdLogSingleEntry0` at `0x1400a0890`
- `watchdog!WdLogSingleEntry0` at `0x1400a01c8`
- `watchdog!WdLogSingleEntry0` at `0x1400a0890`
- `watchdog!WdLogSingleEntry1` at `0x14009fccf`
- `watchdog!WdLogSingleEntry1` at `0x14009fe7b`
- `watchdog!WdLogSingleEntry1` at `0x14009fccf`
- `watchdog!WdLogSingleEntry1` at `0x14009fe7b`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400a0528`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400a07a3`
- `dxgkrnl!g_IsInternalRelease` at `0x1400a051c`
- `dxgkrnl!g_IsInternalRelease` at `0x1400a0797`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a0082`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400a084a`

## string_xrefs

- `0x1400a0202`: `Exception occured while accessing allocation user mode page.\n`

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
  int v34; // edx
  int v35; // r8d
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
  int v48; // edx
  int v49; // r8d
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
          WdLogGlobalForLineNumber = 912;
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
          WdLogGlobalForLineNumber = 1021;
        }
        if ( (byte_140086201 & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v19, EventPerformanceWarning, v20, 2);
        v69 = (_DWORD **)((char *)v7 + 384);
        if ( (**((_DWORD **)v7 + 48) & 8) == 0 )
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
    if ( (**((_DWORD **)v7 + 48) & 0x20000) == 0 )
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
          if ( (byte_140086201 & 1) != 0 )
            McTemplateK0q_EtwWriteTransfer(v37, EventPerformanceWarning, v38, 24);
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
                         *(ADAPTER_RENDER **)(*((_QWORD *)*v8 + 3) + 3240LL),
                         &v93);
        if ( (int)v10 < 0 && g_IsInternalRelease )
        {
          g_DxgMmsBugcheckExportIndex = 1;
          WdLogSingleEntry5(0, 270, 9);
          WdLogGlobalForLineNumber = 222;
        }
        if ( (byte_140086201 & 1) != 0 )
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
        WdLogGlobalForLineNumber = 1277;
      }
    }
    else
    {
      if ( (unsigned int)DXG_DEFERRED_WORK_QUEUE::GetNumWorkItems((VIDMM_GLOBAL *)((char *)*v8 + 37440)) )
      {
        if ( (byte_140086201 & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v32, EventPerformanceWarning, v33, 24);
        KeWaitForSingleObject((char *)*v8 + 37488, Executive, 0, 0, 0);
      }
      (*(void (__fastcall **)(_QWORD, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(**((_QWORD **)this + 2) + 200LL))(
        *((_QWORD *)this + 2),
        v63);
      VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(*v8, v63, *((unsigned __int16 *)this + 34));
      v93.NewStartOffset = *((_QWORD *)v65 + 14);
      v93.NewSize = Size;
      LODWORD(v10) = ADAPTER_RENDER::DdiSetVideoProtectedRegion(
                       *(ADAPTER_RENDER **)(*((_QWORD *)*v8 + 3) + 3240LL),
                       &v93);
      if ( (int)v10 < 0 && g_IsInternalRelease )
      {
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 270, 9);
        WdLogGlobalForLineNumber = 222;
      }
      if ( (byte_140086201 & 1) != 0 )
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
    WdLogGlobalForLineNumber = 1283;
    DxgkLogInternalTriageEvent(v52, 0x40000, v53, (unsigned int)L"Failed to set video protected region", 1283, 0, 0, 0);
    return (unsigned int)v10;
  }
  LODWORD(v10) = -1073741130;
  if ( !v61 )
  {
    WdLogSingleEntry1(4, v89);
    WdLogGlobalForLineNumber = 785;
    return (unsigned int)v10;
  }
LABEL_17:
  v13 = v65;
  v14 = (VIDMM_SEGMENT *)*((_QWORD *)v65 + 15);
  *((_QWORD *)a3 + 17) = v14;
  *((_QWORD *)a3 + 18) = *((_QWORD *)v13 + 14);
  *(_WORD *)(*((_QWORD *)v7 + 48) + 10LL) = VIDMM_SEGMENT::DriverId(v14);
  *(_QWORD *)(*((_QWORD *)v7 + 48) + 40LL) = *((_QWORD *)a3 + 18) + *(_QWORD *)(*((_QWORD *)a3 + 17) + 24LL);
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
  if ( (**((_DWORD **)v7 + 48) & 0x10000) != 0 )
  {
    v68 = (unsigned int)Feature_NotifyResidency2__private_featureState;
    if ( (Feature_NotifyResidency2__private_featureState & 0x10) == 0 )
    {
      v65 = (struct VIDMM_PHYSICAL_ALLOC_LEGACY *)__PAIR64__(
                                                    HIDWORD(v68),
                                                    Feature_NotifyResidency2__private_featureState | 1u);
      wil_details_FeatureReporting_ReportUsageToService(
        Feature_NotifyResidency2__private_descriptor,
        __PAIR64__(HIDWORD(v68), Feature_NotifyResidency2__private_featureState | 1u),
        3);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v65, 3, Feature_NotifyResidency2__private_descriptor);
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
0x14009fbf4  mov     r11, rsp
0x14009fbf7  push    rbx
0x14009fbf8  push    rsi
0x14009fbf9  push    rdi
0x14009fbfa  push    r12
0x14009fbfc  push    r13
0x14009fbfe  push    r14
0x14009fc00  push    r15
0x14009fc02  sub     rsp, 1C0h
0x14009fc09  mov     rax, cs:__security_cookie
0x14009fc10  xor     rax, rsp
0x14009fc13  mov     [rsp+1F8h+var_48], rax
0x14009fc1b  mov     [rsp+1F8h+var_198], r9b
0x14009fc20  mov     r12, r8
0x14009fc23  mov     r14, rdx
0x14009fc26  mov     [rsp+1F8h+var_190], rdx
0x14009fc2b  mov     r13, rcx
0x14009fc2e  mov     [rsp+1F8h+var_C8], rcx
0x14009fc36  mov     [rsp+1F8h+var_150], rcx
0x14009fc3e  mov     [rsp+1F8h+var_B0], rdx
0x14009fc46  mov     [rsp+1F8h+var_148], r8
0x14009fc4e  mov     [rsp+1F8h+var_180], r8
0x14009fc53  mov     rsi, [r8]
0x14009fc56  mov     [rsp+1F8h+var_C0], rsi
0x14009fc5e  xor     edi, edi
0x14009fc60  mov     [rsp+1F8h+var_197], dil
0x14009fc65  mov     [r11-0A8h], rdi
0x14009fc6c  xorps   xmm0, xmm0
0x14009fc6f  xor     eax, eax
0x14009fc71  movups  xmmword ptr [rsp+1F8h+ApcState.ApcListHead.Blink], xmm0
0x14009fc79  movups  xmmword ptr [rsp+1F8h+ApcState.ApcListHead.Blink+10h], xmm0
0x14009fc81  mov     [r11-80h], rax
0x14009fc85  mov     rax, [rsi+30h]
0x14009fc89  mov     [rsp+1F8h+Size], rax
0x14009fc8e  lea     rbx, [rcx+8]
0x14009fc92  mov     [rsp+1F8h+var_170], rbx
0x14009fc9a  lea     r15d, [rdi+1]
0x14009fc9e  mov     r8b, r15b; unsigned __int8
0x14009fca1  mov     rdx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x14009fca4  mov     rcx, [rbx]; this
0x14009fca7  call    ?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z; VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)
0x14009fcac  mov     rcx, [rbx]; this
0x14009fcaf  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x14009fcb4  test    al, al
0x14009fcb6  jz      short loc_14009FCEA
0x14009fcb8  mov     r14d, 0C00002B6h
0x14009fcbe  cmp     [rsp+1F8h+var_198], dil
0x14009fcc3  jnz     loc_14009FED0
0x14009fcc9  mov     rdx, rsi
0x14009fccc  lea     ecx, [rdi+4]
0x14009fccf  call    cs:__imp_WdLogSingleEntry1
0x14009fcd6  nop     dword ptr [rax+rax+00h]
0x14009fcdb  mov     cs:WdLogGlobalForLineNumber, 311h
0x14009fce5  jmp     loc_1400A0A2A
0x14009fcea  cmp     [rsi+28h], dil
0x14009fcee  jz      loc_14009FF8C
0x14009fcf4  cmp     [rsi+0BCh], edi
0x14009fcfa  jle     short loc_14009FD31
0x14009fcfc  mov     byte ptr [rsp+1F8h+var_1D0], dil; bool
0x14009fd01  mov     byte ptr [rsp+1F8h+Timeout], dil; bool
0x14009fd06  mov     r9, [r12+10h]; unsigned __int64
0x14009fd0b  xor     r8d, r8d; unsigned __int64
0x14009fd0e  mov     rdx, [rsp+1F8h+Size]; struct VIDMM_LOCAL_ALLOC *
0x14009fd13  call    ?UnlockAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_K1_N2@Z; VIDMM_GLOBAL::UnlockAllocation(VIDMM_LOCAL_ALLOC *,unsigned __int64,unsigned __int64,bool,bool)
0x14009fd18  mov     rdx, [r12+10h]; unsigned __int64
0x14009fd1d  mov     rcx, [rbx]; this
0x14009fd20  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x14009fd25  and     dword ptr [rsi+20h], 0FFFFFFFDh
0x14009fd29  mov     rcx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x14009fd2c  call    ?VidMmiRemoveProbeAndLockReference@@YAXPEAUVIDMM_GLOBAL_ALLOC@@@Z; VidMmiRemoveProbeAndLockReference(VIDMM_GLOBAL_ALLOC *)
0x14009fd31  mov     [rsp+1F8h+var_100], rdi
0x14009fd39  mov     qword ptr [rsp+1F8h+var_F8+8], rdi
0x14009fd41  mov     qword ptr [rsp+1F8h+var_F8], r14
0x14009fd49  mov     [rsp+1F8h+var_E8], rdi
0x14009fd51  mov     [rsp+1F8h+var_D8], rdi
0x14009fd59  mov     [rsp+1F8h+var_108], rbx
0x14009fd61  mov     rax, [r12+70h]
0x14009fd66  mov     [rsp+1F8h+var_D0], rax
0x14009fd6e  mov     rax, [r13+10h]
0x14009fd72  mov     [rsp+1F8h+var_118], rax
0x14009fd7a  mov     [rsp+1F8h+var_110], r12
0x14009fd82  mov     rax, [r12+10h]
0x14009fd87  mov     [rsp+1F8h+var_E0], rax
0x14009fd8f  mov     rax, [rsp+1F8h+Size]
0x14009fd94  mov     rcx, [rax+8]
0x14009fd98  lea     rdx, [rsp+1F8h+ApcState]; ApcState
0x14009fda0  mov     rcx, [rcx+10h]; PROCESS
0x14009fda4  call    cs:__imp_KeStackAttachProcess
0x14009fdab  nop     dword ptr [rax+rax+00h]
0x14009fdb0  mov     rcx, [r13+10h]
0x14009fdb4  mov     rax, [rcx]
0x14009fdb7  mov     rax, [rax+0D8h]
0x14009fdbe  mov     r8, r12
0x14009fdc1  mov     rdx, r14
0x14009fdc4  call    _guard_dispatch_icall
0x14009fdc9  movzx   eax, [rsp+1F8h+var_198]
0x14009fdce  add     eax, eax
0x14009fdd0  mov     dword ptr [rsp+1F8h+var_1D0], eax
0x14009fdd4  lea     rax, [rsp+1F8h+var_118]
0x14009fddc  mov     [rsp+1F8h+Timeout], rax
0x14009fde1  lea     r9, ?VidMmRotateCopyCallback@@YAJPEAU_MDL@@0PEAX@Z; VidMmRotateCopyCallback(_MDL *,_MDL *,void *)
0x14009fde8  xor     r8d, r8d
0x14009fdeb  mov     rdx, r12
0x14009fdee  mov     rcx, [rbx]
0x14009fdf1  call    ?VidMmRotateLegacyAllocation@@YAJPEAVVIDMM_GLOBAL@@PEAUVIDMM_PHYSICAL_ALLOC@@W4_MM_ROTATE_DIRECTION@@P6AJPEAU_MDL@@3PEAX@ZPEAUVIDMM_ROTATE_COPY_CONTEXT@@TVIDMM_ROTATE_FLAGS@@@Z; VidMmRotateLegacyAllocation(VIDMM_GLOBAL *,VIDMM_PHYSICAL_ALLOC *,_MM_ROTATE_DIRECTION,long (*)(_MDL *,_MDL *,void *),VIDMM_ROTATE_COPY_CONTEXT *,VIDMM_ROTATE_FLAGS)
0x14009fdf6  movsxd  r14, eax
0x14009fdf9  lea     rcx, [rsp+1F8h+ApcState]; ApcState
0x14009fe01  call    cs:__imp_KeUnstackDetachProcess
0x14009fe08  nop     dword ptr [rax+rax+00h]
0x14009fe0d  cmp     [rsp+1F8h+var_198], dil
0x14009fe12  jz      short loc_14009FE70
0x14009fe14  test    r14d, r14d
0x14009fe17  jns     loc_14009FEC3
0x14009fe1d  bts     dword ptr [rsi+18h], 10h
0x14009fe22  mov     r10, [rbx]
0x14009fe25  mov     rcx, [r12+78h]
0x14009fe2a  lea     rax, [rcx+8]
0x14009fe2e  neg     rcx
0x14009fe31  sbb     rdx, rdx
0x14009fe34  and     rdx, rax
0x14009fe37  mov     rax, [r12+70h]
0x14009fe3c  mov     qword ptr [rsp+1F8h+var_1C0], rax; unsigned __int64
0x14009fe41  mov     [rsp+1F8h+var_1C8], rdx; struct VIDMM_SEGMENT_BASE *
0x14009fe46  mov     eax, [r10+0C78h]
0x14009fe4d  mov     dword ptr [rsp+1F8h+var_1D0], eax; unsigned int
0x14009fe51  mov     rax, [r12+10h]
0x14009fe56  mov     [rsp+1F8h+Timeout], rax; unsigned __int64
0x14009fe5b  xor     r9d, r9d; unsigned __int64
0x14009fe5e  mov     r8, rsi; struct VIDMM_GLOBAL_ALLOC *
0x14009fe61  mov     rdx, [rsp+1F8h+var_190]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x14009fe66  mov     rcx, r10; this
0x14009fe69  call    ?FillAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@_K2IPEBUVIDMM_SEGMENT_BASE@@2@Z; VIDMM_GLOBAL::FillAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,uint,VIDMM_SEGMENT_BASE const *,unsigned __int64)
0x14009fe6e  jmp     short loc_14009FEBE
0x14009fe70  test    r14d, r14d
0x14009fe73  jns     short loc_14009FEBB
0x14009fe75  mov     rdx, r14
0x14009fe78  mov     ecx, r15d
0x14009fe7b  call    cs:__imp_WdLogSingleEntry1
0x14009fe82  nop     dword ptr [rax+rax+00h]
0x14009fe87  mov     cs:WdLogGlobalForLineNumber, 390h
0x14009fe91  mov     qword ptr [rsp+1F8h+var_1C0], rdi
0x14009fe96  mov     [rsp+1F8h+var_1C8], rdi
0x14009fe9b  mov     [rsp+1F8h+var_1D0], rdi
0x14009fea0  mov     [rsp+1F8h+Timeout], r14
0x14009fea5  lea     r9, aFailedToRotate; "Failed to rotate VAD to CpuHostAperture"...
0x14009feac  mov     edx, 40000h
0x14009feb1  call    DxgkLogInternalTriageEvent
0x14009feb6  jmp     loc_1400A0A2A
0x14009febb  mov     r14d, edi
0x14009febe  test    r14d, r14d
0x14009fec1  js      short loc_14009FEC7
0x14009fec3  add     [rsi+24h], r15d
0x14009fec7  mov     [rsi+2Bh], r15b
0x14009fecb  mov     [rsp+1F8h+var_197], r15b
0x14009fed0  mov     rdx, [rsp+1F8h+var_180]
0x14009fed5  mov     rcx, [rdx+78h]; this
0x14009fed9  mov     [r12+88h], rcx
0x14009fee1  mov     rax, [rdx+70h]
0x14009fee5  mov     [r12+90h], rax
0x14009feed  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x14009fef2  mov     rcx, [rsi+180h]
0x14009fef9  mov     [rcx+0Ah], ax
0x14009fefd  mov     rax, [r12+88h]
0x14009ff05  mov     rcx, [rax+18h]
0x14009ff09  add     rcx, [r12+90h]
0x14009ff11  mov     rax, [rsi+180h]
0x14009ff18  mov     [rax+28h], rcx
0x14009ff1c  mov     [rdx+78h], rdi
0x14009ff20  mov     eax, [rsi+20h]
0x14009ff23  test    al, 2
0x14009ff25  jz      short loc_14009FF50
0x14009ff27  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC *
0x14009ff2a  mov     rdx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x14009ff2d  mov     rcx, [r13+8]; this
0x14009ff31  call    ?UnlockAllocationBackingStore@VIDMM_SEGMENT@@SAXPEAVVIDMM_GLOBAL@@PEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_LOCAL_ALLOC@@@Z; VIDMM_SEGMENT::UnlockAllocationBackingStore(VIDMM_GLOBAL *,VIDMM_GLOBAL_ALLOC *,VIDMM_LOCAL_ALLOC *)
0x14009ff36  mov     rdx, [r12+10h]; unsigned __int64
0x14009ff3b  mov     rcx, [r13+8]; this
0x14009ff3f  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x14009ff44  and     dword ptr [rsi+20h], 0FFFFFFFDh
0x14009ff48  mov     eax, [rsi+20h]
0x14009ff4b  mov     rdx, [rsp+1F8h+var_180]
0x14009ff50  cmp     [rsp+1F8h+var_197], dil
0x14009ff55  jz      loc_1400A08C7
0x14009ff5b  test    al, 8
0x14009ff5d  jnz     loc_1400A08C7
0x14009ff63  mov     rbx, [rsp+1F8h+var_190]
0x14009ff68  cmp     [rdx+0E8h], rdi
0x14009ff6f  jnz     loc_1400A08CC
0x14009ff75  xor     r9d, r9d
0x14009ff78  mov     r8, rsi
0x14009ff7b  mov     rdx, rbx
0x14009ff7e  mov     rcx, [r13+8]
0x14009ff82  call    ?ResetBackingStore@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_RESET_BACKING_STORE_REASON@@@Z; VIDMM_GLOBAL::ResetBackingStore(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,VIDMM_RESET_BACKING_STORE_REASON)
0x14009ff87  jmp     loc_1400A08CC
0x14009ff8c  mov     r14d, 0C0000001h
0x14009ff92  cmp     [rsi+2Ah], dil
0x14009ff96  jnz     short loc_1400A0003
0x14009ff98  mov     rdx, [rsi+0F0h]
0x14009ff9f  test    rdx, rdx
0x14009ffa2  jz      short loc_14009FFB7
0x14009ffa4  mov     rcx, [rsi+0E8h]
0x14009ffab  mov     rax, [rcx]
0x14009ffae  mov     rax, [rax+60h]
0x14009ffb2  call    _guard_dispatch_icall
0x14009ffb7  mov     eax, [rsi+18h]
0x14009ffba  test    al, 4
0x14009ffbc  jnz     short loc_14009FFFB
0x14009ffbe  mov     eax, [rsi+1Ch]
0x14009ffc1  test    al, 4
0x14009ffc3  jnz     short loc_14009FFFB
0x14009ffc5  mov     rcx, [rbx]; this
0x14009ffc8  mov     rax, [r12+70h]
0x14009ffcd  mov     qword ptr [rsp+1F8h+var_1C0], rax; unsigned __int64
0x14009ffd2  mov     [rsp+1F8h+var_1C8], rbx; struct VIDMM_SEGMENT_BASE *
0x14009ffd7  mov     eax, [rcx+0C78h]
0x14009ffdd  mov     dword ptr [rsp+1F8h+var_1D0], eax; unsigned int
0x14009ffe1  mov     rax, [r12+10h]
0x14009ffe6  mov     [rsp+1F8h+Timeout], rax; unsigned __int64
0x14009ffeb  xor     r9d, r9d; unsigned __int64
0x14009ffee  mov     r8, rsi; struct VIDMM_GLOBAL_ALLOC *
0x14009fff1  mov     rdx, [rsp+1F8h+var_190]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x14009fff6  call    ?FillAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@_K2IPEBUVIDMM_SEGMENT_BASE@@2@Z; VIDMM_GLOBAL::FillAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,unsigned __int64,unsigned __int64,uint,VIDMM_SEGMENT_BASE const *,unsigned __int64)
0x14009fffb  mov     r14d, edi
0x14009fffe  mov     [rsp+1F8h+var_197], r15b
0x1400a0003  test    r14d, r14d
0x1400a0006  jns     loc_1400A03FE
0x1400a000c  mov     [rsp+1F8h+var_198], dil
0x1400a0011  lea     rax, [rsp+1F8h+var_197]
0x1400a0016  mov     [rsp+1F8h+var_1C8], rax; bool *
0x1400a001b  lea     rax, [rsp+1F8h+var_198]
0x1400a0020  mov     [rsp+1F8h+var_1D0], rax; bool *
0x1400a0025  mov     rax, [r12+70h]
0x1400a002a  mov     [rsp+1F8h+Timeout], rax; unsigned __int64
0x1400a002f  mov     r9d, r15d; enum _DXGK_MEMORY_TRANSFER_DIRECTION
0x1400a0032  mov     r8, r12; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a0035  mov     rdx, [rsp+1F8h+var_190]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a003a  mov     rcx, r13; this
0x1400a003d  call    ?TransferMemory@VIDMM_MEMORY_SEGMENT@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@W4_DXGK_MEMORY_TRANSFER_DIRECTION@@_KPEA_N4@Z; VIDMM_MEMORY_SEGMENT::TransferMemory(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,_DXGK_MEMORY_TRANSFER_DIRECTION,unsigned __int64,bool *,bool *)
0x1400a0042  mov     r14d, eax
0x1400a0045  cmp     [rsp+1F8h+var_198], dil
0x1400a004a  jz      short loc_1400A0060
0x1400a004c  mov     r9b, r15b; bool
0x1400a004f  mov     r8, r12; struct VIDMM_PHYSICAL_ALLOC_LEGACY *
0x1400a0052  mov     rdx, [rsp+1F8h+var_190]; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400a0057  mov     rcx, [r13+10h]; struct VIDMM_PHYSICAL_ADAPTER_LEGACY *
0x1400a005b  call    ?VidMmReleaseTemporaryResourcesForLegacyAllocation@@YAXPEAUVIDMM_PHYSICAL_ADAPTER_LEGACY@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_N@Z; VidMmReleaseTemporaryResourcesForLegacyAllocation(VIDMM_PHYSICAL_ADAPTER_LEGACY *,VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool)
0x1400a0060  test    r14d, r14d
0x1400a0063  jns     loc_1400A03FE
0x1400a0069  mov     ebx, edi
0x1400a006b  mov     [rsp+1F8h+var_158], ebx
0x1400a0072  mov     r14, [rsp+1F8h+var_170]
0x1400a007a  mov     [rsp+1F8h+var_138], r14
0x1400a0082  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400a0089  cmp     [rax], dil
0x1400a008c  jz      short loc_1400A00A4
0x1400a008e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400a0095  nop     dword ptr [rax+rax+00h]
0x1400a009a  mov     cs:WdLogGlobalForLineNumber, 3FDh
0x1400a00a4  test    cs:byte_140086201, r15b
0x1400a00ab  jz      short loc_1400A00BF
0x1400a00ad  mov     r9d, 2
0x1400a00b3  lea     rdx, EventPerformanceWarning
0x1400a00ba  call    McTemplateK0q_EtwWriteTransfer
0x1400a00bf  lea     r9, [rsi+180h]
0x1400a00c6  mov     [rsp+1F8h+var_160], r9
0x1400a00ce  mov     rax, [r9]
0x1400a00d1  mov     ecx, [rax]
0x1400a00d3  test    cl, 8
0x1400a00d6  jnz     short loc_1400A00F9
0x1400a00d8  mov     rax, [rsp+1F8h+Size]
0x1400a00dd  mov     rcx, [rax+8]
0x1400a00e1  lea     rdx, [rsp+1F8h+ApcState]; ApcState
0x1400a00e9  mov     rcx, [rcx+10h]; PROCESS
0x1400a00ed  call    cs:__imp_KeStackAttachProcess
0x1400a00f4  nop     dword ptr [rax+rax+00h]
0x1400a00f9  mov     rdx, [r12+78h]
0x1400a00fe  mov     rcx, r12
0x1400a0101  call    Use64KbPagesForTransfer
0x1400a0106  mov     r8, [r12+10h]
0x1400a010b  mov     cl, al
0x1400a010d  neg     cl
0x1400a010f  sbb     rdx, rdx
0x1400a0112  and     edx, 0F000h
0x1400a0118  add     rdx, 1000h
0x1400a011f  mov     [rsp+1F8h+Size], rdx
0x1400a0124  mov     rcx, r8
0x1400a0127  shr     rcx, 0Ch
0x1400a012b  shr     r8, 10h
0x1400a012f  test    al, al
0x1400a0131  cmovz   r8d, ecx
0x1400a0135  mov     [rsp+1F8h+var_168], r8
0x1400a013d  mov     [rsp+1F8h+var_154], r8d
0x1400a0145  mov     rax, [r12+70h]
0x1400a014a  mov     [rsp+1F8h+var_128], rax
0x1400a0152  mov     [rsp+1F8h+var_B8], rax
0x1400a015a  mov     eax, edi
0x1400a015c  mov     [rsp+1F8h+var_178], eax
0x1400a0163  cmp     eax, r8d
0x1400a0166  jnb     loc_1400A03C8
0x1400a016c  mov     [rsp+1F8h+var_130], rdi
  ... truncated ...
```
