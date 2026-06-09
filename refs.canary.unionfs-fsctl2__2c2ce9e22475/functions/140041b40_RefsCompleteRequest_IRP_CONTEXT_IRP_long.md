# RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)

- ea: `0x140041b40`
- end: `0x140042764`
- name: `?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z`
- size: `3108`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, PIRP Irp, NTSTATUS Status)`
- caller_count: `142`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003a1a0`
- `0x14003a850`
- `0x14003b3f0`
- `0x14003e0b0`
- `0x14003ec10`
- `0x14003fbe0`
- `0x140040b20`
- `0x140041280`
- `0x140041a40`
- `0x1400a4ff0`
- `0x1400a7f90`
- `0x1400b2b60`
- `0x1400bc440`
- `0x1400c78f0`
- `0x1400c8660`
- `0x1400ea204`
- `0x1400eac5c`
- `0x1400f1184`
- `0x1400f1330`
- `0x1400f2030`
- `0x140104830`
- `0x1401048f0`
- `0x1401064d0`
- `0x1402864ec`
- `0x140286acc`
- `0x14028aa64`
- `0x14028d074`
- `0x1402961f4`
- `0x14029a520`
- `0x14029b12c`
- `0x14029ca54`
- `0x14029d218`
- `0x1402a03b8`
- `0x1402a56b0`
- `0x1402a8b7c`
- `0x1402a90cc`
- `0x1402a9d08`
- `0x1402aa028`
- `0x1402aa504`
- `0x1402aae48`
- `0x1402ab328`
- `0x1402ab528`
- `0x1402ac008`
- `0x1402ac330`
- `0x1402ac510`
- `0x1402ad28c`
- `0x1402ad65c`
- `0x1402ad6dc`
- `0x1402ad9cc`
- `0x1402ae1a8`

## callees

- `0x140041b40`
- `0x140042770`
- `0x14008dbd0`
- `0x1400c8644`
- `0x1400ca788`
- `0x1400f81b8`
- `0x1402fed30`
- `0x140320020`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140041f60`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140041f60`
- `ntoskrnl!IofCompleteRequest` at `0x140041f06`
- `ntoskrnl!IofCompleteRequest` at `0x140041f06`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140041f78`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140041f78`
- `ntoskrnl!KeSetEvent` at `0x140042253`
- `ntoskrnl!KeSetEvent` at `0x140042253`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14004232b`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14004232b`
- `ntoskrnl!KdDebuggerEnabled` at `0x140042650`
- `ntoskrnl!KdDebuggerEnabled` at `0x140042667`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041e8c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400421dd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004248b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140041e8c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400421dd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004248b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140042724`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140042724`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14004211e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140042208`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400423c8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14004211e`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140042208`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400423c8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004212d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140042217`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400423d7`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14004212d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140042217`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400423d7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004216d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140042263`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004241c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004216d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140042263`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14004241c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140042179`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14004226f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140042428`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140042179`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14004226f`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140042428`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140041fb1`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140041fb1`
- `ntoskrnl!ExReleaseFastResource` at `0x140041fd4`
- `ntoskrnl!ExReleaseFastResource` at `0x140042036`
- `ntoskrnl!ExReleaseFastResource` at `0x1400422ec`
- `ntoskrnl!ExReleaseFastResource` at `0x1400426ab`
- `ntoskrnl!ExReleaseFastResource` at `0x140041fd4`
- `ntoskrnl!ExReleaseFastResource` at `0x140042036`
- `ntoskrnl!ExReleaseFastResource` at `0x1400422ec`
- `ntoskrnl!ExReleaseFastResource` at `0x1400426ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400424b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400426c7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400424b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400426c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042700`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042739`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004274c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042700`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042739`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004274c`

## pseudocode

```c
void __fastcall RefsCompleteRequest(PSECURITY_SUBJECT_CONTEXT *a1, PIRP Irp, NTSTATUS Status)
{
  PSECURITY_SUBJECT_CONTEXT *v3; // r13
  struct _FILE_OBJECT *v6; // rdx
  unsigned int v7; // r8d
  PSECURITY_SUBJECT_CONTEXT v9; // r10
  PSECURITY_SUBJECT_CONTEXT v10; // r11
  int *v11; // rax
  volatile signed __int64 *v12; // rax
  PSECURITY_SUBJECT_CONTEXT v13; // rax
  char v14; // al
  PSECURITY_SUBJECT_CONTEXT v15; // rsi
  int v16; // eax
  struct _IRP_CONTEXT *v17; // rbx
  char *v18; // r15
  struct _IRP_CONTEXT *v19; // rcx
  PSECURITY_SUBJECT_CONTEXT v20; // rax
  __int16 v21; // r8
  _QWORD *v22; // rcx
  struct _IRP_CONTEXT *v23; // r13
  struct _IRP_CONTEXT *v24; // rax
  PSECURITY_SUBJECT_CONTEXT *v25; // rsi
  char *v26; // r13
  PSECURITY_SUBJECT_CONTEXT *v27; // rsi
  struct _KTHREAD *CurrentThread; // r9
  __int64 v29; // r8
  unsigned int i; // edx
  __int64 v31; // rcx
  PSECURITY_SUBJECT_CONTEXT *v32; // rax
  struct _IRP_CONTEXT *v33; // rsi
  struct _IRP_CONTEXT *v34; // rax
  PSECURITY_SUBJECT_CONTEXT *v35; // r15
  PSECURITY_SUBJECT_CONTEXT *m; // rcx
  int v37; // ecx
  unsigned __int64 v38; // rax
  _QWORD **v39; // rbx
  _QWORD *v40; // rcx
  bool v41; // zf
  int v42; // eax
  PSECURITY_SUBJECT_CONTEXT v43; // rcx
  unsigned int v44; // eax
  struct _NPAGED_LOOKASIDE_LIST *v45; // r9
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _QWORD *FsContext; // rcx
  PFILE_OBJECT FileObject; // rax
  _QWORD *v49; // rax
  PIRP TopLevelIrp; // rax
  IRP *MdlAddress; // rcx
  struct _IRP_CONTEXT *j; // rcx
  char IsFastResourceHeldExclusive; // al
  struct _ERESOURCE *v54; // rcx
  int v55; // ecx
  char v56; // cl
  PSECURITY_SUBJECT_CONTEXT v57; // rcx
  struct _FAST_MUTEX *v58; // rbx
  PSECURITY_SUBJECT_CONTEXT v59; // rdx
  PSECURITY_SUBJECT_CONTEXT **v60; // rcx
  unsigned int v61; // eax
  struct _FAST_MUTEX *PrimaryToken; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *v63; // rcx
  _QWORD *v64; // rcx
  __int64 v65; // rcx
  struct _IRP_CONTEXT *k; // rax
  PSECURITY_SUBJECT_CONTEXT v67; // rdx
  struct _ERESOURCE *ClientToken; // rcx
  PVOID *p_ProcessAuditId; // rdx
  BOOLEAN IsOperationSynchronous; // al
  struct _IRP_CONTEXT *v71; // rax
  PSECURITY_SUBJECT_CONTEXT v72; // rcx
  struct _FAST_MUTEX *v73; // rsi
  PSECURITY_SUBJECT_CONTEXT v74; // rdx
  PSECURITY_SUBJECT_CONTEXT **v75; // rcx
  unsigned int v76; // eax
  struct _VCB *v77; // rcx
  volatile signed __int64 *v78; // rax
  struct _FILE_OBJECT *v79; // [rsp+30h] [rbp-68h]
  PSECURITY_SUBJECT_CONTEXT v80; // [rsp+38h] [rbp-60h]
  PSECURITY_SUBJECT_CONTEXT v81; // [rsp+40h] [rbp-58h]
  PSECURITY_SUBJECT_CONTEXT *v82; // [rsp+48h] [rbp-50h]
  struct _IRP_CONTEXT *v83; // [rsp+50h] [rbp-48h]
  PSECURITY_SUBJECT_CONTEXT *v84; // [rsp+58h] [rbp-40h]
  __int16 v85; // [rsp+A0h] [rbp+8h]
  int v86; // [rsp+B8h] [rbp+20h]

  v3 = 0;
  v80 = 0;
  v81 = 0;
  v6 = 0;
  v79 = 0;
  v7 = 29;
  v86 = 29;
  v9 = 0;
  v10 = 0;
  if ( a1 )
  {
    if ( a1[3] )
      RefsCommitCurrentTransaction((struct _IRP_CONTEXT *)a1, 0);
    v11 = (int *)a1[13];
    if ( a1 != (PSECURITY_SUBJECT_CONTEXT *)v11
      && v11[4] >= 0
      && Status < 0
      && *((_BYTE *)a1 + 40) != 3
      && (*((_DWORD *)a1 + 1) & 0x8000) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          36,
          WPP_3a66e9b7f5c134dfe789af195554f06a_Traceguids,
          (unsigned int)Status);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(Status, 0, "NtfsData.c", 0xB09u);
      LODWORD(a1[13]->PrimaryToken) = Status;
    }
    if ( Status == -1073741202 )
    {
      v77 = (struct _VCB *)a1[8];
      if ( v77 )
      {
        if ( (*((_DWORD *)v77 + 6) & 1) != 0 && (*((_DWORD *)v77 + 7) & 1) == 0 )
          RefsPostSelfDismount(v77, v6, -1073741202);
      }
    }
    if ( *((_DWORD *)a1 + 164) && (_BYTE)KdDebuggerEnabled )
      __int2c();
    if ( *((_DWORD *)a1 + 165) && (_BYTE)KdDebuggerEnabled )
      __int2c();
    v12 = (volatile signed __int64 *)a1[8];
    if ( v12 && Status < 0 )
    {
      v56 = *((_BYTE *)a1 + 40);
      if ( v56 == 4 )
      {
        switch ( Status )
        {
          case -1073741803:
            v78 = v12 + 975;
            break;
          case -1073741435:
            v78 = v12 + 976;
            break;
          case -1073741391:
            v78 = v12 + 977;
            break;
          default:
            v78 = v12 + 978;
            break;
        }
        _InterlockedIncrement64(v78);
      }
      else if ( v56 == 3 )
      {
        _InterlockedIncrement64(v12 + 979);
      }
    }
    if ( Irp )
    {
      v13 = a1[8];
      if ( v13 )
      {
        if ( Status >= 0 && LOBYTE(v13[328].ClientToken) )
        {
          v14 = *((_BYTE *)a1 + 40);
          if ( v14 == 2 )
            goto LABEL_17;
          if ( v14 )
          {
            if ( v14 != 18 )
              goto LABEL_18;
            goto LABEL_17;
          }
          if ( ((_BYTE)a1[1] & 0x40) == 0 )
          {
LABEL_17:
            v80 = a1[88];
            v86 = *((_DWORD *)a1 + 175);
            v79 = (struct _FILE_OBJECT *)a1[86];
            v81 = a1[8];
            a1[86] = (PSECURITY_SUBJECT_CONTEXT)21;
          }
        }
      }
    }
LABEL_18:
    if ( a1[6] )
      RefsReleaseSharedResources((struct _IRP_CONTEXT *)a1);
    v15 = a1[7];
    if ( !v15 )
      goto LABEL_21;
    if ( LOWORD(v15->ClientToken) == 2050 )
    {
      v67 = a1[13];
      ClientToken = (struct _ERESOURCE *)v15[3].ClientToken;
      if ( v67[10].PrimaryToken != ClientToken
        || !LODWORD(v67[10].ClientToken)
        || (p_ProcessAuditId = &v67[7].ProcessAuditId) == 0 )
      {
        ExReleaseResourceLite(ClientToken);
        a1[7] = 0;
        goto LABEL_21;
      }
      v41 = (*((_DWORD *)p_ProcessAuditId + 18))-- == 1;
      if ( v41 )
      {
        *((_DWORD *)p_ProcessAuditId + 19) &= ~2u;
        ExReleaseFastResource(ClientToken, p_ProcessAuditId);
        a1[7] = 0;
        goto LABEL_21;
      }
    }
    else
    {
      a1[7] = 0;
      PrimaryToken = (struct _FAST_MUTEX *)v15[1].PrimaryToken;
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe(PrimaryToken);
      v63 = v15 + 14;
      if ( v63->ClientToken == v63 )
      {
        v15[13].ProcessAuditId = 0;
      }
      else
      {
        v64 = v63->ClientToken;
        v15[13].ProcessAuditId = (PVOID)((unsigned __int64)v15[13].ProcessAuditId | 3);
        ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v64);
        *(_QWORD *)(v65 + 8) = 0;
        *(_QWORD *)v65 = 0;
        KeSetEvent((PRKEVENT)(v65 + 16), 0, 0);
      }
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)v15[1].PrimaryToken);
      KeLeaveGuardedRegion();
    }
    a1[7] = 0;
LABEL_21:
    v16 = *((_DWORD *)a1 + 1);
    if ( (v16 & 0x2000) != 0 )
    {
      *((_DWORD *)a1 + 1) = v16 & 0xFFFFCFFF;
      ExReleaseFastResource(&a1[8][37].ProcessAuditId, 0);
    }
    v17 = (struct _IRP_CONTEXT *)a1[14];
LABEL_24:
    if ( v17 != (struct _IRP_CONTEXT *)(a1 + 14) )
    {
      v18 = (char *)v17 - 64;
      v85 = *((_WORD *)v17 - 18);
      v19 = v17;
      v83 = v17;
      v17 = *(struct _IRP_CONTEXT **)v17;
      while ( !*(_QWORD *)v19 )
      {
LABEL_36:
        if ( *(_WORD *)v18 == 2050 )
          v26 = v18;
        else
          v26 = (char *)*((_QWORD *)v18 + 17);
        v27 = 0;
        CurrentThread = KeGetCurrentThread();
        v29 = *((_QWORD *)v26 + 11) + 64LL;
        for ( i = 0; i < 2; ++i )
        {
          v31 = 14LL * i;
          v32 = &a1[v31 + 44];
          if ( *v32 == (PSECURITY_SUBJECT_CONTEXT)v29 && a1[v31 + 45] == (PSECURITY_SUBJECT_CONTEXT)CurrentThread )
          {
            v27 = &a1[v31 + 44];
            if ( v32 )
              goto LABEL_82;
            break;
          }
        }
        for ( j = (struct _IRP_CONTEXT *)a1[72]; j != (struct _IRP_CONTEXT *)(a1 + 72); j = *(struct _IRP_CONTEXT **)j )
        {
          if ( *((_QWORD *)j - 12) == v29 && *((struct _KTHREAD **)j - 11) == CurrentThread )
          {
            v27 = (PSECURITY_SUBJECT_CONTEXT *)((char *)j - 96);
            break;
          }
        }
LABEL_82:
        IsFastResourceHeldExclusive = ExIsFastResourceHeldExclusive(*((_QWORD *)v26 + 11) + 64LL);
        if ( !v27 )
        {
          v54 = (struct _ERESOURCE *)(*((_QWORD *)v26 + 11) + 64LL);
          if ( IsFastResourceHeldExclusive )
            ExReleaseFastResource(v54, 0);
          else
            ExReleaseResourceLite(v54);
          goto LABEL_85;
        }
        v55 = *((_DWORD *)v27 + 4);
        if ( IsFastResourceHeldExclusive )
        {
          if ( !v55 )
            goto LABEL_91;
          *((_DWORD *)v27 + 4) = v55 - 1;
          if ( v55 != 1 )
            goto LABEL_91;
LABEL_90:
          *v27 = 0;
          v27[1] = 0;
          goto LABEL_91;
        }
        *((_DWORD *)v27 + 4) = v55 - 1;
        if ( v55 == 1 )
          goto LABEL_90;
LABEL_91:
        ExReleaseFastResource(*((_QWORD *)v26 + 11) + 64LL, v27 + 3);
LABEL_85:
        v19 = v83;
        v3 = 0;
LABEL_86:
        if ( !--v85 )
          goto LABEL_24;
      }
      if ( *((_WORD *)v18 + 14) != 1 )
        goto LABEL_35;
      v20 = a1[3];
      if ( v20 && v20[4].PrimaryToken && ((*((_DWORD *)v18 + 2) & 0x8000LL) == 0 || (*((_DWORD *)a1 + 1) & 0x1000) != 0) )
        goto LABEL_86;
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(v19);
      v22[1] = 0;
      *v22 = 0;
      v23 = (struct _IRP_CONTEXT *)(a1 + 80);
      v24 = (struct _IRP_CONTEXT *)a1[80];
      if ( v24 == (struct _IRP_CONTEXT *)(a1 + 80) )
        goto LABEL_35;
      v25 = 0;
      v82 = 0;
      while ( v24 != v23 )
      {
        if ( *((_WORD *)v24 - 4) == v21 )
        {
          v25 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v24 - 8);
          v82 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v24 - 8);
          break;
        }
        v24 = *(struct _IRP_CONTEXT **)v24;
      }
      if ( !v25 )
      {
LABEL_35:
        --*((_WORD *)v18 + 14);
        goto LABEL_36;
      }
      while ( 1 )
      {
        v71 = *(struct _IRP_CONTEXT **)v23;
        v84 = 0;
        if ( *(struct _IRP_CONTEXT **)v23 != v23 )
        {
          if ( v25 )
            v71 = (struct _IRP_CONTEXT *)v25[1];
          while ( v71 != v23 )
          {
            if ( *((_WORD *)v71 - 4) == v21 )
            {
              v84 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v71 - 8);
              break;
            }
            v71 = *(struct _IRP_CONTEXT **)v71;
          }
        }
        v72 = v25[6];
        if ( v72 )
        {
          if ( *(char **)&v72[4].ImpersonationLevel != v18 )
            goto LABEL_151;
          if ( (((__int64)v72[4].ProcessAuditId & 0x2000) != 0 || (*(&v72[9].ImpersonationLevel + 1) & 0x40) != 0)
            && ((__int64)v72[4].ProcessAuditId & 0x2000) != 0 )
          {
            _InterlockedAnd((volatile signed __int32 *)&v72[4].ProcessAuditId, 0xFFFFDFFF);
          }
          v73 = (struct _FAST_MUTEX *)v25[6][1].PrimaryToken;
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v73);
          v25 = v82;
          _InterlockedIncrement((volatile signed __int32 *)&v82[6][5].ImpersonationLevel + 1);
          v82[6][8].ProcessAuditId = 0;
          ++*((_DWORD *)&v82[6][5].ImpersonationLevel + 1);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)v82[6][1].PrimaryToken);
          KeLeaveGuardedRegion();
        }
        v74 = v25[1];
        if ( *(PSECURITY_SUBJECT_CONTEXT **)&v74->ImpersonationLevel != v25 + 1 )
          goto LABEL_163;
        v75 = (PSECURITY_SUBJECT_CONTEXT **)v25[2];
        if ( *v75 != v25 + 1 )
          goto LABEL_163;
        *v75 = (PSECURITY_SUBJECT_CONTEXT *)v74;
        *(_QWORD *)&v74->ImpersonationLevel = v75;
        if ( v25 != a1 + 91 )
        {
          v76 = *((_DWORD *)v25 - 2);
          if ( v76 >= RefsNumberProcessors )
            v76 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v76], v25 - 1);
        }
LABEL_151:
        v21 = 2087;
        v82 = v84;
        v25 = v84;
        if ( !v84 )
          goto LABEL_35;
      }
    }
    v33 = (struct _IRP_CONTEXT *)(a1 + 80);
    v34 = (struct _IRP_CONTEXT *)a1[80];
    if ( v34 != (struct _IRP_CONTEXT *)(a1 + 80) )
    {
      v35 = 0;
      while ( v34 != v33 )
      {
        if ( *((_WORD *)v34 - 4) == 2087 )
        {
          v35 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v34 - 8);
          break;
        }
        v34 = *(struct _IRP_CONTEXT **)v34;
      }
      if ( v35 )
      {
        while ( 1 )
        {
          if ( *(struct _IRP_CONTEXT **)v33 != v33 )
          {
            for ( k = (struct _IRP_CONTEXT *)v35[1]; k != v33; k = *(struct _IRP_CONTEXT **)k )
            {
              if ( *((_WORD *)k - 4) == 2087 )
              {
                v3 = (PSECURITY_SUBJECT_CONTEXT *)((char *)k - 8);
                break;
              }
            }
          }
          v57 = v35[6];
          if ( v57 )
          {
            if ( (((__int64)v57[4].ProcessAuditId & 0x2000) != 0 || (*(&v57[9].ImpersonationLevel + 1) & 0x40) != 0)
              && ((__int64)v57[4].ProcessAuditId & 0x2000) != 0 )
            {
              _InterlockedAnd((volatile signed __int32 *)&v57[4].ProcessAuditId, 0xFFFFDFFF);
            }
            v58 = (struct _FAST_MUTEX *)v35[6][1].PrimaryToken;
            KeEnterGuardedRegion();
            ExAcquireFastMutexUnsafe(v58);
            _InterlockedIncrement((volatile signed __int32 *)&v35[6][5].ImpersonationLevel + 1);
            v35[6][8].ProcessAuditId = 0;
            ++*((_DWORD *)&v35[6][5].ImpersonationLevel + 1);
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)v35[6][1].PrimaryToken);
            KeLeaveGuardedRegion();
          }
          v59 = v35[1];
          if ( *(PSECURITY_SUBJECT_CONTEXT **)&v59->ImpersonationLevel != v35 + 1
            || (v60 = (PSECURITY_SUBJECT_CONTEXT **)v35[2], *v60 != v35 + 1) )
          {
LABEL_163:
            __fastfail(3u);
          }
          *v60 = (PSECURITY_SUBJECT_CONTEXT *)v59;
          *(_QWORD *)&v59->ImpersonationLevel = v60;
          if ( v35 != a1 + 91 )
          {
            v61 = *((_DWORD *)v35 - 2);
            if ( v61 >= RefsNumberProcessors )
              v61 %= RefsNumberProcessors;
            ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v61], v35 - 1);
          }
          if ( !v3 )
            break;
          v35 = v3;
          v3 = 0;
        }
      }
    }
    for ( m = (PSECURITY_SUBJECT_CONTEXT *)a1[75]; m; m = (PSECURITY_SUBJECT_CONTEXT *)a1[75] )
    {
      a1[75] = *m;
      ExFreePoolWithTag(m, 0);
    }
    v37 = *((_DWORD *)a1 + 1);
    if ( (v37 & 0x400) != 0 || (v38 = (unsigned __int64)a1[1], (v38 & 0x10000) != 0) )
    {
      if ( (v37 & 0x40000) != 0 )
      {
        *((_DWORD *)a1 + 1) = v37 & 0xFFFBFBFF;
      }
      else
      {
        *((_DWORD *)a1 + 1) = v37 & 0xBFF9C0C5;
        a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFFFFBFFuLL);
      }
      *((_DWORD *)a1 + 4) = 0;
      goto LABEL_67;
    }
    if ( (v38 & 0x20000000000LL) != 0 )
    {
      *((_DWORD *)a1 + 59) &= ~1u;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)(v38 & 0xFFFFFDFFFFFFFFFFuLL);
    }
    if ( a1[42] )
    {
      *((_DWORD *)a1 + 81) &= ~1u;
      a1[42] = 0;
    }
    v39 = (_QWORD **)(a1 + 72);
    while ( 1 )
    {
      v40 = *v39;
      if ( *v39 == v39 )
        break;
      if ( (_QWORD **)v40[1] != v39 )
        goto LABEL_163;
      v49 = (_QWORD *)*v40;
      if ( *(_QWORD **)(*v40 + 8LL) != v40 )
        goto LABEL_163;
      *v39 = v49;
      v49[1] = v39;
      ExFreePoolWithTag(v40 - 12, 0);
    }
    a1[44] = 0;
    a1[58] = 0;
    v41 = ((_BYTE)a1[1] & 0x20) == 0;
    *((_DWORD *)a1 + 148) = 0;
    if ( !v41 )
    {
      SeReleaseSubjectContext(a1[18]);
      ExFreePoolWithTag(a1[18], 0);
    }
    v42 = *((_DWORD *)a1 + 2);
    a1[18] = 0;
    if ( (*(_QWORD *)&v42 & 0x100000LL) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      MdlAddress = (IRP *)TopLevelIrp->MdlAddress;
      *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
      *(_QWORD *)&TopLevelIrp->Flags = 0;
      IoSetTopLevelIrp(MdlAddress);
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFEFFFFFuLL);
    }
    v43 = a1[89];
    if ( v43 )
    {
      ExFreePoolWithTag(v43, 0);
      a1[89] = 0;
    }
    if ( ((_DWORD)a1[1] & 0x80000LL) == 0 )
      goto LABEL_67;
    v44 = *((_DWORD *)a1 - 2);
    if ( *((_WORD *)a1 + 1) == 1664 )
    {
      v45 = RefsIrpAndIoContextLookasideList;
      if ( v44 < RefsNumberProcessors )
        goto LABEL_66;
    }
    else
    {
      v45 = RefsIrpContextLookasideList;
      if ( v44 < RefsNumberProcessors )
      {
LABEL_66:
        ExFreeToNPagedLookasideList(&v45[(unsigned __int64)v44], a1 - 1);
LABEL_67:
        v10 = v81;
        v9 = v80;
        v7 = v86;
        v6 = v79;
        goto LABEL_68;
      }
    }
    v44 %= RefsNumberProcessors;
    goto LABEL_66;
  }
LABEL_68:
  if ( Irp )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    FsContext = 0;
    FileObject = CurrentStackLocation->FileObject;
    if ( FileObject )
      FsContext = FileObject->FsContext;
    Irp->IoStatus.Status = Status;
    if ( (unsigned __int8)(CurrentStackLocation->MajorFunction - 3) <= 1u && Status == -1073741670 )
    {
      if ( FsContext )
      {
        if ( (*(_BYTE *)(FsContext[17] + 8LL) & 4) != 0 )
        {
          IsOperationSynchronous = IoIsOperationSynchronous(Irp);
          v6 = v79;
          v7 = v86;
          v9 = v80;
          v10 = v81;
          if ( IsOperationSynchronous )
            ++RefsFailedPagingFileOps;
        }
      }
    }
    if ( CurrentStackLocation->MajorFunction == 3 && Status == -1073741670 && (Irp->Flags & 2) != 0 )
      ++RefsFailedPagingReads;
    if ( (__int64)v6 > 23 )
      RefsIoPerfCollectBasicData(v10, Irp, v9, v7, v6);
    IofCompleteRequest(Irp, 1);
  }
}

```

## disassembly

```asm
0x140041b40  mov     [rsp+arg_8], rbx
0x140041b45  push    rbp
0x140041b46  push    rsi
0x140041b47  push    rdi
0x140041b48  push    r12
0x140041b4a  push    r13
0x140041b4c  push    r14
0x140041b4e  push    r15
0x140041b50  sub     rsp, 60h
0x140041b54  xor     r13d, r13d
0x140041b57  mov     r12d, r8d
0x140041b5a  mov     [rsp+98h+var_60], r13
0x140041b5f  mov     rbp, rdx
0x140041b62  mov     [rsp+98h+var_58], r13
0x140041b67  mov     edx, r13d; struct _FILE_OBJECT *
0x140041b6a  mov     [rsp+98h+var_68], rdx
0x140041b6f  mov     r8d, 1Dh
0x140041b75  mov     [rsp+98h+arg_18], r8d
0x140041b7d  mov     rdi, rcx
0x140041b80  mov     r10d, r13d
0x140041b83  mov     r11d, r13d
0x140041b86  test    rcx, rcx
0x140041b89  jz      loc_140041EAF
0x140041b8f  cmp     [rcx+18h], rdx
0x140041b93  jnz     loc_140041F91
0x140041b99  mov     rax, [rdi+68h]
0x140041b9d  cmp     rdi, rax
0x140041ba0  jnz     loc_140042565
0x140041ba6  cmp     r12d, 0C000026Eh
0x140041bad  jz      loc_14004261D
0x140041bb3  cmp     [rdi+290h], r13d
0x140041bba  jnz     loc_140042650
0x140041bc0  cmp     [rdi+294h], r13d
0x140041bc7  jnz     loc_140042667
0x140041bcd  mov     rax, [rdi+40h]
0x140041bd1  test    rax, rax
0x140041bd4  jz      short loc_140041BDF
0x140041bd6  test    r12d, r12d
0x140041bd9  js      loc_140042044
0x140041bdf  test    rbp, rbp
0x140041be2  jz      short loc_140041C4A
0x140041be4  mov     rax, [rdi+40h]
0x140041be8  test    rax, rax
0x140041beb  jz      short loc_140041C4A
0x140041bed  test    r12d, r12d
0x140041bf0  js      short loc_140041C4A
0x140041bf2  movzx   eax, byte ptr [rax+2900h]
0x140041bf9  test    al, al
0x140041bfb  jz      short loc_140041C4A
0x140041bfd  movzx   eax, byte ptr [rdi+28h]
0x140041c01  cmp     al, 2
0x140041c03  jz      short loc_140041C11
0x140041c05  test    al, al
0x140041c07  jz      loc_1400420D0
0x140041c0d  cmp     al, 12h
0x140041c0f  jnz     short loc_140041C4A
0x140041c11  mov     rax, [rdi+2C0h]
0x140041c18  mov     rcx, [rdi+40h]
0x140041c1c  mov     [rsp+98h+var_60], rax
0x140041c21  mov     eax, [rdi+2BCh]
0x140041c27  mov     [rsp+98h+arg_18], eax
0x140041c2e  mov     rax, [rdi+2B0h]
0x140041c35  mov     [rsp+98h+var_68], rax
0x140041c3a  mov     [rsp+98h+var_58], rcx
0x140041c3f  mov     qword ptr [rdi+2B0h], 15h
0x140041c4a  cmp     [rdi+30h], r13
0x140041c4e  jz      short loc_140041C58
0x140041c50  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140041c53  call    ?RefsReleaseSharedResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseSharedResources(_IRP_CONTEXT *)
0x140041c58  mov     rsi, [rdi+38h]
0x140041c5c  mov     eax, 802h
0x140041c61  test    rsi, rsi
0x140041c64  jnz     loc_1400421F7
0x140041c6a  mov     eax, [rdi+4]
0x140041c6d  bt      eax, 0Dh
0x140041c71  jb      loc_140042696
0x140041c77  mov     rbx, [rdi+70h]
0x140041c7b  lea     r14, [rdi+70h]
0x140041c7f  mov     r8d, 827h
0x140041c85  cmp     rbx, r14
0x140041c88  jz      loc_140041D65
0x140041c8e  movzx   eax, word ptr [rbx-24h]
0x140041c92  lea     r15, [rbx-40h]
0x140041c96  mov     [rsp+98h+arg_0], ax
0x140041c9e  mov     rcx, rbx
0x140041ca1  mov     [rsp+98h+var_48], rbx
0x140041ca6  mov     eax, 0FFFFh
0x140041cab  mov     rbx, [rbx]
0x140041cae  cmp     qword ptr [rcx], 0
0x140041cb2  jz      short loc_140041D18
0x140041cb4  cmp     word ptr [r15+1Ch], 1
0x140041cba  jnz     short loc_140041D13
0x140041cbc  mov     rax, [rdi+18h]
0x140041cc0  test    rax, rax
0x140041cc3  jnz     loc_1400424FC
0x140041cc9  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140041cce  mov     [rcx+8], r13
0x140041cd2  mov     [rcx], r13
0x140041cd5  lea     r13, [rdi+280h]
0x140041cdc  mov     rax, [r13+0]
0x140041ce0  cmp     rax, r13
0x140041ce3  jz      short loc_140041D0E
0x140041ce5  xor     esi, esi
0x140041ce7  mov     [rsp+98h+var_50], rsi
0x140041cec  cmp     rax, r13
0x140041cef  jz      short loc_140041D05
0x140041cf1  cmp     [rax-8], r8w
0x140041cf6  jnz     loc_14004257D
0x140041cfc  lea     rsi, [rax-8]
0x140041d00  mov     [rsp+98h+var_50], rsi
0x140041d05  test    rsi, rsi
0x140041d08  jnz     loc_140042370
0x140041d0e  mov     eax, 0FFFFh
0x140041d13  add     [r15+1Ch], ax
0x140041d18  mov     eax, 802h
0x140041d1d  cmp     [r15], ax
0x140041d21  jnz     loc_1400420C4
0x140041d27  mov     r13, r15
0x140041d2a  mov     r8, [r13+58h]
0x140041d2e  xor     esi, esi
0x140041d30  mov     r9, gs:188h
0x140041d39  add     r8, 40h ; '@'
0x140041d3d  xor     edx, edx
0x140041d3f  cmp     edx, 2
0x140041d42  jnb     loc_140041F9B
0x140041d48  mov     eax, edx
0x140041d4a  imul    rcx, rax, 70h ; 'p'
0x140041d4e  lea     rax, [rdi+160h]
0x140041d55  add     rax, rcx
0x140041d58  cmp     [rax], r8
0x140041d5b  jz      loc_14004208B
0x140041d61  inc     edx
0x140041d63  jmp     short loc_140041D3F
0x140041d65  lea     rsi, [rdi+280h]
0x140041d6c  mov     rax, [rsi]
0x140041d6f  cmp     rax, rsi
0x140041d72  jz      short loc_140041D94
0x140041d74  mov     r15, r13
0x140041d77  cmp     rax, rsi
0x140041d7a  jz      short loc_140041D8B
0x140041d7c  cmp     [rax-8], r8w
0x140041d81  jnz     loc_14004252B
0x140041d87  lea     r15, [rax-8]
0x140041d8b  test    r15, r15
0x140041d8e  jnz     loc_1400420E0
0x140041d94  mov     rcx, [rdi+258h]; P
0x140041d9b  test    rcx, rcx
0x140041d9e  jnz     loc_1400426F4
0x140041da4  mov     ecx, [rdi+4]
0x140041da7  bt      ecx, 0Ah
0x140041dab  jb      loc_140042067
0x140041db1  mov     rax, [rdi+8]
0x140041db5  bt      rax, 10h
0x140041dba  jb      loc_140042067
0x140041dc0  bt      rax, 29h ; ')'
0x140041dc5  jnb     short loc_140041DDF
0x140041dc7  and     dword ptr [rdi+0ECh], 0FFFFFFFEh
0x140041dce  mov     rcx, 0FFFFFDFFFFFFFFFFh
0x140041dd8  and     rax, rcx
0x140041ddb  mov     [rdi+8], rax
0x140041ddf  cmp     qword ptr [rdi+150h], 0
0x140041de7  jz      short loc_140041DF7
0x140041de9  and     dword ptr [rdi+144h], 0FFFFFFFEh
0x140041df0  mov     [rdi+150h], r13
0x140041df7  lea     rbx, [rdi+240h]
0x140041dfe  mov     rcx, [rbx]
0x140041e01  cmp     rcx, rbx
0x140041e04  jnz     loc_140041F2B
0x140041e0a  mov     [rdi+160h], r13
0x140041e11  mov     [r14+160h], r13
0x140041e18  test    byte ptr [rdi+8], 20h
0x140041e1c  mov     [rdi+250h], r13d
0x140041e23  jnz     loc_14004271D
0x140041e29  mov     eax, [rdi+8]
0x140041e2c  mov     [rdi+90h], r13
0x140041e33  bt      rax, 14h
0x140041e38  jb      loc_140041F60
0x140041e3e  mov     rcx, [rdi+2C8h]; P
0x140041e45  test    rcx, rcx
0x140041e48  jnz     loc_14004274A
0x140041e4e  mov     eax, [rdi+8]
0x140041e51  bt      rax, 13h
0x140041e56  jnb     short loc_140041E98
0x140041e58  mov     eax, [rdi-8]
0x140041e5b  mov     ecx, 680h
0x140041e60  cmp     [rdi+2], cx
0x140041e64  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x140041e6a  jz      loc_1400420AA
0x140041e70  mov     r9, cs:?RefsIrpContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpContextLookasideList
0x140041e77  cmp     eax, ecx
0x140041e79  jnb     loc_1400420B9
0x140041e7f  mov     ecx, eax
0x140041e81  lea     rdx, [rdi-8]; Entry
0x140041e85  shl     rcx, 7
0x140041e89  add     rcx, r9; Lookaside
0x140041e8c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140041e93  nop     dword ptr [rax+rax+00h]
0x140041e98  mov     r11, [rsp+98h+var_58]
0x140041e9d  mov     r10, [rsp+98h+var_60]
0x140041ea2  mov     r8d, [rsp+98h+arg_18]
0x140041eaa  mov     rdx, [rsp+98h+var_68]
0x140041eaf  test    rbp, rbp
0x140041eb2  jz      short loc_140041F12
0x140041eb4  mov     rbx, [rbp+0B8h]
0x140041ebb  mov     rcx, r13
0x140041ebe  mov     rax, [rbx+30h]
0x140041ec2  test    rax, rax
0x140041ec5  jz      short loc_140041ECB
0x140041ec7  mov     rcx, [rax+18h]
0x140041ecb  mov     [rbp+30h], r12d
0x140041ecf  movzx   eax, byte ptr [rbx]
0x140041ed2  sub     al, 3
0x140041ed4  cmp     al, 1
0x140041ed6  jbe     loc_140042301
0x140041edc  cmp     byte ptr [rbx], 3
0x140041edf  jz      loc_1400424CD
0x140041ee5  cmp     rdx, 17h
0x140041ee9  jle     short loc_140041F01
0x140041eeb  mov     [rsp+98h+var_78], rdx
0x140041ef0  mov     r9d, r8d
0x140041ef3  mov     r8, r10
0x140041ef6  mov     rdx, rbp
0x140041ef9  mov     rcx, r11
0x140041efc  call    ?RefsIoPerfCollectBasicData@@YAXPEAU_VCB@@PEAU_IRP@@PEAXW4_REFS_IO_PERF_IO_TYPE@@_J@Z; RefsIoPerfCollectBasicData(_VCB *,_IRP *,void *,_REFS_IO_PERF_IO_TYPE,__int64)
0x140041f01  mov     dl, 1; PriorityBoost
0x140041f03  mov     rcx, rbp; Irp
0x140041f06  call    cs:__imp_IofCompleteRequest
0x140041f0d  nop     dword ptr [rax+rax+00h]
0x140041f12  mov     rbx, [rsp+98h+arg_8]
0x140041f1a  add     rsp, 60h
0x140041f1e  pop     r15
0x140041f20  pop     r14
0x140041f22  pop     r13
0x140041f24  pop     r12
0x140041f26  pop     rdi
0x140041f27  pop     rsi
0x140041f28  pop     rbp
0x140041f29  retn
0x140041f2b  cmp     [rcx+8], rbx
0x140041f2f  jnz     loc_140042533
0x140041f35  mov     rax, [rcx]
0x140041f38  cmp     [rax+8], rcx
0x140041f3c  jnz     loc_140042533
0x140041f42  mov     [rbx], rax
0x140041f45  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x140041f49  xor     edx, edx; Tag
0x140041f4b  mov     [rax+8], rbx
0x140041f4f  call    cs:__imp_ExFreePoolWithTag
0x140041f56  nop     dword ptr [rax+rax+00h]
0x140041f5b  jmp     loc_140041DFE
0x140041f60  call    cs:__imp_IoGetTopLevelIrp
0x140041f67  nop     dword ptr [rax+rax+00h]
0x140041f6c  mov     rcx, [rax+8]; Irp
0x140041f70  mov     [rax+4], r13d
0x140041f74  mov     [rax+10h], r13
0x140041f78  call    cs:__imp_IoSetTopLevelIrp
0x140041f7f  nop     dword ptr [rax+rax+00h]
0x140041f84  and     qword ptr [rdi+8], 0FFFFFFFFFFEFFFFFh
0x140041f8c  jmp     loc_140041E3E
0x140041f91  call    ?RefsCommitCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsCommitCurrentTransaction(_IRP_CONTEXT *,uchar)
0x140041f96  jmp     loc_140041B99
0x140041f9b  lea     rax, [rdi+240h]
0x140041fa2  mov     rcx, [rax]
0x140041fa5  cmp     rcx, rax
0x140041fa8  jnz     loc_1400425D0
0x140041fae  mov     rcx, r8
0x140041fb1  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140041fb8  nop     dword ptr [rax+rax+00h]
0x140041fbd  test    rsi, rsi
0x140041fc0  jnz     short loc_140042006
0x140041fc2  mov     rcx, [r13+58h]
0x140041fc6  add     rcx, 40h ; '@'; Resource
0x140041fca  test    al, al
0x140041fcc  jz      loc_1400426C7
0x140041fd2  xor     edx, edx
0x140041fd4  call    cs:__imp_ExReleaseFastResource
0x140041fdb  nop     dword ptr [rax+rax+00h]
0x140041fe0  mov     rcx, [rsp+98h+var_48]
0x140041fe5  xor     r13d, r13d
0x140041fe8  mov     r8d, 827h
0x140041fee  mov     eax, 0FFFFh
0x140041ff3  add     [rsp+98h+arg_0], ax
0x140041ffb  jz      loc_140041C85
0x140042001  jmp     loc_140041CAE
0x140042006  mov     ecx, [rsi+10h]
0x140042009  test    al, al
0x14004200b  jnz     loc_1400425AD
0x140042011  lea     eax, [rcx-1]
0x140042014  mov     [rsi+10h], eax
0x140042017  test    eax, eax
0x140042019  jnz     short loc_14004202A
0x14004201b  mov     qword ptr [rsi], 0
0x140042022  mov     qword ptr [rsi+8], 0
0x14004202a  mov     rcx, [r13+58h]
0x14004202e  lea     rdx, [rsi+18h]
0x140042032  add     rcx, 40h ; '@'
0x140042036  call    cs:__imp_ExReleaseFastResource
0x14004203d  nop     dword ptr [rax+rax+00h]
0x140042042  jmp     short loc_140041FE0
0x140042044  movzx   ecx, byte ptr [rdi+28h]
  ... truncated ...
```
