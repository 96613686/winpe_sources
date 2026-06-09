# VIDMM_MEMORY_SEGMENT::TransferToSystem(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_PHYSICAL_ALLOC_LEGACY *,bool,VIDMM_LOCAL_ALLOC *,bool)

- ea: `0x1400982d0`
- end: `0x1400990f1`
- name: `?TransferToSystem@VIDMM_MEMORY_SEGMENT@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_PHYSICAL_ALLOC_LEGACY@@_NPEAUVIDMM_LOCAL_ALLOC@@2@Z`
- size: `3617`
- prototype: `void __usercall(VIDMM_MEMORY_SEGMENT *__hidden this@<rcx>, struct VIDMM_PAGING_EXECUTION_CONTEXT *@<rdx>, struct VIDMM_PHYSICAL_ALLOC_LEGACY *@<r8>, bool@<r9b>, struct VIDMM_LOCAL_ALLOC *, bool)`
- caller_count: `2`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140098130`
- `0x1400d6850`

## callees

- `0x140003490`
- `0x140004268`
- `0x1400128c8`
- `0x14002e6c0`
- `0x14002eae8`
- `0x14002ed18`
- `0x140030bac`
- `0x140031434`
- `0x14003196c`
- `0x140034678`
- `0x14003e344`
- `0x140044fcc`
- `0x1400499f0`
- `0x14004ae88`
- `0x140058f50`
- `0x140059030`
- `0x140059080`
- `0x140059380`
- `0x140096800`
- `0x140097b0c`
- `0x1400982d0`
- `0x14009e200`
- `0x14009ecf4`
- `0x14009ed9c`
- `0x1400a1bf8`
- `0x1400a7410`
- `0x1400adf2c`
- `0x1400af314`
- `0x1400d3fcc`
- `0x1400d4120`
- `0x1400df0f4`
- `0x1400ef500`
- `0x140104610`
- `0x140106010`
- `0x140108318`
- `0x14010d9c0`
- `0x14010e858`
- `0x1401105c8`
- `0x140110ae0`
- `0x1401114dc`
- `0x14011ac38`
- `0x140122d88`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140098a29`
- `ntoskrnl!KeStackAttachProcess` at `0x140098a29`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140098c9f`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140098c9f`
- `ntoskrnl!PsIsProcessCommitRelinquished` at `0x14009842a`
- `ntoskrnl!PsIsProcessCommitRelinquished` at `0x14009842a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140098fe9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140098fe9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14009868e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14009888a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400989c9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14009868e`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14009888a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400989c9`
- `watchdog!WdLogSingleEntry5` at `0x140098860`
- `watchdog!WdLogSingleEntry5` at `0x14009907f`
- `watchdog!WdLogSingleEntry5` at `0x140098860`
- `watchdog!WdLogSingleEntry5` at `0x14009907f`
- `watchdog!WdLogSingleEntry0` at `0x1400985b7`
- `watchdog!WdLogSingleEntry0` at `0x140098bca`
- `watchdog!WdLogSingleEntry0` at `0x1400985b7`
- `watchdog!WdLogSingleEntry0` at `0x140098bca`
- `watchdog!WdLogSingleEntry1` at `0x140098464`
- `watchdog!WdLogSingleEntry1` at `0x140098464`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14009883c`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14009905d`
- `dxgkrnl!g_IsInternalRelease` at `0x140099051`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140098682`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14009887e`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400989bd`

## string_xrefs

- `0x140098c04`: `Exception occurred while accessing allocation (user mode page).\n`

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
  int v14; // edx
  int v15; // eax
  _DWORD *v16; // rcx
  int v17; // edx
  int v18; // edx
  __int64 v19; // rcx
  int v20; // r8d
  int v21; // edx
  unsigned __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // r8d
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v26; // rbx
  char v27; // dl
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  char v31; // al
  unsigned __int64 v32; // rdx
  __int64 v33; // r8
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  _QWORD *v36; // rcx
  unsigned int v37; // eax
  unsigned __int64 v38; // rbx
  unsigned __int64 LogicalAddress; // rax
  VIDMM_GLOBAL *v40; // r10
  void *v41; // rax
  VIDMM_GLOBAL *v42; // rdx
  char *v43; // rcx
  VIDMM_GLOBAL *v44; // rax
  VIDMM_GLOBAL *v45; // rcx
  __int64 (__fastcall *v46)(struct _MDL *, struct _MDL *, void *); // rcx
  __int64 v47; // rbx
  _QWORD *v48; // rax
  _QWORD *v49; // rdx
  __int64 *v50; // rax
  __int64 v51; // rcx
  unsigned __int64 v52; // r8
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // rdx
  __int64 v56; // r8
  int Timeout; // [rsp+20h] [rbp-1C8h]
  struct VIDMM_SEGMENT_BASE *v58; // [rsp+28h] [rbp-1C0h]
  char v59; // [rsp+50h] [rbp-198h]
  bool v60; // [rsp+51h] [rbp-197h] BYREF
  int v61; // [rsp+54h] [rbp-194h]
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v62; // [rsp+58h] [rbp-190h]
  char v63[4]; // [rsp+60h] [rbp-188h] BYREF
  unsigned int v64; // [rsp+64h] [rbp-184h]
  __int64 (__fastcall *v65)(struct _MDL *, struct _MDL *, void *); // [rsp+68h] [rbp-180h] BYREF
  size_t Size; // [rsp+70h] [rbp-178h]
  void *v67; // [rsp+78h] [rbp-170h] BYREF
  _DWORD *v68; // [rsp+80h] [rbp-168h]
  __int64 (__fastcall *v69)(VIDMM_SEGMENT *__hidden, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool *, void *); // [rsp+90h] [rbp-158h] BYREF
  int v70; // [rsp+98h] [rbp-150h]
  int v71; // [rsp+9Ch] [rbp-14Ch]
  _QWORD *v72; // [rsp+A0h] [rbp-148h] BYREF
  int v73; // [rsp+ACh] [rbp-13Ch]
  struct VIDMM_GLOBAL_ALLOC *v74; // [rsp+B0h] [rbp-138h]
  char *v75; // [rsp+B8h] [rbp-130h]
  VIDMM_GLOBAL **v76; // [rsp+C0h] [rbp-128h]
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v77; // [rsp+C8h] [rbp-120h]
  struct VIDMM_PHYSICAL_ALLOC_LEGACY *v78; // [rsp+D0h] [rbp-118h]
  _BYTE v79[80]; // [rsp+E0h] [rbp-108h] BYREF
  _QWORD v80[4]; // [rsp+130h] [rbp-B8h] BYREF
  __int128 v81; // [rsp+150h] [rbp-98h]
  _KAPC_STATE ApcState; // [rsp+170h] [rbp-78h] BYREF

  v62 = a2;
  v76 = this;
  v77 = a2;
  v78 = a3;
  Size = (size_t)a5;
  v74 = *(struct VIDMM_GLOBAL_ALLOC **)a3;
  v9 = v74;
  memset(&ApcState, 0, sizeof(ApcState));
  v60 = 0;
  v10 = this + 1;
  v75 = (char *)(this + 1);
  VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(this[1], v74, 0);
  if ( *((_QWORD *)*v10 + 4670) )
  {
    v11 = VIDMM_SEGMENT::DriverId((VIDMM_SEGMENT *)this);
    HIDWORD(v58) = HIDWORD(v74);
    Timeout = 4;
    VIDMM_GLOBAL::RecordPageMappingHistory(v12, v11);
  }
  v13 = (int *)((char *)v74 + 24);
  v68 = (_DWORD *)((char *)v74 + 24);
  v14 = *((_DWORD *)v74 + 6);
  if ( (v14 & 4) != 0 )
  {
    v64 = 2;
LABEL_8:
    a4 = 0;
    goto LABEL_9;
  }
  v15 = *((_DWORD *)v74 + 7);
  v64 = 2;
  if ( (v15 & 2) != 0 || (v14 & 0x40) != 0 )
    goto LABEL_8;
LABEL_9:
  v65 = (__int64 (__fastcall *)(struct _MDL *, struct _MDL *, void *))((char *)v74 + 392);
  v16 = (_DWORD *)*((_QWORD *)v74 + 49);
  if ( (*v16 & 0x20000) != 0 && ((_DWORD)this[8] & 0x40000) == 0 )
    *v13 = v14 | 0x10000;
  if ( (*v16 & 0x20000000) == 0
    && (unsigned __int8)PsIsProcessCommitRelinquished(*(_QWORD *)(*(_QWORD *)(Size + 8) + 16LL)) )
  {
    *v13 |= 0x10000u;
  }
  v17 = a4;
  if ( (*v13 & 0x10000) != 0 )
    v17 = 0;
  v61 = v17;
  if ( VIDMM_GLOBAL::IsTdrPending(*v10) )
  {
    WdLogSingleEntry1(4, v9);
    WdLogGlobalForLineNumber = 1635;
    LOBYTE(v18) = 0;
    v61 = v18;
  }
  if ( (VIDMM_GLOBAL::_Config & 8) == 0 && (*((_DWORD *)v9 + 8) & 8) != 0 )
    *((_BYTE *)v9 + 43) = 1;
  if ( (_BYTE)v18 && (*((_DWORD *)v9 + 8) & 8) != 0 && !*((_BYTE *)v9 + 43) && Size )
  {
    VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
      (VIDMM_PROCESS_AUTOATTACH *)v80,
      *(struct VIDMM_PROCESS **)(Size + 8),
      1);
    LODWORD(v67) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v9 + 29) + 40LL))(
                     *((_QWORD *)v9 + 29),
                     *((_QWORD *)v9 + 30),
                     *(_QWORD *)(*((_QWORD *)v9 + 6) + 16LL),
                     *((_QWORD *)a3 + 2));
    VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v80);
    v21 = (int)v67;
    if ( (int)v67 < 0 )
    {
      *((_BYTE *)v9 + 43) = 1;
      v19 = (__int64)*v10 + 3552;
    }
    else
    {
      v19 = (__int64)*v10 + 3536;
    }
    v22 = *((_QWORD *)a3 + 2);
    _InterlockedAdd((volatile signed __int32 *)v19, 1u);
    _InterlockedAdd64((volatile signed __int64 *)(v19 + 8), v22);
    if ( (byte_140087201 & 1) != 0 )
      McTemplateK0pqqt_EtwWriteTransfer(v19, v21 >= 0, v20, (_DWORD)v9, Timeout, *((_QWORD *)a3 + 2) >> 12, v21 >= 0);
    LOBYTE(v18) = v61;
  }
  LOBYTE(v19) = *((_BYTE *)v9 + 43) != 0 ? v18 : 0;
  v59 = v19;
  v23 = *((unsigned int *)v9 + 8);
  if ( (v23 & 8) != 0
    || (*((_DWORD *)v9 + 7) & 0x100) == 0
    || *((_DWORD *)v9 + 9)
    || (v23 & 2) != 0
    || *((_QWORD *)a3 + 29) )
  {
    goto LABEL_41;
  }
  if ( (*v13 & 0x400000) == 0 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1723;
    DxgkLogInternalTriageEvent(
      v24,
      0x40000,
      v25,
      (unsigned int)L"Failed to reset allocations early enough.",
      1723,
      0,
      0,
      0);
    LOBYTE(v19) = v59;
  }
  if ( (_BYTE)v19 )
  {
    VIDMM_GLOBAL::ResetBackingStore(*v10, v62, v9, 0);
    LOBYTE(v19) = v59;
LABEL_41:
    if ( (_BYTE)v19 )
    {
      if ( (**(_DWORD **)v65 & 0x8000000) != 0 && !*((_DWORD *)v9 + 9) )
      {
        v19 = 2;
        if ( (*((_DWORD *)v9 + 8) & 2) == 0
          && (int)VIDMM_GLOBAL::ChargePinnedBackingStore(*v10, *((_QWORD *)a3 + 2)) >= 0 )
        {
          if ( (int)VIDMM_SEGMENT::LockAllocationBackingStore((VIDMM_SEGMENT *)this, v9) < 0 )
            VIDMM_GLOBAL::ReturnPinnedBackingStore(*v10, *((_QWORD *)a3 + 2));
          else
            *((_DWORD *)v9 + 8) |= 2u;
        }
      }
      LOBYTE(v19) = v59;
    }
  }
  if ( (*v13 & 4) == 0 && *((_DWORD *)v9 + 9) )
  {
    if ( g_IsInternalReleaseOrDbg )
    {
      WdLogNewEntry5_WdTrace(v19, v23);
      WdLogGlobalForLineNumber = 1781;
    }
    memset(v79, 0, sizeof(v79));
    if ( v59 )
    {
      (*(void (__fastcall **)(VIDMM_GLOBAL *, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *))(*(_QWORD *)this[2] + 216LL))(
        this[2],
        v62,
        a3);
      *(_QWORD *)&v79[32] = v62;
      *(_QWORD *)&v79[48] = 0;
      *(_QWORD *)&v79[64] = 0;
      *(_DWORD *)&v79[44] = 2;
      *(_QWORD *)&v79[16] = v10;
      *(_QWORD *)&v79[72] = *((_QWORD *)a3 + 14);
      *(_DWORD *)&v79[24] = 0;
      *(_QWORD *)v79 = this[2];
      *(_QWORD *)&v79[8] = a3;
      *(_QWORD *)&v79[56] = *((_QWORD *)a3 + 2);
      v65 = VidMmRotateCopyCallback;
      v61 = 3;
    }
    else
    {
      v65 = 0;
      v61 = 3;
      v64 = 3;
    }
    if ( !a6 || !*((_BYTE *)v9 + 40) )
      v61 = 1;
    VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
      (VIDMM_PROCESS_AUTOATTACH *)v80,
      *(struct VIDMM_PROCESS **)(Size + 8),
      1);
    LODWORD(v58) = v61;
    v10 = (VIDMM_GLOBAL **)(int)VidMmRotateLegacyAllocation(*v10, a3, v64, v65, v79, v58);
    VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v80);
    if ( (_DWORD)v10 == -1073741558 )
    {
      *v13 |= 0x10000u;
LABEL_62:
      VidMmDecrementRotateCount(v9, 1u);
LABEL_63:
      v26 = v62;
      goto LABEL_64;
    }
    if ( (int)v10 >= 0 )
      goto LABEL_62;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 4, v64, v10, 0);
    WdLogGlobalForLineNumber = 227;
  }
  if ( (_BYTE)v19 )
  {
    if ( (int)VIDMM_MEMORY_SEGMENT::TransferMemory(
                (VIDMM_MEMORY_SEGMENT *)this,
                v62,
                a3,
                DXGK_MEMORY_TRANSFER_LOCAL_TO_SYSTEM,
                *((_QWORD *)a3 + 18),
                &v60,
                0) < 0 )
    {
      if ( g_IsInternalReleaseOrDbg )
      {
        WdLogNewEntry5_WdTrace(v29, v28);
        WdLogGlobalForLineNumber = 1908;
      }
      if ( (byte_140087201 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v29, &EventPerformanceWarning, v30, 2);
      v64 = 0;
      if ( (**(_DWORD **)v65 & 8) == 0 && Size )
      {
        KeStackAttachProcess(*(PRKPROCESS *)(*(_QWORD *)(Size + 8) + 16LL), &ApcState);
        v64 = 1;
      }
      v31 = Use64KbPagesForTransfer(a3, *((_QWORD *)a3 + 17));
      v32 = *((_QWORD *)a3 + 2);
      v33 = v31 != 0 ? 0x10000LL : 4096LL;
      Size = v33;
      v34 = v32 >> 12;
      v35 = v32 >> 16;
      if ( !v31 )
        v35 = (unsigned int)v34;
      v69 = (__int64 (__fastcall *)(VIDMM_SEGMENT *__hidden, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct VIDMM_PHYSICAL_ALLOC_LEGACY *, bool *, void *))v35;
      v36 = (_QWORD *)*((_QWORD *)a3 + 18);
      v72 = v36;
      v37 = 0;
      while ( 1 )
      {
        v61 = v37;
        if ( v37 >= (unsigned int)v35 )
          break;
        v38 = v33 * v37;
        v80[1] = 0;
        v81 = 0;
        memset(v79, 0, 48);
        v80[0] = v36;
        v80[2] = v10;
        v80[3] = v38;
        LogicalAddress = SysMmGetLogicalAddress(*((void *const *)*v10 + 5180));
        v40 = *v10;
        *(_QWORD *)&v79[32] = *((_QWORD *)*v10 + 5179);
        *(_QWORD *)&v79[40] = *(_QWORD *)&v79[32] + 48LL;
        *(_QWORD *)&v79[8] = LogicalAddress;
        VIDMM_GLOBAL::MemoryTransfer(
          v40,
          v62,
          v9,
          Size,
          v38,
          (struct VIDMM_TRANSFER_PARAMETER *)v80,
          (struct VIDMM_TRANSFER_PARAMETER *)v79,
          0);
        VIDMM_GLOBAL::WaitForAllPagingEngines(*v10, v62, v9);
        v67 = 0;
        v41 = VidMmMapViewOfAllocation(v9, v38, Size, &v67);
        if ( v41 )
        {
          memmove(v41, *((const void **)*v10 + 5178), Size);
          VidMmUnmapViewOfAllocation(v9, v67);
        }
        else
        {
          *v68 |= 0x10000u;
        }
        v37 = v61 + 1;
        LODWORD(v35) = (_DWORD)v69;
        v33 = Size;
        v36 = v72;
      }
      if ( v64 )
        KeUnstackDetachProcess(&ApcState);
    }
  }
  else
  {
    if ( g_IsInternalReleaseOrDbg )
    {
      WdLogNewEntry5_WdTrace(v19, v23);
      WdLogGlobalForLineNumber = 1860;
    }
    if ( (*v13 & 4) == 0 )
      VIDMM_GLOBAL::DiscardAllocation(
        *v10,
        v62,
        v9,
        0,
        *((_QWORD *)a3 + 2),
        (struct VIDMM_SEGMENT_BASE *)((*((_QWORD *)a3 + 17) + 8LL)
                                    & ((unsigned __int128)-(__int128)*((unsigned __int64 *)a3 + 17) >> 64)),
        *((_QWORD *)a3 + 18));
  }
  if ( (**(_DWORD **)v65 & 0x20000) == 0 || !*((_QWORD *)a3 + 16) )
    goto LABEL_63;
  memset(v79, 0, 48);
  *(_DWORD *)v79 = *((unsigned __int16 *)this + 34);
  *(_DWORD *)&v79[4] = VIDMM_SEGMENT::DriverId((VIDMM_SEGMENT *)this);
  if ( *((_DWORD *)this + 105) )
  {
    v65 = 0;
    v63[0] = 0;
    v69 = VIDMM_SEGMENT::CheckLowestAddress;
    v70 = 0;
    v71 = v73;
    if ( (unsigned int)VIDMM_LINEAR_POOL::DirectedIterateAllocatedBlocksInRange(
                         (unsigned int)this[32],
                         (_DWORD)v62,
                         (unsigned int)this[53],
                         (unsigned int)this[54],
                         0,
                         (__int64)&v69,
                         (__int64)this,
                         (__int64)&v65,
                         (__int64)&v72,
                         (__int64)v63) != -1073741823
      || v65 != *((__int64 (__fastcall **)(struct _MDL *, struct _MDL *, void *))a3 + 18) )
    {
      goto LABEL_105;
    }
    v42 = this[54];
    v43 = (char *)*((_QWORD *)a3 + 16);
    v44 = (VIDMM_GLOBAL *)(*(_QWORD *)v43 + *((_QWORD *)v43 + 1));
    if ( v44 >= v42 )
    {
LABEL_102:
      v44 = this[54];
    }
    else
    {
      while ( 1 )
      {
        v45 = (VIDMM_GLOBAL *)*((_QWORD *)v43 + 5);
        if ( v45 == (VIDMM_GLOBAL *)((char *)this[32] + 80) )
          break;
        v43 = (char *)v45 - 40;
        if ( v43[56] != 2 )
          break;
        v44 = (VIDMM_GLOBAL *)(*(_QWORD *)v43 + *((_QWORD *)v43 + 1));
        if ( v44 >= v42 )
          goto LABEL_102;
      }
    }
    v46 = (__int64 (__fastcall *)(struct _MDL *, struct _MDL *, void *))((unsigned __int64)v44
                                                                       & ~(unsigned __int64)this[51]);
    v65 = v46;
    if ( (VIDMM_GLOBAL *)v46 > this[53] )
    {
      *(_QWORD *)&v79[16] = this[53];
      *(_QWORD *)&v79[24] = this[55];
      *(_QWORD *)&v79[32] = v46;
      *(_QWORD *)&v79[40] = v42 - (VIDMM_GLOBAL *)v46;
      this[55] = (VIDMM_GLOBAL *)(v42 - (VIDMM_GLOBAL *)v46);
      this[53] = (VIDMM_GLOBAL *)v46;
      v27 = 1;
    }
    else
    {
LABEL_105:
      v27 = 0;
    }
  }
  else
  {
    v27 = 1;
    *(_QWORD *)&v79[16] = *((_QWORD *)a3 + 18);
    *(_QWORD *)&v79[24] = ~(unsigned __int64)this[51] & ((unsigned __int64)this[51] + *((_QWORD *)a3 + 2));
  }
  if ( !v27 )
    goto LABEL_63;
  v47 = operator new(104, 825583958, 256);
  v48 = (_QWORD *)operator new(56, 943024470, 256);
  v49 = v48;
  v72 = v48;
  if ( v47 )
  {
    if ( v48 )
    {
      *(_QWORD *)(v47 + 16) = DeferredSetVprCallback;
      *(_QWORD *)(v47 + 32) = DeferredSetVprCompletionCallback;
      *(_OWORD *)(v47 + 56) = *(_OWORD *)v79;
      *(_OWORD *)(v47 + 72) = *(_OWORD *)&v79[16];
      *(_OWORD *)(v47 + 88) = *(_OWORD *)&v79[32];
      *(_QWORD *)(v47 + 40) = *v10;
      *(_QWORD *)(v47 + 48) = v48;
      v48[2] = this;
      v48[3] = *((_QWORD *)a3 + 16);
      v48[4] = *((_QWORD *)a3 + 2);
      if ( g_Feature_ResourcePoolManagement )
      {
        v50 = (__int64 *)*((_QWORD *)v9 + 44);
        v51 = *v50;
        v49[6] = *v50;
        _InterlockedAdd((volatile signed __int32 *)(v51 + 24), 1u);
      }
      else
      {
        v48[5] = **((_QWORD **)v9 + 43);
      }
      *(_QWORD *)(v47 + 24) = v47;
      (*(void (__fastcall **)(VIDMM_GLOBAL *, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(*(_QWORD *)this[2] + 200LL))(
        this[2],
        v62);
      VIDMM_GLOBAL::FlushPagingBuffer(*v10, v62, 0);
      VIDMM_LINEAR_POOL::MarkBlockAsAllocatedScrubPending(
        this[32],
        *((void **)a3 + 16),
        *(unsigned __int64 *)&v79[16],
        *(unsigned __int64 *)&v79[32]);
      DXG_DEFERRED_WORK_QUEUE::QueueWorkItem(
        (VIDMM_GLOBAL *)((char *)*v10 + 37440),
        (struct DXG_DEFERRED_QUEUE_WORK_ITEM *)v47);
      *((_QWORD *)a3 + 16) = 0;
      if ( *((_DWORD *)v9 + 18) != 1 )
      {
        v52 = *((_QWORD *)a3 + 2);
        if ( g_Feature_ResourcePoolManagement )
          VIDMM_SEGMENT::DecrementBytesCommitted(
            (VIDMM_SEGMENT *)this,
            **((struct VIDMM_RESOURCE_POOL ***)v9 + 44),
            v52);
        else
          VIDMM_SEGMENT::DecrementBytesCommitted((VIDMM_SEGMENT *)this, **((struct VIDMM_PARTITION ***)v9 + 43), v52);
        --*((_DWORD *)this + 88);
      }
      goto LABEL_63;
    }
    operator delete((void *)v47);
    v49 = v72;
  }
  if ( v49 )
    operator delete(v49);
  if ( (unsigned int)DXG_DEFERRED_WORK_QUEUE::GetNumWorkItems((VIDMM_GLOBAL *)((char *)*v10 + 37440)) )
  {
    if ( (byte_140087201 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(v53, &EventPerformanceWarning, v54, 24);
    KeWaitForSingleObject((char *)*v10 + 37488, Executive, 0, 0, 0);
  }
  v26 = v62;
  (*(void (__fastcall **)(VIDMM_GLOBAL *, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(*(_QWORD *)this[2] + 200LL))(
    this[2],
    v62);
  VIDMM_GLOBAL::WaitForAllPagingEnginesIdle(*v10, v26, *((unsigned __int16 *)this + 34));
  VIDMM_SEGMENT::CheckFreeVPRReserve((VIDMM_SEGMENT *)this, (struct _DXGKARG_SETVIDEOPROTECTEDREGION *)v79);
  if ( (int)ADAPTER_RENDER::DdiSetVideoProtectedRegion(
              *(ADAPTER_RENDER **)(*((_QWORD *)*v10 + 3) + 3256LL),
              (const struct _DXGKARG_SETVIDEOPROTECTEDREGION *)v79) < 0
    && g_IsInternalRelease )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 9, 0, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  if ( (byte_140087201 & 1) != 0 )
    McTemplateK0qqqxxp_EtwWriteTransfer(
      *((_QWORD *)*v10 + 3),
      v55,
      v56,
      *(int *)v79,
      v79[4],
      v79[8],
      v79[32],
      v79[40],
      *((_QWORD *)*v10 + 3));
LABEL_64:
  *v68 &= ~0x400000u;
  if ( v60 )
    VidMmReleaseTemporaryResourcesForLegacyAllocation(this[2], v26, a3, 0);
}

```

## disassembly

```asm
0x1400982d0  mov     r11, rsp
0x1400982d3  push    rbx
0x1400982d4  push    rsi
0x1400982d5  push    rdi
0x1400982d6  push    r12
0x1400982d8  push    r13
0x1400982da  push    r14
0x1400982dc  push    r15
0x1400982de  sub     rsp, 1B0h
0x1400982e5  mov     rax, cs:__security_cookie
0x1400982ec  xor     rax, rsp
0x1400982ef  mov     [rsp+1E8h+var_48], rax
0x1400982f7  mov     r12b, r9b
0x1400982fa  mov     r15, r8
0x1400982fd  mov     [rsp+1E8h+var_190], rdx
0x140098302  mov     r14, rcx
0x140098305  mov     [rsp+1E8h+var_128], rcx
0x14009830d  mov     [rsp+1E8h+var_120], rdx
0x140098315  mov     [rsp+1E8h+var_118], r8
0x14009831d  mov     rax, [rsp+1E8h+arg_20]
0x140098325  mov     [rsp+1E8h+Size], rax
0x14009832a  mov     rsi, [r8]
0x14009832d  mov     [rsp+1E8h+var_138], rsi
0x140098335  xorps   xmm0, xmm0
0x140098338  movups  xmmword ptr [r11-78h], xmm0
0x14009833d  movups  xmmword ptr [r11-68h], xmm0
0x140098342  movups  xmmword ptr [r11-58h], xmm0
0x140098347  xor     edi, edi
0x140098349  mov     [rsp+1E8h+var_197], dil
0x14009834e  lea     r13, [rcx+8]
0x140098352  mov     [rsp+1E8h+var_130], r13
0x14009835a  xor     r8d, r8d; unsigned __int8
0x14009835d  mov     rdx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x140098360  mov     rcx, [r13+0]; this
0x140098364  call    ?RecordVaPagingHistoryEvictCommitAlloc@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@E@Z; VIDMM_GLOBAL::RecordVaPagingHistoryEvictCommitAlloc(VIDMM_GLOBAL_ALLOC *,uchar)
0x140098369  mov     r10, [r13+0]
0x14009836d  cmp     [r10+91F0h], rdi
0x140098374  jz      short loc_1400983B9
0x140098376  mov     rax, [r15+10h]
0x14009837a  test    rax, 0FFFh
0x140098380  mov     r9d, edi
0x140098383  setnz   r9b
0x140098387  shr     rax, 0Ch
0x14009838b  add     r9, rax
0x14009838e  mov     r8, [r15+90h]
0x140098395  shr     r8, 0Ch
0x140098399  mov     rcx, r14; this
0x14009839c  call    ?DriverId@VIDMM_SEGMENT@@QEBAGXZ; VIDMM_SEGMENT::DriverId(void)
0x1400983a1  movzx   edx, ax
0x1400983a4  mov     [rsp+1E8h+var_1C0], rsi
0x1400983a9  mov     dword ptr [rsp+1E8h+Timeout], 4
0x1400983b1  mov     rcx, r10
0x1400983b4  call    ?RecordPageMappingHistory@VIDMM_GLOBAL@@QEAAXI_K0W4VIDMM_PAGE_HISTORY_TYPE@@0@Z; VIDMM_GLOBAL::RecordPageMappingHistory(uint,unsigned __int64,unsigned __int64,VIDMM_PAGE_HISTORY_TYPE,unsigned __int64)
0x1400983b9  lea     rbx, [rsi+18h]
0x1400983bd  mov     [rsp+1E8h+var_168], rbx
0x1400983c5  mov     edx, [rbx]
0x1400983c7  test    dl, 4
0x1400983ca  jnz     short loc_1400983E3
0x1400983cc  mov     eax, [rsi+1Ch]
0x1400983cf  mov     ecx, 2
0x1400983d4  mov     [rsp+1E8h+var_184], ecx
0x1400983d8  test    cl, al
0x1400983da  jnz     short loc_1400983EB
0x1400983dc  test    dl, 40h
0x1400983df  jz      short loc_1400983EE
0x1400983e1  jmp     short loc_1400983EB
0x1400983e3  mov     [rsp+1E8h+var_184], 2
0x1400983eb  mov     r12b, dil
0x1400983ee  lea     rax, [rsi+188h]
0x1400983f5  mov     [rsp+1E8h+var_180], rax
0x1400983fa  mov     rcx, [rax]
0x1400983fd  test    dword ptr [rcx], 20000h
0x140098403  jz      short loc_140098415
0x140098405  test    dword ptr [r14+40h], 40000h
0x14009840d  jnz     short loc_140098415
0x14009840f  bts     edx, 10h
0x140098413  mov     [rbx], edx
0x140098415  test    dword ptr [rcx], 20000000h
0x14009841b  jnz     short loc_14009843E
0x14009841d  mov     rcx, [rsp+1E8h+Size]
0x140098422  mov     rcx, [rcx+8]
0x140098426  mov     rcx, [rcx+10h]
0x14009842a  call    cs:__imp_PsIsProcessCommitRelinquished
0x140098431  nop     dword ptr [rax+rax+00h]
0x140098436  test    al, al
0x140098438  jz      short loc_14009843E
0x14009843a  bts     dword ptr [rbx], 10h
0x14009843e  test    dword ptr [rbx], 10000h
0x140098444  movzx   edx, r12b
0x140098448  cmovnz  edx, edi
0x14009844b  mov     [rsp+1E8h+var_194], edx
0x14009844f  mov     rcx, [r13+0]; this
0x140098453  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x140098458  test    al, al
0x14009845a  jz      short loc_140098481
0x14009845c  mov     rdx, rsi
0x14009845f  mov     ecx, 4
0x140098464  call    cs:__imp_WdLogSingleEntry1
0x14009846b  nop     dword ptr [rax+rax+00h]
0x140098470  mov     cs:WdLogGlobalForLineNumber, 663h
0x14009847a  mov     dl, dil
0x14009847d  mov     [rsp+1E8h+var_194], edx
0x140098481  mov     eax, cs:?_Config@VIDMM_GLOBAL@@2U_VIDMM_CONFIGURATION@@A; _VIDMM_CONFIGURATION VIDMM_GLOBAL::_Config
0x140098487  mov     cl, 8
0x140098489  test    cl, al
0x14009848b  jnz     short loc_1400984A0
0x14009848d  mov     eax, [rsi+20h]
0x140098490  test    cl, al
0x140098492  jz      short loc_1400984A0
0x140098494  mov     r12d, 1
0x14009849a  mov     [rsi+2Bh], r12b
0x14009849e  jmp     short loc_1400984A6
0x1400984a0  mov     r12d, 1
0x1400984a6  test    dl, dl
0x1400984a8  jz      loc_140098577
0x1400984ae  mov     eax, [rsi+20h]
0x1400984b1  test    cl, al
0x1400984b3  jz      loc_140098577
0x1400984b9  cmp     [rsi+2Bh], dil
0x1400984bd  jnz     loc_140098577
0x1400984c3  mov     rax, [rsp+1E8h+Size]
0x1400984c8  test    rax, rax
0x1400984cb  jz      loc_140098577
0x1400984d1  mov     r8b, r12b; bool
0x1400984d4  mov     rdx, [rax+8]; struct VIDMM_PROCESS *
0x1400984d8  lea     rcx, [rsp+1E8h+var_B8]; this
0x1400984e0  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400984e5  mov     rcx, [rsi+0E8h]
0x1400984ec  mov     rax, [rcx]
0x1400984ef  mov     r8, [rsi+30h]
0x1400984f3  mov     rax, [rax+28h]
0x1400984f7  mov     r9, [r15+10h]
0x1400984fb  mov     r8, [r8+10h]
0x1400984ff  mov     rdx, [rsi+0F0h]
0x140098506  call    _guard_dispatch_icall
0x14009850b  mov     dword ptr [rsp+1E8h+var_170], eax
0x14009850f  lea     rcx, [rsp+1E8h+var_B8]; this
0x140098517  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x14009851c  mov     edx, dword ptr [rsp+1E8h+var_170]
0x140098520  test    edx, edx
0x140098522  js      short loc_140098531
0x140098524  mov     rcx, [r13+0]
0x140098528  add     rcx, 0DD0h
0x14009852f  jmp     short loc_140098540
0x140098531  mov     [rsi+2Bh], r12b
0x140098535  mov     rcx, [r13+0]
0x140098539  add     rcx, 0DE0h
0x140098540  mov     rax, [r15+10h]
0x140098544  lock add [rcx], r12d
0x140098548  lock add [rcx+8], rax
0x14009854d  test    cs:byte_140087201, r12b
0x140098554  jz      short loc_140098573
0x140098556  not     edx
0x140098558  shr     edx, 1Fh
0x14009855b  mov     rax, [r15+10h]
0x14009855f  shr     rax, 0Ch
0x140098563  mov     dword ptr [rsp+1E8h+var_1B8], edx
0x140098567  mov     dword ptr [rsp+1E8h+var_1C0], eax
0x14009856b  mov     r9, rsi
0x14009856e  call    McTemplateK0pqqt_EtwWriteTransfer
0x140098573  mov     edx, [rsp+1E8h+var_194]
0x140098577  mov     al, [rsi+2Bh]
0x14009857a  neg     al
0x14009857c  sbb     cl, cl
0x14009857e  and     cl, dl
0x140098580  mov     [rsp+1E8h+var_198], cl
0x140098584  mov     edx, [rsi+20h]
0x140098587  test    dl, 8
0x14009858a  jnz     loc_140098613
0x140098590  test    dword ptr [rsi+1Ch], 100h
0x140098597  jz      short loc_140098613
0x140098599  cmp     [rsi+24h], edi
0x14009859c  jnz     short loc_140098613
0x14009859e  test    dl, 2
0x1400985a1  jnz     short loc_140098613
0x1400985a3  cmp     [r15+0E8h], rdi
0x1400985aa  jnz     short loc_140098613
0x1400985ac  test    dword ptr [rbx], 400000h
0x1400985b2  jnz     short loc_1400985F7
0x1400985b4  mov     ecx, r12d
0x1400985b7  call    cs:__imp_WdLogSingleEntry0
0x1400985be  nop     dword ptr [rax+rax+00h]
0x1400985c3  mov     eax, 6BBh
0x1400985c8  mov     cs:WdLogGlobalForLineNumber, eax
0x1400985ce  mov     qword ptr [rsp+1E8h+var_1B0], rdi
0x1400985d3  mov     [rsp+1E8h+var_1B8], rdi
0x1400985d8  mov     [rsp+1E8h+var_1C0], rdi
0x1400985dd  mov     [rsp+1E8h+Timeout], rax
0x1400985e2  lea     r9, aFailedToResetA; "Failed to reset allocations early enoug"...
0x1400985e9  mov     edx, 40000h
0x1400985ee  call    DxgkLogInternalTriageEvent
0x1400985f3  mov     cl, [rsp+1E8h+var_198]
0x1400985f7  test    cl, cl
0x1400985f9  jz      short loc_14009866F
0x1400985fb  xor     r9d, r9d
0x1400985fe  mov     r8, rsi
0x140098601  mov     rdx, [rsp+1E8h+var_190]
0x140098606  mov     rcx, [r13+0]
0x14009860a  call    ?ResetBackingStore@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@W4VIDMM_RESET_BACKING_STORE_REASON@@@Z; VIDMM_GLOBAL::ResetBackingStore(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *,VIDMM_RESET_BACKING_STORE_REASON)
0x14009860f  mov     cl, [rsp+1E8h+var_198]
0x140098613  test    cl, cl
0x140098615  jz      short loc_14009866F
0x140098617  mov     rax, [rsp+1E8h+var_180]
0x14009861c  mov     rax, [rax]
0x14009861f  test    dword ptr [rax], 8000000h
0x140098625  jz      short loc_14009866B
0x140098627  cmp     [rsi+24h], edi
0x14009862a  jnz     short loc_14009866B
0x14009862c  mov     eax, [rsi+20h]
0x14009862f  mov     ecx, 2
0x140098634  test    cl, al
0x140098636  jnz     short loc_14009866B
0x140098638  mov     rdx, [r15+10h]; unsigned __int64
0x14009863c  mov     rcx, [r13+0]; this
0x140098640  call    ?ChargePinnedBackingStore@VIDMM_GLOBAL@@QEAAJ_K@Z; VIDMM_GLOBAL::ChargePinnedBackingStore(unsigned __int64)
0x140098645  test    eax, eax
0x140098647  js      short loc_14009866B
0x140098649  mov     rdx, rsi; struct VIDMM_GLOBAL_ALLOC *
0x14009864c  mov     rcx, r14; this
0x14009864f  call    ?LockAllocationBackingStore@VIDMM_SEGMENT@@QEAAJPEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_SEGMENT::LockAllocationBackingStore(VIDMM_GLOBAL_ALLOC *)
0x140098654  test    eax, eax
0x140098656  js      short loc_14009865E
0x140098658  or      dword ptr [rsi+20h], 2
0x14009865c  jmp     short loc_14009866B
0x14009865e  mov     rdx, [r15+10h]; unsigned __int64
0x140098662  mov     rcx, [r13+0]; this
0x140098666  call    ?ReturnPinnedBackingStore@VIDMM_GLOBAL@@QEAAX_K@Z; VIDMM_GLOBAL::ReturnPinnedBackingStore(unsigned __int64)
0x14009866b  mov     cl, [rsp+1E8h+var_198]
0x14009866f  mov     eax, [rbx]
0x140098671  test    al, 4
0x140098673  jnz     loc_140098876
0x140098679  cmp     [rsi+24h], edi
0x14009867c  jz      loc_140098876
0x140098682  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x140098689  cmp     [rax], dil
0x14009868c  jz      short loc_1400986A4
0x14009868e  call    cs:__imp_WdLogNewEntry5_WdTrace
0x140098695  nop     dword ptr [rax+rax+00h]
0x14009869a  mov     cs:WdLogGlobalForLineNumber, 6F5h
0x1400986a4  xor     edx, edx; Val
0x1400986a6  lea     r8d, [rdx+50h]; Size
0x1400986aa  lea     rcx, [rsp+1E8h+var_108]; void *
0x1400986b2  call    memset
0x1400986b7  cmp     [rsp+1E8h+var_198], dil
0x1400986bc  jz      loc_140098756
0x1400986c2  mov     rcx, [r14+10h]
0x1400986c6  mov     rax, [rcx]
0x1400986c9  mov     rax, [rax+0D8h]
0x1400986d0  mov     r8, r15
0x1400986d3  mov     rdx, [rsp+1E8h+var_190]
0x1400986d8  call    _guard_dispatch_icall
0x1400986dd  mov     rax, [rsp+1E8h+var_190]
0x1400986e2  mov     [rsp+1E8h+var_108.NewStartOffset], rax
0x1400986ea  mov     [rsp+1E8h+var_D8], rdi
0x1400986f2  mov     [rsp+1E8h+var_C8], rdi
0x1400986fa  mov     dword ptr [rsp+1E8h+var_108.NewSize+4], 2
0x140098705  mov     [rsp+1E8h+var_108.CurrentStartOffset], r13
0x14009870d  mov     rax, [r15+70h]
0x140098711  mov     [rsp+1E8h+var_C0], rax
0x140098719  mov     dword ptr [rsp+1E8h+var_108.CurrentSize], edi
0x140098720  mov     rax, [r14+10h]
0x140098724  mov     qword ptr [rsp+1E8h+var_108.PhysicalAdapterIndex], rax
0x14009872c  mov     qword ptr [rsp+1E8h+var_108.VprIndex], r15
0x140098734  mov     rax, [r15+10h]
0x140098738  mov     [rsp+1E8h+var_D0], rax
0x140098740  lea     rcx, ?VidMmRotateCopyCallback@@YAJPEAU_MDL@@0PEAX@Z; VidMmRotateCopyCallback(_MDL *,_MDL *,void *)
0x140098747  mov     [rsp+1E8h+var_180], rcx
0x14009874c  mov     [rsp+1E8h+var_194], 3
0x140098754  jmp     short loc_140098768
0x140098756  mov     [rsp+1E8h+var_180], rdi
0x14009875b  mov     eax, 3
0x140098760  mov     [rsp+1E8h+var_194], eax
0x140098764  mov     [rsp+1E8h+var_184], eax
0x140098768  cmp     [rsp+1E8h+arg_28], dil
0x140098770  jz      short loc_140098778
0x140098772  cmp     [rsi+28h], dil
0x140098776  jnz     short loc_14009877D
0x140098778  mov     [rsp+1E8h+var_194], r12d
0x14009877d  mov     r8b, r12b; bool
0x140098780  mov     rax, [rsp+1E8h+Size]
0x140098785  mov     rdx, [rax+8]; struct VIDMM_PROCESS *
0x140098789  lea     rcx, [rsp+1E8h+var_B8]; this
0x140098791  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x140098796  mov     eax, [rsp+1E8h+var_194]
0x14009879a  mov     dword ptr [rsp+1E8h+var_1C0], eax
0x14009879e  lea     rax, [rsp+1E8h+var_108]
0x1400987a6  mov     [rsp+1E8h+Timeout], rax
0x1400987ab  mov     r9, [rsp+1E8h+var_180]
0x1400987b0  mov     r8d, [rsp+1E8h+var_184]
0x1400987b5  mov     rdx, r15
0x1400987b8  mov     rcx, [r13+0]
0x1400987bc  call    ?VidMmRotateLegacyAllocation@@YAJPEAVVIDMM_GLOBAL@@PEAUVIDMM_PHYSICAL_ALLOC@@W4_MM_ROTATE_DIRECTION@@P6AJPEAU_MDL@@3PEAX@ZPEAUVIDMM_ROTATE_COPY_CONTEXT@@TVIDMM_ROTATE_FLAGS@@@Z; VidMmRotateLegacyAllocation(VIDMM_GLOBAL *,VIDMM_PHYSICAL_ALLOC *,_MM_ROTATE_DIRECTION,long (*)(_MDL *,_MDL *,void *),VIDMM_ROTATE_COPY_CONTEXT *,VIDMM_ROTATE_FLAGS)
0x1400987c1  movsxd  r13, eax
0x1400987c4  lea     rcx, [rsp+1E8h+var_B8]; this
0x1400987cc  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400987d1  cmp     r13d, 0C000010Ah
0x1400987d8  jnz     short loc_140098837
0x1400987da  bts     dword ptr [rbx], 10h
0x1400987de  mov     edx, r12d; unsigned int
0x1400987e1  mov     rcx, rsi; struct VIDMM_GLOBAL_ALLOC *
  ... truncated ...
```
