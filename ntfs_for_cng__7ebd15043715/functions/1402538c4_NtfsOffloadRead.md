# NtfsOffloadRead

- ea: `0x1402538c4`
- end: `0x140254e66`
- name: `NtfsOffloadRead`
- size: `5538`
- prototype: `__int64 __fastcall(_BYTE *, PIRP Irp)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401f5890`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x140014e74`
- `0x140021220`
- `0x140021590`
- `0x140028470`
- `0x140049d40`
- `0x14004a110`
- `0x14004a1bc`
- `0x1400596c0`
- `0x1400d3a78`
- `0x140159768`
- `0x140160be0`
- `0x1401be398`
- `0x1401be91c`
- `0x1401c00e0`
- `0x14022b9dc`
- `0x1402332a8`
- `0x14024f868`
- `0x1402538c4`
- `0x1402949c4`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x140253c50`
- `ntoskrnl!FsRtlCheckOplock` at `0x140253c50`
- `ntoskrnl!IoGetRequestorProcess` at `0x14025444f`
- `ntoskrnl!IoGetRequestorProcess` at `0x14025444f`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x14025447b`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x14025447b`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1402543cd`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1402543cd`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140253d1e`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140254180`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1402544a2`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1402544c9`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140253d1e`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140254180`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1402544a2`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1402544c9`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140253ca7`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140253ca7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b8f74`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b8f91`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402d09f5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402d0a13`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b8f74`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b8f91`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402d09f5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402d0a13`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140253d7d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140253d7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140254387`
- `ntoskrnl!ExReleaseResourceLite` at `0x140254387`

## pseudocode

```c
__int64 __fastcall NtfsOffloadRead(_BYTE *a1, PIRP Irp)
{
  PIRP v2; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r11
  __int64 v5; // r8
  __int64 v6; // r11
  __int64 v7; // r15
  __int64 v8; // rax
  __int64 v9; // r13
  int v10; // r10d
  int v11; // r9d
  unsigned int v12; // ebx
  unsigned int v13; // r8d
  struct _IRP *MasterIrp; // r14
  unsigned __int64 v16; // r9
  __int64 *p_Flags; // rbx
  struct _IRP *v18; // rcx
  BOOLEAN v19; // cl
  BOOLEAN v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  int v27; // edx
  int v28; // edx
  __int64 v29; // rbx
  unsigned __int64 v30; // r8
  struct _IRP *v31; // rdx
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *p_AssociatedIrp; // r9
  struct _IRP *v33; // rax
  struct _IRP *v34; // r13
  _DWORD *v35; // r13
  int v36; // ebx
  __int64 v37; // rax
  char v38; // al
  char v39; // r11
  __int64 v40; // r10
  __int64 v41; // r9
  struct _IRP *v42; // r8
  ULONG_PTR Information; // rcx
  struct _IRP *v44; // rax
  PVOID v45; // r14
  unsigned int v46; // r8d
  unsigned int v47; // r8d
  struct _ERESOURCE *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rdx
  char v51; // al
  FILE_LOCK *v52; // rbx
  PEPROCESS ProcessId; // rax
  __int64 v54; // r9
  __int64 v55; // r8
  struct _MDL *v56; // r8
  unsigned __int64 v57; // rbx
  struct _IRP *v58; // rdx
  unsigned __int64 v59; // rdx
  int v60; // ebx
  PMDL MdlAddress; // rax
  unsigned int v62; // ecx
  __int64 v63; // r9
  ULONG *v64; // rax
  __int64 v65; // r9
  int v66; // eax
  char v67; // al
  __int64 v68; // rax
  SIZE_T NumberOfBytes; // [rsp+38h] [rbp-100h]
  char v70; // [rsp+64h] [rbp-D4h]
  struct _IRP *Entry; // [rsp+68h] [rbp-D0h]
  PVOID v72; // [rsp+70h] [rbp-C8h] BYREF
  int v73; // [rsp+78h] [rbp-C0h]
  int v74[2]; // [rsp+80h] [rbp-B8h]
  struct _IRP *v75; // [rsp+88h] [rbp-B0h]
  __int64 v76; // [rsp+90h] [rbp-A8h]
  __int64 v77; // [rsp+98h] [rbp-A0h] BYREF
  __int64 v78; // [rsp+A0h] [rbp-98h]
  int v79; // [rsp+A8h] [rbp-90h]
  unsigned int v80; // [rsp+ACh] [rbp-8Ch]
  __int64 v81; // [rsp+B0h] [rbp-88h] BYREF
  _QWORD *v82; // [rsp+B8h] [rbp-80h]
  unsigned __int64 v83; // [rsp+C0h] [rbp-78h]
  ULONG_PTR v84; // [rsp+C8h] [rbp-70h]
  PFILE_OBJECT FileObject; // [rsp+D0h] [rbp-68h]
  __int64 v86; // [rsp+D8h] [rbp-60h]
  __int64 i; // [rsp+E0h] [rbp-58h]
  ULONG *v88; // [rsp+E8h] [rbp-50h]
  __int64 v89; // [rsp+F0h] [rbp-48h]
  char v90; // [rsp+150h] [rbp+18h] BYREF
  BOOLEAN v91; // [rsp+158h] [rbp+20h]

  v2 = Irp;
  v81 = 0;
  v77 = 0;
  v90 = 0;
  v72 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Irp->IoStatus.Information = 0;
  FileObject = CurrentStackLocation->FileObject;
  if ( !NtfsDecodeFileObjectForRead((__int64)FileObject) )
  {
    v12 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000000D, 0x12801Eu);
    NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1212447;
    goto LABEL_212;
  }
  v7 = *(_QWORD *)(v5 + 24);
  if ( v7 )
  {
    v8 = *(_QWORD *)(v5 + 32);
    v78 = v8;
    v9 = *(_QWORD *)(v7 + 192);
    *(_QWORD *)v74 = v9;
    v82 = *(_QWORD **)(v7 + 184);
    if ( v8 )
      v10 = *(unsigned __int8 *)(v8 + 88);
    else
      v10 = 5;
  }
  else
  {
    v9 = 0;
    *(_QWORD *)v74 = 0;
    v78 = 0;
    v82 = 0;
    v10 = 1;
  }
  v11 = *(_DWORD *)(v9 + 7760);
  if ( v11 != 3 && MEMORY[0xFFFFF78000000320] - *(_QWORD *)(v9 + 7768) >= 0x218711A00uLL / (unsigned int)dword_1400953B0 )
  {
    LOBYTE(v11) = 3;
    _InterlockedExchange((volatile __int32 *)(v9 + 7760), 3);
  }
  if ( (v11 & 1) != 0 )
  {
    if ( v10 != 2 )
    {
      v12 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000000D, 0x128038u);
      NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741811, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1212473;
      goto LABEL_212;
    }
    v89 = v7;
    if ( (*(_DWORD *)(v7 + 512) & 0x1000000) != 0 )
    {
      v12 = -1073741816;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000008, 0x128042u);
      NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741816, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1212483;
      goto LABEL_212;
    }
    if ( (*(_DWORD *)(v9 + 4) & 1) == 0 )
    {
      v12 = -1073741202;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000026E, 0x128050u);
      NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741202, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1212497;
LABEL_212:
      NtfsStatusTraceAndDebugInternal(0, v12, v13);
      return v12;
    }
    if ( *(_DWORD *)(v6 + 16) < 0x20u )
    {
      v12 = -1073741789;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000023, 0x128063u);
      NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741789, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1212516;
      goto LABEL_212;
    }
    if ( *(_DWORD *)(v6 + 8) < 0x210u )
    {
      v12 = -1073741789;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000023, 0x128069u);
      NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741789, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1212522;
      goto LABEL_212;
    }
    MasterIrp = v2->AssociatedIrp.MasterIrp;
    v16 = *(unsigned int *)(v9 + 364);
    p_Flags = (__int64 *)&MasterIrp->Flags;
    v88 = &MasterIrp->Flags;
    if ( *(_QWORD *)&MasterIrp->Flags % v16 )
    {
      v12 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000000D, 0x128076u);
      NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741811, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1212535;
      goto LABEL_212;
    }
    v18 = MasterIrp->AssociatedIrp.MasterIrp;
    if ( (unsigned __int64)v18 % v16 )
    {
      v12 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000000D, 0x12807Cu);
      NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741811, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1212541;
      goto LABEL_212;
    }
    if ( *(_DWORD *)&MasterIrp->Type != 32 )
    {
      v12 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000000D, 0x128082u);
      NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741811, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1212547;
      goto LABEL_212;
    }
    if ( (unsigned __int64)v18 + *(_QWORD *)&MasterIrp->Flags < *(_QWORD *)&MasterIrp->Flags )
    {
      v12 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000000D, 0x12808Eu);
      NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741811, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1212559;
      goto LABEL_212;
    }
    if ( v18 )
    {
      if ( *(_QWORD *)(v7 + 528) )
      {
        v12 = -1073700189;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000A2A3, 0x1280ADu);
        NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073700189, v2 != 0, 0);
        if ( !NtfsStatusDebugFlags )
          return v12;
        v13 = 1212590;
        goto LABEL_212;
      }
      if ( *(_DWORD *)(v7 + 256) != 128 )
      {
        v12 = -1073700189;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000A2A3, 0x1280B7u);
        NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073700189, v2 != 0, 0);
        if ( !NtfsStatusDebugFlags )
          return v12;
        v13 = 1212600;
        goto LABEL_212;
      }
      v73 = 0;
      Entry = 0;
      v75 = 0;
      v83 = 0;
      v70 = 1;
      v19 = a1[12] & 1;
      v91 = v19;
      if ( *(_DWORD *)(*(_QWORD *)(v7 + 184) + 8LL) < 0x10u )
      {
        v12 = -1073700189;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000A2A3, 0x1280C1u);
        NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073700189, v2 != 0, 0);
        if ( !NtfsStatusDebugFlags )
          return v12;
        v13 = 1212610;
        goto LABEL_212;
      }
      v20 = v19;
      v21 = v7;
      v22 = (__int64)a1;
      if ( *(_QWORD *)(*(_QWORD *)(v7 + 288) + 16LL) )
        goto LABEL_30;
      LOBYTE(v24) = NtfsAcquirePagingShared((__int64)a1, v7, v20, 0);
      v90 = v24;
      if ( (_BYTE)v24 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v7 + 288) + 16LL) )
        {
          NtfsReleasePagingResourcePriv(v24, v7);
          v20 = v91;
          v21 = v7;
          v22 = (__int64)a1;
LABEL_30:
          LOBYTE(v24) = NtfsAcquirePagingResourceExclusive(v22, v21, v20);
          v90 = v24;
        }
      }
      else
      {
        LOBYTE(v24) = 0;
      }
      if ( !(_BYTE)v24 )
        NtfsRaiseStatusInternal((__int64)a1, -1073741608, 0, 0, 1212652);
      v25 = *(unsigned __int16 *)(v7 + 460);
      if ( (_BYTE)v25 )
      {
        v12 = -1073700189;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_69;
        v47 = 1212663;
      }
      else if ( (v25 & 0x4000) != 0 )
      {
        v12 = -1073700189;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_69;
        v47 = 1212669;
      }
      else if ( (v25 & 0x8000u) != 0LL )
      {
        v12 = -1073700189;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_69;
        v47 = 1212675;
      }
      else
      {
        v26 = *(_DWORD *)(v7 + 512);
        if ( (v26 & 0x10000) != 0 )
        {
          v12 = -1073741202;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_69;
          v47 = 1212685;
        }
        else if ( (v26 & 0x4000000) != 0 )
        {
          v12 = -1073741431;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_69;
          v47 = 1212691;
        }
        else
        {
          if ( *(_QWORD *)(*(_QWORD *)(v7 + 288) + 16LL) )
          {
            if ( !*(_DWORD *)(v7 + 544) )
            {
              v12 = NtfsCacheCoherencyFlush(
                      (__int64)a1,
                      v23,
                      v7,
                      *p_Flags,
                      (unsigned __int64)MasterIrp->AssociatedIrp.MasterIrp,
                      0,
                      *(_DWORD *)(v7 + 220) == 0);
              if ( (v12 & 0x80000000) != 0 )
                goto LABEL_69;
            }
          }
          if ( (*(_DWORD *)(v78 + 4) & 0x8000) != 0 )
          {
            v12 = -1073741528;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_69;
            v47 = 1212729;
          }
          else
          {
            v27 = *(_DWORD *)(v7 + 512);
            if ( (v27 & 0x1000000) == 0 )
            {
              v28 = v27 & 0x10000;
              v25 = v28 != 0 ? 0xC000026E : 0;
              v12 = v28 != 0 ? 0xC000026E : 0;
              if ( NtfsStatusDebugFlags && v28 )
                NtfsStatusTraceAndDebugInternal(0, v25, 0x128149u);
              if ( (*(_DWORD *)(v7 + 512) & 0x40) != 0 )
              {
                v12 = -1073741533;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 0xC0000123, 0x12814Du);
              }
              if ( (v12 & 0x80000000) != 0 )
                goto LABEL_69;
              if ( (*(_DWORD *)(v7 + 200) & 0x20) == 0 )
              {
                NtfsAcquireResourceShared(v25, v7, 1u);
                NtfsUpdateScbFromAttribute((__int64)a1, v7, 0);
                if ( *(_WORD *)v7 == 1794 )
                  v48 = (struct _ERESOURCE *)(*(_QWORD *)(v7 + 104) + 64LL);
                else
                  v48 = *(struct _ERESOURCE **)(v7 + 8);
                ExReleaseResourceLite(v48);
              }
              v12 = FsRtlCheckOplock(
                      (POPLOCK)(v7 + 88),
                      v2,
                      a1,
                      NtfsOplockComplete,
                      (POPLOCK_FS_PREPOST_IRP)NtfsPrePostIrp);
              if ( v12 )
              {
                v2 = 0;
                a1 = 0;
                if ( NtfsStatusDebugFlags
                  && (((v12 - 294) & 0xFFFFFFFA) != 0 || v12 == 295)
                  && v12 < 0xFFFFFFED
                  && v12 != -1073741608
                  && v12 != -1073741802
                  && v12 != -1073741807
                  && v12 + 2147483643 > 1
                  && v12 != 259 )
                {
                  NtfsStatusTraceAndDebugInternal(0, v12, 0x128172u);
                }
                goto LABEL_69;
              }
              if ( !*(_BYTE *)(v7 + 5) )
              {
                if ( (*(_DWORD *)(*(_QWORD *)(v7 + 192) + 4LL) & 0x4000005) == 1
                  && *(_WORD *)v7 == 1797
                  && FsRtlOplockIsFastIoPossible((POPLOCK)(v7 + 88)) )
                {
                  if ( *(_DWORD *)(v7 + 452)
                    || (v49 = *(_QWORD *)(v7 + 584)) != 0 && *(_BYTE *)(v49 + 16)
                    || (v50 = *(_QWORD *)(v7 + 192),
                        (*(_DWORD *)(v50 + 4) & 0x2000000) != 0 || (*(_DWORD *)(v7 + 512) & 0x4000000) != 0)
                    || *(_QWORD *)(v7 + 528)
                    || *(_QWORD *)(v50 + 40) )
                  {
                    v51 = 2;
                  }
                  else
                  {
                    v51 = 1;
                  }
                }
                else
                {
                  v51 = 0;
                }
                *(_BYTE *)(v7 + 5) = v51;
              }
              if ( *(_QWORD *)(v7 + 584) )
              {
                v52 = *(FILE_LOCK **)(v7 + 584);
                ProcessId = IoGetRequestorProcess(v2);
                if ( !FsRtlFastCheckLockForRead(
                        v52,
                        (PLARGE_INTEGER)&MasterIrp->Flags,
                        (PLARGE_INTEGER)&MasterIrp->AssociatedIrp,
                        0,
                        FileObject,
                        ProcessId) )
                {
                  v12 = -1073741740;
                  if ( !NtfsStatusDebugFlags )
                    goto LABEL_69;
                  v46 = 1212810;
                  goto LABEL_77;
                }
              }
              v76 = *(_QWORD *)&MasterIrp->Flags / (unsigned __int64)*(unsigned int *)(v9 + 356);
              FsRtlAcquireHeaderMutex(v7 + 120, v7 + 160);
              v29 = *(_QWORD *)(v7 + 32);
              v86 = v29 >> *(_BYTE *)(v9 + 488);
              if ( v76 <= v86 )
              {
                if ( v76 < 0 )
                {
                  FsRtlReleaseHeaderMutex(v7 + 120, v7 + 160);
                  v12 = -1073741811;
                  if ( !NtfsStatusDebugFlags )
                    goto LABEL_69;
                  v46 = 1212858;
                  goto LABEL_77;
                }
                v30 = *(_QWORD *)&MasterIrp->Flags;
                if ( v30 < v29 )
                {
                  v31 = *(struct _IRP **)(v7 + 40);
                  if ( v30 >= (unsigned __int64)v31 )
                  {
                    FsRtlReleaseHeaderMutex(v7 + 120, v7 + 160);
                    LOBYTE(v54) = 1;
                    if ( (unsigned __int8)NtfsQuerySupportedFeatures(v9, a1, v55, v54) )
                    {
                      v56 = (struct _MDL *)MasterIrp->AssociatedIrp.MasterIrp;
                      v57 = v29 - *(_QWORD *)&MasterIrp->Flags;
                      if ( v57 <= (unsigned __int64)v56 )
                      {
                        MasterIrp->MdlAddress = (PMDL)v57;
                        v56 = (struct _MDL *)v57;
                      }
                      else
                      {
                        MasterIrp->MdlAddress = v56;
                      }
                      MasterIrp->MdlAddress = (PMDL)(-*(_DWORD *)(v9 + 364)
                                                   & ((unsigned __int64)v56 + *(_DWORD *)(v9 + 364) - 1));
                      *(_DWORD *)&MasterIrp->Type = 528;
                      *(_DWORD *)(&MasterIrp->Size + 1) = 1;
                      memset(&MasterIrp->Flags, 0, 0x200u);
                      LOWORD(MasterIrp->Flags) = -1;
                      HIBYTE(MasterIrp->Flags) = 1;
                      *((_WORD *)&MasterIrp->Flags + 3) = -2047;
                      v2->IoStatus.Information = 528;
                      v12 = 0;
                      goto LABEL_69;
                    }
                    v12 = -1073700189;
                    if ( !NtfsStatusDebugFlags )
                    {
LABEL_69:
                      v34 = Entry;
                      goto LABEL_70;
                    }
                    v46 = 1212888;
                  }
                  else
                  {
                    p_AssociatedIrp = &MasterIrp->AssociatedIrp;
                    if ( (char *)MasterIrp->AssociatedIrp.MasterIrp + v30 >= (char *)v31 )
                    {
                      v58 = (struct _IRP *)((char *)v31 - v30);
                      p_AssociatedIrp->MasterIrp = v58;
                      v83 = -*(_DWORD *)(v9 + 364) & ((unsigned __int64)v58 + *(_DWORD *)(v9 + 364) - 1);
                      p_AssociatedIrp->MasterIrp = (struct _IRP *)v83;
                      v73 = 1;
                      v80 = 1;
                    }
                    FsRtlReleaseHeaderMutex(v7 + 120, v7 + 160);
                    if ( (*(_DWORD *)(v7 + 200) & 8) == 0 && (*(_DWORD *)(v7 + 512) & 0x4000) == 0 )
                    {
                      NtfsPreloadAllocationInternal((__int64)a1, v7, 0, v76, v86, 0);
                      v33 = (struct _IRP *)ExAllocateFromLookasideListEx(&NtfsFileOffloadLookasideList);
                      v34 = v33;
                      Entry = v33;
                      if ( !v33 )
                      {
                        LOBYTE(v25) = NtfsStatusDebugFlags;
                        v12 = -1073741670;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x12823Cu);
LABEL_70:
                        v45 = v72;
LABEL_183:
                        v67 = v70;
                        if ( v70 )
                        {
                          if ( v90 )
                            NtfsReleasePagingResourcePriv(v25, v7);
                          if ( v34 )
                            ExFreeToLookasideListEx(&NtfsFileOffloadLookasideList, v34);
                          if ( v45 )
                            ExFreeToLookasideListEx(&NtfsOffloadIoContextLookasideList, v45);
                          v67 = v70;
                        }
                        if ( v2 )
                        {
                          if ( v67 )
                          {
                            v68 = 0;
                            if ( (v12 & 0x80000000) == 0 )
                              v68 = 528;
                            v2->IoStatus.Information = v68;
                          }
                          else
                          {
                            v2 = 0;
                            v12 = 259;
                          }
                        }
                        if ( NtfsStatusDebugFlags
                          && v12
                          && v12 != 294
                          && v12 - 298 > 1
                          && v12 < 0xFFFFFFED
                          && v12 != -1073741608
                          && v12 != -1073741802
                          && v12 != -1073741807
                          && v12 + 2147483643 > 1
                          && v12 != 259 )
                        {
                          NtfsStatusTraceAndDebugInternal((__int64)a1, v12, 0x12838Fu);
                        }
                        NtfsExtendedCompleteRequestInternal((__int64)a1, v2, v12, v2 != 0, (v12 & 0x80000000) == 0);
                        if ( !NtfsStatusDebugFlags
                          || !v12
                          || v12 == 294
                          || v12 - 298 <= 1
                          || v12 >= 0xFFFFFFED
                          || v12 == -1073741608
                          || v12 == -1073741802
                          || v12 == -1073741807
                          || v12 + 2147483643 <= 1
                          || v12 == 259 )
                        {
                          return v12;
                        }
                        v13 = 1213329;
                        goto LABEL_212;
                      }
                      memset(v33, 0, 0x1000u);
                      *(_DWORD *)&v34->Type = 28;
                      *(_DWORD *)(&v34->Size + 1) = -2147483645;
                      HIDWORD(v34->MdlAddress) = 32;
                      v34->Flags = 16;
                      LODWORD(v34->ThreadListEntry.Flink) = *(_DWORD *)(&MasterIrp->Size + 1);
                      HIDWORD(v34->ThreadListEntry.Flink) = MasterIrp->MdlAddress;
                      v35 = &v34->Flags + 1;
                      *v35 = 48;
                      v36 = 0;
                      v79 = 0;
                      v37 = v76;
                      for ( i = v76; ; i = v37 )
                      {
                        v38 = NtfsLookupNtfsMcbEntryWithSyncFlag(v7 + 400, v37, &v81, &v77, 0, 0, 0, 0);
                        v39 = v38;
                        if ( !v38 && !v36 )
                        {
                          v12 = -1073741566;
                          if ( !NtfsStatusDebugFlags )
                            goto LABEL_69;
                          v46 = 1213064;
                          goto LABEL_77;
                        }
                        if ( v38 )
                        {
                          if ( v81 == -1 )
                          {
                            v12 = -1073741566;
                            if ( !NtfsStatusDebugFlags )
                              goto LABEL_69;
                            v46 = 1213074;
                            goto LABEL_77;
                          }
                          v40 = *(_QWORD *)v74;
                          v41 = 16LL * v36;
                          v42 = Entry;
                          *(PVOID *)((char *)&Entry->IoStatus.Pointer + v41) = (PVOID)(v81 << *(_BYTE *)(*(_QWORD *)v74 + 488LL));
                          *(ULONG_PTR *)((char *)&Entry->IoStatus.Information + v41) = v77 << *(_BYTE *)(v40 + 488);
                          Information = (ULONG_PTR)v75 + (v77 << *(_BYTE *)(v40 + 488));
                          v75 = (struct _IRP *)Information;
                          v84 = Information;
                          if ( !v36 )
                          {
                            v59 = *(_QWORD *)&MasterIrp->Flags % (unsigned __int64)*(unsigned int *)(v40 + 356);
                            if ( v59 )
                            {
                              Entry->IoStatus.Pointer = (char *)Entry->IoStatus.Pointer + v59;
                              v42 = Entry;
                              Entry->IoStatus.Information -= *(_QWORD *)&MasterIrp->Flags
                                                           % (unsigned __int64)*(unsigned int *)(v40 + 356);
                              Information = Entry->IoStatus.Information;
                              v75 = (struct _IRP *)Information;
                              v84 = Information;
                            }
                            else
                            {
                              v42 = Entry;
                              Information = (ULONG_PTR)v75;
                            }
                          }
                          v44 = MasterIrp->AssociatedIrp.MasterIrp;
                          if ( Information >= (unsigned __int64)v44 )
                          {
                            *(ULONG_PTR *)((char *)&v42->IoStatus.Information + v41) += (ULONG_PTR)v44 - Information;
                            v75 = MasterIrp->AssociatedIrp.MasterIrp;
                            v84 = (ULONG_PTR)v75;
                          }
                          v79 = ++v36;
                        }
                        else
                        {
                          v40 = *(_QWORD *)v74;
                        }
                        if ( v36 >= 253 || !v39 && v36 > 0 || v75 >= MasterIrp->AssociatedIrp.MasterIrp )
                          break;
                        v37 = v77 + v76;
                        v76 = v37;
                      }
                      v60 = 16 * v36;
                      Entry->AssociatedIrp.IrpCount = v60;
                      if ( !v91 )
                      {
                        v34 = Entry;
                        v12 = NtfsCreateOffloadIoContext((__int64)v2, v82, v78, (__int64)Entry, &v90, &v72);
                        v45 = v72;
                        if ( (v12 & 0x80000000) == 0 )
                        {
                          *((_DWORD *)v72 + 12) = v73;
                          *((_QWORD *)v45 + 7) = v83;
                          v2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
                          v70 = 0;
                          LODWORD(NumberOfBytes) = Entry->AssociatedIrp.IrpCount + 48;
                          v66 = NtfsDeviceIoControlAsync3(
                                  (__int64)a1,
                                  *(struct _DEVICE_OBJECT **)(*(_QWORD *)v74 + 224LL),
                                  *(__int64 *)v74,
                                  v65,
                                  (IO_COMPLETION_ROUTINE *)NtfsAsyncOffloadReadCompletionRoutine,
                                  v45,
                                  Entry,
                                  NumberOfBytes,
                                  0x218u,
                                  3,
                                  0,
                                  0);
                          v12 = v66;
                          if ( v66 < 0 )
                          {
                            *((_DWORD *)v45 + 2) = v66;
                            NtfsAsyncOffloadReadCompletionRoutine(0, 0, (__int64)v45);
                          }
                        }
                        goto LABEL_183;
                      }
                      v12 = NtfsDeviceIoControl2(
                              (__int64)a1,
                              *(struct _DEVICE_OBJECT **)(v40 + 224),
                              v40,
                              0x2D9404u,
                              (__int64)Entry,
                              v60 + 48,
                              536,
                              3);
                      if ( (v12 & 0x80000000) != 0 )
                      {
                        if ( v12 == -1073741637 || v12 == -1073740701 )
                          NtfsClearSupportedFeatures(*(__int64 *)v74);
                        else
                          NtfsSetSupportedFeatures(*(__int64 *)v74);
                      }
                      else
                      {
                        MdlAddress = Entry->MdlAddress;
                        MasterIrp->MdlAddress = MdlAddress;
                        v62 = v73;
                        if ( (v73 & 1) != 0 && (unsigned __int64)MdlAddress < v83 )
                        {
                          v62 = v73 & 0xFFFFFFFE;
                          v80 = v73 & 0xFFFFFFFE;
                        }
                        *(_DWORD *)&MasterIrp->Type = 528;
                        *(_DWORD *)(&MasterIrp->Size + 1) = v62;
                        v63 = 4;
                        v64 = v88;
                        do
                        {
                          *(_OWORD *)v64 = *(_OWORD *)v35;
                          *((_OWORD *)v64 + 1) = *((_OWORD *)v35 + 1);
                          *((_OWORD *)v64 + 2) = *((_OWORD *)v35 + 2);
                          *((_OWORD *)v64 + 3) = *((_OWORD *)v35 + 3);
                          *((_OWORD *)v64 + 4) = *((_OWORD *)v35 + 4);
                          *((_OWORD *)v64 + 5) = *((_OWORD *)v35 + 5);
                          *((_OWORD *)v64 + 6) = *((_OWORD *)v35 + 6);
                          *((_OWORD *)v64 + 7) = *((_OWORD *)v35 + 7);
                          v64 += 32;
                          v35 += 32;
                          --v63;
                        }
                        while ( v63 );
                        NtfsUpdateFileTimestampsForAccess((__int64)FileObject, (__int64)v82, v78);
                      }
                      if ( NtfsStatusDebugFlags
                        && v12
                        && v12 != 294
                        && v12 - 298 > 1
                        && v12 < 0xFFFFFFED
                        && v12 != -1073741608
                        && v12 != -1073741802
                        && v12 != -1073741807
                        && v12 + 2147483643 > 1
                        && v12 != 259 )
                      {
                        v46 = 1213208;
                        goto LABEL_77;
                      }
                      goto LABEL_69;
                    }
                    v12 = -1073700189;
                    if ( !NtfsStatusDebugFlags )
                      goto LABEL_69;
                    v46 = 1212965;
                  }
LABEL_77:
                  NtfsStatusTraceAndDebugInternal(0, v12, v46);
                  goto LABEL_69;
                }
              }
              FsRtlReleaseHeaderMutex(v7 + 120, v7 + 160);
              v12 = -1073741807;
              goto LABEL_69;
            }
            v12 = -1073741816;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_69;
            v47 = 1212735;
          }
        }
      }
      NtfsStatusTraceAndDebugInternal(0, v12, v47);
      goto LABEL_69;
    }
    memset(MasterIrp, 0, 0x210u);
    *(_DWORD *)&MasterIrp->Type = 528;
    *(_BYTE *)p_Flags = -1;
    BYTE1(MasterIrp->Flags) = -1;
    HIBYTE(MasterIrp->Flags) = 1;
    *((_WORD *)&MasterIrp->Flags + 3) = -2047;
    v2->IoStatus.Information = 528;
    NtfsExtendedCompleteRequestInternal((__int64)a1, v2, 0, v2 != 0, 1);
    return 0;
  }
  else
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC00000BB, 0x12802Eu);
    NtfsExtendedCompleteRequestInternal((__int64)a1, v2, -1073741637, v2 != 0, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC00000BB, 0x12802Fu);
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x1402538c4  mov     rax, rsp
0x1402538c7  push    rbx
0x1402538c8  push    rsi
0x1402538c9  push    rdi
0x1402538ca  push    r12
0x1402538cc  push    r13
0x1402538ce  push    r14
0x1402538d0  push    r15
0x1402538d2  sub     rsp, 100h
0x1402538d9  mov     rdi, rdx
0x1402538dc  mov     rsi, rcx
0x1402538df  xor     r14d, r14d
0x1402538e2  mov     [rax-88h], r14
0x1402538e9  mov     [rax-0A0h], r14
0x1402538f0  mov     [rax+18h], r14b
0x1402538f4  mov     [rsp+138h+var_C8], r14
0x1402538f9  mov     r11, [rdx+0B8h]
0x140253900  mov     [rdx+38h], r14
0x140253904  mov     r8, [r11+30h]
0x140253908  mov     [rsp+138h+FileObject], r8
0x140253910  mov     rcx, r8
0x140253913  call    NtfsDecodeFileObjectForRead
0x140253918  test    rax, rax
0x14025391b  jz      loc_140254A1C
0x140253921  mov     r15, [r8+18h]
0x140253925  lea     r12d, [r14+1]
0x140253929  test    r15, r15
0x14025392c  jz      loc_140254A7A
0x140253932  mov     rax, [r8+20h]
0x140253936  mov     [rsp+138h+var_98], rax
0x14025393e  mov     r13, [r15+0C0h]
0x140253945  mov     qword ptr [rsp+138h+var_B8], r13
0x14025394d  mov     rcx, [r15+0B8h]
0x140253954  mov     [rsp+138h+var_80], rcx
0x14025395c  test    rax, rax
0x14025395f  jz      loc_140254A6F
0x140253965  movzx   r10d, byte ptr [rax+58h]
0x14025396a  mov     r9d, [r13+1E50h]
0x140253971  mov     ebx, 3
0x140253976  cmp     r9d, ebx
0x140253979  jnz     loc_140254DE3
0x14025397f  test    r12b, r9b
0x140253982  jz      loc_140253A0A
0x140253988  cmp     r10d, 2
0x14025398c  jnz     loc_140254A9D
0x140253992  mov     [rsp+138h+var_48], r15
0x14025399a  test    dword ptr [r15+200h], 1000000h
0x1402539a5  jnz     loc_140254AEF
0x1402539ab  mov     eax, [r13+4]
0x1402539af  test    r12b, al
0x1402539b2  jnz     loc_140253A68
0x1402539b8  mov     al, cs:NtfsStatusDebugFlags
0x1402539be  mov     ebx, 0C000026Eh
0x1402539c3  test    al, al
0x1402539c5  jz      short loc_1402539D7
0x1402539c7  mov     r8d, 128050h
0x1402539cd  mov     edx, ebx
0x1402539cf  mov     rcx, rsi
0x1402539d2  call    NtfsStatusTraceAndDebugInternal
0x1402539d7  test    rdi, rdi
0x1402539da  setnz   r9b
0x1402539de  mov     dword ptr [rsp+138h+PostIrpRoutine], r14d
0x1402539e3  mov     r8d, ebx
0x1402539e6  mov     rdx, rdi
0x1402539e9  mov     rcx, rsi
0x1402539ec  call    NtfsExtendedCompleteRequestInternal
0x1402539f1  mov     al, cs:NtfsStatusDebugFlags
0x1402539f7  test    al, al
0x1402539f9  jz      loc_1402548B5
0x1402539ff  mov     r8d, 128051h
0x140253a05  jmp     loc_140254A59
0x140253a0a  mov     al, cs:NtfsStatusDebugFlags
0x140253a10  mov     r14d, 0C00000BBh
0x140253a16  test    al, al
0x140253a18  jz      short loc_140253A2B
0x140253a1a  mov     r8d, 12802Eh
0x140253a20  mov     edx, r14d
0x140253a23  mov     rcx, rsi
0x140253a26  call    NtfsStatusTraceAndDebugInternal
0x140253a2b  xor     ebx, ebx
0x140253a2d  test    rdi, rdi
0x140253a30  setnz   r9b
0x140253a34  mov     dword ptr [rsp+138h+PostIrpRoutine], ebx
0x140253a38  mov     r8d, r14d
0x140253a3b  mov     rdx, rdi
0x140253a3e  mov     rcx, rsi
0x140253a41  call    NtfsExtendedCompleteRequestInternal
0x140253a46  mov     cl, cs:NtfsStatusDebugFlags
0x140253a4c  test    cl, cl
0x140253a4e  jz      short loc_140253A60
0x140253a50  mov     r8d, 12802Fh
0x140253a56  mov     edx, r14d
0x140253a59  xor     ecx, ecx
0x140253a5b  call    NtfsStatusTraceAndDebugInternal
0x140253a60  mov     eax, r14d
0x140253a63  jmp     loc_1402548B7
0x140253a68  cmp     dword ptr [r11+10h], 20h ; ' '
0x140253a6d  jb      loc_140254B41
0x140253a73  cmp     dword ptr [r11+8], 210h
0x140253a7b  jb      loc_140254B93
0x140253a81  mov     r14, [rdi+18h]
0x140253a85  mov     r9d, [r13+16Ch]
0x140253a8c  lea     rbx, [r14+10h]
0x140253a90  mov     [rsp+138h+var_50], rbx
0x140253a98  mov     r8, [rbx]
0x140253a9b  xor     edx, edx
0x140253a9d  mov     rax, r8
0x140253aa0  div     r9
0x140253aa3  xor     r10d, r10d
0x140253aa6  test    rdx, rdx
0x140253aa9  jnz     loc_140254BE5
0x140253aaf  mov     rcx, [r14+18h]
0x140253ab3  mov     rax, rcx
0x140253ab6  div     r9
0x140253ab9  test    rdx, rdx
0x140253abc  jnz     loc_140254C3A
0x140253ac2  cmp     dword ptr [r14], 20h ; ' '
0x140253ac6  jnz     loc_140254C8F
0x140253acc  lea     rax, [r8+rcx]
0x140253ad0  cmp     rax, r8
0x140253ad3  jb      loc_1402548CB
0x140253ad9  test    rcx, rcx
0x140253adc  jz      loc_1402D0992
0x140253ae2  cmp     [r15+210h], r10
0x140253ae9  jnz     loc_140254CE4
0x140253aef  cmp     dword ptr [r15+100h], 80h
0x140253afa  jnz     loc_140254D39
0x140253b00  mov     [rsp+138h+var_C0], r10d
0x140253b05  mov     [rsp+138h+Entry], r10
0x140253b0a  mov     [rsp+138h+var_B0], r10
0x140253b12  mov     [rsp+138h+var_78], r10
0x140253b1a  mov     [rsp+138h+var_D4], r12b
0x140253b1f  mov     cl, [rsi+0Ch]
0x140253b22  and     cl, r12b
0x140253b25  mov     [rsp+138h+arg_18], cl
0x140253b2c  mov     rax, [r15+0B8h]
0x140253b33  cmp     dword ptr [rax+8], 10h
0x140253b37  jb      loc_140254D8E
0x140253b3d  mov     rax, [r15+120h]
0x140253b44  mov     r8b, cl
0x140253b47  mov     rdx, r15
0x140253b4a  mov     rcx, rsi
0x140253b4d  cmp     [rax+10h], r10
0x140253b51  jz      loc_14025429D
0x140253b57  call    NtfsAcquirePagingResourceExclusive
0x140253b5c  mov     cl, al
0x140253b5e  mov     [rsp+138h+arg_10], al
0x140253b65  xor     r9d, r9d
0x140253b68  test    cl, cl
0x140253b6a  jz      loc_1402542E9
0x140253b70  movzx   ecx, word ptr [r15+1CCh]
0x140253b78  test    cl, cl
0x140253b7a  jnz     loc_140253FFC
0x140253b80  bt      cx, 0Eh
0x140253b85  jb      loc_140254017
0x140253b8b  test    cx, cx
0x140253b8e  js      loc_140254032
0x140253b94  mov     eax, [r15+200h]
0x140253b9b  bt      eax, 10h
0x140253b9f  jb      loc_14025404D
0x140253ba5  bt      eax, 1Ah
0x140253ba9  jb      loc_140253F73
0x140253baf  mov     rax, [r15+120h]
0x140253bb6  cmp     [rax+10h], r9
0x140253bba  jnz     loc_14025430B
0x140253bc0  mov     r8, [rsp+138h+var_98]
0x140253bc8  test    dword ptr [r8+4], 8000h
0x140253bd0  jnz     loc_14025406B
0x140253bd6  mov     edx, [r15+200h]
0x140253bdd  bt      edx, 18h
0x140253be1  jb      loc_140254089
0x140253be7  and     edx, 10000h
0x140253bed  mov     eax, edx
0x140253bef  neg     eax
0x140253bf1  sbb     ecx, ecx
0x140253bf3  and     ecx, 0C000026Eh
0x140253bf9  mov     ebx, ecx
0x140253bfb  mov     [rsp+138h+var_D8], ecx
0x140253bff  mov     al, cs:NtfsStatusDebugFlags
0x140253c05  test    al, al
0x140253c07  jnz     loc_140253F98
0x140253c0d  mov     eax, [r15+200h]
0x140253c14  test    al, 40h
0x140253c16  jnz     loc_1402540A7
0x140253c1c  test    ebx, ebx
0x140253c1e  js      loc_140253F86
0x140253c24  mov     eax, [r15+0C8h]
0x140253c2b  test    al, 20h
0x140253c2d  jz      loc_140254355
0x140253c33  lea     rcx, NtfsPrePostIrp
0x140253c3a  mov     [rsp+138h+PostIrpRoutine], rcx; PostIrpRoutine
0x140253c3f  lea     r9, NtfsOplockComplete; CompletionRoutine
0x140253c46  mov     r8, rsi; Context
0x140253c49  mov     rdx, rdi; Irp
0x140253c4c  lea     rcx, [r15+58h]; Oplock
0x140253c50  call    cs:__imp_FsRtlCheckOplock
0x140253c57  nop     dword ptr [rax+rax+00h]
0x140253c5c  mov     ebx, eax
0x140253c5e  mov     [rsp+138h+var_D8], eax
0x140253c62  xor     r8d, r8d
0x140253c65  test    eax, eax
0x140253c67  jnz     loc_1402540CE
0x140253c6d  cmp     [r15+5], r8b
0x140253c71  jz      loc_1402543A9
0x140253c77  cmp     [r15+248h], r8
0x140253c7e  jnz     loc_140254445
0x140253c84  mov     ecx, [r13+164h]
0x140253c8b  xor     edx, edx
0x140253c8d  mov     rax, [r14+10h]
0x140253c91  div     rcx
0x140253c94  mov     [rsp+138h+var_A8], rax
0x140253c9c  lea     rdx, [r15+0A0h]
0x140253ca3  lea     rcx, [r15+78h]
0x140253ca7  call    cs:__imp_FsRtlAcquireHeaderMutex
0x140253cae  nop     dword ptr [rax+rax+00h]
0x140253cb3  mov     rbx, [r15+20h]
0x140253cb7  mov     cl, [r13+1E8h]
0x140253cbe  mov     rdx, rbx
0x140253cc1  sar     rdx, cl
0x140253cc4  mov     [rsp+138h+var_60], rdx
0x140253ccc  mov     rax, [rsp+138h+var_A8]
0x140253cd4  cmp     rax, rdx
0x140253cd7  jg      loc_140254497
0x140253cdd  test    rax, rax
0x140253ce0  js      loc_140254175
0x140253ce6  mov     r8, [r14+10h]
0x140253cea  cmp     r8, rbx
0x140253ced  jnb     loc_140254497
0x140253cf3  mov     rdx, [r15+28h]
0x140253cf7  cmp     r8, rdx
0x140253cfa  jnb     loc_1402544BE
0x140253d00  lea     r9, [r14+18h]
0x140253d04  mov     rcx, [r9]
0x140253d07  add     rcx, r8
0x140253d0a  cmp     rcx, rdx
0x140253d0d  jnb     loc_140254566
0x140253d13  lea     rdx, [r15+0A0h]
0x140253d1a  lea     rcx, [r15+78h]
0x140253d1e  call    cs:__imp_FsRtlReleaseHeaderMutex
0x140253d25  nop     dword ptr [rax+rax+00h]
0x140253d2a  mov     eax, [r15+0C8h]
0x140253d31  test    al, 8
0x140253d33  jnz     loc_14025427C
0x140253d39  test    dword ptr [r15+200h], 4000h
0x140253d44  jnz     loc_14025427C
0x140253d4a  mov     [rsp+138h+ProcessId], 0
0x140253d53  mov     rax, [rsp+138h+var_60]
0x140253d5b  mov     [rsp+138h+PostIrpRoutine], rax
0x140253d60  mov     r9, [rsp+138h+var_A8]
0x140253d68  xor     r8d, r8d
0x140253d6b  mov     rdx, r15
0x140253d6e  mov     rcx, rsi
0x140253d71  call    NtfsPreloadAllocationInternal
0x140253d76  lea     rcx, NtfsFileOffloadLookasideList; Lookaside
0x140253d7d  call    cs:__imp_ExAllocateFromLookasideListEx
0x140253d84  nop     dword ptr [rax+rax+00h]
0x140253d89  mov     r13, rax
0x140253d8c  mov     [rsp+138h+Entry], rax
0x140253d91  xor     r8d, r8d
0x140253d94  test    rax, rax
0x140253d97  jz      loc_1402541CB
0x140253d9d  xor     edx, edx; Val
0x140253d9f  mov     r8d, 1000h; Size
0x140253da5  mov     rcx, rax; void *
0x140253da8  call    memset
0x140253dad  mov     dword ptr [r13+0], 1Ch
0x140253db5  mov     dword ptr [r13+4], 80000003h
0x140253dbd  mov     dword ptr [r13+0Ch], 20h ; ' '
0x140253dc5  mov     dword ptr [r13+10h], 10h
0x140253dcd  mov     eax, [r14+4]
0x140253dd1  mov     [r13+20h], eax
0x140253dd5  mov     eax, [r14+8]
0x140253dd9  mov     [r13+24h], eax
0x140253ddd  add     r13, 14h
0x140253de1  mov     dword ptr [r13+0], 30h ; '0'
0x140253de9  xor     r8d, r8d
0x140253dec  mov     ebx, r8d
0x140253def  mov     [rsp+138h+var_90], ebx
0x140253df6  mov     rax, [rsp+138h+var_A8]
0x140253dfe  mov     [rsp+138h+var_58], rax
0x140253e06  lea     rcx, [r15+190h]
0x140253e0d  mov     [rsp+138h+NumberOfBytes], r8
0x140253e12  mov     [rsp+138h+Src], r8
0x140253e17  mov     [rsp+138h+ProcessId], r8
0x140253e1c  mov     [rsp+138h+PostIrpRoutine], r8
0x140253e21  lea     r9, [rsp+138h+var_A0]
0x140253e29  lea     r8, [rsp+138h+var_88]
0x140253e31  mov     rdx, rax
0x140253e34  call    NtfsLookupNtfsMcbEntryWithSyncFlag
0x140253e39  mov     r11b, al
0x140253e3c  xor     r8d, r8d
0x140253e3f  test    al, al
0x140253e41  jz      loc_140253FD9
0x140253e47  test    r11b, r11b
0x140253e4a  jz      loc_140253F8B
0x140253e50  cmp     [rsp+138h+var_88], 0FFFFFFFFFFFFFFFFh
0x140253e59  jz      loc_140253F51
0x140253e5f  test    r11b, r11b
0x140253e62  jz      loc_140253F8B
0x140253e68  mov     r10, qword ptr [rsp+138h+var_B8]
  ... truncated ...
```
