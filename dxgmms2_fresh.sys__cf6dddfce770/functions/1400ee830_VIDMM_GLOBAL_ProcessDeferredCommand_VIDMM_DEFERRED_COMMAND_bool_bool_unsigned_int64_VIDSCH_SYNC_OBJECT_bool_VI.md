# VIDMM_GLOBAL::ProcessDeferredCommand(_VIDMM_DEFERRED_COMMAND *,bool *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *,bool,VIDMM_ALLOC * *)

- ea: `0x1400ee830`
- end: `0x1400ef29c`
- name: `?ProcessDeferredCommand@VIDMM_GLOBAL@@QEAAJPEAU_VIDMM_DEFERRED_COMMAND@@PEA_N_N_KPEAU_VIDSCH_SYNC_OBJECT@@2PEAPEAUVIDMM_ALLOC@@@Z`
- size: `2668`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct _VIDMM_DEFERRED_COMMAND *@<rdx>, bool *@<r8>, bool@<r9b>, unsigned __int64, struct _VIDSCH_SYNC_OBJECT *, bool, struct VIDMM_ALLOC **)`
- caller_count: `2`
- callee_count: `42`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400eb75c`
- `0x1400ee750`

## callees

- `0x14002b730`
- `0x14002b830`
- `0x14002ba94`
- `0x14002bcc0`
- `0x14002bddc`
- `0x14002eba4`
- `0x1400305ac`
- `0x140031434`
- `0x14003196c`
- `0x140035924`
- `0x14003b4fc`
- `0x140058f50`
- `0x140059030`
- `0x140096a04`
- `0x140096b90`
- `0x140096bfc`
- `0x140097580`
- `0x140099714`
- `0x14009ca80`
- `0x14009cf50`
- `0x14009e4a0`
- `0x1400a00dc`
- `0x1400a5598`
- `0x1400a6a34`
- `0x1400aad90`
- `0x1400ab03c`
- `0x1400b7298`
- `0x1400b8418`
- `0x1400bb310`
- `0x1400bd6ac`
- `0x1400c4984`
- `0x1400eb130`
- `0x1400eb290`
- `0x1400ee830`
- `0x1400ef500`
- `0x1400ef8f4`
- `0x1400efa1c`
- `0x14011249c`
- `0x140115f00`
- `0x14011610c`
- `0x14011a83c`
- `0x14011e98c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400ef08d`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400ef08d`
- `ntoskrnl!KeSetEvent` at `0x1400ee9e2`
- `ntoskrnl!KeSetEvent` at `0x1400ee9e2`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400eed1d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400eed6c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400eef8a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400eed1d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400eed6c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400eef8a`
- `watchdog!WdLogSingleEntry5` at `0x1400ef0c4`
- `watchdog!WdLogSingleEntry5` at `0x1400ef0c4`
- `watchdog!WdLogSingleEntry1` at `0x1400eebda`
- `watchdog!WdLogSingleEntry1` at `0x1400eebda`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400ef09e`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400eed11`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400eed60`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400eef7e`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_GLOBAL::ProcessDeferredCommand(
        VIDMM_GLOBAL *this,
        struct _VIDMM_DEFERRED_COMMAND *a2,
        bool *a3,
        bool a4,
        unsigned __int64 a5,
        struct _VIDSCH_SYNC_OBJECT *a6,
        char a7,
        __int64 ****a8)
{
  struct _VIDMM_DEFERRED_COMMAND *v8; // rsi
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // r15
  _QWORD *v13; // r12
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r10
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v17; // r13
  __int64 v18; // r9
  unsigned int v19; // ebx
  bool *v20; // r12
  unsigned int v21; // r15d
  struct VIDMM_PAGING *v22; // rcx
  int v24; // r10d
  unsigned int inited; // eax
  unsigned int *v26; // rax
  int updated; // eax
  __int64 v28; // rdx
  unsigned int v29; // eax
  unsigned __int16 v30; // r8
  int v31; // r10d
  unsigned int v32; // eax
  const signed __int32 *v33; // rcx
  int v34; // eax
  int v35; // ecx
  unsigned int v36; // r9d
  __int64 v37; // r8
  VIDMM_GLOBAL *v38; // rcx
  bool v39; // r8
  __int64 v40; // rax
  int v41; // eax
  struct VIDMM_GLOBAL_ALLOC *v42; // rbx
  char v43; // r15
  VIDMM_GLOBAL *v44; // rcx
  _QWORD **v45; // rax
  _QWORD *v46; // r15
  __int64 v47; // rsi
  _QWORD *i; // r12
  int v49; // [rsp+20h] [rbp-E0h]
  struct VIDMM_ALLOC **v50; // [rsp+28h] [rbp-D8h]
  char v52; // [rsp+58h] [rbp-A8h]
  union _LARGE_INTEGER Interval; // [rsp+68h] [rbp-98h] BYREF
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v55; // [rsp+70h] [rbp-90h] BYREF
  __int64 v56; // [rsp+78h] [rbp-88h]
  __int64 v57; // [rsp+80h] [rbp-80h]
  _BYTE v58[24]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v59[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _VIDSCH_SYNC_OBJECT *v60; // [rsp+B0h] [rbp-50h]
  _BYTE v61[64]; // [rsp+C0h] [rbp-40h] BYREF

  v8 = a2;
  v60 = a6;
  v59[0] = a2;
  *a8 = 0;
  v10 = *((_QWORD *)a2 + 2);
  if ( v10 )
  {
    v11 = *((_QWORD *)this + 4560);
    Interval = *(union _LARGE_INTEGER *)v10;
    v12 = *(_QWORD *)Interval.QuadPart;
    v57 = **(_QWORD **)Interval.QuadPart;
    v56 = *(_QWORD *)(v11 + 8LL * ((*(_DWORD *)(v57 + 60) >> 2) & 0x3F));
  }
  else
  {
    Interval.QuadPart = 0;
    v12 = 0;
    v57 = 0;
    v56 = 0;
  }
  v13 = (_QWORD *)*((_QWORD *)a2 + 1);
  if ( !v13 )
    v13 = *(_QWORD **)(v10 + 8);
  *a3 = 0;
  v50 = &v55;
  v14 = *(_DWORD *)a2;
  v55 = 0;
  VIDMM_GLOBAL::StartPreparation(this, 0xFFFFFFFFLL, v13, v10, v14);
  v15 = v13[4];
  v16 = 0;
  if ( v15 && (*(_BYTE *)(v15 + 212) || _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 208), 0, 0))
    || VIDMM_GLOBAL::IsTdrPending(this) )
  {
    *((_DWORD *)v8 + 21) = -1071775232;
    *((_BYTE *)v8 + 80) = 1;
  }
  v17 = v55;
  if ( *((_BYTE *)v8 + 80) != (_BYTE)v16 )
  {
    if ( *(_DWORD *)v8 == 113 )
    {
      DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
        (DXGAUTOPUSHLOCKEXCLUSIVE *)v58,
        (struct DXGPUSHLOCK *const)(*((_QWORD *)v8 + 4) + 64LL));
      VIDMM_GLOBAL::CleanupVadReference(v38, (struct _VIDMM_DEFERRED_COMMAND *)((char *)v8 + 32));
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v58);
      v16 = 0;
    }
    if ( (v29 = *(_DWORD *)v8 - 203, v29 <= 0xB) && (v15 = 2281, _bittest((const int *)&v15, v29))
      || *(_DWORD *)v8 == 113 )
    {
      v19 = *((_DWORD *)v8 + 21);
      goto LABEL_14;
    }
  }
  v18 = *(int *)v8;
  v19 = v16;
  LODWORD(v55) = v16;
  if ( (int)v18 > 209 )
  {
    switch ( (_DWORD)v18 )
    {
      case 0xD2:
        if ( !VIDMM_ALLOC::HasAnyResidencyReferences((VIDMM_ALLOC *)v10) )
          goto LABEL_14;
        v20 = a3;
        if ( v30 < 2u )
        {
          v32 = VIDMM_GLOBAL::PageInOneAllocation((__int64)this, v17, (__int64 ***)v10, 0, a7, a3, a8, v31, -1);
          *(_DWORD *)(v12 + 24) &= ~0x4000000u;
          v19 = v32;
        }
        goto LABEL_15;
      case 0xD3:
        v45 = (_QWORD **)(*((_QWORD *)v8 + 4) + 112LL);
        v46 = *v45;
        if ( *v45 != v45 )
        {
          v47 = *((_QWORD *)v8 + 4) + 112LL;
          do
          {
            for ( i = (_QWORD *)*(v46 - 2); i != v46 - 2; i = (_QWORD *)*i )
              VIDMM_GLOBAL::EvictOneAllocation(this, v17, (struct VIDMM_ALLOC *)(i - 5), 0);
            v46 = (_QWORD *)*v46;
          }
          while ( v46 != (_QWORD *)v47 );
          v8 = (struct _VIDMM_DEFERRED_COMMAND *)v59[0];
          v19 = (unsigned int)v55;
        }
        goto LABEL_14;
      case 0xD4:
        VIDMM_GLOBAL::UpdateAllocationPriority(this, (struct VIDMM_ALLOC *)v10, *((_DWORD *)v8 + 8));
        goto LABEL_14;
      case 0xD5:
        VIDMM_DEVICE::SuspendSchedulerDevice((VIDMM_DEVICE *)v13);
        VIDMM_DEVICE::SuspendPagingQueues((VIDMM_DEVICE *)v13);
        if ( v13[23] )
        {
          v52 = 0;
        }
        else
        {
          v52 = 1;
          DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
            (DXGAUTOPUSHLOCKEXCLUSIVE *)v58,
            (struct DXGPUSHLOCK *const)(*v13 + 41152LL));
          LOBYTE(v37) = 4;
          VIDMM_GLOBAL::InsertToPenaltyBox(*v13, v13, v37);
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v58);
        }
        if ( v10 )
        {
          if ( (*(_DWORD *)(v10 + 28) & 3) == 2 )
            VIDMM_GLOBAL::FaultOneAllocation((VIDMM_GLOBAL *)*v13, v17, (struct VIDMM_ALLOC *)v10);
        }
        else
        {
          VIDMM_DEVICE::FaultAllAllocations((VIDMM_DEVICE *)v13, v17);
        }
        VIDMM_GLOBAL::EvictFromFaultedList(this, v17, (struct VIDMM_DEVICE *)v13);
        v19 = VIDMM_GLOBAL::PageInFromFaultedList(this, v17, (struct VIDMM_DEVICE *)v13);
        VIDMM_DEVICE::ResumeSchedulerDevice((VIDMM_DEVICE *)v13);
        VIDMM_DEVICE::ResumePagingQueues((VIDMM_DEVICE *)v13);
        if ( v52 )
        {
          DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
            (DXGAUTOPUSHLOCKEXCLUSIVE *)v58,
            (struct DXGPUSHLOCK *const)(*v13 + 41152LL));
          VIDMM_GLOBAL::RemoveFromPenaltyBoxByListEntry(v44, (struct _LIST_ENTRY *)(v13 + 23));
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v58);
        }
        goto LABEL_14;
      case 0xD6:
        LOBYTE(v50) = *((_BYTE *)v8 + 53);
        LOBYTE(v49) = *((_BYTE *)v8 + 52);
        (*(void (__fastcall **)(__int64, struct VIDMM_PAGING_EXECUTION_CONTEXT *, __int64, _QWORD, int, struct VIDMM_ALLOC **, __int64))(*(_QWORD *)v56 + 328LL))(
          v56,
          v17,
          v10,
          *((unsigned int *)v8 + 8),
          v49,
          v50,
          (__int64)v8 + 36);
        if ( !VIDMM_ALLOC::HasAnyResidencyReferences((VIDMM_ALLOC *)v10) )
          goto LABEL_14;
        v20 = a3;
        if ( *(_WORD *)(*(_QWORD *)(v12 + 392) + 8LL) < 2u )
        {
          inited = VIDMM_GLOBAL::PageInOneAllocation((__int64)this, v17, (__int64 ***)v10, 0, a7, a3, a8, 0, -1);
          goto LABEL_27;
        }
        goto LABEL_15;
      case 0xD7:
LABEL_105:
        v42 = (struct VIDMM_GLOBAL_ALLOC *)*((_QWORD *)v8 + 4);
        v43 = v16;
        DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
          (DXGAUTOPUSHLOCKEXCLUSIVE *)v58,
          (VIDMM_GLOBAL *)((char *)this + 36408));
        if ( *((_QWORD *)v42 + 36) )
        {
          VIDMM_GLOBAL::RemoveAllocationFromDecommitList(this, v42);
          v43 = 1;
        }
        DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v58);
        if ( v43 )
          VIDMM_GLOBAL::DecommitGlobalAllocation(this, v17, v42);
        v19 = 0;
        goto LABEL_14;
      case 0xD9:
        Interval.QuadPart = -10000LL * *((unsigned int *)v8 + 8);
        KeDelayExecutionThread(0, 0, &Interval);
        goto LABEL_14;
    }
LABEL_104:
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 5, v18, -1073741811, v16);
    WdLogGlobalForLineNumber = 227;
    goto LABEL_105;
  }
  switch ( (_DWORD)v18 )
  {
    case 0xD1:
      v20 = a3;
      inited = VIDMM_GLOBAL::InitContextAllocation(
                 this,
                 v17,
                 (struct VIDMM_ALLOC *)v10,
                 1,
                 a3,
                 (struct VIDMM_ALLOC **)a8);
      goto LABEL_27;
    case 0x71:
      updated = VIDMM_GLOBAL::CommitVirtualAddressRangeSystemCommand(
                  this,
                  v17,
                  (struct _VIDMM_DEFERRED_COMMAND *)((char *)v8 + 32),
                  (struct VIDMM_ALLOC **)a8);
      goto LABEL_37;
    case 0x77:
      updated = VIDMM_GLOBAL::UpdateGpuVirtualAddressSystemCommand(
                  this,
                  v17,
                  *((struct VIDSCH_DEVICE_COMMAND_UPDATEGPUVA **)v8 + 4),
                  (struct VIDMM_ALLOC **)a8);
LABEL_37:
      v20 = a3;
      v19 = updated;
      if ( updated == -1073741267 )
        *a3 = 1;
      goto LABEL_15;
    case 0xC8:
      VIDMM_GLOBAL::VidMmOpCloseAllocationCommand(this, v17, (struct VIDMM_ALLOC *)v10);
      goto LABEL_14;
    case 0xCB:
      if ( g_IsInternalReleaseOrDbg != (_BYTE)v16 )
      {
        v40 = WdLogNewEntry5_WdTrace((unsigned int)(v18 - 203), v15);
        LOBYTE(v16) = 0;
        *(_QWORD *)(v40 + 24) = v10;
        WdLogGlobalForLineNumber = 12531;
      }
      if ( *(_BYTE *)(v12 + 41) != (_BYTE)v16 )
      {
        v19 = -1071775482;
        goto LABEL_14;
      }
      if ( !*(_DWORD *)(*(_QWORD *)(v12 + 392) + 16LL) )
      {
        v33 = *(const signed __int32 **)(v12 + 392);
        if ( !_bittest(v33, 0x11u) )
        {
          if ( g_IsInternalReleaseOrDbg != (_BYTE)v16 )
          {
            WdLogNewEntry5_WdTrace(v33, v15);
            WdLogGlobalForLineNumber = 12554;
            LOBYTE(v16) = 0;
            v33 = *(const signed __int32 **)(v12 + 392);
          }
          if ( (*(_DWORD *)(v57 + 64) & 1) != 0 )
          {
            v34 = *v33;
            if ( (*v33 & 0x40000000) == 0 && ((v34 & 0x20000000) == 0 || v34 >= 0) && (v34 & 0x80000) == 0 )
            {
              if ( g_IsInternalReleaseOrDbg != (_BYTE)v16 )
              {
                WdLogNewEntry5_WdTrace(v33, v57);
                WdLogGlobalForLineNumber = 12567;
              }
              VidMmSuspendAccessToAllocation(
                *(struct VIDMM_WORKER_THREAD **)this,
                v17,
                (struct VIDMM_GLOBAL_ALLOC *)v12);
              VIDMM_GLOBAL::EvictAllocation(this, v17, (struct VIDMM_GLOBAL_ALLOC *)v12);
              (*(void (__fastcall **)(__int64, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(*(_QWORD *)v56 + 200LL))(
                v56,
                v17);
            }
          }
        }
      }
      v35 = **(_DWORD **)(v12 + 392);
      if ( (v35 & 0x20000) != 0 )
      {
        v36 = *((_DWORD *)v8 + 8);
      }
      else if ( (v35 & 0x40000000) != 0 || (v36 = 4, v35 < 0) )
      {
        v36 = 3;
      }
      if ( *((_QWORD *)v8 + 5) != -1 )
        *(_DWORD *)(v12 + 28) |= 4u;
      v20 = a3;
      v41 = VIDMM_GLOBAL::PageInOneAllocation(
              (__int64)this,
              v17,
              (__int64 ***)v10,
              v36,
              a7,
              a3,
              a8,
              *((_DWORD *)v8 + 9),
              *((_QWORD *)v8 + 5));
      *(_DWORD *)(v12 + 28) &= ~4u;
      v19 = v41;
      if ( v41 >= 0 )
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v12 + 392) + 16LL));
      VIDMM_GLOBAL::RecommitTrimmedList(this);
      goto LABEL_15;
  }
  if ( (_DWORD)v18 != 206 )
  {
    if ( (_DWORD)v18 == 207 )
    {
      if ( !*(_DWORD *)(v10 + 688) && (*(_BYTE *)(v10 + 25) & 1) == 0 )
        VIDMM_GLOBAL::EvictOneAllocation(this, v17, (struct VIDMM_ALLOC *)v10, *((_BYTE *)v8 + 32) & 1);
      _InterlockedDecrement((volatile signed __int32 *)(v10 + 700));
      goto LABEL_14;
    }
    if ( (_DWORD)v18 == 208 )
    {
      if ( *((_BYTE *)v8 + 45) == (_BYTE)v16 )
      {
        (*(void (__fastcall **)(__int64, struct VIDMM_PAGING_EXECUTION_CONTEXT *, __int64))(*(_QWORD *)v56 + 216LL))(
          v56,
          v17,
          v57);
        VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
          (VIDMM_PROCESS_AUTOATTACH *)v61,
          *(struct VIDMM_PROCESS **)(Interval.QuadPart + 8),
          1);
        DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(
          (DXGAUTOPUSHLOCKFASTEXCLUSIVE *)v59,
          (struct DXGPUSHLOCKFAST *)(v12 + 320),
          v39);
        v19 = VIDMM_GLOBAL::LockInternal(
                this,
                v17,
                (struct VIDMM_ALLOC *)v10,
                *((_BYTE *)v8 + 44),
                *((_DWORD *)v8 + 10),
                *((void ***)v8 + 4),
                (bool *)v8 + 45);
        DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release((DXGAUTOPUSHLOCKFASTEXCLUSIVE *)v59);
        VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v61);
        LODWORD(v16) = 0;
        if ( !*((_BYTE *)v8 + 45) )
          goto LABEL_14;
      }
      v20 = a3;
      inited = VIDMM_GLOBAL::PageInOneAllocation((__int64)this, v17, (__int64 ***)v10, 2u, v16, a3, a8, v16, -1);
      goto LABEL_27;
    }
    goto LABEL_104;
  }
  if ( *(int *)(v12 + 184) > 0 && (unsigned __int8)NeedsApertureForLock(this, v12) && (*(_DWORD *)(v12 + 24) & 1) == 0 )
  {
    WdLogSingleEntry1(3, v28);
    WdLogGlobalForLineNumber = 12635;
    v19 = -1073741823;
    goto LABEL_14;
  }
  if ( !VIDMM_ALLOC::HasAnyResidencyReferences((VIDMM_ALLOC *)v10) )
  {
LABEL_14:
    v20 = a3;
    goto LABEL_15;
  }
  v20 = a3;
  if ( *(_WORD *)(*(_QWORD *)(v12 + 392) + 8LL) < 2u )
  {
    inited = VIDMM_GLOBAL::PageInOneAllocation((__int64)this, v17, (__int64 ***)v10, 0, a7, a3, a8, v24, -1);
LABEL_27:
    v19 = inited;
  }
LABEL_15:
  if ( *v20 )
  {
    v21 = 0;
    *((_QWORD *)this + 82) = (char *)this + 648;
    for ( *((_QWORD *)this + 81) = (char *)this + 648; v21 < *((_DWORD *)this + 778); ++v21 )
      VIDMM_GLOBAL::EndPreparationOnPhysicalAdapter(this, v17, v21);
    VIDMM_GLOBAL::ResumeSuspendedDevicesForMove(this, 0xFFFFFFFF);
    v22 = (struct VIDMM_PAGING *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 390) = 0;
    *((_QWORD *)this + 391) = 0;
    *((_DWORD *)this + 2) = 0;
    VidMmReleasePagingExecutionContext(v22, v17);
  }
  else
  {
    v26 = (unsigned int *)*((_QWORD *)v8 + 3);
    if ( v26 )
      *v26 = v19;
    VIDMM_GLOBAL::EndPreparation(this, v17, 0xFFFFFFFF, 0, a4, a5, v60);
  }
  if ( *(_DWORD *)v8 == 200 )
  {
    KeSetEvent((PRKEVENT)(*((_QWORD *)v8 + 2) + 72LL), 0, 0);
  }
  else if ( !*v20 && v10 )
  {
    VIDMM_ALLOC::DecrementPagingPacketReferenceCount((VIDMM_ALLOC *)v10);
  }
  *((_DWORD *)v8 + 21) = v19;
  return v19;
}

```

## disassembly

```asm
0x1400ee830  mov     [rsp-8+arg_18], rbx
0x1400ee835  push    rbp
0x1400ee836  push    rsi
0x1400ee837  push    rdi
0x1400ee838  push    r12
0x1400ee83a  push    r13
0x1400ee83c  push    r14
0x1400ee83e  push    r15
0x1400ee840  lea     rbp, [rsp-10h]
0x1400ee845  sub     rsp, 110h
0x1400ee84c  mov     rax, cs:__security_cookie
0x1400ee853  xor     rax, rsp
0x1400ee856  mov     [rbp+40h+var_40], rax
0x1400ee85a  mov     rax, [rbp+40h+arg_28]
0x1400ee85e  mov     rsi, rdx
0x1400ee861  mov     [rbp+40h+var_90], rax
0x1400ee865  mov     rdi, rcx
0x1400ee868  mov     rax, [rbp+40h+arg_38]
0x1400ee86f  mov     [rsp+140h+var_E7], r9b
0x1400ee874  xor     r9d, r9d
0x1400ee877  mov     [rsp+140h+var_F0], r8
0x1400ee87c  mov     [rbp+40h+var_A0], rdx
0x1400ee880  mov     [rax], r9
0x1400ee883  mov     r14, [rdx+10h]
0x1400ee887  mov     [rsp+140h+var_E0], rax
0x1400ee88c  test    r14, r14
0x1400ee88f  jz      loc_1400EEE2C
0x1400ee895  mov     rdx, [r14]
0x1400ee898  mov     rax, [rdi+8E80h]
0x1400ee89f  mov     qword ptr [rsp+140h+Interval], rdx
0x1400ee8a4  mov     r15, [rdx]
0x1400ee8a7  mov     rdx, [r15]
0x1400ee8aa  mov     [rbp+40h+var_C0], rdx
0x1400ee8ae  mov     ecx, [rdx+3Ch]
0x1400ee8b1  shr     rcx, 2
0x1400ee8b5  and     ecx, 3Fh
0x1400ee8b8  mov     rax, [rax+rcx*8]
0x1400ee8bc  mov     [rsp+140h+var_C8], rax
0x1400ee8c1  mov     r12, [rsi+8]
0x1400ee8c5  test    r12, r12
0x1400ee8c8  jz      loc_1400EEE42
0x1400ee8ce  mov     [r8], r9b
0x1400ee8d1  lea     rax, [rsp+140h+var_D0]
0x1400ee8d6  mov     [rsp+140h+var_118], rax
0x1400ee8db  mov     r8, r12
0x1400ee8de  mov     eax, [rsi]
0x1400ee8e0  or      edx, 0FFFFFFFFh
0x1400ee8e3  mov     [rsp+140h+var_D0], r9
0x1400ee8e8  mov     rcx, rdi
0x1400ee8eb  mov     r9, r14
0x1400ee8ee  mov     dword ptr [rsp+140h+var_120], eax
0x1400ee8f2  call    ?StartPreparation@VIDMM_GLOBAL@@QEAAXIPEAVVIDMM_DEVICE@@PEAUVIDMM_ALLOC@@W4VIDMM_OPERATION@@PEAPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_GLOBAL::StartPreparation(uint,VIDMM_DEVICE *,VIDMM_ALLOC *,VIDMM_OPERATION,VIDMM_PAGING_EXECUTION_CONTEXT * *)
0x1400ee8f7  mov     rdx, [r12+20h]
0x1400ee8fc  xor     r10d, r10d
0x1400ee8ff  test    rdx, rdx
0x1400ee902  jnz     loc_1400EEAA6
0x1400ee908  mov     rcx, rdi; this
0x1400ee90b  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400ee910  test    al, al
0x1400ee912  jnz     loc_1400EEAC2
0x1400ee918  mov     r13, [rsp+140h+var_D0]
0x1400ee91d  cmp     [rsi+50h], r10b
0x1400ee921  jnz     loc_1400EEC1F
0x1400ee927  movsxd  r9, dword ptr [rsi]
0x1400ee92a  mov     eax, 0D1h
0x1400ee92f  mov     ebx, r10d
0x1400ee932  mov     dword ptr [rsp+140h+var_D0], ebx
0x1400ee936  cmp     r9d, eax
0x1400ee939  jg      loc_1400EEB81
0x1400ee93f  jz      loc_1400EECC4
0x1400ee945  mov     ecx, r9d
0x1400ee948  sub     ecx, 71h ; 'q'
0x1400ee94b  jz      loc_1400EEB30
0x1400ee951  sub     ecx, 6
0x1400ee954  jz      loc_1400EF03C
0x1400ee95a  sub     ecx, 51h ; 'Q'
0x1400ee95d  jnz     loc_1400EEA1B
0x1400ee963  mov     r8, r14; struct VIDMM_ALLOC *
0x1400ee966  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400ee969  mov     rcx, rdi; this
0x1400ee96c  call    ?VidMmOpCloseAllocationCommand@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::VidMmOpCloseAllocationCommand(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *)
0x1400ee971  mov     r12, [rsp+140h+var_F0]
0x1400ee976  cmp     byte ptr [r12], 0
0x1400ee97b  jz      loc_1400EEAF2
0x1400ee981  lea     rax, [rdi+288h]
0x1400ee988  xor     r15d, r15d
0x1400ee98b  mov     [rax+8], rax
0x1400ee98f  mov     [rax], rax
0x1400ee992  cmp     [rdi+0C28h], r15d
0x1400ee999  ja      loc_1400EEAD2
0x1400ee99f  or      edx, 0FFFFFFFFh; unsigned int
0x1400ee9a2  mov     rcx, rdi; this
0x1400ee9a5  call    ?ResumeSuspendedDevicesForMove@VIDMM_GLOBAL@@QEAAXI@Z; VIDMM_GLOBAL::ResumeSuspendedDevicesForMove(uint)
0x1400ee9aa  mov     rcx, [rdi+30h]; struct VIDMM_PAGING *
0x1400ee9ae  xor     eax, eax
0x1400ee9b0  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400ee9b3  mov     [rdi+0C30h], rax
0x1400ee9ba  mov     [rdi+0C38h], rax
0x1400ee9c1  mov     [rdi+8], eax
0x1400ee9c4  call    ?VidMmReleasePagingExecutionContext@@YAXPEAUVIDMM_PAGING@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VidMmReleasePagingExecutionContext(VIDMM_PAGING *,VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400ee9c9  cmp     dword ptr [rsi], 0C8h
0x1400ee9cf  jnz     loc_1400EEB60
0x1400ee9d5  mov     rcx, [rsi+10h]
0x1400ee9d9  xor     r8d, r8d; Wait
0x1400ee9dc  add     rcx, 48h ; 'H'; Event
0x1400ee9e0  xor     edx, edx; Increment
0x1400ee9e2  call    cs:__imp_KeSetEvent
0x1400ee9e9  nop     dword ptr [rax+rax+00h]
0x1400ee9ee  mov     [rsi+54h], ebx
0x1400ee9f1  mov     eax, ebx
0x1400ee9f3  mov     rcx, [rbp+40h+var_40]
0x1400ee9f7  xor     rcx, rsp; StackCookie
0x1400ee9fa  call    __security_check_cookie
0x1400ee9ff  mov     rbx, [rsp+140h+arg_18]
0x1400eea07  add     rsp, 110h
0x1400eea0e  pop     r15
0x1400eea10  pop     r14
0x1400eea12  pop     r13
0x1400eea14  pop     r12
0x1400eea16  pop     rdi
0x1400eea17  pop     rsi
0x1400eea18  pop     rbp
0x1400eea19  retn
0x1400eea1b  sub     ecx, 3
0x1400eea1e  jz      loc_1400EEF7E
0x1400eea24  sub     ecx, 3
0x1400eea27  jnz     loc_1400EEBFA
0x1400eea2d  mov     eax, [r15+0B8h]
0x1400eea34  test    eax, eax
0x1400eea36  jg      loc_1400EEBB6
0x1400eea3c  mov     rcx, r14; this
0x1400eea3f  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x1400eea44  test    al, al
0x1400eea46  jz      loc_1400EE971
0x1400eea4c  mov     rax, [r15+188h]
0x1400eea53  mov     edx, 2
0x1400eea58  mov     r12, [rsp+140h+var_F0]
0x1400eea5d  cmp     [rax+8], dx
0x1400eea61  jnb     loc_1400EE976
0x1400eea67  mov     [rsp+140h+var_100], 0FFFFFFFFFFFFFFFFh
0x1400eea70  mov     [rsp+140h+var_108], r10d
0x1400eea75  mov     rax, [rsp+140h+var_E0]
0x1400eea7a  xor     r9d, r9d
0x1400eea7d  mov     [rsp+140h+var_110], rax
0x1400eea82  mov     al, [rbp+40h+arg_30]
0x1400eea88  mov     [rsp+140h+var_118], r12
0x1400eea8d  mov     byte ptr [rsp+140h+var_120], al
0x1400eea91  mov     r8, r14
0x1400eea94  mov     rdx, r13
0x1400eea97  mov     rcx, rdi
0x1400eea9a  call    ?PageInOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@W4VIDMM_PLACEMENT_RESTRICTION@@_NPEA_NPEAPEAU3@I_K@Z; VIDMM_GLOBAL::PageInOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,VIDMM_PLACEMENT_RESTRICTION,bool,bool *,VIDMM_ALLOC * *,uint,unsigned __int64)
0x1400eea9f  mov     ebx, eax
0x1400eeaa1  jmp     loc_1400EE976
0x1400eeaa6  cmp     [rdx+0D4h], r10b
0x1400eeaad  jnz     short loc_1400EEAC2
0x1400eeaaf  mov     ecx, r10d
0x1400eeab2  xor     eax, eax
0x1400eeab4  lock cmpxchg [rdx+0D0h], ecx
0x1400eeabc  jz      loc_1400EE908
0x1400eeac2  mov     dword ptr [rsi+54h], 0C01E0200h
0x1400eeac9  mov     byte ptr [rsi+50h], 1
0x1400eeacd  jmp     loc_1400EE918
0x1400eead2  mov     r8d, r15d; unsigned int
0x1400eead5  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400eead8  mov     rcx, rdi; this
0x1400eeadb  call    ?EndPreparationOnPhysicalAdapter@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::EndPreparationOnPhysicalAdapter(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400eeae0  inc     r15d
0x1400eeae3  cmp     r15d, [rdi+0C28h]
0x1400eeaea  jnb     loc_1400EE99F
0x1400eeaf0  jmp     short loc_1400EEAD2
0x1400eeaf2  mov     rax, [rsi+18h]
0x1400eeaf6  test    rax, rax
0x1400eeaf9  jnz     loc_1400EF295
0x1400eeaff  mov     rax, [rbp+40h+var_90]
0x1400eeb03  xor     r9d, r9d; struct _KEVENT *
0x1400eeb06  mov     [rsp+140h+var_110], rax; struct _VIDSCH_SYNC_OBJECT *
0x1400eeb0b  or      r8d, 0FFFFFFFFh; unsigned int
0x1400eeb0f  mov     rax, [rbp+40h+arg_20]
0x1400eeb13  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400eeb16  mov     [rsp+140h+var_118], rax; unsigned __int64
0x1400eeb1b  mov     rcx, rdi; this
0x1400eeb1e  mov     al, [rsp+140h+var_E7]
0x1400eeb22  mov     byte ptr [rsp+140h+var_120], al; bool
0x1400eeb26  call    ?EndPreparation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@IPEAU_KEVENT@@_N_KPEAU_VIDSCH_SYNC_OBJECT@@@Z; VIDMM_GLOBAL::EndPreparation(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,_KEVENT *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *)
0x1400eeb2b  jmp     loc_1400EE9C9
0x1400eeb30  mov     r9, [rsp+140h+var_E0]; struct VIDMM_ALLOC **
0x1400eeb35  lea     r8, [rsi+20h]; struct VIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE *
0x1400eeb39  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400eeb3c  mov     rcx, rdi; this
0x1400eeb3f  call    ?CommitVirtualAddressRangeSystemCommand@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::CommitVirtualAddressRangeSystemCommand(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE *,VIDMM_ALLOC * *)
0x1400eeb44  mov     r12, [rsp+140h+var_F0]
0x1400eeb49  mov     ebx, eax
0x1400eeb4b  cmp     eax, 0C000022Dh
0x1400eeb50  jnz     loc_1400EE976
0x1400eeb56  mov     byte ptr [r12], 1
0x1400eeb5b  jmp     loc_1400EE976
0x1400eeb60  cmp     byte ptr [r12], 0
0x1400eeb65  jnz     loc_1400EE9EE
0x1400eeb6b  test    r14, r14
0x1400eeb6e  jz      loc_1400EE9EE
0x1400eeb74  mov     rcx, r14; this
0x1400eeb77  call    ?DecrementPagingPacketReferenceCount@VIDMM_ALLOC@@QEAAXXZ; VIDMM_ALLOC::DecrementPagingPacketReferenceCount(void)
0x1400eeb7c  jmp     loc_1400EE9EE
0x1400eeb81  mov     ecx, r9d
0x1400eeb84  sub     ecx, 0D2h
0x1400eeb8a  jz      loc_1400EEC4F
0x1400eeb90  sub     ecx, 1
0x1400eeb93  jz      loc_1400EF23D
0x1400eeb99  sub     ecx, 1
0x1400eeb9c  jnz     loc_1400EF055
0x1400eeba2  mov     r8d, [rsi+20h]; unsigned int
0x1400eeba6  mov     rdx, r14; struct VIDMM_ALLOC *
0x1400eeba9  mov     rcx, rdi; this
0x1400eebac  call    ?UpdateAllocationPriority@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@K@Z; VIDMM_GLOBAL::UpdateAllocationPriority(VIDMM_ALLOC *,ulong)
0x1400eebb1  jmp     loc_1400EE971
0x1400eebb6  mov     rdx, r15
0x1400eebb9  mov     rcx, rdi
0x1400eebbc  call    NeedsApertureForLock
0x1400eebc1  test    al, al
0x1400eebc3  jz      loc_1400EEA3C
0x1400eebc9  mov     eax, [r15+18h]
0x1400eebcd  test    al, 1
0x1400eebcf  jnz     loc_1400EEA3C
0x1400eebd5  mov     ecx, 3
0x1400eebda  call    cs:__imp_WdLogSingleEntry1
0x1400eebe1  nop     dword ptr [rax+rax+00h]
0x1400eebe6  mov     cs:WdLogGlobalForLineNumber, 315Bh
0x1400eebf0  mov     ebx, 0C0000001h
0x1400eebf5  jmp     loc_1400EE971
0x1400eebfa  sub     ecx, 1
0x1400eebfd  jnz     loc_1400EEE84
0x1400eec03  mov     eax, [r14+2B0h]
0x1400eec0a  test    eax, eax
0x1400eec0c  jz      loc_1400EEF58
0x1400eec12  lock dec dword ptr [r14+2BCh]
0x1400eec1a  jmp     loc_1400EE971
0x1400eec1f  cmp     dword ptr [rsi], 71h ; 'q'
0x1400eec22  jz      loc_1400EEE4B
0x1400eec28  mov     ecx, [rsi]
0x1400eec2a  lea     eax, [rcx-0CBh]
0x1400eec30  cmp     eax, 0Bh
0x1400eec33  ja      loc_1400EEE76
0x1400eec39  mov     edx, 8E9h
0x1400eec3e  bt      edx, eax
0x1400eec41  jnb     loc_1400EEE76
0x1400eec47  mov     ebx, [rsi+54h]
0x1400eec4a  jmp     loc_1400EE971
0x1400eec4f  mov     rax, [r15+188h]
0x1400eec56  mov     rcx, r14; this
0x1400eec59  movzx   r8d, word ptr [rax+8]
0x1400eec5e  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x1400eec63  test    al, al
0x1400eec65  jz      loc_1400EE971
0x1400eec6b  mov     r12, [rsp+140h+var_F0]
0x1400eec70  mov     edx, 2
0x1400eec75  cmp     r8w, dx
0x1400eec79  jnb     loc_1400EE976
0x1400eec7f  mov     rax, [rsp+140h+var_E0]
0x1400eec84  xor     r9d, r9d
0x1400eec87  mov     [rsp+140h+var_100], 0FFFFFFFFFFFFFFFFh
0x1400eec90  mov     r8, r14
0x1400eec93  mov     [rsp+140h+var_108], r10d
0x1400eec98  mov     rdx, r13
0x1400eec9b  mov     [rsp+140h+var_110], rax
0x1400eeca0  mov     rcx, rdi
0x1400eeca3  mov     al, [rbp+40h+arg_30]
0x1400eeca9  mov     [rsp+140h+var_118], r12
0x1400eecae  mov     byte ptr [rsp+140h+var_120], al
0x1400eecb2  call    ?PageInOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@W4VIDMM_PLACEMENT_RESTRICTION@@_NPEA_NPEAPEAU3@I_K@Z; VIDMM_GLOBAL::PageInOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,VIDMM_PLACEMENT_RESTRICTION,bool,bool *,VIDMM_ALLOC * *,uint,unsigned __int64)
0x1400eecb7  btr     dword ptr [r15+18h], 1Ah
0x1400eecbd  mov     ebx, eax
0x1400eecbf  jmp     loc_1400EE976
0x1400eecc4  mov     rax, [rsp+140h+var_E0]
0x1400eecc9  mov     r9b, 1; bool
0x1400eeccc  mov     r12, [rsp+140h+var_F0]
0x1400eecd1  mov     r8, r14; struct VIDMM_ALLOC *
0x1400eecd4  mov     [rsp+140h+var_118], rax; struct VIDMM_ALLOC **
0x1400eecd9  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400eecdc  mov     rcx, rdi; this
0x1400eecdf  mov     [rsp+140h+var_120], r12; bool *
0x1400eece4  call    ?InitContextAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_NPEA_NPEAPEAU3@@Z; VIDMM_GLOBAL::InitContextAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool,bool *,VIDMM_ALLOC * *)
0x1400eece9  jmp     loc_1400EEA9F
0x1400eecee  mov     rax, [r15+188h]
0x1400eecf5  mov     ecx, [rax+10h]
0x1400eecf8  test    ecx, ecx
0x1400eecfa  jnz     loc_1400EEDB8
0x1400eed00  mov     rcx, [r15+188h]
0x1400eed07  bt      dword ptr [rcx], 11h
0x1400eed0b  jb      loc_1400EEDB8
0x1400eed11  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400eed18  cmp     [rax], r10b
0x1400eed1b  jz      short loc_1400EED3D
0x1400eed1d  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400eed24  nop     dword ptr [rax+rax+00h]
0x1400eed29  mov     cs:WdLogGlobalForLineNumber, 310Ah
0x1400eed33  xor     r10d, r10d
0x1400eed36  mov     rcx, [r15+188h]
0x1400eed3d  mov     rdx, [rbp+40h+var_C0]
0x1400eed41  mov     eax, [rdx+40h]
0x1400eed44  test    al, 1
  ... truncated ...
```
