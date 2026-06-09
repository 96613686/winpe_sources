# NtfsOffloadWrite

- ea: `0x1400d5200`
- end: `0x1400d6796`
- name: `NtfsOffloadWrite`
- size: `5526`
- prototype: `__int64 __fastcall(__int64, PIRP Irp)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401f5890`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140009af0`
- `0x14000a0f0`
- `0x14000c290`
- `0x140010be0`
- `0x140014e74`
- `0x14001c910`
- `0x140021220`
- `0x140021590`
- `0x140031af8`
- `0x140049f70`
- `0x14004a110`
- `0x14004a1bc`
- `0x1400596c0`
- `0x1400d3a78`
- `0x1400d5018`
- `0x1400d5200`
- `0x14012d150`
- `0x14012f39c`
- `0x140159768`
- `0x140160be0`
- `0x1401be398`
- `0x1401c00e0`
- `0x1401e9e20`
- `0x14022b9dc`
- `0x1402332a8`
- `0x14023af00`
- `0x14024f868`
- `0x1402949c4`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x1400d5c77`
- `ntoskrnl!FsRtlCheckOplock` at `0x1400d5c77`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400d5abd`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1400d5abd`
- `ntoskrnl!IoGetRequestorProcess` at `0x1400d5ddb`
- `ntoskrnl!IoGetRequestorProcess` at `0x1400d5ddb`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x1400d5e0c`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x1400d5e0c`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400d5d56`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400d5d56`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400d5eac`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400d5ed7`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400d5f51`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400d5eac`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400d5ed7`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1400d5f51`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1400d5e89`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1400d5e89`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400d6628`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400d664b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c1b3b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c1b5b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400d6628`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400d664b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c1b3b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c1b5b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400d601f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400d601f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d5c4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d5c4e`

## pseudocode

```c
__int64 __fastcall NtfsOffloadWrite(__int64 a1, PIRP Irp)
{
  PIRP v2; // rsi
  __int64 v3; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  int v5; // r14d
  __int64 v6; // r9
  __int64 v7; // r13
  __int64 v8; // r8
  unsigned int v9; // r14d
  unsigned int v10; // r8d
  unsigned int v12; // ebx
  unsigned int v13; // r8d
  int v14; // ecx
  __int64 v15; // r15
  union _LARGE_INTEGER *MasterIrp; // r11
  unsigned __int64 v17; // rcx
  PLARGE_INTEGER v18; // r14
  unsigned __int64 QuadPart; // r9
  __int64 *v20; // rbx
  __int64 v21; // r8
  __int64 v22; // r10
  _QWORD *v23; // r11
  char v24; // r12
  __int64 v25; // rcx
  __int64 v26; // rdx
  int v27; // edx
  __int64 v28; // rcx
  PFILE_OBJECT v29; // r9
  char v30; // al
  unsigned __int64 v31; // rcx
  unsigned int v32; // r8d
  union _LARGE_INTEGER *v33; // r14
  int v34; // eax
  int v35; // eax
  LONGLONG v36; // r8
  struct _ERESOURCE *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rdx
  char v40; // al
  FILE_LOCK *v41; // rbx
  PEPROCESS ProcessId; // rax
  unsigned int v43; // r8d
  unsigned __int64 v44; // r8
  unsigned __int64 v45; // rcx
  union _LARGE_INTEGER *v46; // rax
  unsigned int v47; // r8d
  __int64 v48; // rdx
  LONGLONG *v49; // rcx
  union _LARGE_INTEGER *v50; // rax
  _OWORD *v51; // rcx
  int v52; // ebx
  __int64 v53; // r14
  char v54; // al
  __int64 v55; // r8
  unsigned __int64 v56; // rdx
  PLARGE_INTEGER v57; // r10
  unsigned __int64 v58; // rdx
  PLARGE_INTEGER v59; // rcx
  int v60; // ebx
  union _LARGE_INTEGER v61; // r14
  PLARGE_INTEGER v62; // r13
  LONGLONG v63; // r12
  __int64 v64; // r8
  char v65; // r12
  _DWORD *v66; // r14
  int v67; // r9d
  int v68; // eax
  unsigned int i; // eax
  __int64 v70; // rcx
  __int64 j; // rcx
  __int64 v72; // rax
  SIZE_T NumberOfBytes; // [rsp+38h] [rbp-F0h]
  union _LARGE_INTEGER *Entry; // [rsp+68h] [rbp-C0h]
  PFILE_OBJECT FileObject; // [rsp+78h] [rbp-B0h]
  int v76[2]; // [rsp+80h] [rbp-A8h] BYREF
  PLARGE_INTEGER Length; // [rsp+88h] [rbp-A0h]
  PLARGE_INTEGER StartingByte; // [rsp+90h] [rbp-98h]
  __int64 v79; // [rsp+98h] [rbp-90h] BYREF
  __int64 v80; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v81; // [rsp+A8h] [rbp-80h] BYREF
  PVOID v82; // [rsp+B0h] [rbp-78h] BYREF
  int v83; // [rsp+B8h] [rbp-70h]
  __int64 v84; // [rsp+C0h] [rbp-68h] BYREF
  _QWORD *v85; // [rsp+C8h] [rbp-60h] BYREF
  unsigned __int64 v86; // [rsp+D0h] [rbp-58h]
  LONGLONG *v87; // [rsp+D8h] [rbp-50h]
  __int64 v88; // [rsp+E0h] [rbp-48h] BYREF
  __int64 v89; // [rsp+E8h] [rbp-40h]
  char v90; // [rsp+140h] [rbp+18h] BYREF
  char v91; // [rsp+148h] [rbp+20h] BYREF

  v2 = Irp;
  v3 = a1;
  *(_QWORD *)v76 = 0;
  v85 = 0;
  v81 = 0;
  v79 = 0;
  v84 = 0;
  v80 = 0;
  v90 = 0;
  v82 = 0;
  v91 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Irp->IoStatus.Information = 0;
  FileObject = CurrentStackLocation->FileObject;
  v5 = NtfsDecodeFileObject(a1, (__int64)FileObject, v76, &v85, &v81, &v79, 0);
  LOBYTE(v6) = 1;
  v7 = *(_QWORD *)v76;
  if ( !(unsigned __int8)NtfsQuerySupportedFeatures(*(_QWORD *)v76, v3, v8, v6) )
  {
    v9 = -1073741637;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC00000BB, 0x12847Fu);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741637, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v9;
    v10 = 1213568;
LABEL_6:
    NtfsStatusTraceAndDebugInternal(0, v9, v10);
    return v9;
  }
  if ( v5 != 2 )
  {
    v12 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC000000D, 0x128489u);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1213578;
LABEL_19:
    NtfsStatusTraceAndDebugInternal(0, v12, v13);
    return v12;
  }
  v14 = *(_DWORD *)(v7 + 4);
  if ( (v14 & 0xA000021) != 1 )
  {
    if ( (v14 & 0x20) != 0 )
    {
      v12 = -1073741431;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v3, 0xC0000189, 0x12849Au);
      NtfsExtendedCompleteRequestInternal(v3, v2, -1073741431, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1213595;
      goto LABEL_19;
    }
    if ( (v14 & 0x8000001) != 1 )
    {
      v12 = -1073741202;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v3, 0xC000026E, 0x1284A6u);
      NtfsExtendedCompleteRequestInternal(v3, v2, -1073741202, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1213607;
      goto LABEL_19;
    }
    if ( (v14 & 0x2000000) != 0 )
    {
      v12 = -1073741662;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v3, 0xC00000A2, 0x1284B0u);
      NtfsExtendedCompleteRequestInternal(v3, v2, -1073741662, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1213617;
      goto LABEL_19;
    }
  }
  v15 = v81;
  if ( (*(_DWORD *)(v81 + 512) & 0x1000000) != 0 )
  {
    v9 = -1073741816;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC0000008, 0x1284BCu);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741816, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v9;
    v10 = 1213629;
    goto LABEL_6;
  }
  if ( v79 && (*(_DWORD *)(v79 + 4) & 0x2000) != 0 )
  {
    v12 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC000000D, 0x1284CAu);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1213643;
    goto LABEL_19;
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 0x220 )
  {
    v12 = -1073741789;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC0000023, 0x1284D6u);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741789, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1213655;
    goto LABEL_19;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x10 )
  {
    v12 = -1073741789;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC0000023, 0x1284DCu);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741789, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1213661;
    goto LABEL_19;
  }
  MasterIrp = (union _LARGE_INTEGER *)v2->AssociatedIrp.MasterIrp;
  v87 = (LONGLONG *)MasterIrp;
  v17 = *(unsigned int *)(v7 + 364);
  v18 = MasterIrp + 1;
  StartingByte = MasterIrp + 1;
  QuadPart = MasterIrp[1].QuadPart;
  if ( QuadPart % v17 )
  {
    v12 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC000000D, 0x1284EDu);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1213678;
    goto LABEL_19;
  }
  v20 = (__int64 *)&MasterIrp[2];
  Length = MasterIrp + 2;
  if ( MasterIrp[2].QuadPart % v17 )
  {
    v12 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC000000D, 0x1284F3u);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1213684;
    goto LABEL_19;
  }
  if ( MasterIrp[3].QuadPart % v17 )
  {
    v12 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC000000D, 0x1284F9u);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1213690;
    goto LABEL_19;
  }
  if ( MasterIrp->LowPart != 544 )
  {
    v12 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC000000D, 0x1284FFu);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1213696;
    goto LABEL_19;
  }
  if ( (int)RtlLongLongAdd(QuadPart, MasterIrp[2].QuadPart, (unsigned __int64 *)&v88) < 0 )
  {
    v12 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 0xC000000D, 0x12850Bu);
    NtfsExtendedCompleteRequestInternal(v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v12;
    v13 = 1213708;
    goto LABEL_19;
  }
  if ( v22 )
  {
    if ( *(_QWORD *)(v15 + 528) )
    {
      v12 = -1073700188;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v3, 0xC000A2A4, 0x128524u);
      NtfsExtendedCompleteRequestInternal(v3, v2, -1073700188, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v12;
      v13 = 1213733;
      goto LABEL_19;
    }
    Entry = 0;
    *(_QWORD *)v76 = 0;
    v24 = *(_BYTE *)(v3 + 12) & 1;
    if ( v79 )
      *(_DWORD *)(v3 + 272) = *(_DWORD *)(v79 + 100);
    LOBYTE(v21) = v24;
    v25 = v3;
    v26 = v15;
    if ( !FileObject->SectionObjectPointer->DataSectionObject )
    {
      LOBYTE(v28) = NtfsAcquirePagingShared(v3, v15, v21, 0);
      v90 = v28;
      v29 = FileObject;
      if ( !FileObject->SectionObjectPointer->DataSectionObject )
        goto LABEL_92;
      if ( (_BYTE)v28 )
      {
        NtfsReleasePagingResourcePriv(v28, v15);
        v90 = 0;
      }
      LOBYTE(v21) = v24;
      v26 = v15;
      v25 = v3;
    }
    v30 = NtfsAcquirePagingResourceExclusive(v25, v26, v21);
    v29 = FileObject;
    v90 = v30;
    LOBYTE(v28) = v30;
LABEL_92:
    if ( !(_BYTE)v28 )
      NtfsRaiseStatusInternal(v3, -1073741608, 0, 0, 1213781);
    v31 = *(unsigned __int16 *)(v15 + 460);
    if ( (_BYTE)v31 )
    {
      v12 = -1073700188;
      if ( !NtfsStatusDebugFlags )
      {
LABEL_98:
        v33 = 0;
        goto LABEL_250;
      }
      v32 = 1213792;
LABEL_97:
      NtfsStatusTraceAndDebugInternal(0, v12, v32);
      goto LABEL_98;
    }
    if ( (v31 & 0x4000) != 0 )
    {
      v12 = -1073700188;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213798;
      goto LABEL_97;
    }
    if ( (v31 & 0x8000u) != 0LL )
    {
      v12 = -1073700188;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213804;
      goto LABEL_97;
    }
    v34 = *(_DWORD *)(v15 + 512);
    if ( (v34 & 0x10000) != 0 )
    {
      v12 = -1073741202;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213814;
      goto LABEL_97;
    }
    if ( (v34 & 0x4000000) != 0 )
    {
      v12 = -1073741431;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213820;
      goto LABEL_97;
    }
    if ( v29->SectionObjectPointer->DataSectionObject )
    {
      if ( *(_DWORD *)(v15 + 216) )
      {
        v12 = -1073740747;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_98;
        v32 = 1213844;
        goto LABEL_97;
      }
      v12 = NtfsCacheCoherencyFlush(v3, v27, v15, v18->QuadPart, *v20, 1, *(_DWORD *)(v15 + 220) == 0);
      if ( (v12 & 0x80000000) != 0 )
        goto LABEL_98;
      if ( FileObject->PrivateCacheMap )
        CcUninitializeCacheMap(FileObject, 0, 0);
    }
    if ( v79 && (*(_DWORD *)(v79 + 4) & 0x8000) != 0 )
    {
      v12 = -1073741528;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213890;
      goto LABEL_97;
    }
    v35 = *(_DWORD *)(v15 + 512);
    if ( (v35 & 0x40) != 0 )
    {
      v12 = -1073741533;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213900;
      goto LABEL_97;
    }
    if ( (v35 & 0x10000) != 0 )
    {
      v12 = -1073741202;
    }
    else
    {
      v12 = (v35 & 0x1000000) != 0 ? 0xC0000008 : 0;
      v18 = StartingByte;
    }
    if ( (v12 & 0x80000000) != 0 )
    {
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213906;
      goto LABEL_97;
    }
    v36 = v18->QuadPart;
    v31 = *(unsigned int *)(v7 + 356);
    v88 = v18->QuadPart / v31;
    if ( v88 < 0 )
    {
      v12 = -1073741811;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213923;
      goto LABEL_97;
    }
    v31 = v36 + Length->QuadPart;
    if ( v31 > *(_QWORD *)(v7 + 7776) )
    {
      v12 = -1073741811;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213933;
      goto LABEL_97;
    }
    if ( *(_DWORD *)(v15 + 256) == 160 )
    {
      v12 = -1073700188;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v32 = 1213940;
      goto LABEL_97;
    }
    if ( (*(_DWORD *)(v15 + 200) & 0x20) == 0 )
    {
      NtfsAcquireResourceShared(v31, v15, 1u);
      NtfsUpdateScbFromAttribute(v3, v15, 0);
      if ( *(_WORD *)v15 == 1794 )
        v37 = (struct _ERESOURCE *)(*(_QWORD *)(v15 + 104) + 64LL);
      else
        v37 = *(struct _ERESOURCE **)(v15 + 8);
      ExReleaseResourceLite(v37);
    }
    v12 = FsRtlCheckOplock(
            (POPLOCK)(v15 + 88),
            v2,
            (PVOID)v3,
            NtfsOplockComplete,
            (POPLOCK_FS_PREPOST_IRP)NtfsPrePostIrp);
    if ( v12 )
    {
      v2 = 0;
      v3 = 0;
      if ( !NtfsStatusDebugFlags
        || ((v12 - 294) & 0xFFFFFFFA) == 0 && v12 != 295
        || v12 >= 0xFFFFFFED
        || v12 == -1073741608
        || v12 == -1073741802
        || v12 == -1073741807
        || v12 + 2147483643 <= 1
        || v12 == 259 )
      {
        goto LABEL_98;
      }
      v32 = 1213977;
      goto LABEL_97;
    }
    if ( !*(_BYTE *)(v15 + 5) )
    {
      if ( (*(_DWORD *)(*(_QWORD *)(v15 + 192) + 4LL) & 0x4000005) == 1
        && *(_WORD *)v15 == 1797
        && FsRtlOplockIsFastIoPossible((POPLOCK)(v15 + 88)) )
      {
        if ( *(_DWORD *)(v15 + 452)
          || (v38 = *(_QWORD *)(v15 + 584)) != 0 && *(_BYTE *)(v38 + 16)
          || (v39 = *(_QWORD *)(v15 + 192),
              (*(_DWORD *)(v39 + 4) & 0x2000000) != 0 || (*(_DWORD *)(v15 + 512) & 0x4000000) != 0)
          || *(_QWORD *)(v15 + 528)
          || *(_QWORD *)(v39 + 40) )
        {
          v40 = 2;
        }
        else
        {
          v40 = 1;
        }
      }
      else
      {
        v40 = 0;
      }
      *(_BYTE *)(v15 + 5) = v40;
    }
    if ( !*(_QWORD *)(v15 + 584)
      || (v41 = *(FILE_LOCK **)(v15 + 584),
          ProcessId = IoGetRequestorProcess(v2),
          FsRtlFastCheckLockForWrite(v41, StartingByte, Length, 0, FileObject, ProcessId)) )
    {
      NtfsPurgeFileRecordCache(v3);
      if ( (*(_DWORD *)(v15 + 200) & 8) != 0 )
      {
        v12 = -1073700188;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_175;
        v43 = 1214022;
        goto LABEL_174;
      }
      FsRtlAcquireHeaderMutex(v15 + 120, v15 + 160);
      v44 = StartingByte->QuadPart;
      if ( StartingByte->QuadPart >= *(_QWORD *)(v15 + 32) )
      {
        FsRtlReleaseHeaderMutex(v15 + 120, v15 + 160);
        v12 = -1073741807;
        goto LABEL_98;
      }
      v45 = *(_QWORD *)(v15 + 40);
      if ( v44 > v45 )
      {
        FsRtlReleaseHeaderMutex(v15 + 120, v15 + 160);
        v12 = -1073740750;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_175;
        v43 = 1214063;
        goto LABEL_174;
      }
      if ( v44 + Length->QuadPart > v45 )
      {
        if ( !v24 )
          v24 = 1;
        NtfsGetIoAtEof(v3, v15, v44, Length->QuadPart, v24, &v91);
      }
      FsRtlReleaseHeaderMutex(v15 + 120, v15 + 160);
      NtfsPreloadAllocationInternal(v3, 0x7FFFFFFFFFFFFFFFLL, 0);
      v12 = NtfsPrepareForCriticalIo(v3, (_DWORD)v2, v15, StartingByte->QuadPart, Length->QuadPart, 2);
      if ( (v12 & 0x80000000) == 0 )
      {
        v46 = (union _LARGE_INTEGER *)ExAllocateFromLookasideListEx(&NtfsFileOffloadLookasideList);
        v33 = v46;
        Entry = v46;
        if ( v46 )
        {
          memset(v46, 0, 0x1000u);
          v33->LowPart = 28;
          v48 = 4;
          v33->HighPart = 4;
          v33[1].HighPart = 32;
          v33[2].LowPart = 528;
          v49 = v87;
          v33[5].QuadPart = v87[3];
          v50 = v33 + 6;
          v51 = v49 + 4;
          do
          {
            *(_OWORD *)&v50->LowPart = *v51;
            *(_OWORD *)&v50[2].LowPart = v51[1];
            *(_OWORD *)&v50[4].LowPart = v51[2];
            *(_OWORD *)&v50[6].LowPart = v51[3];
            *(_OWORD *)&v50[8].LowPart = v51[4];
            *(_OWORD *)&v50[10].LowPart = v51[5];
            *(_OWORD *)&v50[12].LowPart = v51[6];
            *(_OWORD *)&v50[14].LowPart = v51[7];
            v50 += 16;
            v51 += 8;
            --v48;
          }
          while ( v48 );
          v33[2].HighPart = 560;
          v52 = 0;
          v83 = 0;
          v53 = v88;
          v89 = v88;
          NtfsPostUsnChangeWithOverrideOption(v3, v15, 1, 0, StartingByte->QuadPart, Length->QuadPart, 0);
          while ( 1 )
          {
            v54 = NtfsLookupNtfsMcbEntryWithSyncFlag(v15 + 400, v53, &v84, &v80, 0, 0, 0, 0);
            if ( !v54 && !v52 )
            {
              v12 = -1073741566;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_175;
              v43 = 1214237;
              goto LABEL_174;
            }
            if ( v54 )
            {
              if ( v84 == -1 )
              {
                v12 = -1073741566;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_175;
                v43 = 1214251;
                goto LABEL_174;
              }
              v55 = 2LL * v52;
              Entry[v55 + 70].QuadPart = v84 << *(_BYTE *)(v7 + 488);
              Entry[v55 + 71].QuadPart = v80 << *(_BYTE *)(v7 + 488);
              v56 = (v80 << *(_BYTE *)(v7 + 488)) + *(_QWORD *)v76;
              *(_QWORD *)v76 = v56;
              v86 = v56;
              if ( !v52 )
              {
                v57 = StartingByte;
                v58 = StartingByte->QuadPart % (unsigned __int64)*(unsigned int *)(v7 + 356);
                if ( v58 )
                {
                  Entry[70].QuadPart += v58;
                  Entry[71].QuadPart -= v57->QuadPart % (unsigned __int64)*(unsigned int *)(v7 + 356);
                  v56 = Entry[71].QuadPart;
                  *(_QWORD *)v76 = v56;
                  v86 = v56;
                }
                else
                {
                  v56 = *(_QWORD *)v76;
                }
              }
              v59 = Length;
              if ( v56 >= Length->QuadPart )
              {
                Entry[v55 + 71].QuadPart += Length->QuadPart - v56;
                *(union _LARGE_INTEGER *)v76 = *v59;
                v86 = *(_QWORD *)v76;
              }
              v83 = ++v52;
            }
            else
            {
              v59 = Length;
            }
            if ( v52 >= 221 || !v54 && v52 || *(_QWORD *)v76 >= v59->QuadPart )
              break;
            v53 += v80;
            v89 = v53;
          }
          v60 = 16 * v52;
          v33 = Entry;
          Entry[3].LowPart = v60;
          if ( !v24 )
          {
            v12 = NtfsCreateOffloadIoContext((__int64)v2, v85, v79, (__int64)Entry, &v90, &v82);
            if ( (v12 & 0x80000000) != 0 )
              goto LABEL_250;
            NtfsPrePostIrp((_DWORD *)v3, v2, v64);
            v65 = 0;
            LODWORD(NumberOfBytes) = Entry[3].LowPart + 560;
            v66 = v82;
            v68 = NtfsDeviceIoControlAsync3(
                    v3,
                    *(_QWORD *)(v7 + 224),
                    v7,
                    v67,
                    (__int64)NtfsAsyncOffloadWriteCompletionRoutine,
                    (__int64)v82,
                    Entry,
                    NumberOfBytes,
                    16,
                    3,
                    0,
                    0);
            v12 = v68;
            if ( v68 < 0 )
            {
              v66[2] = v68;
              NtfsAsyncOffloadWriteCompletionRoutine(0, 0, (__int64)v66);
            }
            v33 = Entry;
            goto LABEL_251;
          }
          v12 = NtfsDeviceIoControl2(v3, *(_QWORD *)(v7 + 224), v7, 2987012, (__int64)Entry, v60 + 560, 16, 3);
          if ( (v12 & 0x80000000) != 0 )
          {
            if ( v12 == -1073741637 || v12 == -1073740701 )
              NtfsClearSupportedFeatures(v7);
            else
              NtfsSetSupportedFeatures(v7);
            v33 = Entry;
          }
          else
          {
            v61 = Entry[1];
            v62 = StartingByte;
            v63 = StartingByte->QuadPart;
            NtfsUpdateFileTimestampsForModification(FileObject, v85, v79);
            if ( v91 )
            {
              NtfsUpdateScbFromFileObject(FileObject, v15, 0);
              NtfsOffloadUpdateScb(v3, v15, (__int64)FileObject, v61.QuadPart + v63);
            }
            v33 = Entry;
            *v62 = Entry[1];
            v31 = (unsigned __int64)v87;
            *v87 = 16;
          }
          if ( NtfsStatusDebugFlags )
          {
            if ( v12 )
            {
              if ( v12 != 294 )
              {
                v31 = 1;
                if ( v12 - 298 > 1
                  && v12 < 0xFFFFFFED
                  && v12 != -1073741608
                  && v12 != -1073741802
                  && v12 != -1073741807
                  && v12 + 2147483643 > 1
                  && v12 != 259 )
                {
                  v47 = 1214404;
                  goto LABEL_199;
                }
              }
            }
          }
        }
        else
        {
          LOBYTE(v31) = NtfsStatusDebugFlags;
          v12 = -1073741670;
          if ( NtfsStatusDebugFlags )
          {
            v47 = 1214146;
LABEL_199:
            NtfsStatusTraceAndDebugInternal(0, v12, v47);
          }
        }
LABEL_250:
        v65 = 1;
LABEL_251:
        if ( v65 )
        {
          if ( v90 )
          {
            if ( v3 && *(_DWORD *)(v3 + 28) )
            {
              for ( i = 0; i < 2; ++i )
              {
                v70 = *(_QWORD *)(v3 + 8LL * i + 48);
                if ( !v70 || v70 == *(_QWORD *)(v15 + 184) )
                {
                  *(_QWORD *)(v3 + 8LL * i + 48) = *(_QWORD *)(v15 + 184);
                  break;
                }
              }
            }
            else
            {
              NtfsReleasePagingResourcePriv(v31, *(_QWORD *)(v15 + 184));
              if ( v3 )
              {
                for ( j = 0; j != 2; ++j )
                {
                  if ( *(_QWORD *)(v3 + 8 * j + 48) == *(_QWORD *)(v15 + 184) )
                    *(_QWORD *)(v3 + 8 * j + 48) = 0;
                }
              }
            }
          }
          if ( v33 )
            ExFreeToLookasideListEx(&NtfsFileOffloadLookasideList, v33);
          if ( v82 )
            ExFreeToLookasideListEx(&NtfsOffloadIoContextLookasideList, v82);
        }
        if ( v2 )
        {
          if ( v65 )
          {
            v72 = 0;
            if ( (v12 & 0x80000000) == 0 )
              v72 = 16;
            v2->IoStatus.Information = v72;
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
          NtfsStatusTraceAndDebugInternal(v3, v12, 0x12883Au);
        }
        NtfsExtendedCompleteRequestInternal(v3, v2, v12, v2 != 0, (v12 & 0x80000000) == 0);
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
        v13 = 1214524;
        goto LABEL_19;
      }
      if ( NtfsStatusDebugFlags
        && v12 < 0xFFFFFFED
        && v12 != -1073741802
        && v12 != -1073741807
        && v12 + 2147483643 > 1
        && v12 != -1073741608 )
      {
        v43 = 1214133;
        goto LABEL_174;
      }
    }
    else
    {
      v12 = -1073741740;
      if ( NtfsStatusDebugFlags )
      {
        v43 = 1214006;
LABEL_174:
        NtfsStatusTraceAndDebugInternal(0, v12, v43);
      }
    }
LABEL_175:
    v33 = Entry;
    goto LABEL_250;
  }
  *v23 = 16;
  v18->QuadPart = 0;
  v2->IoStatus.Information = 16;
  NtfsExtendedCompleteRequestInternal(v3, v2, 0, v2 != 0, 1);
  return 0;
}

```

## disassembly

```asm
0x1400d5200  mov     r11, rsp
0x1400d5203  mov     [r11+8], rcx
0x1400d5207  push    rbx
0x1400d5208  push    rsi
0x1400d5209  push    rdi
0x1400d520a  push    r12
0x1400d520c  push    r13
0x1400d520e  push    r14
0x1400d5210  push    r15
0x1400d5212  sub     rsp, 0F0h
0x1400d5219  mov     rsi, rdx
0x1400d521c  mov     rdi, rcx
0x1400d521f  xor     r12d, r12d
0x1400d5222  mov     [r11-0A8h], r12
0x1400d5229  mov     [r11-60h], r12
0x1400d522d  mov     [r11-80h], r12
0x1400d5231  mov     [r11-90h], r12
0x1400d5238  mov     [r11-68h], r12
0x1400d523c  mov     [r11-88h], r12
0x1400d5243  mov     [r11+18h], r12b
0x1400d5247  mov     [r11-78h], r12
0x1400d524b  mov     [r11+20h], r12b
0x1400d524f  mov     rbx, [rdx+0B8h]
0x1400d5256  mov     [rdx+38h], r12
0x1400d525a  mov     rax, [rbx+30h]
0x1400d525e  mov     [rsp+128h+FileObject], rax
0x1400d5263  mov     byte ptr [rsp+128h+Src], r12b
0x1400d5268  lea     rcx, [r11-90h]
0x1400d526f  mov     [rsp+128h+ProcessId], rcx
0x1400d5274  lea     rcx, [r11-80h]
0x1400d5278  mov     [rsp+128h+PostIrpRoutine], rcx
0x1400d527d  lea     r9, [r11-60h]
0x1400d5281  lea     r8, [r11-0A8h]
0x1400d5288  mov     rdx, rax
0x1400d528b  mov     rcx, rdi
0x1400d528e  call    NtfsDecodeFileObject
0x1400d5293  mov     r14d, eax
0x1400d5296  lea     r15d, [r12+1]
0x1400d529b  mov     r9b, r15b
0x1400d529e  mov     rdx, rdi
0x1400d52a1  mov     r13, qword ptr [rsp+128h+var_A8]
0x1400d52a9  mov     rcx, r13
0x1400d52ac  call    NtfsQuerySupportedFeatures
0x1400d52b1  test    al, al
0x1400d52b3  jnz     short loc_1400D5313
0x1400d52b5  mov     al, cs:NtfsStatusDebugFlags
0x1400d52bb  mov     r14d, 0C00000BBh
0x1400d52c1  test    al, al
0x1400d52c3  jz      short loc_1400D52D6
0x1400d52c5  mov     r8d, 12847Fh
0x1400d52cb  mov     edx, r14d
0x1400d52ce  mov     rcx, rdi
0x1400d52d1  call    NtfsStatusTraceAndDebugInternal
0x1400d52d6  test    rsi, rsi
0x1400d52d9  setnz   r9b
0x1400d52dd  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d52e2  mov     r8d, r14d
0x1400d52e5  mov     rdx, rsi
0x1400d52e8  mov     rcx, rdi
0x1400d52eb  call    NtfsExtendedCompleteRequestInternal
0x1400d52f0  mov     cl, cs:NtfsStatusDebugFlags
0x1400d52f6  test    cl, cl
0x1400d52f8  jz      short loc_1400D530A
0x1400d52fa  mov     r8d, 128480h
0x1400d5300  mov     edx, r14d
0x1400d5303  xor     ecx, ecx
0x1400d5305  call    NtfsStatusTraceAndDebugInternal
0x1400d530a  mov     eax, r14d
0x1400d530d  jmp     loc_1400D6783
0x1400d5313  cmp     r14d, 2
0x1400d5317  jz      short loc_1400D5364
0x1400d5319  mov     al, cs:NtfsStatusDebugFlags
0x1400d531f  mov     ebx, 0C000000Dh
0x1400d5324  test    al, al
0x1400d5326  jz      short loc_1400D5338
0x1400d5328  mov     r8d, 128489h
0x1400d532e  mov     edx, ebx
0x1400d5330  mov     rcx, rdi
0x1400d5333  call    NtfsStatusTraceAndDebugInternal
0x1400d5338  test    rsi, rsi
0x1400d533b  setnz   r9b
0x1400d533f  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d5344  mov     r8d, ebx
0x1400d5347  mov     rdx, rsi
0x1400d534a  mov     rcx, rdi
0x1400d534d  call    NtfsExtendedCompleteRequestInternal
0x1400d5352  mov     al, cs:NtfsStatusDebugFlags
0x1400d5358  test    al, al
0x1400d535a  jz      short loc_1400D53CF
0x1400d535c  mov     r8d, 12848Ah
0x1400d5362  jmp     short loc_1400D53C6
0x1400d5364  mov     ecx, [r13+4]
0x1400d5368  mov     eax, ecx
0x1400d536a  and     eax, 0A000021h
0x1400d536f  cmp     eax, r15d
0x1400d5372  jz      loc_1400D5489
0x1400d5378  test    cl, 20h
0x1400d537b  jz      short loc_1400D53D6
0x1400d537d  mov     al, cs:NtfsStatusDebugFlags
0x1400d5383  mov     ebx, 0C0000189h
0x1400d5388  test    al, al
0x1400d538a  jz      short loc_1400D539C
0x1400d538c  mov     r8d, 12849Ah
0x1400d5392  mov     edx, ebx
0x1400d5394  mov     rcx, rdi
0x1400d5397  call    NtfsStatusTraceAndDebugInternal
0x1400d539c  test    rsi, rsi
0x1400d539f  setnz   r9b
0x1400d53a3  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d53a8  mov     r8d, ebx
0x1400d53ab  mov     rdx, rsi
0x1400d53ae  mov     rcx, rdi
0x1400d53b1  call    NtfsExtendedCompleteRequestInternal
0x1400d53b6  mov     al, cs:NtfsStatusDebugFlags
0x1400d53bc  test    al, al
0x1400d53be  jz      short loc_1400D53CF
0x1400d53c0  mov     r8d, 12849Bh
0x1400d53c6  mov     edx, ebx
0x1400d53c8  xor     ecx, ecx
0x1400d53ca  call    NtfsStatusTraceAndDebugInternal
0x1400d53cf  mov     eax, ebx
0x1400d53d1  jmp     loc_1400D6783
0x1400d53d6  mov     eax, ecx
0x1400d53d8  and     eax, 8000001h
0x1400d53dd  cmp     eax, r15d
0x1400d53e0  jnz     short loc_1400D5437
0x1400d53e2  bt      ecx, 19h
0x1400d53e6  jnb     loc_1400D5489
0x1400d53ec  mov     al, cs:NtfsStatusDebugFlags
0x1400d53f2  mov     ebx, 0C00000A2h
0x1400d53f7  test    al, al
0x1400d53f9  jz      short loc_1400D540B
0x1400d53fb  mov     r8d, 1284B0h
0x1400d5401  mov     edx, ebx
0x1400d5403  mov     rcx, rdi
0x1400d5406  call    NtfsStatusTraceAndDebugInternal
0x1400d540b  test    rsi, rsi
0x1400d540e  setnz   r9b
0x1400d5412  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d5417  mov     r8d, ebx
0x1400d541a  mov     rdx, rsi
0x1400d541d  mov     rcx, rdi
0x1400d5420  call    NtfsExtendedCompleteRequestInternal
0x1400d5425  mov     cl, cs:NtfsStatusDebugFlags
0x1400d542b  test    cl, cl
0x1400d542d  jz      short loc_1400D53CF
0x1400d542f  mov     r8d, 1284B1h
0x1400d5435  jmp     short loc_1400D53C6
0x1400d5437  mov     al, cs:NtfsStatusDebugFlags
0x1400d543d  mov     ebx, 0C000026Eh
0x1400d5442  test    al, al
0x1400d5444  jz      short loc_1400D5456
0x1400d5446  mov     r8d, 1284A6h
0x1400d544c  mov     edx, ebx
0x1400d544e  mov     rcx, rdi
0x1400d5451  call    NtfsStatusTraceAndDebugInternal
0x1400d5456  test    rsi, rsi
0x1400d5459  setnz   r9b
0x1400d545d  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d5462  mov     r8d, ebx
0x1400d5465  mov     rdx, rsi
0x1400d5468  mov     rcx, rdi
0x1400d546b  call    NtfsExtendedCompleteRequestInternal
0x1400d5470  mov     al, cs:NtfsStatusDebugFlags
0x1400d5476  test    al, al
0x1400d5478  jz      loc_1400D53CF
0x1400d547e  mov     r8d, 1284A7h
0x1400d5484  jmp     loc_1400D53C6
0x1400d5489  mov     r15, [rsp+128h+var_80]
0x1400d5491  test    dword ptr [r15+200h], 1000000h
0x1400d549c  jz      short loc_1400D54F2
0x1400d549e  mov     al, cs:NtfsStatusDebugFlags
0x1400d54a4  mov     r14d, 0C0000008h
0x1400d54aa  test    al, al
0x1400d54ac  jz      short loc_1400D54BF
0x1400d54ae  mov     r8d, 1284BCh
0x1400d54b4  mov     edx, r14d
0x1400d54b7  mov     rcx, rdi
0x1400d54ba  call    NtfsStatusTraceAndDebugInternal
0x1400d54bf  test    rsi, rsi
0x1400d54c2  setnz   r9b
0x1400d54c6  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d54cb  mov     r8d, r14d
0x1400d54ce  mov     rdx, rsi
0x1400d54d1  mov     rcx, rdi
0x1400d54d4  call    NtfsExtendedCompleteRequestInternal
0x1400d54d9  mov     cl, cs:NtfsStatusDebugFlags
0x1400d54df  test    cl, cl
0x1400d54e1  jz      loc_1400D530A
0x1400d54e7  mov     r8d, 1284BDh
0x1400d54ed  jmp     loc_1400D5300
0x1400d54f2  mov     r8, [rsp+128h+var_90]
0x1400d54fa  test    r8, r8
0x1400d54fd  jz      short loc_1400D555B
0x1400d54ff  test    dword ptr [r8+4], 2000h
0x1400d5507  jz      short loc_1400D555B
0x1400d5509  mov     al, cs:NtfsStatusDebugFlags
0x1400d550f  mov     ebx, 0C000000Dh
0x1400d5514  test    al, al
0x1400d5516  jz      short loc_1400D5528
0x1400d5518  mov     r8d, 1284CAh
0x1400d551e  mov     edx, ebx
0x1400d5520  mov     rcx, rdi
0x1400d5523  call    NtfsStatusTraceAndDebugInternal
0x1400d5528  test    rsi, rsi
0x1400d552b  setnz   r9b
0x1400d552f  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d5534  mov     r8d, ebx
0x1400d5537  mov     rdx, rsi
0x1400d553a  mov     rcx, rdi
0x1400d553d  call    NtfsExtendedCompleteRequestInternal
0x1400d5542  mov     al, cs:NtfsStatusDebugFlags
0x1400d5548  test    al, al
0x1400d554a  jz      loc_1400D53CF
0x1400d5550  mov     r8d, 1284CBh
0x1400d5556  jmp     loc_1400D53C6
0x1400d555b  mov     r8d, 220h
0x1400d5561  cmp     [rbx+10h], r8d
0x1400d5565  jnb     short loc_1400D55B9
0x1400d5567  mov     al, cs:NtfsStatusDebugFlags
0x1400d556d  mov     ebx, 0C0000023h
0x1400d5572  test    al, al
0x1400d5574  jz      short loc_1400D5586
0x1400d5576  mov     r8d, 1284D6h
0x1400d557c  mov     edx, ebx
0x1400d557e  mov     rcx, rdi
0x1400d5581  call    NtfsStatusTraceAndDebugInternal
0x1400d5586  test    rsi, rsi
0x1400d5589  setnz   r9b
0x1400d558d  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d5592  mov     r8d, ebx
0x1400d5595  mov     rdx, rsi
0x1400d5598  mov     rcx, rdi
0x1400d559b  call    NtfsExtendedCompleteRequestInternal
0x1400d55a0  mov     al, cs:NtfsStatusDebugFlags
0x1400d55a6  test    al, al
0x1400d55a8  jz      loc_1400D53CF
0x1400d55ae  mov     r8d, 1284D7h
0x1400d55b4  jmp     loc_1400D53C6
0x1400d55b9  cmp     dword ptr [rbx+8], 10h
0x1400d55bd  jnb     short loc_1400D5611
0x1400d55bf  mov     al, cs:NtfsStatusDebugFlags
0x1400d55c5  mov     ebx, 0C0000023h
0x1400d55ca  test    al, al
0x1400d55cc  jz      short loc_1400D55DE
0x1400d55ce  mov     r8d, 1284DCh
0x1400d55d4  mov     edx, ebx
0x1400d55d6  mov     rcx, rdi
0x1400d55d9  call    NtfsStatusTraceAndDebugInternal
0x1400d55de  test    rsi, rsi
0x1400d55e1  setnz   r9b
0x1400d55e5  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d55ea  mov     r8d, ebx
0x1400d55ed  mov     rdx, rsi
0x1400d55f0  mov     rcx, rdi
0x1400d55f3  call    NtfsExtendedCompleteRequestInternal
0x1400d55f8  mov     cl, cs:NtfsStatusDebugFlags
0x1400d55fe  test    cl, cl
0x1400d5600  jz      loc_1400D53CF
0x1400d5606  mov     r8d, 1284DDh
0x1400d560c  jmp     loc_1400D53C6
0x1400d5611  mov     r11, [rsi+18h]
0x1400d5615  mov     [rsp+128h+var_50], r11
0x1400d561d  mov     ecx, [r13+16Ch]
0x1400d5624  lea     r14, [r11+8]
0x1400d5628  mov     [rsp+128h+StartingByte], r14
0x1400d5630  mov     r9, [r14]
0x1400d5633  xor     edx, edx
0x1400d5635  mov     rax, r9
0x1400d5638  div     rcx
0x1400d563b  test    rdx, rdx
0x1400d563e  jz      short loc_1400D5692
0x1400d5640  mov     al, cs:NtfsStatusDebugFlags
0x1400d5646  mov     ebx, 0C000000Dh
0x1400d564b  test    al, al
0x1400d564d  jz      short loc_1400D565F
0x1400d564f  mov     r8d, 1284EDh
0x1400d5655  mov     edx, ebx
0x1400d5657  mov     rcx, rdi
0x1400d565a  call    NtfsStatusTraceAndDebugInternal
0x1400d565f  test    rsi, rsi
0x1400d5662  setnz   r9b
0x1400d5666  mov     dword ptr [rsp+128h+PostIrpRoutine], r12d
0x1400d566b  mov     r8d, ebx
0x1400d566e  mov     rdx, rsi
0x1400d5671  mov     rcx, rdi
0x1400d5674  call    NtfsExtendedCompleteRequestInternal
0x1400d5679  mov     al, cs:NtfsStatusDebugFlags
0x1400d567f  test    al, al
0x1400d5681  jz      loc_1400D53CF
0x1400d5687  mov     r8d, 1284EEh
0x1400d568d  jmp     loc_1400D53C6
0x1400d5692  lea     rbx, [r11+10h]
0x1400d5696  mov     [rsp+128h+Length], rbx
0x1400d569e  mov     r10, [rbx]
0x1400d56a1  xor     edx, edx
0x1400d56a3  mov     rax, r10
0x1400d56a6  div     rcx
0x1400d56a9  test    rdx, rdx
0x1400d56ac  jz      short loc_1400D5700
  ... truncated ...
```
