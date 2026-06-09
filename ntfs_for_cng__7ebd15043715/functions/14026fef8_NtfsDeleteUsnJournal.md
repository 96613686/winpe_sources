# NtfsDeleteUsnJournal

- ea: `0x14026fef8`
- end: `0x140270e05`
- name: `NtfsDeleteUsnJournal`
- size: `3853`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401f5890`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000ea70`
- `0x140012e70`
- `0x14001e810`
- `0x140020524`
- `0x14002066c`
- `0x140020de0`
- `0x140021e60`
- `0x14002b4a0`
- `0x14002c130`
- `0x140037854`
- `0x14003ebc4`
- `0x1400543a0`
- `0x140059250`
- `0x14012c1ec`
- `0x140138b60`
- `0x140140380`
- `0x1401cb2c4`
- `0x1401cf24c`
- `0x1401d295c`
- `0x1401d2c34`
- `0x140230888`
- `0x14026fef8`
- `0x1402a4230`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1402709d2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1402709d2`
- `ntoskrnl!KeSetEvent` at `0x1402706b8`
- `ntoskrnl!KeSetEvent` at `0x1402706b8`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1402706e3`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1402706e3`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1402705b4`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1402705b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140270aad`
- `ntoskrnl!RtlInitUnicodeString` at `0x140270aad`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140270a45`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140270a45`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140270cc5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bac86`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140270cc5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bac86`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402709f6`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402709f6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1402709a6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1402709a6`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140270bd5`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140270bd5`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402708c0`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140270933`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402babf7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402708c0`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140270933`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402babf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140270677`
- `ntoskrnl!ExFreePoolWithTag` at `0x140270677`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402707b0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027081c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402707b0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027081c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402704d6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402704d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402704fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402704fd`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402706f9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402706f9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14027076d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14027076d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14026ff98`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14026ff98`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140270a58`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140270a58`
- `ntoskrnl!CcFlushCache` at `0x140270546`
- `ntoskrnl!CcFlushCache` at `0x140270546`

## pseudocode

```c
__int64 __fastcall NtfsDeleteUsnJournal(__int64 a1, IRP *a2)
{
  IRP *v2; // r13
  int v4; // edi
  int v5; // esi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct _IRP *MasterIrp; // r12
  PMDL MdlAddress; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  PFILE_OBJECT FileObject; // rcx
  PVOID FsContext; // r8
  unsigned __int16 *FsContext2; // rcx
  __int64 v14; // r14
  int v15; // eax
  unsigned __int16 *v16; // r9
  __int64 v17; // r10
  unsigned __int16 v18; // ax
  int v19; // eax
  __int64 v21; // rbx
  int v22; // ecx
  __int64 v23; // r12
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  __int64 v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // rax
  PEPROCESS v29; // rbx
  PEPROCESS v30; // rcx
  PEPROCESS *v31; // rax
  _QWORD **v32; // r8
  _QWORD *i; // rax
  __int64 v34; // rdx
  _QWORD *v35; // rcx
  __int64 *v36; // rax
  __int64 v37; // rcx
  __int64 **v38; // rdx
  struct _LIST_ENTRY *v39; // rdx
  char v40; // di
  __int64 v41; // rcx
  __int64 v42; // rcx
  int ActivityIdIrp; // eax
  char *v44; // rdx
  _QWORD *ActivityIdThread; // rax
  WCHAR *v46; // rdx
  const wchar_t *v47; // rcx
  int v48; // r8d
  const wchar_t *v49; // rcx
  const wchar_t *v50; // rcx
  const wchar_t *v51; // rcx
  const wchar_t *v52; // rcx
  __int64 v53; // rax
  const GUID *v54; // rdi
  int v55; // ebx
  const char *ProcessImageFileName; // rax
  int v57; // r8d
  IRP *v58; // rdx
  ULONG BugCheckOnFailure[2]; // [rsp+A8h] [rbp-168h]
  char v60; // [rsp+128h] [rbp-E8h]
  char v61; // [rsp+129h] [rbp-E7h]
  char v62; // [rsp+12Ah] [rbp-E6h] BYREF
  char v63; // [rsp+12Bh] [rbp-E5h]
  char v64; // [rsp+12Ch] [rbp-E4h]
  char v65; // [rsp+12Dh] [rbp-E3h]
  int v66; // [rsp+130h] [rbp-E0h]
  __int64 v67; // [rsp+138h] [rbp-D8h]
  PEPROCESS CurrentProcess; // [rsp+140h] [rbp-D0h]
  __int64 v69; // [rsp+148h] [rbp-C8h]
  __int64 v70; // [rsp+150h] [rbp-C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+158h] [rbp-B8h] BYREF
  __int64 v72; // [rsp+168h] [rbp-A8h]
  const wchar_t *v73; // [rsp+170h] [rbp-A0h]
  const wchar_t *v74; // [rsp+178h] [rbp-98h]
  const wchar_t *v75; // [rsp+180h] [rbp-90h]
  const wchar_t *v76; // [rsp+188h] [rbp-88h]
  const wchar_t *v77; // [rsp+190h] [rbp-80h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+198h] [rbp-78h] BYREF
  __int128 v79; // [rsp+1A8h] [rbp-68h] BYREF
  __int128 v80; // [rsp+1B8h] [rbp-58h]
  __int128 v81; // [rsp+1C8h] [rbp-48h] BYREF
  __int64 v82; // [rsp+1D8h] [rbp-38h]

  v2 = a2;
  v69 = a1;
  v4 = 0;
  v5 = 0;
  v66 = 0;
  v72 = 0;
  v79 = 0;
  v80 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  *(_DWORD *)(a1 + 12) |= 1u;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( MasterIrp )
    goto LABEL_11;
  MdlAddress = a2->MdlAddress;
  if ( !MdlAddress )
  {
    v9 = -1073741592;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC00000E8, 0x2B14E2u);
    NtfsExtendedCompleteRequestInternal(a1, v2, -1073741592, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v9;
    v10 = 2823395;
    goto LABEL_184;
  }
  MasterIrp = (struct _IRP *)((MdlAddress->MdlFlags & 5) != 0
                            ? MdlAddress->MappedSystemVa
                            : MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u));
  if ( MasterIrp )
  {
LABEL_11:
    if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
    {
      v9 = -1073741592;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC00000E8, 0x2B14E8u);
      NtfsExtendedCompleteRequestInternal(a1, v2, -1073741592, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v9;
      v10 = 2823401;
      goto LABEL_184;
    }
    FileObject = CurrentStackLocation->FileObject;
    FsContext = FileObject->FsContext;
    if ( FsContext )
    {
      FsContext2 = (unsigned __int16 *)FileObject->FsContext2;
      v14 = *((_QWORD *)FsContext + 24);
      v15 = *(_DWORD *)(v14 + 4);
      if ( (v15 & 1) == 0 && (!FsContext2 || *((_BYTE *)FsContext2 + 88) != 4 || (v15 & 2) == 0) )
        NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
      CurrentProcess = (PEPROCESS)*((_QWORD *)FsContext + 23);
    }
    else
    {
      v14 = 0;
      FsContext2 = 0;
      CurrentProcess = 0;
    }
    v67 = v14;
    if ( v2->RequestorMode && (!FsContext2 || !_bittest16((const signed __int16 *)FsContext2 + 52, 9u)) )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        if ( FsContext2 )
          v4 = FsContext2[52];
        v16 = FsContext2 + 8;
        if ( !FsContext2 )
          v16 = 0;
        v17 = *(_QWORD *)(v14 + 248);
        v18 = *(_WORD *)(v17 + 6);
        if ( v18 > 0x40u || (v18 & 1) != 0 )
          v18 = 0;
        BugCheckOnFailure[0] = *(unsigned __int16 *)(v14 + 7872) >> 1;
        McTemplateU0ppwwpiwd_EtwWriteTransfer(
          *((_QWORD *)FsContext + 23),
          (const EVENT_DESCRIPTOR *)usnsup_c5371,
          KeGetCurrentThread(),
          v14,
          *(_QWORD *)BugCheckOnFailure,
          *(_QWORD *)(v14 + 7880),
          v18 >> 1,
          v17 + 32,
          CurrentProcess,
          *(_QWORD *)(*((_QWORD *)FsContext + 23) + 8LL),
          *v16 >> 1,
          *((_QWORD *)v16 + 1),
          v4);
      }
      v9 = -1073741790;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC0000022, 0x2B1509u);
      NtfsExtendedCompleteRequestInternal(a1, v2, -1073741790, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v9;
      v10 = 2823434;
      goto LABEL_184;
    }
    v19 = (int)MasterIrp->MdlAddress;
    if ( !v19 )
    {
      NtfsExtendedCompleteRequestInternal(a1, v2, 0, v2 != 0, 1);
      return 0;
    }
    if ( (v19 & 0xFFFFFFFC) != 0 )
    {
      v5 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x2B1519u);
      NtfsExtendedCompleteRequestInternal(a1, v2, -1073741811, v2 != 0, 0);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0x2B151Au);
      return (unsigned int)v5;
    }
    if ( (*(_DWORD *)(v14 + 4) & 0x2000000) != 0 )
    {
      v9 = -1073741662;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC00000A2, 0x2B151Fu);
      NtfsExtendedCompleteRequestInternal(a1, v2, -1073741662, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v9;
      v10 = 2823456;
      goto LABEL_184;
    }
    v65 = 0;
    v60 = 0;
    v21 = 0;
    v70 = 0;
    v64 = 0;
    v63 = 0;
    DestinationString = *(struct _UNICODE_STRING *)&MasterIrp->Type;
    NtfsAcquireCheckpointSynchronization(a1, v14, 18);
    v61 = 1;
    NtfsAcquireExclusiveVcb(a1, v14, 1);
    v65 = 1;
    v79 = *(_OWORD *)(v14 + 1896);
    v80 = *(_OWORD *)(v14 + 1912);
    v22 = *(_DWORD *)(v14 + 4);
    if ( (v22 & 1) == 0 )
    {
      LOBYTE(v23) = 0;
      v5 = -1073741202;
      if ( !NtfsStatusDebugFlags )
      {
LABEL_57:
        v66 = v5;
        goto LABEL_126;
      }
      v24 = 2823495;
LABEL_56:
      NtfsStatusTraceAndDebugInternal(0, v5, v24);
      goto LABEL_57;
    }
    if ( ((__int64)MasterIrp->MdlAddress & 1) != 0 )
    {
      if ( (v22 & 0x100000) != 0 )
      {
        LOBYTE(v23) = 0;
        if ( !NtfsStatusDebugFlags )
        {
LABEL_63:
          v5 = -1073741129;
          goto LABEL_57;
        }
        v25 = 2823523;
LABEL_62:
        NtfsStatusTraceAndDebugInternal(0, 0xC00002B7, v25);
        goto LABEL_63;
      }
      if ( *(int *)(v14 + 24) < 0 && v2->RequestorMode )
      {
        LOBYTE(v23) = 0;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_63;
        v25 = 2823535;
        goto LABEL_62;
      }
      if ( (v22 & 0x200000) != 0 || *(_QWORD *)(v14 + 40) )
      {
        v26 = *(_QWORD *)(v14 + 40);
        if ( v26 && *(_QWORD *)&MasterIrp->Type != *(_QWORD *)(v14 + 1912) )
        {
          LOBYTE(v23) = 0;
          v5 = -1073741811;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_57;
          v24 = 2823555;
          goto LABEL_56;
        }
        NtfsSetVolumeInformationFlags(a1, v14, 0x10u, 0x10u, 1, 0);
        NtfsCheckpointCurrentTransaction(a1);
        ClearFlagInterlocked((unsigned int *)(v14 + 4), 0x80000);
        NtfsFlushVolume((_DWORD *)a1, v14, 0x20u);
        v70 = v26;
        if ( v26 )
        {
          NtfsAcquireExclusiveScbEx(a1, v26, 0);
          v72 = *(_QWORD *)(v26 + 32);
        }
        SetFlagInterlocked((unsigned int *)(v14 + 4), 0x100000u);
        *(_WORD *)(v14 + 2148) = 0;
        *(_DWORD *)(v14 + 2144) = 0;
        ExAcquireResourceExclusiveLite((PERESOURCE)(v14 + 8032), 1u);
        *(_DWORD *)(v14 + 8008) &= ~1u;
        *(_QWORD *)(v14 + 8016) = 0;
        *(_QWORD *)(v14 + 8024) = 0;
        ExReleaseResourceLite((PERESOURCE)(v14 + 8032));
        *(_WORD *)(v14 + 2150) = 0;
        *(_DWORD *)(v14 + 2152) = 0;
        *(_QWORD *)(v14 + 40) = 0;
        if ( v26 )
        {
          IoStatus = 0;
          CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v26 + 288) + 16LL), 0, 0, &IoStatus);
          NtfsPurgeCacheSection(a1, (__int64 *)v26, 0, 0, 0);
          *(_DWORD *)(v26 + 512) &= ~1u;
          *(_QWORD *)(v26 + 464) = 0;
        }
        *(_QWORD *)(v14 + 1952) = 0;
        *(_QWORD *)(v14 + 1944) = 0;
        NtfsReleaseCheckpointSynchronization(v27, v14, 18);
        v61 = 0;
        if ( v26 )
        {
          FsRtlAcquireHeaderMutex(v26 + 120, v26 + 160);
          v28 = v26 + 592;
          v29 = *(PEPROCESS *)(v26 + 592);
          while ( v29 != (PEPROCESS)v28 )
          {
            CurrentProcess = *(PEPROCESS *)v29;
            if ( NtfsClearCancelRoutine(*((_QWORD *)v29 + 6)) )
            {
              if ( (*((_DWORD *)v29 + 17) & 1) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v26 + 212));
                v30 = *(PEPROCESS *)v29;
                if ( *(PEPROCESS *)(*(_QWORD *)v29 + 8LL) != v29
                  || (v31 = (PEPROCESS *)*((_QWORD *)v29 + 1), *v31 != v29) )
                {
                  __fastfail(3u);
                }
                *v31 = v30;
                *((_QWORD *)v30 + 1) = v31;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 0xC00002B7, 0x2B1605u);
                NtfsExtendedCompleteRequestInternal(0, *((IRP **)v29 + 6), -1073741129, *((_QWORD *)v29 + 6) != 0, 0);
                if ( a1 && *(_QWORD *)(a1 + 112) == *((_QWORD *)v29 + 6) )
                  *(_QWORD *)(a1 + 112) = 0;
                *((_QWORD *)v29 + 6) = 0;
                ExFreePoolWithTag(v29, 0);
              }
              else
              {
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 0xC00002B7, 0x2B160Fu);
                *((_DWORD *)v29 + 16) = -1073741129;
                KeSetEvent((PRKEVENT)v29 + 1, 0, 0);
              }
            }
            v29 = CurrentProcess;
            v28 = v26 + 592;
          }
          FsRtlReleaseHeaderMutex(v26 + 120, v26 + 160);
          ExAcquireFastMutex((PFAST_MUTEX)(v14 + 1992));
          v32 = (_QWORD **)(v14 + 1976);
          for ( i = *(_QWORD **)(v14 + 1976); i != v32; i = *v32 )
          {
            v34 = *i;
            if ( *(_QWORD **)(*i + 8LL) != i || (v35 = (_QWORD *)i[1], (_QWORD *)*v35 != i) )
              __fastfail(3u);
            *v35 = v34;
            *(_QWORD *)(v34 + 8) = v35;
            *i = 0;
            v36 = i - 2;
            v37 = *v36;
            if ( *v36 )
            {
              if ( *(__int64 **)(v37 + 8) != v36 || (v38 = (__int64 **)v36[1], *v38 != v36) )
                __fastfail(3u);
              *v38 = (__int64 *)v37;
              *(_QWORD *)(v37 + 8) = v38;
            }
          }
          ExReleaseFastMutex((PFAST_MUTEX)(v14 + 1992));
          NtOfsCloseAttributeSafe(a1, v26);
          v21 = 0;
          v70 = 0;
        }
        else
        {
          v21 = v70;
        }
        v64 = 1;
        if ( ((__int64)MasterIrp->MdlAddress & 2) != 0 )
        {
          KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v14 + 576));
          LOBYTE(v4) = 1;
          v60 = 1;
        }
        else
        {
          LOBYTE(v4) = 0;
        }
        NtfsPostSpecial(a1, v14, (__int64 (__fastcall *)(__int64))NtfsDeleteUsnSpecial, (_QWORD *)(v14 + 2144), 13);
      }
    }
    if ( (*(_DWORD *)(v14 + 4) & 0x100000) != 0 && ((__int64)MasterIrp->MdlAddress & 2) != 0 )
    {
      LOBYTE(v23) = 0;
      if ( !(_BYTE)v4 )
        KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v14 + 576));
      v5 = 259;
      v66 = 259;
      if ( NtfsSetCancelRoutine((__int64)v2, (__int64)NtfsCancelDeleteUsnJournal, 0, 1) )
      {
        v39 = *(struct _LIST_ENTRY **)(v14 + 1968);
        if ( v39->Flink != (struct _LIST_ENTRY *)(v14 + 1960) )
          __fastfail(3u);
        v2->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)(v14 + 1960);
        v2->Tail.Overlay.ListEntry.Blink = v39;
        v39->Flink = &v2->Tail.Overlay.ListEntry;
        *(_QWORD *)(v14 + 1968) = &v2->Tail.Overlay.ListEntry;
        v63 = 1;
      }
      else
      {
        v5 = -1073741536;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC0000120, 0x2B166Fu);
        v66 = -1073741536;
      }
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v14 + 576));
      v40 = 0;
      goto LABEL_127;
    }
    LOBYTE(v23) = 0;
LABEL_126:
    v40 = v60;
LABEL_127:
    if ( NtfsTelemetryGuard(0x800u) )
      NtfsTelemetryUsnDelete(a1, v14, (unsigned int)&DestinationString, (unsigned int)&v79, v64, v63, v5);
    if ( v40 )
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v14 + 576));
    if ( v21 )
      NtfsReleaseFcbEx(a1, *(_QWORD *)(v21 + 184), 0);
    NtfsReleaseVcb(a1, v14);
    if ( v61 )
      NtfsReleaseCheckpointSynchronization(v41, v14, 18);
    if ( v5 >= 0 )
    {
      v81 = 0;
      v82 = 0;
      v62 = 0;
      DestinationString = 0;
      CurrentProcess = IoGetCurrentProcess();
      if ( v5 == 259 || !v2 )
      {
        ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v42);
        if ( ActivityIdThread )
        {
          *((_QWORD *)&v81 + 1) = *ActivityIdThread;
          v82 = ActivityIdThread[1];
          *(_QWORD *)&v81 = (char *)&v81 + 8;
        }
        else
        {
          *(_QWORD *)&v81 = 0;
        }
      }
      else
      {
        ActivityIdIrp = IoGetActivityIdIrp(v2, (char *)&v81 + 8);
        v44 = (char *)&v81 + 8;
        if ( ActivityIdIrp < 0 )
          v44 = 0;
        *(_QWORD *)&v81 = v44;
      }
      if ( !ExIsResourceAcquiredSharedLite((PERESOURCE)(v14 + 2160))
        || ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v14 + 2160)) )
      {
        NtfsFillVcbVolumeGuid(a1);
      }
      NtfsRepairGetVolumeId(a1, v14, 0, (__int64)&DestinationString, &v62);
      if ( !DestinationString.Length )
        RtlInitUnicodeString(&DestinationString, L"??");
      if ( (Microsoft_Windows_NtfsEnableBits & 0x800) != 0 )
      {
        v46 = (WCHAR *)&word_140064400;
        v47 = &word_140064400;
        if ( *(_QWORD *)(v14 + 6736) )
          v47 = *(const wchar_t **)(v14 + 6736);
        v73 = v47;
        LODWORD(v69) = (*(_DWORD *)(v14 + 28) >> 2) & 1;
        v48 = *(_DWORD *)(v14 + 6660);
        if ( (unsigned int)(v48 - 1) > 0x13 )
          v48 = 0;
        LODWORD(v67) = v48;
        v49 = &word_140064400;
        if ( *(_QWORD *)(v14 + 6720) )
          v49 = *(const wchar_t **)(v14 + 6720);
        v74 = v49;
        v50 = &word_140064400;
        if ( *(_QWORD *)(v14 + 6704) )
          v50 = *(const wchar_t **)(v14 + 6704);
        v75 = v50;
        v51 = &word_140064400;
        if ( *(_QWORD *)(v14 + 6688) )
          v51 = *(const wchar_t **)(v14 + 6688);
        v76 = v51;
        v52 = &word_140064400;
        if ( *(_QWORD *)(v14 + 6672) )
          v52 = *(const wchar_t **)(v14 + 6672);
        v77 = v52;
        if ( *(_QWORD *)(v14 + 7864) )
          v46 = *(WCHAR **)(v14 + 7864);
        IoStatus.Pointer = v46;
        if ( (*(_DWORD *)(v14 + 4) & 0xC00) != 0x800 )
        {
          v53 = *(_QWORD *)(v14 + 248);
          if ( v53 )
          {
            v23 = *(_QWORD *)(v53 + 16);
            if ( v23 )
              LODWORD(v23) = (*(_DWORD *)(v23 + 48) >> 8) & 1;
          }
        }
        v54 = (const GUID *)v81;
        v55 = *(_DWORD *)(v14 + 6792);
        ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess);
        McTemplateK0jmztzzzzzqjqtzsii_EtwWriteTransfer(
          (__int64)ProcessImageFileName,
          v14 + 7808,
          v54,
          v14 + 7824,
          v14 + 8528,
          DestinationString.Buffer,
          v23,
          (const wchar_t *)IoStatus.Pointer,
          v77,
          v76,
          v75,
          v74,
          v67,
          v14 + 7808,
          v55,
          v69,
          v73,
          ProcessImageFileName,
          v80,
          v72);
      }
      if ( v62 )
        RtlFreeUnicodeString(&DestinationString);
    }
    if ( NtfsStatusDebugFlags && v5 && (unsigned int)(v5 - 298) > 1 && (unsigned int)(v5 + 2147483643) > 1 && v5 != 259 )
      NtfsStatusTraceAndDebugInternal(a1, v5, 0x2B16EEu);
    v57 = 0;
    v58 = v2;
    if ( v5 == 259 )
    {
      v58 = 0;
      v2 = 0;
    }
    LOBYTE(v57) = v5 >= 0;
    NtfsExtendedCompleteRequestInternal(a1, v2, v5, v58 != 0, v57);
    return (unsigned int)v5;
  }
  v9 = -1073741670;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 0xC000009A, 0x2B14DCu);
  NtfsExtendedCompleteRequestInternal(a1, v2, -1073741670, v2 != 0, 0);
  if ( !NtfsStatusDebugFlags )
    return v9;
  v10 = 2823389;
LABEL_184:
  NtfsStatusTraceAndDebugInternal(0, v9, v10);
  return v9;
}

```

## disassembly

```asm
0x14026fef8  mov     r11, rsp
0x14026fefb  mov     [r11+18h], rbx
0x14026feff  mov     [r11+20h], rsi
0x14026ff03  push    rdi
0x14026ff04  push    r12
0x14026ff06  push    r13
0x14026ff08  push    r14
0x14026ff0a  push    r15
0x14026ff0c  sub     rsp, 160h
0x14026ff13  mov     rax, cs:__security_cookie
0x14026ff1a  xor     rax, rsp
0x14026ff1d  mov     [rsp+188h+var_30], rax
0x14026ff25  mov     r13, rdx
0x14026ff28  mov     r15, rcx
0x14026ff2b  mov     [rsp+188h+var_C8], rcx
0x14026ff33  xor     edi, edi
0x14026ff35  mov     esi, edi
0x14026ff37  mov     [rsp+188h+var_E0], edi
0x14026ff3e  mov     [r11-0A8h], rdi
0x14026ff45  xorps   xmm0, xmm0
0x14026ff48  movups  xmmword ptr [r11-68h], xmm0
0x14026ff4d  movups  xmmword ptr [r11-58h], xmm0
0x14026ff52  mov     rbx, [rdx+0B8h]
0x14026ff59  or      dword ptr [rcx+0Ch], 1
0x14026ff5d  mov     r12, [rdx+18h]
0x14026ff61  test    r12, r12
0x14026ff64  jnz     loc_14026FFFD
0x14026ff6a  mov     rcx, [rdx+8]; MemoryDescriptorList
0x14026ff6e  test    rcx, rcx
0x14026ff71  jz      loc_140270D6B
0x14026ff77  test    byte ptr [rcx+0Ah], 5
0x14026ff7b  jz      short loc_14026FF83
0x14026ff7d  mov     r12, [rcx+18h]
0x14026ff81  jmp     short loc_14026FFA7
0x14026ff83  mov     [rsp+188h+Priority], 40000010h; Priority
0x14026ff8b  mov     [rsp+188h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14026ff8f  xor     r9d, r9d; RequestedAddress
0x14026ff92  xor     edx, edx; AccessMode
0x14026ff94  lea     r8d, [r9+1]; CacheType
0x14026ff98  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14026ff9f  nop     dword ptr [rax+rax+00h]
0x14026ffa4  mov     r12, rax
0x14026ffa7  test    r12, r12
0x14026ffaa  jnz     short loc_14026FFFD
0x14026ffac  mov     al, cs:NtfsStatusDebugFlags
0x14026ffb2  mov     ebx, 0C000009Ah
0x14026ffb7  test    al, al
0x14026ffb9  jz      short loc_14026FFCB
0x14026ffbb  mov     r8d, 2B14DCh
0x14026ffc1  mov     edx, ebx
0x14026ffc3  mov     rcx, r15
0x14026ffc6  call    NtfsStatusTraceAndDebugInternal
0x14026ffcb  test    r13, r13
0x14026ffce  setnz   r9b
0x14026ffd2  mov     [rsp+188h+BugCheckOnFailure], edi
0x14026ffd6  mov     r8d, ebx
0x14026ffd9  mov     rdx, r13
0x14026ffdc  mov     rcx, r15
0x14026ffdf  call    NtfsExtendedCompleteRequestInternal
0x14026ffe4  mov     al, cs:NtfsStatusDebugFlags
0x14026ffea  test    al, al
0x14026ffec  jz      loc_140270DBC
0x14026fff2  mov     r8d, 2B14DDh
0x14026fff8  jmp     loc_140270DB3
0x14026fffd  cmp     dword ptr [rbx+10h], 10h
0x140270001  jnb     short loc_140270054
0x140270003  mov     al, cs:NtfsStatusDebugFlags
0x140270009  mov     ebx, 0C00000E8h
0x14027000e  test    al, al
0x140270010  jz      short loc_140270022
0x140270012  mov     r8d, 2B14E8h
0x140270018  mov     edx, ebx
0x14027001a  mov     rcx, r15
0x14027001d  call    NtfsStatusTraceAndDebugInternal
0x140270022  test    r13, r13
0x140270025  setnz   r9b
0x140270029  mov     [rsp+188h+BugCheckOnFailure], edi
0x14027002d  mov     r8d, ebx
0x140270030  mov     rdx, r13
0x140270033  mov     rcx, r15
0x140270036  call    NtfsExtendedCompleteRequestInternal
0x14027003b  mov     al, cs:NtfsStatusDebugFlags
0x140270041  test    al, al
0x140270043  jz      loc_140270DBC
0x140270049  mov     r8d, 2B14E9h
0x14027004f  jmp     loc_140270DB3
0x140270054  mov     rcx, [rbx+30h]
0x140270058  mov     r8, [rcx+18h]
0x14027005c  test    r8, r8
0x14027005f  jz      short loc_1402700A0
0x140270061  mov     rcx, [rcx+20h]
0x140270065  mov     r14, [r8+0C0h]
0x14027006c  mov     eax, [r14+4]
0x140270070  test    al, 1
0x140270072  jnz     short loc_14027008F
0x140270074  test    rcx, rcx
0x140270077  jz      loc_140270DEC
0x14027007d  cmp     byte ptr [rcx+58h], 4
0x140270081  jnz     loc_140270DEC
0x140270087  test    al, 2
0x140270089  jz      loc_140270DEC
0x14027008f  mov     rax, [r8+0B8h]
0x140270096  mov     [rsp+188h+var_D0], rax
0x14027009e  jmp     short loc_1402700AE
0x1402700a0  mov     r14, rdi
0x1402700a3  mov     rcx, rdi
0x1402700a6  mov     [rsp+188h+var_D0], rdi
0x1402700ae  mov     [rsp+188h+var_D8], r14
0x1402700b6  cmp     [r13+40h], dil
0x1402700ba  jz      loc_1402701EC
0x1402700c0  test    rcx, rcx
0x1402700c3  jz      short loc_1402700D1
0x1402700c5  bt      word ptr [rcx+68h], 9
0x1402700cb  jb      loc_1402701EC
0x1402700d1  mov     eax, [r15+10h]
0x1402700d5  bt      rax, 14h
0x1402700da  jb      loc_14027019B
0x1402700e0  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1402700e7  test    al, 20h
0x1402700e9  jz      loc_14027019B
0x1402700ef  test    rcx, rcx
0x1402700f2  jz      short loc_1402700F8
0x1402700f4  movzx   edi, word ptr [rcx+68h]
0x1402700f8  xor     edx, edx
0x1402700fa  test    rcx, rcx
0x1402700fd  lea     r9, [rcx+10h]
0x140270101  jnz     short loc_140270106
0x140270103  mov     r9d, edx
0x140270106  mov     r10, [r14+0F8h]
0x14027010d  movzx   eax, word ptr [r10+6]
0x140270112  cmp     ax, 40h ; '@'
0x140270116  ja      short loc_14027011C
0x140270118  test    al, 1
0x14027011a  jz      short loc_14027011E
0x14027011c  mov     eax, edx
0x14027011e  movzx   edx, word ptr [r9]
0x140270122  shr     edx, 1
0x140270124  mov     rcx, [r8+0B8h]
0x14027012b  add     r10, 20h ; ' '
0x14027012f  movzx   r11d, ax
0x140270133  shr     r11d, 1
0x140270136  movzx   ebx, word ptr [r14+1EC0h]
0x14027013e  shr     ebx, 1
0x140270140  mov     r8, gs:188h
0x140270149  mov     [rsp+188h+var_128], edi
0x14027014d  mov     rax, [r9+8]
0x140270151  mov     [rsp+188h+var_130], rax
0x140270156  mov     dword ptr [rsp+188h+var_138], edx
0x14027015a  mov     rax, [rcx+8]
0x14027015e  mov     [rsp+188h+var_140], rax
0x140270163  mov     rax, [rsp+188h+var_D0]
0x14027016b  mov     [rsp+188h+var_148], rax
0x140270170  mov     [rsp+188h+var_150], r10
0x140270175  mov     [rsp+188h+var_158], r11d
0x14027017a  mov     rax, [r14+1EC8h]
0x140270181  mov     qword ptr [rsp+188h+Priority], rax
0x140270186  mov     [rsp+188h+BugCheckOnFailure], ebx
0x14027018a  mov     r9, r14
0x14027018d  lea     rdx, usnsup_c5371
0x140270194  call    McTemplateU0ppwwpiwd_EtwWriteTransfer
0x140270199  xor     edi, edi
0x14027019b  mov     al, cs:NtfsStatusDebugFlags
0x1402701a1  mov     ebx, 0C0000022h
0x1402701a6  test    al, al
0x1402701a8  jz      short loc_1402701BA
0x1402701aa  mov     r8d, 2B1509h
0x1402701b0  mov     edx, ebx
0x1402701b2  mov     rcx, r15
0x1402701b5  call    NtfsStatusTraceAndDebugInternal
0x1402701ba  test    r13, r13
0x1402701bd  setnz   r9b
0x1402701c1  mov     [rsp+188h+BugCheckOnFailure], edi
0x1402701c5  mov     r8d, ebx
0x1402701c8  mov     rdx, r13
0x1402701cb  mov     rcx, r15
0x1402701ce  call    NtfsExtendedCompleteRequestInternal
0x1402701d3  mov     al, cs:NtfsStatusDebugFlags
0x1402701d9  test    al, al
0x1402701db  jz      loc_140270DBC
0x1402701e1  mov     r8d, 2B150Ah
0x1402701e7  jmp     loc_140270DB3
0x1402701ec  mov     eax, [r12+8]
0x1402701f1  test    eax, eax
0x1402701f3  jnz     short loc_14027021F
0x1402701f5  mov     al, cs:NtfsStatusDebugFlags
0x1402701fb  test    r13, r13
0x1402701fe  setnz   r9b
0x140270202  mov     [rsp+188h+BugCheckOnFailure], 1
0x14027020a  xor     r8d, r8d
0x14027020d  mov     rdx, r13
0x140270210  mov     rcx, r15
0x140270213  call    NtfsExtendedCompleteRequestInternal
0x140270218  xor     eax, eax
0x14027021a  jmp     loc_140270DBE
0x14027021f  test    eax, 0FFFFFFFCh
0x140270224  jz      short loc_14027027E
0x140270226  mov     al, cs:NtfsStatusDebugFlags
0x14027022c  mov     esi, 0C000000Dh
0x140270231  test    al, al
0x140270233  jz      short loc_140270245
0x140270235  mov     r8d, 2B1519h
0x14027023b  mov     edx, esi
0x14027023d  mov     rcx, r15
0x140270240  call    NtfsStatusTraceAndDebugInternal
0x140270245  test    r13, r13
0x140270248  setnz   r9b
0x14027024c  mov     [rsp+188h+BugCheckOnFailure], edi
0x140270250  mov     r8d, esi
0x140270253  mov     rdx, r13
0x140270256  mov     rcx, r15
0x140270259  call    NtfsExtendedCompleteRequestInternal
0x14027025e  mov     al, cs:NtfsStatusDebugFlags
0x140270264  test    al, al
0x140270266  jz      short loc_140270277
0x140270268  mov     r8d, 2B151Ah
0x14027026e  mov     edx, esi
0x140270270  xor     ecx, ecx
0x140270272  call    NtfsStatusTraceAndDebugInternal
0x140270277  mov     eax, esi
0x140270279  jmp     loc_140270DBE
0x14027027e  test    dword ptr [r14+4], 2000000h
0x140270286  jz      short loc_1402702D9
0x140270288  mov     al, cs:NtfsStatusDebugFlags
0x14027028e  mov     ebx, 0C00000A2h
0x140270293  test    al, al
0x140270295  jz      short loc_1402702A7
0x140270297  mov     r8d, 2B151Fh
0x14027029d  mov     edx, ebx
0x14027029f  mov     rcx, r15
0x1402702a2  call    NtfsStatusTraceAndDebugInternal
0x1402702a7  test    r13, r13
0x1402702aa  setnz   r9b
0x1402702ae  mov     [rsp+188h+BugCheckOnFailure], edi
0x1402702b2  mov     r8d, ebx
0x1402702b5  mov     rdx, r13
0x1402702b8  mov     rcx, r15
0x1402702bb  call    NtfsExtendedCompleteRequestInternal
0x1402702c0  mov     al, cs:NtfsStatusDebugFlags
0x1402702c6  test    al, al
0x1402702c8  jz      loc_140270DBC
0x1402702ce  mov     r8d, 2B1520h
0x1402702d4  jmp     loc_140270DB3
0x1402702d9  mov     [rsp+188h+var_E3], dil
0x1402702e1  mov     [rsp+188h+var_E7], dil
0x1402702e9  mov     [rsp+188h+var_E8], dil
0x1402702f1  xor     eax, eax
0x1402702f3  mov     ebx, eax
0x1402702f5  mov     [rsp+188h+var_C0], rax
0x1402702fd  mov     [rsp+188h+var_E4], al
0x140270304  mov     [rsp+188h+var_E5], al
0x14027030b  movups  xmm0, xmmword ptr [r12]
0x140270310  movdqu  xmmword ptr [rsp+188h+DestinationString.Length], xmm0
0x140270319  lea     r8d, [rax+12h]
0x14027031d  mov     rdx, r14
0x140270320  mov     rcx, r15
0x140270323  call    NtfsAcquireCheckpointSynchronization
0x140270328  mov     [rsp+188h+var_E7], 1
0x140270330  mov     r8b, 1
0x140270333  mov     rdx, r14
0x140270336  mov     rcx, r15
0x140270339  call    NtfsAcquireExclusiveVcb
0x14027033e  mov     [rsp+188h+var_E3], 1
0x140270346  movups  xmm0, xmmword ptr [r14+768h]
0x14027034e  movups  [rsp+188h+var_68], xmm0
0x140270356  movups  xmm1, xmmword ptr [r14+778h]
0x14027035e  movups  [rsp+188h+var_58], xmm1
0x140270366  mov     ecx, [r14+4]
0x14027036a  test    cl, 1
0x14027036d  jnz     short loc_14027039C
0x14027036f  mov     al, cs:NtfsStatusDebugFlags
0x140270375  xor     r12d, r12d
0x140270378  mov     esi, 0C000026Eh
0x14027037d  test    al, al
0x14027037f  jz      short loc_140270390
0x140270381  mov     r8d, 2B1547h
0x140270387  mov     edx, esi
0x140270389  xor     ecx, ecx
0x14027038b  call    NtfsStatusTraceAndDebugInternal
0x140270390  mov     [rsp+188h+var_E0], esi
0x140270397  jmp     loc_1402708DC
0x14027039c  mov     eax, [r12+8]
0x1402703a1  test    al, 1
0x1402703a3  jz      loc_1402707F2
0x1402703a9  bt      ecx, 14h
0x1402703ad  jnb     short loc_1402703D5
0x1402703af  mov     al, cs:NtfsStatusDebugFlags
0x1402703b5  xor     r12d, r12d
0x1402703b8  test    al, al
0x1402703ba  jz      short loc_1402703CE
0x1402703bc  mov     r8d, 2B1563h
0x1402703c2  xor     ecx, ecx
0x1402703c4  mov     edx, 0C00002B7h
0x1402703c9  call    NtfsStatusTraceAndDebugInternal
0x1402703ce  mov     esi, 0C00002B7h
0x1402703d3  jmp     short loc_140270390
0x1402703d5  xor     edx, edx
0x1402703d7  cmp     [r14+18h], edx
0x1402703db  jge     short loc_1402703F8
0x1402703dd  cmp     [r13+40h], dl
0x1402703e1  jz      short loc_1402703F8
  ... truncated ...
```
