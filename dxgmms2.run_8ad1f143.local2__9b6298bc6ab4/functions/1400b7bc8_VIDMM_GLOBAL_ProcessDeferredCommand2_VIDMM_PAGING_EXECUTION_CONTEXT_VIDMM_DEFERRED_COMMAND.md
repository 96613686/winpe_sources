# VIDMM_GLOBAL::ProcessDeferredCommand2(VIDMM_PAGING_EXECUTION_CONTEXT *,_VIDMM_DEFERRED_COMMAND *)

- ea: `0x1400b7bc8`
- end: `0x1400b836c`
- name: `?ProcessDeferredCommand2@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAU_VIDMM_DEFERRED_COMMAND@@@Z`
- size: `1956`
- prototype: `__int64 __fastcall(VIDMM_GLOBAL *__hidden this, struct VIDMM_PAGING_EXECUTION_CONTEXT *, struct _VIDMM_DEFERRED_COMMAND *)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400d10b0`

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
- `0x140058680`
- `0x140058760`
- `0x140095bc4`
- `0x140098f38`
- `0x140099408`
- `0x14009a958`
- `0x1400a52b8`
- `0x1400a61a4`
- `0x1400a9c40`
- `0x1400a9efc`
- `0x1400b395c`
- `0x1400b4ae0`
- `0x1400b7928`
- `0x1400b7bc8`
- `0x1400b9cc4`
- `0x1400c0894`
- `0x1400e6a00`
- `0x1400e6f1c`
- `0x1400ff9e8`
- `0x1400ffb48`
- `0x140113110`
- `0x14011331c`
- `0x140116d3c`
- `0x14011b07c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400b817b`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b817b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b7ec0`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b7f1c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b7f68`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b7ec0`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b7f1c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b7f68`
- `watchdog!WdLogSingleEntry5` at `0x1400b814e`
- `watchdog!WdLogSingleEntry5` at `0x1400b814e`
- `watchdog!WdLogSingleEntry1` at `0x1400b7e2a`
- `watchdog!WdLogSingleEntry1` at `0x1400b7e2a`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400b8128`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b7eb1`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b7f10`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b7f5c`

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
  int v15; // r8d
  unsigned int v16; // ecx
  unsigned int v17; // ecx
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
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
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
  v15 = *(_DWORD *)a3;
  if ( v15 <= 210 )
  {
    switch ( v15 )
    {
      case 210:
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
      case 113:
        updated = VIDMM_GLOBAL::CommitVirtualAddressRangeSystemCommand(
                    this,
                    a2,
                    (struct _VIDMM_DEFERRED_COMMAND *)((char *)a3 + 32),
                    (struct VIDMM_ALLOC **)a2 + 8);
        break;
      case 119:
        updated = VIDMM_GLOBAL::UpdateGpuVirtualAddressSystemCommand(
                    this,
                    a2,
                    *((struct VIDSCH_DEVICE_COMMAND_UPDATEGPUVA **)a3 + 4),
                    (struct VIDMM_ALLOC **)a2 + 8);
        break;
      case 203:
        if ( g_IsInternalReleaseOrDbg )
        {
          *(_QWORD *)(WdLogNewEntry5_WdTrace((unsigned int)(v15 - 203), v13) + 24) = v3;
          WdLogGlobalForLineNumber = 12887;
        }
        if ( BYTE1(v8[5].LowPart) )
        {
          return (unsigned int)-1071775482;
        }
        else
        {
          if ( !*(_DWORD *)(v8[48].QuadPart + 16) )
          {
            QuadPart = (int *)v8[48].QuadPart;
            if ( (*QuadPart & 0x20000) == 0 )
            {
              if ( g_IsInternalReleaseOrDbg )
              {
                WdLogNewEntry5_WdTrace(QuadPart, v13);
                WdLogGlobalForLineNumber = 12910;
                QuadPart = (int *)v8[48].QuadPart;
              }
              if ( (*(_DWORD *)(Interval.QuadPart + 64) & 1) != 0 )
              {
                v24 = *QuadPart;
                if ( (*QuadPart & 0x40000000) == 0 && ((v24 & 0x20000000) == 0 || v24 >= 0) && (v24 & 0x80000) == 0 )
                {
                  if ( g_IsInternalReleaseOrDbg )
                  {
                    WdLogNewEntry5_WdTrace(QuadPart, v13);
                    WdLogGlobalForLineNumber = 12923;
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
          v25 = *(_DWORD *)v8[48].QuadPart;
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
            _InterlockedIncrement((volatile signed __int32 *)(v8[48].QuadPart + 16));
          VIDMM_GLOBAL::RecommitTrimmedList(this);
        }
        return v12;
      case 206:
        if ( (int)v8[23].LowPart > 0
          && (unsigned __int8)NeedsApertureForLock(this, v8)
          && ((unsigned __int8)v8[3].LowPart & v22) == 0 )
        {
          WdLogSingleEntry1(v21, v20);
          WdLogGlobalForLineNumber = 12991;
          return (unsigned int)-1073741823;
        }
LABEL_33:
        if ( VIDMM_ALLOC::HasAnyResidencyReferences((VIDMM_ALLOC *)v3) && *(_WORD *)(v8[48].QuadPart + 8) < 2u )
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
  if ( v15 == 211 )
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
    WdLogSingleEntry5(0, 270, 5);
    WdLogGlobalForLineNumber = 222;
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
0x1400b7bc8  mov     [rsp-8+arg_18], rbx
0x1400b7bcd  push    rbp
0x1400b7bce  push    rsi
0x1400b7bcf  push    rdi
0x1400b7bd0  push    r12
0x1400b7bd2  push    r13
0x1400b7bd4  push    r14
0x1400b7bd6  push    r15
0x1400b7bd8  lea     rbp, [rsp-27h]
0x1400b7bdd  sub     rsp, 0D0h
0x1400b7be4  mov     rax, cs:__security_cookie
0x1400b7beb  xor     rax, rsp
0x1400b7bee  mov     [rbp+57h+var_40], rax
0x1400b7bf2  mov     rdi, [r8+10h]
0x1400b7bf6  mov     r15, r8
0x1400b7bf9  mov     rbx, rdx
0x1400b7bfc  mov     r14, rcx
0x1400b7bff  test    rdi, rdi
0x1400b7c02  jz      short loc_1400B7C29
0x1400b7c04  mov     rdx, [rdi]
0x1400b7c07  mov     rax, [r14+8E80h]
0x1400b7c0e  mov     [rbp+57h+var_90], rdx
0x1400b7c12  mov     rsi, [rdx]
0x1400b7c15  mov     r11, [rsi]
0x1400b7c18  mov     ecx, [r11+3Ch]
0x1400b7c1c  shr     rcx, 2
0x1400b7c20  and     ecx, 3Fh
0x1400b7c23  mov     r9, [rax+rcx*8]
0x1400b7c27  jmp     short loc_1400B7C39
0x1400b7c29  xor     r11d, r11d
0x1400b7c2c  mov     [rbp+57h+var_90], 0
0x1400b7c34  xor     r9d, r9d
0x1400b7c37  xor     esi, esi
0x1400b7c39  mov     r12, [r8+8]
0x1400b7c3d  xor     r13d, r13d
0x1400b7c40  mov     [rbp+57h+var_B0], r9
0x1400b7c44  mov     qword ptr [rbp+57h+Interval], r11
0x1400b7c48  test    r12, r12
0x1400b7c4b  jnz     short loc_1400B7C51
0x1400b7c4d  mov     r12, [rdi+8]
0x1400b7c51  mov     rdx, [r12+20h]
0x1400b7c56  mov     r10d, 1
0x1400b7c5c  test    rdx, rdx
0x1400b7c5f  jz      short loc_1400B7C78
0x1400b7c61  cmp     [rdx+0D4h], r13b
0x1400b7c68  jnz     short loc_1400B7C84
0x1400b7c6a  xor     ecx, ecx
0x1400b7c6c  xor     eax, eax
0x1400b7c6e  lock cmpxchg [rdx+0D0h], ecx
0x1400b7c76  jnz     short loc_1400B7C84
0x1400b7c78  mov     rcx, r14; this
0x1400b7c7b  call    ?IsTdrPending@VIDMM_GLOBAL@@QEBAEXZ; VIDMM_GLOBAL::IsTdrPending(void)
0x1400b7c80  test    al, al
0x1400b7c82  jz      short loc_1400B7C90
0x1400b7c84  mov     dword ptr [r8+54h], 0C01E0200h
0x1400b7c8c  mov     [r8+50h], r10b
0x1400b7c90  movsxd  r8, dword ptr [r8]
0x1400b7c93  mov     eax, 0D2h
0x1400b7c98  cmp     r8d, eax
0x1400b7c9b  jg      loc_1400B80F0
0x1400b7ca1  jz      loc_1400B8080
0x1400b7ca7  mov     ecx, r8d
0x1400b7caa  sub     ecx, 71h ; 'q'
0x1400b7cad  jz      loc_1400B8056
0x1400b7cb3  sub     ecx, 6
0x1400b7cb6  jz      loc_1400B8041
0x1400b7cbc  sub     ecx, 54h ; 'T'
0x1400b7cbf  jz      loc_1400B7EB1
0x1400b7cc5  mov     r9d, 3
0x1400b7ccb  sub     ecx, r9d
0x1400b7cce  jz      loc_1400B7E06
0x1400b7cd4  sub     ecx, r10d
0x1400b7cd7  jz      loc_1400B7DD5
0x1400b7cdd  sub     ecx, r10d
0x1400b7ce0  jz      short loc_1400B7D13
0x1400b7ce2  cmp     ecx, r10d
0x1400b7ce5  jnz     loc_1400B8128
0x1400b7ceb  lea     r9, [rbx+48h]
0x1400b7cef  mov     r8, rdi; struct VIDMM_ALLOC *
0x1400b7cf2  lea     rax, [rbx+40h]
0x1400b7cf6  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400b7cf9  mov     [rsp+100h+var_D8], rax; struct VIDMM_ALLOC **
0x1400b7cfe  mov     rcx, r14; this
0x1400b7d01  mov     [rsp+100h+var_E0], r9; bool *
0x1400b7d06  mov     r9b, r10b; bool
0x1400b7d09  call    ?InitContextAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_NPEA_NPEAPEAU3@@Z; VIDMM_GLOBAL::InitContextAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool,bool *,VIDMM_ALLOC * *)
0x1400b7d0e  jmp     loc_1400B7EA9
0x1400b7d13  lea     r12, [r15+2Dh]
0x1400b7d17  cmp     [r12], r13b
0x1400b7d1b  jnz     short loc_1400B7D97
0x1400b7d1d  mov     rcx, [rbp+57h+var_B0]
0x1400b7d21  mov     r8, r11
0x1400b7d24  mov     rdx, rbx
0x1400b7d27  mov     rax, [rcx]
0x1400b7d2a  mov     rax, [rax+0D8h]
0x1400b7d31  call    _guard_dispatch_icall
0x1400b7d36  mov     rdx, [rbp+57h+var_90]
0x1400b7d3a  lea     rcx, [rbp+57h+var_80]; this
0x1400b7d3e  mov     r8b, 1; bool
0x1400b7d41  mov     rdx, [rdx+8]; struct VIDMM_PROCESS *
0x1400b7d45  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400b7d4a  lea     rdx, [rsi+140h]; struct DXGPUSHLOCKFAST *
0x1400b7d51  lea     rcx, [rbp+57h+Interval]; this
0x1400b7d55  call    ??0DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(DXGPUSHLOCKFAST &,bool)
0x1400b7d5a  mov     rax, [r15+20h]
0x1400b7d5e  mov     r8, rdi; struct VIDMM_ALLOC *
0x1400b7d61  mov     r9b, [r15+2Ch]; bool
0x1400b7d65  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400b7d68  mov     [rsp+100h+var_D0], r12; bool *
0x1400b7d6d  mov     rcx, r14; this
0x1400b7d70  mov     [rsp+100h+var_D8], rax; void **
0x1400b7d75  mov     eax, [r15+28h]
0x1400b7d79  mov     dword ptr [rsp+100h+var_E0], eax; unsigned int
0x1400b7d7d  call    ?LockInternal@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_NKPEAPEAXPEA_N@Z; VIDMM_GLOBAL::LockInternal(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool,ulong,void * *,bool *)
0x1400b7d82  lea     rcx, [rbp+57h+Interval]; this
0x1400b7d86  mov     r13d, eax
0x1400b7d89  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x1400b7d8e  lea     rcx, [rbp+57h+var_80]; this
0x1400b7d92  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400b7d97  cmp     byte ptr [r12], 0
0x1400b7d9c  jz      loc_1400B8341
0x1400b7da2  mov     [rsp+100h+var_C0], 0FFFFFFFFFFFFFFFFh
0x1400b7dab  lea     rax, [rbx+40h]
0x1400b7daf  mov     [rsp+100h+var_C8], 0
0x1400b7db7  lea     rcx, [rbx+48h]
0x1400b7dbb  mov     [rsp+100h+var_D0], rax
0x1400b7dc0  mov     r9d, 2
0x1400b7dc6  mov     [rsp+100h+var_D8], rcx
0x1400b7dcb  mov     byte ptr [rsp+100h+var_E0], 0
0x1400b7dd0  jmp     loc_1400B7E9B
0x1400b7dd5  mov     eax, [rdi+2B0h]
0x1400b7ddb  test    eax, eax
0x1400b7ddd  jnz     short loc_1400B7DFA
0x1400b7ddf  test    [rdi+19h], r10b
0x1400b7de3  jnz     short loc_1400B7DFA
0x1400b7de5  mov     r9b, [r15+20h]
0x1400b7de9  mov     r8, rdi; struct VIDMM_ALLOC *
0x1400b7dec  and     r9b, r10b; bool
0x1400b7def  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400b7df2  mov     rcx, r14; this
0x1400b7df5  call    ?EvictOneAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@_N@Z; VIDMM_GLOBAL::EvictOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,bool)
0x1400b7dfa  lock dec dword ptr [rdi+2BCh]
0x1400b7e01  jmp     loc_1400B8341
0x1400b7e06  mov     eax, [rsi+0B8h]
0x1400b7e0c  test    eax, eax
0x1400b7e0e  jle     short loc_1400B7E4B
0x1400b7e10  mov     rdx, rsi
0x1400b7e13  mov     rcx, r14
0x1400b7e16  call    NeedsApertureForLock
0x1400b7e1b  test    al, al
0x1400b7e1d  jz      short loc_1400B7E4B
0x1400b7e1f  mov     eax, [rsi+18h]
0x1400b7e22  test    r10b, al
0x1400b7e25  jnz     short loc_1400B7E4B
0x1400b7e27  mov     ecx, r9d
0x1400b7e2a  call    cs:__imp_WdLogSingleEntry1
0x1400b7e31  nop     dword ptr [rax+rax+00h]
0x1400b7e36  mov     cs:WdLogGlobalForLineNumber, 32BFh
0x1400b7e40  mov     r13d, 0C0000001h
0x1400b7e46  jmp     loc_1400B8341
0x1400b7e4b  mov     rcx, rdi; this
0x1400b7e4e  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x1400b7e53  test    al, al
0x1400b7e55  jz      loc_1400B8341
0x1400b7e5b  mov     rax, [rsi+180h]
0x1400b7e62  mov     edx, 2
0x1400b7e67  cmp     [rax+8], dx
0x1400b7e6b  jnb     loc_1400B8341
0x1400b7e71  mov     [rsp+100h+var_C0], 0FFFFFFFFFFFFFFFFh
0x1400b7e7a  lea     rax, [rbx+40h]
0x1400b7e7e  mov     [rsp+100h+var_C8], r13d
0x1400b7e83  lea     rcx, [rbx+48h]
0x1400b7e87  mov     [rsp+100h+var_D0], rax
0x1400b7e8c  xor     r9d, r9d
0x1400b7e8f  mov     al, [rbx+34h]
0x1400b7e92  mov     [rsp+100h+var_D8], rcx
0x1400b7e97  mov     byte ptr [rsp+100h+var_E0], al
0x1400b7e9b  mov     r8, rdi
0x1400b7e9e  mov     rdx, rbx
0x1400b7ea1  mov     rcx, r14
0x1400b7ea4  call    ?PageInOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@W4VIDMM_PLACEMENT_RESTRICTION@@_NPEA_NPEAPEAU3@I_K@Z; VIDMM_GLOBAL::PageInOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,VIDMM_PLACEMENT_RESTRICTION,bool,bool *,VIDMM_ALLOC * *,uint,unsigned __int64)
0x1400b7ea9  mov     r13d, eax
0x1400b7eac  jmp     loc_1400B8341
0x1400b7eb1  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b7eb8  xor     r12d, r12d
0x1400b7ebb  cmp     [rax], r12b
0x1400b7ebe  jz      short loc_1400B7EDA
0x1400b7ec0  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b7ec7  nop     dword ptr [rax+rax+00h]
0x1400b7ecc  mov     [rax+18h], rdi
0x1400b7ed0  mov     cs:WdLogGlobalForLineNumber, 3257h
0x1400b7eda  cmp     [rsi+29h], r12b
0x1400b7ede  jz      short loc_1400B7EEB
0x1400b7ee0  mov     r13d, 0C01E0106h
0x1400b7ee6  jmp     loc_1400B8341
0x1400b7eeb  mov     rax, [rsi+180h]
0x1400b7ef2  mov     ecx, [rax+10h]
0x1400b7ef5  test    ecx, ecx
0x1400b7ef7  jnz     loc_1400B7FB0
0x1400b7efd  mov     rcx, [rsi+180h]
0x1400b7f04  test    dword ptr [rcx], 20000h
0x1400b7f0a  jnz     loc_1400B7FB0
0x1400b7f10  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b7f17  cmp     [rax], r12b
0x1400b7f1a  jz      short loc_1400B7F39
0x1400b7f1c  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b7f23  nop     dword ptr [rax+rax+00h]
0x1400b7f28  mov     cs:WdLogGlobalForLineNumber, 326Eh
0x1400b7f32  mov     rcx, [rsi+180h]
0x1400b7f39  mov     rax, qword ptr [rbp+57h+Interval]
0x1400b7f3d  mov     eax, [rax+40h]
0x1400b7f40  test    al, 1
0x1400b7f42  jz      short loc_1400B7FB0
0x1400b7f44  mov     eax, [rcx]
0x1400b7f46  bt      eax, 1Eh
0x1400b7f4a  jb      short loc_1400B7FB0
0x1400b7f4c  bt      eax, 1Dh
0x1400b7f50  jnb     short loc_1400B7F56
0x1400b7f52  test    eax, eax
0x1400b7f54  js      short loc_1400B7FB0
0x1400b7f56  bt      eax, 13h
0x1400b7f5a  jb      short loc_1400B7FB0
0x1400b7f5c  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b7f63  cmp     [rax], r12b
0x1400b7f66  jz      short loc_1400B7F7E
0x1400b7f68  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b7f6f  nop     dword ptr [rax+rax+00h]
0x1400b7f74  mov     cs:WdLogGlobalForLineNumber, 327Bh
0x1400b7f7e  mov     rcx, [r14]; struct VIDMM_WORKER_THREAD *
0x1400b7f81  mov     r8, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400b7f84  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400b7f87  call    ?VidMmSuspendAccessToAllocation@@YAPEAVVIDMM_DEVICE@@PEAUVIDMM_WORKER_THREAD@@PEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VidMmSuspendAccessToAllocation(VIDMM_WORKER_THREAD *,VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400b7f8c  mov     r8, rsi; struct VIDMM_GLOBAL_ALLOC *
0x1400b7f8f  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400b7f92  mov     rcx, r14; this
0x1400b7f95  call    ?EvictAllocation@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_GLOBAL_ALLOC@@@Z; VIDMM_GLOBAL::EvictAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_GLOBAL_ALLOC *)
0x1400b7f9a  mov     rcx, [rbp+57h+var_B0]
0x1400b7f9e  mov     rdx, rbx
0x1400b7fa1  mov     rax, [rcx]
0x1400b7fa4  mov     rax, [rax+0C8h]
0x1400b7fab  call    _guard_dispatch_icall
0x1400b7fb0  mov     rax, [rsi+180h]
0x1400b7fb7  mov     ecx, [rax]
0x1400b7fb9  bt      ecx, 11h
0x1400b7fbd  jnb     short loc_1400B7FC5
0x1400b7fbf  mov     r9d, [r15+20h]
0x1400b7fc3  jmp     short loc_1400B7FDB
0x1400b7fc5  bt      ecx, 1Eh
0x1400b7fc9  jb      short loc_1400B7FD5
0x1400b7fcb  mov     r9d, 4
0x1400b7fd1  test    ecx, ecx
0x1400b7fd3  jns     short loc_1400B7FDB
0x1400b7fd5  mov     r9d, 3
0x1400b7fdb  cmp     qword ptr [r15+28h], 0FFFFFFFFFFFFFFFFh
0x1400b7fe0  jz      short loc_1400B7FE6
0x1400b7fe2  or      dword ptr [rsi+1Ch], 4
0x1400b7fe6  mov     rax, [r15+28h]
0x1400b7fea  lea     rcx, [rbx+40h]
0x1400b7fee  mov     [rsp+100h+var_C0], rax
0x1400b7ff3  lea     rdx, [rbx+48h]
0x1400b7ff7  mov     eax, [r15+24h]
0x1400b7ffb  mov     r8, rdi
0x1400b7ffe  mov     [rsp+100h+var_C8], eax
0x1400b8002  mov     al, [rbx+34h]
0x1400b8005  mov     [rsp+100h+var_D0], rcx
0x1400b800a  mov     rcx, r14
0x1400b800d  mov     [rsp+100h+var_D8], rdx
0x1400b8012  mov     rdx, rbx
0x1400b8015  mov     byte ptr [rsp+100h+var_E0], al
0x1400b8019  call    ?PageInOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_ALLOC@@W4VIDMM_PLACEMENT_RESTRICTION@@_NPEA_NPEAPEAU3@I_K@Z; VIDMM_GLOBAL::PageInOneAllocation(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_ALLOC *,VIDMM_PLACEMENT_RESTRICTION,bool,bool *,VIDMM_ALLOC * *,uint,unsigned __int64)
0x1400b801e  and     dword ptr [rsi+1Ch], 0FFFFFFFBh
0x1400b8022  mov     r13d, eax
0x1400b8025  test    eax, eax
0x1400b8027  js      short loc_1400B8034
0x1400b8029  mov     rax, [rsi+180h]
0x1400b8030  lock inc dword ptr [rax+10h]
0x1400b8034  mov     rcx, r14; this
0x1400b8037  call    ?RecommitTrimmedList@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::RecommitTrimmedList(void)
0x1400b803c  jmp     loc_1400B8341
0x1400b8041  mov     r8, [r15+20h]; struct VIDSCH_DEVICE_COMMAND_UPDATEGPUVA *
0x1400b8045  lea     r9, [rbx+40h]; struct VIDMM_ALLOC **
0x1400b8049  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400b804c  mov     rcx, r14; this
0x1400b804f  call    ?UpdateGpuVirtualAddressSystemCommand@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDSCH_DEVICE_COMMAND_UPDATEGPUVA@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::UpdateGpuVirtualAddressSystemCommand(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDSCH_DEVICE_COMMAND_UPDATEGPUVA *,VIDMM_ALLOC * *)
0x1400b8054  jmp     short loc_1400B8069
0x1400b8056  lea     r9, [rbx+40h]; struct VIDMM_ALLOC **
0x1400b805a  mov     rdx, rbx; struct VIDMM_PAGING_EXECUTION_CONTEXT *
0x1400b805d  lea     r8, [r15+20h]; struct VIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE *
0x1400b8061  mov     rcx, r14; this
0x1400b8064  call    ?CommitVirtualAddressRangeSystemCommand@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_EXECUTION_CONTEXT@@PEAUVIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::CommitVirtualAddressRangeSystemCommand(VIDMM_PAGING_EXECUTION_CONTEXT *,VIDMM_COMMIT_VIRTUAL_ADDRESS_RANGE *,VIDMM_ALLOC * *)
0x1400b8069  mov     r13d, eax
0x1400b806c  cmp     eax, 0C000022Dh
0x1400b8071  jnz     loc_1400B8341
0x1400b8077  mov     byte ptr [rbx+48h], 1
0x1400b807b  jmp     loc_1400B8341
0x1400b8080  mov     rax, [rsi+180h]
0x1400b8087  mov     rcx, rdi; this
0x1400b808a  movzx   r8d, word ptr [rax+8]
0x1400b808f  call    ?HasAnyResidencyReferences@VIDMM_ALLOC@@QEBA_NXZ; VIDMM_ALLOC::HasAnyResidencyReferences(void)
0x1400b8094  test    al, al
  ... truncated ...
```
