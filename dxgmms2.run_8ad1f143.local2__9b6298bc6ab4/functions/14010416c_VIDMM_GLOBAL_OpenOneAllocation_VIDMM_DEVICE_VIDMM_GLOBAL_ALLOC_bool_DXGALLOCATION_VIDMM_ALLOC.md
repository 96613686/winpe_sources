# VIDMM_GLOBAL::OpenOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool,DXGALLOCATION *,VIDMM_ALLOC * *)

- ea: `0x14010416c`
- end: `0x140104b45`
- name: `?OpenOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_NPEAVDXGALLOCATION@@PEAPEAUVIDMM_ALLOC@@@Z`
- size: `2521`
- prototype: `__int64 __usercall@<rax>(VIDMM_GLOBAL *__hidden this@<rcx>, struct VIDMM_DEVICE *@<rdx>, struct VIDMM_GLOBAL_ALLOC *@<r8>, bool@<r9b>, struct DXGALLOCATION *, struct VIDMM_ALLOC **)`
- caller_count: `6`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400bc240`
- `0x1400bdbf8`
- `0x140103bfc`
- `0x1401040f4`
- `0x140105510`
- `0x1401177a0`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14002ec00`
- `0x14002ed1c`
- `0x14002fbac`
- `0x14002fd94`
- `0x140030ae0`
- `0x140031f1c`
- `0x140031fb8`
- `0x140032a04`
- `0x1400348c4`
- `0x140058760`
- `0x140058ac0`
- `0x1400aa854`
- `0x1400e1d30`
- `0x1400e2504`
- `0x1400e8a34`
- `0x1400e8b30`
- `0x14010416c`
- `0x140104b4c`
- `0x140104c48`
- `0x140113140`
- `0x14011ab54`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140104ab4`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140104ab4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140104967`
- `ntoskrnl!KeWaitForSingleObject` at `0x140104967`
- `watchdog!WdLogSingleEntry2` at `0x14010483a`
- `watchdog!WdLogSingleEntry2` at `0x14010483a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401043b6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401046a0`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401046cd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010489b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401048d5`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401043b6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401046a0`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401046cd`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14010489b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401048d5`
- `watchdog!WdLogSingleEntry5` at `0x1401047bd`
- `watchdog!WdLogSingleEntry5` at `0x140104a08`
- `watchdog!WdLogSingleEntry5` at `0x1401047bd`
- `watchdog!WdLogSingleEntry5` at `0x140104a08`
- `watchdog!WdLogSingleEntry0` at `0x1401041fd`
- `watchdog!WdLogSingleEntry0` at `0x1401041fd`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14010479e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1401049e3`
- `dxgkrnl!g_IsInternalRelease` at `0x14010478e`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010418d`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1401041c7`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140104694`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1401046c2`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14010488f`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1401048ca`

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
  __int64 v52; // rdx
  __int64 v53; // rax
  int v54; // ecx
  struct VIDMM_PROCESS_ADAPTER_INFO *v55; // rax
  __int64 v56; // rax
  __int64 v57; // rbx
  __int64 v58; // rdi
  unsigned int CurrentProcessId; // eax
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v61; // [rsp+28h] [rbp-D8h]
  struct VIDMM_PROCESS_ADAPTER_INFO *v62; // [rsp+80h] [rbp-80h] BYREF
  struct VIDMM_LOCAL_ALLOC *v63; // [rsp+88h] [rbp-78h]
  struct _VIDSCH_SYNC_OBJECT **v64; // [rsp+90h] [rbp-70h]
  struct VIDMM_MULTI_ALLOC *v65; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v66; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-58h]
  _BYTE v68[32]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v69[18]; // [rsp+D0h] [rbp-30h] BYREF
  DXGFASTMUTEX *v71; // [rsp+180h] [rbp+80h]
  int v72; // [rsp+180h] [rbp+80h]
  char v73; // [rsp+198h] [rbp+98h]

  v6 = 0;
  v7 = *(_QWORD *)a3;
  v9 = a3;
  v67 = *(_QWORD *)a3;
  v10 = a2;
  if ( g_IsInternalReleaseOrDbg )
  {
    v27 = WdLogNewEntry5_WdTrace(this, a2);
    *(_QWORD *)(v27 + 24) = v9;
    *(_QWORD *)(v27 + 32) = v10;
    WdLogGlobalForLineNumber = 5051;
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
    v71 = (struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136);
    *(_DWORD *)(v6 + 32) ^= v30 & 0xFC;
    DXGFASTMUTEX::Acquire((struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136));
    if ( *((_BYTE *)v9 + 41) == 1 )
    {
      if ( g_IsInternalReleaseOrDbg )
      {
        *(_QWORD *)(WdLogNewEntry5_WdTrace(v32, v31) + 24) = v9;
        WdLogGlobalForLineNumber = 5100;
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
        WdLogGlobalForLineNumber = 5113;
      }
      LODWORD(v15) = -1071775470;
      goto LABEL_48;
    }
    v34 = *((_QWORD *)v9 + 6);
    v62 = 0;
    v66 = v34;
    if ( (v33 & 4) != 0 )
      v62 = *(struct VIDMM_PROCESS_ADAPTER_INFO **)(*(_QWORD *)(*(_QWORD *)(v34 + 8) + 32LL)
                                                  + 8LL * *(unsigned int *)(*((_QWORD *)this + 3) + 240LL));
    v35 = VIDMM_GLOBAL::OpenLocalAllocation(this, v9, v10[1], a4);
    v63 = v35;
    v26 = v35;
    if ( !v35 )
    {
      v26 = (struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136);
      LODWORD(v15) = -1071775488;
      goto LABEL_48;
    }
    v36 = v6 + 8;
    v37 = *(_DWORD *)(v6 + 28);
    v64 = (struct _VIDSCH_SYNC_OBJECT **)*((_QWORD *)v9 + 6);
    *(_QWORD *)(v6 + 8) = a2;
    *(_QWORD *)v6 = v35;
    *(_QWORD *)(v6 + 16) = a5;
    *(_QWORD *)(v6 + 96) = *((_QWORD *)v9 + 48);
    v38 = v37 ^ (**((_DWORD **)v9 + 48) >> 26);
    *(_BYTE *)(v6 + 24) = a4;
    *(_DWORD *)(v6 + 28) = v37 ^ v38 & 8;
    if ( a4
      && (**((_DWORD **)v9 + 48) & 0x200000) != 0
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
      if ( (**((_DWORD **)v9 + 48) & 0x10000008) != 0 )
      {
        if ( (*(_DWORD *)(*((_QWORD *)this + 3) + 444LL) & 0x10) != 0 )
        {
          v42 = *((_QWORD *)v9 + 28);
        }
        else
        {
          v41 = *((_QWORD *)v9 + 29);
          v65 = 0;
          v42 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, char, bool, struct VIDMM_MULTI_ALLOC **))(*(_QWORD *)v41 + 56LL))(
                  v41,
                  *((_QWORD *)v9 + 30),
                  0,
                  *(_QWORD *)(v67 + 16),
                  1,
                  a4,
                  &v65);
        }
      }
      else
      {
        v42 = *((_QWORD *)v35 + 2);
      }
      *(_QWORD *)(v6 + 680) = v42;
    }
    DXGFASTMUTEX::Release((struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136));
    if ( (struct _VIDSCH_SYNC_OBJECT **)v66 != v64 )
    {
      v16 = 0;
      if ( v26 != *((struct VIDMM_LOCAL_ALLOC **)v9 + 6) && g_IsInternalRelease )
      {
        g_DxgMmsBugcheckExportIndex = 1;
        v61 = 0;
        Timeout = 0;
        WdLogSingleEntry5(0, 270, 9);
        WdLogGlobalForLineNumber = 222;
        goto LABEL_66;
      }
      if ( !*(_WORD *)(*((_QWORD *)v9 + 48) + 8LL) )
      {
LABEL_9:
        if ( (**((_DWORD **)v9 + 48) & 0x40000000) == 0 )
        {
          v17 = (struct VIDMM_DEVICE *)a2;
          LODWORD(v15) = 0;
          v18 = a2[3];
          if ( !v18
            || (*((_BYTE *)v18 + 1919)
             || *((_DWORD *)v18 + 116) == 2 && *(int *)(*(_QWORD *)(*((_QWORD *)v18 + 2) + 16LL) + 3116LL) >= 2000)
            && (*((_DWORD *)v9 + 6) & 0x2000000) == 0 )
          {
LABEL_13:
            *(_DWORD *)(v6 + 28) |= 0x40u;
            *a6 = (struct VIDMM_ALLOC *)v6;
            if ( (byte_140086201 & 0x10) == 0 )
            {
LABEL_14:
              v19 = *(_QWORD *)(v67 + 16);
              _InterlockedAdd((volatile signed __int32 *)this + 948, 1u);
              _InterlockedAdd64((volatile signed __int64 *)this + 475, v19);
              return (unsigned int)v15;
            }
LABEL_91:
            v52 = *(_QWORD *)(v6 + 16);
            LOBYTE(v72) = (_BYTE)v16;
            v73 = (char)v16;
            v64 = (struct _VIDSCH_SYNC_OBJECT **)v16;
            if ( v52 )
            {
              v72 = *(_DWORD *)(v52 + 16);
              v53 = *(_QWORD *)(v52 + 40);
              if ( v53 )
              {
                v54 = *(_DWORD *)(v53 + 16);
                v64 = *(struct _VIDSCH_SYNC_OBJECT ***)(v53 + 48);
                v73 = v54;
              }
            }
            v66 = *((_QWORD *)v9 + 30);
            if ( (**((_DWORD **)v9 + 48) & 8) != 0 )
              v55 = (struct VIDMM_PROCESS_ADAPTER_INFO *)*((_QWORD *)v9 + 28);
            else
              v55 = (struct VIDMM_PROCESS_ADAPTER_INFO *)*((_QWORD *)v26 + 2);
            v62 = v55;
            if ( v52 && (v56 = *(_QWORD *)(v52 + 40)) != 0 )
            {
              v63 = *(struct VIDMM_LOCAL_ALLOC **)(v56 + 56);
            }
            else
            {
              v63 = v16;
              if ( !v52 )
              {
                v65 = v16;
                v63 = v16;
                goto LABEL_101;
              }
            }
            v65 = *(struct VIDMM_MULTI_ALLOC **)(v52 + 40);
LABEL_101:
            v57 = *((_QWORD *)this + 3);
            v58 = *((_QWORD *)v17 + 3);
            CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
            McTemplateK0ppppppppppppq_EtwWriteTransfer(
              (_DWORD)v65,
              (unsigned int)EventCreateDeviceAllocation,
              (_DWORD)v64,
              CurrentProcessId,
              v58,
              v57,
              v6,
              (char)v9,
              (char)v65,
              (char)v63,
              v72,
              v73,
              (char)v64,
              (char)v62,
              v66);
            goto LABEL_14;
          }
          v62 = 0;
          v66 = 0;
          v65 = (struct VIDMM_MULTI_ALLOC *)v6;
          v64 = *(struct _VIDSCH_SYNC_OBJECT ***)(32LL * ((*(_DWORD *)(v67 + 60) >> 2) & 0x3F)
                                                + *(_QWORD *)(*(_QWORD *)v36 + 72LL));
          Resident = VIDMM_GLOBAL::MakeResident(
                       this,
                       (struct VIDMM_PAGING_QUEUE *)v64,
                       &v65,
                       1u,
                       0,
                       (unsigned __int64 *)&v62,
                       &v66);
          LODWORD(v15) = Resident;
          if ( Resident == 259 )
          {
            VIDMM_GLOBAL::WaitForFence(this, v64[11], (unsigned __int64)v62);
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
          || (**(_DWORD **)(*(_QWORD *)v26 + 384LL) & 0x20000000) == 0
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
                WdLogGlobalForLineNumber = 5360;
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
                WdLogGlobalForLineNumber = 5369;
              }
              LODWORD(v15) = -1071775470;
            }
            v26 = (struct VIDMM_GLOBAL_ALLOC *)((char *)v9 + 136);
            DXGFASTMUTEX::Release(v71);
            v9 = 0;
            goto LABEL_85;
          }
          _InterlockedAdd(&dword_140086730, 1u);
          WdLogSingleEntry2(6, v6, v44);
          v9 = 0;
          WdLogGlobalForLineNumber = 5341;
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
          v26 = v71;
LABEL_85:
          if ( (*((_BYTE *)this + 37225) & 0x10) != 0 )
          {
            v49 = *(_QWORD *)this;
            *(_DWORD *)(v6 + 32) |= 1u;
            VidMmQueueWorkerThreadWorkItem(v49, TerminateWorkItemCB, v6, 1, Timeout, v61);
          }
          else
          {
            memset(v69, 0, 0x58u);
            LODWORD(v69[0]) = 200;
            v69[2] = v6;
            if ( (int)VIDMM_GLOBAL::QueueDeferredCommand(
                        this,
                        *(struct VIDMM_PAGING_QUEUE **)(32LL * ((*(_DWORD *)(v67 + 60) >> 2) & 0x3F)
                                                      + *(_QWORD *)(*(_QWORD *)v36 + 72LL)),
                        (struct _VIDMM_DEFERRED_COMMAND *)v69,
                        1,
                        0) < 0 )
            {
              g_DxgMmsBugcheckExportIndex = 1;
              WdLogSingleEntry5(0, 270, 5);
              WdLogGlobalForLineNumber = 222;
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
          VIDMM_GLOBAL::CloseLocalAllocation(this, v63, 1);
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
        (DXGAUTOPUSHLOCKEXCLUSIVE *)v68,
        (VIDMM_GLOBAL *)((char *)this + 36408));
      v22 = (_QWORD *)((char *)v9 + 288);
      if ( *((_QWORD *)v9 + 36) )
        VIDMM_GLOBAL::RemoveAllocationFromDecommitList(v21, v9, v62);
      if ( (*((_BYTE *)v9 + 32) & 0x60) == 0x60 )
      {
        v23 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v63 + 1) + 32LL)
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
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v68);
      v26 = v63;
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
  _InterlockedAdd(&dword_1400866A8, 1u);
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 5074;
  DxgkLogInternalTriageEvent(
    v13,
    262145,
    v14,
    (unsigned int)L"Couldn't allocate memory for allocation.\n",
    5074,
    v6,
    v6,
    v6);
  LODWORD(v15) = -1073741801;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14010416c  mov     [rsp-8+arg_0], rbx
0x140104171  mov     [rsp-8+arg_8], rdx
0x140104176  push    rbp
0x140104177  push    rsi
0x140104178  push    rdi
0x140104179  push    r12
0x14010417b  push    r13
0x14010417d  push    r14
0x14010417f  push    r15
0x140104181  lea     rbp, [rsp-30h]
0x140104186  sub     rsp, 130h
0x14010418d  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x140104194  xor     esi, esi
0x140104196  mov     rbx, [r8]
0x140104199  mov     r15b, r9b
0x14010419c  mov     r14, r8
0x14010419f  mov     [rbp+60h+var_B8], rbx
0x1401041a3  mov     rdi, rdx
0x1401041a6  mov     r13, rcx
0x1401041a9  cmp     [rax], sil
0x1401041ac  jnz     loc_1401043B6
0x1401041b2  mov     rax, [rbp+60h+arg_28]
0x1401041b9  mov     edx, 33306956h
0x1401041be  mov     r8d, 40h ; '@'
0x1401041c4  mov     [rax], rsi
0x1401041c7  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1401041ce  cmp     [rax], sil
0x1401041d1  jnz     loc_1401043D9
0x1401041d7  mov     ecx, 308h
0x1401041dc  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401041e1  test    rax, rax
0x1401041e4  jnz     loc_140104687
0x1401041ea  mov     r12d, 1
0x1401041f0  lock add cs:dword_1400866A8, r12d
0x1401041f8  lea     ecx, [r12+5]
0x1401041fd  call    cs:__imp_WdLogSingleEntry0
0x140104204  nop     dword ptr [rax+rax+00h]
0x140104209  mov     [rsp+160h+var_128], rsi
0x14010420e  lea     r9, aCouldnTAllocat_26; "Couldn't allocate memory for allocation"...
0x140104215  mov     eax, 13D2h
0x14010421a  mov     [rsp+160h+var_130], rsi
0x14010421f  mov     [rsp+160h+var_138], rsi
0x140104224  mov     edx, 40001h
0x140104229  mov     cs:WdLogGlobalForLineNumber, eax
0x14010422f  mov     [rsp+160h+Timeout], rax
0x140104234  call    DxgkLogInternalTriageEvent
0x140104239  mov     r15d, 0C0000017h
0x14010423f  jmp     loc_1401042F9
0x140104244  lea     rax, [rsi+28h]
0x140104248  mov     [rax], rcx
0x14010424b  mov     [rax+8], rdx
0x14010424f  mov     [rdx], rax
0x140104252  mov     [rcx+8], rax
0x140104256  test    byte ptr [r13+9168h], 20h
0x14010425e  jnz     loc_140104766
0x140104264  lea     rcx, [r14+88h]; this
0x14010426b  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x140104270  mov     rax, [rbp+60h+var_D0]
0x140104274  cmp     [rbp+60h+var_C0], rax
0x140104278  jnz     loc_140104318
0x14010427e  xor     r9d, r9d
0x140104281  mov     rax, [r14+180h]
0x140104288  test    dword ptr [rax], 40000000h
0x14010428e  jnz     loc_1401047D3
0x140104294  mov     r8, [rbp+60h+arg_8]
0x140104298  mov     r15d, r9d
0x14010429b  mov     rax, [r8+18h]
0x14010429f  test    rax, rax
0x1401042a2  jz      short loc_1401042BF
0x1401042a4  cmp     [rax+77Fh], r9b
0x1401042ab  jz      loc_140104533
0x1401042b1  test    dword ptr [r14+18h], 2000000h
0x1401042b9  jnz     loc_140104554
0x1401042bf  mov     rax, [rbp+60h+arg_28]
0x1401042c6  or      dword ptr [rsi+1Ch], 40h
0x1401042ca  mov     [rax], rsi
0x1401042cd  mov     al, cs:byte_140086201
0x1401042d3  and     al, 10h
0x1401042d5  mov     byte ptr [rbp+60h+arg_28], al
0x1401042db  jnz     loc_140104A1E
0x1401042e1  mov     rax, [rbp+60h+var_B8]
0x1401042e5  mov     rax, [rax+10h]
0x1401042e9  lock add [r13+0ED0h], r12d
0x1401042f1  lock add [r13+0ED8h], rax
0x1401042f9  mov     rbx, [rsp+160h+arg_0]
0x140104301  mov     eax, r15d
0x140104304  add     rsp, 130h
0x14010430b  pop     r15
0x14010430d  pop     r14
0x14010430f  pop     r13
0x140104311  pop     r12
0x140104313  pop     rdi
0x140104314  pop     rsi
0x140104315  pop     rbp
0x140104316  retn
0x140104318  xor     r9d, r9d
0x14010431b  cmp     rbx, [r14+30h]
0x14010431f  jnz     loc_14010478E
0x140104325  mov     rax, [r14+180h]
0x14010432c  cmp     [rax+8], r9w
0x140104331  jz      loc_140104281
0x140104337  lea     rdx, [r13+8E38h]; struct DXGPUSHLOCK *
0x14010433e  lea     rcx, [rbp+60h+var_B0]; this
0x140104342  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x140104347  lea     rbx, [r14+120h]
0x14010434e  cmp     qword ptr [rbx], 0
0x140104352  jz      short loc_140104360
0x140104354  mov     r8, [rbp+60h+var_E0]; struct VIDMM_PROCESS_ADAPTER_INFO *
0x140104358  mov     rdx, r14; struct VIDMM_GLOBAL_ALLOC *
0x14010435b  call    ?RemoveAllocationFromDecommitList@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_GLOBAL_ALLOC@@PEAUVIDMM_PROCESS_ADAPTER_INFO@@@Z; VIDMM_GLOBAL::RemoveAllocationFromDecommitList(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS_ADAPTER_INFO *)
0x140104360  mov     eax, [r14+20h]
0x140104364  and     eax, 60h
0x140104367  cmp     al, 60h ; '`'
0x140104369  jnz     short loc_1401043A4
0x14010436b  mov     rax, [r13+18h]
0x14010436f  mov     edx, [rax+0F0h]
0x140104375  mov     rax, [rbp+60h+var_D8]
0x140104379  mov     rax, [rax+8]
0x14010437d  mov     rcx, [rax+20h]
0x140104381  mov     rax, [rcx+rdx*8]
0x140104385  mov     rcx, [rax+60h]
0x140104389  add     rax, 58h ; 'X'
0x14010438d  cmp     [rcx], rax
0x140104390  jnz     loc_14010452C
0x140104396  mov     [rbx], rax
0x140104399  mov     [rbx+8], rcx
0x14010439d  mov     [rcx], rbx
0x1401043a0  mov     [rax+8], rbx
0x1401043a4  lea     rcx, [rbp+60h+var_B0]; this
0x1401043a8  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401043ad  mov     rbx, [rbp+60h+var_D8]
0x1401043b1  jmp     loc_14010427E
0x1401043b6  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1401043bd  nop     dword ptr [rax+rax+00h]
0x1401043c2  mov     [rax+18h], r14
0x1401043c6  mov     [rax+20h], rdi
0x1401043ca  mov     cs:WdLogGlobalForLineNumber, 13BBh
0x1401043d4  jmp     loc_1401041B2
0x1401043d9  mov     ecx, 338h
0x1401043de  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401043e3  test    rax, rax
0x1401043e6  jz      short loc_1401043F3
0x1401043e8  mov     rcx, rax; this
0x1401043eb  call    ??0VIDMM_ALLOC_DEBUG@@QEAA@XZ; VIDMM_ALLOC_DEBUG::VIDMM_ALLOC_DEBUG(void)
0x1401043f0  mov     rsi, rax
0x1401043f3  test    rsi, rsi
0x1401043f6  jz      loc_1401041EA
0x1401043fc  mov     ecx, [r13+0C48h]
0x140104403  mov     r12d, 1
0x140104409  mov     al, [rsi+24h]
0x14010440c  mov     rdx, rsi; struct VIDMM_ALLOC *
0x14010440f  shr     ecx, 0Dh
0x140104412  and     al, 0FEh
0x140104414  and     cl, r12b
0x140104417  or      cl, al
0x140104419  mov     [rsi+24h], cl
0x14010441c  mov     rcx, rdi; this
0x14010441f  call    ?NotifyAllocationOpened@VIDMM_DEVICE@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_DEVICE::NotifyAllocationOpened(VIDMM_ALLOC *)
0x140104424  mov     ecx, [rsi+20h]
0x140104427  mov     eax, ecx
0x140104429  xor     eax, [rbx+3Ch]
0x14010442c  lea     rbx, [r14+88h]
0x140104433  and     eax, 0FCh
0x140104438  mov     [rbp+60h+arg_10], rbx
0x14010443f  xor     eax, ecx
0x140104441  mov     rcx, rbx; this
0x140104444  mov     [rsi+20h], eax
0x140104447  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x14010444c  cmp     [r14+29h], r12b
0x140104450  jz      loc_140104694
0x140104456  mov     ecx, [r14+20h]
0x14010445a  xor     edx, edx
0x14010445c  mov     eax, ecx
0x14010445e  and     eax, r12d
0x140104461  test    al, al
0x140104463  jnz     loc_1401046C2
0x140104469  mov     r8, [r14+30h]
0x14010446d  shr     ecx, 2
0x140104470  mov     [rbp+60h+var_E0], rdx
0x140104474  mov     [rbp+60h+var_C0], r8
0x140104478  test    r12b, cl
0x14010447b  jnz     loc_1401046F2
0x140104481  mov     r8, [rdi+8]; struct VIDMM_PROCESS *
0x140104485  mov     r9b, r15b; bool
0x140104488  mov     rdx, r14; struct VIDMM_GLOBAL_ALLOC *
0x14010448b  mov     rcx, r13; this
0x14010448e  call    ?OpenLocalAllocation@VIDMM_GLOBAL@@QEAAPEAUVIDMM_LOCAL_ALLOC@@PEAUVIDMM_GLOBAL_ALLOC@@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_GLOBAL::OpenLocalAllocation(VIDMM_GLOBAL_ALLOC *,VIDMM_PROCESS *,bool)
0x140104493  xor     r9d, r9d
0x140104496  mov     [rbp+60h+var_D8], rax
0x14010449a  mov     rbx, rax
0x14010449d  test    rax, rax
0x1401044a0  jz      loc_140104711
0x1401044a6  mov     rax, [r14+30h]
0x1401044aa  lea     rdi, [rsi+8]
0x1401044ae  mov     edx, [rsi+1Ch]
0x1401044b1  mov     r8, [rbp+60h+arg_20]
0x1401044b8  mov     [rbp+60h+var_D0], rax
0x1401044bc  mov     rax, [rbp+60h+arg_8]
0x1401044c0  mov     [rdi], rax
0x1401044c3  mov     [rsi], rbx
0x1401044c6  mov     [rsi+10h], r8
0x1401044ca  mov     rax, [r14+180h]
0x1401044d1  mov     [rsi+60h], rax
0x1401044d5  mov     rax, [r14+180h]
0x1401044dc  mov     ecx, [rax]
0x1401044de  shr     ecx, 1Ah
0x1401044e1  xor     ecx, edx
0x1401044e3  mov     [rsi+18h], r15b
0x1401044e7  and     ecx, 8
0x1401044ea  xor     ecx, edx
0x1401044ec  mov     [rsi+1Ch], ecx
0x1401044ef  test    r15b, r15b
0x1401044f2  jnz     loc_140104723
0x1401044f8  lea     rax, [rsi+288h]
0x1401044ff  mov     [rsi+2A8h], r9
0x140104506  mov     [rax+8], rax
0x14010450a  mov     [rax], rax
0x14010450d  lea     rax, [rsi+298h]
0x140104514  lea     rcx, [rbx+20h]
0x140104518  mov     [rax+8], rax
0x14010451c  mov     [rax], rax
0x14010451f  mov     rdx, [rcx+8]
0x140104523  cmp     [rdx], rcx
0x140104526  jz      loc_140104244
0x14010452c  mov     ecx, 3
0x140104531  int     29h; Win8: RtlFailFast(ecx)
0x140104533  cmp     dword ptr [rax+1D0h], 2
0x14010453a  jnz     short loc_140104554
0x14010453c  mov     rax, [rax+10h]
0x140104540  mov     rcx, [rax+10h]
0x140104544  cmp     dword ptr [rcx+0C2Ch], 7D0h
0x14010454e  jge     loc_1401042B1
0x140104554  mov     rax, [rbp+60h+var_B8]
0x140104558  lea     r8, [rbp+60h+var_C8]; struct VIDMM_MULTI_ALLOC **
0x14010455c  mov     [rbp+60h+var_E0], r9
0x140104560  mov     [rbp+60h+var_C0], r9
0x140104564  mov     [rbp+60h+var_C8], rsi
0x140104568  mov     edx, [rax+3Ch]
0x14010456b  mov     rax, [rdi]
0x14010456e  shr     rdx, 2
0x140104572  and     edx, 3Fh
0x140104575  shl     rdx, 5
0x140104579  mov     rcx, [rax+48h]
0x14010457d  mov     rax, [rdx+rcx]
0x140104581  lea     rcx, [rbp+60h+var_C0]
0x140104585  mov     [rsp+160h+var_130], rcx; unsigned __int64 *
0x14010458a  mov     rdx, rax; struct VIDMM_PAGING_QUEUE *
0x14010458d  lea     rcx, [rbp+60h+var_E0]
0x140104591  mov     [rbp+60h+var_D0], rax
0x140104595  mov     [rsp+160h+var_138], rcx; unsigned __int64 *
0x14010459a  mov     rcx, r13; this
0x14010459d  mov     dword ptr [rsp+160h+Timeout], r9d; char
0x1401045a2  mov     r9, r12; unsigned __int64
0x1401045a5  call    ?MakeResident@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAPEAUVIDMM_MULTI_ALLOC@@_KKPEA_K3@Z; VIDMM_GLOBAL::MakeResident(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC * *,unsigned __int64,ulong,unsigned __int64 *,unsigned __int64 *)
0x1401045aa  mov     r15d, eax
0x1401045ad  cmp     eax, 103h
0x1401045b2  jnz     loc_14010491D
0x1401045b8  mov     rdx, [rbp+60h+var_D0]
0x1401045bc  mov     rcx, r13; this
0x1401045bf  mov     r8, [rbp+60h+var_E0]; unsigned __int64
0x1401045c3  mov     rdx, [rdx+58h]; struct _VIDSCH_SYNC_OBJECT *
0x1401045c7  call    ?WaitForFence@VIDMM_GLOBAL@@QEAAXPEAU_VIDSCH_SYNC_OBJECT@@_K@Z; VIDMM_GLOBAL::WaitForFence(_VIDSCH_SYNC_OBJECT *,unsigned __int64)
0x1401045cc  xor     r9d, r9d
0x1401045cf  mov     r15d, r9d
0x1401045d2  mov     r8, [rbp+60h+arg_8]
0x1401045d6  jmp     loc_1401042BF
0x1401045db  mov     rax, [r13+18h]
0x1401045df  mov     ecx, [rax+1BCh]
0x1401045e5  test    cl, 10h
0x1401045e8  jnz     loc_140104782
0x1401045ee  mov     rcx, [r14+0E8h]
0x1401045f5  lea     rdx, [rbp+60h+var_C8]
0x1401045f9  mov     [rbp+60h+var_C8], r9
0x1401045fd  xor     r8d, r8d
0x140104600  mov     r9, [rbp+60h+var_B8]
0x140104604  mov     [rsp+160h+var_130], rdx
0x140104609  mov     rax, [rcx]
0x14010460c  mov     rdx, [r14+0F0h]
0x140104613  mov     r9, [r9+10h]
0x140104617  mov     byte ptr [rsp+160h+var_138], r15b
0x14010461c  mov     rax, [rax+38h]
0x140104620  mov     byte ptr [rsp+160h+Timeout], r12b
0x140104625  call    _guard_dispatch_icall
0x14010462a  mov     [rsi+2A8h], rax
0x140104631  jmp     loc_140104264
0x140104636  cmp     [rax+8], rcx
0x14010463a  jnz     loc_14010452C
0x140104640  mov     rdx, [rcx+8]
0x140104644  cmp     [rdx], rcx
0x140104647  jnz     loc_14010452C
0x14010464d  mov     [rdx], rax
0x140104650  mov     [rax+8], rdx
0x140104654  mov     rdx, [rbp+60h+var_D8]; struct VIDMM_LOCAL_ALLOC *
0x140104658  mov     r8b, r12b; bool
0x14010465b  mov     rcx, r13; this
0x14010465e  call    ?CloseLocalAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_LOCAL_ALLOC@@_N@Z; VIDMM_GLOBAL::CloseLocalAllocation(VIDMM_LOCAL_ALLOC *,bool)
0x140104663  mov     rdi, [rbp+60h+arg_8]
0x140104667  mov     rdx, rsi; struct VIDMM_ALLOC *
0x14010466a  mov     rcx, rdi; this
0x14010466d  call    ?NotifyAllocationClosed@VIDMM_DEVICE@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_DEVICE::NotifyAllocationClosed(VIDMM_ALLOC *)
  ... truncated ...
```
