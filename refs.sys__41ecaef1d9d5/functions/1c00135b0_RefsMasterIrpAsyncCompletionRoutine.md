# RefsMasterIrpAsyncCompletionRoutine

- ea: `0x1c00135b0`
- end: `0x1c0013d6f`
- name: `RefsMasterIrpAsyncCompletionRoutine`
- size: `1983`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1c000384c`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c0011660`
- `0x1c00135b0`
- `0x1c0013d80`
- `0x1c0014110`
- `0x1c0014410`
- `0x1c0014450`
- `0x1c003de50`
- `0x1c00582b0`
- `0x1c00592b0`
- `0x1c005936c`
- `0x1c005bb10`
- `0x1c005f020`
- `0x1c0068168`
- `0x1c006ac80`
- `0x1c0092b74`
- `0x1c0093ddc`
- `0x1c00a92a8`
- `0x1c00b1324`
- `0x1c00b3598`
- `0x1c00b3dc8`
- `0x1c00fd504`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x1c007474c`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c0074771`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c007474c`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c0074771`
- `ntoskrnl!KeSetEvent` at `0x1c00745c5`
- `ntoskrnl!KeSetEvent` at `0x1c00745c5`
- `ntoskrnl!DbgPrintEx` at `0x1c00746e1`
- `ntoskrnl!DbgPrintEx` at `0x1c00746e1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0013939`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0013a8e`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0013939`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0013a8e`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001391d`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0013a71`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001391d`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0013a71`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1c007470a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1c007470a`
- `ntoskrnl!_strnicmp` at `0x1c007479c`
- `ntoskrnl!_strnicmp` at `0x1c007479c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c0074780`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c0074780`
- `ntoskrnl!IoFreeMdl` at `0x1c0074a48`
- `ntoskrnl!IoFreeMdl` at `0x1c0074aa2`
- `ntoskrnl!IoFreeMdl` at `0x1c0074af1`
- `ntoskrnl!IoFreeMdl` at `0x1c0074a48`
- `ntoskrnl!IoFreeMdl` at `0x1c0074aa2`
- `ntoskrnl!IoFreeMdl` at `0x1c0074af1`
- `ntoskrnl!MmUnlockPages` at `0x1c0074a35`
- `ntoskrnl!MmUnlockPages` at `0x1c0074a8a`
- `ntoskrnl!MmUnlockPages` at `0x1c0074ad9`
- `ntoskrnl!MmUnlockPages` at `0x1c0074a35`
- `ntoskrnl!MmUnlockPages` at `0x1c0074a8a`
- `ntoskrnl!MmUnlockPages` at `0x1c0074ad9`
- `ntoskrnl!CcUnpinData` at `0x1c0074aba`
- `ntoskrnl!CcUnpinData` at `0x1c0074b09`
- `ntoskrnl!CcUnpinData` at `0x1c0074aba`
- `ntoskrnl!CcUnpinData` at `0x1c0074b09`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c00747e5`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c00747e5`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1c0074b67`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1c0074b67`
- `ntoskrnl!ExReleaseDisownedFastResource` at `0x1c00139af`
- `ntoskrnl!ExReleaseDisownedFastResource` at `0x1c00139af`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c00137c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0013b39`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0074959`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c007499d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c00137c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0013b39`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0074959`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c007499d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c00137f9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c00137f9`

## pseudocode

```c
__int64 __fastcall RefsMasterIrpAsyncCompletionRoutine(_QWORD *a1, __int64 a2, int *a3, __int64 a4)
{
  int v4; // eax
  __int64 v5; // r13
  __int64 v6; // rdi
  _QWORD *v9; // r15
  __int64 v10; // rbx
  ERESOURCE_THREAD v11; // rdx
  struct _ERESOURCE *v12; // r12
  NTSTATUS v13; // ecx
  PDEVICE_OBJECT *v14; // r8
  const char *v15; // r9
  __int64 v16; // rax
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // r10
  __int64 v30; // r15
  _QWORD *v31; // rdx
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rcx
  __int64 v33; // rdx
  __int64 v34; // rax
  bool v35; // zf
  struct _MDL *v36; // rcx
  void *v37; // rcx
  struct _MDL *v38; // rcx
  void *v39; // rcx
  __int64 v40; // rcx
  unsigned int v41; // eax
  struct _SLIST_ENTRY *v42; // rdi
  unsigned __int64 v43; // rbx
  __int64 v44; // rcx
  __int64 v45; // rcx
  int v46; // r8d
  int v47; // r9d
  int v48; // r8d
  int v49; // eax
  unsigned int v50; // eax
  unsigned __int64 v51; // rbx
  __int64 v53; // r15
  char v54; // r10
  _QWORD *v55; // rdx
  _QWORD *v56; // r8
  _QWORD *v57; // rcx
  __int64 v58; // rcx
  struct _KTHREAD *CurrentThread; // rbx
  unsigned __int32 v60; // eax
  __int64 v61; // rax
  __int64 v62; // rax
  _QWORD *v63; // r8
  _QWORD *v64; // rcx
  int v65; // ecx
  int v66; // eax
  bool v67; // al
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  __int64 v70; // rdx
  int v71; // eax
  int v72; // eax
  int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // rdx
  struct _MDL *v76; // rcx
  struct _MDL *Next; // rdi
  __int64 v78; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v79[2]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v80[2]; // [rsp+58h] [rbp-31h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-21h] BYREF
  struct _KLOCK_QUEUE_HANDLE v82; // [rsp+80h] [rbp-9h] BYREF
  char v84; // [rsp+F8h] [rbp+6Fh]
  ERESOURCE_THREAD ResourceThreadId; // [rsp+108h] [rbp+7Fh]

  v4 = *a3;
  v5 = 0;
  v6 = *(_QWORD *)(a2 + 184);
  v84 = 1;
  v9 = a1;
  v78 = 0;
  if ( (v4 & 0x40) != 0 )
  {
    KeSetEvent((PRKEVENT)(a3 + 2), 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_a1f0ec5c527f3c4dda14189a8c4d4f39_Traceguids, 3221225494LL);
    }
    if ( !RefsStatusDebugEnabled )
      return 3221225494LL;
LABEL_207:
    RefsStatusDebug(-1073741802);
    return 3221225494LL;
  }
  v10 = *((_QWORD *)a3 + 25);
  if ( v10 )
  {
    if ( *(_BYTE *)(v10 + 282) )
    {
      v65 = *(_DWORD *)(a2 + 48);
      if ( (int)(v65 + 0x80000000) >= 0 && v65 != -1073741608 && *(_BYTE *)v6 == 4 )
      {
        v67 = 0;
        if ( (unsigned __int8)MsSetWPOutOfSync(*(_QWORD *)(v10 + 296)) )
        {
          v66 = *(_DWORD *)(a2 + 48);
          if ( v66 == -1073741391 || v66 == -1073741435 )
            v67 = 1;
        }
        *(_BYTE *)(v10 + 281) |= v67;
      }
    }
    if ( a3[67] || (a3[60] & 0x40) != 0 || *(_BYTE *)(v10 + 281) )
    {
      v58 = *(_QWORD *)(v10 + 304);
      LOBYTE(a4) = 1;
      *(_QWORD *)(v10 + 304) = 0;
      v78 = v58;
      *(_QWORD *)(v58 + 144) = a3;
      *(_DWORD *)(v58 + 8) |= 0x9010u;
      *(_DWORD *)(v58 + 12) |= 0x100u;
      RefsAddToWorkqueInternal(v58, a2, 0, a4);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_a1f0ec5c527f3c4dda14189a8c4d4f39_Traceguids, 3221225494LL);
      }
      if ( RefsStatusDebugEnabled )
      {
        CurrentThread = KeGetCurrentThread();
        if ( RefsStatusDisplayStatus == -1073741802 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", CurrentThread, -1073741802, "DevIoSup.c", 11463);
        if ( (RefsStatusBreakOnStatus && RefsStatusBreakOnStatus == -1073741802
           || RefsStatusBreakOnWin32Error && RefsStatusBreakOnWin32Error == RtlNtStatusToDosErrorNoTeb(-1073741802))
          && (!RefsStatusBreakForThread || (struct _KTHREAD *)RefsStatusBreakForThread == CurrentThread)
          && (!RefsStatusBreakForProcess || (PEPROCESS)RefsStatusBreakForProcess == IoGetCurrentProcess()) )
        {
          if ( !RefsStatusBreakForImage
            || (CurrentProcess = IoGetCurrentProcess(),
                ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
                !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu)) )
          {
            __int2c();
          }
        }
        v60 = _InterlockedIncrement(&RefsStatusNextQueueEntry);
        if ( RefsStatusDebugQueueMax == 1024 )
          v61 = v60 & 0x3FF;
        else
          v61 = v60 % RefsStatusDebugQueueMax;
        v62 = 4 * v61;
        RefsStatusQueue[v62] = (__int64)CurrentThread;
        LODWORD(RefsStatusQueue[v62 + 1]) = -1073741802;
        RefsStatusQueue[v62 + 2] = (__int64)"DevIoSup.c";
        LODWORD(RefsStatusQueue[v62 + 3]) = 11463;
      }
      return 3221225494LL;
    }
  }
  v11 = *((_QWORD *)a3 + 7);
  v12 = (struct _ERESOURCE *)*((_QWORD *)a3 + 6);
  ResourceThreadId = v11;
  if ( (*a3 & 0x80u) != 0 )
  {
    v70 = *(unsigned int *)(a2 + 48);
    if ( (int)v70 >= 0 )
      RefsIncReadCopyCounts(v9 + 42, v70, 0);
    v11 = ResourceThreadId;
  }
  v13 = *(_DWORD *)(a2 + 48);
  v14 = &WPP_GLOBAL_Control;
  v15 = "DevIoSup.c";
  if ( (unsigned int)v13 <= 0x40000009 || v13 >= 1073741836 )
  {
    *(_QWORD *)(a2 + 56) = (unsigned int)a3[48];
    if ( *((_BYTE *)a3 + 196) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_a1f0ec5c527f3c4dda14189a8c4d4f39_Traceguids, 303);
        v11 = ResourceThreadId;
        v15 = "DevIoSup.c";
      }
      if ( RefsStatusDebugEnabled )
      {
        RefsStatusDebug(303);
        v11 = ResourceThreadId;
      }
      v5 = v78;
      *(_DWORD *)(a2 + 48) = 303;
    }
    if ( (*a3 & 2) == 0 )
    {
      v16 = *(_QWORD *)(v6 + 48);
      if ( v16 )
      {
        v17 = *(_DWORD *)(v16 + 80);
        if ( *(_BYTE *)v6 == 3 )
          v18 = v17 | 0x80000;
        else
          v18 = v17 | 0x1000;
        *(_DWORD *)(v16 + 80) = v18;
      }
    }
    if ( *(_BYTE *)v6 == 4 )
    {
      v5 = v78;
      v9[808] = MEMORY[0xFFFFF78000000014];
    }
    goto LABEL_18;
  }
  v71 = *a3;
  if ( (*a3 & 0x42) != 0 )
    goto LABEL_163;
  if ( v13 != -2147483626 && FsRtlIsTotalDeviceFailure(v13) )
  {
    v71 = *a3;
    v11 = ResourceThreadId;
LABEL_163:
    if ( (v71 & 2) != 0 && *(_DWORD *)(a2 + 48) == -1073741670 && *(_BYTE *)v6 == 3 )
      ++RefsFailedHandedOffPagingReads;
    goto LABEL_18;
  }
  if ( !*(_DWORD *)(a2 + 24) )
    RefsTelemetryPostFileObjectError((_DWORD)v9, a2, 0, 0, *(_DWORD *)(a2 + 48));
  LOBYTE(v11) = 1;
  RefsInitializeIrpContext(a2, v11, 0, &v78);
  v5 = v78;
  v11 = ResourceThreadId;
  if ( v78 )
  {
    *(_QWORD *)(v78 + 144) = a3;
    *(_DWORD *)(v5 + 8) |= 0x8010u;
    v84 = 0;
  }
LABEL_18:
  v19 = *((_QWORD *)a3 + 25);
  if ( !v19 )
    goto LABEL_65;
  v20 = *(_QWORD *)(v19 + 296);
  if ( v20 )
  {
    v21 = *(_QWORD *)(v19 + 296);
    if ( *(_BYTE *)(v19 + 282) )
    {
      v11 = *(unsigned int *)(a2 + 48);
      if ( (v11 & 0x80000000) != 0LL && (_DWORD)v11 != -1073741608 && *(_BYTE *)v6 == 4 )
      {
        MsSetWPOutOfSync(v20);
        v21 = *(_QWORD *)(v19 + 296);
      }
    }
    MsReacquireTransactionContextThread(v21, v11, v14, v15);
    v22 = *(_DWORD *)(a2 + 48);
    if ( (unsigned int)v22 > 0x40000009 && v22 < 1073741836 )
      MsAbortTransaction(*(_QWORD *)(v19 + 296));
    else
      MsCommitTransaction(*(CmsTransactionContext **)(v19 + 296));
    MsDeleteTransactionContext(*(_QWORD *)(v19 + 296));
  }
  v23 = *(_QWORD *)(v19 + 256);
  if ( v23 )
  {
    v24 = v19 + 72;
    v25 = *(_QWORD *)(v19 + 272);
    v26 = *(_QWORD *)(v19 + 264);
    v27 = *(_QWORD *)(v23 + 56);
    if ( !*(_BYTE *)(v19 + 280) )
    {
      if ( *(_DWORD *)(v27 + 464) == 12 )
      {
        v28 = -4096;
        v29 = 4095;
      }
      else
      {
        v28 = -16384;
        v29 = 0x3FFF;
      }
      v30 = *(_QWORD *)(v23 + 64);
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( *(_QWORD *)(v30 + 8) )
      {
        v79[0] = v26 & v28;
        v79[1] = (v28 & (v25 + v29 + v26)) - 1;
        if ( v19 == -72 || !*(_QWORD *)(v19 + 80) )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v30, &LockHandle);
          v72 = FsLibPrivateUnlockRange(*(PVOID *)(v30 + 8));
          if ( v72 == -1073741698 )
          {
            if ( !*(_QWORD *)(v30 + 24) )
              goto LABEL_34;
            goto LABEL_122;
          }
          if ( v72 < 0 )
            goto LABEL_34;
        }
        else
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v30, &LockHandle);
          v31 = *(_QWORD **)(v30 + 8);
          *(_QWORD *)(*(_QWORD *)(v19 + 72) + 8LL) &= ~*(_QWORD *)(v19 + 80);
          if ( *(_QWORD **)v24 != v31 && !*(_QWORD *)(*(_QWORD *)v24 + 8LL) )
          {
            v56 = v31;
            v57 = v31;
            if ( v31 )
            {
              while ( v57[1] || v57 == v31 )
              {
                v56 = v57;
                v57 = (_QWORD *)*v57;
                if ( !v57 )
                  goto LABEL_33;
              }
              *v56 = *v57;
              ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v57);
            }
          }
        }
LABEL_33:
        if ( !*(_QWORD *)(v30 + 24) )
        {
LABEL_34:
          p_LockHandle = &LockHandle;
          goto LABEL_35;
        }
LABEL_122:
        FsLibPrivateCheckWaitingRangeLocks(v30, v30, v79);
        goto LABEL_34;
      }
LABEL_37:
      v9 = a1;
      *(_QWORD *)(v19 + 256) = 0;
      goto LABEL_38;
    }
    v53 = *(_QWORD *)(v23 + 64);
    v54 = *(_BYTE *)(v27 + 464);
    memset(&v82, 0, sizeof(v82));
    if ( !*(_QWORD *)(v53 + 16) )
      goto LABEL_37;
    v80[0] = v26 >> v54 << v54;
    v80[1] = ((v25 + v26 + *(unsigned int *)(v27 + 456)) >> v54 << v54) - 1;
    if ( v19 == -72 || !*(_QWORD *)(v19 + 80) )
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v53, &v82);
      v73 = FsLibPrivateUnlockRange(*(PVOID *)(v53 + 16));
      if ( v73 == -1073741698 )
      {
        if ( !*(_QWORD *)(v53 + 24) )
          goto LABEL_98;
        goto LABEL_123;
      }
      if ( v73 < 0 )
        goto LABEL_98;
    }
    else
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v53, &v82);
      v55 = *(_QWORD **)(v53 + 16);
      *(_QWORD *)(*(_QWORD *)(v19 + 72) + 8LL) &= ~*(_QWORD *)(v19 + 80);
      if ( *(_QWORD **)v24 != v55 && !*(_QWORD *)(*(_QWORD *)v24 + 8LL) )
      {
        v63 = v55;
        v64 = v55;
        if ( v55 )
        {
          while ( v64[1] || v64 == v55 )
          {
            v63 = v64;
            v64 = (_QWORD *)*v64;
            if ( !v64 )
              goto LABEL_97;
          }
          *v63 = *v64;
          ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v64);
        }
      }
    }
LABEL_97:
    if ( !*(_QWORD *)(v53 + 24) )
    {
LABEL_98:
      p_LockHandle = &v82;
LABEL_35:
      KeReleaseInStackQueuedSpinLock(p_LockHandle);
      if ( v19 != -72 )
        *(_QWORD *)(v19 + 80) = 0;
      goto LABEL_37;
    }
LABEL_123:
    FsLibPrivateCheckWaitingRangeLocks(v53, v53, v80);
    goto LABEL_98;
  }
LABEL_38:
  if ( *(_QWORD *)(v19 + 16) )
  {
    v74 = *(_QWORD *)(a2 + 8);
    *(_DWORD *)(v74 + 40) = *(_DWORD *)(v19 + 8);
    v75 = *(_QWORD *)(a2 + 8);
    if ( *(_QWORD *)(v19 + 32) == v75 )
    {
      *(_QWORD *)(v19 + 32) = 0;
      *(_QWORD *)(v19 + 40) = 0;
      *(_DWORD *)(v19 + 48) = 0;
      v75 = *(_QWORD *)(a2 + 8);
    }
    RefsDeleteMdlAndBuffer(v74, v75);
  }
  else
  {
    v33 = *(_QWORD *)(v19 + 32);
    if ( v33 )
    {
      RefsDeleteMdlAndBuffer(v23, v33);
      *(_QWORD *)(v19 + 32) = 0;
      *(_QWORD *)(v19 + 40) = 0;
      *(_DWORD *)(v19 + 48) = 0;
    }
  }
  if ( *(_QWORD *)(v19 + 168) )
  {
    do
    {
      v76 = *(struct _MDL **)(v19 + 168);
      Next = v76->Next;
      MmUnlockPages(v76);
      IoFreeMdl(*(PMDL *)(v19 + 168));
      *(_QWORD *)(v19 + 168) = Next;
    }
    while ( Next );
  }
  v34 = *(_QWORD *)(v19 + 16);
  if ( v34 )
  {
    *(_QWORD *)(a2 + 8) = v34;
    *(_QWORD *)(a2 + 112) = *(_QWORD *)(v19 + 24);
  }
  if ( *(_QWORD *)(v19 + 184) )
    RefsDeleteMdlAndBuffer(v23, 0);
  v35 = *(_BYTE *)(v19 + 216) == 0;
  *(_QWORD *)(v19 + 16) = 0;
  *(_QWORD *)(v19 + 24) = 0;
  *(_QWORD *)v19 = 0;
  *(_QWORD *)(v19 + 184) = 0;
  *(_DWORD *)(v19 + 8) = 0;
  if ( !v35 )
  {
    MmUnlockPages(*(PMDL *)(v19 + 192));
    *(_BYTE *)(v19 + 216) = 0;
  }
  v36 = *(struct _MDL **)(v19 + 192);
  if ( v36 )
  {
    IoFreeMdl(v36);
    *(_QWORD *)(v19 + 192) = 0;
  }
  v37 = *(void **)(v19 + 208);
  if ( v37 )
  {
    CcUnpinData(v37);
    *(_QWORD *)(v19 + 208) = 0;
  }
  v35 = *(_BYTE *)(v19 + 248) == 0;
  *(_QWORD *)(v19 + 200) = 0;
  if ( !v35 )
  {
    MmUnlockPages(*(PMDL *)(v19 + 224));
    *(_BYTE *)(v19 + 248) = 0;
  }
  v38 = *(struct _MDL **)(v19 + 224);
  if ( v38 )
  {
    IoFreeMdl(v38);
    *(_QWORD *)(v19 + 224) = 0;
  }
  v39 = *(void **)(v19 + 240);
  if ( v39 )
  {
    CcUnpinData(v39);
    *(_QWORD *)(v19 + 240) = 0;
  }
  v40 = *(_QWORD *)(v19 + 304);
  *(_QWORD *)(v19 + 232) = 0;
  if ( v40 )
    RefsCleanupIrpContext(v40, 0);
  v41 = *(_DWORD *)(v19 - 8);
  v42 = (struct _SLIST_ENTRY *)(v19 - 8);
  if ( v41 >= RefsNumberProcessors )
    v41 %= (unsigned int)RefsNumberProcessors;
  v43 = RefsCompressCtxLookasideList + ((unsigned __int64)v41 << 7);
  ++*(_DWORD *)(v43 + 28);
  if ( ExQueryDepthSList((PSLIST_HEADER)v43) >= *(_WORD *)(v43 + 16) )
  {
    ++*(_DWORD *)(v43 + 32);
    (*(void (__fastcall **)(struct _SLIST_ENTRY *))(v43 + 56))(v42);
  }
  else
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)v43, v42);
  }
  v11 = ResourceThreadId;
  *((_QWORD *)a3 + 25) = 0;
LABEL_65:
  v44 = *((_QWORD *)a3 + 21);
  if ( v44 )
  {
    RefsReleaseRangeLock(v44, *((_QWORD *)a3 + 22), a3[46], *((unsigned __int8 *)a3 + 188), (__int64)(a3 + 8));
    v11 = ResourceThreadId;
    *((_QWORD *)a3 + 21) = 0;
  }
  if ( v12 )
    ExReleaseResourceForThreadLite(v12, v11);
  v45 = *((_QWORD *)a3 + 8);
  if ( v45 )
  {
    v46 = a3[38];
    if ( !v46 )
      goto LABEL_201;
    v47 = a3[39];
    v48 = v46 - 1;
    a3[38] = v48;
    if ( !v48 )
      v47 &= ~2u;
    a3[39] = v47 & 0xFFFFFFFB;
    ExReleaseDisownedFastResource(v45);
  }
  if ( !v84 )
  {
    RefsPostRequest((PVOID)v5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_a1f0ec5c527f3c4dda14189a8c4d4f39_Traceguids, 3221225494LL);
    }
    if ( !RefsStatusDebugEnabled )
      return 3221225494LL;
    goto LABEL_207;
  }
  if ( (dword_1C012E0B0 & 0x400) != 0 )
    RefsCompleteThroughDebugInfoIrpImplementation(a2, v11, v14, v15);
  v49 = *(_DWORD *)(a2 + 48);
  if ( ((unsigned int)v49 <= 0x40000009 || v49 >= 1073741836) && v9[535] )
    RefsTelemetryCollectReadWritePerfData(v9 + 42, a2, a3, v15);
  if ( v5 )
  {
    *(_QWORD *)(v5 + 144) = 0;
    *(_DWORD *)(v5 + 8) &= 0xFFFF7FEF;
  }
  if ( *((int **)a3 + 28) != a3 + 56 || a3[67] || (a3[60] & 0x40) != 0 )
  {
    MsUpdateCacheFromCacheContext(v9[55], a3 + 54);
    MsFreeCacheContextResources(v9[55], a3 + 54);
  }
  if ( a3[38] )
LABEL_201:
    __fastfail(5u);
  a3[39] &= ~1u;
  v50 = *(a3 - 2);
  if ( v50 >= RefsNumberProcessors )
    v50 %= (unsigned int)RefsNumberProcessors;
  v51 = RefsIoContextLookasideList + ((unsigned __int64)v50 << 7);
  ++*(_DWORD *)(v51 + 28);
  if ( ExQueryDepthSList((PSLIST_HEADER)v51) >= *(_WORD *)(v51 + 16) )
  {
    ++*(_DWORD *)(v51 + 32);
    (*(void (__fastcall **)(int *))(v51 + 56))(a3 - 2);
  }
  else
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)v51, (PSLIST_ENTRY)(a3 - 2));
  }
  return 0;
}

```

## disassembly

```asm
0x1c00135b0  mov     [rsp-8+arg_0], rcx
0x1c00135b5  push    rbp
0x1c00135b6  push    rbx
0x1c00135b7  push    rsi
0x1c00135b8  push    rdi
0x1c00135b9  push    r13
0x1c00135bb  push    r14
0x1c00135bd  push    r15
0x1c00135bf  lea     rbp, [rsp-27h]
0x1c00135c4  sub     rsp, 0B0h
0x1c00135cb  mov     eax, [r8]
0x1c00135ce  xor     r13d, r13d
0x1c00135d1  mov     rdi, [rdx+0B8h]
0x1c00135d8  mov     rsi, r8
0x1c00135db  mov     [rbp+57h+arg_8], 1
0x1c00135df  mov     r14, rdx
0x1c00135e2  mov     byte ptr [rbp+57h+arg_10], 0
0x1c00135e6  mov     r15, rcx
0x1c00135e9  mov     [rbp+57h+var_A0], r13
0x1c00135ed  test    al, 40h
0x1c00135ef  jnz     loc_1C00745BC
0x1c00135f5  mov     rbx, [r8+0C8h]
0x1c00135fc  test    rbx, rbx
0x1c00135ff  jz      short loc_1C0013635
0x1c0013601  cmp     [rbx+11Ah], r13b
0x1c0013608  jnz     loc_1C0074628
0x1c001360e  cmp     [rsi+10Ch], r13d
0x1c0013615  ja      loc_1C0013BAC
0x1c001361b  test    byte ptr [rsi+0F0h], 40h
0x1c0013622  jnz     loc_1C0013BAC
0x1c0013628  cmp     [rbx+119h], r13b
0x1c001362f  jnz     loc_1C0013BAC
0x1c0013635  mov     rdx, [rsi+38h]
0x1c0013639  mov     eax, [rsi]
0x1c001363b  mov     [rsp+0E0h+var_38], r12
0x1c0013643  mov     r12, [rsi+30h]
0x1c0013647  mov     [rbp+57h+ResourceThreadId], rdx
0x1c001364b  test    al, al
0x1c001364d  js      loc_1C00747B7
0x1c0013653  mov     ecx, [r14+30h]; Status
0x1c0013657  lea     r8, WPP_GLOBAL_Control
0x1c001365e  lea     r9, aDeviosupC; "DevIoSup.c"
0x1c0013665  cmp     ecx, 40000009h
0x1c001366b  jbe     short loc_1C0013679
0x1c001366d  cmp     ecx, 4000000Ch
0x1c0013673  jl      loc_1C00747D7
0x1c0013679  mov     eax, [rsi+0C0h]
0x1c001367f  mov     [r14+38h], rax
0x1c0013683  cmp     [rsi+0C4h], r13b
0x1c001368a  jnz     loc_1C0074888
0x1c0013690  mov     eax, [rsi]
0x1c0013692  test    al, 2
0x1c0013694  jnz     short loc_1C00136B2
0x1c0013696  mov     rax, [rdi+30h]
0x1c001369a  test    rax, rax
0x1c001369d  jz      short loc_1C00136B2
0x1c001369f  cmp     byte ptr [rdi], 3
0x1c00136a2  mov     ecx, [rax+50h]
0x1c00136a5  jnz     loc_1C0013AAF
0x1c00136ab  bts     ecx, 13h
0x1c00136af  mov     [rax+50h], ecx
0x1c00136b2  cmp     byte ptr [rdi], 4
0x1c00136b5  jz      loc_1C0013AB8
0x1c00136bb  mov     rbx, [rsi+0C8h]
0x1c00136c2  test    rbx, rbx
0x1c00136c5  jz      loc_1C0013954
0x1c00136cb  mov     rcx, [rbx+128h]
0x1c00136d2  test    rcx, rcx
0x1c00136d5  jz      short loc_1C0013722
0x1c00136d7  cmp     byte ptr [rbx+11Ah], 0
0x1c00136de  mov     rax, rcx
0x1c00136e1  jnz     loc_1C00748FC
0x1c00136e7  mov     rcx, rax
0x1c00136ea  call    MsReacquireTransactionContextThread
0x1c00136ef  mov     eax, [r14+30h]
0x1c00136f3  cmp     eax, 40000009h
0x1c00136f8  jbe     short loc_1C0013705
0x1c00136fa  cmp     eax, 4000000Ch
0x1c00136ff  jl      loc_1C007492E
0x1c0013705  mov     rcx, [rbx+128h]; this
0x1c001370c  xor     r8d, r8d
0x1c001370f  xor     edx, edx
0x1c0013711  call    MsCommitTransaction
0x1c0013716  mov     rcx, [rbx+128h]
0x1c001371d  call    MsDeleteTransactionContext
0x1c0013722  mov     rcx, [rbx+100h]
0x1c0013729  test    rcx, rcx
0x1c001372c  jz      loc_1C00749DA
0x1c0013732  cmp     byte ptr [rbx+118h], 0
0x1c0013739  lea     rdi, [rbx+48h]
0x1c001373d  mov     r9, [rbx+110h]
0x1c0013744  mov     r8, [rbx+108h]
0x1c001374b  mov     rdx, [rcx+38h]
0x1c001374f  jnz     loc_1C0013AD2
0x1c0013755  cmp     dword ptr [rdx+1D0h], 0Ch
0x1c001375c  jnz     loc_1C0074940
0x1c0013762  mov     rdx, 0FFFFFFFFFFFFF000h
0x1c0013769  mov     r10d, 0FFFh
0x1c001376f  mov     r15, [rcx+40h]
0x1c0013773  xor     eax, eax
0x1c0013775  xorps   xmm0, xmm0
0x1c0013778  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1c001377c  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1c0013780  cmp     [r15+8], rax
0x1c0013784  jz      loc_1C0013812
0x1c001378a  mov     rax, rdx
0x1c001378d  and     rax, r8
0x1c0013790  mov     [rbp+57h+var_98], rax
0x1c0013794  lea     rax, [r10+r8]
0x1c0013798  add     rax, r9
0x1c001379b  and     rax, rdx
0x1c001379e  dec     rax
0x1c00137a1  mov     [rbp+57h+var_90], rax
0x1c00137a5  test    rdi, rdi
0x1c00137a8  jz      loc_1C0074952
0x1c00137ae  cmp     qword ptr [rdi+8], 0
0x1c00137b3  jz      loc_1C0074952
0x1c00137b9  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x1c00137bd  mov     rcx, r15; SpinLock
0x1c00137c0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c00137c7  nop     dword ptr [rax+rax+00h]
0x1c00137cc  mov     rax, [rdi+8]
0x1c00137d0  mov     rdx, [r15+8]
0x1c00137d4  not     rax
0x1c00137d7  mov     rcx, [rdi]
0x1c00137da  and     [rcx+8], rax
0x1c00137de  mov     rax, [rdi]
0x1c00137e1  cmp     rax, rdx
0x1c00137e4  jnz     loc_1C0013B77
0x1c00137ea  cmp     qword ptr [r15+18h], 0
0x1c00137ef  jnz     loc_1C0013D09
0x1c00137f5  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1c00137f9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c0013800  nop     dword ptr [rax+rax+00h]
0x1c0013805  test    rdi, rdi
0x1c0013808  jz      short loc_1C0013812
0x1c001380a  mov     qword ptr [rdi+8], 0
0x1c0013812  mov     r15, [rbp+57h+arg_0]
0x1c0013816  xor     edi, edi
0x1c0013818  mov     [rbx+100h], rdi
0x1c001381f  cmp     qword ptr [rbx+10h], 0
0x1c0013824  jnz     loc_1C00749E1
0x1c001382a  mov     rdx, [rbx+20h]
0x1c001382e  test    rdx, rdx
0x1c0013831  jnz     loc_1C0074A12
0x1c0013837  cmp     qword ptr [rbx+0A8h], 0
0x1c001383f  jnz     loc_1C0074A2B
0x1c0013845  mov     rax, [rbx+10h]
0x1c0013849  test    rax, rax
0x1c001384c  jnz     loc_1C0074A65
0x1c0013852  mov     r8, [rbx+0B8h]
0x1c0013859  test    r8, r8
0x1c001385c  jnz     loc_1C0074A76
0x1c0013862  cmp     byte ptr [rbx+0D8h], 0
0x1c0013869  mov     [rbx+10h], rdi
0x1c001386d  mov     [rbx+18h], rdi
0x1c0013871  mov     [rbx], rdi
0x1c0013874  mov     [rbx+0B8h], rdi
0x1c001387b  mov     [rbx+8], edi
0x1c001387e  jnz     loc_1C0074A83
0x1c0013884  mov     rcx, [rbx+0C0h]; Mdl
0x1c001388b  test    rcx, rcx
0x1c001388e  jnz     loc_1C0074AA2
0x1c0013894  mov     rcx, [rbx+0D0h]; Bcb
0x1c001389b  test    rcx, rcx
0x1c001389e  jnz     loc_1C0074ABA
0x1c00138a4  cmp     byte ptr [rbx+0F8h], 0
0x1c00138ab  mov     [rbx+0C8h], rdi
0x1c00138b2  jnz     loc_1C0074AD2
0x1c00138b8  mov     rcx, [rbx+0E0h]; Mdl
0x1c00138bf  test    rcx, rcx
0x1c00138c2  jnz     loc_1C0074AF1
0x1c00138c8  mov     rcx, [rbx+0F0h]; Bcb
0x1c00138cf  test    rcx, rcx
0x1c00138d2  jnz     loc_1C0074B09
0x1c00138d8  mov     rcx, [rbx+130h]
0x1c00138df  mov     [rbx+0E8h], rdi
0x1c00138e6  test    rcx, rcx
0x1c00138e9  jz      short loc_1C00138F2
0x1c00138eb  xor     edx, edx
0x1c00138ed  call    RefsCleanupIrpContext
0x1c00138f2  mov     eax, [rbx-8]
0x1c00138f5  lea     rdi, [rbx-8]
0x1c00138f9  mov     ecx, cs:RefsNumberProcessors
0x1c00138ff  mov     r8, cs:RefsCompressCtxLookasideList
0x1c0013906  cmp     eax, ecx
0x1c0013908  jnb     loc_1C0074B21
0x1c001390e  mov     ebx, eax
0x1c0013910  shl     rbx, 7
0x1c0013914  add     rbx, r8
0x1c0013917  mov     rcx, rbx; SListHead
0x1c001391a  inc     dword ptr [rbx+1Ch]
0x1c001391d  call    cs:__imp_ExQueryDepthSList
0x1c0013924  nop     dword ptr [rax+rax+00h]
0x1c0013929  cmp     ax, [rbx+10h]
0x1c001392d  jnb     loc_1C0013C9E
0x1c0013933  mov     rdx, rdi; ListEntry
0x1c0013936  mov     rcx, rbx; ListHead
0x1c0013939  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c0013940  nop     dword ptr [rax+rax+00h]
0x1c0013945  mov     rdx, [rbp+57h+ResourceThreadId]; ResourceThreadId
0x1c0013949  mov     qword ptr [rsi+0C8h], 0
0x1c0013954  mov     rcx, [rsi+0A8h]
0x1c001395b  test    rcx, rcx
0x1c001395e  jnz     loc_1C0074B2C
0x1c0013964  test    r12, r12
0x1c0013967  jnz     loc_1C0074B64
0x1c001396d  mov     rcx, [rsi+40h]
0x1c0013971  mov     r12, [rsp+0E0h+var_38]
0x1c0013979  test    rcx, rcx
0x1c001397c  jz      short loc_1C00139BB
0x1c001397e  lea     rdx, [rsi+50h]
0x1c0013982  mov     r8d, [rdx+48h]
0x1c0013986  test    r8d, r8d
0x1c0013989  jz      loc_1C0074BCB
0x1c001398f  mov     r9d, [rdx+4Ch]
0x1c0013993  dec     r8d
0x1c0013996  mov     eax, r9d
0x1c0013999  mov     [rdx+48h], r8d
0x1c001399d  and     eax, 0FFFFFFFDh
0x1c00139a0  test    r8d, r8d
0x1c00139a3  cmovz   r9d, eax
0x1c00139a7  and     r9d, 0FFFFFFFBh
0x1c00139ab  mov     [rdx+4Ch], r9d
0x1c00139af  call    cs:__imp_ExReleaseDisownedFastResource
0x1c00139b6  nop     dword ptr [rax+rax+00h]
0x1c00139bb  cmp     [rbp+57h+arg_8], 0
0x1c00139bf  jz      loc_1C0074BDD
0x1c00139c5  test    cs:dword_1C012E0B0, 400h
0x1c00139cf  jnz     loc_1C0074B79
0x1c00139d5  mov     eax, [r14+30h]
0x1c00139d9  lea     rcx, [r15+150h]
0x1c00139e0  cmp     eax, 40000009h
0x1c00139e5  jbe     short loc_1C00139EE
0x1c00139e7  cmp     eax, 4000000Ch
0x1c00139ec  jl      short loc_1C0013A03
0x1c00139ee  cmp     qword ptr [rcx+0F68h], 0
0x1c00139f6  jz      short loc_1C0013A03
0x1c00139f8  mov     r8, rsi
0x1c00139fb  mov     rdx, r14
0x1c00139fe  call    RefsTelemetryCollectReadWritePerfData
0x1c0013a03  test    r13, r13
0x1c0013a06  jnz     loc_1C0074B87
0x1c0013a0c  lea     rax, [rsi+0E0h]
0x1c0013a13  cmp     [rax], rax
0x1c0013a16  jnz     loc_1C0074B9F
0x1c0013a1c  cmp     dword ptr [rsi+10Ch], 0
0x1c0013a23  ja      loc_1C0074B9F
0x1c0013a29  test    byte ptr [rsi+0F0h], 40h
0x1c0013a30  jnz     loc_1C0074B9F
0x1c0013a36  cmp     dword ptr [rsi+98h], 0
0x1c0013a3d  jnz     loc_1C0074BCB
0x1c0013a43  and     dword ptr [rsi+9Ch], 0FFFFFFFEh
0x1c0013a4a  mov     eax, [rsi-8]
0x1c0013a4d  mov     ecx, cs:RefsNumberProcessors
0x1c0013a53  mov     r8, cs:RefsIoContextLookasideList
0x1c0013a5a  cmp     eax, ecx
0x1c0013a5c  jnb     loc_1C0074BD2
0x1c0013a62  mov     ebx, eax
0x1c0013a64  shl     rbx, 7
0x1c0013a68  add     rbx, r8
0x1c0013a6b  mov     rcx, rbx; SListHead
0x1c0013a6e  inc     dword ptr [rbx+1Ch]
0x1c0013a71  call    cs:__imp_ExQueryDepthSList
0x1c0013a78  nop     dword ptr [rax+rax+00h]
0x1c0013a7d  cmp     ax, [rbx+10h]
0x1c0013a81  jnb     loc_1C0013CB3
0x1c0013a87  lea     rdx, [rsi-8]; ListEntry
0x1c0013a8b  mov     rcx, rbx; ListHead
0x1c0013a8e  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c0013a95  nop     dword ptr [rax+rax+00h]
0x1c0013a9a  xor     eax, eax
0x1c0013a9c  add     rsp, 0B0h
0x1c0013aa3  pop     r15
0x1c0013aa5  pop     r14
0x1c0013aa7  pop     r13
0x1c0013aa9  pop     rdi
0x1c0013aaa  pop     rsi
0x1c0013aab  pop     rbx
0x1c0013aac  pop     rbp
0x1c0013aad  retn
0x1c0013aaf  bts     ecx, 0Ch
0x1c0013ab3  jmp     loc_1C00136AF
0x1c0013ab8  mov     rax, ds:0FFFFF78000000014h
0x1c0013ac2  mov     r13, [rbp+57h+var_A0]
0x1c0013ac6  mov     [r15+1940h], rax
0x1c0013acd  jmp     loc_1C00136BB
0x1c0013ad2  mov     r15, [rcx+40h]
0x1c0013ad6  xor     eax, eax
0x1c0013ad8  movsx   r10d, byte ptr [rdx+1D0h]
0x1c0013ae0  xorps   xmm0, xmm0
0x1c0013ae3  movups  xmmword ptr [rbp+57h+var_60.LockQueue.Next], xmm0
0x1c0013ae7  mov     qword ptr [rbp+57h+var_60.OldIrql], rax
0x1c0013aeb  cmp     [r15+10h], rax
0x1c0013aef  jz      loc_1C0013812
0x1c0013af5  mov     ecx, r10d
0x1c0013af8  mov     rax, r8
0x1c0013afb  sar     rax, cl
0x1c0013afe  shl     rax, cl
0x1c0013b01  mov     [rbp+57h+var_88], rax
  ... truncated ...
```
