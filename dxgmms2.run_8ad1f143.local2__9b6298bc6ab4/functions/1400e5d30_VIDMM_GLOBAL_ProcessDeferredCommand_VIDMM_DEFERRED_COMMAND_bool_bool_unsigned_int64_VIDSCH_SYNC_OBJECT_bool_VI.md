# VIDMM_GLOBAL::ProcessDeferredCommand(_VIDMM_DEFERRED_COMMAND *,bool *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *,bool,VIDMM_ALLOC * *)

- ea: `0x1400e5d30`
- end: `0x1400e679c`
- name: `?ProcessDeferredCommand@VIDMM_GLOBAL@@QEAAJPEAU_VIDMM_DEFERRED_COMMAND@@PEA_N_N_KPEAU_VIDSCH_SYNC_OBJECT@@2PEAPEAUVIDMM_ALLOC@@@Z`
- size: `2668`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct _VIDMM_DEFERRED_COMMAND *@<rdx>, bool *@<r8>, bool@<r9b>, unsigned __int64, struct _VIDSCH_SYNC_OBJECT *, bool, struct VIDMM_ALLOC **)`
- caller_count: `2`
- callee_count: `42`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400e5c50`
- `0x1400e7114`

## callees

- `0x14002e850`
- `0x14002e950`
- `0x14002e9d4`
- `0x14002ec00`
- `0x14002ed1c`
- `0x140030fc4`
- `0x1400327ec`
- `0x1400335c4`
- `0x1400336b8`
- `0x140036b14`
- `0x14003c7ec`
- `0x140058680`
- `0x140058760`
- `0x140095bc4`
- `0x140098f38`
- `0x140099408`
- `0x14009a958`
- `0x14009c7fc`
- `0x14009c988`
- `0x14009c9f4`
- `0x14009ced0`
- `0x1400a38c4`
- `0x1400a52b8`
- `0x1400a61a4`
- `0x1400a9c40`
- `0x1400a9efc`
- `0x1400b395c`
- `0x1400b4ae0`
- `0x1400b7928`
- `0x1400b9cc4`
- `0x1400c0894`
- `0x1400e5d30`
- `0x1400e6a00`
- `0x1400e6df4`
- `0x1400e6f1c`
- `0x1400ff9e8`
- `0x1400ffb48`
- `0x14010f268`
- `0x140113110`
- `0x14011331c`
- `0x140116d3c`
- `0x14011b07c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400e658d`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400e658d`
- `ntoskrnl!KeSetEvent` at `0x1400e5ee2`
- `ntoskrnl!KeSetEvent` at `0x1400e5ee2`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e621d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e626c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e648a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e621d`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e626c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400e648a`
- `watchdog!WdLogSingleEntry5` at `0x1400e65c4`
- `watchdog!WdLogSingleEntry5` at `0x1400e65c4`
- `watchdog!WdLogSingleEntry1` at `0x1400e60da`
- `watchdog!WdLogSingleEntry1` at `0x1400e60da`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400e659e`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e6211`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e6260`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400e647e`

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
  int v16; // r10d
  struct VIDMM_PAGING_EXECUTION_CONTEXT *v17; // r13
  int v18; // r9d
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
  v18 = *(_DWORD *)v8;
  v19 = v16;
  LODWORD(v55) = v16;
  if ( v18 > 209 )
  {
    switch ( v18 )
    {
      case 210:
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
      case 211:
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
      case 212:
        VIDMM_GLOBAL::UpdateAllocationPriority(this, (struct VIDMM_ALLOC *)v10, *((_DWORD *)v8 + 8));
        goto LABEL_14;
      case 213:
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
      case 214:
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
        if ( *(_WORD *)(*(_QWORD *)(v12 + 384) + 8LL) < 2u )
        {
          inited = VIDMM_GLOBAL::PageInOneAllocation((__int64)this, v17, (__int64 ***)v10, 0, a7, a3, a8, 0, -1);
          goto LABEL_27;
        }
        goto LABEL_15;
      case 215:
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
      case 217:
        Interval.QuadPart = -10000LL * *((unsigned int *)v8 + 8);
        KeDelayExecutionThread(0, 0, &Interval);
        goto LABEL_14;
    }
LABEL_104:
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 5);
    WdLogGlobalForLineNumber = 222;
    goto LABEL_105;
  }
  switch ( v18 )
  {
    case 209:
      v20 = a3;
      inited = VIDMM_GLOBAL::InitContextAllocation(
                 this,
                 v17,
                 (struct VIDMM_ALLOC *)v10,
                 1,
                 a3,
                 (struct VIDMM_ALLOC **)a8);
      goto LABEL_27;
    case 113:
      updated = VIDMM_GLOBAL::CommitVirtualAddressRangeSystemCommand(
                  this,
                  v17,
                  (struct _VIDMM_DEFERRED_COMMAND *)((char *)v8 + 32),
                  (struct VIDMM_ALLOC **)a8);
      goto LABEL_37;
    case 119:
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
    case 200:
      VIDMM_GLOBAL::VidMmOpCloseAllocationCommand(this, v17, (struct VIDMM_ALLOC *)v10);
      goto LABEL_14;
    case 203:
      if ( g_IsInternalReleaseOrDbg != (_BYTE)v16 )
      {
        v40 = WdLogNewEntry5_WdTrace((unsigned int)(v18 - 203), v15);
        LOBYTE(v16) = 0;
        *(_QWORD *)(v40 + 24) = v10;
        WdLogGlobalForLineNumber = 12359;
      }
      if ( *(_BYTE *)(v12 + 41) != (_BYTE)v16 )
      {
        v19 = -1071775482;
        goto LABEL_14;
      }
      if ( !*(_DWORD *)(*(_QWORD *)(v12 + 384) + 16LL) )
      {
        v33 = *(const signed __int32 **)(v12 + 384);
        if ( !_bittest(v33, 0x11u) )
        {
          if ( g_IsInternalReleaseOrDbg != (_BYTE)v16 )
          {
            WdLogNewEntry5_WdTrace(v33, v15);
            WdLogGlobalForLineNumber = 12382;
            LOBYTE(v16) = 0;
            v33 = *(const signed __int32 **)(v12 + 384);
          }
          if ( (*(_DWORD *)(v57 + 64) & 1) != 0 )
          {
            v34 = *v33;
            if ( (*v33 & 0x40000000) == 0 && ((v34 & 0x20000000) == 0 || v34 >= 0) && (v34 & 0x80000) == 0 )
            {
              if ( g_IsInternalReleaseOrDbg != (_BYTE)v16 )
              {
                WdLogNewEntry5_WdTrace(v33, v57);
                WdLogGlobalForLineNumber = 12395;
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
      v35 = **(_DWORD **)(v12 + 384);
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
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v12 + 384) + 16LL));
      VIDMM_GLOBAL::RecommitTrimmedList(this);
      goto LABEL_15;
  }
  if ( v18 != 206 )
  {
    if ( v18 == 207 )
    {
      if ( !*(_DWORD *)(v10 + 688) && (*(_BYTE *)(v10 + 25) & 1) == 0 )
        VIDMM_GLOBAL::EvictOneAllocation(this, v17, (struct VIDMM_ALLOC *)v10, *((_BYTE *)v8 + 32) & 1);
      _InterlockedDecrement((volatile signed __int32 *)(v10 + 700));
      goto LABEL_14;
    }
    if ( v18 == 208 )
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
        v16 = 0;
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
    WdLogGlobalForLineNumber = 12463;
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
  if ( *(_WORD *)(*(_QWORD *)(v12 + 384) + 8LL) < 2u )
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
0x1400e5d30  mov     [rsp-8+arg_18], rbx
0x1400e5d35  push    rbp
0x1400e5d36  push    rsi
0x1400e5d37  push    rdi
0x1400e5d38  push    r12
0x1400e5d3a  push    r13
0x1400e5d3c  push    r14
0x1400e5d3e  push    r15
0x1400e5d40  lea     rbp, [rsp-10h]
0x1400e5d45  sub     rsp, 110h
0x1400e5d4c  mov     rax, cs:__security_cookie
0x1400e5d53  xor     rax, rsp
0x1400e5d56  mov     [rbp+40h+var_40], rax
0x1400e5d5a  mov     rax, [rbp+40h+arg_28]
0x1400e5d5e  mov     rsi, rdx
0x1400e5d61  mov     [rbp+40h+var_90], rax
0x1400e5d65  mov     rdi, rcx
0x1400e5d68  mov     rax, [rbp+40h+arg_38]
0x1400e5d6f  mov     [rsp+140h+var_E7], r9b
0x1400e5d74  xor     r9d, r9d
0x1400e5d77  mov     [rsp+140h+var_F0], r8
0x1400e5d7c  mov     [rbp+40h+var_A0], rdx
0x1400e5d80  mov     [rax], r9
0x1400e5d83  mov     r14, [rdx+10h]
0x1400e5d87  mov     [rsp+140h+var_E0], rax
0x1400e5d8c  test    r14, r14
0x1400e5d8f  jz      loc_1400E632C
0x1400e5d95  mov     rdx, [r14]
0x1400e5d98  mov     rax, [rdi+8E80h]
0x1400e5d9f  mov     qword ptr [rsp+140h+Interval], rdx
0x1400e5da4  mov     r15, [rdx]
0x1400e5da7  mov     rdx, [r15]
0x1400e5daa  mov     [rbp+40h+var_C0], rdx
0x1400e5dae  mov     ecx, [rdx+3Ch]
0x1400e5db1  shr     rcx, 2
0x1400e5db5  and     ecx, 3Fh
0x1400e5db8  mov     rax, [rax+rcx*8]
0x1400e5dbc  mov     [rsp+140h+var_C8], rax
0x1400e5dc1  mov     r12, [rsi+8]
0x1400e5dc5  test    r12, r12
0x1400e5dc8  jz      loc_1400E6342
0x1400e5dce  mov     [r8], r9b
0x1400e5dd1  lea     rax, [rsp+140h+var_D0]
0x1400e5dd6  mov     [rsp+140h+var_118], rax
0x1400e5ddb  mov     r8, r12
0x1400e5dde  mov     eax, [rsi]
0x1400e5de0  or      edx, 0FFFFFFFFh
0x1400e5de3  mov     [rsp+140h+var_D0], r9
0x1400e5de8  mov     rcx, rdi
0x1400e5deb  mov     r9, r14
0x1400e5dee  mov     dword ptr [rsp+140h+var_120], eax
0x1400e5df2  call    ?StartPreparation@VIDMM_GLOBAL@@QEAAXIPEAVVIDMM_DEVICE@@PEAUVIDMM_ALLOC@@W4VIDMM_OPERATION@@PEAPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VIDMM_GLOBAL::StartPreparation(uint,VIDMM_DEVICE *,VIDMM_ALLOC *,VIDMM_OPERATION,VIDMM_PAGING_EXECUTION_CONTEXT * *)
0x1400e5df7  mov     rdx, [r12+20h]
0x1400e5dfc  xor     r10d, r10d
0x1400e5dff  test    rdx, rdx
0x1400e5e02  jnz     loc_1400E5FA6
0x1400e5e08  mov     rcx, rdi; this
0x1400e5e0b  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400e5e10  test    al, al
0x1400e5e12  jnz     loc_1400E5FC2
0x1400e5e18  mov     r13, [rsp+140h+var_D0]
0x1400e5e1d  cmp     [rsi+50h], r10b
0x1400e5e21  jnz     loc_1400E611F
0x1400e5e27  movsxd  r9, dword ptr [rsi]
0x1400e5e2a  mov     eax, 0D1h
0x1400e5e2f  mov     ebx, r10d
0x1400e5e32  mov     dword ptr [rsp+140h+var_D0], ebx
0x1400e5e36  cmp     r9d, eax
0x1400e5e39  jg      loc_1400E6081
0x1400e5e3f  jz      loc_1400E61C4
0x1400e5e45  mov     ecx, r9d
0x1400e5e48  sub     ecx, 71h ; 'q'
0x1400e5e4b  jz      loc_1400E6030
0x1400e5e51  sub     ecx, 6
0x1400e5e54  jz      loc_1400E653C
0x1400e5e5a  sub     ecx, 51h ; 'Q'
0x1400e5e5d  jnz     loc_1400E5F1B
0x1400e5e63  mov     r8, r14; struct VIDMM_ALLOC *
0x1400e5e66  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400e5e69  mov     rcx, rdi; this
0x1400e5e6c  call    ?VidMmOpCloseAllocationCommand@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::VidMmOpCloseAllocationCommand(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *)
0x1400e5e71  mov     r12, [rsp+140h+var_F0]
0x1400e5e76  cmp     byte ptr [r12], 0
0x1400e5e7b  jz      loc_1400E5FF2
0x1400e5e81  lea     rax, [rdi+288h]
0x1400e5e88  xor     r15d, r15d
0x1400e5e8b  mov     [rax+8], rax
0x1400e5e8f  mov     [rax], rax
0x1400e5e92  cmp     [rdi+0C28h], r15d
0x1400e5e99  ja      loc_1400E5FD2
0x1400e5e9f  or      edx, 0FFFFFFFFh; unsigned int
0x1400e5ea2  mov     rcx, rdi; this
0x1400e5ea5  call    ?ResumeSuspendedDevicesForMove@VIDMM_GLOBAL@@QEAAXI@Z; VIDMM_GLOBAL::ResumeSuspendedDevicesForMove(uint)
0x1400e5eaa  mov     rcx, [rdi+30h]; struct VIDMM_PAGING *
0x1400e5eae  xor     eax, eax
0x1400e5eb0  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400e5eb3  mov     [rdi+0C30h], rax
0x1400e5eba  mov     [rdi+0C38h], rax
0x1400e5ec1  mov     [rdi+8], eax
0x1400e5ec4  call    ?VidMmReleasePagingExecutionContext@@YAXPEAUVIDMM_PAGING@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@@Z; VidMmReleasePagingExecutionContext(VIDMM_PAGING *,VIDMM_PAGING_EXECUTION_CONTEXT *)
0x1400e5ec9  cmp     dword ptr [rsi], 0C8h
0x1400e5ecf  jnz     loc_1400E6060
0x1400e5ed5  mov     rcx, [rsi+10h]
0x1400e5ed9  xor     r8d, r8d; Wait
0x1400e5edc  add     rcx, 48h ; 'H'; Event
0x1400e5ee0  xor     edx, edx; Increment
0x1400e5ee2  call    cs:__imp_KeSetEvent
0x1400e5ee9  nop     dword ptr [rax+rax+00h]
0x1400e5eee  mov     [rsi+54h], ebx
0x1400e5ef1  mov     eax, ebx
0x1400e5ef3  mov     rcx, [rbp+40h+var_40]
0x1400e5ef7  xor     rcx, rsp; StackCookie
0x1400e5efa  call    __security_check_cookie
0x1400e5eff  mov     rbx, [rsp+140h+arg_18]
0x1400e5f07  add     rsp, 110h
0x1400e5f0e  pop     r15
0x1400e5f10  pop     r14
0x1400e5f12  pop     r13
0x1400e5f14  pop     r12
0x1400e5f16  pop     rdi
0x1400e5f17  pop     rsi
0x1400e5f18  pop     rbp
0x1400e5f19  retn
0x1400e5f1b  sub     ecx, 3
0x1400e5f1e  jz      loc_1400E647E
0x1400e5f24  sub     ecx, 3
0x1400e5f27  jnz     loc_1400E60FA
0x1400e5f2d  mov     eax, [r15+0B8h]
0x1400e5f34  test    eax, eax
0x1400e5f36  jg      loc_1400E60B6
0x1400e5f3c  mov     rcx, r14; this
0x1400e5f3f  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x1400e5f44  test    al, al
0x1400e5f46  jz      loc_1400E5E71
0x1400e5f4c  mov     rax, [r15+180h]
0x1400e5f53  mov     edx, 2
0x1400e5f58  mov     r12, [rsp+140h+var_F0]
0x1400e5f5d  cmp     [rax+8], dx
0x1400e5f61  jnb     loc_1400E5E76
0x1400e5f67  mov     [rsp+140h+var_100], 0FFFFFFFFFFFFFFFFh
0x1400e5f70  mov     [rsp+140h+var_108], r10d
0x1400e5f75  mov     rax, [rsp+140h+var_E0]
0x1400e5f7a  xor     r9d, r9d
0x1400e5f7d  mov     [rsp+140h+var_110], rax
0x1400e5f82  mov     al, [rbp+40h+arg_30]
0x1400e5f88  mov     [rsp+140h+var_118], r12
0x1400e5f8d  mov     byte ptr [rsp+140h+var_120], al
0x1400e5f91  mov     r8, r14
0x1400e5f94  mov     rdx, r13
0x1400e5f97  mov     rcx, rdi
0x1400e5f9a  call    ?PageInOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@W4VIDMM_PLACEMENT_RESTRICTION@@_NPEA_NPEAPEAU3@I_K@Z; VIDMM_GLOBAL::PageInOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,VIDMM_PLACEMENT_RESTRICTION,bool,bool *,VIDMM_ALLOC * *,uint,unsigned __int64)
0x1400e5f9f  mov     ebx, eax
0x1400e5fa1  jmp     loc_1400E5E76
0x1400e5fa6  cmp     [rdx+0D4h], r10b
0x1400e5fad  jnz     short loc_1400E5FC2
0x1400e5faf  mov     ecx, r10d
0x1400e5fb2  xor     eax, eax
0x1400e5fb4  lock cmpxchg [rdx+0D0h], ecx
0x1400e5fbc  jz      loc_1400E5E08
0x1400e5fc2  mov     dword ptr [rsi+54h], 0C01E0200h
0x1400e5fc9  mov     byte ptr [rsi+50h], 1
0x1400e5fcd  jmp     loc_1400E5E18
0x1400e5fd2  mov     r8d, r15d; unsigned int
0x1400e5fd5  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400e5fd8  mov     rcx, rdi; this
0x1400e5fdb  call    ?EndPreparationOnPhysicalAdapter@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@I@Z; VIDMM_GLOBAL::EndPreparationOnPhysicalAdapter(VIDMM_PAGING_EXECUTION_CONTEXT *,uint)
0x1400e5fe0  inc     r15d
0x1400e5fe3  cmp     r15d, [rdi+0C28h]
0x1400e5fea  jnb     loc_1400E5E9F
0x1400e5ff0  jmp     short loc_1400E5FD2
0x1400e5ff2  mov     rax, [rsi+18h]
0x1400e5ff6  test    rax, rax
0x1400e5ff9  jnz     loc_1400E6795
0x1400e5fff  mov     rax, [rbp+40h+var_90]
0x1400e6003  xor     r9d, r9d; Event
0x1400e6006  mov     [rsp+140h+var_110], rax; struct _VIDSCH_SYNC_OBJECT *
0x1400e600b  or      r8d, 0FFFFFFFFh; unsigned int
0x1400e600f  mov     rax, [rbp+40h+arg_20]
0x1400e6013  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400e6016  mov     [rsp+140h+var_118], rax; unsigned __int64
0x1400e601b  mov     rcx, rdi; this
0x1400e601e  mov     al, [rsp+140h+var_E7]
0x1400e6022  mov     byte ptr [rsp+140h+var_120], al; bool
0x1400e6026  call    ?EndPreparation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@IPEAU_KEVENT@@_N_KPEAU_VIDSCH_SYNC_OBJECT@@@Z; VIDMM_GLOBAL::EndPreparation(VIDMM_PAGING_EXECUTION_CONTEXT *,uint,_KEVENT *,bool,unsigned __int64,_VIDSCH_SYNC_OBJECT *)
0x1400e602b  jmp     loc_1400E5EC9
0x1400e6030  mov     r9, [rsp+140h+var_E0]; struct VIDMM_ALLOC **
0x1400e6035  lea     r8, [rsi+20h]; struct VIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE *
0x1400e6039  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400e603c  mov     rcx, rdi; this
0x1400e603f  call    ?CommitVirtualAddressRangeSystemCommand@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::CommitVirtualAddressRangeSystemCommand(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE *,VIDMM_ALLOC * *)
0x1400e6044  mov     r12, [rsp+140h+var_F0]
0x1400e6049  mov     ebx, eax
0x1400e604b  cmp     eax, 0C000022Dh
0x1400e6050  jnz     loc_1400E5E76
0x1400e6056  mov     byte ptr [r12], 1
0x1400e605b  jmp     loc_1400E5E76
0x1400e6060  cmp     byte ptr [r12], 0
0x1400e6065  jnz     loc_1400E5EEE
0x1400e606b  test    r14, r14
0x1400e606e  jz      loc_1400E5EEE
0x1400e6074  mov     rcx, r14; this
0x1400e6077  call    ?DecrementPagingPacketReferenceCount@VIDMM_ALLOC@@QEAAXXZ; VIDMM_ALLOC::DecrementPagingPacketReferenceCount(void)
0x1400e607c  jmp     loc_1400E5EEE
0x1400e6081  mov     ecx, r9d
0x1400e6084  sub     ecx, 0D2h
0x1400e608a  jz      loc_1400E614F
0x1400e6090  sub     ecx, 1
0x1400e6093  jz      loc_1400E673D
0x1400e6099  sub     ecx, 1
0x1400e609c  jnz     loc_1400E6555
0x1400e60a2  mov     r8d, [rsi+20h]; unsigned int
0x1400e60a6  mov     rdx, r14; struct VIDMM_ALLOC *
0x1400e60a9  mov     rcx, rdi; this
0x1400e60ac  call    ?UpdateAllocationPriority@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@K@Z; VIDMM_GLOBAL::UpdateAllocationPriority(VIDMM_ALLOC *,ulong)
0x1400e60b1  jmp     loc_1400E5E71
0x1400e60b6  mov     rdx, r15
0x1400e60b9  mov     rcx, rdi
0x1400e60bc  call    NeedsApertureForLock
0x1400e60c1  test    al, al
0x1400e60c3  jz      loc_1400E5F3C
0x1400e60c9  mov     eax, [r15+18h]
0x1400e60cd  test    al, 1
0x1400e60cf  jnz     loc_1400E5F3C
0x1400e60d5  mov     ecx, 3
0x1400e60da  call    cs:__imp_WdLogSingleEntry1
0x1400e60e1  nop     dword ptr [rax+rax+00h]
0x1400e60e6  mov     cs:WdLogGlobalForLineNumber, 30AFh
0x1400e60f0  mov     ebx, 0C0000001h
0x1400e60f5  jmp     loc_1400E5E71
0x1400e60fa  sub     ecx, 1
0x1400e60fd  jnz     loc_1400E6384
0x1400e6103  mov     eax, [r14+2B0h]
0x1400e610a  test    eax, eax
0x1400e610c  jz      loc_1400E6458
0x1400e6112  lock dec dword ptr [r14+2BCh]
0x1400e611a  jmp     loc_1400E5E71
0x1400e611f  cmp     dword ptr [rsi], 71h ; 'q'
0x1400e6122  jz      loc_1400E634B
0x1400e6128  mov     ecx, [rsi]
0x1400e612a  lea     eax, [rcx-0CBh]
0x1400e6130  cmp     eax, 0Bh
0x1400e6133  ja      loc_1400E6376
0x1400e6139  mov     edx, 8E9h
0x1400e613e  bt      edx, eax
0x1400e6141  jnb     loc_1400E6376
0x1400e6147  mov     ebx, [rsi+54h]
0x1400e614a  jmp     loc_1400E5E71
0x1400e614f  mov     rax, [r15+180h]
0x1400e6156  mov     rcx, r14; this
0x1400e6159  movzx   r8d, word ptr [rax+8]
0x1400e615e  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x1400e6163  test    al, al
0x1400e6165  jz      loc_1400E5E71
0x1400e616b  mov     r12, [rsp+140h+var_F0]
0x1400e6170  mov     edx, 2
0x1400e6175  cmp     r8w, dx
0x1400e6179  jnb     loc_1400E5E76
0x1400e617f  mov     rax, [rsp+140h+var_E0]
0x1400e6184  xor     r9d, r9d
0x1400e6187  mov     [rsp+140h+var_100], 0FFFFFFFFFFFFFFFFh
0x1400e6190  mov     r8, r14
0x1400e6193  mov     [rsp+140h+var_108], r10d
0x1400e6198  mov     rdx, r13
0x1400e619b  mov     [rsp+140h+var_110], rax
0x1400e61a0  mov     rcx, rdi
0x1400e61a3  mov     al, [rbp+40h+arg_30]
0x1400e61a9  mov     [rsp+140h+var_118], r12
0x1400e61ae  mov     byte ptr [rsp+140h+var_120], al
0x1400e61b2  call    ?PageInOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@W4VIDMM_PLACEMENT_RESTRICTION@@_NPEA_NPEAPEAU3@I_K@Z; VIDMM_GLOBAL::PageInOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,VIDMM_PLACEMENT_RESTRICTION,bool,bool *,VIDMM_ALLOC * *,uint,unsigned __int64)
0x1400e61b7  btr     dword ptr [r15+18h], 1Ah
0x1400e61bd  mov     ebx, eax
0x1400e61bf  jmp     loc_1400E5E76
0x1400e61c4  mov     rax, [rsp+140h+var_E0]
0x1400e61c9  mov     r9b, 1; bool
0x1400e61cc  mov     r12, [rsp+140h+var_F0]
0x1400e61d1  mov     r8, r14; struct VIDMM_ALLOC *
0x1400e61d4  mov     [rsp+140h+var_118], rax; struct VIDMM_ALLOC **
0x1400e61d9  mov     rdx, r13; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400e61dc  mov     rcx, rdi; this
0x1400e61df  mov     [rsp+140h+var_120], r12; bool *
0x1400e61e4  call    ?InitContextAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_NPEA_NPEAPEAU3@@Z; VIDMM_GLOBAL::InitContextAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool,bool *,VIDMM_ALLOC * *)
0x1400e61e9  jmp     loc_1400E5F9F
0x1400e61ee  mov     rax, [r15+180h]
0x1400e61f5  mov     ecx, [rax+10h]
0x1400e61f8  test    ecx, ecx
0x1400e61fa  jnz     loc_1400E62B8
0x1400e6200  mov     rcx, [r15+180h]
0x1400e6207  bt      dword ptr [rcx], 11h
0x1400e620b  jb      loc_1400E62B8
0x1400e6211  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400e6218  cmp     [rax], r10b
0x1400e621b  jz      short loc_1400E623D
0x1400e621d  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400e6224  nop     dword ptr [rax+rax+00h]
0x1400e6229  mov     cs:WdLogGlobalForLineNumber, 305Eh
0x1400e6233  xor     r10d, r10d
0x1400e6236  mov     rcx, [r15+180h]
0x1400e623d  mov     rdx, [rbp+40h+var_C0]
0x1400e6241  mov     eax, [rdx+40h]
0x1400e6244  test    al, 1
  ... truncated ...
```
