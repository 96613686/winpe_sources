# VIDMM_GLOBAL::OpenOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool,DXGALLOCATION *,VIDMM_ALLOC * *)

- ea: `0x1400f24e0`
- end: `0x1400f2eb9`
- name: `?OpenOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_NPEAVDXGALLOCATION@@PEAPEAUVIDMM_ALLOC@@@Z`
- size: `2521`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_DEVICE *@<rdx>, struct VIDMM_GLOBAL_ALLOC *@<r8>, bool@<r9b>, struct DXGALLOCATION *, struct VIDMM_ALLOC **)`
- caller_count: `6`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400bfce0`
- `0x1400c1cdc`
- `0x1400f18cc`
- `0x1400f2168`
- `0x1400f2468`
- `0x14011b2a0`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002bcc0`
- `0x14002bddc`
- `0x14002d8cc`
- `0x14002dab4`
- `0x14002e6c0`
- `0x14002fce8`
- `0x14002fd84`
- `0x140030854`
- `0x1400331b4`
- `0x140059030`
- `0x140059380`
- `0x1400ab994`
- `0x1400ea180`
- `0x1400ea904`
- `0x1400f24e0`
- `0x1400f2ec0`
- `0x1400f2fbc`
- `0x1400ff110`
- `0x1400ff20c`
- `0x140115f30`
- `0x14011e5e4`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400f2e28`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400f2e28`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f2cdb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f2cdb`
- `watchdog!WdLogSingleEntry2` at `0x1400f2bae`
- `watchdog!WdLogSingleEntry2` at `0x1400f2bae`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f272a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f2a14`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f2a41`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f2c0f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f2c49`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f272a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f2a14`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f2a41`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f2c0f`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400f2c49`
- `watchdog!WdLogSingleEntry5` at `0x1400f2b31`
- `watchdog!WdLogSingleEntry5` at `0x1400f2d7c`
- `watchdog!WdLogSingleEntry5` at `0x1400f2b31`
- `watchdog!WdLogSingleEntry5` at `0x1400f2d7c`
- `watchdog!WdLogSingleEntry0` at `0x1400f2571`
- `watchdog!WdLogSingleEntry0` at `0x1400f2571`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f2b12`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f2d57`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f2b02`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f2501`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f253b`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f2a08`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f2a36`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f2c03`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400f2c3e`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_GLOBAL::OpenOneAllocation(
        VIDMM_GLOBAL *this,
        struct VIDMM_PROCESS **a2,
        struct VIDMM_GLOBAL_ALLOC *a3,
        bool a4,
        struct DXGALLOCATION *a5,
        struct VIDMM_ALLOC **a6)
{
  __int64 v6; // rsi
  __int64 v7; // rbx
  struct VIDMM_GLOBAL_ALLOC *v9; // r14
  struct VIDMM_PROCESS **v10; // rdi
  VIDMM_ALLOC *v12; // rax
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // r15
  struct VIDMM_PAGING_QUEUE *v16; // r9
  struct VIDMM_DEVICE *v17; // r8
  struct VIDMM_PROCESS *v18; // rax
  unsigned __int64 v19; // rax
  VIDMM_GLOBAL *v21; // rcx
  _QWORD *v22; // rbx
  __int64 v23; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rax
  struct VIDMM_LOCAL_ALLOC *v26; // rbx
  __int64 v27; // rax
  VIDMM_ALLOC_DEBUG *v28; // rax
  VIDMM_ALLOC *v29; // rax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  unsigned __int64 v34; // r8
  struct VIDMM_LOCAL_ALLOC *v35; // rax
  __int64 v36; // rdi
  int v37; // edx
  char v38; // cl
  struct VIDMM_LOCAL_ALLOC **v39; // rdx
  int Resident; // eax
  __int64 v41; // rcx
  __int64 v42; // rax
  _QWORD *v43; // rdx
  int v44; // eax
  int v45; // ecx
  int v46; // r8d
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rax
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // rax
  int v55; // ecx
  struct VIDMM_PROCESS_ADAPTER_INFO *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rbx
  __int64 v59; // rdi
  unsigned int CurrentProcessId; // eax
  struct VIDMM_PROCESS_ADAPTER_INFO *v61; // [rsp+80h] [rbp-80h] BYREF
  struct VIDMM_LOCAL_ALLOC *v62; // [rsp+88h] [rbp-78h]
  struct _VIDSCH_SYNC_OBJECT **v63; // [rsp+90h] [rbp-70h]
  struct VIDMM_MULTI_ALLOC *v64; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v65; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-58h]
  _BYTE v67[32]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v68[18]; // [rsp+D0h] [rbp-30h] BYREF
  DXGFASTMUTEX *v70; // [rsp+180h] [rbp+80h]
  int v71; // [rsp+180h] [rbp+80h]
  char v72; // [rsp+198h] [rbp+98h]

  v6 = 0;
  v7 = *(_QWORD *)a3;
  v9 = a3;
  v66 = *(_QWORD *)a3;
  v10 = a2;
  if ( g_IsInternalReleaseOrDbg )
  {
    v27 = WdLogNewEntry5_WdTrace(this, a2);
    *(_QWORD *)(v27 + 24) = v9;
    *(_QWORD *)(v27 + 32) = v10;
    WdLogGlobalForLineNumber = 5192;
  }
  *a6 = 0;
  if ( g_IsInternalReleaseOrDbg )
  {
    v28 = (VIDMM_ALLOC_DEBUG *)operator new(824, 858810710, 64);
    if ( !v28 )
      goto LABEL_27;
    v29 = VIDMM_ALLOC_DEBUG::VIDMM_ALLOC_DEBUG(v28);
LABEL_26:
    v6 = (__int64)v29;
LABEL_27:
    if ( !v6 )
      goto LABEL_5;
    *(_BYTE *)(v6 + 36) = *(_BYTE *)(v6 + 36) & 0xFE | ((*((_DWORD *)this + 786) & 0x2000) != 0);
    VIDMM_DEVICE::NotifyAllocationOpened((VIDMM_DEVICE *)v10, (struct VIDMM_ALLOC *)v6);
    v30 = *(_DWORD *)(v7 + 60) ^ *(_DWORD *)(v6 + 32);
    v26 = (struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136);
    v70 = (struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136);
    *(_DWORD *)(v6 + 32) ^= v30 & 0xFC;
    DXGFASTMUTEX::Acquire((struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136));
    if ( *((_BYTE *)v9 + 41) == 1 )
    {
      if ( g_IsInternalReleaseOrDbg )
      {
        *(_QWORD *)(WdLogNewEntry5_WdTrace(v32, v31) + 24) = v9;
        WdLogGlobalForLineNumber = 5241;
      }
      LODWORD(v15) = -1071775482;
      goto LABEL_48;
    }
    v33 = *((unsigned int *)v9 + 8);
    if ( (*((_BYTE *)v9 + 32) & 1) != 0 )
    {
      if ( g_IsInternalReleaseOrDbg )
      {
        *(_QWORD *)(WdLogNewEntry5_WdTrace(v33, 0) + 24) = v9;
        WdLogGlobalForLineNumber = 5254;
      }
      LODWORD(v15) = -1071775470;
      goto LABEL_48;
    }
    v34 = *((_QWORD *)v9 + 6);
    v61 = 0;
    v65 = v34;
    if ( (v33 & 4) != 0 )
      v61 = *(struct VIDMM_PROCESS_ADAPTER_INFO **)(*(_QWORD *)(*(_QWORD *)(v34 + 8) + 32LL)
                                                  + 8LL * *(unsigned int *)(*((_QWORD *)this + 3) + 240LL));
    v35 = VIDMM_GLOBAL::OpenLocalAllocation(this, v9, v10[1], a4);
    v62 = v35;
    v26 = v35;
    if ( !v35 )
    {
      v26 = (struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136);
      LODWORD(v15) = -1071775488;
      goto LABEL_48;
    }
    v36 = v6 + 8;
    v37 = *(_DWORD *)(v6 + 28);
    v63 = (struct _VIDSCH_SYNC_OBJECT **)*((_QWORD *)v9 + 6);
    *(_QWORD *)(v6 + 8) = a2;
    *(_QWORD *)v6 = v35;
    *(_QWORD *)(v6 + 16) = a5;
    *(_QWORD *)(v6 + 96) = *((_QWORD *)v9 + 49);
    v38 = v37 ^ (**((_DWORD **)v9 + 49) >> 26);
    *(_BYTE *)(v6 + 24) = a4;
    *(_DWORD *)(v6 + 28) = v37 ^ v38 & 8;
    if ( a4
      && (**((_DWORD **)v9 + 49) & 0x200000) != 0
      && (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)a5 + 1) + 40LL) + 408LL) & 4) != 0
      && *((_DWORD *)this + 778) > 1u )
    {
      *(_BYTE *)(v6 + 24) = 0;
    }
    *(_QWORD *)(v6 + 680) = 0;
    *(_QWORD *)(v6 + 656) = v6 + 648;
    *(_QWORD *)(v6 + 648) = v6 + 648;
    *(_QWORD *)(v6 + 672) = v6 + 664;
    *(_QWORD *)(v6 + 664) = v6 + 664;
    v39 = (struct VIDMM_LOCAL_ALLOC **)*((_QWORD *)v35 + 5);
    if ( *v39 != (struct VIDMM_LOCAL_ALLOC *)((char *)v35 + 32) )
LABEL_35:
      __fastfail(3u);
    *(_QWORD *)(v6 + 40) = (char *)v35 + 32;
    *(_QWORD *)(v6 + 48) = v39;
    *v39 = (struct VIDMM_LOCAL_ALLOC *)(v6 + 40);
    *((_QWORD *)v35 + 5) = v6 + 40;
    if ( (*((_BYTE *)this + 37224) & 0x20) != 0 )
    {
      if ( (**((_DWORD **)v9 + 49) & 0x10000008) != 0 )
      {
        if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 0x10) != 0 )
        {
          v42 = *((_QWORD *)v9 + 28);
        }
        else
        {
          v41 = *((_QWORD *)v9 + 29);
          v64 = 0;
          v42 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, char, bool, struct VIDMM_MULTI_ALLOC **))(*(_QWORD *)v41 + 56LL))(
                  v41,
                  *((_QWORD *)v9 + 30),
                  0,
                  *(_QWORD *)(v66 + 16),
                  1,
                  a4,
                  &v64);
        }
      }
      else
      {
        v42 = *((_QWORD *)v35 + 2);
      }
      *(_QWORD *)(v6 + 680) = v42;
    }
    DXGFASTMUTEX::Release((struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136));
    if ( (struct _VIDSCH_SYNC_OBJECT **)v65 != v63 )
    {
      v16 = 0;
      if ( v26 != *((struct VIDMM_LOCAL_ALLOC **)v9 + 6) && g_IsInternalRelease )
      {
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 270, 9, 0, 0, 0);
        WdLogGlobalForLineNumber = 227;
        goto LABEL_66;
      }
      if ( !*(_WORD *)(*((_QWORD *)v9 + 49) + 8LL) )
      {
LABEL_9:
        if ( (**((_DWORD **)v9 + 49) & 0x40000000) == 0 )
        {
          v17 = (struct VIDMM_DEVICE *)a2;
          LODWORD(v15) = 0;
          v18 = a2[3];
          if ( !v18
            || (*((_BYTE *)v18 + 1919)
             || *((_DWORD *)v18 + 116) == 2 && *(int *)(*(_QWORD *)(*((_QWORD *)v18 + 2) + 16LL) + 3132LL) >= 2000)
            && (*((_DWORD *)v9 + 6) & 0x2000000) == 0 )
          {
LABEL_13:
            *(_DWORD *)(v6 + 28) |= 0x40u;
            *a6 = (struct VIDMM_ALLOC *)v6;
            if ( (byte_140087201 & 0x10) == 0 )
            {
LABEL_14:
              v19 = *(_QWORD *)(v66 + 16);
              _InterlockedAdd((volatile signed __int32 *)this + 948, 1u);
              _InterlockedAdd64((volatile signed __int64 *)this + 475, v19);
              return (unsigned int)v15;
            }
LABEL_91:
            v53 = *(_QWORD *)(v6 + 16);
            LOBYTE(v71) = (_BYTE)v16;
            v72 = (char)v16;
            v63 = (struct _VIDSCH_SYNC_OBJECT **)v16;
            if ( v53 )
            {
              v71 = *(_DWORD *)(v53 + 16);
              v54 = *(_QWORD *)(v53 + 40);
              if ( v54 )
              {
                v55 = *(_DWORD *)(v54 + 16);
                v63 = *(struct _VIDSCH_SYNC_OBJECT ***)(v54 + 48);
                v72 = v55;
              }
            }
            v65 = *((_QWORD *)v9 + 30);
            if ( (**((_DWORD **)v9 + 49) & 8) != 0 )
              v56 = (struct VIDMM_PROCESS_ADAPTER_INFO *)*((_QWORD *)v9 + 28);
            else
              v56 = (struct VIDMM_PROCESS_ADAPTER_INFO *)*((_QWORD *)v26 + 2);
            v61 = v56;
            if ( v53 && (v57 = *(_QWORD *)(v53 + 40)) != 0 )
            {
              v62 = *(struct VIDMM_LOCAL_ALLOC **)(v57 + 56);
            }
            else
            {
              v62 = v16;
              if ( !v53 )
              {
                v64 = v16;
                v62 = v16;
                goto LABEL_101;
              }
            }
            v64 = *(struct VIDMM_MULTI_ALLOC **)(v53 + 40);
LABEL_101:
            v58 = *((_QWORD *)this + 3);
            v59 = *((_QWORD *)v17 + 3);
            CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
            McTemplateK0ppppppppppppq_EtwWriteTransfer(
              (_DWORD)v64,
              (unsigned int)&EventCreateDeviceAllocation,
              (_DWORD)v63,
              CurrentProcessId,
              v59,
              v58,
              v6,
              (char)v9,
              (char)v64,
              (char)v62,
              v71,
              v72,
              (char)v63,
              (char)v61,
              v65);
            goto LABEL_14;
          }
          v61 = 0;
          v65 = 0;
          v64 = (struct VIDMM_MULTI_ALLOC *)v6;
          v63 = *(struct _VIDSCH_SYNC_OBJECT ***)(32LL * ((*(_DWORD *)(v66 + 60) >> 2) & 0x3F)
                                                + *(_QWORD *)(*(_QWORD *)v36 + 72LL));
          Resident = VIDMM_GLOBAL::MakeResident(
                       this,
                       (struct VIDMM_PAGING_QUEUE *)v63,
                       &v64,
                       1u,
                       0,
                       (unsigned __int64 *)&v61,
                       &v65);
          LODWORD(v15) = Resident;
          if ( Resident == 259 )
          {
            VIDMM_GLOBAL::WaitForFence(this, v63[11], (unsigned __int64)v61);
            v16 = 0;
            LODWORD(v15) = 0;
LABEL_40:
            v17 = (struct VIDMM_DEVICE *)a2;
            goto LABEL_13;
          }
          v16 = 0;
          if ( Resident >= 0 )
            goto LABEL_40;
          goto LABEL_83;
        }
LABEL_66:
        if ( (*((_DWORD *)this + 786) & 2) == 0
          || (**(_DWORD **)(*(_QWORD *)v26 + 392LL) & 0x20000000) == 0
          || v26 != *(struct VIDMM_LOCAL_ALLOC **)(*(_QWORD *)v26 + 48LL) )
        {
          v44 = VIDMM_GLOBAL::PinOneAllocation(
                  this,
                  (struct VIDMM_ALLOC *)v6,
                  0,
                  0,
                  0xFFFFFFFFFFFFFFFFuLL,
                  (unsigned __int64 *)v16);
          v15 = v44;
          if ( v44 >= 0 )
          {
            DXGFASTMUTEX::Acquire((struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136));
            if ( *((_BYTE *)v9 + 41) == 1 )
            {
              if ( g_IsInternalReleaseOrDbg )
              {
                *(_QWORD *)(WdLogNewEntry5_WdTrace(v48, v47) + 24) = v9;
                WdLogGlobalForLineNumber = 5501;
              }
              LODWORD(v15) = -1071775482;
            }
            else
            {
              if ( (*((_BYTE *)v9 + 32) & 1) == 0 )
              {
                DXGFASTMUTEX::Release((struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136));
                v16 = 0;
                goto LABEL_40;
              }
              if ( g_IsInternalReleaseOrDbg )
              {
                *(_QWORD *)(WdLogNewEntry5_WdTrace(0, v47) + 24) = v9;
                WdLogGlobalForLineNumber = 5510;
              }
              LODWORD(v15) = -1071775470;
            }
            v26 = (struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136);
            DXGFASTMUTEX::Release(v70);
            v9 = 0;
            goto LABEL_85;
          }
          _InterlockedAdd(&dword_140087710, 1u);
          WdLogSingleEntry2(6, v6, v44);
          v9 = 0;
          WdLogGlobalForLineNumber = 5482;
          DxgkLogInternalTriageEvent(
            v45,
            262145,
            v46,
            (unsigned int)L"Couldn't allocate resources for allocation 0x%p, NtStatus=0x%08X.\n",
            v6,
            v15,
            0,
            0);
LABEL_84:
          v26 = v70;
LABEL_85:
          if ( (*((_BYTE *)this + 37225) & 0x10) != 0 )
          {
            v49 = *(_QWORD *)this;
            *(_DWORD *)(v6 + 32) |= 1u;
            VidMmQueueWorkerThreadWorkItem(v49, TerminateWorkItemCB, v6, 1);
          }
          else
          {
            memset(v68, 0, 0x58u);
            LODWORD(v68[0]) = 200;
            v68[2] = v6;
            v52 = VIDMM_GLOBAL::QueueDeferredCommand(
                    this,
                    *(struct VIDMM_PAGING_QUEUE **)(32LL * ((*(_DWORD *)(v66 + 60) >> 2) & 0x3F)
                                                  + *(_QWORD *)(*(_QWORD *)v36 + 72LL)),
                    (struct _VIDMM_DEFERRED_COMMAND *)v68,
                    1,
                    0);
            if ( v52 < 0 )
            {
              g_DxgMmsBugcheckExportIndex = 1;
              WdLogSingleEntry5(0, 270, 5, 200, v52, 0);
              WdLogGlobalForLineNumber = 227;
              goto LABEL_91;
            }
          }
          KeWaitForSingleObject((PVOID)(v6 + 72), Executive, 0, 0, 0);
          DXGFASTMUTEX::Acquire(v26);
          v50 = v6 + 40;
          v51 = *(_QWORD *)(v6 + 40);
          if ( v51 )
          {
            if ( *(_QWORD *)(v51 + 8) != v50 )
              goto LABEL_35;
            v43 = *(_QWORD **)(v6 + 48);
            if ( *v43 != v50 )
              goto LABEL_35;
            *v43 = v51;
            *(_QWORD *)(v51 + 8) = v43;
          }
          VIDMM_GLOBAL::CloseLocalAllocation(this, v62, 1);
          v10 = a2;
LABEL_48:
          VIDMM_DEVICE::NotifyAllocationClosed((VIDMM_DEVICE *)v10, (struct VIDMM_ALLOC *)v6);
          operator delete((void *)v6);
          DXGFASTMUTEX::Release(v26);
          return (unsigned int)v15;
        }
        LODWORD(v15) = -1071775487;
LABEL_83:
        v9 = 0;
        goto LABEL_84;
      }
      DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
        (DXGAUTOPUSHLOCKEXCLUSIVE *)v67,
        (VIDMM_GLOBAL *)((char *)this + 36408));
      v22 = (_QWORD *)((char *)v9 + 288);
      if ( *((_QWORD *)v9 + 36) )
        VIDMM_GLOBAL::RemoveAllocationFromDecommitList(v21, v9, v61);
      if ( (*((_BYTE *)v9 + 32) & 0x60) == 0x60 )
      {
        v23 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v62 + 1) + 32LL)
                        + 8LL * *(unsigned int *)(*((_QWORD *)this + 3) + 240LL));
        v24 = *(_QWORD **)(v23 + 96);
        v25 = v23 + 88;
        if ( *v24 != v25 )
          goto LABEL_35;
        *v22 = v25;
        *((_QWORD *)v9 + 37) = v24;
        *v24 = v22;
        *(_QWORD *)(v25 + 8) = v22;
      }
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v67);
      v26 = v62;
    }
    v16 = 0;
    goto LABEL_9;
  }
  v12 = (VIDMM_ALLOC *)operator new(776, 858810710, 64);
  if ( v12 )
  {
    v29 = VIDMM_ALLOC::VIDMM_ALLOC(v12);
    goto LABEL_26;
  }
LABEL_5:
  _InterlockedAdd(&dword_140087688, 1u);
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 5215;
  DxgkLogInternalTriageEvent(
    v13,
    262145,
    v14,
    (unsigned int)L"Couldn't allocate memory for allocation.\n",
    5215,
    v6,
    v6,
    v6);
  LODWORD(v15) = -1073741801;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400f24e0  mov     [rsp-8+arg_0], rbx
0x1400f24e5  mov     [rsp-8+arg_8], rdx
0x1400f24ea  push    rbp
0x1400f24eb  push    rsi
0x1400f24ec  push    rdi
0x1400f24ed  push    r12
0x1400f24ef  push    r13
0x1400f24f1  push    r14
0x1400f24f3  push    r15
0x1400f24f5  lea     rbp, [rsp-30h]
0x1400f24fa  sub     rsp, 130h
0x1400f2501  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400f2508  xor     esi, esi
0x1400f250a  mov     rbx, [r8]
0x1400f250d  mov     r15b, r9b
0x1400f2510  mov     r14, r8
0x1400f2513  mov     [rbp+60h+var_B8], rbx
0x1400f2517  mov     rdi, rdx
0x1400f251a  mov     r13, rcx
0x1400f251d  cmp     [rax], sil
0x1400f2520  jnz     loc_1400F272A
0x1400f2526  mov     rax, [rbp+60h+arg_28]
0x1400f252d  mov     edx, 33306956h
0x1400f2532  mov     r8d, 40h ; '@'
0x1400f2538  mov     [rax], rsi
0x1400f253b  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400f2542  cmp     [rax], sil
0x1400f2545  jnz     loc_1400F274D
0x1400f254b  mov     ecx, 308h
0x1400f2550  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400f2555  test    rax, rax
0x1400f2558  jnz     loc_1400F29FB
0x1400f255e  mov     r12d, 1
0x1400f2564  lock add cs:dword_140087688, r12d
0x1400f256c  lea     ecx, [r12+5]
0x1400f2571  call    cs:__imp_WdLogSingleEntry0
0x1400f2578  nop     dword ptr [rax+rax+00h]
0x1400f257d  mov     [rsp+160h+var_128], rsi
0x1400f2582  lea     r9, aCouldnTAllocat_28; "Couldn't allocate memory for allocation"...
0x1400f2589  mov     eax, 145Fh
0x1400f258e  mov     [rsp+160h+var_130], rsi
0x1400f2593  mov     [rsp+160h+var_138], rsi
0x1400f2598  mov     edx, 40001h
0x1400f259d  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f25a3  mov     [rsp+160h+Timeout], rax
0x1400f25a8  call    DxgkLogInternalTriageEvent
0x1400f25ad  mov     r15d, 0C0000017h
0x1400f25b3  jmp     loc_1400F266D
0x1400f25b8  lea     rax, [rsi+28h]
0x1400f25bc  mov     [rax], rcx
0x1400f25bf  mov     [rax+8], rdx
0x1400f25c3  mov     [rdx], rax
0x1400f25c6  mov     [rcx+8], rax
0x1400f25ca  test    byte ptr [r13+9168h], 20h
0x1400f25d2  jnz     loc_1400F2ADA
0x1400f25d8  lea     rcx, [r14+88h]; this
0x1400f25df  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400f25e4  mov     rax, [rbp+60h+var_D0]
0x1400f25e8  cmp     [rbp+60h+var_C0], rax
0x1400f25ec  jnz     loc_1400F268C
0x1400f25f2  xor     r9d, r9d
0x1400f25f5  mov     rax, [r14+188h]
0x1400f25fc  test    dword ptr [rax], 40000000h
0x1400f2602  jnz     loc_1400F2B47
0x1400f2608  mov     r8, [rbp+60h+arg_8]
0x1400f260c  mov     r15d, r9d
0x1400f260f  mov     rax, [r8+18h]
0x1400f2613  test    rax, rax
0x1400f2616  jz      short loc_1400F2633
0x1400f2618  cmp     [rax+77Fh], r9b
0x1400f261f  jz      loc_1400F28A7
0x1400f2625  test    dword ptr [r14+18h], 2000000h
0x1400f262d  jnz     loc_1400F28C8
0x1400f2633  mov     rax, [rbp+60h+arg_28]
0x1400f263a  or      dword ptr [rsi+1Ch], 40h
0x1400f263e  mov     [rax], rsi
0x1400f2641  mov     al, cs:byte_140087201
0x1400f2647  and     al, 10h
0x1400f2649  mov     byte ptr [rbp+60h+arg_28], al
0x1400f264f  jnz     loc_1400F2D92
0x1400f2655  mov     rax, [rbp+60h+var_B8]
0x1400f2659  mov     rax, [rax+10h]
0x1400f265d  lock add [r13+0ED0h], r12d
0x1400f2665  lock add [r13+0ED8h], rax
0x1400f266d  mov     rbx, [rsp+160h+arg_0]
0x1400f2675  mov     eax, r15d
0x1400f2678  add     rsp, 130h
0x1400f267f  pop     r15
0x1400f2681  pop     r14
0x1400f2683  pop     r13
0x1400f2685  pop     r12
0x1400f2687  pop     rdi
0x1400f2688  pop     rsi
0x1400f2689  pop     rbp
0x1400f268a  retn
0x1400f268c  xor     r9d, r9d
0x1400f268f  cmp     rbx, [r14+30h]
0x1400f2693  jnz     loc_1400F2B02
0x1400f2699  mov     rax, [r14+188h]
0x1400f26a0  cmp     [rax+8], r9w
0x1400f26a5  jz      loc_1400F25F5
0x1400f26ab  lea     rdx, [r13+8E38h]; struct DXGPUSHLOCK *
0x1400f26b2  lea     rcx, [rbp+60h+var_B0]; this
0x1400f26b6  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1400f26bb  lea     rbx, [r14+120h]
0x1400f26c2  cmp     qword ptr [rbx], 0
0x1400f26c6  jz      short loc_1400F26D4
0x1400f26c8  mov     r8, [rbp+60h+var_E0]; struct VIDMM_PROCESS_ADAPTER_INFO *
0x1400f26cc  mov     rdx, r14; struct VIDMM_GLOBAL_ALLOC *
0x1400f26cf  call    ?RemoveAllocationFromDecommitList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_PROCESS_ADAPTER_INFO@@@Z; VIDMM_GLOBAL::RemoveAllocationFromDecommitList(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS_ADAPTER_INFO *)
0x1400f26d4  mov     eax, [r14+20h]
0x1400f26d8  and     eax, 60h
0x1400f26db  cmp     al, 60h ; '`'
0x1400f26dd  jnz     short loc_1400F2718
0x1400f26df  mov     rax, [r13+18h]
0x1400f26e3  mov     edx, [rax+0F0h]
0x1400f26e9  mov     rax, [rbp+60h+var_D8]
0x1400f26ed  mov     rax, [rax+8]
0x1400f26f1  mov     rcx, [rax+20h]
0x1400f26f5  mov     rax, [rcx+rdx*8]
0x1400f26f9  mov     rcx, [rax+60h]
0x1400f26fd  add     rax, 58h ; 'X'
0x1400f2701  cmp     [rcx], rax
0x1400f2704  jnz     loc_1400F28A0
0x1400f270a  mov     [rbx], rax
0x1400f270d  mov     [rbx+8], rcx
0x1400f2711  mov     [rcx], rbx
0x1400f2714  mov     [rax+8], rbx
0x1400f2718  lea     rcx, [rbp+60h+var_B0]; this
0x1400f271c  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400f2721  mov     rbx, [rbp+60h+var_D8]
0x1400f2725  jmp     loc_1400F25F2
0x1400f272a  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400f2731  nop     dword ptr [rax+rax+00h]
0x1400f2736  mov     [rax+18h], r14
0x1400f273a  mov     [rax+20h], rdi
0x1400f273e  mov     cs:WdLogGlobalForLineNumber, 1448h
0x1400f2748  jmp     loc_1400F2526
0x1400f274d  mov     ecx, 338h
0x1400f2752  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400f2757  test    rax, rax
0x1400f275a  jz      short loc_1400F2767
0x1400f275c  mov     rcx, rax; this
0x1400f275f  call    ??0VIDMM_ALLOC_DEBUG@@QEAA@XZ; VIDMM_ALLOC_DEBUG::VIDMM_ALLOC_DEBUG(void)
0x1400f2764  mov     rsi, rax
0x1400f2767  test    rsi, rsi
0x1400f276a  jz      loc_1400F255E
0x1400f2770  mov     ecx, [r13+0C48h]
0x1400f2777  mov     r12d, 1
0x1400f277d  mov     al, [rsi+24h]
0x1400f2780  mov     rdx, rsi; struct VIDMM_ALLOC *
0x1400f2783  shr     ecx, 0Dh
0x1400f2786  and     al, 0FEh
0x1400f2788  and     cl, r12b
0x1400f278b  or      cl, al
0x1400f278d  mov     [rsi+24h], cl
0x1400f2790  mov     rcx, rdi; this
0x1400f2793  call    ?NotifyAllocationOpened@VIDMM_DEVICE@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_DEVICE::NotifyAllocationOpened(VIDMM_ALLOC *)
0x1400f2798  mov     ecx, [rsi+20h]
0x1400f279b  mov     eax, ecx
0x1400f279d  xor     eax, [rbx+3Ch]
0x1400f27a0  lea     rbx, [r14+88h]
0x1400f27a7  and     eax, 0FCh
0x1400f27ac  mov     [rbp+60h+arg_10], rbx
0x1400f27b3  xor     eax, ecx
0x1400f27b5  mov     rcx, rbx; this
0x1400f27b8  mov     [rsi+20h], eax
0x1400f27bb  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1400f27c0  cmp     [r14+29h], r12b
0x1400f27c4  jz      loc_1400F2A08
0x1400f27ca  mov     ecx, [r14+20h]
0x1400f27ce  xor     edx, edx
0x1400f27d0  mov     eax, ecx
0x1400f27d2  and     eax, r12d
0x1400f27d5  test    al, al
0x1400f27d7  jnz     loc_1400F2A36
0x1400f27dd  mov     r8, [r14+30h]
0x1400f27e1  shr     ecx, 2
0x1400f27e4  mov     [rbp+60h+var_E0], rdx
0x1400f27e8  mov     [rbp+60h+var_C0], r8
0x1400f27ec  test    r12b, cl
0x1400f27ef  jnz     loc_1400F2A66
0x1400f27f5  mov     r8, [rdi+8]; struct VIDMM_PROCESS *
0x1400f27f9  mov     r9b, r15b; bool
0x1400f27fc  mov     rdx, r14; struct VIDMM_GLOBAL_ALLOC *
0x1400f27ff  mov     rcx, r13; this
0x1400f2802  call    ?OpenLocalAllocation@VIDMM_GLOBAL@@QEAAPEAUVIDMM_LOCAL_ALLOC@@PEAUVIDMM_GLOBAL_ALLOC@@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_GLOBAL::OpenLocalAllocation(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS *,bool)
0x1400f2807  xor     r9d, r9d
0x1400f280a  mov     [rbp+60h+var_D8], rax
0x1400f280e  mov     rbx, rax
0x1400f2811  test    rax, rax
0x1400f2814  jz      loc_1400F2A85
0x1400f281a  mov     rax, [r14+30h]
0x1400f281e  lea     rdi, [rsi+8]
0x1400f2822  mov     edx, [rsi+1Ch]
0x1400f2825  mov     r8, [rbp+60h+arg_20]
0x1400f282c  mov     [rbp+60h+var_D0], rax
0x1400f2830  mov     rax, [rbp+60h+arg_8]
0x1400f2834  mov     [rdi], rax
0x1400f2837  mov     [rsi], rbx
0x1400f283a  mov     [rsi+10h], r8
0x1400f283e  mov     rax, [r14+188h]
0x1400f2845  mov     [rsi+60h], rax
0x1400f2849  mov     rax, [r14+188h]
0x1400f2850  mov     ecx, [rax]
0x1400f2852  shr     ecx, 1Ah
0x1400f2855  xor     ecx, edx
0x1400f2857  mov     [rsi+18h], r15b
0x1400f285b  and     ecx, 8
0x1400f285e  xor     ecx, edx
0x1400f2860  mov     [rsi+1Ch], ecx
0x1400f2863  test    r15b, r15b
0x1400f2866  jnz     loc_1400F2A97
0x1400f286c  lea     rax, [rsi+288h]
0x1400f2873  mov     [rsi+2A8h], r9
0x1400f287a  mov     [rax+8], rax
0x1400f287e  mov     [rax], rax
0x1400f2881  lea     rax, [rsi+298h]
0x1400f2888  lea     rcx, [rbx+20h]
0x1400f288c  mov     [rax+8], rax
0x1400f2890  mov     [rax], rax
0x1400f2893  mov     rdx, [rcx+8]
0x1400f2897  cmp     [rdx], rcx
0x1400f289a  jz      loc_1400F25B8
0x1400f28a0  mov     ecx, 3
0x1400f28a5  int     29h; Win8: RtlFailFast(ecx)
0x1400f28a7  cmp     dword ptr [rax+1D0h], 2
0x1400f28ae  jnz     short loc_1400F28C8
0x1400f28b0  mov     rax, [rax+10h]
0x1400f28b4  mov     rcx, [rax+10h]
0x1400f28b8  cmp     dword ptr [rcx+0C3Ch], 7D0h
0x1400f28c2  jge     loc_1400F2625
0x1400f28c8  mov     rax, [rbp+60h+var_B8]
0x1400f28cc  lea     r8, [rbp+60h+var_C8]; struct VIDMM_MULTI_ALLOC **
0x1400f28d0  mov     [rbp+60h+var_E0], r9
0x1400f28d4  mov     [rbp+60h+var_C0], r9
0x1400f28d8  mov     [rbp+60h+var_C8], rsi
0x1400f28dc  mov     edx, [rax+3Ch]
0x1400f28df  mov     rax, [rdi]
0x1400f28e2  shr     rdx, 2
0x1400f28e6  and     edx, 3Fh
0x1400f28e9  shl     rdx, 5
0x1400f28ed  mov     rcx, [rax+48h]
0x1400f28f1  mov     rax, [rdx+rcx]
0x1400f28f5  lea     rcx, [rbp+60h+var_C0]
0x1400f28f9  mov     [rsp+160h+var_130], rcx; unsigned __int64 *
0x1400f28fe  mov     rdx, rax; struct VIDMM_PAGING_QUEUE *
0x1400f2901  lea     rcx, [rbp+60h+var_E0]
0x1400f2905  mov     [rbp+60h+var_D0], rax
0x1400f2909  mov     [rsp+160h+var_138], rcx; unsigned __int64 *
0x1400f290e  mov     rcx, r13; this
0x1400f2911  mov     dword ptr [rsp+160h+Timeout], r9d; unsigned int
0x1400f2916  mov     r9, r12; unsigned __int64
0x1400f2919  call    ?MakeResident@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAPEAUVIDMM_MULTI_ALLOC@@_KKPEA_K3@Z; VIDMM_GLOBAL::MakeResident(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC * *,unsigned __int64,ulong,unsigned __int64 *,unsigned __int64 *)
0x1400f291e  mov     r15d, eax
0x1400f2921  cmp     eax, 103h
0x1400f2926  jnz     loc_1400F2C91
0x1400f292c  mov     rdx, [rbp+60h+var_D0]
0x1400f2930  mov     rcx, r13; this
0x1400f2933  mov     r8, [rbp+60h+var_E0]; unsigned __int64
0x1400f2937  mov     rdx, [rdx+58h]; struct _VIDSCH_SYNC_OBJECT *
0x1400f293b  call    ?WaitForFence@VIDMM_GLOBAL@@QEAAXPEAU_VIDSCH_SYNC_OBJECT@@_K@Z; VIDMM_GLOBAL::WaitForFence(_VIDSCH_SYNC_OBJECT *,unsigned __int64)
0x1400f2940  xor     r9d, r9d
0x1400f2943  mov     r15d, r9d
0x1400f2946  mov     r8, [rbp+60h+arg_8]
0x1400f294a  jmp     loc_1400F2633
0x1400f294f  mov     rax, [r13+18h]
0x1400f2953  mov     ecx, [rax+1BCh]
0x1400f2959  test    cl, 10h
0x1400f295c  jnz     loc_1400F2AF6
0x1400f2962  mov     rcx, [r14+0E8h]
0x1400f2969  lea     rdx, [rbp+60h+var_C8]
0x1400f296d  mov     [rbp+60h+var_C8], r9
0x1400f2971  xor     r8d, r8d
0x1400f2974  mov     r9, [rbp+60h+var_B8]
0x1400f2978  mov     [rsp+160h+var_130], rdx
0x1400f297d  mov     rax, [rcx]
0x1400f2980  mov     rdx, [r14+0F0h]
0x1400f2987  mov     r9, [r9+10h]
0x1400f298b  mov     byte ptr [rsp+160h+var_138], r15b
0x1400f2990  mov     rax, [rax+38h]
0x1400f2994  mov     byte ptr [rsp+160h+Timeout], r12b
0x1400f2999  call    _guard_dispatch_icall
0x1400f299e  mov     [rsi+2A8h], rax
0x1400f29a5  jmp     loc_1400F25D8
0x1400f29aa  cmp     [rax+8], rcx
0x1400f29ae  jnz     loc_1400F28A0
0x1400f29b4  mov     rdx, [rcx+8]
0x1400f29b8  cmp     [rdx], rcx
0x1400f29bb  jnz     loc_1400F28A0
0x1400f29c1  mov     [rdx], rax
0x1400f29c4  mov     [rax+8], rdx
0x1400f29c8  mov     rdx, [rbp+60h+var_D8]; struct VIDMM_LOCAL_ALLOC *
0x1400f29cc  mov     r8b, r12b; bool
0x1400f29cf  mov     rcx, r13; this
0x1400f29d2  call    ?CloseLocalAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_N@Z; VIDMM_GLOBAL::CloseLocalAllocation(VIDMM_LOCAL_ALLOC *,bool)
0x1400f29d7  mov     rdi, [rbp+60h+arg_8]
0x1400f29db  mov     rdx, rsi; struct VIDMM_ALLOC *
0x1400f29de  mov     rcx, rdi; this
0x1400f29e1  call    ?NotifyAllocationClosed@VIDMM_DEVICE@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_DEVICE::NotifyAllocationClosed(VIDMM_ALLOC *)
  ... truncated ...
```
