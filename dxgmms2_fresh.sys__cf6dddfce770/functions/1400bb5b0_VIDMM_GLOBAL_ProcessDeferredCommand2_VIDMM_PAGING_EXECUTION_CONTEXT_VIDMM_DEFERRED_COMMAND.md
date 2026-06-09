# VIDMM_GLOBAL::ProcessDeferredCommand2(VIDMM_PAGING_EXECUTION_CONTEXT *,_VIDMM_DEFERRED_COMMAND *)

- ea: `0x1400bb5b0`
- end: `0x1400bbd54`
- name: `?ProcessDeferredCommand2@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAU_VIDMM_DEFERRED_COMMAND@@@Z`
- size: `1956`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct _VIDMM_DEFERRED_COMMAND *)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400d81a0`

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
- `0x140058f50`
- `0x140059030`
- `0x140099714`
- `0x14009ca80`
- `0x14009cf50`
- `0x14009e4a0`
- `0x1400a5598`
- `0x1400a6a34`
- `0x1400aad90`
- `0x1400ab03c`
- `0x1400b7298`
- `0x1400b8418`
- `0x1400bb310`
- `0x1400bb5b0`
- `0x1400bd6ac`
- `0x1400c4984`
- `0x1400eb130`
- `0x1400eb290`
- `0x1400ef500`
- `0x1400efa1c`
- `0x140115f00`
- `0x14011610c`
- `0x14011a83c`
- `0x14011e98c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400bbb63`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400bbb63`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bb8a8`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bb904`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bb950`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bb8a8`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bb904`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400bb950`
- `watchdog!WdLogSingleEntry5` at `0x1400bbb36`
- `watchdog!WdLogSingleEntry5` at `0x1400bbb36`
- `watchdog!WdLogSingleEntry1` at `0x1400bb812`
- `watchdog!WdLogSingleEntry1` at `0x1400bb812`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400bbb10`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400bb899`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400bb8f8`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400bb944`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_GLOBAL::ProcessDeferredCommand2(
        VIDMM_GLOBAL *this,
        struct VIDMM_PAGING_EXECUTION_CONTEXT *a2,
        struct _VIDMM_DEFERRED_COMMAND *a3)
{
  __int64 v3; // rdi
  __int64 v7; // rax
  union _LARGE_INTEGER *v8; // rsi
  union _LARGE_INTEGER v9; // r11
  __int64 v10; // r9
  _QWORD *v11; // r12
  unsigned int v12; // r13d
  __int64 v13; // rdx
  unsigned int v14; // r10d
  __int64 v15; // r8
  int v16; // ecx
  int v17; // ecx
  bool v19; // r8
  __int64 v20; // rdx
  unsigned int v21; // r9d
  unsigned __int8 v22; // r10
  int *QuadPart; // rcx
  int v24; // eax
  int v25; // ecx
  unsigned int v26; // r9d
  int v27; // eax
  int updated; // eax
  unsigned __int16 v29; // r8
  unsigned int v30; // eax
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  struct VIDMM_GLOBAL_ALLOC *v35; // rdi
  char v36; // si
  char v37; // si
  __int64 v38; // r8
  VIDMM_GLOBAL *v39; // rcx
  _QWORD **v40; // r12
  _QWORD *i; // rdi
  _QWORD *j; // rsi
  __int64 v44; // [rsp+50h] [rbp-59h]
  union _LARGE_INTEGER Interval; // [rsp+58h] [rbp-51h] BYREF
  __int64 **v46; // [rsp+70h] [rbp-39h]
  _BYTE v47[64]; // [rsp+80h] [rbp-29h] BYREF

  v3 = *((_QWORD *)a3 + 2);
  if ( v3 )
  {
    v7 = *((_QWORD *)this + 4560);
    v46 = *(__int64 ***)v3;
    v8 = (union _LARGE_INTEGER *)*v46;
    v9.QuadPart = **v46;
    v10 = *(_QWORD *)(v7 + 8LL * ((*(_DWORD *)(v9.QuadPart + 60) >> 2) & 0x3F));
  }
  else
  {
    v9.QuadPart = 0;
    v46 = 0;
    v10 = 0;
    v8 = 0;
  }
  v11 = (_QWORD *)*((_QWORD *)a3 + 1);
  v12 = 0;
  v44 = v10;
  Interval = v9;
  if ( !v11 )
    v11 = *(_QWORD **)(v3 + 8);
  v13 = v11[4];
  v14 = 1;
  if ( v13 && (*(_BYTE *)(v13 + 212) || _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 208), 0, 0))
    || VIDMM_GLOBAL::IsTdrPending(this) )
  {
    *((_DWORD *)a3 + 21) = -1071775232;
    *((_BYTE *)a3 + 80) = v14;
  }
  v15 = *(int *)a3;
  if ( (int)v15 <= 210 )
  {
    switch ( (_DWORD)v15 )
    {
      case 0xD2:
        if ( VIDMM_ALLOC::HasAnyResidencyReferences((VIDMM_ALLOC *)v3) && v29 < 2u )
        {
          v30 = VIDMM_GLOBAL::PageInOneAllocation(
                  (__int64)this,
                  a2,
                  (__int64 ***)v3,
                  0,
                  *((_BYTE *)a2 + 52),
                  (_BYTE *)a2 + 72,
                  (__int64 ****)a2 + 8,
                  0,
                  -1);
          v8[3].LowPart &= ~0x4000000u;
          return v30;
        }
        return v12;
      case 0x71:
        updated = VIDMM_GLOBAL::CommitVirtualAddressRangeSystemCommand(
                    this,
                    a2,
                    (struct _VIDMM_DEFERRED_COMMAND *)((char *)a3 + 32),
                    (struct VIDMM_ALLOC **)a2 + 8);
        break;
      case 0x77:
        updated = VIDMM_GLOBAL::UpdateGpuVirtualAddressSystemCommand(
                    this,
                    a2,
                    *((struct VIDSCH_DEVICE_COMMAND_UPDATEGPUVA **)a3 + 4),
                    (struct VIDMM_ALLOC **)a2 + 8);
        break;
      case 0xCB:
        if ( g_IsInternalReleaseOrDbg )
        {
          *(_QWORD *)(WdLogNewEntry5_WdTrace((unsigned int)(v15 - 203), v13) + 24) = v3;
          WdLogGlobalForLineNumber = 13059;
        }
        if ( BYTE1(v8[5].LowPart) )
        {
          return (unsigned int)-1071775482;
        }
        else
        {
          if ( !*(_DWORD *)(v8[49].QuadPart + 16) )
          {
            QuadPart = (int *)v8[49].QuadPart;
            if ( (*QuadPart & 0x20000) == 0 )
            {
              if ( g_IsInternalReleaseOrDbg )
              {
                WdLogNewEntry5_WdTrace(QuadPart, v13);
                WdLogGlobalForLineNumber = 13082;
                QuadPart = (int *)v8[49].QuadPart;
              }
              if ( (*(_DWORD *)(Interval.QuadPart + 64) & 1) != 0 )
              {
                v24 = *QuadPart;
                if ( (*QuadPart & 0x40000000) == 0 && ((v24 & 0x20000000) == 0 || v24 >= 0) && (v24 & 0x80000) == 0 )
                {
                  if ( g_IsInternalReleaseOrDbg )
                  {
                    WdLogNewEntry5_WdTrace(QuadPart, v13);
                    WdLogGlobalForLineNumber = 13095;
                  }
                  VidMmSuspendAccessToAllocation(
                    *(struct VIDMM_WORKER_THREAD **)this,
                    a2,
                    (struct VIDMM_GLOBAL_ALLOC *)v8);
                  VIDMM_GLOBAL::EvictAllocation(this, a2, (struct VIDMM_GLOBAL_ALLOC *)v8);
                  (*(void (__fastcall **)(__int64, struct VIDMM_PAGING_EXECUTION_CONTEXT *))(*(_QWORD *)v44 + 200LL))(
                    v44,
                    a2);
                }
              }
            }
          }
          v25 = *(_DWORD *)v8[49].QuadPart;
          if ( (v25 & 0x20000) != 0 )
          {
            v26 = *((_DWORD *)a3 + 8);
          }
          else if ( (v25 & 0x40000000) != 0 || (v26 = 4, v25 < 0) )
          {
            v26 = 3;
          }
          if ( *((_QWORD *)a3 + 5) != -1 )
            v8[3].HighPart |= 4u;
          v27 = VIDMM_GLOBAL::PageInOneAllocation(
                  (__int64)this,
                  a2,
                  (__int64 ***)v3,
                  v26,
                  *((_BYTE *)a2 + 52),
                  (_BYTE *)a2 + 72,
                  (__int64 ****)a2 + 8,
                  *((_DWORD *)a3 + 9),
                  *((_QWORD *)a3 + 5));
          v8[3].HighPart &= ~4u;
          v12 = v27;
          if ( v27 >= 0 )
            _InterlockedIncrement((volatile signed __int32 *)(v8[49].QuadPart + 16));
          VIDMM_GLOBAL::RecommitTrimmedList(this);
        }
        return v12;
      case 0xCE:
        if ( (int)v8[23].LowPart > 0
          && (unsigned __int8)NeedsApertureForLock(this, v8)
          && ((unsigned __int8)v8[3].LowPart & v22) == 0 )
        {
          WdLogSingleEntry1(v21, v20);
          WdLogGlobalForLineNumber = 13163;
          return (unsigned int)-1073741823;
        }
LABEL_33:
        if ( VIDMM_ALLOC::HasAnyResidencyReferences((VIDMM_ALLOC *)v3) && *(_WORD *)(v8[49].QuadPart + 8) < 2u )
          return (unsigned int)VIDMM_GLOBAL::PageInOneAllocation(
                                 (__int64)this,
                                 a2,
                                 (__int64 ***)v3,
                                 0,
                                 *((_BYTE *)a2 + 52),
                                 (_BYTE *)a2 + 72,
                                 (__int64 ****)a2 + 8,
                                 0,
                                 -1);
        return v12;
      default:
        v16 = v15 - 206 - v14;
        if ( v16 )
        {
          v17 = v16 - v14;
          if ( v17 )
          {
            if ( v17 == v14 )
              return (unsigned int)VIDMM_GLOBAL::InitContextAllocation(
                                     this,
                                     a2,
                                     (struct VIDMM_ALLOC *)v3,
                                     v14,
                                     (bool *)a2 + 72,
                                     (struct VIDMM_ALLOC **)a2 + 8);
            goto LABEL_76;
          }
          if ( !*((_BYTE *)a3 + 45) )
          {
            (*(void (__fastcall **)(__int64, struct VIDMM_PAGING_EXECUTION_CONTEXT *, union _LARGE_INTEGER))(*(_QWORD *)v44 + 216LL))(
              v44,
              a2,
              v9);
            VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
              (VIDMM_PROCESS_AUTOATTACH *)v47,
              (struct VIDMM_PROCESS *)v46[1],
              1);
            DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(
              (DXGAUTOPUSHLOCKFASTEXCLUSIVE *)&Interval,
              (struct DXGPUSHLOCKFAST *)&v8[40],
              v19);
            v12 = VIDMM_GLOBAL::LockInternal(
                    this,
                    a2,
                    (struct VIDMM_ALLOC *)v3,
                    *((_BYTE *)a3 + 44),
                    *((_DWORD *)a3 + 10),
                    *((void ***)a3 + 4),
                    (bool *)a3 + 45);
            DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release((DXGAUTOPUSHLOCKFASTEXCLUSIVE *)&Interval);
            VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v47);
          }
          if ( *((_BYTE *)a3 + 45) )
            return (unsigned int)VIDMM_GLOBAL::PageInOneAllocation(
                                   (__int64)this,
                                   a2,
                                   (__int64 ***)v3,
                                   2u,
                                   0,
                                   (_BYTE *)a2 + 72,
                                   (__int64 ****)a2 + 8,
                                   0,
                                   -1);
        }
        else
        {
          if ( !*(_DWORD *)(v3 + 688) && ((unsigned __int8)v14 & *(_BYTE *)(v3 + 25)) == 0 )
            VIDMM_GLOBAL::EvictOneAllocation(this, a2, (struct VIDMM_ALLOC *)v3, v14 & *((_BYTE *)a3 + 32));
          _InterlockedDecrement((volatile signed __int32 *)(v3 + 700));
        }
        return v12;
    }
    v12 = updated;
    if ( updated == -1073741267 )
      *((_BYTE *)a2 + 72) = 1;
    return v12;
  }
  if ( (_DWORD)v15 == 211 )
  {
    v40 = (_QWORD **)(*((_QWORD *)a3 + 4) + 112LL);
    for ( i = *v40; i != v40; i = (_QWORD *)*i )
    {
      for ( j = (_QWORD *)*(i - 2); j != i - 2; j = (_QWORD *)*j )
        VIDMM_GLOBAL::EvictOneAllocation(this, a2, (struct VIDMM_ALLOC *)(j - 5), 0);
    }
    return v12;
  }
  v31 = v15 - 211 - v14;
  if ( !v31 )
  {
    VIDMM_GLOBAL::UpdateAllocationPriority(this, (struct VIDMM_ALLOC *)v3, *((_DWORD *)a3 + 8));
    return v12;
  }
  v32 = v31 - v14;
  if ( !v32 )
  {
    VIDMM_DEVICE::SuspendSchedulerDevice((VIDMM_DEVICE *)v11);
    VIDMM_DEVICE::SuspendPagingQueues((VIDMM_DEVICE *)v11);
    if ( v11[23] )
    {
      v37 = 0;
    }
    else
    {
      DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
        (DXGAUTOPUSHLOCKEXCLUSIVE *)&Interval,
        (struct DXGPUSHLOCK *const)(*v11 + 41152LL));
      LOBYTE(v38) = 4;
      VIDMM_GLOBAL::InsertToPenaltyBox(*v11, v11, v38);
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&Interval);
      v37 = 1;
    }
    if ( v3 )
    {
      if ( (*(_DWORD *)(v3 + 28) & 3) == 2 )
        VIDMM_GLOBAL::FaultOneAllocation((VIDMM_GLOBAL *)*v11, a2, (struct VIDMM_ALLOC *)v3);
    }
    else
    {
      VIDMM_DEVICE::FaultAllAllocations((VIDMM_DEVICE *)v11, a2);
    }
    VIDMM_GLOBAL::EvictFromFaultedList(this, a2, (struct VIDMM_DEVICE *)v11);
    v12 = VIDMM_GLOBAL::PageInFromFaultedList(this, a2, (struct VIDMM_DEVICE *)v11);
    VIDMM_DEVICE::ResumeSchedulerDevice((VIDMM_DEVICE *)v11);
    VIDMM_DEVICE::ResumePagingQueues((VIDMM_DEVICE *)v11);
    if ( v37 )
    {
      DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
        (DXGAUTOPUSHLOCKEXCLUSIVE *)&Interval,
        (struct DXGPUSHLOCK *const)(*v11 + 41152LL));
      VIDMM_GLOBAL::RemoveFromPenaltyBoxByListEntry(v39, (struct _LIST_ENTRY *)(v11 + 23));
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&Interval);
    }
    return v12;
  }
  v33 = v32 - v14;
  if ( !v33 )
  {
    (*(void (__fastcall **)(__int64, struct VIDMM_PAGING_EXECUTION_CONTEXT *, __int64, _QWORD, _BYTE, _BYTE, char *))(*(_QWORD *)v10 + 328LL))(
      v44,
      a2,
      v3,
      *((unsigned int *)a3 + 8),
      *((_BYTE *)a3 + 52),
      *((_BYTE *)a3 + 53),
      (char *)a3 + 36);
    goto LABEL_33;
  }
  v34 = v33 - v14;
  if ( v34 )
  {
    if ( v34 == 2 )
    {
LABEL_77:
      Interval.QuadPart = -10000LL * *((unsigned int *)a3 + 8);
      KeDelayExecutionThread(0, 0, &Interval);
      return v12;
    }
LABEL_76:
    g_DxgMmsBugcheckExportIndex = v14;
    WdLogSingleEntry5(0, 270, 5, v15, -1073741811, 0);
    WdLogGlobalForLineNumber = 227;
    goto LABEL_77;
  }
  v35 = (struct VIDMM_GLOBAL_ALLOC *)*((_QWORD *)a3 + 4);
  v36 = 0;
  DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
    (DXGAUTOPUSHLOCKEXCLUSIVE *)&Interval,
    (VIDMM_GLOBAL *)((char *)this + 36408));
  if ( *((_QWORD *)v35 + 36) )
  {
    VIDMM_GLOBAL::RemoveAllocationFromDecommitList(this, v35);
    v36 = 1;
  }
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)&Interval);
  if ( v36 )
    VIDMM_GLOBAL::DecommitGlobalAllocation(this, a2, v35);
  return v12;
}

```

## disassembly

```asm
0x1400bb5b0  mov     [rsp-8+arg_18], rbx
0x1400bb5b5  push    rbp
0x1400bb5b6  push    rsi
0x1400bb5b7  push    rdi
0x1400bb5b8  push    r12
0x1400bb5ba  push    r13
0x1400bb5bc  push    r14
0x1400bb5be  push    r15
0x1400bb5c0  lea     rbp, [rsp-27h]
0x1400bb5c5  sub     rsp, 0D0h
0x1400bb5cc  mov     rax, cs:__security_cookie
0x1400bb5d3  xor     rax, rsp
0x1400bb5d6  mov     [rbp+57h+var_40], rax
0x1400bb5da  mov     rdi, [r8+10h]
0x1400bb5de  mov     r15, r8
0x1400bb5e1  mov     rbx, rdx
0x1400bb5e4  mov     r14, rcx
0x1400bb5e7  test    rdi, rdi
0x1400bb5ea  jz      short loc_1400BB611
0x1400bb5ec  mov     rdx, [rdi]
0x1400bb5ef  mov     rax, [r14+8E80h]
0x1400bb5f6  mov     [rbp+57h+var_90], rdx
0x1400bb5fa  mov     rsi, [rdx]
0x1400bb5fd  mov     r11, [rsi]
0x1400bb600  mov     ecx, [r11+3Ch]
0x1400bb604  shr     rcx, 2
0x1400bb608  and     ecx, 3Fh
0x1400bb60b  mov     r9, [rax+rcx*8]
0x1400bb60f  jmp     short loc_1400BB621
0x1400bb611  xor     r11d, r11d
0x1400bb614  mov     [rbp+57h+var_90], 0
0x1400bb61c  xor     r9d, r9d
0x1400bb61f  xor     esi, esi
0x1400bb621  mov     r12, [r8+8]
0x1400bb625  xor     r13d, r13d
0x1400bb628  mov     [rbp+57h+var_B0], r9
0x1400bb62c  mov     qword ptr [rbp+57h+Interval], r11
0x1400bb630  test    r12, r12
0x1400bb633  jnz     short loc_1400BB639
0x1400bb635  mov     r12, [rdi+8]
0x1400bb639  mov     rdx, [r12+20h]
0x1400bb63e  mov     r10d, 1
0x1400bb644  test    rdx, rdx
0x1400bb647  jz      short loc_1400BB660
0x1400bb649  cmp     [rdx+0D4h], r13b
0x1400bb650  jnz     short loc_1400BB66C
0x1400bb652  xor     ecx, ecx
0x1400bb654  xor     eax, eax
0x1400bb656  lock cmpxchg [rdx+0D0h], ecx
0x1400bb65e  jnz     short loc_1400BB66C
0x1400bb660  mov     rcx, r14; this
0x1400bb663  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400bb668  test    al, al
0x1400bb66a  jz      short loc_1400BB678
0x1400bb66c  mov     dword ptr [r8+54h], 0C01E0200h
0x1400bb674  mov     [r8+50h], r10b
0x1400bb678  movsxd  r8, dword ptr [r8]
0x1400bb67b  mov     eax, 0D2h
0x1400bb680  cmp     r8d, eax
0x1400bb683  jg      loc_1400BBAD8
0x1400bb689  jz      loc_1400BBA68
0x1400bb68f  mov     ecx, r8d
0x1400bb692  sub     ecx, 71h ; 'q'
0x1400bb695  jz      loc_1400BBA3E
0x1400bb69b  sub     ecx, 6
0x1400bb69e  jz      loc_1400BBA29
0x1400bb6a4  sub     ecx, 54h ; 'T'
0x1400bb6a7  jz      loc_1400BB899
0x1400bb6ad  mov     r9d, 3
0x1400bb6b3  sub     ecx, r9d
0x1400bb6b6  jz      loc_1400BB7EE
0x1400bb6bc  sub     ecx, r10d
0x1400bb6bf  jz      loc_1400BB7BD
0x1400bb6c5  sub     ecx, r10d
0x1400bb6c8  jz      short loc_1400BB6FB
0x1400bb6ca  cmp     ecx, r10d
0x1400bb6cd  jnz     loc_1400BBB10
0x1400bb6d3  lea     r9, [rbx+48h]
0x1400bb6d7  mov     r8, rdi; struct VIDMM_ALLOC *
0x1400bb6da  lea     rax, [rbx+40h]
0x1400bb6de  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400bb6e1  mov     [rsp+100h+var_D8], rax; struct VIDMM_ALLOC **
0x1400bb6e6  mov     rcx, r14; this
0x1400bb6e9  mov     [rsp+100h+var_E0], r9; bool *
0x1400bb6ee  mov     r9b, r10b; bool
0x1400bb6f1  call    ?InitContextAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_NPEA_NPEAPEAU3@@Z; VIDMM_GLOBAL::InitContextAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool,bool *,VIDMM_ALLOC * *)
0x1400bb6f6  jmp     loc_1400BB891
0x1400bb6fb  lea     r12, [r15+2Dh]
0x1400bb6ff  cmp     [r12], r13b
0x1400bb703  jnz     short loc_1400BB77F
0x1400bb705  mov     rcx, [rbp+57h+var_B0]
0x1400bb709  mov     r8, r11
0x1400bb70c  mov     rdx, rbx
0x1400bb70f  mov     rax, [rcx]
0x1400bb712  mov     rax, [rax+0D8h]
0x1400bb719  call    _guard_dispatch_icall
0x1400bb71e  mov     rdx, [rbp+57h+var_90]
0x1400bb722  lea     rcx, [rbp+57h+var_80]; this
0x1400bb726  mov     r8b, 1; bool
0x1400bb729  mov     rdx, [rdx+8]; struct VIDMM_PROCESS *
0x1400bb72d  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400bb732  lea     rdx, [rsi+140h]; struct DXGPUSHLOCKFAST *
0x1400bb739  lea     rcx, [rbp+57h+Interval]; this
0x1400bb73d  call    ??0DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(DXGPUSHLOCKFAST &,bool)
0x1400bb742  mov     rax, [r15+20h]
0x1400bb746  mov     r8, rdi; struct VIDMM_ALLOC *
0x1400bb749  mov     r9b, [r15+2Ch]; bool
0x1400bb74d  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400bb750  mov     [rsp+100h+var_D0], r12; bool *
0x1400bb755  mov     rcx, r14; this
0x1400bb758  mov     [rsp+100h+var_D8], rax; void **
0x1400bb75d  mov     eax, [r15+28h]
0x1400bb761  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x1400bb765  call    ?LockInternal@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_NKPEAPEAXPEA_N@Z; VIDMM_GLOBAL::LockInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool,ulong,void * *,bool *)
0x1400bb76a  lea     rcx, [rbp+57h+Interval]; this
0x1400bb76e  mov     r13d, eax
0x1400bb771  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x1400bb776  lea     rcx, [rbp+57h+var_80]; this
0x1400bb77a  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400bb77f  cmp     byte ptr [r12], 0
0x1400bb784  jz      loc_1400BBD29
0x1400bb78a  mov     [rsp+100h+var_C0], 0FFFFFFFFFFFFFFFFh
0x1400bb793  lea     rax, [rbx+40h]
0x1400bb797  mov     [rsp+100h+var_C8], 0
0x1400bb79f  lea     rcx, [rbx+48h]
0x1400bb7a3  mov     [rsp+100h+var_D0], rax
0x1400bb7a8  mov     r9d, 2
0x1400bb7ae  mov     [rsp+100h+var_D8], rcx
0x1400bb7b3  mov     byte ptr [rsp+100h+var_E0], 0
0x1400bb7b8  jmp     loc_1400BB883
0x1400bb7bd  mov     eax, [rdi+2B0h]
0x1400bb7c3  test    eax, eax
0x1400bb7c5  jnz     short loc_1400BB7E2
0x1400bb7c7  test    [rdi+19h], r10b
0x1400bb7cb  jnz     short loc_1400BB7E2
0x1400bb7cd  mov     r9b, [r15+20h]
0x1400bb7d1  mov     r8, rdi; struct VIDMM_ALLOC *
0x1400bb7d4  and     r9b, r10b; bool
0x1400bb7d7  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400bb7da  mov     rcx, r14; this
0x1400bb7dd  call    ?EvictOneAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_N@Z; VIDMM_GLOBAL::EvictOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool)
0x1400bb7e2  lock dec dword ptr [rdi+2BCh]
0x1400bb7e9  jmp     loc_1400BBD29
0x1400bb7ee  mov     eax, [rsi+0B8h]
0x1400bb7f4  test    eax, eax
0x1400bb7f6  jle     short loc_1400BB833
0x1400bb7f8  mov     rdx, rsi
0x1400bb7fb  mov     rcx, r14
0x1400bb7fe  call    NeedsApertureForLock
0x1400bb803  test    al, al
0x1400bb805  jz      short loc_1400BB833
0x1400bb807  mov     eax, [rsi+18h]
0x1400bb80a  test    r10b, al
0x1400bb80d  jnz     short loc_1400BB833
0x1400bb80f  mov     ecx, r9d
0x1400bb812  call    cs:__imp_WdLogSingleEntry1
0x1400bb819  nop     dword ptr [rax+rax+00h]
0x1400bb81e  mov     cs:WdLogGlobalForLineNumber, 336Bh
0x1400bb828  mov     r13d, 0C0000001h
0x1400bb82e  jmp     loc_1400BBD29
0x1400bb833  mov     rcx, rdi; this
0x1400bb836  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x1400bb83b  test    al, al
0x1400bb83d  jz      loc_1400BBD29
0x1400bb843  mov     rax, [rsi+188h]
0x1400bb84a  mov     edx, 2
0x1400bb84f  cmp     [rax+8], dx
0x1400bb853  jnb     loc_1400BBD29
0x1400bb859  mov     [rsp+100h+var_C0], 0FFFFFFFFFFFFFFFFh
0x1400bb862  lea     rax, [rbx+40h]
0x1400bb866  mov     [rsp+100h+var_C8], r13d
0x1400bb86b  lea     rcx, [rbx+48h]
0x1400bb86f  mov     [rsp+100h+var_D0], rax
0x1400bb874  xor     r9d, r9d
0x1400bb877  mov     al, [rbx+34h]
0x1400bb87a  mov     [rsp+100h+var_D8], rcx
0x1400bb87f  mov     byte ptr [rsp+100h+var_E0], al
0x1400bb883  mov     r8, rdi
0x1400bb886  mov     rdx, rbx
0x1400bb889  mov     rcx, r14
0x1400bb88c  call    ?PageInOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@W4VIDMM_PLACEMENT_RESTRICTION@@_NPEA_NPEAPEAU3@I_K@Z; VIDMM_GLOBAL::PageInOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,VIDMM_PLACEMENT_RESTRICTION,bool,bool *,VIDMM_ALLOC * *,uint,unsigned __int64)
0x1400bb891  mov     r13d, eax
0x1400bb894  jmp     loc_1400BBD29
0x1400bb899  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400bb8a0  xor     r12d, r12d
0x1400bb8a3  cmp     [rax], r12b
0x1400bb8a6  jz      short loc_1400BB8C2
0x1400bb8a8  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400bb8af  nop     dword ptr [rax+rax+00h]
0x1400bb8b4  mov     [rax+18h], rdi
0x1400bb8b8  mov     cs:WdLogGlobalForLineNumber, 3303h
0x1400bb8c2  cmp     [rsi+29h], r12b
0x1400bb8c6  jz      short loc_1400BB8D3
0x1400bb8c8  mov     r13d, 0C01E0106h
0x1400bb8ce  jmp     loc_1400BBD29
0x1400bb8d3  mov     rax, [rsi+188h]
0x1400bb8da  mov     ecx, [rax+10h]
0x1400bb8dd  test    ecx, ecx
0x1400bb8df  jnz     loc_1400BB998
0x1400bb8e5  mov     rcx, [rsi+188h]
0x1400bb8ec  test    dword ptr [rcx], 20000h
0x1400bb8f2  jnz     loc_1400BB998
0x1400bb8f8  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400bb8ff  cmp     [rax], r12b
0x1400bb902  jz      short loc_1400BB921
0x1400bb904  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400bb90b  nop     dword ptr [rax+rax+00h]
0x1400bb910  mov     cs:WdLogGlobalForLineNumber, 331Ah
0x1400bb91a  mov     rcx, [rsi+188h]
0x1400bb921  mov     rax, qword ptr [rbp+57h+Interval]
0x1400bb925  mov     eax, [rax+40h]
0x1400bb928  test    al, 1
0x1400bb92a  jz      short loc_1400BB998
0x1400bb92c  mov     eax, [rcx]
0x1400bb92e  bt      eax, 1Eh
0x1400bb932  jb      short loc_1400BB998
0x1400bb934  bt      eax, 1Dh
0x1400bb938  jnb     short loc_1400BB93E
0x1400bb93a  test    eax, eax
0x1400bb93c  js      short loc_1400BB998
0x1400bb93e  bt      eax, 13h
0x1400bb942  jb      short loc_1400BB998
0x1400bb944  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400bb94b  cmp     [rax], r12b
0x1400bb94e  jz      short loc_1400BB966
0x1400bb950  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400bb957  nop     dword ptr [rax+rax+00h]
0x1400bb95c  mov     cs:WdLogGlobalForLineNumber, 3327h
0x1400bb966  mov     rcx, [r14]; struct VIDMM_WORKER_THREAD *
0x1400bb969  mov     r8, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400bb96c  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400bb96f  call    ?VidMmSuspendAccessToAllocation@@YAPEAVVIDMM_DEVICE@@PEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VidMmSuspendAccessToAllocation(VIDMM_WORKER_THREAD *,VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400bb974  mov     r8, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400bb977  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400bb97a  mov     rcx, r14; this
0x1400bb97d  call    ?EvictAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::EvictAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400bb982  mov     rcx, [rbp+57h+var_B0]
0x1400bb986  mov     rdx, rbx
0x1400bb989  mov     rax, [rcx]
0x1400bb98c  mov     rax, [rax+0C8h]
0x1400bb993  call    _guard_dispatch_icall
0x1400bb998  mov     rax, [rsi+188h]
0x1400bb99f  mov     ecx, [rax]
0x1400bb9a1  bt      ecx, 11h
0x1400bb9a5  jnb     short loc_1400BB9AD
0x1400bb9a7  mov     r9d, [r15+20h]
0x1400bb9ab  jmp     short loc_1400BB9C3
0x1400bb9ad  bt      ecx, 1Eh
0x1400bb9b1  jb      short loc_1400BB9BD
0x1400bb9b3  mov     r9d, 4
0x1400bb9b9  test    ecx, ecx
0x1400bb9bb  jns     short loc_1400BB9C3
0x1400bb9bd  mov     r9d, 3
0x1400bb9c3  cmp     qword ptr [r15+28h], 0FFFFFFFFFFFFFFFFh
0x1400bb9c8  jz      short loc_1400BB9CE
0x1400bb9ca  or      dword ptr [rsi+1Ch], 4
0x1400bb9ce  mov     rax, [r15+28h]
0x1400bb9d2  lea     rcx, [rbx+40h]
0x1400bb9d6  mov     [rsp+100h+var_C0], rax
0x1400bb9db  lea     rdx, [rbx+48h]
0x1400bb9df  mov     eax, [r15+24h]
0x1400bb9e3  mov     r8, rdi
0x1400bb9e6  mov     [rsp+100h+var_C8], eax
0x1400bb9ea  mov     al, [rbx+34h]
0x1400bb9ed  mov     [rsp+100h+var_D0], rcx
0x1400bb9f2  mov     rcx, r14
0x1400bb9f5  mov     [rsp+100h+var_D8], rdx
0x1400bb9fa  mov     rdx, rbx
0x1400bb9fd  mov     byte ptr [rsp+100h+var_E0], al
0x1400bba01  call    ?PageInOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@W4VIDMM_PLACEMENT_RESTRICTION@@_NPEA_NPEAPEAU3@I_K@Z; VIDMM_GLOBAL::PageInOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,VIDMM_PLACEMENT_RESTRICTION,bool,bool *,VIDMM_ALLOC * *,uint,unsigned __int64)
0x1400bba06  and     dword ptr [rsi+1Ch], 0FFFFFFFBh
0x1400bba0a  mov     r13d, eax
0x1400bba0d  test    eax, eax
0x1400bba0f  js      short loc_1400BBA1C
0x1400bba11  mov     rax, [rsi+188h]
0x1400bba18  lock inc dword ptr [rax+10h]
0x1400bba1c  mov     rcx, r14; this
0x1400bba1f  call    ?RecommitTrimmedList@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::RecommitTrimmedList(void)
0x1400bba24  jmp     loc_1400BBD29
0x1400bba29  mov     r8, [r15+20h]; struct VIDSCH_DEVICE_COMMAND_UPDATEGPUVA *
0x1400bba2d  lea     r9, [rbx+40h]; struct VIDMM_ALLOC **
0x1400bba31  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400bba34  mov     rcx, r14; this
0x1400bba37  call    ?UpdateGpuVirtualAddressSystemCommand@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDSCH_DEVICE_COMMAND_UPDATEGPUVA@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::UpdateGpuVirtualAddressSystemCommand(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDSCH_DEVICE_COMMAND_UPDATEGPUVA *,VIDMM_ALLOC * *)
0x1400bba3c  jmp     short loc_1400BBA51
0x1400bba3e  lea     r9, [rbx+40h]; struct VIDMM_ALLOC **
0x1400bba42  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400bba45  lea     r8, [r15+20h]; struct VIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE *
0x1400bba49  mov     rcx, r14; this
0x1400bba4c  call    ?CommitVirtualAddressRangeSystemCommand@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::CommitVirtualAddressRangeSystemCommand(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE *,VIDMM_ALLOC * *)
0x1400bba51  mov     r13d, eax
0x1400bba54  cmp     eax, 0C000022Dh
0x1400bba59  jnz     loc_1400BBD29
0x1400bba5f  mov     byte ptr [rbx+48h], 1
0x1400bba63  jmp     loc_1400BBD29
0x1400bba68  mov     rax, [rsi+188h]
0x1400bba6f  mov     rcx, rdi; this
0x1400bba72  movzx   r8d, word ptr [rax+8]
0x1400bba77  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x1400bba7c  test    al, al
  ... truncated ...
```
