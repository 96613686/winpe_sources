# TxfRedoWriteFile

- ea: `0x14010ae4c`
- end: `0x14010bcea`
- name: `TxfRedoWriteFile`
- size: `3742`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x140133f80`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x140012e70`
- `0x140053244`
- `0x1400592c0`
- `0x140059440`
- `0x1400b6e90`
- `0x14010038c`
- `0x140100b64`
- `0x14010ae4c`
- `0x140133244`
- `0x1401403d0`
- `0x140163fc8`
- `0x140208f8c`
- `0x14020bbc0`
- `0x140244820`
- `0x140294b6c`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14010b776`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14010b776`
- `ntoskrnl!CcMapData` at `0x14010b510`
- `ntoskrnl!CcMapData` at `0x14010b5dd`
- `ntoskrnl!CcMapData` at `0x14010b510`
- `ntoskrnl!CcMapData` at `0x14010b5dd`
- `ntoskrnl!CcPinMappedData` at `0x14010b5a2`
- `ntoskrnl!CcPinMappedData` at `0x14010b5a2`
- `ntoskrnl!CcPreparePinWrite` at `0x14010ba77`
- `ntoskrnl!CcPreparePinWrite` at `0x14010baf3`
- `ntoskrnl!CcPreparePinWrite` at `0x14010ba77`
- `ntoskrnl!CcPreparePinWrite` at `0x14010baf3`
- `ntoskrnl!IoSetInformation` at `0x14010b12d`
- `ntoskrnl!IoSetInformation` at `0x14010b12d`
- `ntoskrnl!KeReleaseMutex` at `0x14010b919`
- `ntoskrnl!KeReleaseMutex` at `0x14010b919`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14010b393`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14010b393`
- `ntoskrnl!DbgPrintEx` at `0x14010b4cd`
- `ntoskrnl!DbgPrintEx` at `0x14010b4cd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010b837`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010b837`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010b1fd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010b85a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010b1fd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010b85a`
- `ntoskrnl!CcUnpinData` at `0x14010b623`
- `ntoskrnl!CcUnpinData` at `0x14010b693`
- `ntoskrnl!CcUnpinData` at `0x14010bc0d`
- `ntoskrnl!CcUnpinData` at `0x14010bc26`
- `ntoskrnl!CcUnpinData` at `0x14010bc3f`
- `ntoskrnl!CcUnpinData` at `0x1402c5bce`
- `ntoskrnl!CcUnpinData` at `0x1402c5be7`
- `ntoskrnl!CcUnpinData` at `0x1402c5c00`
- `ntoskrnl!CcUnpinData` at `0x14010b623`
- `ntoskrnl!CcUnpinData` at `0x14010b693`
- `ntoskrnl!CcUnpinData` at `0x14010bc0d`
- `ntoskrnl!CcUnpinData` at `0x14010bc26`
- `ntoskrnl!CcUnpinData` at `0x14010bc3f`
- `ntoskrnl!CcUnpinData` at `0x1402c5bce`
- `ntoskrnl!CcUnpinData` at `0x1402c5be7`
- `ntoskrnl!CcUnpinData` at `0x1402c5c00`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010b93a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bc59`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bca0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bcba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c1a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c68`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c89`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010b93a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bc59`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bca0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bcba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c1a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c68`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c89`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010b342`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010b739`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010b342`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010b739`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010b3a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010b7bd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c5bb5`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010b3a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010b7bd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c5bb5`
- `ntoskrnl!ExRaiseStatus` at `0x14010b161`
- `ntoskrnl!ExRaiseStatus` at `0x14010b1d3`
- `ntoskrnl!ExRaiseStatus` at `0x14010b161`
- `ntoskrnl!ExRaiseStatus` at `0x14010b1d3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14010b878`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14010b878`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010afed`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010b02d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010b0b2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010afed`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010b02d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010b0b2`

## pseudocode

```c
void __fastcall TxfRedoWriteFile(__int64 a1, __int64 a2, __int64 a3, const CLFS_LSN *a4)
{
  PVOID FsContext; // rsi
  unsigned int *v8; // rdi
  __int64 v9; // r13
  const CLFS_LSN *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // ebx
  __int64 i; // rcx
  __int64 v17; // rdx
  __int64 v18; // rbx
  int v19; // ebx
  __int64 v20; // rdi
  unsigned int *v21; // r13
  __int64 v22; // rdi
  __int64 v23; // rdx
  ULONG v24; // edi
  union _LARGE_INTEGER v25; // rdx
  __int64 v26; // r13
  __int64 v27; // r10
  union _LARGE_INTEGER v28; // rcx
  union _LARGE_INTEGER v29; // rax
  union _LARGE_INTEGER v30; // rax
  union _LARGE_INTEGER v31; // rax
  union _LARGE_INTEGER v32; // rdx
  union _LARGE_INTEGER v33; // r8
  CLFS_LSN *inserted; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  _QWORD *v39; // rax
  _QWORD *v40; // r8
  _QWORD *v41; // rcx
  __int64 v42; // r9
  _QWORD *v43; // rbx
  __int64 v44; // rax
  char v45; // al
  __int64 v46; // rcx
  ULONG v47; // edi
  unsigned int v48; // ebx
  signed __int64 v49; // rcx
  signed __int64 v50; // r8
  int v51; // edx
  signed __int64 v52; // r9
  signed __int64 v53; // r8
  __int64 j; // rcx
  __int64 v55; // rdx
  int RestartKey; // [rsp+20h] [rbp-188h]
  char v57; // [rsp+51h] [rbp-157h] BYREF
  char v58; // [rsp+52h] [rbp-156h]
  char v59; // [rsp+53h] [rbp-155h]
  char v60; // [rsp+54h] [rbp-154h]
  unsigned __int8 NewElement[3]; // [rsp+55h] [rbp-153h] BYREF
  union _LARGE_INTEGER v62; // [rsp+58h] [rbp-150h] BYREF
  __int64 v63; // [rsp+60h] [rbp-148h]
  unsigned int v64; // [rsp+68h] [rbp-140h]
  union _LARGE_INTEGER v65; // [rsp+70h] [rbp-138h] BYREF
  __int64 v66; // [rsp+78h] [rbp-130h]
  union _LARGE_INTEGER FileInformation; // [rsp+80h] [rbp-128h] BYREF
  int v68; // [rsp+88h] [rbp-120h]
  PVOID v69; // [rsp+90h] [rbp-118h] BYREF
  PVOID Src; // [rsp+98h] [rbp-110h] BYREF
  PVOID Bcb; // [rsp+A0h] [rbp-108h] BYREF
  int v72; // [rsp+A8h] [rbp-100h]
  int v73; // [rsp+ACh] [rbp-FCh]
  int v74; // [rsp+B0h] [rbp-F8h]
  PVOID v75; // [rsp+B8h] [rbp-F0h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+C0h] [rbp-E8h] BYREF
  PFILE_OBJECT FileObject; // [rsp+C8h] [rbp-E0h] BYREF
  ULONG DeleteCount; // [rsp+D0h] [rbp-D8h] BYREF
  __int64 v79; // [rsp+D8h] [rbp-D0h]
  __int64 v80; // [rsp+E0h] [rbp-C8h]
  PVOID v81[2]; // [rsp+E8h] [rbp-C0h] BYREF
  PVOID v82; // [rsp+F8h] [rbp-B0h] BYREF
  __int64 v83; // [rsp+100h] [rbp-A8h]
  ULONGLONG *p_ullOffset; // [rsp+108h] [rbp-A0h]
  PVOID v85; // [rsp+110h] [rbp-98h]
  __int64 v86; // [rsp+118h] [rbp-90h]
  __int64 v87; // [rsp+120h] [rbp-88h]
  int v88; // [rsp+128h] [rbp-80h]
  __int128 MatchData; // [rsp+130h] [rbp-78h] BYREF
  __int128 v90; // [rsp+140h] [rbp-68h]
  __int128 v91; // [rsp+150h] [rbp-58h]
  int v92; // [rsp+160h] [rbp-48h]

  p_ullOffset = &a4->ullOffset;
  v83 = a2;
  v86 = a1;
  FileInformation.QuadPart = 0;
  FileObject = 0;
  Src = 0;
  v75 = 0;
  Bcb = 0;
  v69 = 0;
  v81[0] = 0;
  v68 = 0;
  v58 = 0;
  v59 = 0;
  FsContext = 0;
  v85 = 0;
  v66 = *(_QWORD *)(a2 + 208);
  v87 = v66;
  v8 = (unsigned int *)(v66 + 280);
  v81[1] = (PVOID)(v66 + 280);
  DeleteCount = 0;
  v82 = 0;
  v65.QuadPart = 0;
  v62.QuadPart = 0;
  v63 = 0;
  v9 = *(unsigned int *)(a3 + 112);
  v64 = *(_DWORD *)(a3 + 112);
  v80 = 0;
  MatchData = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v60 = 0;
  v74 = 0;
  v57 = 0;
  if ( (int)TxfOpenFileCheckId(
              a1,
              a2,
              a3,
              (int)a3 + 80,
              a3 + 96,
              2,
              0,
              (__int64)&v57,
              (__int64)&FileInformation,
              (__int64)&FileObject) < 0 )
    goto LABEL_102;
  FsContext = FileObject->FsContext;
  v85 = FsContext;
  NtfsAcquireExclusiveScbEx(a1, FsContext, 0);
  v10 = (const CLFS_LSN *)*((_QWORD *)FsContext + 23);
  if ( v57 )
  {
    if ( !ClfsLsnLess(a4, v10 + 30) && NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3241206);
    goto LABEL_102;
  }
  if ( ClfsLsnLess(a4, v10 + 32) )
    goto LABEL_102;
  TxfRebuildTxfStructuresForRecovery(a1, FsContext, v83, 0);
  v11 = *((_QWORD *)FsContext + 66);
  v63 = *(_QWORD *)(v11 + 56);
  if ( !*(_QWORD *)(v11 + 88) )
    *(_QWORD *)(v11 + 88) = FsContext;
  NtfsReleaseFcbEx(a1, *((_QWORD *)FsContext + 23), 0);
  if ( (*(_DWORD *)(a3 + 120) & 1) != 0 || *((_QWORD *)FsContext + 4) >= v9 + *(_QWORD *)(a3 + 104) )
    goto LABEL_32;
  if ( ClfsLsnLess(a4, (const CLFS_LSN *)(*((_QWORD *)FsContext + 23) + 240LL)) )
  {
    v13 = *((_QWORD *)FsContext + 4);
    v14 = *(_QWORD *)(a3 + 104);
    if ( v14 < v13 )
    {
      if ( v14 + v9 > v13 )
      {
        v9 = (unsigned int)(v13 - v14);
        v64 = v13 - v14;
        v88 = v13 - v14;
      }
      goto LABEL_15;
    }
LABEL_102:
    v26 = v66;
    goto LABEL_103;
  }
LABEL_15:
  if ( *((_QWORD *)FsContext + 4) < (signed __int64)(*(_QWORD *)(a3 + 104) + (unsigned int)v9) )
  {
    FileInformation.QuadPart = *(_QWORD *)(a3 + 104) + (unsigned int)v9;
    v15 = IoSetInformation(FileObject, FileEndOfFileInformation, 8u, &FileInformation);
    if ( *(_DWORD *)(a1 + 24) == -1073741432 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225864LL, 4460417);
      ExRaiseStatus(*(_DWORD *)(a1 + 24));
    }
    if ( v15 )
    {
      if ( NtfsStatusDebugFlags
        && (((v15 - 294) & 0xFFFFFFFA) != 0 || v15 == 295)
        && v15 < 0xFFFFFFED
        && v15 != -1073741608
        && v15 != -1073741802
        && v15 != -1073741807
        && v15 + 2147483643 > 1
        && v15 != 259 )
      {
        NtfsStatusTraceAndDebugInternal(a1, v15, 3241343);
      }
      ExRaiseStatus(v15);
    }
  }
LABEL_32:
  LOBYTE(v12) = 1;
  v68 = (unsigned __int8)NtfsAcquireScbPagingResourceExclusive(a1, FsContext, v12);
  ExAcquireResourceExclusiveLite(*((PERESOURCE *)v8 + 11), 1u);
  v59 = 1;
  v58 = NtfsAcquireScbPagingResourceShared(a1, *(_QWORD *)v8);
  v72 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v72 = i;
    if ( (unsigned int)i >= 2 )
      break;
    v17 = *(_QWORD *)(a1 + 8 * i + 48);
    if ( !v17 || v17 == *(_QWORD *)(*(_QWORD *)v8 + 184LL) )
    {
      *(_QWORD *)(a1 + 8LL * (unsigned int)i + 48) = *(_QWORD *)(*(_QWORD *)v8 + 184LL);
      break;
    }
  }
  NtfsCreateInternalAttributeStream(a1, (__int64)FsContext, 0, 0, 0, 0);
  if ( (*(_BYTE *)a3 & 2) == 0 || (*(_BYTE *)(a3 + 158) & 2) == 0 )
  {
    while ( 1 )
    {
LABEL_74:
      if ( (*(_DWORD *)(a3 + 120) & 1) != 0 )
        goto LABEL_102;
      v35 = v66;
      KeWaitForSingleObject((PVOID)(*(_QWORD *)(v66 + 24) + 856LL), Executive, 0, 0, 0);
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*((_QWORD *)FsContext + 23) + 328LL) + 136LL), 1u);
      if ( ClfsLsnInvalid((const CLFS_LSN *)(*(_QWORD *)(*((_QWORD *)FsContext + 23) + 328LL) + 120LL)) )
      {
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)FsContext + 23) + 328LL) + 120LL) = *p_ullOffset;
        v36 = *((_QWORD *)FsContext + 23);
        v37 = *(_QWORD *)(v36 + 328) + 104LL;
        v38 = *(_QWORD *)v37;
        if ( *(_QWORD *)(*(_QWORD *)v37 + 8LL) != v37
          || (v39 = *(_QWORD **)(*(_QWORD *)(v36 + 328) + 112LL), *v39 != v37)
          || (*v39 = v38, *(_QWORD *)(v38 + 8) = v39, v40 = *(_QWORD **)(v35 + 640), *v40 != v35 + 632) )
        {
          __fastfail(3u);
        }
        v41 = (_QWORD *)(*(_QWORD *)(*((_QWORD *)FsContext + 23) + 328LL) + 104LL);
        *v41 = v35 + 632;
        v41[1] = v40;
        *v40 = v41;
        *(_QWORD *)(v35 + 640) = v41;
      }
      KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v35 + 24) + 856LL), 0);
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*((_QWORD *)FsContext + 23) + 328LL) + 136LL));
      v74 = 0;
      *(_DWORD *)(*((_QWORD *)FsContext + 66) + 24LL) = *(_DWORD *)(*((_QWORD *)FsContext + 66) + 24LL);
      v42 = *((_QWORD *)FsContext + 5);
      v43 = (_QWORD *)(a3 + 104);
      v44 = *(_QWORD *)(a3 + 104);
      if ( v44 <= v42 )
        goto LABEL_86;
      v45 = NtfsZeroData(a1, (_DWORD)FsContext, *((PFILE_OBJECT *)FsContext + 35), v44 - v42, 0, 0);
      v46 = *((_QWORD *)FsContext + 66);
      if ( v45 )
        break;
      *(_DWORD *)(v46 + 24) = *(_DWORD *)(v46 + 24);
      *(_QWORD *)(*((_QWORD *)FsContext + 66) + 96LL) = *((_QWORD *)FsContext + 5);
      *(_QWORD *)(*((_QWORD *)FsContext + 66) + 104LL) = *((_QWORD *)FsContext + 4);
      NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 3241881);
    }
    *(_QWORD *)(v46 + 96) = *((_QWORD *)FsContext + 5);
    *(_QWORD *)(*((_QWORD *)FsContext + 66) + 104LL) = *((_QWORD *)FsContext + 4);
LABEL_86:
    if ( ((*v43 ^ (v9 + *v43 - 1LL)) & 0xFFFFFFFFFFFC0000uLL) != 0 )
    {
      v47 = 0x40000 - (*v43 & 0x3FFFF);
      v80 = v47;
      CcPreparePinWrite(*((PFILE_OBJECT *)FsContext + 35), (PLARGE_INTEGER)(a3 + 104), v47, 0, 0x43u, v81, &Src);
      memmove(Src, (const void *)(a3 + *(unsigned int *)(a3 + 116)), v47);
    }
    else
    {
      v47 = v80;
    }
    v62.QuadPart = v47 + *v43;
    v48 = v64 - v80;
    CcPreparePinWrite(*((PFILE_OBJECT *)FsContext + 35), &v62, v64 - v80, 0, 0x43u, &v69, &Src);
    memmove(Src, (const void *)(a3 + v47 + (unsigned __int64)*(unsigned int *)(a3 + 116)), v48);
    v49 = v9 + *(_QWORD *)(a3 + 104);
    v50 = *((_QWORD *)FsContext + 5);
    if ( v50 >= v49 )
      goto LABEL_101;
    if ( (*((_DWORD *)FsContext + 50) & 0x200) != 0 )
      v50 = *((_QWORD *)FsContext + 5);
    v51 = *((_DWORD *)FsContext + 50);
    if ( (v51 & 0x20000) != 0 )
    {
      v52 = *((_QWORD *)FsContext + 58);
      if ( v52 < v49 )
      {
LABEL_99:
        *((_QWORD *)FsContext + 58) = v49;
        goto LABEL_100;
      }
      if ( v50 > v49 )
      {
        if ( *(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) && v49 != 0x7FFFFFFFFFFFFFFFLL )
        {
          v53 = (v49 + 4095) & 0xFFFFFFFFFFFFF000uLL;
          if ( v53 < v52 )
            *((_QWORD *)FsContext + 58) = v53;
          goto LABEL_100;
        }
        goto LABEL_99;
      }
    }
LABEL_100:
    *((_QWORD *)FsContext + 5) = v49;
    *(_QWORD *)(*((_QWORD *)FsContext + 66) + 96LL) = v49;
    *(_QWORD *)(*((_QWORD *)FsContext + 66) + 104LL) = *((_QWORD *)FsContext + 4);
    *(_DWORD *)(*((_QWORD *)FsContext + 66) + 24LL) = *(_DWORD *)(*((_QWORD *)FsContext + 66) + 24LL);
LABEL_101:
    NtfsCheckpointCurrentTransaction(a1);
    goto LABEL_102;
  }
  v79 = *(_QWORD *)(a3 + 136);
  v18 = v66;
  while ( v8[6] < *(_QWORD *)(a3 + 136) + (unsigned __int64)*(unsigned int *)(a3 + 152) )
    TxfExtendTopsStream(a1, v18, v8[10] + 64);
  v79 <<= 12;
  v19 = *(_DWORD *)(a3 + 160);
  v73 = v19;
  v65.QuadPart = *(_QWORD *)(a3 + 128) << 12;
  while ( 1 )
  {
    *(_QWORD *)&MatchData = (unsigned __int64)v65.QuadPart >> 12;
    DWORD2(v90) = (unsigned int)(v19 + 4095) >> 12;
    v82 = 0;
    v20 = v63;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(v63 + 256));
    v21 = (unsigned int *)RtlEnumerateGenericTableLikeADirectory(
                            (PRTL_AVL_TABLE)(v20 + 152),
                            TxfMatchPageRange,
                            &MatchData,
                            0,
                            &v82,
                            &DeleteCount,
                            &MatchData);
    ExReleaseFastMutex(*(PFAST_MUTEX *)(v20 + 256));
    if ( !v21 )
      break;
    v22 = *(_QWORD *)v21;
    if ( *(_QWORD *)v21 > (unsigned __int64)MatchData )
    {
      v24 = ((_DWORD)v22 << 12) - v65.LowPart;
      goto LABEL_50;
    }
    v23 = v21[6];
    if ( v23 + v22 >= (unsigned __int64)MatchData + DWORD2(v90) )
      goto LABEL_73;
    v65.QuadPart = (v23 + v22) << 12;
    v19 = *(_DWORD *)(a3 + 160) + ((*(_DWORD *)(a3 + 128) - (_DWORD)v22 - (_DWORD)v23) << 12);
LABEL_72:
    v73 = v19;
    if ( !v19 )
    {
LABEL_73:
      v9 = v64;
      goto LABEL_74;
    }
  }
  v24 = v19;
LABEL_50:
  if ( !v24 )
  {
LABEL_71:
    v19 -= v24;
    goto LABEL_72;
  }
  FileOffset.QuadPart = 0;
  NewElement[0] = 0;
  v25.QuadPart = (v24 + 4095) & 0xFFFFF000;
  FileInformation = v25;
  FileOffset.QuadPart = v65.QuadPart - (*(_QWORD *)(a3 + 128) << 12) + v79;
  v26 = v66;
  v27 = *(_QWORD *)(v66 + 280);
  if ( v25.QuadPart + FileOffset.QuadPart <= *(_QWORD *)(v27 + 40) )
  {
    CcMapData(*(PFILE_OBJECT *)(v27 + 280), &FileOffset, v25.LowPart, 0x41u, &Bcb, &v75);
    v57 = 1;
    v62.QuadPart = 0;
    v28.QuadPart = 0;
    v29.QuadPart = 0;
    while ( 1 )
    {
      if ( v28.QuadPart >= (unsigned __int64)v24 )
        goto LABEL_66;
      if ( *((unsigned __int8 *)v75 + v29.QuadPart) != *(_WORD *)(a3 + 156) )
        break;
      v28.QuadPart += 512LL;
      v62 = v28;
      v29 = v28;
    }
    if ( *((_QWORD *)FsContext + 5) < (unsigned __int64)v24 + v65.QuadPart )
      goto LABEL_102;
    v57 = 0;
    CcPinMappedData(*(PFILE_OBJECT *)(*(_QWORD *)(v66 + 280) + 280LL), &FileOffset, FileInformation.LowPart, 3u, &Bcb);
    CcMapData(*((PFILE_OBJECT *)FsContext + 35), &v65, v24, 0x41u, &v69, &Src);
    v62.QuadPart = 0;
    for ( v30.QuadPart = 0; v30.QuadPart < (unsigned __int64)v24; v30.QuadPart += 512LL )
      v62 = v30;
    memmove(v75, Src, v24);
    CcUnpinData(v69);
    v69 = 0;
    v62.QuadPart = 0;
    v31.QuadPart = 0;
    v32.QuadPart = 0;
    v33 = FileInformation;
    while ( v31.QuadPart < (unsigned __int64)v33.QuadPart )
    {
      *(_WORD *)((char *)v75 + v32.QuadPart) = *(_WORD *)(a3 + 156);
      v31.QuadPart = v62.QuadPart + 512;
      v62 = v31;
      v32 = v31;
    }
LABEL_66:
    CcUnpinData(Bcb);
    Bcb = 0;
    *(_QWORD *)&MatchData = (unsigned __int64)v65.QuadPart >> 12;
    DWORD2(v90) = FileInformation.LowPart >> 12;
    *((_QWORD *)&MatchData + 1) = (unsigned int)((unsigned __int64)FileOffset.QuadPart >> 12);
    LODWORD(v91) = v24;
    WORD6(v90) = *(_WORD *)(a3 + 156);
    BYTE14(v90) = 4;
    LOBYTE(RestartKey) = v59;
    TxfDirectlyAllocateTopsRange(
      *(_QWORD *)(v83 + 208),
      v63,
      *((_QWORD *)&MatchData + 1),
      FileInformation.LowPart >> 12,
      RestartKey);
    v60 = 1;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(v63 + 256));
    inserted = (CLFS_LSN *)RtlInsertElementGenericTableAvl(
                             (PRTL_AVL_TABLE)(v63 + 152),
                             &MatchData,
                             16 * (DWORD2(v90) - 1) + 52,
                             NewElement);
    if ( v57 )
    {
      inserted[2] = CLFS_LSN_INVALID_EXT;
      BYTE6(inserted[3].ullOffset) |= 0x20u;
    }
    else
    {
      inserted[2].ullOffset = *p_ullOffset;
    }
    BYTE6(inserted[3].ullOffset) |= 1u;
    ExReleaseFastMutex(*(PFAST_MUTEX *)(v63 + 256));
    v60 = 0;
    if ( (*(_DWORD *)(a3 + 120) & 1) != 0 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfFlushUndoPriorToDiskWrite)(
        a1,
        FileObject,
        (union _LARGE_INTEGER)v65.QuadPart,
        v24);
    goto LABEL_71;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3241564);
  DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 30301, "Status", -1073741566);
LABEL_103:
  *(_QWORD *)(a1 + 400) = 0;
  if ( Bcb )
    CcUnpinData(Bcb);
  if ( v69 )
    CcUnpinData(v69);
  if ( v81[0] )
    CcUnpinData(v81[0]);
  if ( v68 )
    ExReleaseResourceLite(*((PERESOURCE *)FsContext + 2));
  if ( v58 )
  {
    for ( j = 0; j != 2; ++j )
    {
      v55 = *(_QWORD *)(v26 + 280);
      if ( *(_QWORD *)(a1 + 8 * j + 48) == *(_QWORD *)(v55 + 184) )
      {
        *(_QWORD *)(a1 + 8 * j + 48) = 0;
        v55 = *(_QWORD *)(v26 + 280);
      }
    }
    ExReleaseResourceLite(*(PERESOURCE *)(v55 + 16));
  }
  if ( v59 )
    ExReleaseResourceLite(*(PERESOURCE *)(v26 + 368));
}

```

## disassembly

```asm
0x14010ae4c  mov     r11, rsp
0x14010ae4f  push    rbx
0x14010ae50  push    rsi
0x14010ae51  push    rdi
0x14010ae52  push    r12
0x14010ae54  push    r13
0x14010ae56  push    r14
0x14010ae58  push    r15
0x14010ae5a  sub     rsp, 170h
0x14010ae61  mov     rax, cs:__security_cookie
0x14010ae68  xor     rax, rsp
0x14010ae6b  mov     [rsp+1A8h+var_40], rax
0x14010ae73  mov     r12, r9
0x14010ae76  mov     [rsp+1A8h+var_A0], r9
0x14010ae7e  mov     r14, r8
0x14010ae81  mov     [rsp+1A8h+var_A8], rdx
0x14010ae89  mov     r15, rcx
0x14010ae8c  mov     [rsp+1A8h+var_90], rcx
0x14010ae94  xor     r8d, r8d
0x14010ae97  mov     [r11-128h], r8
0x14010ae9e  mov     [r11-0E0h], r8
0x14010aea5  mov     [r11-110h], r8
0x14010aeac  mov     [r11-0F0h], r8
0x14010aeb3  mov     [r11-108h], r8
0x14010aeba  mov     [r11-118h], r8
0x14010aec1  mov     [r11-0C0h], r8
0x14010aec8  mov     [r11-120h], r8d
0x14010aecf  mov     [rsp+1A8h+var_156], r8b
0x14010aed4  mov     [rsp+1A8h+var_155], r8b
0x14010aed9  mov     esi, r8d
0x14010aedc  mov     [r11-98h], r8
0x14010aee3  mov     rax, [rdx+0D0h]
0x14010aeea  mov     [rsp+1A8h+var_130], rax
0x14010aeef  mov     [rsp+1A8h+var_88], rax
0x14010aef7  lea     rdi, [rax+118h]
0x14010aefe  mov     [rsp+1A8h+var_B8], rdi
0x14010af06  mov     [r11-0D8h], r8d
0x14010af0d  mov     [r11-0B0h], r8
0x14010af14  mov     qword ptr [rsp+1A8h+var_138], r8
0x14010af19  mov     qword ptr [rsp+1A8h+var_150], r8
0x14010af1e  mov     [rsp+1A8h+var_148], r8
0x14010af23  mov     [rsp+1A8h+var_158], sil
0x14010af28  mov     r13d, [r14+70h]
0x14010af2c  mov     [rsp+1A8h+var_140], r13d
0x14010af31  mov     ecx, r8d
0x14010af34  mov     [rsp+1A8h+var_C8], rcx
0x14010af3c  xorps   xmm0, xmm0
0x14010af3f  xor     eax, eax
0x14010af41  movups  xmmword ptr [r11-78h], xmm0
0x14010af46  movups  xmmword ptr [r11-68h], xmm0
0x14010af4b  movups  xmmword ptr [r11-58h], xmm0
0x14010af50  mov     [r11-48h], eax
0x14010af54  mov     [rsp+1A8h+var_154], al
0x14010af58  mov     [rsp+1A8h+var_F8], eax
0x14010af5f  mov     [rsp+1A8h+var_157], r8b
0x14010af64  lea     rax, [r14+60h]
0x14010af68  lea     r9, [r14+50h]
0x14010af6c  lea     rcx, [r11-0E0h]
0x14010af73  mov     [rsp+1A8h+var_160], rcx
0x14010af78  lea     rcx, [r11-128h]
0x14010af7f  mov     [rsp+1A8h+var_168], rcx
0x14010af84  lea     rcx, [rsp+1A8h+var_157]
0x14010af89  mov     [rsp+1A8h+var_170], rcx
0x14010af8e  mov     byte ptr [rsp+1A8h+Buffer], r8b
0x14010af93  mov     dword ptr [rsp+1A8h+DeleteCount], 2
0x14010af9b  mov     [rsp+1A8h+RestartKey], rax
0x14010afa0  mov     r8, r14
0x14010afa3  mov     rcx, r15
0x14010afa6  call    TxfOpenFileCheckId
0x14010afab  test    eax, eax
0x14010afad  js      loc_14010BBF0
0x14010afb3  mov     rsi, [rsp+1A8h+FileObject]
0x14010afbb  mov     rsi, [rsi+18h]
0x14010afbf  mov     [rsp+1A8h+var_98], rsi
0x14010afc7  xor     r8d, r8d
0x14010afca  mov     rdx, rsi
0x14010afcd  mov     rcx, r15
0x14010afd0  call    NtfsAcquireExclusiveScbEx
0x14010afd5  mov     rdx, [rsi+0B8h]
0x14010afdc  mov     rcx, r12; plsn1
0x14010afdf  cmp     [rsp+1A8h+var_157], 0
0x14010afe4  jz      short loc_14010B026
0x14010afe6  add     rdx, 0F0h; plsn2
0x14010afed  call    cs:__imp_ClfsLsnLess
0x14010aff4  nop     dword ptr [rax+rax+00h]
0x14010aff9  test    al, al
0x14010affb  jnz     loc_14010BBF0
0x14010b001  mov     al, cs:NtfsStatusDebugFlags
0x14010b007  test    al, al
0x14010b009  jz      loc_14010BBF0
0x14010b00f  mov     edx, 0C0000102h
0x14010b014  xor     ecx, ecx
0x14010b016  mov     r8d, 3174F6h
0x14010b01c  call    NtfsStatusTraceAndDebugInternal
0x14010b021  jmp     loc_14010BBF0
0x14010b026  add     rdx, 100h; plsn2
0x14010b02d  call    cs:__imp_ClfsLsnLess
0x14010b034  nop     dword ptr [rax+rax+00h]
0x14010b039  test    al, al
0x14010b03b  jnz     loc_14010BBF0
0x14010b041  xor     r9d, r9d
0x14010b044  mov     r8, [rsp+1A8h+var_A8]
0x14010b04c  mov     rdx, rsi
0x14010b04f  mov     rcx, r15
0x14010b052  call    TxfRebuildTxfStructuresForRecovery
0x14010b057  mov     rax, [rsi+210h]
0x14010b05e  mov     rcx, [rax+38h]
0x14010b062  mov     [rsp+1A8h+var_148], rcx
0x14010b067  cmp     qword ptr [rax+58h], 0
0x14010b06c  jnz     short loc_14010B072
0x14010b06e  mov     [rax+58h], rsi
0x14010b072  xor     r8d, r8d
0x14010b075  mov     rdx, [rsi+0B8h]
0x14010b07c  mov     rcx, r15
0x14010b07f  call    NtfsReleaseFcbEx
0x14010b084  mov     eax, [r14+78h]
0x14010b088  test    al, 1
0x14010b08a  jnz     loc_14010B1DF
0x14010b090  mov     rcx, [r14+68h]
0x14010b094  add     rcx, r13
0x14010b097  cmp     [rsi+20h], rcx
0x14010b09b  jge     loc_14010B1DF
0x14010b0a1  mov     rdx, [rsi+0B8h]
0x14010b0a8  add     rdx, 0F0h; plsn2
0x14010b0af  mov     rcx, r12; plsn1
0x14010b0b2  call    cs:__imp_ClfsLsnLess
0x14010b0b9  nop     dword ptr [rax+rax+00h]
0x14010b0be  test    al, al
0x14010b0c0  jz      short loc_14010B0EF
0x14010b0c2  mov     rcx, [rsi+20h]
0x14010b0c6  mov     rdx, [r14+68h]
0x14010b0ca  cmp     rdx, rcx
0x14010b0cd  jge     loc_14010BBF0
0x14010b0d3  lea     rax, [rdx+r13]
0x14010b0d7  cmp     rax, rcx
0x14010b0da  jle     short loc_14010B0EF
0x14010b0dc  mov     r13d, ecx
0x14010b0df  sub     r13d, edx
0x14010b0e2  mov     [rsp+1A8h+var_140], r13d
0x14010b0e7  mov     [rsp+1A8h+var_80], r13d
0x14010b0ef  mov     edx, r13d
0x14010b0f2  add     rdx, [r14+68h]
0x14010b0f6  cmp     [rsi+20h], rdx
0x14010b0fa  jge     loc_14010B1DF
0x14010b100  mov     [rsp+1A8h+FileInformation], 0
0x14010b10c  mov     [rsp+1A8h+FileInformation], rdx
0x14010b114  lea     r9, [rsp+1A8h+FileInformation]; FileInformation
0x14010b11c  mov     edx, 14h; FileInformationClass
0x14010b121  lea     r8d, [rdx-0Ch]; Length
0x14010b125  mov     rcx, [rsp+1A8h+FileObject]; FileObject
0x14010b12d  call    cs:__imp_IoSetInformation
0x14010b134  nop     dword ptr [rax+rax+00h]
0x14010b139  mov     ebx, eax
0x14010b13b  mov     edx, 0C0000188h
0x14010b140  cmp     [r15+18h], edx
0x14010b144  jnz     short loc_14010B16E
0x14010b146  mov     al, cs:NtfsStatusDebugFlags
0x14010b14c  test    al, al
0x14010b14e  jz      short loc_14010B15D
0x14010b150  xor     ecx, ecx
0x14010b152  mov     r8d, 440F81h
0x14010b158  call    NtfsStatusTraceAndDebugInternal
0x14010b15d  mov     ecx, [r15+18h]; Status
0x14010b161  call    cs:__imp_ExRaiseStatus
0x14010b16e  test    ebx, ebx
0x14010b170  jz      short loc_14010B1DF
0x14010b172  mov     al, cs:NtfsStatusDebugFlags
0x14010b178  test    al, al
0x14010b17a  jz      short loc_14010B1D1
0x14010b17c  lea     eax, [rbx-126h]
0x14010b182  test    eax, 0FFFFFFFAh
0x14010b187  jnz     short loc_14010B191
0x14010b189  cmp     ebx, 127h
0x14010b18f  jnz     short loc_14010B1D1
0x14010b191  cmp     ebx, 0FFFFFFEDh
0x14010b194  jnb     short loc_14010B1D1
0x14010b196  cmp     ebx, 0C00000D8h
0x14010b19c  jz      short loc_14010B1D1
0x14010b19e  cmp     ebx, 0C0000016h
0x14010b1a4  jz      short loc_14010B1D1
0x14010b1a6  cmp     ebx, 0C0000011h
0x14010b1ac  jz      short loc_14010B1D1
0x14010b1ae  lea     eax, [rbx+7FFFFFFBh]
0x14010b1b4  cmp     eax, 1
0x14010b1b7  jbe     short loc_14010B1D1
0x14010b1b9  cmp     ebx, 103h
0x14010b1bf  jz      short loc_14010B1D1
0x14010b1c1  mov     r8d, 31757Fh
0x14010b1c7  mov     edx, ebx
0x14010b1c9  mov     rcx, r15
0x14010b1cc  call    NtfsStatusTraceAndDebugInternal
0x14010b1d1  mov     ecx, ebx; Status
0x14010b1d3  call    cs:__imp_ExRaiseStatus
0x14010b1df  mov     r8b, 1
0x14010b1e2  mov     rdx, rsi
0x14010b1e5  mov     rcx, r15
0x14010b1e8  call    NtfsAcquireScbPagingResourceExclusive
0x14010b1ed  movzx   eax, al
0x14010b1f0  mov     [rsp+1A8h+var_120], eax
0x14010b1f7  mov     dl, 1; Wait
0x14010b1f9  mov     rcx, [rdi+58h]; Resource
0x14010b1fd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14010b204  nop     dword ptr [rax+rax+00h]
0x14010b209  mov     [rsp+1A8h+var_155], 1
0x14010b20e  mov     rdx, [rdi]
0x14010b211  mov     rcx, r15
0x14010b214  call    NtfsAcquireScbPagingResourceShared
0x14010b219  mov     [rsp+1A8h+var_156], al
0x14010b21d  mov     [rsp+1A8h+var_100], 0
0x14010b228  xor     ecx, ecx
0x14010b22a  mov     [rsp+1A8h+var_100], ecx
0x14010b231  cmp     ecx, 2
0x14010b234  jnb     short loc_14010B262
0x14010b236  mov     r8d, ecx
0x14010b239  mov     rdx, [r15+rcx*8+30h]
0x14010b23e  test    rdx, rdx
0x14010b241  jz      short loc_14010B253
0x14010b243  mov     rax, [rdi]
0x14010b246  cmp     rdx, [rax+0B8h]
0x14010b24d  jz      short loc_14010B253
0x14010b24f  inc     ecx
0x14010b251  jmp     short loc_14010B22A
0x14010b253  mov     rax, [rdi]
0x14010b256  mov     rcx, [rax+0B8h]
0x14010b25d  mov     [r15+r8*8+30h], rcx
0x14010b262  mov     [rsp+1A8h+DeleteCount], 0
0x14010b26b  mov     [rsp+1A8h+RestartKey], 0
0x14010b274  xor     r9d, r9d
0x14010b277  xor     r8d, r8d
0x14010b27a  mov     rdx, rsi
0x14010b27d  mov     rcx, r15
0x14010b280  call    NtfsCreateInternalAttributeStream
0x14010b285  test    byte ptr [r14], 2
0x14010b289  jz      loc_14010B9EF
0x14010b28f  test    byte ptr [r14+9Eh], 2
0x14010b297  jz      loc_14010B9EF
0x14010b29d  mov     rax, [r14+88h]
0x14010b2a4  mov     [rsp+1A8h+var_D0], rax
0x14010b2ac  mov     rbx, [rsp+1A8h+var_130]
0x14010b2b1  mov     ecx, [r14+98h]
0x14010b2b8  add     rcx, [r14+88h]
0x14010b2bf  mov     eax, [rdi+18h]
0x14010b2c2  cmp     rax, rcx
0x14010b2c5  jnb     short loc_14010B2DC
0x14010b2c7  mov     r8d, [rdi+28h]
0x14010b2cb  add     r8d, 40h ; '@'
0x14010b2cf  mov     rdx, rbx
0x14010b2d2  mov     rcx, r15
0x14010b2d5  call    TxfExtendTopsStream
0x14010b2da  jmp     short loc_14010B2B1
0x14010b2dc  shl     [rsp+1A8h+var_D0], 0Ch
0x14010b2e5  mov     ebx, [r14+0A0h]
0x14010b2ec  mov     [rsp+1A8h+var_FC], ebx
0x14010b2f3  mov     rax, [r14+80h]
0x14010b2fa  shl     rax, 0Ch
0x14010b2fe  mov     qword ptr [rsp+1A8h+var_138], rax
0x14010b303  mov     r12d, 200h
0x14010b309  mov     rax, qword ptr [rsp+1A8h+var_138]
0x14010b30e  shr     rax, 0Ch
0x14010b312  mov     [rsp+1A8h+MatchData], rax
0x14010b31a  lea     eax, [rbx+0FFFh]
0x14010b320  shr     eax, 0Ch
0x14010b323  mov     [rsp+1A8h+var_60], eax
0x14010b32a  mov     [rsp+1A8h+var_B0], 0
0x14010b336  mov     rdi, [rsp+1A8h+var_148]
0x14010b33b  mov     rcx, [rdi+100h]; FastMutex
0x14010b342  call    cs:__imp_ExAcquireFastMutex
0x14010b349  nop     dword ptr [rax+rax+00h]
0x14010b34e  mov     [rsp+1A8h+var_158], 1
0x14010b353  lea     rcx, [rsp+1A8h+MatchData]
0x14010b35b  mov     [rsp+1A8h+Buffer], rcx; Buffer
0x14010b360  lea     rcx, [rsp+1A8h+var_D8]
0x14010b368  mov     [rsp+1A8h+DeleteCount], rcx; DeleteCount
0x14010b36d  lea     rcx, [rsp+1A8h+var_B0]
0x14010b375  mov     [rsp+1A8h+RestartKey], rcx; RestartKey
0x14010b37a  xor     r9d, r9d; NextFlag
0x14010b37d  lea     r8, [rsp+1A8h+MatchData]; MatchData
0x14010b385  lea     rdx, TxfMatchPageRange; MatchFunction
0x14010b38c  lea     rcx, [rdi+98h]; Table
0x14010b393  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x14010b39a  nop     dword ptr [rax+rax+00h]
0x14010b39f  mov     r13, rax
0x14010b3a2  mov     rcx, [rdi+100h]; FastMutex
0x14010b3a9  call    cs:__imp_ExReleaseFastMutex
0x14010b3b0  nop     dword ptr [rax+rax+00h]
0x14010b3b5  xor     eax, eax
0x14010b3b7  mov     [rsp+1A8h+var_158], al
0x14010b3bb  test    r13, r13
0x14010b3be  jz      short loc_14010B41A
0x14010b3c0  mov     rdi, [r13+0]
0x14010b3c4  cmp     rdi, [rsp+1A8h+MatchData]
0x14010b3cc  ja      short loc_14010B411
0x14010b3ce  mov     edx, [r13+18h]
0x14010b3d2  lea     rcx, [rdx+rdi]
0x14010b3d6  mov     eax, [rsp+1A8h+var_60]
0x14010b3dd  add     rax, [rsp+1A8h+MatchData]
0x14010b3e5  cmp     rcx, rax
0x14010b3e8  jnb     loc_14010B804
0x14010b3ee  shl     rcx, 0Ch
0x14010b3f2  mov     qword ptr [rsp+1A8h+var_138], rcx
  ... truncated ...
```
