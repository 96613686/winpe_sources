# NtfsDeallocateClusters

- ea: `0x14015f620`
- end: `0x140160246`
- name: `NtfsDeallocateClusters`
- size: `3110`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, LONGLONG, __int64, __int64 *)`
- caller_count: `5`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1400cf580`
- `0x140160250`
- `0x1401629fc`
- `0x1401700a0`
- `0x1401e26a0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x140012e70`
- `0x140014e74`
- `0x1400211b0`
- `0x1400286d0`
- `0x14003c210`
- `0x14003c34c`
- `0x14003ecfc`
- `0x14003f474`
- `0x14003f7cc`
- `0x14003fc48`
- `0x140040210`
- `0x14004062c`
- `0x1400596c0`
- `0x14015f620`
- `0x140165278`
- `0x1401730f0`
- `0x1401c0b50`
- `0x1401fd140`
- `0x1401fda90`
- `0x140215720`
- `0x140223a60`

## import_xrefs

- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14015ffab`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14015ffab`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x14015f9fe`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x14015f9fe`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14015fca7`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14015fca7`
- `ntoskrnl!RtlCompressBuffer` at `0x14015fd83`
- `ntoskrnl!RtlCompressBuffer` at `0x14015fd83`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140160003`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x1402a8d63`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140160003`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x1402a8d63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015fdc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140160079`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a8dfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015fdc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140160079`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a8dfe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015fd0d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015fd0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14015fc44`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a8cf7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14015fc44`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a8cf7`
- `ntoskrnl!ExRaiseStatus` at `0x14015fe43`
- `ntoskrnl!ExRaiseStatus` at `0x14015fe71`
- `ntoskrnl!ExRaiseStatus` at `0x14015fe43`
- `ntoskrnl!ExRaiseStatus` at `0x14015fe71`

## pseudocode

```c
__int64 __fastcall NtfsDeallocateClusters(__int64 a1, __int64 a2, __int64 a3, LONGLONG a4, __int64 a5, __int64 *a6)
{
  __int64 v6; // r12
  LONGLONG v10; // rdi
  _QWORD *v11; // r13
  _QWORD *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // r9d
  LONGLONG v18; // r12
  LONGLONG v19; // rdi
  __int64 v20; // rcx
  char v21; // r15
  __int64 DeallocatedClusters; // rax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r12
  __int64 *v28; // rdi
  _WORD *v29; // rcx
  struct _ERESOURCE *v30; // rcx
  __int16 v31; // cx
  NTSTATUS CompressionWorkSpaceSize; // edi
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  SIZE_T v35; // rdx
  unsigned int v36; // edi
  char *PoolWithTag; // rax
  char *v38; // r15
  __int64 v39; // r8
  char *v40; // rdi
  LONGLONG v41; // r8
  int v42; // ecx
  int v43; // eax
  __int64 v44; // r9
  int v45; // ecx
  ULONG *v46; // rcx
  __int64 v47; // rdx
  LONGLONG v48; // rax
  bool v49; // sf
  __int64 v50; // rcx
  __int64 v51; // rdi
  __int64 v52; // r15
  __int64 v53; // rcx
  PVOID v54; // rcx
  _DWORD *v55; // rdi
  unsigned __int8 v56; // r13
  __int64 v57; // rcx
  __int64 v59; // rcx
  ULONG UncompressedChunkSize[2]; // [rsp+80h] [rbp-110h]
  PULONG FinalCompressedSize; // [rsp+88h] [rbp-108h]
  unsigned __int8 v62; // [rsp+A8h] [rbp-E8h]
  char v63; // [rsp+A9h] [rbp-E7h]
  LONGLONG SectorCount; // [rsp+B0h] [rbp-E0h] BYREF
  char v65; // [rsp+B8h] [rbp-D8h]
  char v66[4]; // [rsp+BCh] [rbp-D4h]
  ULONG CompressBufferWorkSpaceSize; // [rsp+C0h] [rbp-D0h] BYREF
  ULONG CompressFragmentWorkSpaceSize; // [rsp+C4h] [rbp-CCh] BYREF
  LONGLONG v69; // [rsp+C8h] [rbp-C8h]
  __int64 v70; // [rsp+D0h] [rbp-C0h]
  PVOID P; // [rsp+D8h] [rbp-B8h]
  _QWORD *v72; // [rsp+E0h] [rbp-B0h]
  LONGLONG Vbn; // [rsp+E8h] [rbp-A8h] BYREF
  LONGLONG v74; // [rsp+F0h] [rbp-A0h]
  LONGLONG v75; // [rsp+F8h] [rbp-98h]
  __int64 *v76; // [rsp+100h] [rbp-90h]
  __int64 v77; // [rsp+108h] [rbp-88h]
  __int64 v78; // [rsp+110h] [rbp-80h]
  __int64 v79; // [rsp+118h] [rbp-78h]
  _DWORD *v80; // [rsp+120h] [rbp-70h]
  _DWORD *v81; // [rsp+128h] [rbp-68h]
  _QWORD *v82; // [rsp+130h] [rbp-60h]
  _DWORD *v83; // [rsp+138h] [rbp-58h]
  __int64 v84; // [rsp+140h] [rbp-50h]
  __int64 v85; // [rsp+148h] [rbp-48h]
  LONGLONG v86; // [rsp+1B0h] [rbp+20h]

  v86 = a4;
  v6 = a4;
  v84 = a3;
  Vbn = 0;
  SectorCount = 0;
  v10 = 0;
  v69 = 0;
  v78 = -1;
  v79 = -1;
  v62 = 0;
  v63 = 0;
  v70 = 0;
  P = 0;
  v11 = (_QWORD *)(a1 + 16);
  if ( (!a1 || (*(_DWORD *)v11 & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
  {
    McTemplateU0ppppii_EtwWriteTransfer(a5, (const EVENT_DESCRIPTOR *)bitmpsup_c3189, a1, a2, a3, a3 + 400, a4, a5);
  }
  v82 = v11;
  if ( (!a1 || (*(_DWORD *)v11 & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
  {
    McTemplateU0pppi_EtwWriteTransfer(
      a1,
      (const EVENT_DESCRIPTOR *)bitmpsup_c3201,
      a2,
      *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL),
      v6,
      a5);
  }
  v76 = (__int64 *)(a2 + 48);
  v12 = (_QWORD *)(a3 + 184);
  v72 = (_QWORD *)(a3 + 184);
  if ( *(_QWORD *)(a3 + 184) == *(_QWORD *)(*(_QWORD *)(a2 + 48) + 184LL)
    && *(_DWORD *)(a3 + 256) == 32
    && (!a1 || (*(_DWORD *)v11 & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 2) != 0 )
  {
    McTemplateU0ppppii_EtwWriteTransfer(a5, (const EVENT_DESCRIPTOR *)bitmpsup_c3212, a1, a2, a3, a3 + 400, v6, a5);
    v12 = v72;
  }
  v81 = (_DWORD *)(a3 + 256);
  if ( *(_DWORD *)(a3 + 256) != 128
    || (v13 = *v12, *(_DWORD *)(*v12 + 8LL) < 0x10u)
    || (v14 = *(_QWORD *)(a2 + 40)) != 0 && v13 == *(_QWORD *)(v14 + 184)
    || (*(_DWORD *)v66 = 0, (*(_DWORD *)(v13 + 4) & 0x8000) != 0) )
  {
    *(_DWORD *)v66 = 2;
  }
  NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(a2 + 72), 0);
  if ( NtfsTrimListLengthThreshold )
  {
    v16 = *(_QWORD *)(a1 + 104);
    v17 = *(_DWORD *)(v16 + 1512);
    if ( v17 > NtfsTrimListLengthThreshold && (*(_BYTE *)(a1 + 32) != 13 || *(_BYTE *)(a1 + 33) == 2) )
    {
      if ( (*(_DWORD *)v11 & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0pd_EtwWriteTransfer(v15, (const EVENT_DESCRIPTOR *)delnotify_c2941, v16, v17);
      }
      v59 = a1;
      if ( a1 != *(_QWORD *)(a1 + 144) )
        v59 = *(_QWORD *)(a1 + 144);
      *(_QWORD *)(v59 + 16) |= 0x20000uLL;
      NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 3738516);
    }
  }
  v83 = (_DWORD *)(a2 + 4);
  if ( (*(_DWORD *)(a2 + 4) & 0x80u) != 0 )
    NtfsScanEntireBitmap(a1, a2, 10, 2);
  while ( 1 )
  {
    v77 = v6;
    if ( v6 > a5 )
      break;
    v85 = a3 + 400;
    if ( !NtfsLookupNtfsMcbEntryWithSyncFlag(a3 + 400, v6, &Vbn, &SectorCount, 0, 0, 0, 0) )
      break;
    v18 = Vbn;
    if ( Vbn == -1 )
    {
      v27 = v86;
      goto LABEL_100;
    }
    v74 = 0;
    v75 = 0;
    v19 = SectorCount;
    v20 = v86;
    if ( SectorCount + v86 > a5 )
    {
      v19 = a5 - v86 + 1;
      SectorCount = v19;
    }
    v80 = (_DWORD *)(a3 + 512);
    if ( (*(_DWORD *)(a3 + 512) & 0x800000) != 0
      || *v81 == 128 && *(_DWORD *)(a3 + 452) && (*(_BYTE *)(a3 + 4) & 0x20) != 0 )
    {
      v20 = *(unsigned __int8 *)(a2 + 488);
      if ( (unsigned __int64)(v19 << v20) > 0xFFFFFFFF )
      {
        v20 = *(unsigned int *)(a2 + 488);
        v19 = 0xFFFFFFFFuLL >> v20;
        SectorCount = 0xFFFFFFFFuLL >> v20;
      }
    }
    v74 = Vbn;
    v75 = v19;
    if ( (!a1 || (*(_DWORD *)v11 & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0pppi_EtwWriteTransfer(
        v20,
        (const EVENT_DESCRIPTOR *)bitmpsup_c3317,
        a2,
        *(_QWORD *)(*v72 + 8LL),
        Vbn,
        v19);
    }
    v21 = 0;
    DeallocatedClusters = NtfsGetDeallocatedClusters(a1, a2, 0);
    v70 = DeallocatedClusters;
    if ( DeallocatedClusters )
      FsRtlAddBaseMcbEntry((PBASE_MCB)(DeallocatedClusters + 16), v18, v18, v19);
    else
      v21 = 1;
    if ( v21 )
    {
      if ( (!a1 || (*(_DWORD *)v11 & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v23, (const EVENT_DESCRIPTOR *)bitmpsup_c3360, a2);
      }
      *(_DWORD *)(a1 + 392) = 6;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC0000188, 0x40D27u);
      NtfsRaiseStatusInternal(a1, -1073741432, 0, 0, 265511);
    }
    v24 = v70;
    *(_QWORD *)(v70 + 48) += v19;
    if ( (!a1 || (*(_DWORD *)v11 & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      LODWORD(FinalCompressedSize) = *(_DWORD *)(v24 + 56);
      McTemplateU0ppiidii_EtwWriteTransfer(
        *(_QWORD *)(a2 + 312),
        (const EVENT_DESCRIPTOR *)bitmpsup_c3377,
        a2,
        v24,
        *(_QWORD *)(v24 + 40),
        *(_QWORD *)(v24 + 48),
        FinalCompressedSize,
        *(_QWORD *)(a2 + 312),
        *(_QWORD *)(a2 + 312) + v19);
    }
    *(_QWORD *)(a2 + 312) += v19;
    *(_QWORD *)(a1 + 184) += v19;
    v69 = v19;
    v78 = v19 + v18;
    v79 = v19 + v18;
    *(_DWORD *)(a1 + 4) |= 0x1000u;
    NtfsFreeBitmapRun(a1, a2, v18, v66[0]);
    v62 = 1;
    v65 = 1;
    if ( !*(_DWORD *)(a3 + 452) || *(_BYTE *)(a3 + 460) )
    {
      v27 = v86;
    }
    else
    {
      v27 = v86;
      if ( (*(_BYTE *)(a3 + 4) & 0x20) != 0 )
        NtfsReserveClusters(a1, 1);
    }
    if ( (*v83 & 0x4000) != 0 && *(__int64 *)(a2 + 296) >> 4 < *(_QWORD *)(a2 + 304) )
    {
      v28 = v76;
      if ( NtfsAcquireResourceExclusive(v26, *v76, 0) )
      {
        NtfsScanEntireBitmap(a1, a2, 8, 4);
        NtfsInitializeMftZone(a1, a2, 0, 0);
        v29 = (_WORD *)*v28;
        if ( *(_WORD *)*v28 == 1794 )
          v30 = (struct _ERESOURCE *)(*((_QWORD *)v29 + 13) + 64LL);
        else
          v30 = (struct _ERESOURCE *)*((_QWORD *)v29 + 1);
        ExReleaseResourceLite(v30);
      }
    }
    if ( (*v80 & 0x800000) == 0 )
      goto LABEL_83;
    if ( (*v11 & 0x40000LL) == 0 )
    {
      *v11 |= 0x40000uLL;
      v63 = 1;
    }
    v31 = (unsigned __int8)*(_WORD *)(a3 + 460);
    if ( !(unsigned __int8)*(_WORD *)(a3 + 460) )
    {
      v45 = *(_DWORD *)(a2 + 488);
      v43 = (_DWORD)SectorCount << v45;
      v44 = v27 << v45;
      goto LABEL_75;
    }
    CompressBufferWorkSpaceSize = 0;
    CompressFragmentWorkSpaceSize = 0;
    CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(
                                 v31 + 1,
                                 &CompressBufferWorkSpaceSize,
                                 &CompressFragmentWorkSpaceSize);
    if ( CompressionWorkSpaceSize < 0 )
    {
      if ( NtfsStatusDebugFlags
        && (unsigned int)CompressionWorkSpaceSize < 0xFFFFFFED
        && CompressionWorkSpaceSize != -1073741802
        && (unsigned int)(CompressionWorkSpaceSize + 2147483643) > 1
        && CompressionWorkSpaceSize != -1073741807
        && CompressionWorkSpaceSize != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(a1, CompressionWorkSpaceSize, 0x40DBCu);
      }
      NtfsRaiseStatusInternal(a1, CompressionWorkSpaceSize, 0, 0, 265660);
    }
    v33 = *(_DWORD *)(a2 + 356);
    v80 = (_DWORD *)(2LL * v33);
    if ( (unsigned __int64)v80 > 0xFFFFFFFF )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000183, 0x40DC1u);
      ExRaiseStatus(-1073741437);
    }
    v34 = 2 * v33;
    v35 = v34 + CompressBufferWorkSpaceSize;
    if ( (unsigned int)v35 < v34 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000183, 0x40DC5u);
      ExRaiseStatus(-1073741437);
    }
    v36 = v34 + CompressBufferWorkSpaceSize;
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x410), v35, 0x5043744Eu);
    v38 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v36);
    P = v38;
    v39 = *(unsigned int *)(a2 + 356);
    v40 = &v38[v39];
    RtlCompressBuffer(
      (unsigned __int8)*(_WORD *)(a3 + 460) + 1,
      (PUCHAR)v38,
      v39,
      (PUCHAR)&v38[v39],
      *(_DWORD *)(a2 + 356),
      0x1000u,
      &CompressFragmentWorkSpaceSize,
      &v38[v39 + v39]);
    NtfsWriteBytes(a1, a2, a3, v27 << *(_BYTE *)(a2 + 488), v40, *(_DWORD *)(a2 + 356), 256);
    ExFreePoolWithTag(v38, 0);
    P = 0;
    v41 = SectorCount;
    if ( SectorCount > 1 )
    {
      v42 = *(_DWORD *)(a2 + 488);
      v43 = ((_DWORD)SectorCount - 1) << v42;
      v44 = (v27 + 1) << v42;
LABEL_75:
      NtfsWriteBytes(a1, a2, a3, v44, 0, v43, 256);
LABEL_83:
      v41 = SectorCount;
    }
    if ( a6 )
    {
      v46 = (ULONG *)(a3 + 200);
      if ( (*(_DWORD *)(a3 + 200) & 0x6000000) == 0 || (*(_DWORD *)v11 & 0x80000000) == 0 )
      {
        NtfsAdjustFcbAllocatedClusterCount(a1, *v72, -v41);
        v41 = SectorCount;
        v48 = SectorCount << *(_BYTE *)(a2 + 488);
        v49 = *a6 - v48 < 0;
        *a6 -= v48;
        v50 = *a6;
        if ( v49 )
        {
          *a6 = 0;
          v50 = 0;
        }
        if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) == 0 )
          goto LABEL_95;
        McTemplateU0ipip_EtwWriteTransfer(v50, v47, v41, a3, v50, a6);
        goto LABEL_94;
      }
    }
    else
    {
      v46 = (ULONG *)(v84 + 200);
    }
    if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
    {
      UncompressedChunkSize[0] = *v46;
      McTemplateU0ippdi_EtwWriteTransfer((__int64)v46, v25, v41, a3, a6, *(_QWORD *)UncompressedChunkSize, *v11);
LABEL_94:
      v41 = SectorCount;
    }
LABEL_95:
    v51 = v85;
    NtfsRemoveNtfsMcbEntry(v85, v27, v41);
    if ( v51 == *v76 + 400 || v51 == *(_QWORD *)(a2 + 208) + 400LL )
    {
      FsRtlAddLargeMcbEntry((PLARGE_MCB)(a3 + 672), v27, Vbn, SectorCount);
      v10 = v69;
    }
    else
    {
      v10 = v69;
    }
LABEL_100:
    v6 = SectorCount + v27;
    v86 = v6;
  }
  if ( v63 )
    *v11 &= ~0x40000uLL;
  if ( v10 )
  {
    v52 = v70;
    FsRtlRemoveBaseMcbEntry((PBASE_MCB)(v70 + 16), v78 - v10, v10);
    if ( (!a1 || (*(_DWORD *)v11 & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0ppp_EtwWriteTransfer(v53, (const EVENT_DESCRIPTOR *)bitmpsup_c3672, a2);
    }
    *(_QWORD *)(v52 + 48) -= v10;
    *(_QWORD *)(a2 + 312) -= v10;
  }
  NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(a2 + 72) + 184LL), 0);
  v54 = P;
  if ( P )
    ExFreePoolWithTag(P, 0);
  v55 = (_DWORD *)(a1 + 16);
  if ( a1 && (*v55 & 0x100000) != 0 || (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) == 0 )
  {
    v56 = v62;
  }
  else
  {
    v56 = v62;
    McTemplateU0pd_EtwWriteTransfer((__int64)v54, (const EVENT_DESCRIPTOR *)bitmpsup_c3693, a1, v62);
  }
  v57 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 184LL);
  if ( *(_QWORD *)(a3 + 184) == v57 && *(_DWORD *)(a3 + 256) == 32 )
  {
    if ( !a1 || (v57 = (unsigned int)*v55, (v57 & 0x100000) == 0) )
    {
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 2) != 0 )
        McTemplateU0pd_EtwWriteTransfer(v57, (const EVENT_DESCRIPTOR *)bitmpsup_c3702, a1, v56);
    }
  }
  return v56;
}

```

## disassembly

```asm
0x14015f620  mov     rax, rsp
0x14015f623  mov     [rax+20h], r9
0x14015f627  mov     [rax+18h], r8
0x14015f62b  mov     [rax+10h], rdx
0x14015f62f  mov     [rax+8], rcx
0x14015f633  push    rbx
0x14015f634  push    rsi
0x14015f635  push    rdi
0x14015f636  push    r12
0x14015f638  push    r13
0x14015f63a  push    r14
0x14015f63c  push    r15
0x14015f63e  sub     rsp, 100h
0x14015f645  mov     r12, r9
0x14015f648  mov     r14, r8
0x14015f64b  mov     rsi, rdx
0x14015f64e  mov     rbx, rcx
0x14015f651  mov     [rsp+138h+var_50], r8
0x14015f659  xor     r15d, r15d
0x14015f65c  mov     [rax-0A8h], r15
0x14015f663  mov     [rsp+138h+SectorCount], r15
0x14015f668  mov     edi, r15d
0x14015f66b  mov     [rsp+138h+var_C8], r15
0x14015f670  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14015f677  mov     [rax-80h], rdx
0x14015f67b  mov     [rax-78h], rdx
0x14015f67f  xor     r13b, r13b
0x14015f682  mov     [rsp+138h+var_E8], r13b
0x14015f687  mov     [rsp+138h+var_E7], dil
0x14015f68c  mov     [rsp+138h+var_C0], r15
0x14015f691  mov     [rax-0B8h], r15
0x14015f698  lea     r13, [rcx+10h]
0x14015f69c  test    rcx, rcx
0x14015f69f  jz      short loc_14015F6AC
0x14015f6a1  mov     eax, [r13+0]
0x14015f6a5  bt      rax, 14h
0x14015f6aa  jb      short loc_14015F6EA
0x14015f6ac  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 4
0x14015f6b3  jz      short loc_14015F6EA
0x14015f6b5  lea     rax, [r8+190h]
0x14015f6bc  mov     rcx, [rsp+138h+arg_20]
0x14015f6c4  mov     [rsp+138h+WorkSpace], rcx
0x14015f6c9  mov     [rsp+138h+FinalCompressedSize], r12
0x14015f6ce  mov     qword ptr [rsp+138h+UncompressedChunkSize], rax
0x14015f6d3  mov     qword ptr [rsp+138h+CompressedBufferSize], r14
0x14015f6d8  mov     r9, rsi
0x14015f6db  mov     r8, rbx
0x14015f6de  lea     rdx, bitmpsup_c3189
0x14015f6e5  call    McTemplateU0ppppii_EtwWriteTransfer
0x14015f6ea  mov     [rsp+138h+var_60], r13
0x14015f6f2  test    rbx, rbx
0x14015f6f5  jz      short loc_14015F702
0x14015f6f7  mov     eax, [r13+0]
0x14015f6fb  bt      rax, 14h
0x14015f700  jb      short loc_14015F737
0x14015f702  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14015f709  jz      short loc_14015F737
0x14015f70b  mov     r9, [r14+0B8h]
0x14015f712  mov     rax, [rsp+138h+arg_20]
0x14015f71a  mov     qword ptr [rsp+138h+UncompressedChunkSize], rax
0x14015f71f  mov     qword ptr [rsp+138h+CompressedBufferSize], r12
0x14015f724  mov     r9, [r9+8]
0x14015f728  mov     r8, rsi
0x14015f72b  lea     rdx, bitmpsup_c3201
0x14015f732  call    McTemplateU0pppi_EtwWriteTransfer
0x14015f737  lea     rax, [rsi+30h]
0x14015f73b  mov     [rsp+138h+var_90], rax
0x14015f743  lea     rdx, [r14+0B8h]
0x14015f74a  mov     [rsp+138h+var_B0], rdx
0x14015f752  mov     rax, [rax]
0x14015f755  mov     rcx, [rax+0B8h]
0x14015f75c  cmp     [rdx], rcx
0x14015f75f  jnz     short loc_14015F7C1
0x14015f761  cmp     dword ptr [r14+100h], 20h ; ' '
0x14015f769  jnz     short loc_14015F7C1
0x14015f76b  test    rbx, rbx
0x14015f76e  jz      short loc_14015F77B
0x14015f770  mov     eax, [r13+0]
0x14015f774  bt      rax, 14h
0x14015f779  jb      short loc_14015F7C1
0x14015f77b  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 2
0x14015f782  jz      short loc_14015F7C1
0x14015f784  lea     rax, [r14+190h]
0x14015f78b  mov     rcx, [rsp+138h+arg_20]
0x14015f793  mov     [rsp+138h+WorkSpace], rcx
0x14015f798  mov     [rsp+138h+FinalCompressedSize], r12
0x14015f79d  mov     qword ptr [rsp+138h+UncompressedChunkSize], rax
0x14015f7a2  mov     qword ptr [rsp+138h+CompressedBufferSize], r14
0x14015f7a7  mov     r9, rsi
0x14015f7aa  mov     r8, rbx
0x14015f7ad  lea     rdx, bitmpsup_c3212
0x14015f7b4  call    McTemplateU0ppppii_EtwWriteTransfer
0x14015f7b9  mov     rdx, [rsp+138h+var_B0]
0x14015f7c1  lea     rax, [r14+100h]
0x14015f7c8  mov     [rsp+138h+var_68], rax
0x14015f7d0  cmp     dword ptr [rax], 80h
0x14015f7d6  jnz     short loc_14015F801
0x14015f7d8  mov     rax, [rdx]
0x14015f7db  cmp     dword ptr [rax+8], 10h
0x14015f7df  jb      short loc_14015F801
0x14015f7e1  mov     rcx, [rsi+28h]
0x14015f7e5  test    rcx, rcx
0x14015f7e8  jz      short loc_14015F7F3
0x14015f7ea  cmp     rax, [rcx+0B8h]
0x14015f7f1  jz      short loc_14015F801
0x14015f7f3  mov     dword ptr [rsp+138h+var_D4], r15d
0x14015f7f8  test    dword ptr [rax+4], 8000h
0x14015f7ff  jz      short loc_14015F809
0x14015f801  mov     dword ptr [rsp+138h+var_D4], 2
0x14015f809  xor     r8d, r8d
0x14015f80c  mov     rdx, [rsi+48h]
0x14015f810  mov     rcx, rbx
0x14015f813  call    NtfsAcquireExclusiveScbEx
0x14015f818  nop
0x14015f819  mov     eax, cs:NtfsTrimListLengthThreshold
0x14015f81f  test    eax, eax
0x14015f821  jz      short loc_14015F847
0x14015f823  mov     r8, [rbx+68h]
0x14015f827  mov     r9d, [r8+5E8h]
0x14015f82e  cmp     r9d, eax
0x14015f831  jbe     short loc_14015F847
0x14015f833  cmp     byte ptr [rbx+20h], 0Dh
0x14015f837  jnz     loc_140160120
0x14015f83d  cmp     byte ptr [rbx+21h], 2
0x14015f841  jz      loc_140160120
0x14015f847  lea     rax, [rsi+4]
0x14015f84b  mov     [rsp+138h+var_58], rax
0x14015f853  mov     eax, [rax]
0x14015f855  test    al, al
0x14015f857  jns     short loc_14015F870
0x14015f859  mov     r9d, 2
0x14015f85f  mov     r8d, 0Ah
0x14015f865  mov     rdx, rsi
0x14015f868  mov     rcx, rbx
0x14015f86b  call    NtfsScanEntireBitmap
0x14015f870  mov     [rsp+138h+var_88], r12
0x14015f878  cmp     r12, [rsp+138h+arg_20]
0x14015f880  jg      loc_14015FFD8
0x14015f886  lea     rax, [r14+190h]
0x14015f88d  mov     [rsp+138h+var_48], rax
0x14015f895  mov     [rsp+138h+WorkSpace], r15
0x14015f89a  mov     [rsp+138h+FinalCompressedSize], r15
0x14015f89f  mov     qword ptr [rsp+138h+UncompressedChunkSize], r15
0x14015f8a4  mov     qword ptr [rsp+138h+CompressedBufferSize], r15
0x14015f8a9  lea     r9, [rsp+138h+SectorCount]
0x14015f8ae  lea     r8, [rsp+138h+Vbn]
0x14015f8b6  mov     rdx, r12
0x14015f8b9  mov     rcx, rax
0x14015f8bc  call    NtfsLookupNtfsMcbEntryWithSyncFlag
0x14015f8c1  test    al, al
0x14015f8c3  jz      loc_14015FFD8
0x14015f8c9  mov     r12, [rsp+138h+Vbn]
0x14015f8d1  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14015f8d5  jz      loc_14015FFBE
0x14015f8db  mov     [rsp+138h+var_A0], r15
0x14015f8e3  mov     [rsp+138h+var_98], r15
0x14015f8eb  mov     rdi, [rsp+138h+SectorCount]
0x14015f8f0  mov     rcx, [rsp+138h+arg_18]
0x14015f8f8  lea     rax, [rdi+rcx]
0x14015f8fc  mov     rdx, [rsp+138h+arg_20]
0x14015f904  cmp     rax, rdx
0x14015f907  jle     short loc_14015F917
0x14015f909  mov     rdi, rdx
0x14015f90c  sub     rdi, rcx
0x14015f90f  inc     rdi
0x14015f912  mov     [rsp+138h+SectorCount], rdi
0x14015f917  lea     rax, [r14+200h]
0x14015f91e  mov     [rsp+138h+var_70], rax
0x14015f926  test    dword ptr [rax], 800000h
0x14015f92c  jnz     short loc_14015F94F
0x14015f92e  mov     rax, [rsp+138h+var_68]
0x14015f936  cmp     dword ptr [rax], 80h
0x14015f93c  jnz     short loc_14015F976
0x14015f93e  cmp     dword ptr [r14+1C4h], 0
0x14015f946  jz      short loc_14015F976
0x14015f948  test    byte ptr [r14+4], 20h
0x14015f94d  jz      short loc_14015F976
0x14015f94f  movzx   ecx, byte ptr [rsi+1E8h]
0x14015f956  mov     rax, rdi
0x14015f959  shl     rax, cl
0x14015f95c  mov     edx, 0FFFFFFFFh
0x14015f961  cmp     rax, rdx
0x14015f964  jbe     short loc_14015F976
0x14015f966  mov     ecx, [rsi+1E8h]
0x14015f96c  mov     edi, edx
0x14015f96e  shr     rdi, cl
0x14015f971  mov     [rsp+138h+SectorCount], rdi
0x14015f976  mov     [rsp+138h+var_A0], r12
0x14015f97e  mov     [rsp+138h+var_98], rdi
0x14015f986  test    rbx, rbx
0x14015f989  jz      short loc_14015F996
0x14015f98b  mov     eax, [r13+0]
0x14015f98f  bt      rax, 14h
0x14015f994  jb      short loc_14015F9C7
0x14015f996  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14015f99d  jz      short loc_14015F9C7
0x14015f99f  mov     rax, [rsp+138h+var_B0]
0x14015f9a7  mov     r9, [rax]
0x14015f9aa  mov     qword ptr [rsp+138h+UncompressedChunkSize], rdi
0x14015f9af  mov     qword ptr [rsp+138h+CompressedBufferSize], r12
0x14015f9b4  mov     r9, [r9+8]
0x14015f9b8  mov     r8, rsi
0x14015f9bb  lea     rdx, bitmpsup_c3317
0x14015f9c2  call    McTemplateU0pppi_EtwWriteTransfer
0x14015f9c7  xor     r15b, r15b
0x14015f9ca  mov     [rsp+138h+var_E6], r15b
0x14015f9cf  xor     r8d, r8d
0x14015f9d2  mov     rdx, rsi
0x14015f9d5  mov     rcx, rbx
0x14015f9d8  call    NtfsGetDeallocatedClusters
0x14015f9dd  mov     [rsp+138h+var_C0], rax
0x14015f9e2  test    rax, rax
0x14015f9e5  jnz     short loc_14015F9F1
0x14015f9e7  mov     r15b, 1
0x14015f9ea  mov     [rsp+138h+var_E6], r15b
0x14015f9ef  jmp     short loc_14015FA0A
0x14015f9f1  lea     rcx, [rax+10h]; Mcb
0x14015f9f5  mov     r9, rdi; SectorCount
0x14015f9f8  mov     r8, r12; Lbn
0x14015f9fb  mov     rdx, r12; Vbn
0x14015f9fe  call    cs:__imp_FsRtlAddBaseMcbEntry
0x14015fa05  nop     dword ptr [rax+rax+00h]
0x14015fa0a  jmp     loc_14015FAB8
0x14015fa0f  mov     edx, eax
0x14015fa11  movzx   eax, cs:NtfsStatusDebugFlags
0x14015fa18  test    al, al
0x14015fa1a  jz      short loc_14015FA70
0x14015fa1c  test    edx, edx
0x14015fa1e  jz      short loc_14015FA70
0x14015fa20  cmp     edx, 126h
0x14015fa26  jz      short loc_14015FA70
0x14015fa28  lea     eax, [rdx-12Ah]
0x14015fa2e  cmp     eax, 1
0x14015fa31  jbe     short loc_14015FA70
0x14015fa33  cmp     edx, 0FFFFFFEDh
0x14015fa36  jnb     short loc_14015FA70
0x14015fa38  cmp     edx, 0C0000016h
0x14015fa3e  jz      short loc_14015FA70
0x14015fa40  lea     eax, [rdx+7FFFFFFBh]
0x14015fa46  cmp     eax, 1
0x14015fa49  jbe     short loc_14015FA70
0x14015fa4b  cmp     edx, 0C0000011h
0x14015fa51  jz      short loc_14015FA70
0x14015fa53  cmp     edx, 103h
0x14015fa59  jz      short loc_14015FA70
0x14015fa5b  cmp     edx, 0C00000D8h
0x14015fa61  jz      short loc_14015FA70
0x14015fa63  xor     ecx, ecx
0x14015fa65  mov     r8d, 40D1Ah
0x14015fa6b  call    NtfsStatusTraceAndDebugInternal
0x14015fa70  mov     r15b, 1
0x14015fa73  mov     [rsp+138h+var_E6], r15b
0x14015fa78  mov     r14, [rsp+138h+arg_10]
0x14015fa80  mov     rsi, [rsp+138h+arg_8]
0x14015fa88  mov     rbx, [rsp+138h+arg_0]
0x14015fa90  mov     rcx, [rsp+138h+var_88]
0x14015fa98  mov     [rsp+138h+arg_18], rcx
0x14015faa0  mov     r12, [rsp+138h+var_A0]
0x14015faa8  mov     rdi, [rsp+138h+var_98]
0x14015fab0  mov     r13, [rsp+138h+var_60]
0x14015fab8  test    r15b, r15b
0x14015fabb  jnz     loc_14016017C
0x14015fac1  mov     r8, [rsp+138h+var_C0]
0x14015fac6  add     [r8+30h], rdi
0x14015faca  mov     rdx, [r8+30h]
0x14015face  test    rbx, rbx
0x14015fad1  jz      short loc_14015FADE
0x14015fad3  mov     eax, [r13+0]
0x14015fad7  bt      rax, 14h
0x14015fadc  jb      short loc_14015FB24
0x14015fade  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14015fae5  jz      short loc_14015FB24
0x14015fae7  mov     rcx, [rsi+138h]
0x14015faee  lea     rax, [rcx+rdi]
0x14015faf2  mov     [rsp+138h+var_F8], rax
0x14015faf7  mov     [rsp+138h+WorkSpace], rcx
0x14015fafc  mov     eax, [r8+38h]
0x14015fb00  mov     dword ptr [rsp+138h+FinalCompressedSize], eax
0x14015fb04  mov     qword ptr [rsp+138h+UncompressedChunkSize], rdx
0x14015fb09  mov     rax, [r8+28h]
0x14015fb0d  mov     qword ptr [rsp+138h+CompressedBufferSize], rax
0x14015fb12  mov     r9, r8
0x14015fb15  mov     r8, rsi
0x14015fb18  lea     rdx, bitmpsup_c3377
0x14015fb1f  call    McTemplateU0ppiidii_EtwWriteTransfer
0x14015fb24  add     [rsi+138h], rdi
0x14015fb2b  add     [rbx+0B8h], rdi
0x14015fb32  mov     [rsp+138h+var_C8], rdi
0x14015fb37  lea     rax, [rdi+r12]
0x14015fb3b  mov     [rsp+138h+var_80], rax
0x14015fb43  mov     [rsp+138h+var_78], rax
0x14015fb4b  or      dword ptr [rbx+4], 1000h
0x14015fb52  mov     eax, dword ptr [rsp+138h+var_D4]
0x14015fb56  mov     [rsp+138h+CompressedBufferSize], eax; char
0x14015fb5a  lea     r9, [rsp+138h+var_C8]
0x14015fb5f  mov     r8, r12; int
0x14015fb62  mov     rdx, rsi; int
0x14015fb65  mov     rcx, rbx; int
0x14015fb68  call    NtfsFreeBitmapRun
0x14015fb6d  mov     al, 1
  ... truncated ...
```
