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

- `0x1401f58e0`

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
- `0x140049fe0`
- `0x14004a180`
- `0x14004a22c`
- `0x140059740`
- `0x1400d3a78`
- `0x1400d5018`
- `0x1400d5200`
- `0x14012d1a0`
- `0x14012f3ec`
- `0x1401597b8`
- `0x140160c30`
- `0x1401be3e8`
- `0x1401c0130`
- `0x1401e9e70`
- `0x14022ba2c`
- `0x1402332f8`
- `0x14023af50`
- `0x14024f8b8`
- `0x140294a14`

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
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c1b8b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c1bab`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400d6628`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400d664b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c1b8b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c1bab`
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
  __int64 v9; // r9
  unsigned int v10; // r14d
  __int64 v11; // r8
  unsigned int OffloadIoContext; // ebx
  __int64 v14; // r8
  int v15; // ecx
  __int64 v16; // r15
  union _LARGE_INTEGER *MasterIrp; // r11
  unsigned __int64 v18; // rcx
  PLARGE_INTEGER v19; // r14
  union _LARGE_INTEGER v20; // r9
  __int64 *v21; // rbx
  __int64 v22; // r8
  PFILE_OBJECT v23; // r9
  __int64 v24; // r10
  _QWORD *v25; // r11
  char v26; // r12
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // edx
  __int64 v30; // rcx
  PVOID v31; // r10
  char v32; // al
  unsigned __int64 v33; // rcx
  __int64 v34; // r8
  union _LARGE_INTEGER *v35; // r14
  int v36; // eax
  int v37; // eax
  LONGLONG QuadPart; // r8
  struct _ERESOURCE *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdx
  char v42; // al
  FILE_LOCK *v43; // rbx
  PEPROCESS ProcessId; // rax
  __int64 v45; // r8
  __int64 v46; // r8
  unsigned __int64 v47; // r8
  unsigned __int64 v48; // rcx
  union _LARGE_INTEGER *v49; // rax
  __int64 v50; // r8
  __int64 v51; // rdx
  LONGLONG *v52; // rcx
  union _LARGE_INTEGER *v53; // rax
  _OWORD *v54; // rcx
  int v55; // ebx
  __int64 v56; // r14
  char v57; // al
  __int64 v58; // r8
  unsigned __int64 v59; // rdx
  PLARGE_INTEGER v60; // r10
  unsigned __int64 v61; // rdx
  PLARGE_INTEGER v62; // rcx
  int v63; // ebx
  union _LARGE_INTEGER v64; // r14
  PLARGE_INTEGER v65; // r13
  LONGLONG v66; // r12
  char v67; // r12
  _DWORD *v68; // r14
  int v69; // r9d
  int v70; // eax
  unsigned int i; // eax
  __int64 v72; // rcx
  __int64 j; // rcx
  __int64 v74; // rax
  SIZE_T NumberOfBytes; // [rsp+38h] [rbp-F0h]
  union _LARGE_INTEGER *Entry; // [rsp+68h] [rbp-C0h]
  PFILE_OBJECT FileObject; // [rsp+78h] [rbp-B0h]
  int v78[2]; // [rsp+80h] [rbp-A8h] BYREF
  PLARGE_INTEGER Length; // [rsp+88h] [rbp-A0h]
  PLARGE_INTEGER StartingByte; // [rsp+90h] [rbp-98h]
  __int64 v81; // [rsp+98h] [rbp-90h] BYREF
  __int64 v82; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v83; // [rsp+A8h] [rbp-80h] BYREF
  PVOID v84; // [rsp+B0h] [rbp-78h] BYREF
  int v85; // [rsp+B8h] [rbp-70h]
  __int64 v86; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v87; // [rsp+C8h] [rbp-60h] BYREF
  unsigned __int64 v88; // [rsp+D0h] [rbp-58h]
  LONGLONG *v89; // [rsp+D8h] [rbp-50h]
  __int64 v90; // [rsp+E0h] [rbp-48h] BYREF
  __int64 v91; // [rsp+E8h] [rbp-40h]
  char v92; // [rsp+140h] [rbp+18h] BYREF
  char v93; // [rsp+148h] [rbp+20h] BYREF

  v2 = Irp;
  v3 = a1;
  *(_QWORD *)v78 = 0;
  v87 = 0;
  v83 = 0;
  v81 = 0;
  v86 = 0;
  v82 = 0;
  v92 = 0;
  v84 = 0;
  v93 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Irp->IoStatus.Information = 0;
  FileObject = CurrentStackLocation->FileObject;
  v5 = NtfsDecodeFileObject(
         a1,
         (_DWORD)FileObject,
         (unsigned int)v78,
         (unsigned int)&v87,
         (__int64)&v83,
         (__int64)&v81,
         0);
  LOBYTE(v6) = 1;
  v7 = *(_QWORD *)v78;
  if ( !(unsigned __int8)NtfsQuerySupportedFeatures(*(_QWORD *)v78, v3, v8, v6) )
  {
    v10 = -1073741637;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225659LL, 1213567);
    LOBYTE(v9) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(v3, v2, 3221225659LL, v9, 0);
    if ( !NtfsStatusDebugFlags )
      return v10;
    v11 = 1213568;
LABEL_6:
    NtfsStatusTraceAndDebugInternal(0, v10, v11);
    return v10;
  }
  if ( v5 != 2 )
  {
    OffloadIoContext = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225485LL, 1213577);
    LOBYTE(v9) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(v3, v2, 3221225485LL, v9, 0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1213578;
LABEL_19:
    NtfsStatusTraceAndDebugInternal(0, OffloadIoContext, v14);
    return OffloadIoContext;
  }
  v15 = *(_DWORD *)(v7 + 4);
  if ( (v15 & 0xA000021) != 1 )
  {
    if ( (v15 & 0x20) != 0 )
    {
      OffloadIoContext = -1073741431;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v3, 3221225865LL, 1213594);
      LOBYTE(v9) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(v3, v2, 3221225865LL, v9, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1213595;
      goto LABEL_19;
    }
    if ( (v15 & 0x8000001) != 1 )
    {
      OffloadIoContext = -1073741202;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v3, 3221226094LL, 1213606);
      LOBYTE(v9) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(v3, v2, 3221226094LL, v9, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1213607;
      goto LABEL_19;
    }
    if ( (v15 & 0x2000000) != 0 )
    {
      OffloadIoContext = -1073741662;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v3, 3221225634LL, 1213616);
      LOBYTE(v9) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(v3, v2, 3221225634LL, v9, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1213617;
      goto LABEL_19;
    }
  }
  v16 = v83;
  if ( (*(_DWORD *)(v83 + 512) & 0x1000000) != 0 )
  {
    v10 = -1073741816;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225480LL, 1213628);
    LOBYTE(v9) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(v3, v2, 3221225480LL, v9, 0);
    if ( !NtfsStatusDebugFlags )
      return v10;
    v11 = 1213629;
    goto LABEL_6;
  }
  if ( v81 && (*(_DWORD *)(v81 + 4) & 0x2000) != 0 )
  {
    OffloadIoContext = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225485LL, 1213642);
    LOBYTE(v9) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(v3, v2, 3221225485LL, v9, 0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1213643;
    goto LABEL_19;
  }
  if ( CurrentStackLocation->Parameters.Create.Options < 0x220 )
  {
    OffloadIoContext = -1073741789;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225507LL, 1213654);
    LOBYTE(v9) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(v3, v2, 3221225507LL, v9, 0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1213655;
    goto LABEL_19;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x10 )
  {
    OffloadIoContext = -1073741789;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225507LL, 1213660);
    LOBYTE(v9) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(v3, v2, 3221225507LL, v9, 0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1213661;
    goto LABEL_19;
  }
  MasterIrp = (union _LARGE_INTEGER *)v2->AssociatedIrp.MasterIrp;
  v89 = (LONGLONG *)MasterIrp;
  v18 = *(unsigned int *)(v7 + 364);
  v19 = MasterIrp + 1;
  StartingByte = MasterIrp + 1;
  v20 = MasterIrp[1];
  if ( v20.QuadPart % v18 )
  {
    OffloadIoContext = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225485LL, 1213677);
    LOBYTE(v20.LowPart) = v2 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v3,
      v2,
      3221225485LL,
      (union _LARGE_INTEGER)v20.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1213678;
    goto LABEL_19;
  }
  v21 = (__int64 *)&MasterIrp[2];
  Length = MasterIrp + 2;
  if ( MasterIrp[2].QuadPart % v18 )
  {
    OffloadIoContext = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225485LL, 1213683);
    LOBYTE(v20.LowPart) = v2 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v3,
      v2,
      3221225485LL,
      (union _LARGE_INTEGER)v20.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1213684;
    goto LABEL_19;
  }
  if ( MasterIrp[3].QuadPart % v18 )
  {
    OffloadIoContext = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225485LL, 1213689);
    LOBYTE(v20.LowPart) = v2 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v3,
      v2,
      3221225485LL,
      (union _LARGE_INTEGER)v20.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1213690;
    goto LABEL_19;
  }
  if ( MasterIrp->LowPart != 544 )
  {
    OffloadIoContext = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225485LL, 1213695);
    LOBYTE(v20.LowPart) = v2 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v3,
      v2,
      3221225485LL,
      (union _LARGE_INTEGER)v20.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1213696;
    goto LABEL_19;
  }
  if ( (int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RtlLongLongAdd)(
              (union _LARGE_INTEGER)v20.QuadPart,
              (union _LARGE_INTEGER)MasterIrp[2].QuadPart,
              &v90) < 0 )
  {
    OffloadIoContext = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v3, 3221225485LL, 1213707);
    LOBYTE(v23) = v2 != 0;
    NtfsExtendedCompleteRequestInternal(v3, v2, 3221225485LL, v23, 0);
    if ( !NtfsStatusDebugFlags )
      return OffloadIoContext;
    v14 = 1213708;
    goto LABEL_19;
  }
  if ( v24 )
  {
    if ( *(_QWORD *)(v16 + 528) )
    {
      OffloadIoContext = -1073700188;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v3, 3221267108LL, 1213732);
      LOBYTE(v23) = v2 != 0;
      NtfsExtendedCompleteRequestInternal(v3, v2, 3221267108LL, v23, 0);
      if ( !NtfsStatusDebugFlags )
        return OffloadIoContext;
      v14 = 1213733;
      goto LABEL_19;
    }
    Entry = 0;
    *(_QWORD *)v78 = 0;
    v26 = *(_BYTE *)(v3 + 12) & 1;
    if ( v81 )
      *(_DWORD *)(v3 + 272) = *(_DWORD *)(v81 + 100);
    LOBYTE(v22) = v26;
    v27 = v3;
    v28 = v16;
    if ( !FileObject->SectionObjectPointer->DataSectionObject )
    {
      LOBYTE(v30) = NtfsAcquirePagingShared(v3, v16, v22, 0);
      v92 = v30;
      v23 = FileObject;
      v31 = 0;
      if ( !FileObject->SectionObjectPointer->DataSectionObject )
        goto LABEL_92;
      if ( (_BYTE)v30 )
      {
        NtfsReleasePagingResourcePriv(v30, v16);
        v92 = 0;
      }
      LOBYTE(v22) = v26;
      v28 = v16;
      v27 = v3;
    }
    v32 = NtfsAcquirePagingResourceExclusive(v27, v28, v22, v23);
    v31 = 0;
    v23 = FileObject;
    v92 = v32;
    LOBYTE(v30) = v32;
LABEL_92:
    if ( !(_BYTE)v30 )
      NtfsRaiseStatusInternal(v3, -1073741608, 0, 0, 1213781);
    v33 = *(unsigned __int16 *)(v16 + 460);
    if ( (_BYTE)v33 )
    {
      OffloadIoContext = -1073700188;
      if ( !NtfsStatusDebugFlags )
      {
LABEL_98:
        v35 = 0;
        goto LABEL_250;
      }
      v34 = 1213792;
LABEL_97:
      NtfsStatusTraceAndDebugInternal(0, OffloadIoContext, v34);
      goto LABEL_98;
    }
    if ( (v33 & 0x4000) != 0 )
    {
      OffloadIoContext = -1073700188;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213798;
      goto LABEL_97;
    }
    if ( (v33 & 0x8000u) != 0LL )
    {
      OffloadIoContext = -1073700188;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213804;
      goto LABEL_97;
    }
    v36 = *(_DWORD *)(v16 + 512);
    if ( (v36 & 0x10000) != 0 )
    {
      OffloadIoContext = -1073741202;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213814;
      goto LABEL_97;
    }
    if ( (v36 & 0x4000000) != 0 )
    {
      OffloadIoContext = -1073741431;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213820;
      goto LABEL_97;
    }
    if ( v23->SectionObjectPointer->DataSectionObject != v31 )
    {
      if ( *(_DWORD *)(v16 + 216) != (_DWORD)v31 )
      {
        OffloadIoContext = -1073740747;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_98;
        v34 = 1213844;
        goto LABEL_97;
      }
      OffloadIoContext = NtfsCacheCoherencyFlush(
                           v3,
                           v29,
                           v16,
                           v19->QuadPart,
                           *v21,
                           1,
                           *(_DWORD *)(v16 + 220) == (_DWORD)v31);
      if ( (OffloadIoContext & 0x80000000) != 0 )
        goto LABEL_98;
      v23 = FileObject;
      if ( FileObject->PrivateCacheMap )
        CcUninitializeCacheMap(FileObject, 0, 0);
    }
    if ( v81 && (*(_DWORD *)(v81 + 4) & 0x8000) != 0 )
    {
      OffloadIoContext = -1073741528;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213890;
      goto LABEL_97;
    }
    v37 = *(_DWORD *)(v16 + 512);
    if ( (v37 & 0x40) != 0 )
    {
      OffloadIoContext = -1073741533;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213900;
      goto LABEL_97;
    }
    if ( (v37 & 0x10000) != 0 )
    {
      OffloadIoContext = -1073741202;
    }
    else
    {
      OffloadIoContext = (v37 & 0x1000000) != 0 ? 0xC0000008 : 0;
      v19 = StartingByte;
    }
    if ( (OffloadIoContext & 0x80000000) != 0 )
    {
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213906;
      goto LABEL_97;
    }
    QuadPart = v19->QuadPart;
    v33 = *(unsigned int *)(v7 + 356);
    v90 = v19->QuadPart / v33;
    if ( v90 < 0 )
    {
      OffloadIoContext = -1073741811;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213923;
      goto LABEL_97;
    }
    v33 = QuadPart + Length->QuadPart;
    if ( v33 > *(_QWORD *)(v7 + 7776) )
    {
      OffloadIoContext = -1073741811;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213933;
      goto LABEL_97;
    }
    if ( *(_DWORD *)(v16 + 256) == 160 )
    {
      OffloadIoContext = -1073700188;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_98;
      v34 = 1213940;
      goto LABEL_97;
    }
    if ( (*(_DWORD *)(v16 + 200) & 0x20) == 0 )
    {
      LOBYTE(QuadPart) = 1;
      NtfsAcquireResourceShared(v33, v16, QuadPart, v23);
      NtfsUpdateScbFromAttribute(v3, v16, 0);
      if ( *(_WORD *)v16 == 1794 )
        v39 = (struct _ERESOURCE *)(*(_QWORD *)(v16 + 104) + 64LL);
      else
        v39 = *(struct _ERESOURCE **)(v16 + 8);
      ExReleaseResourceLite(v39);
    }
    OffloadIoContext = FsRtlCheckOplock((POPLOCK)(v16 + 88), v2, (PVOID)v3, NtfsOplockComplete, NtfsPrePostIrp);
    if ( OffloadIoContext )
    {
      v2 = 0;
      v3 = 0;
      if ( !NtfsStatusDebugFlags
        || ((OffloadIoContext - 294) & 0xFFFFFFFA) == 0 && OffloadIoContext != 295
        || OffloadIoContext >= 0xFFFFFFED
        || OffloadIoContext == -1073741608
        || OffloadIoContext == -1073741802
        || OffloadIoContext == -1073741807
        || OffloadIoContext + 2147483643 <= 1
        || OffloadIoContext == 259 )
      {
        goto LABEL_98;
      }
      v34 = 1213977;
      goto LABEL_97;
    }
    if ( !*(_BYTE *)(v16 + 5) )
    {
      if ( (*(_DWORD *)(*(_QWORD *)(v16 + 192) + 4LL) & 0x4000005) == 1
        && *(_WORD *)v16 == 1797
        && FsRtlOplockIsFastIoPossible((POPLOCK)(v16 + 88)) )
      {
        if ( *(_DWORD *)(v16 + 452)
          || (v40 = *(_QWORD *)(v16 + 584)) != 0 && *(_BYTE *)(v40 + 16)
          || (v41 = *(_QWORD *)(v16 + 192),
              (*(_DWORD *)(v41 + 4) & 0x2000000) != 0 || (*(_DWORD *)(v16 + 512) & 0x4000000) != 0)
          || *(_QWORD *)(v16 + 528)
          || *(_QWORD *)(v41 + 40) )
        {
          v42 = 2;
        }
        else
        {
          v42 = 1;
        }
      }
      else
      {
        v42 = 0;
      }
      *(_BYTE *)(v16 + 5) = v42;
    }
    if ( !*(_QWORD *)(v16 + 584)
      || (v43 = *(FILE_LOCK **)(v16 + 584),
          ProcessId = IoGetRequestorProcess(v2),
          FsRtlFastCheckLockForWrite(v43, StartingByte, Length, 0, FileObject, ProcessId)) )
    {
      NtfsPurgeFileRecordCache(v3);
      if ( (*(_DWORD *)(v16 + 200) & 8) != 0 )
      {
        OffloadIoContext = -1073700188;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_175;
        v45 = 1214022;
        goto LABEL_174;
      }
      FsRtlAcquireHeaderMutex(v16 + 120, v16 + 160, v46);
      v47 = StartingByte->QuadPart;
      if ( StartingByte->QuadPart >= *(_QWORD *)(v16 + 32) )
      {
        FsRtlReleaseHeaderMutex(v16 + 120, v16 + 160);
        OffloadIoContext = -1073741807;
        goto LABEL_98;
      }
      v48 = *(_QWORD *)(v16 + 40);
      if ( v47 > v48 )
      {
        FsRtlReleaseHeaderMutex(v16 + 120, v16 + 160);
        OffloadIoContext = -1073740750;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_175;
        v45 = 1214063;
        goto LABEL_174;
      }
      if ( v47 + Length->QuadPart > v48 )
      {
        if ( !v26 )
          v26 = 1;
        NtfsGetIoAtEof(v3, v16, v47, Length->QuadPart, v26, (__int64)&v93);
      }
      FsRtlReleaseHeaderMutex(v16 + 120, v16 + 160);
      NtfsPreloadAllocationInternal(v3, 0x7FFFFFFFFFFFFFFFLL, 0);
      OffloadIoContext = NtfsPrepareForCriticalIo(v3, (_DWORD)v2, v16, StartingByte->QuadPart, Length->QuadPart, 2);
      if ( (OffloadIoContext & 0x80000000) == 0 )
      {
        v49 = (union _LARGE_INTEGER *)ExAllocateFromLookasideListEx(&NtfsFileOffloadLookasideList);
        v35 = v49;
        Entry = v49;
        if ( v49 )
        {
          memset(v49, 0, 0x1000u);
          v35->LowPart = 28;
          v51 = 4;
          v35->HighPart = 4;
          v35[1].HighPart = 32;
          v35[2].LowPart = 528;
          v52 = v89;
          v35[5].QuadPart = v89[3];
          v53 = v35 + 6;
          v54 = v52 + 4;
          do
          {
            *(_OWORD *)&v53->LowPart = *v54;
            *(_OWORD *)&v53[2].LowPart = v54[1];
            *(_OWORD *)&v53[4].LowPart = v54[2];
            *(_OWORD *)&v53[6].LowPart = v54[3];
            *(_OWORD *)&v53[8].LowPart = v54[4];
            *(_OWORD *)&v53[10].LowPart = v54[5];
            *(_OWORD *)&v53[12].LowPart = v54[6];
            *(_OWORD *)&v53[14].LowPart = v54[7];
            v53 += 16;
            v54 += 8;
            --v51;
          }
          while ( v51 );
          v35[2].HighPart = 560;
          v55 = 0;
          v85 = 0;
          v56 = v90;
          v91 = v90;
          NtfsPostUsnChangeWithOverrideOption(v3, v16, 1, 0, StartingByte->QuadPart, Length->QuadPart, 0);
          while ( 1 )
          {
            v57 = NtfsLookupNtfsMcbEntryWithSyncFlag(v16 + 400, v56, &v86, &v82, 0, 0, 0, 0);
            if ( !v57 && !v55 )
            {
              OffloadIoContext = -1073741566;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_175;
              v45 = 1214237;
              goto LABEL_174;
            }
            if ( v57 )
            {
              if ( v86 == -1 )
              {
                OffloadIoContext = -1073741566;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_175;
                v45 = 1214251;
                goto LABEL_174;
              }
              v58 = 2LL * v55;
              Entry[v58 + 70].QuadPart = v86 << *(_BYTE *)(v7 + 488);
              Entry[v58 + 71].QuadPart = v82 << *(_BYTE *)(v7 + 488);
              v59 = (v82 << *(_BYTE *)(v7 + 488)) + *(_QWORD *)v78;
              *(_QWORD *)v78 = v59;
              v88 = v59;
              if ( !v55 )
              {
                v60 = StartingByte;
                v61 = StartingByte->QuadPart % (unsigned __int64)*(unsigned int *)(v7 + 356);
                if ( v61 )
                {
                  Entry[70].QuadPart += v61;
                  Entry[71].QuadPart -= v60->QuadPart % (unsigned __int64)*(unsigned int *)(v7 + 356);
                  v59 = Entry[71].QuadPart;
                  *(_QWORD *)v78 = v59;
                  v88 = v59;
                }
                else
                {
                  v59 = *(_QWORD *)v78;
                }
              }
              v62 = Length;
              if ( v59 >= Length->QuadPart )
              {
                Entry[v58 + 71].QuadPart += Length->QuadPart - v59;
                *(union _LARGE_INTEGER *)v78 = *v62;
                v88 = *(_QWORD *)v78;
              }
              v85 = ++v55;
            }
            else
            {
              v62 = Length;
            }
            if ( v55 >= 221 || !v57 && v55 || *(_QWORD *)v78 >= v62->QuadPart )
              break;
            v56 += v82;
            v91 = v56;
          }
          v63 = 16 * v55;
          v35 = Entry;
          Entry[3].LowPart = v63;
          if ( !v26 )
          {
            OffloadIoContext = NtfsCreateOffloadIoContext(
                                 (_DWORD)v2,
                                 v87,
                                 v81,
                                 (_DWORD)Entry,
                                 (__int64)&v92,
                                 (__int64)&v84);
            if ( (OffloadIoContext & 0x80000000) != 0 )
              goto LABEL_250;
            NtfsPrePostIrp((PVOID)v3, v2);
            v67 = 0;
            LODWORD(NumberOfBytes) = Entry[3].LowPart + 560;
            v68 = v84;
            v70 = NtfsDeviceIoControlAsync3(
                    v3,
                    *(_QWORD *)(v7 + 224),
                    v7,
                    v69,
                    (__int64)NtfsAsyncOffloadWriteCompletionRoutine,
                    (__int64)v84,
                    Entry,
                    NumberOfBytes,
                    16,
                    3,
                    0,
                    0);
            OffloadIoContext = v70;
            if ( v70 < 0 )
            {
              v68[2] = v70;
              NtfsAsyncOffloadWriteCompletionRoutine(0, 0, v68);
            }
            v35 = Entry;
            goto LABEL_251;
          }
          OffloadIoContext = NtfsDeviceIoControl2(
                               v3,
                               *(_QWORD *)(v7 + 224),
                               v7,
                               2987012,
                               (__int64)Entry,
                               v63 + 560,
                               16,
                               3);
          if ( (OffloadIoContext & 0x80000000) != 0 )
          {
            if ( OffloadIoContext == -1073741637 || OffloadIoContext == -1073740701 )
              NtfsClearSupportedFeatures(v7);
            else
              NtfsSetSupportedFeatures(v7);
            v35 = Entry;
          }
          else
          {
            v64 = Entry[1];
            v65 = StartingByte;
            v66 = StartingByte->QuadPart;
            NtfsUpdateFileTimestampsForModification(FileObject, v87, v81);
            if ( v93 )
            {
              NtfsUpdateScbFromFileObject(FileObject, v16, 0);
              NtfsOffloadUpdateScb(v3, v16, FileObject, v64.QuadPart + v66);
            }
            v35 = Entry;
            *v65 = Entry[1];
            v33 = (unsigned __int64)v89;
            *v89 = 16;
          }
          if ( NtfsStatusDebugFlags )
          {
            if ( OffloadIoContext )
            {
              if ( OffloadIoContext != 294 )
              {
                v33 = 1;
                if ( OffloadIoContext - 298 > 1
                  && OffloadIoContext < 0xFFFFFFED
                  && OffloadIoContext != -1073741608
                  && OffloadIoContext != -1073741802
                  && OffloadIoContext != -1073741807
                  && OffloadIoContext + 2147483643 > 1
                  && OffloadIoContext != 259 )
                {
                  v50 = 1214404;
                  goto LABEL_199;
                }
              }
            }
          }
        }
        else
        {
          LOBYTE(v33) = NtfsStatusDebugFlags;
          OffloadIoContext = -1073741670;
          if ( NtfsStatusDebugFlags )
          {
            v50 = 1214146;
LABEL_199:
            NtfsStatusTraceAndDebugInternal(0, OffloadIoContext, v50);
          }
        }
LABEL_250:
        v67 = 1;
LABEL_251:
        if ( v67 )
        {
          if ( v92 )
          {
            if ( v3 && *(_DWORD *)(v3 + 28) )
            {
              for ( i = 0; i < 2; ++i )
              {
                v72 = *(_QWORD *)(v3 + 8LL * i + 48);
                if ( !v72 || v72 == *(_QWORD *)(v16 + 184) )
                {
                  *(_QWORD *)(v3 + 8LL * i + 48) = *(_QWORD *)(v16 + 184);
                  break;
                }
              }
            }
            else
            {
              NtfsReleasePagingResourcePriv(v33, *(_QWORD *)(v16 + 184));
              if ( v3 )
              {
                for ( j = 0; j != 2; ++j )
                {
                  if ( *(_QWORD *)(v3 + 8 * j + 48) == *(_QWORD *)(v16 + 184) )
                    *(_QWORD *)(v3 + 8 * j + 48) = 0;
                }
              }
            }
          }
          if ( v35 )
            ExFreeToLookasideListEx(&NtfsFileOffloadLookasideList, v35);
          if ( v84 )
            ExFreeToLookasideListEx(&NtfsOffloadIoContextLookasideList, v84);
        }
        if ( v2 )
        {
          if ( v67 )
          {
            v74 = 0;
            if ( (OffloadIoContext & 0x80000000) == 0 )
              v74 = 16;
            v2->IoStatus.Information = v74;
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
          NtfsStatusTraceAndDebugInternal(v3, OffloadIoContext, 1214522);
        }
        LOBYTE(v23) = v2 != 0;
        NtfsExtendedCompleteRequestInternal(v3, v2, OffloadIoContext, v23, (OffloadIoContext & 0x80000000) == 0);
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
        v14 = 1214524;
        goto LABEL_19;
      }
      if ( NtfsStatusDebugFlags
        && OffloadIoContext < 0xFFFFFFED
        && OffloadIoContext != -1073741802
        && OffloadIoContext != -1073741807
        && OffloadIoContext + 2147483643 > 1
        && OffloadIoContext != -1073741608 )
      {
        v45 = 1214133;
        goto LABEL_174;
      }
    }
    else
    {
      OffloadIoContext = -1073741740;
      if ( NtfsStatusDebugFlags )
      {
        v45 = 1214006;
LABEL_174:
        NtfsStatusTraceAndDebugInternal(0, OffloadIoContext, v45);
      }
    }
LABEL_175:
    v35 = Entry;
    goto LABEL_250;
  }
  *v25 = 16;
  v19->QuadPart = 0;
  v2->IoStatus.Information = 16;
  LOBYTE(v23) = v2 != 0;
  NtfsExtendedCompleteRequestInternal(v3, v2, 0, v23, 1);
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
