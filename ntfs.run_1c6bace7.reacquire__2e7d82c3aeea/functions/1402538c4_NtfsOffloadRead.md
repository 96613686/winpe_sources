# NtfsOffloadRead

- ea: `0x1402538c4`
- end: `0x140254e66`
- name: `NtfsOffloadRead`
- size: `5538`
- prototype: `__int64 __fastcall(int, PIRP Irp)`
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
  __int64 v6; // r9
  __int64 v7; // r11
  __int64 v8; // r15
  __int64 v9; // rax
  __int64 v10; // r13
  int v11; // r10d
  __int64 v12; // r9
  unsigned int OffloadIoContext; // ebx
  __int64 v14; // r8
  struct _IRP *MasterIrp; // r14
  unsigned __int64 v17; // r9
  ULONG *p_Flags; // rbx
  unsigned __int64 v19; // r8
  struct _IRP *v20; // rcx
  char v21; // cl
  __int64 v22; // rdx
  _BYTE *v23; // rcx
  int v24; // edx
  __int64 v25; // rcx
  __int64 v26; // r9
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // r8
  int v30; // edx
  int v31; // edx
  __int64 v32; // rbx
  unsigned __int64 v33; // r8
  struct _IRP *v34; // rdx
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *p_AssociatedIrp; // r9
  _DWORD *v36; // rax
  _DWORD *v37; // r13
  _DWORD *v38; // r13
  int v39; // ebx
  signed __int64 v40; // rax
  char v41; // al
  char v42; // r11
  __int64 v43; // r10
  __int64 v44; // r9
  _DWORD *v45; // r8
  struct _IRP *v46; // rcx
  struct _IRP *v47; // rax
  PVOID v48; // r14
  __int64 v49; // r8
  __int64 v50; // r8
  __int64 v51; // r8
  struct _ERESOURCE *v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rdx
  char v55; // al
  FILE_LOCK *v56; // rbx
  PEPROCESS ProcessId; // rax
  __int64 v58; // r9
  __int64 v59; // r8
  struct _MDL *v60; // r8
  unsigned __int64 v61; // rbx
  struct _IRP *v62; // rdx
  unsigned __int64 v63; // rdx
  int v64; // ebx
  struct _MDL *v65; // rax
  unsigned int v66; // ecx
  __int64 v67; // r9
  ULONG *v68; // rax
  int v69; // eax
  char v70; // al
  __int64 v71; // rax
  __int64 v72; // r9
  SIZE_T NumberOfBytes; // [rsp+38h] [rbp-100h]
  char v74; // [rsp+64h] [rbp-D4h]
  _DWORD *Entry; // [rsp+68h] [rbp-D0h]
  PVOID v76; // [rsp+70h] [rbp-C8h] BYREF
  int v77; // [rsp+78h] [rbp-C0h]
  int v78[2]; // [rsp+80h] [rbp-B8h]
  struct _IRP *v79; // [rsp+88h] [rbp-B0h]
  signed __int64 v80; // [rsp+90h] [rbp-A8h]
  __int64 v81; // [rsp+98h] [rbp-A0h] BYREF
  __int64 v82; // [rsp+A0h] [rbp-98h]
  int v83; // [rsp+A8h] [rbp-90h]
  unsigned int v84; // [rsp+ACh] [rbp-8Ch]
  __int64 v85; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v86; // [rsp+B8h] [rbp-80h]
  struct _IRP *v87; // [rsp+C0h] [rbp-78h]
  struct _IRP *v88; // [rsp+C8h] [rbp-70h]
  PFILE_OBJECT FileObject; // [rsp+D0h] [rbp-68h]
  __int64 v90; // [rsp+D8h] [rbp-60h]
  signed __int64 i; // [rsp+E0h] [rbp-58h]
  ULONG *v92; // [rsp+E8h] [rbp-50h]
  __int64 v93; // [rsp+F0h] [rbp-48h]
  char v94; // [rsp+150h] [rbp+18h] BYREF
  char v95; // [rsp+158h] [rbp+20h]

  v2 = Irp;
  v85 = 0;
  v81 = 0;
  v94 = 0;
  v76 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Irp->IoStatus.Information = 0;
  FileObject = CurrentStackLocation->FileObject;
  if ( !NtfsDecodeFileObjectForRead(FileObject) )
  {
    OffloadIoContext = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1212446);
    LOBYTE(v6) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v2, 3221225485LL, v6, 0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1212447;
    goto LABEL_212;
  }
  v8 = *(_QWORD *)(v5 + 24);
  if ( v8 )
  {
    v9 = *(_QWORD *)(v5 + 32);
    v82 = v9;
    v10 = *(_QWORD *)(v8 + 192);
    *(_QWORD *)v78 = v10;
    v86 = *(_QWORD *)(v8 + 184);
    if ( v9 )
      v11 = *(unsigned __int8 *)(v9 + 88);
    else
      v11 = 5;
  }
  else
  {
    v10 = 0;
    *(_QWORD *)v78 = 0;
    v82 = 0;
    v86 = 0;
    v11 = 1;
  }
  v12 = *(unsigned int *)(v10 + 7760);
  if ( (_DWORD)v12 != 3
    && MEMORY[0xFFFFF78000000320] - *(_QWORD *)(v10 + 7768) >= 0x218711A00uLL / (unsigned int)dword_1400953B0 )
  {
    v12 = 3;
    _InterlockedExchange((volatile __int32 *)(v10 + 7760), 3);
  }
  if ( (v12 & 1) != 0 )
  {
    if ( v11 != 2 )
    {
      OffloadIoContext = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1212472);
      LOBYTE(v12) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v2, 3221225485LL, v12, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1212473;
      goto LABEL_212;
    }
    v93 = v8;
    if ( (*(_DWORD *)(v8 + 512) & 0x1000000) != 0 )
    {
      OffloadIoContext = -1073741816;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225480LL, 1212482);
      LOBYTE(v12) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v2, 3221225480LL, v12, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1212483;
      goto LABEL_212;
    }
    if ( (*(_DWORD *)(v10 + 4) & 1) == 0 )
    {
      OffloadIoContext = -1073741202;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221226094LL, 1212496);
      LOBYTE(v12) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v2, 3221226094LL, v12, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1212497;
LABEL_212:
      NtfsStatusTraceAndDebugInternal(0, OffloadIoContext, v14);
      return OffloadIoContext;
    }
    if ( *(_DWORD *)(v7 + 16) < 0x20u )
    {
      OffloadIoContext = -1073741789;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225507LL, 1212515);
      LOBYTE(v12) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v2, 3221225507LL, v12, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1212516;
      goto LABEL_212;
    }
    if ( *(_DWORD *)(v7 + 8) < 0x210u )
    {
      OffloadIoContext = -1073741789;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225507LL, 1212521);
      LOBYTE(v12) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v2, 3221225507LL, v12, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1212522;
      goto LABEL_212;
    }
    MasterIrp = v2->AssociatedIrp.MasterIrp;
    v17 = *(unsigned int *)(v10 + 364);
    p_Flags = &MasterIrp->Flags;
    v92 = &MasterIrp->Flags;
    v19 = *(_QWORD *)&MasterIrp->Flags;
    if ( v19 % v17 )
    {
      OffloadIoContext = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1212534);
      LOBYTE(v17) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v2, 3221225485LL, v17, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1212535;
      goto LABEL_212;
    }
    v20 = MasterIrp->AssociatedIrp.MasterIrp;
    if ( (unsigned __int64)v20 % v17 )
    {
      OffloadIoContext = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1212540);
      LOBYTE(v17) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v2, 3221225485LL, v17, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1212541;
      goto LABEL_212;
    }
    if ( *(_DWORD *)&MasterIrp->Type != 32 )
    {
      OffloadIoContext = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1212546);
      LOBYTE(v17) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v2, 3221225485LL, v17, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1212547;
      goto LABEL_212;
    }
    if ( (unsigned __int64)v20 + v19 < v19 )
    {
      OffloadIoContext = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1212558);
      LOBYTE(v17) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, v2, 3221225485LL, v17, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1212559;
      goto LABEL_212;
    }
    if ( v20 )
    {
      if ( *(_QWORD *)(v8 + 528) )
      {
        OffloadIoContext = -1073700189;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221267107LL, 1212589);
        LOBYTE(v17) = v2 != 0;
        NtfsExtendedCompleteRequestInternal(a1, v2, 3221267107LL, v17, 0);
        if ( !NtfsStatusDebugFlags )
          return OffloadIoContext;
        v14 = 1212590;
        goto LABEL_212;
      }
      if ( *(_DWORD *)(v8 + 256) != 128 )
      {
        OffloadIoContext = -1073700189;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221267107LL, 1212599);
        LOBYTE(v17) = v2 != 0;
        NtfsExtendedCompleteRequestInternal(a1, v2, 3221267107LL, v17, 0);
        if ( !NtfsStatusDebugFlags )
          return OffloadIoContext;
        v14 = 1212600;
        goto LABEL_212;
      }
      v77 = 0;
      Entry = 0;
      v79 = 0;
      v87 = 0;
      v74 = 1;
      v21 = a1[12] & 1;
      v95 = v21;
      if ( *(_DWORD *)(*(_QWORD *)(v8 + 184) + 8LL) < 0x10u )
      {
        OffloadIoContext = -1073700189;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221267107LL, 1212609);
        LOBYTE(v17) = v2 != 0;
        NtfsExtendedCompleteRequestInternal(a1, v2, 3221267107LL, v17, 0);
        if ( !NtfsStatusDebugFlags )
          return OffloadIoContext;
        v14 = 1212610;
        goto LABEL_212;
      }
      LOBYTE(v19) = v21;
      v22 = v8;
      v23 = a1;
      if ( *(_QWORD *)(*(_QWORD *)(v8 + 288) + 16LL) )
        goto LABEL_30;
      LOBYTE(v25) = NtfsAcquirePagingShared(a1, v8, v19, 0);
      v94 = v25;
      v26 = 0;
      if ( (_BYTE)v25 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v8 + 288) + 16LL) )
        {
          NtfsReleasePagingResourcePriv(v25, v8, v51, 0);
          LOBYTE(v19) = v95;
          v22 = v8;
          v23 = a1;
LABEL_30:
          LOBYTE(v25) = NtfsAcquirePagingResourceExclusive(v23, v22, v19);
          v94 = v25;
          v26 = 0;
        }
      }
      else
      {
        LOBYTE(v25) = 0;
      }
      if ( (_BYTE)v25 )
      {
        v27 = *(unsigned __int16 *)(v8 + 460);
        if ( (_BYTE)v27 )
        {
          OffloadIoContext = -1073700189;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_69;
          v50 = 1212663;
          goto LABEL_79;
        }
        if ( (v27 & 0x4000) != 0 )
        {
          OffloadIoContext = -1073700189;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_69;
          v50 = 1212669;
          goto LABEL_79;
        }
        if ( (v27 & 0x8000u) != 0LL )
        {
          OffloadIoContext = -1073700189;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_69;
          v50 = 1212675;
          goto LABEL_79;
        }
        v28 = *(_DWORD *)(v8 + 512);
        if ( (v28 & 0x10000) != 0 )
        {
          OffloadIoContext = -1073741202;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_69;
          v50 = 1212685;
          goto LABEL_79;
        }
        if ( (v28 & 0x4000000) != 0 )
        {
          OffloadIoContext = -1073741431;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_69;
          v50 = 1212691;
          goto LABEL_79;
        }
        if ( !*(_QWORD *)(*(_QWORD *)(v8 + 288) + 16LL) )
        {
LABEL_38:
          v29 = v82;
          if ( (*(_DWORD *)(v82 + 4) & 0x8000) != 0 )
          {
            OffloadIoContext = -1073741528;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_69;
            v50 = 1212729;
          }
          else
          {
            v30 = *(_DWORD *)(v8 + 512);
            if ( (v30 & 0x1000000) == 0 )
            {
              v31 = v30 & 0x10000;
              v27 = v31 != 0 ? 0xC000026E : 0;
              OffloadIoContext = v31 != 0 ? 0xC000026E : 0;
              if ( NtfsStatusDebugFlags && v31 )
                NtfsStatusTraceAndDebugInternal(0, (unsigned int)v27, 1212745);
              if ( (*(_DWORD *)(v8 + 512) & 0x40) != 0 )
              {
                OffloadIoContext = -1073741533;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 3221225763LL, 1212749);
              }
              if ( (OffloadIoContext & 0x80000000) != 0 )
                goto LABEL_69;
              if ( (*(_DWORD *)(v8 + 200) & 0x20) == 0 )
              {
                LOBYTE(v29) = 1;
                NtfsAcquireResourceShared(v27, v8, v29);
                NtfsUpdateScbFromAttribute(a1, v8, 0);
                if ( *(_WORD *)v8 == 1794 )
                  v52 = (struct _ERESOURCE *)(*(_QWORD *)(v8 + 104) + 64LL);
                else
                  v52 = *(struct _ERESOURCE **)(v8 + 8);
                ExReleaseResourceLite(v52);
              }
              OffloadIoContext = FsRtlCheckOplock((POPLOCK)(v8 + 88), v2, a1, NtfsOplockComplete, NtfsPrePostIrp);
              if ( OffloadIoContext )
              {
                v2 = 0;
                a1 = 0;
                if ( NtfsStatusDebugFlags
                  && (((OffloadIoContext - 294) & 0xFFFFFFFA) != 0 || OffloadIoContext == 295)
                  && OffloadIoContext < 0xFFFFFFED
                  && OffloadIoContext != -1073741608
                  && OffloadIoContext != -1073741802
                  && OffloadIoContext != -1073741807
                  && OffloadIoContext + 2147483643 > 1
                  && OffloadIoContext != 259 )
                {
                  NtfsStatusTraceAndDebugInternal(0, OffloadIoContext, 1212786);
                }
                goto LABEL_69;
              }
              if ( !*(_BYTE *)(v8 + 5) )
              {
                if ( (*(_DWORD *)(*(_QWORD *)(v8 + 192) + 4LL) & 0x4000005) == 1
                  && *(_WORD *)v8 == 1797
                  && FsRtlOplockIsFastIoPossible((POPLOCK)(v8 + 88)) )
                {
                  if ( *(_DWORD *)(v8 + 452)
                    || (v53 = *(_QWORD *)(v8 + 584)) != 0 && *(_BYTE *)(v53 + 16)
                    || (v54 = *(_QWORD *)(v8 + 192),
                        (*(_DWORD *)(v54 + 4) & 0x2000000) != 0 || (*(_DWORD *)(v8 + 512) & 0x4000000) != 0)
                    || *(_QWORD *)(v8 + 528)
                    || *(_QWORD *)(v54 + 40) )
                  {
                    v55 = 2;
                  }
                  else
                  {
                    v55 = 1;
                  }
                }
                else
                {
                  v55 = 0;
                }
                *(_BYTE *)(v8 + 5) = v55;
              }
              if ( *(_QWORD *)(v8 + 584) )
              {
                v56 = *(FILE_LOCK **)(v8 + 584);
                ProcessId = IoGetRequestorProcess(v2);
                if ( !FsRtlFastCheckLockForRead(
                        v56,
                        (PLARGE_INTEGER)&MasterIrp->Flags,
                        (PLARGE_INTEGER)&MasterIrp->AssociatedIrp,
                        0,
                        FileObject,
                        ProcessId) )
                {
                  OffloadIoContext = -1073741740;
                  if ( !NtfsStatusDebugFlags )
                    goto LABEL_69;
                  v49 = 1212810;
                  goto LABEL_77;
                }
              }
              v80 = *(_QWORD *)&MasterIrp->Flags / (unsigned __int64)*(unsigned int *)(v10 + 356);
              FsRtlAcquireHeaderMutex(v8 + 120, v8 + 160);
              v32 = *(_QWORD *)(v8 + 32);
              v90 = v32 >> *(_BYTE *)(v10 + 488);
              if ( v80 <= v90 )
              {
                if ( v80 < 0 )
                {
                  FsRtlReleaseHeaderMutex(v8 + 120, v8 + 160);
                  OffloadIoContext = -1073741811;
                  if ( !NtfsStatusDebugFlags )
                    goto LABEL_69;
                  v49 = 1212858;
                  goto LABEL_77;
                }
                v33 = *(_QWORD *)&MasterIrp->Flags;
                if ( v33 < v32 )
                {
                  v34 = *(struct _IRP **)(v8 + 40);
                  if ( v33 >= (unsigned __int64)v34 )
                  {
                    FsRtlReleaseHeaderMutex(v8 + 120, v8 + 160);
                    LOBYTE(v58) = 1;
                    if ( (unsigned __int8)NtfsQuerySupportedFeatures(v10, a1, v59, v58) )
                    {
                      v60 = (struct _MDL *)MasterIrp->AssociatedIrp.MasterIrp;
                      v61 = v32 - *(_QWORD *)&MasterIrp->Flags;
                      if ( v61 <= (unsigned __int64)v60 )
                      {
                        MasterIrp->MdlAddress = (PMDL)v61;
                        v60 = (struct _MDL *)v61;
                      }
                      else
                      {
                        MasterIrp->MdlAddress = v60;
                      }
                      MasterIrp->MdlAddress = (PMDL)(-*(_DWORD *)(v10 + 364)
                                                   & ((unsigned __int64)v60 + *(_DWORD *)(v10 + 364) - 1));
                      *(_DWORD *)&MasterIrp->Type = 528;
                      *(_DWORD *)(&MasterIrp->Size + 1) = 1;
                      memset(&MasterIrp->Flags, 0, 0x200u);
                      LOWORD(MasterIrp->Flags) = -1;
                      HIBYTE(MasterIrp->Flags) = 1;
                      *((_WORD *)&MasterIrp->Flags + 3) = -2047;
                      v2->IoStatus.Information = 528;
                      OffloadIoContext = 0;
                      goto LABEL_69;
                    }
                    OffloadIoContext = -1073700189;
                    if ( !NtfsStatusDebugFlags )
                    {
LABEL_69:
                      v37 = Entry;
                      goto LABEL_70;
                    }
                    v49 = 1212888;
                  }
                  else
                  {
                    p_AssociatedIrp = &MasterIrp->AssociatedIrp;
                    if ( (char *)MasterIrp->AssociatedIrp.MasterIrp + v33 >= (char *)v34 )
                    {
                      v62 = (struct _IRP *)((char *)v34 - v33);
                      p_AssociatedIrp->MasterIrp = v62;
                      v87 = (struct _IRP *)(-*(_DWORD *)(v10 + 364)
                                          & ((unsigned __int64)v62 + *(_DWORD *)(v10 + 364) - 1));
                      p_AssociatedIrp->MasterIrp = v87;
                      v77 = 1;
                      v84 = 1;
                    }
                    FsRtlReleaseHeaderMutex(v8 + 120, v8 + 160);
                    if ( (*(_DWORD *)(v8 + 200) & 8) == 0 && (*(_DWORD *)(v8 + 512) & 0x4000) == 0 )
                    {
                      NtfsPreloadAllocationInternal((_DWORD)a1, v90, 0);
                      v36 = ExAllocateFromLookasideListEx(&NtfsFileOffloadLookasideList);
                      v37 = v36;
                      Entry = v36;
                      if ( !v36 )
                      {
                        LOBYTE(v27) = NtfsStatusDebugFlags;
                        OffloadIoContext = -1073741670;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 1212988);
LABEL_70:
                        v48 = v76;
LABEL_183:
                        v70 = v74;
                        if ( v74 )
                        {
                          if ( v94 )
                            NtfsReleasePagingResourcePriv(v27, v8, 0, v26);
                          if ( v37 )
                            ExFreeToLookasideListEx(&NtfsFileOffloadLookasideList, v37);
                          if ( v48 )
                            ExFreeToLookasideListEx(&NtfsOffloadIoContextLookasideList, v48);
                          v70 = v74;
                        }
                        if ( v2 )
                        {
                          if ( v70 )
                          {
                            v71 = 0;
                            if ( (OffloadIoContext & 0x80000000) == 0 )
                              v71 = 528;
                            v2->IoStatus.Information = v71;
                          }
                          else
                          {
                            v2 = 0;
                            OffloadIoContext = 259;
                          }
                        }
                        if ( NtfsStatusDebugFlags
                          && OffloadIoContext
                          && OffloadIoContext != 294
                          && OffloadIoContext - 298 > 1
                          && OffloadIoContext < 0xFFFFFFED
                          && OffloadIoContext != -1073741608
                          && OffloadIoContext != -1073741802
                          && OffloadIoContext != -1073741807
                          && OffloadIoContext + 2147483643 > 1
                          && OffloadIoContext != 259 )
                        {
                          NtfsStatusTraceAndDebugInternal(a1, OffloadIoContext, 1213327);
                        }
                        LOBYTE(v26) = v2 != 0;
                        NtfsExtendedCompleteRequestInternal(
                          a1,
                          v2,
                          OffloadIoContext,
                          v26,
                          (OffloadIoContext & 0x80000000) == 0);
                        if ( !NtfsStatusDebugFlags
                          || !OffloadIoContext
                          || OffloadIoContext == 294
                          || OffloadIoContext - 298 <= 1
                          || OffloadIoContext >= 0xFFFFFFED
                          || OffloadIoContext == -1073741608
                          || OffloadIoContext == -1073741802
                          || OffloadIoContext == -1073741807
                          || OffloadIoContext + 2147483643 <= 1
                          || OffloadIoContext == 259 )
                        {
                          return OffloadIoContext;
                        }
                        v14 = 1213329;
                        goto LABEL_212;
                      }
                      memset(v36, 0, 0x1000u);
                      *v37 = 28;
                      v37[1] = -2147483645;
                      v37[3] = 32;
                      v37[4] = 16;
                      v37[8] = *(_DWORD *)(&MasterIrp->Size + 1);
                      v37[9] = MasterIrp->MdlAddress;
                      v38 = v37 + 5;
                      *v38 = 48;
                      v39 = 0;
                      v83 = 0;
                      v40 = v80;
                      for ( i = v80; ; i = v40 )
                      {
                        v41 = NtfsLookupNtfsMcbEntryWithSyncFlag(v8 + 400, v40, &v85, &v81, 0, 0, 0, 0);
                        v42 = v41;
                        if ( !v41 && !v39 )
                        {
                          OffloadIoContext = -1073741566;
                          if ( !NtfsStatusDebugFlags )
                            goto LABEL_69;
                          v49 = 1213064;
                          goto LABEL_77;
                        }
                        if ( v41 )
                        {
                          if ( v85 == -1 )
                          {
                            OffloadIoContext = -1073741566;
                            if ( !NtfsStatusDebugFlags )
                              goto LABEL_69;
                            v49 = 1213074;
                            goto LABEL_77;
                          }
                          v43 = *(_QWORD *)v78;
                          v44 = 4LL * v39;
                          v45 = Entry;
                          *(_QWORD *)&Entry[v44 + 12] = v85 << *(_BYTE *)(*(_QWORD *)v78 + 488LL);
                          *(_QWORD *)&Entry[v44 + 14] = v81 << *(_BYTE *)(v43 + 488);
                          v46 = (struct _IRP *)((char *)v79 + (v81 << *(_BYTE *)(v43 + 488)));
                          v79 = v46;
                          v88 = v46;
                          if ( !v39 )
                          {
                            v63 = *(_QWORD *)&MasterIrp->Flags % (unsigned __int64)*(unsigned int *)(v43 + 356);
                            if ( v63 )
                            {
                              *((_QWORD *)Entry + 6) += v63;
                              v45 = Entry;
                              *((_QWORD *)Entry + 7) -= *(_QWORD *)&MasterIrp->Flags
                                                      % (unsigned __int64)*(unsigned int *)(v43 + 356);
                              v46 = (struct _IRP *)*((_QWORD *)Entry + 7);
                              v79 = v46;
                              v88 = v46;
                            }
                            else
                            {
                              v45 = Entry;
                              v46 = v79;
                            }
                          }
                          v47 = MasterIrp->AssociatedIrp.MasterIrp;
                          if ( v46 >= v47 )
                          {
                            *(_QWORD *)&v45[v44 + 14] += (char *)v47 - (char *)v46;
                            v79 = MasterIrp->AssociatedIrp.MasterIrp;
                            v88 = v79;
                          }
                          v83 = ++v39;
                        }
                        else
                        {
                          v43 = *(_QWORD *)v78;
                        }
                        if ( v39 >= 253 || !v42 && v39 > 0 || v79 >= MasterIrp->AssociatedIrp.MasterIrp )
                          break;
                        v40 = v81 + v80;
                        v80 = v40;
                      }
                      v64 = 16 * v39;
                      Entry[6] = v64;
                      if ( !v95 )
                      {
                        v37 = Entry;
                        OffloadIoContext = NtfsCreateOffloadIoContext(
                                             (_DWORD)v2,
                                             v86,
                                             v82,
                                             (_DWORD)Entry,
                                             (__int64)&v94,
                                             (__int64)&v76);
                        v48 = v76;
                        if ( (OffloadIoContext & 0x80000000) == 0 )
                        {
                          *((_DWORD *)v76 + 12) = v77;
                          *((_QWORD *)v48 + 7) = v87;
                          v2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
                          v74 = 0;
                          LODWORD(NumberOfBytes) = Entry[6] + 48;
                          v69 = NtfsDeviceIoControlAsync3(
                                  (int)a1,
                                  *(_QWORD *)(*(_QWORD *)v78 + 224LL),
                                  v78[0],
                                  v26,
                                  (__int64)NtfsAsyncOffloadReadCompletionRoutine,
                                  (__int64)v48,
                                  Entry,
                                  NumberOfBytes,
                                  536,
                                  3,
                                  0,
                                  0);
                          OffloadIoContext = v69;
                          if ( v69 < 0 )
                          {
                            *((_DWORD *)v48 + 2) = v69;
                            NtfsAsyncOffloadReadCompletionRoutine(0, 0, v48);
                          }
                        }
                        goto LABEL_183;
                      }
                      OffloadIoContext = NtfsDeviceIoControl2(
                                           (_DWORD)a1,
                                           *(_QWORD *)(v43 + 224),
                                           v43,
                                           2987012,
                                           (__int64)Entry,
                                           v64 + 48,
                                           536,
                                           3);
                      if ( (OffloadIoContext & 0x80000000) != 0 )
                      {
                        if ( OffloadIoContext == -1073741637 || OffloadIoContext == -1073740701 )
                          NtfsClearSupportedFeatures(*(_QWORD *)v78);
                        else
                          NtfsSetSupportedFeatures(*(_QWORD *)v78);
                      }
                      else
                      {
                        v65 = (struct _MDL *)*((_QWORD *)Entry + 1);
                        MasterIrp->MdlAddress = v65;
                        v66 = v77;
                        if ( (v77 & 1) != 0 && v65 < (struct _MDL *)v87 )
                        {
                          v66 = v77 & 0xFFFFFFFE;
                          v84 = v77 & 0xFFFFFFFE;
                        }
                        *(_DWORD *)&MasterIrp->Type = 528;
                        *(_DWORD *)(&MasterIrp->Size + 1) = v66;
                        v67 = 4;
                        v68 = v92;
                        do
                        {
                          *(_OWORD *)v68 = *(_OWORD *)v38;
                          *((_OWORD *)v68 + 1) = *((_OWORD *)v38 + 1);
                          *((_OWORD *)v68 + 2) = *((_OWORD *)v38 + 2);
                          *((_OWORD *)v68 + 3) = *((_OWORD *)v38 + 3);
                          *((_OWORD *)v68 + 4) = *((_OWORD *)v38 + 4);
                          *((_OWORD *)v68 + 5) = *((_OWORD *)v38 + 5);
                          *((_OWORD *)v68 + 6) = *((_OWORD *)v38 + 6);
                          *((_OWORD *)v68 + 7) = *((_OWORD *)v38 + 7);
                          v68 += 32;
                          v38 += 32;
                          --v67;
                        }
                        while ( v67 );
                        NtfsUpdateFileTimestampsForAccess(FileObject, v86, v82);
                      }
                      if ( NtfsStatusDebugFlags
                        && OffloadIoContext
                        && OffloadIoContext != 294
                        && OffloadIoContext - 298 > 1
                        && OffloadIoContext < 0xFFFFFFED
                        && OffloadIoContext != -1073741608
                        && OffloadIoContext != -1073741802
                        && OffloadIoContext != -1073741807
                        && OffloadIoContext + 2147483643 > 1
                        && OffloadIoContext != 259 )
                      {
                        v49 = 1213208;
                        goto LABEL_77;
                      }
                      goto LABEL_69;
                    }
                    OffloadIoContext = -1073700189;
                    if ( !NtfsStatusDebugFlags )
                      goto LABEL_69;
                    v49 = 1212965;
                  }
LABEL_77:
                  NtfsStatusTraceAndDebugInternal(0, OffloadIoContext, v49);
                  goto LABEL_69;
                }
              }
              FsRtlReleaseHeaderMutex(v8 + 120, v8 + 160);
              OffloadIoContext = -1073741807;
              goto LABEL_69;
            }
            OffloadIoContext = -1073741816;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_69;
            v50 = 1212735;
          }
LABEL_79:
          NtfsStatusTraceAndDebugInternal(0, OffloadIoContext, v50);
          goto LABEL_69;
        }
      }
      else
      {
        NtfsRaiseStatusInternal((_DWORD)a1, -1073741608, 0, 0, 1212652);
      }
      if ( *(_DWORD *)(v8 + 544) == (_DWORD)v26 )
      {
        OffloadIoContext = NtfsCacheCoherencyFlush(
                             (_DWORD)a1,
                             v24,
                             v8,
                             *(_QWORD *)p_Flags,
                             (__int64)MasterIrp->AssociatedIrp.MasterIrp,
                             v26,
                             *(_DWORD *)(v8 + 220) == (_DWORD)v26);
        if ( (OffloadIoContext & 0x80000000) != 0 )
          goto LABEL_69;
      }
      goto LABEL_38;
    }
    memset(MasterIrp, 0, 0x210u);
    *(_DWORD *)&MasterIrp->Type = 528;
    *(_BYTE *)p_Flags = -1;
    BYTE1(MasterIrp->Flags) = -1;
    HIBYTE(MasterIrp->Flags) = 1;
    *((_WORD *)&MasterIrp->Flags + 3) = -2047;
    v2->IoStatus.Information = 528;
    LOBYTE(v72) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v2, 0, v72, 1);
    return 0;
  }
  else
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225659LL, 1212462);
    LOBYTE(v12) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, v2, 3221225659LL, v12, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225659LL, 1212463);
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
