# RefsCleanupIrpContext(_IRP_CONTEXT *,ulong)

- ea: `0x140069750`
- end: `0x14006a0b4`
- name: `?RefsCleanupIrpContext@@YAXPEAU_IRP_CONTEXT@@K@Z`
- size: `2404`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, unsigned int)`
- caller_count: `33`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003ec10`
- `0x1400bbf74`
- `0x1400f0770`
- `0x1400f4428`
- `0x1400f4754`
- `0x1400f59bc`
- `0x1400f6580`
- `0x1400f68cc`
- `0x1400f6a34`
- `0x1400f6c04`
- `0x1400f6f00`
- `0x1400f76e8`
- `0x1400f7880`
- `0x140289084`
- `0x140295870`
- `0x1402c34f4`
- `0x1402c3ce0`
- `0x1402c3f70`
- `0x1402c8de0`
- `0x1402c8f60`
- `0x1402cc6f0`
- `0x1402d29c4`
- `0x1402e8ea0`
- `0x1402e8fd0`
- `0x1403012f0`
- `0x14030f3f0`
- `0x140313e40`
- `0x140325c50`
- `0x140326460`
- `0x140328060`
- `0x14032c290`
- `0x140330af8`
- `0x1403389e4`

## callees

- `0x140069750`
- `0x1400c8644`
- `0x140320020`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400699f8`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400699f8`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140069a10`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140069a10`
- `ntoskrnl!KeSetEvent` at `0x140069cca`
- `ntoskrnl!KeSetEvent` at `0x140069cca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400699a5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069c4a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069ec9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400699a5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069c4a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069ec9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006a074`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14006a074`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140069b95`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140069c7f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140069e0d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140069b95`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140069c7f`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140069e0d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140069ba4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140069c8e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140069e1c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140069ba4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140069c8e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140069e1c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140069be0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140069d68`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140069e5c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140069be0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140069d68`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140069e5c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140069bec`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140069d74`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140069e68`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140069bec`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140069d74`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140069e68`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140069a3f`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140069a3f`
- `ntoskrnl!ExReleaseFastResource` at `0x140069a62`
- `ntoskrnl!ExReleaseFastResource` at `0x140069ac4`
- `ntoskrnl!ExReleaseFastResource` at `0x140069d48`
- `ntoskrnl!ExReleaseFastResource` at `0x14006a00c`
- `ntoskrnl!ExReleaseFastResource` at `0x140069a62`
- `ntoskrnl!ExReleaseFastResource` at `0x140069ac4`
- `ntoskrnl!ExReleaseFastResource` at `0x140069d48`
- `ntoskrnl!ExReleaseFastResource` at `0x14006a00c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140069efa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a028`
- `ntoskrnl!ExReleaseResourceLite` at `0x140069efa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006a028`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400699e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a050`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a089`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a09c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400699e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a050`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a089`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a09c`

## pseudocode

```c
void __fastcall RefsCleanupIrpContext(PSECURITY_SUBJECT_CONTEXT *a1, int a2)
{
  PSECURITY_SUBJECT_CONTEXT v3; // rsi
  PSECURITY_SUBJECT_CONTEXT *v4; // r13
  int v5; // eax
  struct _IRP_CONTEXT *v6; // rbx
  __int16 v7; // r12
  char *v8; // rbp
  struct _IRP_CONTEXT *v9; // rcx
  PSECURITY_SUBJECT_CONTEXT v10; // rax
  __int16 v11; // r8
  struct _IRP_CONTEXT *v12; // r15
  _QWORD *v13; // rcx
  struct _IRP_CONTEXT *v14; // rax
  char *v15; // r15
  PSECURITY_SUBJECT_CONTEXT *v16; // rsi
  struct _KTHREAD *CurrentThread; // r9
  __int64 v18; // r8
  unsigned int j; // edx
  __int64 v20; // rcx
  PSECURITY_SUBJECT_CONTEXT *v21; // rax
  struct _IRP_CONTEXT *v22; // rsi
  struct _IRP_CONTEXT *v23; // rax
  PSECURITY_SUBJECT_CONTEXT *v24; // rbp
  PSECURITY_SUBJECT_CONTEXT *n; // rcx
  int v26; // ecx
  unsigned __int64 v27; // rax
  _QWORD **v28; // rbx
  _QWORD *v29; // rcx
  bool v30; // zf
  int v31; // eax
  PSECURITY_SUBJECT_CONTEXT v32; // rcx
  unsigned int v33; // eax
  struct _NPAGED_LOOKASIDE_LIST *v34; // r9
  _QWORD *v35; // rax
  PIRP TopLevelIrp; // rax
  IRP *MdlAddress; // rcx
  struct _IRP_CONTEXT *k; // rcx
  char IsFastResourceHeldExclusive; // al
  struct _ERESOURCE *v40; // rcx
  int v41; // ecx
  unsigned int v42; // ecx
  struct _IRP_CONTEXT **v43; // r15
  PSECURITY_SUBJECT_CONTEXT *v44; // r12
  PSECURITY_SUBJECT_CONTEXT v45; // rcx
  struct _FAST_MUTEX *v46; // rbx
  struct _IRP_CONTEXT *v47; // rcx
  struct _IRP_CONTEXT **v48; // rax
  unsigned int v49; // eax
  struct _FAST_MUTEX *PrimaryToken; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *v51; // rcx
  _QWORD *ClientToken; // rcx
  __int64 v53; // rcx
  struct _IRP_CONTEXT *m; // rax
  PSECURITY_SUBJECT_CONTEXT v55; // rdx
  struct _ERESOURCE *v56; // rcx
  PVOID *p_ProcessAuditId; // rdx
  struct _IRP_CONTEXT **v58; // r12
  struct _IRP_CONTEXT *i; // rax
  PSECURITY_SUBJECT_CONTEXT v60; // rcx
  struct _FAST_MUTEX *v61; // rsi
  struct _IRP_CONTEXT *v62; // rcx
  struct _IRP_CONTEXT **v63; // rax
  unsigned int v64; // eax
  __int16 v65; // [rsp+70h] [rbp+8h]
  struct _IRP_CONTEXT *v67; // [rsp+80h] [rbp+18h]
  PSECURITY_SUBJECT_CONTEXT *v68; // [rsp+88h] [rbp+20h]

  if ( a1[6] )
    RefsReleaseSharedResources((struct _IRP_CONTEXT *)a1);
  v3 = a1[7];
  v4 = 0;
  if ( !v3 )
    goto LABEL_4;
  if ( LOWORD(v3->ClientToken) != 2050 )
  {
    a1[7] = 0;
    PrimaryToken = (struct _FAST_MUTEX *)v3[1].PrimaryToken;
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(PrimaryToken);
    v51 = v3 + 14;
    if ( v51->ClientToken == v51 )
    {
      v3[13].ProcessAuditId = 0;
    }
    else
    {
      ClientToken = v51->ClientToken;
      v3[13].ProcessAuditId = (PVOID)((unsigned __int64)v3[13].ProcessAuditId | 3);
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(ClientToken);
      *(_QWORD *)(v53 + 8) = 0;
      *(_QWORD *)v53 = 0;
      KeSetEvent((PRKEVENT)(v53 + 16), 0, 0);
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)v3[1].PrimaryToken);
    KeLeaveGuardedRegion();
LABEL_105:
    a1[7] = 0;
    goto LABEL_4;
  }
  v55 = a1[13];
  v56 = (struct _ERESOURCE *)v3[3].ClientToken;
  if ( v55[10].PrimaryToken != v56 || !LODWORD(v55[10].ClientToken) || (p_ProcessAuditId = &v55[7].ProcessAuditId) == 0 )
  {
    ExReleaseResourceLite(v56);
    a1[7] = 0;
    goto LABEL_4;
  }
  v30 = (*((_DWORD *)p_ProcessAuditId + 18))-- == 1;
  if ( !v30 )
    goto LABEL_105;
  *((_DWORD *)p_ProcessAuditId + 19) &= ~2u;
  ExReleaseFastResource(v56, p_ProcessAuditId);
  a1[7] = 0;
LABEL_4:
  v5 = *((_DWORD *)a1 + 1);
  if ( (v5 & 0x2000) != 0 )
  {
    *((_DWORD *)a1 + 1) = v5 & 0xFFFFCFFF;
    ExReleaseFastResource(&a1[8][37].ProcessAuditId, 0);
  }
  v6 = (struct _IRP_CONTEXT *)a1[14];
  while ( v6 != (struct _IRP_CONTEXT *)(a1 + 14) )
  {
    v7 = *((_WORD *)v6 - 18);
    v8 = (char *)v6 - 64;
    v9 = v6;
    v67 = v6;
    v6 = *(struct _IRP_CONTEXT **)v6;
    v65 = v7;
    while ( 2 )
    {
      if ( !*(_QWORD *)v9 )
        goto LABEL_19;
      if ( *((_WORD *)v8 + 14) != 1 )
        goto LABEL_18;
      v10 = a1[3];
      if ( v10 && v10[4].PrimaryToken && ((*((_DWORD *)v8 + 2) & 0x8000LL) == 0 || (*((_DWORD *)a1 + 1) & 0x1000) != 0) )
        goto LABEL_60;
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v9);
      v12 = (struct _IRP_CONTEXT *)(a1 + 80);
      v13[1] = 0;
      *v13 = 0;
      v14 = (struct _IRP_CONTEXT *)a1[80];
      if ( v14 == (struct _IRP_CONTEXT *)(a1 + 80) )
        goto LABEL_18;
      while ( v14 != v12 )
      {
        if ( *((_WORD *)v14 - 4) == v11 )
        {
          v4 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v14 - 8);
          break;
        }
        v14 = *(struct _IRP_CONTEXT **)v14;
      }
      if ( !v4 )
        goto LABEL_17;
      do
      {
        v58 = (struct _IRP_CONTEXT **)(v4 + 1);
        v68 = 0;
        if ( *(struct _IRP_CONTEXT **)v12 != v12 )
        {
          for ( i = *v58; ; i = *(struct _IRP_CONTEXT **)i )
          {
            v58 = (struct _IRP_CONTEXT **)(v4 + 1);
            if ( i == v12 )
              break;
            if ( *((_WORD *)i - 4) == v11 )
            {
              v68 = (PSECURITY_SUBJECT_CONTEXT *)((char *)i - 8);
              break;
            }
          }
        }
        v60 = v4[6];
        if ( v60 )
        {
          if ( *(char **)&v60[4].ImpersonationLevel != v8 )
            goto LABEL_122;
          if ( (((__int64)v60[4].ProcessAuditId & 0x2000) != 0 || (*(&v60[9].ImpersonationLevel + 1) & 0x40) != 0)
            && ((__int64)v60[4].ProcessAuditId & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)&v60[4].ProcessAuditId, 0xFFFFDFFF);
          }
          v61 = (struct _FAST_MUTEX *)v4[6][1].PrimaryToken;
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v61);
          _InterlockedIncrement((volatile signed __int32 *)&v4[6][5].ImpersonationLevel + 1);
          v4[6][8].ProcessAuditId = 0;
          ++*((_DWORD *)&v4[6][5].ImpersonationLevel + 1);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)v4[6][1].PrimaryToken);
          KeLeaveGuardedRegion();
        }
        v62 = *v58;
        if ( *((struct _IRP_CONTEXT ***)*v58 + 1) != v58 )
          goto LABEL_130;
        v63 = (struct _IRP_CONTEXT **)v58[1];
        if ( *v63 != (struct _IRP_CONTEXT *)v58 )
          goto LABEL_130;
        *v63 = v62;
        *((_QWORD *)v62 + 1) = v63;
        if ( v4 != a1 + 91 )
        {
          v64 = *((_DWORD *)v4 - 2);
          if ( v64 >= RefsNumberProcessors )
            v64 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v64], v4 - 1);
        }
LABEL_122:
        v11 = 2087;
        v4 = v68;
      }
      while ( v68 );
      v7 = v65;
LABEL_17:
      v4 = 0;
LABEL_18:
      --*((_WORD *)v8 + 14);
LABEL_19:
      if ( *(_WORD *)v8 == 2050 )
        v15 = v8;
      else
        v15 = (char *)*((_QWORD *)v8 + 17);
      v16 = 0;
      CurrentThread = KeGetCurrentThread();
      v18 = *((_QWORD *)v15 + 11) + 64LL;
      for ( j = 0; j < 2; ++j )
      {
        v20 = 14LL * j;
        v21 = &a1[v20 + 44];
        if ( *v21 == (PSECURITY_SUBJECT_CONTEXT)v18 && a1[v20 + 45] == (PSECURITY_SUBJECT_CONTEXT)CurrentThread )
        {
          v16 = &a1[v20 + 44];
          if ( v21 )
            goto LABEL_56;
          break;
        }
      }
      for ( k = (struct _IRP_CONTEXT *)a1[72]; k != (struct _IRP_CONTEXT *)(a1 + 72); k = *(struct _IRP_CONTEXT **)k )
      {
        if ( *((_QWORD *)k - 12) == v18 && *((struct _KTHREAD **)k - 11) == CurrentThread )
        {
          v16 = (PSECURITY_SUBJECT_CONTEXT *)((char *)k - 96);
          break;
        }
      }
LABEL_56:
      IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(v18);
      if ( v16 )
      {
        v41 = *((_DWORD *)v16 + 4);
        if ( IsFastResourceHeldExclusive )
        {
          if ( v41 )
          {
            *((_DWORD *)v16 + 4) = v41 - 1;
            if ( v41 == 1 )
            {
LABEL_64:
              *v16 = 0;
              v16[1] = 0;
            }
          }
        }
        else
        {
          *((_DWORD *)v16 + 4) = v41 - 1;
          if ( v41 == 1 )
            goto LABEL_64;
        }
        ExReleaseFastResource(*((_QWORD *)v15 + 11) + 64LL, v16 + 3);
        goto LABEL_59;
      }
      v40 = (struct _ERESOURCE *)(*((_QWORD *)v15 + 11) + 64LL);
      if ( IsFastResourceHeldExclusive )
        ExReleaseFastResource(v40, 0);
      else
        ExReleaseResourceLite(v40);
LABEL_59:
      v9 = v67;
LABEL_60:
      v30 = v7-- == 1;
      v65 = v7;
      if ( !v30 )
        continue;
      break;
    }
  }
  v22 = (struct _IRP_CONTEXT *)(a1 + 80);
  v23 = (struct _IRP_CONTEXT *)a1[80];
  if ( v23 != (struct _IRP_CONTEXT *)(a1 + 80) )
  {
    v24 = 0;
    while ( v23 != v22 )
    {
      if ( *((_WORD *)v23 - 4) == 2087 )
      {
        v24 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v23 - 8);
        break;
      }
      v23 = *(struct _IRP_CONTEXT **)v23;
    }
    if ( v24 )
    {
      while ( 1 )
      {
        v43 = (struct _IRP_CONTEXT **)(v24 + 1);
        v44 = 0;
        if ( *(struct _IRP_CONTEXT **)v22 != v22 )
        {
          for ( m = *v43; ; m = *(struct _IRP_CONTEXT **)m )
          {
            v43 = (struct _IRP_CONTEXT **)(v24 + 1);
            if ( m == v22 )
              break;
            if ( *((_WORD *)m - 4) == 2087 )
            {
              v44 = (PSECURITY_SUBJECT_CONTEXT *)((char *)m - 8);
              break;
            }
          }
        }
        v45 = v24[6];
        if ( v45 )
        {
          if ( (((__int64)v45[4].ProcessAuditId & 0x2000) != 0 || (*(&v45[9].ImpersonationLevel + 1) & 0x40) != 0)
            && ((__int64)v45[4].ProcessAuditId & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)&v45[4].ProcessAuditId, 0xFFFFDFFF);
          }
          v46 = (struct _FAST_MUTEX *)v24[6][1].PrimaryToken;
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v46);
          _InterlockedIncrement((volatile signed __int32 *)&v24[6][5].ImpersonationLevel + 1);
          v24[6][8].ProcessAuditId = 0;
          ++*((_DWORD *)&v24[6][5].ImpersonationLevel + 1);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)v24[6][1].PrimaryToken);
          KeLeaveGuardedRegion();
        }
        v47 = *v43;
        if ( *((struct _IRP_CONTEXT ***)*v43 + 1) != v43
          || (v48 = (struct _IRP_CONTEXT **)v43[1], *v48 != (struct _IRP_CONTEXT *)v43) )
        {
LABEL_130:
          __fastfail(3u);
        }
        *v48 = v47;
        *((_QWORD *)v47 + 1) = v48;
        if ( v24 != a1 + 91 )
        {
          v49 = *((_DWORD *)v24 - 2);
          if ( v49 >= RefsNumberProcessors )
            v49 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v49], v24 - 1);
        }
        if ( !v44 )
          break;
        v24 = v44;
      }
    }
  }
  for ( n = (PSECURITY_SUBJECT_CONTEXT *)a1[75]; n; n = (PSECURITY_SUBJECT_CONTEXT *)a1[75] )
  {
    a1[75] = *n;
    ExFreePoolWithTag(n, 0);
  }
  v26 = *((_DWORD *)a1 + 1);
  if ( (v26 & 0x400) != 0 || (v27 = (unsigned __int64)a1[1], (v27 & 0x10000) != 0) )
  {
    if ( (v26 & 0x40000) != 0 )
    {
      *((_DWORD *)a1 + 1) = v26 & 0xFFFBFBFF;
    }
    else
    {
      if ( a2 )
        v42 = v26 & 0xBFF9C0C5;
      else
        v42 = v26 & 0xF779C0CD;
      *((_DWORD *)a1 + 1) = v42;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFFFFBFFuLL);
    }
    *((_DWORD *)a1 + 4) = 0;
  }
  else
  {
    if ( (v27 & 0x20000000000LL) != 0 )
    {
      *((_DWORD *)a1 + 59) &= ~1u;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)(v27 & 0xFFFFFDFFFFFFFFFFuLL);
    }
    if ( a1[42] )
    {
      *((_DWORD *)a1 + 81) &= ~1u;
      a1[42] = 0;
    }
    v28 = (_QWORD **)(a1 + 72);
    while ( 1 )
    {
      v29 = *v28;
      if ( *v28 == v28 )
        break;
      if ( (_QWORD **)v29[1] != v28 )
        goto LABEL_130;
      v35 = (_QWORD *)*v29;
      if ( *(_QWORD **)(*v29 + 8LL) != v29 )
        goto LABEL_130;
      *v28 = v35;
      v35[1] = v28;
      ExFreePoolWithTag(v29 - 12, 0);
    }
    a1[44] = 0;
    a1[58] = 0;
    v30 = ((_BYTE)a1[1] & 0x20) == 0;
    *((_DWORD *)a1 + 148) = 0;
    if ( !v30 )
    {
      SeReleaseSubjectContext(a1[18]);
      ExFreePoolWithTag(a1[18], 0);
    }
    v31 = *((_DWORD *)a1 + 2);
    a1[18] = 0;
    if ( (*(_QWORD *)&v31 & 0x100000LL) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      MdlAddress = (IRP *)TopLevelIrp->MdlAddress;
      *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
      *(_QWORD *)&TopLevelIrp->Flags = 0;
      IoSetTopLevelIrp(MdlAddress);
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFEFFFFFuLL);
    }
    v32 = a1[89];
    if ( v32 )
    {
      ExFreePoolWithTag(v32, 0);
      a1[89] = 0;
    }
    if ( ((_DWORD)a1[1] & 0x80000LL) != 0 )
    {
      v33 = *((_DWORD *)a1 - 2);
      if ( *((_WORD *)a1 + 1) == 1664 )
      {
        v34 = RefsIrpAndIoContextLookasideList;
        if ( v33 >= RefsNumberProcessors )
          goto LABEL_75;
      }
      else
      {
        v34 = RefsIrpContextLookasideList;
        if ( v33 < RefsNumberProcessors )
          goto LABEL_49;
LABEL_75:
        v33 %= RefsNumberProcessors;
      }
LABEL_49:
      ExFreeToNPagedLookasideList(&v34[(unsigned __int64)v33], a1 - 1);
    }
  }
}

```

## disassembly

```asm
0x140069750  mov     [rsp+arg_8], edx
0x140069754  push    rbx
0x140069755  push    rbp
0x140069756  push    rsi
0x140069757  push    rdi
0x140069758  push    r12
0x14006975a  push    r13
0x14006975c  push    r14
0x14006975e  push    r15
0x140069760  sub     rsp, 28h
0x140069764  cmp     qword ptr [rcx+30h], 0
0x140069769  mov     rdi, rcx
0x14006976c  jz      short loc_140069773
0x14006976e  call    ?RefsReleaseSharedResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseSharedResources(_IRP_CONTEXT *)
0x140069773  mov     rsi, [rdi+38h]
0x140069777  xor     r13d, r13d
0x14006977a  mov     r15d, 802h
0x140069780  test    rsi, rsi
0x140069783  jnz     loc_140069C6D
0x140069789  mov     eax, [rdi+4]
0x14006978c  bt      eax, 0Dh
0x140069790  jb      loc_140069FF7
0x140069796  mov     rbx, [rdi+70h]
0x14006979a  lea     r14, [rdi+70h]
0x14006979e  mov     r8d, 827h
0x1400697a4  cmp     rbx, r14
0x1400697a7  jz      loc_14006987E
0x1400697ad  movzx   r12d, word ptr [rbx-24h]
0x1400697b2  lea     rbp, [rbx-40h]
0x1400697b6  mov     rcx, rbx
0x1400697b9  mov     [rsp+68h+arg_10], rbx
0x1400697c1  mov     rbx, [rbx]
0x1400697c4  mov     eax, 0FFFFh
0x1400697c9  mov     [rsp+68h+arg_0], r12w
0x1400697cf  cmp     qword ptr [rcx], 0
0x1400697d3  jz      short loc_140069833
0x1400697d5  cmp     word ptr [rbp+1Ch], 1
0x1400697da  jnz     short loc_14006982F
0x1400697dc  mov     rax, [rdi+18h]
0x1400697e0  test    rax, rax
0x1400697e3  jnz     loc_140069F0F
0x1400697e9  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x1400697ee  lea     r15, [rdi+280h]
0x1400697f5  mov     [rcx+8], r13
0x1400697f9  mov     [rcx], r13
0x1400697fc  mov     rax, [r15]
0x1400697ff  cmp     rax, r15
0x140069802  jz      short loc_140069824
0x140069804  cmp     rax, r15
0x140069807  jz      short loc_140069818
0x140069809  cmp     [rax-8], r8w
0x14006980e  jnz     loc_140069F57
0x140069814  lea     r13, [rax-8]
0x140069818  test    r13, r13
0x14006981b  jnz     loc_140069D90
0x140069821  xor     r13d, r13d
0x140069824  mov     eax, 0FFFFh
0x140069829  mov     r15d, 802h
0x14006982f  add     [rbp+1Ch], ax
0x140069833  cmp     [rbp+0], r15w
0x140069838  jnz     loc_140069B3A
0x14006983e  mov     r15, rbp
0x140069841  mov     r8, [r15+58h]
0x140069845  mov     rsi, r13
0x140069848  mov     r9, gs:188h
0x140069851  add     r8, 40h ; '@'
0x140069855  mov     edx, r13d
0x140069858  cmp     edx, 2
0x14006985b  jnb     loc_140069A29
0x140069861  mov     eax, edx
0x140069863  imul    rcx, rax, 70h ; 'p'
0x140069867  lea     rax, [rdi+160h]
0x14006986e  add     rax, rcx
0x140069871  cmp     [rax], r8
0x140069874  jz      loc_140069B01
0x14006987a  inc     edx
0x14006987c  jmp     short loc_140069858
0x14006987e  lea     rsi, [rdi+280h]
0x140069885  mov     rax, [rsi]
0x140069888  cmp     rax, rsi
0x14006988b  jz      short loc_1400698AD
0x14006988d  mov     rbp, r13
0x140069890  cmp     rax, rsi
0x140069893  jz      short loc_1400698A4
0x140069895  cmp     [rax-8], r8w
0x14006989a  jnz     loc_140069F3D
0x1400698a0  lea     rbp, [rax-8]
0x1400698a4  test    rbp, rbp
0x1400698a7  jnz     loc_140069B50
0x1400698ad  mov     rcx, [rdi+258h]; P
0x1400698b4  test    rcx, rcx
0x1400698b7  jnz     loc_14006A044
0x1400698bd  mov     ecx, [rdi+4]
0x1400698c0  bt      ecx, 0Ah
0x1400698c4  jb      loc_140069AD2
0x1400698ca  mov     rax, [rdi+8]
0x1400698ce  bt      rax, 10h
0x1400698d3  jb      loc_140069AD2
0x1400698d9  bt      rax, 29h ; ')'
0x1400698de  jnb     short loc_1400698F8
0x1400698e0  and     dword ptr [rdi+0ECh], 0FFFFFFFEh
0x1400698e7  mov     rcx, 0FFFFFDFFFFFFFFFFh
0x1400698f1  and     rax, rcx
0x1400698f4  mov     [rdi+8], rax
0x1400698f8  cmp     qword ptr [rdi+150h], 0
0x140069900  jz      short loc_140069910
0x140069902  and     dword ptr [rdi+144h], 0FFFFFFFEh
0x140069909  mov     [rdi+150h], r13
0x140069910  lea     rbx, [rdi+240h]
0x140069917  mov     rcx, [rbx]
0x14006991a  cmp     rcx, rbx
0x14006991d  jnz     loc_1400699C3
0x140069923  mov     [rdi+160h], r13
0x14006992a  mov     [r14+160h], r13
0x140069931  test    byte ptr [rdi+8], 20h
0x140069935  mov     [rdi+250h], r13d
0x14006993c  jnz     loc_14006A06D
0x140069942  mov     eax, [rdi+8]
0x140069945  mov     [rdi+90h], r13
0x14006994c  bt      rax, 14h
0x140069951  jb      loc_1400699F8
0x140069957  mov     rcx, [rdi+2C8h]; P
0x14006995e  test    rcx, rcx
0x140069961  jnz     loc_14006A09A
0x140069967  mov     eax, [rdi+8]
0x14006996a  bt      rax, 13h
0x14006996f  jnb     short loc_1400699B1
0x140069971  mov     eax, [rdi-8]
0x140069974  mov     ecx, 680h
0x140069979  cmp     [rdi+2], cx
0x14006997d  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x140069983  jz      loc_140069B20
0x140069989  mov     r9, cs:?RefsIrpContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpContextLookasideList
0x140069990  cmp     eax, ecx
0x140069992  jnb     loc_140069B2F
0x140069998  mov     ecx, eax
0x14006999a  lea     rdx, [rdi-8]; Entry
0x14006999e  shl     rcx, 7
0x1400699a2  add     rcx, r9; Lookaside
0x1400699a5  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400699ac  nop     dword ptr [rax+rax+00h]
0x1400699b1  add     rsp, 28h
0x1400699b5  pop     r15
0x1400699b7  pop     r14
0x1400699b9  pop     r13
0x1400699bb  pop     r12
0x1400699bd  pop     rdi
0x1400699be  pop     rsi
0x1400699bf  pop     rbp
0x1400699c0  pop     rbx
0x1400699c1  retn
0x1400699c3  cmp     [rcx+8], rbx
0x1400699c7  jnz     loc_140069F45
0x1400699cd  mov     rax, [rcx]
0x1400699d0  cmp     [rax+8], rcx
0x1400699d4  jnz     loc_140069F45
0x1400699da  mov     [rbx], rax
0x1400699dd  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x1400699e1  xor     edx, edx; Tag
0x1400699e3  mov     [rax+8], rbx
0x1400699e7  call    cs:__imp_ExFreePoolWithTag
0x1400699ee  nop     dword ptr [rax+rax+00h]
0x1400699f3  jmp     loc_140069917
0x1400699f8  call    cs:__imp_IoGetTopLevelIrp
0x1400699ff  nop     dword ptr [rax+rax+00h]
0x140069a04  mov     rcx, [rax+8]; Irp
0x140069a08  mov     [rax+4], r13d
0x140069a0c  mov     [rax+10h], r13
0x140069a10  call    cs:__imp_IoSetTopLevelIrp
0x140069a17  nop     dword ptr [rax+rax+00h]
0x140069a1c  and     qword ptr [rdi+8], 0FFFFFFFFFFEFFFFFh
0x140069a24  jmp     loc_140069957
0x140069a29  lea     rax, [rdi+240h]
0x140069a30  mov     rcx, [rax]
0x140069a33  cmp     rcx, rax
0x140069a36  jnz     loc_140069FAA
0x140069a3c  mov     rcx, r8
0x140069a3f  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140069a46  nop     dword ptr [rax+rax+00h]
0x140069a4b  test    rsi, rsi
0x140069a4e  jnz     short loc_140069A9C
0x140069a50  mov     rcx, [r15+58h]
0x140069a54  add     rcx, 40h ; '@'; Resource
0x140069a58  test    al, al
0x140069a5a  jz      loc_14006A028
0x140069a60  xor     edx, edx
0x140069a62  call    cs:__imp_ExReleaseFastResource
0x140069a69  nop     dword ptr [rax+rax+00h]
0x140069a6e  mov     rcx, [rsp+68h+arg_10]
0x140069a76  mov     r15d, 802h
0x140069a7c  mov     r8d, 827h
0x140069a82  mov     eax, 0FFFFh
0x140069a87  add     r12w, ax
0x140069a8b  mov     [rsp+68h+arg_0], r12w
0x140069a91  jz      loc_1400697A4
0x140069a97  jmp     loc_1400697CF
0x140069a9c  mov     ecx, [rsi+10h]
0x140069a9f  test    al, al
0x140069aa1  jnz     loc_140069F87
0x140069aa7  lea     eax, [rcx-1]
0x140069aaa  mov     [rsi+10h], eax
0x140069aad  test    eax, eax
0x140069aaf  jnz     short loc_140069AB8
0x140069ab1  mov     [rsi], r13
0x140069ab4  mov     [rsi+8], r13
0x140069ab8  mov     rcx, [r15+58h]
0x140069abc  lea     rdx, [rsi+18h]
0x140069ac0  add     rcx, 40h ; '@'
0x140069ac4  call    cs:__imp_ExReleaseFastResource
0x140069acb  nop     dword ptr [rax+rax+00h]
0x140069ad0  jmp     short loc_140069A6E
0x140069ad2  bt      ecx, 12h
0x140069ad6  jb      loc_140069D01
0x140069adc  cmp     [rsp+68h+arg_8], 0
0x140069ae1  jz      loc_140069F4C
0x140069ae7  and     ecx, 0BFF9C0C5h
0x140069aed  mov     [rdi+4], ecx
0x140069af0  and     qword ptr [rdi+8], 0FFFFFFFFFFFFFBFFh
0x140069af8  mov     [rdi+10h], r13d
0x140069afc  jmp     loc_1400699B1
0x140069b01  cmp     [rcx+rdi+168h], r9
0x140069b09  jnz     loc_14006987A
0x140069b0f  mov     rsi, rax
0x140069b12  test    rax, rax
0x140069b15  jnz     loc_140069A3C
0x140069b1b  jmp     loc_140069A29
0x140069b20  mov     r9, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpAndIoContextLookasideList
0x140069b27  cmp     eax, ecx
0x140069b29  jb      loc_140069998
0x140069b2f  xor     edx, edx
0x140069b31  div     ecx
0x140069b33  mov     eax, edx
0x140069b35  jmp     loc_140069998
0x140069b3a  mov     r15, [rbp+88h]
0x140069b41  jmp     loc_140069841
0x140069b50  lea     r15, [rbp+8]
0x140069b54  mov     r12, r13
0x140069b57  cmp     [rsi], rsi
0x140069b5a  jnz     loc_140069CDB
0x140069b60  mov     rcx, [rbp+30h]
0x140069b64  test    rcx, rcx
0x140069b67  jz      loc_140069BF8
0x140069b6d  mov     edx, [rcx+98h]
0x140069b73  and     edx, 2000h
0x140069b79  jnz     loc_140069F5F
0x140069b7f  mov     eax, [rcx+12Ch]
0x140069b85  test    al, 40h
0x140069b87  jnz     loc_140069F5F
0x140069b8d  mov     rax, [rbp+30h]
0x140069b91  mov     rbx, [rax+30h]
0x140069b95  call    cs:__imp_KeEnterGuardedRegion
0x140069b9c  nop     dword ptr [rax+rax+00h]
0x140069ba1  mov     rcx, rbx; FastMutex
0x140069ba4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140069bab  nop     dword ptr [rax+rax+00h]
0x140069bb0  mov     rax, [rbp+30h]
0x140069bb4  lock inc dword ptr [rax+0ACh]
0x140069bbb  mov     rax, [rbp+30h]
0x140069bbf  mov     [rax+118h], r13
0x140069bc6  mov     rcx, [rbp+30h]
0x140069bca  mov     eax, [rcx+0ACh]
0x140069bd0  inc     eax
0x140069bd2  mov     [rcx+0ACh], eax
0x140069bd8  mov     rcx, [rbp+30h]
0x140069bdc  mov     rcx, [rcx+30h]; FastMutex
0x140069be0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140069be7  nop     dword ptr [rax+rax+00h]
0x140069bec  call    cs:__imp_KeLeaveGuardedRegion
0x140069bf3  nop     dword ptr [rax+rax+00h]
0x140069bf8  mov     rcx, [r15]
0x140069bfb  cmp     [rcx+8], r15
0x140069bff  jnz     loc_140069F45
0x140069c05  mov     rax, [r15+8]
0x140069c09  cmp     [rax], r15
0x140069c0c  jnz     loc_140069F45
0x140069c12  mov     [rax], rcx
0x140069c15  mov     [rcx+8], rax
0x140069c19  lea     rax, [rdi+2D8h]
0x140069c20  cmp     rbp, rax
0x140069c23  jz      short loc_140069C56
0x140069c25  mov     eax, [rbp-8]
0x140069c28  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x140069c2e  mov     r8, cs:?RefsScbSnapshotLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsScbSnapshotLookasideList
0x140069c35  cmp     eax, ecx
0x140069c37  jnb     loc_14006A039
0x140069c3d  mov     ecx, eax
0x140069c3f  lea     rdx, [rbp-8]; Entry
0x140069c43  shl     rcx, 7
0x140069c47  add     rcx, r8; Lookaside
0x140069c4a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140069c51  nop     dword ptr [rax+rax+00h]
0x140069c56  test    r12, r12
0x140069c59  jz      loc_1400698AD
0x140069c5f  mov     rbp, r12
0x140069c62  mov     r8d, 827h
0x140069c68  jmp     loc_140069B50
0x140069c6d  cmp     [rsi], r15w
0x140069c71  jz      loc_140069D0F
0x140069c77  mov     [rdi+38h], r13
0x140069c7b  mov     rbx, [rsi+30h]
  ... truncated ...
```
