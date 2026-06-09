# VIDMM_MEMORY_SEGMENT::TransferToSystem(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool,VIDMM_LOCAL_ALLOC *,bool)

- ea: `0x140094660`
- end: `0x14009548d`
- name: `?TransferToSystem@VIDMM_MEMORY_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_NPEAUVIDMM_LOCAL_ALLOC@@2@Z`
- size: `3629`
- prototype: `void __usercall(VIDMM_MEMORY_SEGMENT *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, struct VIDMM_PHYSICAL_ALLOC_LEGACY *@<r8>, bool@<r9b>, struct VIDMM_LOCAL_ALLOC *, bool)`
- caller_count: `2`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400944c0`
- `0x1400cfac0`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140012e28`
- `0x140030ae0`
- `0x140030f08`
- `0x140031138`
- `0x140032d3c`
- `0x1400335c4`
- `0x1400336b8`
- `0x140035984`
- `0x14003f9c4`
- `0x140044dc8`
- `0x140049320`
- `0x14004a778`
- `0x140058680`
- `0x140058760`
- `0x1400587c0`
- `0x140058ac0`
- `0x140094660`
- `0x140095494`
- `0x14009a6b8`
- `0x14009b1ac`
- `0x14009b254`
- `0x14009c5f8`
- `0x14009d45c`
- `0x1400a0a58`
- `0x1400a6bac`
- `0x1400addc4`
- `0x1400ce13c`
- `0x1400d6c94`
- `0x1400e6a00`
- `0x1400ed9e0`
- `0x1400f16f0`
- `0x1400f1710`
- `0x1400f9d10`
- `0x1400fcf18`
- `0x1400fdb18`
- `0x140109c10`
- `0x14010ad3c`
- `0x14010c9b8`
- `0x14010db5c`
- `0x140117138`
- `0x14011f5a8`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140094d45`
- `ntoskrnl!KeStackAttachProcess` at `0x140094d45`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140094fbf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140094fbf`
- `ntoskrnl!PsIsProcessCommitRelinquished` at `0x1400947c3`
- `ntoskrnl!PsIsProcessCommitRelinquished` at `0x1400947c3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140095385`
- `ntoskrnl!KeWaitForSingleObject` at `0x140095385`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140094a27`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140094c3e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140094ce7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140094a27`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140094c3e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140094ce7`
- `watchdog!WdLogSingleEntry5` at `0x140094c18`
- `watchdog!WdLogSingleEntry5` at `0x14009541b`
- `watchdog!WdLogSingleEntry5` at `0x140094c18`
- `watchdog!WdLogSingleEntry5` at `0x14009541b`
- `watchdog!WdLogSingleEntry0` at `0x140094950`
- `watchdog!WdLogSingleEntry0` at `0x140094eee`
- `watchdog!WdLogSingleEntry0` at `0x140094950`
- `watchdog!WdLogSingleEntry0` at `0x140094eee`
- `watchdog!WdLogSingleEntry1` at `0x1400947fd`
- `watchdog!WdLogSingleEntry1` at `0x1400947fd`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140094bf4`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400953f9`
- `dxgkrnl!g_IsInternalRelease` at `0x1400953ed`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140094a1b`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140094c32`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140094cdb`

## string_xrefs

- `0x140094f28`: `Exception occurred while accessing allocation (user mode page).\n`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_MEMORY_SEGMENT::TransferToSystem(
        VIDMM_GLOBAL **this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        struct VIDMM_PHYSICAL_ALLOC_LEGACY *a3,
        unsigned __int8 a4,
        struct VIDMM_LOCAL_ALLOC *a5,
        bool a6)
{
  struct VIDMM_GLOBAL_ALLOC *v9; // rsi
  VIDMM_GLOBAL **v10; // r13
  unsigned __int16 v11; // ax
  __int64 v12; // r10
  int *v13; // rbx
  int v14; // r8d
  _DWORD *v15; // rcx
  int v16; // edx
  int v17; // edx
  __int64 v18; // rcx
  int v19; // r8d
  int v20; // edx
  unsigned __int64 v21; // rax
  __int64 v22; // rdx
  int v23; // ecx
  int v24; // r8d
  VIDMM_PROCESS *v25; // rcx
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v26; // rsi
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  char v30; // al
  unsigned __int64 v31; // rdx
  __int64 v32; // r8
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rdx
  _QWORD *v35; // rcx
  unsigned int v36; // eax
  unsigned __int64 v37; // rbx
  unsigned __int64 LogicalAddress; // rax
  VIDMM_GLOBAL *v39; // r10
  void *v40; // rax
  char v41; // dl
  VIDMM_GLOBAL *v42; // r8
  char *v43; // r9
  VIDMM_GLOBAL *v44; // r10
  VIDMM_GLOBAL *v45; // r9
  struct DXG_DEFERRED_QUEUE_WORK_ITEM *v46; // rcx
  _QWORD *v47; // rax
  void *v48; // r8
  struct DXG_DEFERRED_QUEUE_WORK_ITEM *v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  int v52; // edx
  int v53; // r8d
  int Timeout; // [rsp+20h] [rbp-1C8h]
  struct VIDMM_SEGMENT_BASE *v55; // [rsp+28h] [rbp-1C0h]
  char v56; // [rsp+50h] [rbp-198h]
  bool v57; // [rsp+51h] [rbp-197h] BYREF
  int v58; // [rsp+54h] [rbp-194h]
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v59; // [rsp+58h] [rbp-190h]
  char v60[4]; // [rsp+60h] [rbp-188h] BYREF
  unsigned int v61; // [rsp+64h] [rbp-184h]
  struct DXG_DEFERRED_QUEUE_WORK_ITEM *v62; // [rsp+68h] [rbp-180h] BYREF
  void *v63; // [rsp+70h] [rbp-178h] BYREF
  size_t Size; // [rsp+78h] [rbp-170h]
  int *v65; // [rsp+80h] [rbp-168h]
  __int64 (__fastcall *v66)(VIDMM_SEGMENT *__hidden, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool *, void *); // [rsp+90h] [rbp-158h] BYREF
  int v67; // [rsp+98h] [rbp-150h]
  int v68; // [rsp+9Ch] [rbp-14Ch]
  _QWORD *v69; // [rsp+A0h] [rbp-148h] BYREF
  int v70; // [rsp+ACh] [rbp-13Ch]
  struct VIDMM_GLOBAL_ALLOC *v71; // [rsp+B0h] [rbp-138h]
  char *v72; // [rsp+B8h] [rbp-130h]
  VIDMM_GLOBAL **v73; // [rsp+C0h] [rbp-128h]
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v74; // [rsp+C8h] [rbp-120h]
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v75; // [rsp+D0h] [rbp-118h]
  _BYTE v76[80]; // [rsp+E0h] [rbp-108h] BYREF
  _QWORD *v77; // [rsp+130h] [rbp-B8h] BYREF
  struct _KAPC_STATE v78; // [rsp+138h] [rbp-B0h] BYREF
  VIDMM_PROCESS *v79; // [rsp+168h] [rbp-80h]
  _KAPC_STATE ApcState; // [rsp+170h] [rbp-78h] BYREF

  v59 = a2;
  v73 = this;
  v74 = a2;
  v75 = a3;
  Size = (size_t)a5;
  v71 = *(struct VIDMM_GLOBAL_ALLOC **)a3;
  v9 = v71;
  memset(&ApcState, 0, sizeof(ApcState));
  v57 = 0;
  v10 = this + 1;
  v72 = (char *)(this + 1);
  VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(this[1], v71, 0);
  if ( *((_QWORD *)*v10 + 4670) )
  {
    v11 = VIDMM_SEGMENT::DriverId((VIDMM_SEGMENT *)this);
    HIDWORD(v55) = HIDWORD(v71);
    Timeout = 4;
    VIDMM_GLOBAL::RecordPageMappingHistory(v12, v11);
  }
  v13 = (int *)((char *)v71 + 24);
  v65 = (int *)((char *)v71 + 24);
  v14 = *((_DWORD *)v71 + 6);
  if ( (v14 & 4) != 0 )
  {
    v61 = 2;
  }
  else
  {
    v61 = 2;
    if ( (*((_BYTE *)v71 + 28) & 2) == 0 && (v14 & 0x40) == 0 )
      goto LABEL_8;
  }
  a4 = 0;
LABEL_8:
  v62 = (struct VIDMM_GLOBAL_ALLOC *)((char *)v71 + 384);
  v15 = (_DWORD *)*((_QWORD *)v71 + 48);
  if ( (*v15 & 0x20000) != 0 && ((_DWORD)this[8] & 0x40000) == 0 )
    *v13 = v14 | 0x10000;
  if ( (*v15 & 0x20000000) == 0
    && (unsigned __int8)PsIsProcessCommitRelinquished(*(_QWORD *)(*(_QWORD *)(Size + 8) + 16LL)) )
  {
    *v13 |= 0x10000u;
  }
  v16 = a4;
  if ( (*v13 & 0x10000) != 0 )
    v16 = 0;
  v58 = v16;
  if ( VIDMM_GLOBAL::IsTdrPending(*v10) )
  {
    WdLogSingleEntry1(4, v9);
    WdLogGlobalForLineNumber = 1619;
    LOBYTE(v17) = 0;
    v58 = v17;
  }
  if ( (VIDMM_GLOBAL::_Config & 8) == 0 && (*((_DWORD *)v9 + 8) & 8) != 0 )
    *((_BYTE *)v9 + 43) = 1;
  if ( (_BYTE)v17 && (*((_DWORD *)v9 + 8) & 8) != 0 && !*((_BYTE *)v9 + 43) && Size )
  {
    VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
      (VIDMM_PROCESS_AUTOATTACH *)&v77,
      *(struct VIDMM_PROCESS **)(Size + 8),
      1);
    LODWORD(v63) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v9 + 29) + 40LL))(
                     *((_QWORD *)v9 + 29),
                     *((_QWORD *)v9 + 30),
                     *(_QWORD *)(*((_QWORD *)v9 + 6) + 16LL),
                     *((_QWORD *)a3 + 2));
    VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)&v77);
    v20 = (int)v63;
    if ( (int)v63 < 0 )
    {
      *((_BYTE *)v9 + 43) = 1;
      v18 = (__int64)*v10 + 3552;
    }
    else
    {
      v18 = (__int64)*v10 + 3536;
    }
    v21 = *((_QWORD *)a3 + 2);
    _InterlockedAdd((volatile signed __int32 *)v18, 1u);
    _InterlockedAdd64((volatile signed __int64 *)(v18 + 8), v21);
    if ( (byte_140086201 & 1) != 0 )
      McTemplateK0pqqt_EtwWriteTransfer(v18, v20 >= 0, v19, (_DWORD)v9, Timeout, *((_QWORD *)a3 + 2) >> 12, v20 >= 0);
    LOBYTE(v17) = v58;
  }
  LOBYTE(v18) = *((_BYTE *)v9 + 43) != 0 ? v17 : 0;
  v56 = v18;
  v22 = *((unsigned int *)v9 + 8);
  if ( (v22 & 8) != 0
    || (*((_DWORD *)v9 + 7) & 0x100) == 0
    || *((_DWORD *)v9 + 9)
    || (v22 & 2) != 0
    || *((_QWORD *)a3 + 29) )
  {
    goto LABEL_40;
  }
  if ( (*v13 & 0x400000) == 0 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1707;
    DxgkLogInternalTriageEvent(
      v23,
      0x40000,
      v24,
      (unsigned int)L"Failed to reset allocations early enough.",
      1707,
      0,
      0,
      0);
    LOBYTE(v18) = v56;
  }
  if ( (_BYTE)v18 )
  {
    VIDMM_GLOBAL::ResetBackingStore(*v10, v59, v9, 0);
    LOBYTE(v18) = v56;
LABEL_40:
    if ( (_BYTE)v18 )
    {
      if ( (**(_DWORD **)v62 & 0x8000000) != 0 && !*((_DWORD *)v9 + 9) )
      {
        v18 = 2;
        if ( (*((_DWORD *)v9 + 8) & 2) == 0
          && (int)VIDMM_GLOBAL::ChargePinnedBackingStore(*v10, *((_QWORD *)a3 + 2)) >= 0 )
        {
          if ( VIDMM_SEGMENT::LockAllocationBackingStore((VIDMM_SEGMENT *)this, v9) < 0 )
            VIDMM_GLOBAL::ReturnPinnedBackingStore(*v10, *((_QWORD *)a3 + 2));
          else
            *((_DWORD *)v9 + 8) |= 2u;
        }
      }
      LOBYTE(v18) = v56;
    }
  }
  if ( (*v13 & 4) == 0 && *((_DWORD *)v9 + 9) )
  {
    if ( g_IsInternalReleaseOrDbg )
    {
      WdLogNewEntry5_WdTrace(v18, v22);
      WdLogGlobalForLineNumber = 1765;
    }
    memset(v76, 0, sizeof(v76));
    if ( v56 )
    {
      (*(void (__fastcall **)(VIDMM_GLOBAL *, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *))(*(_QWORD *)this[2] + 216LL))(
        this[2],
        v59,
        a3);
      *(_QWORD *)&v76[32] = v59;
      *(_QWORD *)&v76[48] = 0;
      *(_QWORD *)&v76[64] = 0;
      *(_DWORD *)&v76[44] = 2;
      *(_QWORD *)&v76[16] = v10;
      *(_QWORD *)&v76[72] = *((_QWORD *)a3 + 14);
      *(_DWORD *)&v76[24] = 0;
      *(_QWORD *)v76 = this[2];
      *(_QWORD *)&v76[8] = a3;
      *(_QWORD *)&v76[56] = *((_QWORD *)a3 + 2);
      v62 = (struct DXG_DEFERRED_QUEUE_WORK_ITEM *)VidMmRotateCopyCallback;
      v58 = 3;
    }
    else
    {
      v62 = 0;
      v58 = 3;
      v61 = 3;
    }
    if ( !a6 || !*((_BYTE *)v9 + 40) )
      v58 = 1;
    LOBYTE(v77) = 0;
    v79 = *(VIDMM_PROCESS **)(Size + 8);
    VIDMM_PROCESS::SafeAttach(v79, &v78);
    LOBYTE(v77) = 1;
    LODWORD(v55) = v58;
    v10 = (VIDMM_GLOBAL **)(int)VidMmRotateLegacyAllocation(*v10, a3, v61, v62, v76, v55);
    if ( (_BYTE)v77 )
    {
      VIDMM_PROCESS::SafeDetach(v25, &v78);
      LOBYTE(v77) = 0;
    }
    if ( (_DWORD)v10 == -1073741558 )
    {
      *v13 |= 0x10000u;
LABEL_63:
      VidMmDecrementRotateCount(v9, 1u);
LABEL_64:
      v26 = v59;
      goto LABEL_65;
    }
    if ( (int)v10 >= 0 )
      goto LABEL_63;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 4);
    WdLogGlobalForLineNumber = 222;
  }
  if ( (_BYTE)v18 )
  {
    if ( (int)VIDMM_MEMORY_SEGMENT::TransferMemory(
                (VIDMM_MEMORY_SEGMENT *)this,
                v59,
                a3,
                DXGK_MEMORY_TRANSFER_LOCAL_TO_SYSTEM,
                *((_QWORD *)a3 + 18),
                &v57,
                0) < 0 )
    {
      if ( g_IsInternalReleaseOrDbg )
      {
        WdLogNewEntry5_WdTrace(v28, v27);
        WdLogGlobalForLineNumber = 1892;
      }
      if ( (byte_140086201 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v28, EventPerformanceWarning, v29, 2);
      v61 = 0;
      if ( (**(_DWORD **)v62 & 8) == 0 && Size )
      {
        KeStackAttachProcess(*(PRKPROCESS *)(*(_QWORD *)(Size + 8) + 16LL), &ApcState);
        v61 = 1;
      }
      v30 = Use64KbPagesForTransfer(a3, *((_QWORD *)a3 + 17));
      v31 = *((_QWORD *)a3 + 2);
      v32 = v30 != 0 ? 0x10000LL : 4096LL;
      Size = v32;
      v33 = v31 >> 12;
      v34 = v31 >> 16;
      if ( !v30 )
        v34 = (unsigned int)v33;
      v66 = (__int64 (__fastcall *)(VIDMM_SEGMENT *__hidden, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool *, void *))v34;
      v35 = (_QWORD *)*((_QWORD *)a3 + 18);
      v69 = v35;
      v36 = 0;
      while ( 1 )
      {
        v58 = v36;
        if ( v36 >= (unsigned int)v34 )
          break;
        v37 = v32 * v36;
        v78.ApcListHead[0].Flink = 0;
        *(_OWORD *)&v78.ApcListHead[1].Blink = 0;
        memset(v76, 0, 48);
        v77 = v35;
        v78.ApcListHead[0].Blink = (struct _LIST_ENTRY *)v10;
        v78.ApcListHead[1].Flink = (struct _LIST_ENTRY *)v37;
        LogicalAddress = SysMmGetLogicalAddress(*((void *const *)*v10 + 5180));
        v39 = *v10;
        *(_QWORD *)&v76[32] = *((_QWORD *)*v10 + 5179);
        *(_QWORD *)&v76[40] = *(_QWORD *)&v76[32] + 48LL;
        *(_QWORD *)&v76[8] = LogicalAddress;
        VIDMM_GLOBAL::MemoryTransfer(
          v39,
          v59,
          v9,
          Size,
          v37,
          (struct VIDMM_TRANSFER_PARAMETER *)&v77,
          (struct VIDMM_TRANSFER_PARAMETER *)v76,
          0);
        VIDMM_GLOBAL::WaitForAllPagingEngines(*v10, v59, v9);
        v63 = 0;
        v40 = VidMmMapViewOfAllocation(v9, v37, Size, &v63);
        if ( v40 )
        {
          memmove(v40, *((const void **)*v10 + 5178), Size);
          VidMmUnmapViewOfAllocation(v9, v63);
          v13 = v65;
        }
        else
        {
          v13 = v65;
          *v65 |= 0x10000u;
        }
        v36 = v58 + 1;
        LODWORD(v34) = (_DWORD)v66;
        v32 = Size;
        v35 = v69;
      }
      if ( v61 )
        KeUnstackDetachProcess(&ApcState);
    }
  }
  else
  {
    if ( g_IsInternalReleaseOrDbg )
    {
      WdLogNewEntry5_WdTrace(v18, v22);
      WdLogGlobalForLineNumber = 1844;
    }
    if ( (*v13 & 4) == 0 )
      VIDMM_GLOBAL::DiscardAllocation(
        *v10,
        v59,
        v9,
        0,
        *((_QWORD *)a3 + 2),
        (struct VIDMM_SEGMENT_BASE *)((*((_QWORD *)a3 + 17) + 8LL)
                                    & ((unsigned __int128)-(__int128)*((unsigned __int64 *)a3 + 17) >> 64)),
        *((_QWORD *)a3 + 18));
  }
  if ( (**(_DWORD **)v62 & 0x20000) == 0 || !*((_QWORD *)a3 + 16) )
    goto LABEL_64;
  memset(v76, 0, 48);
  *(_DWORD *)v76 = *((unsigned __int16 *)this + 34);
  *(_DWORD *)&v76[4] = VIDMM_SEGMENT::DriverId((VIDMM_SEGMENT *)this);
  if ( !*((_DWORD *)this + 105) )
  {
    v41 = 1;
    *(_QWORD *)&v76[16] = *((_QWORD *)a3 + 18);
    *(_QWORD *)&v76[24] = ~(unsigned __int64)this[51] & ((unsigned __int64)this[51] + *((_QWORD *)a3 + 2));
LABEL_109:
    v63 = this + 32;
    goto LABEL_110;
  }
  v62 = 0;
  v60[0] = 0;
  v63 = this + 32;
  v66 = VIDMM_SEGMENT::CheckLowestAddress;
  v67 = 0;
  v68 = v70;
  if ( (unsigned int)VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(
                       (unsigned int)this[32],
                       (_DWORD)v59,
                       (unsigned int)this[53],
                       (unsigned int)this[54],
                       0,
                       (__int64)&v66,
                       (__int64)this,
                       (__int64)&v62,
                       (__int64)&v69,
                       (__int64)v60) != -1073741823
    || v62 != *((struct DXG_DEFERRED_QUEUE_WORK_ITEM **)a3 + 18) )
  {
    v41 = 0;
    goto LABEL_109;
  }
  v42 = this[54];
  v43 = (char *)*((_QWORD *)a3 + 16);
  while ( 1 )
  {
    v44 = (VIDMM_GLOBAL *)(*(_QWORD *)v43 + *((_QWORD *)v43 + 1));
    if ( v44 >= v42 )
      break;
    v45 = (VIDMM_GLOBAL *)*((_QWORD *)v43 + 5);
    if ( v45 != (VIDMM_GLOBAL *)((char *)this[32] + 80) )
    {
      v43 = (char *)v45 - 40;
      if ( v43[56] == 2 )
        continue;
    }
    goto LABEL_105;
  }
  v44 = this[54];
LABEL_105:
  v46 = (struct DXG_DEFERRED_QUEUE_WORK_ITEM *)((unsigned __int64)v44 & ~(unsigned __int64)this[51]);
  v62 = v46;
  if ( v46 <= this[53] )
  {
    v63 = this + 32;
    v41 = 0;
  }
  else
  {
    *(_QWORD *)&v76[16] = this[53];
    *(_QWORD *)&v76[24] = this[55];
    *(_QWORD *)&v76[32] = v46;
    *(_QWORD *)&v76[40] = v42 - v46;
    this[55] = (VIDMM_GLOBAL *)(v42 - v46);
    this[53] = v46;
    v41 = 1;
  }
LABEL_110:
  if ( !v41 )
    goto LABEL_64;
  v62 = (struct DXG_DEFERRED_QUEUE_WORK_ITEM *)operator new(104, 825583958, 256);
  v47 = (_QWORD *)operator new(48, 943024470, 256);
  v48 = v47;
  v69 = v47;
  v49 = v62;
  if ( v62 )
  {
    if ( v47 )
    {
      *((_QWORD *)v62 + 2) = DeferredSetVprCallback;
      *((_QWORD *)v49 + 4) = DeferredSetVprCompletionCallback;
      *(_OWORD *)((char *)v49 + 56) = *(_OWORD *)v76;
      *(_OWORD *)((char *)v49 + 72) = *(_OWORD *)&v76[16];
      *(_OWORD *)((char *)v49 + 88) = *(_OWORD *)&v76[32];
      *((_QWORD *)v49 + 5) = *v10;
      *((_QWORD *)v49 + 6) = v47;
      v47[2] = this;
      v47[3] = *((_QWORD *)a3 + 16);
      v47[4] = *((_QWORD *)a3 + 2);
      v47[5] = **((_QWORD **)v9 + 43);
      *((_QWORD *)v49 + 3) = v49;
      (*(void (__fastcall **)(VIDMM_GLOBAL *, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(*(_QWORD *)this[2] + 200LL))(
        this[2],
        v59);
      VIDMM_GLOBAL::FlushPagingBuffer(*v10, v59, 0);
      VIDMM_LINEAR_POOL::MarkBlockAsAllocatedScrubPending(
        *(VIDMM_LINEAR_POOL **)v63,
        *((void **)a3 + 16),
        *(unsigned __int64 *)&v76[16],
        *(unsigned __int64 *)&v76[32]);
      DXG_DEFERRED_WORK_QUEUE::QueueWorkItem((VIDMM_GLOBAL *)((char *)*v10 + 37440), v62);
      *((_QWORD *)a3 + 16) = 0;
      if ( *((_DWORD *)v9 + 18) != 1 )
      {
        VIDMM_SEGMENT::DecrementBytesCommitted(
          (VIDMM_SEGMENT *)this,
          **((struct VIDMM_PARTITION ***)v9 + 43),
          *((_QWORD *)a3 + 2));
        --*((_DWORD *)this + 88);
      }
      goto LABEL_64;
    }
    operator delete(v62);
    v48 = v69;
  }
  if ( v48 )
    operator delete(v48);
  if ( (unsigned int)DXG_DEFERRED_WORK_QUEUE::GetNumWorkItems((VIDMM_GLOBAL *)((char *)*v10 + 37440)) )
  {
    if ( (byte_140086201 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(v50, EventPerformanceWarning, v51, 24);
    KeWaitForSingleObject((char *)*v10 + 37488, Executive, 0, 0, 0);
  }
  v26 = v59;
  (*(void (__fastcall **)(VIDMM_GLOBAL *, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(*(_QWORD *)this[2] + 200LL))(
    this[2],
    v59);
  VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(*v10, v26, *((unsigned __int16 *)this + 34));
  VIDMM_SEGMENT::CheckFreeVPRReserve((VIDMM_SEGMENT *)this, (struct _DXGKARG_SETVIDEOPROTECTEDREGION *)v76);
  if ( (int)ADAPTER_RENDER::DdiSetVideoProtectedRegion(
              *(ADAPTER_RENDER **)(*((_QWORD *)*v10 + 3) + 3240LL),
              (const struct _DXGKARG_SETVIDEOPROTECTEDREGION *)v76) < 0
    && g_IsInternalRelease )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 9);
    WdLogGlobalForLineNumber = 222;
  }
  if ( (byte_140086201 & 1) != 0 )
    McTemplateK0qqqxxp_EtwWriteTransfer(
      *((_QWORD *)*v10 + 3),
      v52,
      v53,
      *(_DWORD *)v76,
      v76[4],
      v76[8],
      v76[32],
      v76[40],
      *((_QWORD *)*v10 + 3));
LABEL_65:
  *v13 &= ~0x400000u;
  if ( v57 )
    VidMmReleaseTemporaryResourcesForLegacyAllocation(this[2], v26, a3, 0);
}

```

## disassembly

```asm
0x140094660  mov     r11, rsp
0x140094663  push    rbx
0x140094664  push    rsi
0x140094665  push    rdi
0x140094666  push    r12
0x140094668  push    r13
0x14009466a  push    r14
0x14009466c  push    r15
0x14009466e  sub     rsp, 1B0h
0x140094675  mov     rax, cs:__security_cookie
0x14009467c  xor     rax, rsp
0x14009467f  mov     [rsp+1E8h+var_48], rax
0x140094687  mov     r12b, r9b
0x14009468a  mov     r14, r8
0x14009468d  mov     [rsp+1E8h+var_190], rdx
0x140094692  mov     r15, rcx
0x140094695  mov     [rsp+1E8h+var_128], rcx
0x14009469d  mov     [rsp+1E8h+var_120], rdx
0x1400946a5  mov     [rsp+1E8h+var_118], r8
0x1400946ad  mov     rax, [rsp+1E8h+arg_20]
0x1400946b5  mov     [rsp+1E8h+Size], rax
0x1400946ba  mov     rsi, [r8]
0x1400946bd  mov     [rsp+1E8h+var_138], rsi
0x1400946c5  xorps   xmm0, xmm0
0x1400946c8  movups  xmmword ptr [r11-78h], xmm0
0x1400946cd  movups  xmmword ptr [r11-68h], xmm0
0x1400946d2  movups  xmmword ptr [r11-58h], xmm0
0x1400946d7  xor     edi, edi
0x1400946d9  mov     [rsp+1E8h+var_197], dil
0x1400946de  lea     r13, [rcx+8]
0x1400946e2  mov     [rsp+1E8h+var_130], r13
0x1400946ea  xor     r8d, r8d; unsigned __int8
0x1400946ed  mov     rdx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400946f0  mov     rcx, [r13+0]; this
0x1400946f4  call    ?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z; VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)
0x1400946f9  mov     r10, [r13+0]
0x1400946fd  cmp     [r10+91F0h], rdi
0x140094704  jz      short loc_140094749
0x140094706  mov     rax, [r14+10h]
0x14009470a  test    rax, 0FFFh
0x140094710  mov     r9d, edi
0x140094713  setnz   r9b
0x140094717  shr     rax, 0Ch
0x14009471b  add     r9, rax
0x14009471e  mov     r8, [r14+90h]
0x140094725  shr     r8, 0Ch
0x140094729  mov     rcx, r15; this
0x14009472c  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x140094731  movzx   edx, ax
0x140094734  mov     [rsp+1E8h+var_1C0], rsi
0x140094739  mov     dword ptr [rsp+1E8h+Timeout], 4
0x140094741  mov     rcx, r10
0x140094744  call    ?RecordPageMappingHistory@VIDMM_GLOBAL@@QEAAXI_K0W4VIDMM_PAGE_HISTORY_TYPE@@0@Z; VIDMM_GLOBAL::RecordPageMappingHistory(uint,unsigned __int64,unsigned __int64,VIDMM_PAGE_HISTORY_TYPE,unsigned __int64)
0x140094749  lea     rbx, [rsi+18h]
0x14009474d  mov     [rsp+1E8h+var_168], rbx
0x140094755  mov     r8d, [rbx]
0x140094758  test    r8b, 4
0x14009475c  jnz     short loc_14009477A
0x14009475e  mov     edx, 2
0x140094763  mov     [rsp+1E8h+var_184], edx
0x140094767  test    [rsi+1Ch], dl
0x14009476a  setz    cl
0x14009476d  test    r8b, 40h
0x140094771  setz    al
0x140094774  test    al, cl
0x140094776  jz      short loc_140094782
0x140094778  jmp     short loc_140094785
0x14009477a  mov     [rsp+1E8h+var_184], 2
0x140094782  mov     r12b, dil
0x140094785  lea     rax, [rsi+180h]
0x14009478c  mov     [rsp+1E8h+var_180], rax
0x140094791  mov     rcx, [rax]
0x140094794  test    dword ptr [rcx], 20000h
0x14009479a  jz      short loc_1400947AE
0x14009479c  test    dword ptr [r15+40h], 40000h
0x1400947a4  jnz     short loc_1400947AE
0x1400947a6  bts     r8d, 10h
0x1400947ab  mov     [rbx], r8d
0x1400947ae  test    dword ptr [rcx], 20000000h
0x1400947b4  jnz     short loc_1400947D7
0x1400947b6  mov     rcx, [rsp+1E8h+Size]
0x1400947bb  mov     rcx, [rcx+8]
0x1400947bf  mov     rcx, [rcx+10h]
0x1400947c3  call    cs:__imp_PsIsProcessCommitRelinquished
0x1400947ca  nop     dword ptr [rax+rax+00h]
0x1400947cf  test    al, al
0x1400947d1  jz      short loc_1400947D7
0x1400947d3  bts     dword ptr [rbx], 10h
0x1400947d7  test    dword ptr [rbx], 10000h
0x1400947dd  movzx   edx, r12b
0x1400947e1  cmovnz  edx, edi
0x1400947e4  mov     [rsp+1E8h+var_194], edx
0x1400947e8  mov     rcx, [r13+0]; this
0x1400947ec  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400947f1  test    al, al
0x1400947f3  jz      short loc_14009481A
0x1400947f5  mov     rdx, rsi
0x1400947f8  mov     ecx, 4
0x1400947fd  call    cs:__imp_WdLogSingleEntry1
0x140094804  nop     dword ptr [rax+rax+00h]
0x140094809  mov     cs:WdLogGlobalForLineNumber, 653h
0x140094813  mov     dl, dil
0x140094816  mov     [rsp+1E8h+var_194], edx
0x14009481a  mov     eax, cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x140094820  mov     cl, 8
0x140094822  test    cl, al
0x140094824  jnz     short loc_140094839
0x140094826  mov     eax, [rsi+20h]
0x140094829  test    cl, al
0x14009482b  jz      short loc_140094839
0x14009482d  mov     r12d, 1
0x140094833  mov     [rsi+2Bh], r12b
0x140094837  jmp     short loc_14009483F
0x140094839  mov     r12d, 1
0x14009483f  test    dl, dl
0x140094841  jz      loc_140094910
0x140094847  mov     eax, [rsi+20h]
0x14009484a  test    cl, al
0x14009484c  jz      loc_140094910
0x140094852  cmp     [rsi+2Bh], dil
0x140094856  jnz     loc_140094910
0x14009485c  mov     rax, [rsp+1E8h+Size]
0x140094861  test    rax, rax
0x140094864  jz      loc_140094910
0x14009486a  mov     r8b, r12b; bool
0x14009486d  mov     rdx, [rax+8]; struct VIDMM_PROCESS *
0x140094871  lea     rcx, [rsp+1E8h+var_B8]; this
0x140094879  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x14009487e  mov     rcx, [rsi+0E8h]
0x140094885  mov     rax, [rcx]
0x140094888  mov     r8, [rsi+30h]
0x14009488c  mov     rax, [rax+28h]
0x140094890  mov     r9, [r14+10h]
0x140094894  mov     r8, [r8+10h]
0x140094898  mov     rdx, [rsi+0F0h]
0x14009489f  call    _guard_dispatch_icall
0x1400948a4  mov     dword ptr [rsp+1E8h+var_178], eax
0x1400948a8  lea     rcx, [rsp+1E8h+var_B8]; this
0x1400948b0  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400948b5  mov     edx, dword ptr [rsp+1E8h+var_178]
0x1400948b9  test    edx, edx
0x1400948bb  js      short loc_1400948CA
0x1400948bd  mov     rcx, [r13+0]
0x1400948c1  add     rcx, 0DD0h
0x1400948c8  jmp     short loc_1400948D9
0x1400948ca  mov     [rsi+2Bh], r12b
0x1400948ce  mov     rcx, [r13+0]
0x1400948d2  add     rcx, 0DE0h
0x1400948d9  mov     rax, [r14+10h]
0x1400948dd  lock add [rcx], r12d
0x1400948e1  lock add [rcx+8], rax
0x1400948e6  test    cs:byte_140086201, r12b
0x1400948ed  jz      short loc_14009490C
0x1400948ef  not     edx
0x1400948f1  shr     edx, 1Fh
0x1400948f4  mov     rax, [r14+10h]
0x1400948f8  shr     rax, 0Ch
0x1400948fc  mov     dword ptr [rsp+1E8h+var_1B8], edx
0x140094900  mov     dword ptr [rsp+1E8h+var_1C0], eax
0x140094904  mov     r9, rsi
0x140094907  call    McTemplateK0pqqt_EtwWriteTransfer
0x14009490c  mov     edx, [rsp+1E8h+var_194]
0x140094910  mov     al, [rsi+2Bh]
0x140094913  neg     al
0x140094915  sbb     cl, cl
0x140094917  and     cl, dl
0x140094919  mov     [rsp+1E8h+var_198], cl
0x14009491d  mov     edx, [rsi+20h]
0x140094920  test    dl, 8
0x140094923  jnz     loc_1400949AC
0x140094929  test    dword ptr [rsi+1Ch], 100h
0x140094930  jz      short loc_1400949AC
0x140094932  cmp     [rsi+24h], edi
0x140094935  jnz     short loc_1400949AC
0x140094937  test    dl, 2
0x14009493a  jnz     short loc_1400949AC
0x14009493c  cmp     [r14+0E8h], rdi
0x140094943  jnz     short loc_1400949AC
0x140094945  test    dword ptr [rbx], 400000h
0x14009494b  jnz     short loc_140094990
0x14009494d  mov     ecx, r12d
0x140094950  call    cs:__imp_WdLogSingleEntry0
0x140094957  nop     dword ptr [rax+rax+00h]
0x14009495c  mov     eax, 6ABh
0x140094961  mov     cs:WdLogGlobalForLineNumber, eax
0x140094967  mov     qword ptr [rsp+1E8h+var_1B0], rdi
0x14009496c  mov     [rsp+1E8h+var_1B8], rdi
0x140094971  mov     [rsp+1E8h+var_1C0], rdi
0x140094976  mov     [rsp+1E8h+Timeout], rax
0x14009497b  lea     r9, aFailedToResetA; "Failed to reset allocations early enoug"...
0x140094982  mov     edx, 40000h
0x140094987  call    DxgkLogInternalTriageEvent
0x14009498c  mov     cl, [rsp+1E8h+var_198]
0x140094990  test    cl, cl
0x140094992  jz      short loc_140094A08
0x140094994  xor     r9d, r9d
0x140094997  mov     r8, rsi
0x14009499a  mov     rdx, [rsp+1E8h+var_190]
0x14009499f  mov     rcx, [r13+0]
0x1400949a3  call    ?ResetBackingStore@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_RESET_BACKING_STORE_REASON@@@Z; VIDMM_GLOBAL::ResetBackingStore(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,VIDMM_RESET_BACKING_STORE_REASON)
0x1400949a8  mov     cl, [rsp+1E8h+var_198]
0x1400949ac  test    cl, cl
0x1400949ae  jz      short loc_140094A08
0x1400949b0  mov     rax, [rsp+1E8h+var_180]
0x1400949b5  mov     rax, [rax]
0x1400949b8  test    dword ptr [rax], 8000000h
0x1400949be  jz      short loc_140094A04
0x1400949c0  cmp     [rsi+24h], edi
0x1400949c3  jnz     short loc_140094A04
0x1400949c5  mov     eax, [rsi+20h]
0x1400949c8  mov     ecx, 2
0x1400949cd  test    cl, al
0x1400949cf  jnz     short loc_140094A04
0x1400949d1  mov     rdx, [r14+10h]; unsigned __int64
0x1400949d5  mov     rcx, [r13+0]; this
0x1400949d9  call    ?ChargePinnedBackingStore@VIDMM_GLOBAL@@QEAAJ_K@Z; VIDMM_GLOBAL::ChargePinnedBackingStore(unsigned __int64)
0x1400949de  test    eax, eax
0x1400949e0  js      short loc_140094A04
0x1400949e2  mov     rdx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400949e5  mov     rcx, r15; this
0x1400949e8  call    ?LockAllocationBackingStore@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::LockAllocationBackingStore(VIDMM_GLOBAL_ALLOC *)
0x1400949ed  test    eax, eax
0x1400949ef  js      short loc_1400949F7
0x1400949f1  or      dword ptr [rsi+20h], 2
0x1400949f5  jmp     short loc_140094A04
0x1400949f7  mov     rdx, [r14+10h]; unsigned __int64
0x1400949fb  mov     rcx, [r13+0]; this
0x1400949ff  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x140094a04  mov     cl, [rsp+1E8h+var_198]
0x140094a08  mov     eax, [rbx]
0x140094a0a  test    al, 4
0x140094a0c  jnz     loc_140094C2E
0x140094a12  cmp     [rsi+24h], edi
0x140094a15  jz      loc_140094C2E
0x140094a1b  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x140094a22  cmp     [rax], dil
0x140094a25  jz      short loc_140094A3D
0x140094a27  call    cs:__imp_WdLogNewEntry5_WdTrace
0x140094a2e  nop     dword ptr [rax+rax+00h]
0x140094a33  mov     cs:WdLogGlobalForLineNumber, 6E5h
0x140094a3d  xor     edx, edx; Val
0x140094a3f  lea     r8d, [rdx+50h]; Size
0x140094a43  lea     rcx, [rsp+1E8h+var_108]; void *
0x140094a4b  call    memset
0x140094a50  cmp     [rsp+1E8h+var_198], dil
0x140094a55  jz      loc_140094AEF
0x140094a5b  mov     rcx, [r15+10h]
0x140094a5f  mov     rax, [rcx]
0x140094a62  mov     rax, [rax+0D8h]
0x140094a69  mov     r8, r14
0x140094a6c  mov     rdx, [rsp+1E8h+var_190]
0x140094a71  call    _guard_dispatch_icall
0x140094a76  mov     rax, [rsp+1E8h+var_190]
0x140094a7b  mov     [rsp+1E8h+var_108.NewStartOffset], rax
0x140094a83  mov     [rsp+1E8h+var_D8], rdi
0x140094a8b  mov     [rsp+1E8h+var_C8], rdi
0x140094a93  mov     dword ptr [rsp+1E8h+var_108.NewSize+4], 2
0x140094a9e  mov     [rsp+1E8h+var_108.CurrentStartOffset], r13
0x140094aa6  mov     rax, [r14+70h]
0x140094aaa  mov     [rsp+1E8h+var_C0], rax
0x140094ab2  mov     dword ptr [rsp+1E8h+var_108.CurrentSize], edi
0x140094ab9  mov     rax, [r15+10h]
0x140094abd  mov     qword ptr [rsp+1E8h+var_108.PhysicalAdapterIndex], rax
0x140094ac5  mov     qword ptr [rsp+1E8h+var_108.VprIndex], r14
0x140094acd  mov     rax, [r14+10h]
0x140094ad1  mov     [rsp+1E8h+var_D0], rax
0x140094ad9  lea     rcx, ?VidMmRotateCopyCallback@@YAJPEAU_MDL@@0PEAX@Z; VidMmRotateCopyCallback(_MDL *,_MDL *,void *)
0x140094ae0  mov     [rsp+1E8h+var_180], rcx
0x140094ae5  mov     [rsp+1E8h+var_194], 3
0x140094aed  jmp     short loc_140094B01
0x140094aef  mov     [rsp+1E8h+var_180], rdi
0x140094af4  mov     eax, 3
0x140094af9  mov     [rsp+1E8h+var_194], eax
0x140094afd  mov     [rsp+1E8h+var_184], eax
0x140094b01  cmp     [rsp+1E8h+arg_28], dil
0x140094b09  jz      short loc_140094B11
0x140094b0b  cmp     [rsi+28h], dil
0x140094b0f  jnz     short loc_140094B16
0x140094b11  mov     [rsp+1E8h+var_194], r12d
0x140094b16  mov     byte ptr [rsp+1E8h+var_B8], dil
0x140094b1e  mov     rax, [rsp+1E8h+Size]
0x140094b23  mov     rcx, [rax+8]; this
0x140094b27  mov     [rsp+1E8h+var_80], rcx
0x140094b2f  lea     rdx, [rsp+1E8h+var_B0]; struct _KAPC_STATE *
0x140094b37  call    ?SafeAttach@VIDMM_PROCESS@@QEAAXPEAU_KAPC_STATE@@@Z; VIDMM_PROCESS::SafeAttach(_KAPC_STATE *)
0x140094b3c  mov     byte ptr [rsp+1E8h+var_B8], r12b
0x140094b44  mov     eax, [rsp+1E8h+var_194]
0x140094b48  mov     dword ptr [rsp+1E8h+var_1C0], eax
0x140094b4c  lea     rax, [rsp+1E8h+var_108]
0x140094b54  mov     [rsp+1E8h+Timeout], rax
0x140094b59  mov     r9, [rsp+1E8h+var_180]
0x140094b5e  mov     r8d, [rsp+1E8h+var_184]
0x140094b63  mov     rdx, r14
0x140094b66  mov     rcx, [r13+0]
0x140094b6a  call    ?VidMmRotateLegacyAllocation@@YAJPEAVVIDMM_GLOBAL@@PEAUVIDMM_PHYSICAL_ALLOC@@W4_MM_ROTATE_DIRECTION@@P6AJPEAU_MDL@@3PEAX@ZPEAUVIDMM_ROTATE_COPY_CONTEXT@@TVIDMM_ROTATE_FLAGS@@@Z; VidMmRotateLegacyAllocation(VIDMM_GLOBAL *,VIDMM_PHYSICAL_ALLOC *,_MM_ROTATE_DIRECTION,long (*)(_MDL *,_MDL *,void *),VIDMM_ROTATE_COPY_CONTEXT *,VIDMM_ROTATE_FLAGS)
0x140094b6f  movsxd  r13, eax
0x140094b72  cmp     byte ptr [rsp+1E8h+var_B8], dil
0x140094b7a  jz      short loc_140094B91
0x140094b7c  lea     rdx, [rsp+1E8h+var_B0]; struct _KAPC_STATE *
0x140094b84  call    ?SafeDetach@VIDMM_PROCESS@@QEAAXPEAU_KAPC_STATE@@@Z; VIDMM_PROCESS::SafeDetach(_KAPC_STATE *)
  ... truncated ...
```
