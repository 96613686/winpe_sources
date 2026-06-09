# TxfRedoWriteFile

- ea: `0x14010adfc`
- end: `0x14010bc9a`
- name: `TxfRedoWriteFile`
- size: `3742`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x140133f30`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x140012e70`
- `0x1400531d4`
- `0x140059250`
- `0x1400593c0`
- `0x1400b6e90`
- `0x14010033c`
- `0x140100b14`
- `0x14010adfc`
- `0x1401331f4`
- `0x140140380`
- `0x140163f78`
- `0x140208f3c`
- `0x14020bb70`
- `0x1402447d0`
- `0x140294b1c`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14010b726`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14010b726`
- `ntoskrnl!CcMapData` at `0x14010b4c0`
- `ntoskrnl!CcMapData` at `0x14010b58d`
- `ntoskrnl!CcMapData` at `0x14010b4c0`
- `ntoskrnl!CcMapData` at `0x14010b58d`
- `ntoskrnl!CcPinMappedData` at `0x14010b552`
- `ntoskrnl!CcPinMappedData` at `0x14010b552`
- `ntoskrnl!CcPreparePinWrite` at `0x14010ba27`
- `ntoskrnl!CcPreparePinWrite` at `0x14010baa3`
- `ntoskrnl!CcPreparePinWrite` at `0x14010ba27`
- `ntoskrnl!CcPreparePinWrite` at `0x14010baa3`
- `ntoskrnl!IoSetInformation` at `0x14010b0dd`
- `ntoskrnl!IoSetInformation` at `0x14010b0dd`
- `ntoskrnl!KeReleaseMutex` at `0x14010b8c9`
- `ntoskrnl!KeReleaseMutex` at `0x14010b8c9`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14010b343`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14010b343`
- `ntoskrnl!DbgPrintEx` at `0x14010b47d`
- `ntoskrnl!DbgPrintEx` at `0x14010b47d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010b7e7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010b7e7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010b1ad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010b80a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010b1ad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14010b80a`
- `ntoskrnl!CcUnpinData` at `0x14010b5d3`
- `ntoskrnl!CcUnpinData` at `0x14010b643`
- `ntoskrnl!CcUnpinData` at `0x14010bbbd`
- `ntoskrnl!CcUnpinData` at `0x14010bbd6`
- `ntoskrnl!CcUnpinData` at `0x14010bbef`
- `ntoskrnl!CcUnpinData` at `0x1402c5b7e`
- `ntoskrnl!CcUnpinData` at `0x1402c5b97`
- `ntoskrnl!CcUnpinData` at `0x1402c5bb0`
- `ntoskrnl!CcUnpinData` at `0x14010b5d3`
- `ntoskrnl!CcUnpinData` at `0x14010b643`
- `ntoskrnl!CcUnpinData` at `0x14010bbbd`
- `ntoskrnl!CcUnpinData` at `0x14010bbd6`
- `ntoskrnl!CcUnpinData` at `0x14010bbef`
- `ntoskrnl!CcUnpinData` at `0x1402c5b7e`
- `ntoskrnl!CcUnpinData` at `0x1402c5b97`
- `ntoskrnl!CcUnpinData` at `0x1402c5bb0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010b8ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bc09`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bc50`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bc6a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5bca`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c18`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c39`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010b8ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bc09`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bc50`
- `ntoskrnl!ExReleaseResourceLite` at `0x14010bc6a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5bca`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c18`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c5c39`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010b2f2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010b6e9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010b2f2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14010b6e9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010b359`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010b76d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c5b65`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010b359`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010b76d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c5b65`
- `ntoskrnl!ExRaiseStatus` at `0x14010b111`
- `ntoskrnl!ExRaiseStatus` at `0x14010b183`
- `ntoskrnl!ExRaiseStatus` at `0x14010b111`
- `ntoskrnl!ExRaiseStatus` at `0x14010b183`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14010b828`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14010b828`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010af9d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010afdd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010b062`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010af9d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010afdd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010b062`

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
0x14010adfc  mov     r11, rsp
0x14010adff  push    rbx
0x14010ae00  push    rsi
0x14010ae01  push    rdi
0x14010ae02  push    r12
0x14010ae04  push    r13
0x14010ae06  push    r14
0x14010ae08  push    r15
0x14010ae0a  sub     rsp, 170h
0x14010ae11  mov     rax, cs:__security_cookie
0x14010ae18  xor     rax, rsp
0x14010ae1b  mov     [rsp+1A8h+var_40], rax
0x14010ae23  mov     r12, r9
0x14010ae26  mov     [rsp+1A8h+var_A0], r9
0x14010ae2e  mov     r14, r8
0x14010ae31  mov     [rsp+1A8h+var_A8], rdx
0x14010ae39  mov     r15, rcx
0x14010ae3c  mov     [rsp+1A8h+var_90], rcx
0x14010ae44  xor     r8d, r8d
0x14010ae47  mov     [r11-128h], r8
0x14010ae4e  mov     [r11-0E0h], r8
0x14010ae55  mov     [r11-110h], r8
0x14010ae5c  mov     [r11-0F0h], r8
0x14010ae63  mov     [r11-108h], r8
0x14010ae6a  mov     [r11-118h], r8
0x14010ae71  mov     [r11-0C0h], r8
0x14010ae78  mov     [r11-120h], r8d
0x14010ae7f  mov     [rsp+1A8h+var_156], r8b
0x14010ae84  mov     [rsp+1A8h+var_155], r8b
0x14010ae89  mov     esi, r8d
0x14010ae8c  mov     [r11-98h], r8
0x14010ae93  mov     rax, [rdx+0D0h]
0x14010ae9a  mov     [rsp+1A8h+var_130], rax
0x14010ae9f  mov     [rsp+1A8h+var_88], rax
0x14010aea7  lea     rdi, [rax+118h]
0x14010aeae  mov     [rsp+1A8h+var_B8], rdi
0x14010aeb6  mov     [r11-0D8h], r8d
0x14010aebd  mov     [r11-0B0h], r8
0x14010aec4  mov     qword ptr [rsp+1A8h+var_138], r8
0x14010aec9  mov     qword ptr [rsp+1A8h+var_150], r8
0x14010aece  mov     [rsp+1A8h+var_148], r8
0x14010aed3  mov     [rsp+1A8h+var_158], sil
0x14010aed8  mov     r13d, [r14+70h]
0x14010aedc  mov     [rsp+1A8h+var_140], r13d
0x14010aee1  mov     ecx, r8d
0x14010aee4  mov     [rsp+1A8h+var_C8], rcx
0x14010aeec  xorps   xmm0, xmm0
0x14010aeef  xor     eax, eax
0x14010aef1  movups  xmmword ptr [r11-78h], xmm0
0x14010aef6  movups  xmmword ptr [r11-68h], xmm0
0x14010aefb  movups  xmmword ptr [r11-58h], xmm0
0x14010af00  mov     [r11-48h], eax
0x14010af04  mov     [rsp+1A8h+var_154], al
0x14010af08  mov     [rsp+1A8h+var_F8], eax
0x14010af0f  mov     [rsp+1A8h+var_157], r8b
0x14010af14  lea     rax, [r14+60h]
0x14010af18  lea     r9, [r14+50h]
0x14010af1c  lea     rcx, [r11-0E0h]
0x14010af23  mov     [rsp+1A8h+var_160], rcx
0x14010af28  lea     rcx, [r11-128h]
0x14010af2f  mov     [rsp+1A8h+var_168], rcx
0x14010af34  lea     rcx, [rsp+1A8h+var_157]
0x14010af39  mov     [rsp+1A8h+var_170], rcx
0x14010af3e  mov     byte ptr [rsp+1A8h+Buffer], r8b
0x14010af43  mov     dword ptr [rsp+1A8h+DeleteCount], 2
0x14010af4b  mov     [rsp+1A8h+RestartKey], rax
0x14010af50  mov     r8, r14
0x14010af53  mov     rcx, r15
0x14010af56  call    TxfOpenFileCheckId
0x14010af5b  test    eax, eax
0x14010af5d  js      loc_14010BBA0
0x14010af63  mov     rsi, [rsp+1A8h+FileObject]
0x14010af6b  mov     rsi, [rsi+18h]
0x14010af6f  mov     [rsp+1A8h+var_98], rsi
0x14010af77  xor     r8d, r8d
0x14010af7a  mov     rdx, rsi
0x14010af7d  mov     rcx, r15
0x14010af80  call    NtfsAcquireExclusiveScbEx
0x14010af85  mov     rdx, [rsi+0B8h]
0x14010af8c  mov     rcx, r12; plsn1
0x14010af8f  cmp     [rsp+1A8h+var_157], 0
0x14010af94  jz      short loc_14010AFD6
0x14010af96  add     rdx, 0F0h; plsn2
0x14010af9d  call    cs:__imp_ClfsLsnLess
0x14010afa4  nop     dword ptr [rax+rax+00h]
0x14010afa9  test    al, al
0x14010afab  jnz     loc_14010BBA0
0x14010afb1  mov     al, cs:NtfsStatusDebugFlags
0x14010afb7  test    al, al
0x14010afb9  jz      loc_14010BBA0
0x14010afbf  mov     edx, 0C0000102h
0x14010afc4  xor     ecx, ecx
0x14010afc6  mov     r8d, 3174F6h
0x14010afcc  call    NtfsStatusTraceAndDebugInternal
0x14010afd1  jmp     loc_14010BBA0
0x14010afd6  add     rdx, 100h; plsn2
0x14010afdd  call    cs:__imp_ClfsLsnLess
0x14010afe4  nop     dword ptr [rax+rax+00h]
0x14010afe9  test    al, al
0x14010afeb  jnz     loc_14010BBA0
0x14010aff1  xor     r9d, r9d
0x14010aff4  mov     r8, [rsp+1A8h+var_A8]
0x14010affc  mov     rdx, rsi
0x14010afff  mov     rcx, r15
0x14010b002  call    TxfRebuildTxfStructuresForRecovery
0x14010b007  mov     rax, [rsi+210h]
0x14010b00e  mov     rcx, [rax+38h]
0x14010b012  mov     [rsp+1A8h+var_148], rcx
0x14010b017  cmp     qword ptr [rax+58h], 0
0x14010b01c  jnz     short loc_14010B022
0x14010b01e  mov     [rax+58h], rsi
0x14010b022  xor     r8d, r8d
0x14010b025  mov     rdx, [rsi+0B8h]
0x14010b02c  mov     rcx, r15
0x14010b02f  call    NtfsReleaseFcbEx
0x14010b034  mov     eax, [r14+78h]
0x14010b038  test    al, 1
0x14010b03a  jnz     loc_14010B18F
0x14010b040  mov     rcx, [r14+68h]
0x14010b044  add     rcx, r13
0x14010b047  cmp     [rsi+20h], rcx
0x14010b04b  jge     loc_14010B18F
0x14010b051  mov     rdx, [rsi+0B8h]
0x14010b058  add     rdx, 0F0h; plsn2
0x14010b05f  mov     rcx, r12; plsn1
0x14010b062  call    cs:__imp_ClfsLsnLess
0x14010b069  nop     dword ptr [rax+rax+00h]
0x14010b06e  test    al, al
0x14010b070  jz      short loc_14010B09F
0x14010b072  mov     rcx, [rsi+20h]
0x14010b076  mov     rdx, [r14+68h]
0x14010b07a  cmp     rdx, rcx
0x14010b07d  jge     loc_14010BBA0
0x14010b083  lea     rax, [rdx+r13]
0x14010b087  cmp     rax, rcx
0x14010b08a  jle     short loc_14010B09F
0x14010b08c  mov     r13d, ecx
0x14010b08f  sub     r13d, edx
0x14010b092  mov     [rsp+1A8h+var_140], r13d
0x14010b097  mov     [rsp+1A8h+var_80], r13d
0x14010b09f  mov     edx, r13d
0x14010b0a2  add     rdx, [r14+68h]
0x14010b0a6  cmp     [rsi+20h], rdx
0x14010b0aa  jge     loc_14010B18F
0x14010b0b0  mov     [rsp+1A8h+FileInformation], 0
0x14010b0bc  mov     [rsp+1A8h+FileInformation], rdx
0x14010b0c4  lea     r9, [rsp+1A8h+FileInformation]; FileInformation
0x14010b0cc  mov     edx, 14h; FileInformationClass
0x14010b0d1  lea     r8d, [rdx-0Ch]; Length
0x14010b0d5  mov     rcx, [rsp+1A8h+FileObject]; FileObject
0x14010b0dd  call    cs:__imp_IoSetInformation
0x14010b0e4  nop     dword ptr [rax+rax+00h]
0x14010b0e9  mov     ebx, eax
0x14010b0eb  mov     edx, 0C0000188h
0x14010b0f0  cmp     [r15+18h], edx
0x14010b0f4  jnz     short loc_14010B11E
0x14010b0f6  mov     al, cs:NtfsStatusDebugFlags
0x14010b0fc  test    al, al
0x14010b0fe  jz      short loc_14010B10D
0x14010b100  xor     ecx, ecx
0x14010b102  mov     r8d, 440F81h
0x14010b108  call    NtfsStatusTraceAndDebugInternal
0x14010b10d  mov     ecx, [r15+18h]; Status
0x14010b111  call    cs:__imp_ExRaiseStatus
0x14010b11e  test    ebx, ebx
0x14010b120  jz      short loc_14010B18F
0x14010b122  mov     al, cs:NtfsStatusDebugFlags
0x14010b128  test    al, al
0x14010b12a  jz      short loc_14010B181
0x14010b12c  lea     eax, [rbx-126h]
0x14010b132  test    eax, 0FFFFFFFAh
0x14010b137  jnz     short loc_14010B141
0x14010b139  cmp     ebx, 127h
0x14010b13f  jnz     short loc_14010B181
0x14010b141  cmp     ebx, 0FFFFFFEDh
0x14010b144  jnb     short loc_14010B181
0x14010b146  cmp     ebx, 0C00000D8h
0x14010b14c  jz      short loc_14010B181
0x14010b14e  cmp     ebx, 0C0000016h
0x14010b154  jz      short loc_14010B181
0x14010b156  cmp     ebx, 0C0000011h
0x14010b15c  jz      short loc_14010B181
0x14010b15e  lea     eax, [rbx+7FFFFFFBh]
0x14010b164  cmp     eax, 1
0x14010b167  jbe     short loc_14010B181
0x14010b169  cmp     ebx, 103h
0x14010b16f  jz      short loc_14010B181
0x14010b171  mov     r8d, 31757Fh
0x14010b177  mov     edx, ebx
0x14010b179  mov     rcx, r15
0x14010b17c  call    NtfsStatusTraceAndDebugInternal
0x14010b181  mov     ecx, ebx; Status
0x14010b183  call    cs:__imp_ExRaiseStatus
0x14010b18f  mov     r8b, 1
0x14010b192  mov     rdx, rsi
0x14010b195  mov     rcx, r15
0x14010b198  call    NtfsAcquireScbPagingResourceExclusive
0x14010b19d  movzx   eax, al
0x14010b1a0  mov     [rsp+1A8h+var_120], eax
0x14010b1a7  mov     dl, 1; Wait
0x14010b1a9  mov     rcx, [rdi+58h]; Resource
0x14010b1ad  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14010b1b4  nop     dword ptr [rax+rax+00h]
0x14010b1b9  mov     [rsp+1A8h+var_155], 1
0x14010b1be  mov     rdx, [rdi]
0x14010b1c1  mov     rcx, r15
0x14010b1c4  call    NtfsAcquireScbPagingResourceShared
0x14010b1c9  mov     [rsp+1A8h+var_156], al
0x14010b1cd  mov     [rsp+1A8h+var_100], 0
0x14010b1d8  xor     ecx, ecx
0x14010b1da  mov     [rsp+1A8h+var_100], ecx
0x14010b1e1  cmp     ecx, 2
0x14010b1e4  jnb     short loc_14010B212
0x14010b1e6  mov     r8d, ecx
0x14010b1e9  mov     rdx, [r15+rcx*8+30h]
0x14010b1ee  test    rdx, rdx
0x14010b1f1  jz      short loc_14010B203
0x14010b1f3  mov     rax, [rdi]
0x14010b1f6  cmp     rdx, [rax+0B8h]
0x14010b1fd  jz      short loc_14010B203
0x14010b1ff  inc     ecx
0x14010b201  jmp     short loc_14010B1DA
0x14010b203  mov     rax, [rdi]
0x14010b206  mov     rcx, [rax+0B8h]
0x14010b20d  mov     [r15+r8*8+30h], rcx
0x14010b212  mov     [rsp+1A8h+DeleteCount], 0
0x14010b21b  mov     [rsp+1A8h+RestartKey], 0
0x14010b224  xor     r9d, r9d
0x14010b227  xor     r8d, r8d
0x14010b22a  mov     rdx, rsi
0x14010b22d  mov     rcx, r15
0x14010b230  call    NtfsCreateInternalAttributeStream
0x14010b235  test    byte ptr [r14], 2
0x14010b239  jz      loc_14010B99F
0x14010b23f  test    byte ptr [r14+9Eh], 2
0x14010b247  jz      loc_14010B99F
0x14010b24d  mov     rax, [r14+88h]
0x14010b254  mov     [rsp+1A8h+var_D0], rax
0x14010b25c  mov     rbx, [rsp+1A8h+var_130]
0x14010b261  mov     ecx, [r14+98h]
0x14010b268  add     rcx, [r14+88h]
0x14010b26f  mov     eax, [rdi+18h]
0x14010b272  cmp     rax, rcx
0x14010b275  jnb     short loc_14010B28C
0x14010b277  mov     r8d, [rdi+28h]
0x14010b27b  add     r8d, 40h ; '@'
0x14010b27f  mov     rdx, rbx
0x14010b282  mov     rcx, r15
0x14010b285  call    TxfExtendTopsStream
0x14010b28a  jmp     short loc_14010B261
0x14010b28c  shl     [rsp+1A8h+var_D0], 0Ch
0x14010b295  mov     ebx, [r14+0A0h]
0x14010b29c  mov     [rsp+1A8h+var_FC], ebx
0x14010b2a3  mov     rax, [r14+80h]
0x14010b2aa  shl     rax, 0Ch
0x14010b2ae  mov     qword ptr [rsp+1A8h+var_138], rax
0x14010b2b3  mov     r12d, 200h
0x14010b2b9  mov     rax, qword ptr [rsp+1A8h+var_138]
0x14010b2be  shr     rax, 0Ch
0x14010b2c2  mov     [rsp+1A8h+MatchData], rax
0x14010b2ca  lea     eax, [rbx+0FFFh]
0x14010b2d0  shr     eax, 0Ch
0x14010b2d3  mov     [rsp+1A8h+var_60], eax
0x14010b2da  mov     [rsp+1A8h+var_B0], 0
0x14010b2e6  mov     rdi, [rsp+1A8h+var_148]
0x14010b2eb  mov     rcx, [rdi+100h]; FastMutex
0x14010b2f2  call    cs:__imp_ExAcquireFastMutex
0x14010b2f9  nop     dword ptr [rax+rax+00h]
0x14010b2fe  mov     [rsp+1A8h+var_158], 1
0x14010b303  lea     rcx, [rsp+1A8h+MatchData]
0x14010b30b  mov     [rsp+1A8h+Buffer], rcx; Buffer
0x14010b310  lea     rcx, [rsp+1A8h+var_D8]
0x14010b318  mov     [rsp+1A8h+DeleteCount], rcx; DeleteCount
0x14010b31d  lea     rcx, [rsp+1A8h+var_B0]
0x14010b325  mov     [rsp+1A8h+RestartKey], rcx; RestartKey
0x14010b32a  xor     r9d, r9d; NextFlag
0x14010b32d  lea     r8, [rsp+1A8h+MatchData]; MatchData
0x14010b335  lea     rdx, TxfMatchPageRange; MatchFunction
0x14010b33c  lea     rcx, [rdi+98h]; Table
0x14010b343  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x14010b34a  nop     dword ptr [rax+rax+00h]
0x14010b34f  mov     r13, rax
0x14010b352  mov     rcx, [rdi+100h]; FastMutex
0x14010b359  call    cs:__imp_ExReleaseFastMutex
0x14010b360  nop     dword ptr [rax+rax+00h]
0x14010b365  xor     eax, eax
0x14010b367  mov     [rsp+1A8h+var_158], al
0x14010b36b  test    r13, r13
0x14010b36e  jz      short loc_14010B3CA
0x14010b370  mov     rdi, [r13+0]
0x14010b374  cmp     rdi, [rsp+1A8h+MatchData]
0x14010b37c  ja      short loc_14010B3C1
0x14010b37e  mov     edx, [r13+18h]
0x14010b382  lea     rcx, [rdx+rdi]
0x14010b386  mov     eax, [rsp+1A8h+var_60]
0x14010b38d  add     rax, [rsp+1A8h+MatchData]
0x14010b395  cmp     rcx, rax
0x14010b398  jnb     loc_14010B7B4
0x14010b39e  shl     rcx, 0Ch
0x14010b3a2  mov     qword ptr [rsp+1A8h+var_138], rcx
  ... truncated ...
```
