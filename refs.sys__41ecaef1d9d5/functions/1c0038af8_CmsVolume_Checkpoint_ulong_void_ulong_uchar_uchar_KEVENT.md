# CmsVolume::Checkpoint(ulong,void *,ulong,uchar *,uchar *,_KEVENT *)

- ea: `0x1c0038af8`
- end: `0x1c0039841`
- name: `?Checkpoint@CmsVolume@@QEAAJKPEAXKPEAE1PEAU_KEVENT@@@Z`
- size: `3401`
- prototype: `__int64 __usercall@<rax>(CmsVolume *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned __int8 *, struct _KEVENT *)`
- caller_count: `2`
- callee_count: `36`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c004cef0`
- `0x1c0052880`

## callees

- `0x1c001e400`
- `0x1c00224d0`
- `0x1c002357c`
- `0x1c0030504`
- `0x1c00339ac`
- `0x1c00348e8`
- `0x1c0034e34`
- `0x1c0038af8`
- `0x1c003b95c`
- `0x1c00439f0`
- `0x1c004d164`
- `0x1c004d1c0`
- `0x1c004ea78`
- `0x1c0051fb8`
- `0x1c0052a54`
- `0x1c00535c0`
- `0x1c005b4ac`
- `0x1c005d2ec`
- `0x1c005eacc`
- `0x1c005edc4`
- `0x1c005fb08`
- `0x1c0061664`
- `0x1c00638b0`
- `0x1c0063c94`
- `0x1c0063e38`
- `0x1c0064274`
- `0x1c00642c4`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006af80`
- `0x1c00be698`
- `0x1c00bebf0`
- `0x1c00bfd70`
- `0x1c00c2368`
- `0x1c00e7cc4`
- `0x1c01747f4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0038e71`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0038e71`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c003978b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c003978b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0038d4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0039713`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00397e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0038d4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0039713`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c00397e8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0038c30`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0038cea`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0038c30`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0038cea`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0039279`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0039279`
- `ntoskrnl!KeSetEvent` at `0x1c0038d62`
- `ntoskrnl!KeSetEvent` at `0x1c00397a3`
- `ntoskrnl!KeSetEvent` at `0x1c0039802`
- `ntoskrnl!KeSetEvent` at `0x1c0038d62`
- `ntoskrnl!KeSetEvent` at `0x1c00397a3`
- `ntoskrnl!KeSetEvent` at `0x1c0039802`
- `ntoskrnl!RtlCompareMemory` at `0x1c00391a0`
- `ntoskrnl!RtlCompareMemory` at `0x1c00391a0`
- `HAL!KeQueryPerformanceCounter` at `0x1c0038dd3`
- `HAL!KeQueryPerformanceCounter` at `0x1c0038de7`
- `HAL!KeQueryPerformanceCounter` at `0x1c0039658`
- `HAL!KeQueryPerformanceCounter` at `0x1c0038dd3`
- `HAL!KeQueryPerformanceCounter` at `0x1c0038de7`
- `HAL!KeQueryPerformanceCounter` at `0x1c0039658`

## pseudocode

```c
__int64 __fastcall CmsVolume::Checkpoint(
        CmsVolume *this,
        int a2,
        void *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        struct _KEVENT *a7)
{
  int v7; // eax
  int v8; // r13d
  unsigned int v10; // r14d
  _QWORD *v11; // r15
  int v12; // eax
  char *v14; // rax
  unsigned __int8 v15; // dl
  int updated; // esi
  __int64 v17; // r8
  CmsVolumeAnalyzer *v18; // rcx
  PERESOURCE v19; // r13
  __int64 v20; // rdx
  __int64 v21; // r9
  int v22; // ecx
  SIZE_T v23; // rbx
  struct _ERESOURCE *v24; // rcx
  __int64 v25; // rcx
  _QWORD *PoolWithTag; // rax
  __int64 v27; // rcx
  __int64 v28; // rax
  struct CmsTransactionContext *v29; // rax
  struct CmsTransactionContext *v30; // rdx
  CmsReadCache *v31; // rcx
  struct CmsTransactionContext *v32; // r12
  int CacheMetadata; // eax
  unsigned __int64 v34; // rdx
  __int64 v35; // rax
  bool v36; // cf
  __int64 *v37; // rbx
  struct _SmsCheckpointRecord *v38; // rdx
  __int64 v39; // rdx
  struct CmsTransactionContext *v40; // rdx
  int ActivityIdThread; // eax
  _DWORD *v42; // r8
  int v43; // ecx
  int v44; // r9d
  int v45; // eax
  char v46; // bl
  __int64 v47; // rbx
  __int64 v48; // r11
  struct CmsBPlusTable *v49; // rax
  __int64 v50; // rdx
  int v51; // r10d
  __int64 v52; // rdx
  __int64 v53; // rdx
  unsigned __int8 v54; // zf
  __int64 v55; // rbx
  char v56; // bl
  unsigned __int8 v57; // al
  int v58; // r14d
  __int64 v59; // r9
  LONGLONG v60; // r8
  unsigned __int32 v61; // edx
  __int64 v62; // r9
  unsigned __int8 v63; // dl
  CmsVolumeAnalyzer *v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rax
  int Timeout; // [rsp+28h] [rbp-E0h]
  int v68; // [rsp+30h] [rbp-D8h]
  unsigned int v69; // [rsp+30h] [rbp-D8h]
  int v70; // [rsp+30h] [rbp-D8h]
  size_t Size; // [rsp+38h] [rbp-D0h]
  int v72; // [rsp+40h] [rbp-C8h]
  __int16 v73; // [rsp+68h] [rbp-A0h] BYREF
  char v74; // [rsp+6Ah] [rbp-9Eh]
  __int16 v75; // [rsp+6Bh] [rbp-9Dh]
  unsigned __int8 v76; // [rsp+6Dh] [rbp-9Bh]
  unsigned __int8 v77; // [rsp+6Eh] [rbp-9Ah]
  PERESOURCE Resource; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v79; // [rsp+78h] [rbp-90h]
  _BYTE v80[12]; // [rsp+7Ch] [rbp-8Ch]
  int v81; // [rsp+88h] [rbp-80h]
  int v82; // [rsp+8Ch] [rbp-7Ch]
  int v83; // [rsp+90h] [rbp-78h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+98h] [rbp-70h] BYREF
  int v85; // [rsp+A0h] [rbp-68h]
  void *Source2; // [rsp+A8h] [rbp-60h]
  LARGE_INTEGER PerformanceCounter; // [rsp+B0h] [rbp-58h]
  PRKEVENT Event; // [rsp+B8h] [rbp-50h]
  __int64 v89; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v90; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v91; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v92; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v93; // [rsp+E0h] [rbp-28h]
  void *v94[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v95; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v96; // [rsp+100h] [rbp-8h]
  __int64 v97; // [rsp+110h] [rbp+8h]
  __int64 v98; // [rsp+118h] [rbp+10h] BYREF
  __int128 v99; // [rsp+120h] [rbp+18h]
  __int64 v100; // [rsp+130h] [rbp+28h]
  _DWORD v101[24]; // [rsp+138h] [rbp+30h] BYREF
  struct _KWAIT_BLOCK v102; // [rsp+198h] [rbp+90h] BYREF

  v79 = a4;
  Source2 = a3;
  v93 = 0;
  PerformanceFrequency.QuadPart = 0;
  Resource = 0;
  *(_DWORD *)&v80[8] = 0;
  *(_QWORD *)v80 = a2 & 0x20;
  v7 = *((_DWORD *)this + 779);
  v76 = (a2 & 0x20) != 0;
  v8 = a2 & 0x80;
  v81 = -1073741823;
  v82 = 0;
  v92 = 0;
  v77 = (a2 & 0x100) != 0;
  v73 = 0;
  v10 = a2 & 0xFFFFFE5F;
  v11 = 0;
  v75 = 0;
  v83 = v8;
  v85 = a2 & 0x100;
  v12 = v7 & 2;
  if ( v12 && v10 == 1 )
    return 0;
  if ( (a2 & 2) == 0 || (a2 & 1) != 0 || (v74 = 1, v12) )
    v74 = 0;
  v14 = (char *)this + 1512;
  Event = (PRKEVENT)((char *)this + 1512);
  while ( 1 )
  {
    if ( a7 )
    {
      v94[0] = v14;
      v94[1] = a7;
      if ( MsWaitForMultipleObjects(2u, v94, &v102, a4) )
        return 3221225760LL;
    }
    else
    {
      KeWaitForSingleObject(v14, Executive, 0, 0, 0);
    }
    updated = CmsVolume::UpdateTreesBoundToCheckpoint(this);
    if ( updated < 0 )
      goto LABEL_139;
    if ( *((_BYTE *)this + 3114) )
    {
      memset(v101, 0, 0x58u);
      LOBYTE(v17) = 1;
      v101[19] = 1;
      MsAcquireFastResourceExclusive(&VolumeLazyWriterResource, v101, v17);
      *((_DWORD *)this + 603) = 0;
      MsReleaseFastResource(&VolumeLazyWriterResource, v101);
      MsCleanupFastResourceOwnerEntry(v101);
    }
    if ( v8 )
    {
      v18 = (CmsVolumeAnalyzer *)*((_QWORD *)this + 383);
      if ( v18 )
        CmsVolumeAnalyzer::CancelVolumeAnalysis(v18, v15, 0, 0);
    }
    CmsVolume::AcquireForCheckpoint(this, (struct _SmsCheckpointContext **)&Resource);
    v19 = Resource;
    if ( !*((_BYTE *)this + 3113) )
      break;
    KeWaitForSingleObject(&Resource[1], Executive, 0, 0, 0);
    if ( *(PERESOURCE *)&v19[1].ActiveEntries == (PERESOURCE)&v19[1].ActiveEntries
      || (*((_DWORD *)this + 779) & 0x20000000) != 0 )
    {
      *((_DWORD *)this + 788) = 0;
      v22 = v10 & 1;
      goto LABEL_25;
    }
    v21 = *((_QWORD *)this + 193);
    LOBYTE(v68) = 0;
    *(_QWORD *)&v80[4] = *((_QWORD *)this + 221);
    CmsVolume::TransitionCheckpointState(this, v20, v19, *(_QWORD *)(v21 + 112), *(_QWORD *)&v80[4], v68);
    CmsVolume::EnableNextCheckpoint(this, (struct _SmsCheckpointContext *)v19);
    ExReleaseResourceLite(v19);
    KeSetEvent((PRKEVENT)this + 63, 0, 0);
    v8 = v83;
    v14 = (char *)this + 1512;
  }
  v22 = v10 & 1;
  if ( (v10 & 1) != 0 )
  {
    CmsVolume::EnableNextCheckpoint(this, (struct _SmsCheckpointContext *)Resource);
    v24 = Resource;
    goto LABEL_138;
  }
LABEL_25:
  if ( (*((_DWORD *)this + 779) & 0x20000000) != 0 )
  {
    v23 = 0;
    v79 = 0;
    Source2 = 0;
    if ( v22 )
    {
      CmsVolume::EnableNextCheckpoint(this, (struct _SmsCheckpointContext *)v19);
      v24 = v19;
LABEL_138:
      ExReleaseResourceLite(v24);
      updated = -1073741202;
LABEL_139:
      KeSetEvent(Event, 0, 0);
      return (unsigned int)updated;
    }
  }
  else
  {
    v23 = v79;
  }
  Event = (PRKEVENT)KeQueryPerformanceCounter(0).QuadPart;
  KeQueryPerformanceCounter(&PerformanceFrequency);
  if ( qword_1C0136BA0 && *((_BYTE *)this + 3113) && !*(_DWORD *)v80 && *((__int64 *)this + 256) > 0 )
  {
    v25 = MEMORY[0xFFFFF78000000014] - *((_QWORD *)this + 257);
    if ( v25 <= *((_QWORD *)this + 256) )
    {
      if ( v25 < 0 )
        *((_QWORD *)this + 257) = MEMORY[0xFFFFF78000000014];
    }
    else
    {
      v93 = MEMORY[0xFFFFF78000000320];
      *((_QWORD *)this + 257) = MEMORY[0xFFFFF78000000014];
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0xC8u, 0x6950534Du);
      v11 = PoolWithTag;
      if ( PoolWithTag )
      {
        *(_DWORD *)PoolWithTag = 1;
        PoolWithTag[1] = *((_QWORD *)this + 6);
        *((_DWORD *)PoolWithTag + 4) = 0;
        PoolWithTag[3] = *((_QWORD *)this + 230);
        *((_DWORD *)PoolWithTag + 10) = v10;
        PoolWithTag[12] = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 379) + 32LL) + 32LL);
        PoolWithTag[13] = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 379) + 32LL) + 8LL)
                        - *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 379) + 32LL) + 32LL)
                        - *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 379) + 32LL) + 16LL);
        PoolWithTag[14] = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 379) + 32LL) + 24LL);
        PoolWithTag[15] = _InterlockedExchange64((volatile __int64 *)this + 272, 0);
        PoolWithTag[16] = _InterlockedExchange64((volatile __int64 *)this + 273, 0);
        PoolWithTag[17] = _InterlockedExchange64((volatile __int64 *)this + 274, 0);
        PoolWithTag[18] = _InterlockedExchange64((volatile __int64 *)this + 275, 0);
        *((_DWORD *)PoolWithTag + 38) = _InterlockedExchange((volatile __int32 *)this + 552, 0);
        PoolWithTag[20] = _InterlockedExchange64((volatile __int64 *)this + 277, 0);
        *((_DWORD *)PoolWithTag + 42) = _InterlockedExchange((volatile __int32 *)this + 556, 0);
        PoolWithTag[22] = _InterlockedExchange64((volatile __int64 *)this + 279, 0);
        *((_DWORD *)PoolWithTag + 46) = _InterlockedExchange((volatile __int32 *)this + 560, 0);
        PoolWithTag[24] = _InterlockedExchange64((volatile __int64 *)this + 281, 0);
        v27 = *((_QWORD *)this + 324);
        if ( !v27 || (*((_DWORD *)this + 779) & 2) != 0 )
        {
          PoolWithTag[10] = 0;
          PoolWithTag[11] = 0;
        }
        else
        {
          PoolWithTag[10] = *(_QWORD *)(v27 + 48);
          PoolWithTag[11] = *(_QWORD *)(*((_QWORD *)this + 324) + 56LL);
          v28 = *((_QWORD *)this + 324);
          *(_QWORD *)(v28 + 48) = 0;
          *(_QWORD *)(v28 + 56) = 0;
        }
      }
    }
    v19 = Resource;
  }
  CmsVolume::AggregatedCheckpointTelemetry(this, v76);
  v29 = CmsTransactionContext::MakeFromReservedPool(this, (CmsVolume *)((char *)this + 88));
  v31 = (CmsReadCache *)*((_QWORD *)this + 325);
  v32 = v29;
  if ( v31 )
  {
    CacheMetadata = CmsReadCache::PersistReadCacheMetadata(v31, v29, v77, v76);
    v31 = 0;
    updated = CacheMetadata;
    if ( CacheMetadata < 0 )
      updated = 0;
  }
  if ( v85 != (_DWORD)v31 )
  {
    CmsVolume::ChangeVolumeOptionDynamically(this, 0x400u, 1u);
    v31 = 0;
  }
  if ( *(_DWORD *)v80 != (_DWORD)v31 )
  {
    CmsVolume::ChangeVolumeOptionDynamically(this, 0x8000u, 1u);
    v31 = 0;
  }
  *((_QWORD *)v32 + 2) |= 0x400uLL;
  if ( v11 )
  {
    if ( (*((_DWORD *)this + 779) & 2) != 0 )
    {
      v11[6] = v31;
      v11[7] = v31;
      v11[8] = v31;
    }
    else
    {
      v89 = (__int64)v31;
      v90 = (__int64)v31;
      v91 = (__int64)v31;
      CmsVolume::QueryClusterCounts(this, v30, &v89, &v90, &v91, (unsigned int *)v31);
      v11[6] = v89 << *((_DWORD *)this + 16);
      v11[7] = v90 << *((_DWORD *)this + 16);
      v11[8] = v91 << *((_DWORD *)this + 16);
    }
  }
  v34 = (unsigned __int64)CmsVolume::BindAndQueueGlobalTablesForCheckpoint(this, v32, v10, &v92);
  if ( v34 )
  {
    updated = CmsBPlusTable::UpdateBoundTrees(
                v32,
                (struct CmsBPlusTable *)v34,
                (struct _SmsCheckpointContext *)v19,
                v10,
                (unsigned __int8 *)&v73,
                v92);
    if ( updated < 0 || (*((_DWORD *)this + 779) & 0x20000000) != 0 && !v74 )
    {
      LOBYTE(v10) = v10 & 0xFE;
      v73 = 256;
      if ( updated < 0 )
      {
        LOBYTE(v75) = 1;
      }
      else
      {
        updated = -1073741668;
        v74 = 1;
      }
    }
    CmsTransactionContext::Commit(v32, 0, 0, 0);
  }
  if ( (v10 & 1) == 0 )
    goto LABEL_84;
  LOBYTE(v34) = v73;
  if ( (_BYTE)v73 )
    goto LABEL_72;
  v35 = *((_QWORD *)this + 193);
  if ( *(_DWORD *)(v35 + 140) != (_DWORD)v23 )
    goto LABEL_67;
  if ( !(_DWORD)v23 )
    goto LABEL_69;
  if ( RtlCompareMemory((const void *)(v35 + *(unsigned int *)(v35 + 136)), Source2, v23) == v23 )
  {
    LOBYTE(v34) = v73;
  }
  else
  {
LABEL_67:
    LOBYTE(v34) = 1;
    LOBYTE(v73) = 1;
  }
  if ( (_BYTE)v34 )
  {
LABEL_72:
    *((_DWORD *)this + 388) = 0;
    goto LABEL_75;
  }
LABEL_69:
  v34 = (unsigned __int8)v34;
  if ( *((_QWORD *)this + 361) )
    v34 = 1;
  LOBYTE(v73) = v34;
  if ( (_BYTE)v34 )
    goto LABEL_72;
  v36 = ++*((_DWORD *)this + 388) < 2u;
  HIBYTE(v75) = 1;
  if ( !v36 )
  {
LABEL_85:
    v46 = v75;
    goto LABEL_86;
  }
  LOBYTE(v34) = 1;
  LOBYTE(v73) = 1;
LABEL_75:
  if ( !(_BYTE)v34 )
    goto LABEL_85;
  v38 = (struct _SmsCheckpointRecord *)*((_QWORD *)this + 193);
  *(_QWORD *)&v80[4] = *((_QWORD *)this + 221);
  v37 = *(__int64 **)&v80[4];
  CmsVolume::FormatCheckpointRecord(this, v38, Source2, v79);
  v39 = *((_QWORD *)this + 193);
  v95 = *v37;
  v97 = 0;
  v96 = 0;
  CmsVolume::FormatPageHeader(this, v39, &v95, 0, 1347110979);
  if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    ActivityIdThread = IoGetActivityIdThread();
    McTemplateK0qii_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)"\v",
      ActivityIdThread,
      0,
      0,
      0);
  }
  v42 = (_DWORD *)*((_QWORD *)this + 193);
  v43 = *((_DWORD *)this + 16);
  v44 = *((_DWORD *)v37 + 2);
  v98 = *v37;
  v100 = 0;
  LODWORD(Size) = v42[23];
  v69 = v42[22];
  v99 = 0;
  CmsVolume::ComputeOrVerifySelfChecksumBlock(this, v40, v42, v44 << v43, (const union _LCN_TUPLE *)&v98, v69, Size, 0);
  v82 = CmsVolume::NotifyCheckpointFlushStart(this);
  if ( !v82 || (v45 = ((__int64 (__fastcall *)(_QWORD))qword_1C0136AB0)(*((_QWORD *)this + 6)), v81 = v45, v45 >= 0) )
  {
LABEL_84:
    LOBYTE(v34) = v73;
    goto LABEL_85;
  }
  LOBYTE(v10) = v10 & 0xFE;
  LOBYTE(v34) = 0;
  v73 = 256;
  v46 = 1;
  if ( HIBYTE(v75) )
    --*((_DWORD *)this + 388);
  updated = v45;
LABEL_86:
  if ( *((_BYTE *)this + 3113) )
  {
    CmsVolume::NotifyCheckpointFlushCompletion(this, v32, v82, v81);
    if ( (*((_DWORD *)this + 779) & 0x20000000) == 0 || v74 )
    {
      LOBYTE(v34) = v73;
    }
    else
    {
      LOBYTE(v34) = v73;
      LOBYTE(v10) = v10 & 0xFE;
      HIBYTE(v73) = 1;
      v46 = 0;
      if ( (_BYTE)v73 )
        CmsVolume::ReleaseCheckpointLocation(this, (struct _SmsCheckpointLocation *)v34, 0);
    }
  }
  if ( (v10 & 1) != 0 && (_BYTE)v34 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) == 0 )
    {
      v47 = *(_QWORD *)&v80[4];
    }
    else
    {
      v47 = *(_QWORD *)&v80[4];
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v48 = *((_QWORD *)this + 193);
        WPP_SF_Diiiiiiii(
          WPP_GLOBAL_Control->AttachedDevice,
          *(unsigned int *)(v48 + 148),
          *(unsigned int *)(v48 + 156),
          *((unsigned int *)this + 770),
          *(_QWORD *)(*(unsigned int *)(v48 + 196) + v48),
          *(_QWORD *)(*(unsigned int *)(v48 + 152) + v48),
          *(_QWORD *)(*(unsigned int *)(v48 + 156) + v48),
          *(_QWORD *)(*(unsigned int *)(v48 + 148) + v48),
          *(_QWORD *)(v48 + 96),
          *(_QWORD *)(v48 + 104),
          *(_QWORD *)(v48 + 112),
          **(_QWORD **)&v80[4]);
      }
    }
    v49 = CmsBPlusTable::BindableUnitTable(*(CmsBPlusTable **)(*((_QWORD *)this + 379) + 16LL));
    v70 = v51;
    updated = CmsVolume::SyncIo(this, *(_QWORD *)(*(_QWORD *)(v50 + 48) + 72LL), *((_QWORD *)v49 + 10) + 376LL);
    LOBYTE(v70) = updated >= 0;
    CmsVolume::TransitionCheckpointState(this, v52, v19, *(_QWORD *)(*((_QWORD *)this + 193) + 112LL), v47, v70);
    if ( updated < 0 )
    {
      v53 = 1;
      HIBYTE(v73) = 1;
      if ( HIBYTE(v75) )
        --*((_DWORD *)this + 388);
      v74 = 1;
      if ( qword_1C0136B38 )
      {
        LOBYTE(v72) = (*((_DWORD *)this + 779) & 0x40000000) != 0;
        LOBYTE(Timeout) = 1;
        qword_1C0136B38(*((_QWORD *)this + 6), 0, (unsigned int)updated, 0, Timeout, 0xB400904CALL, 0, v72);
      }
    }
    v54 = HIBYTE(v73) == 0;
  }
  else
  {
    if ( !v46 )
      goto LABEL_110;
    v55 = *(_QWORD *)&v80[4];
    if ( !*(_QWORD *)&v80[4] )
      v55 = *((_QWORD *)this + 221);
    LOBYTE(v68) = 0;
    CmsVolume::TransitionCheckpointState(this, v34, v19, *(_QWORD *)(*((_QWORD *)this + 193) + 112LL), v55, v68);
    v54 = HIBYTE(v73) == 0;
  }
  CmsVolume::ReleaseCheckpointLocation(this, (struct _SmsCheckpointLocation *)v53, v54);
LABEL_110:
  CmsTransactionContext::Commit(v32, 0, 0, 0);
  CmsReferenced::Release(v32);
  v56 = v74;
  if ( v74 )
    CmsVolume::ChangeVolumeOptionDynamically(this, 0x20000000u, 1u);
  if ( *(_DWORD *)v80 )
    *((_BYTE *)this + 3113) = 0;
  if ( a6 )
  {
    if ( *((__int64 *)this + 418) > 0 || *((int *)this + 786) > 0 || (v57 = 1, *((int *)this + 787) > 0) )
      v57 = 0;
    *a6 = v57;
  }
  CmsVolume::EnableNextCheckpoint(this, (struct _SmsCheckpointContext *)v19);
  v58 = v83;
  if ( v83 )
  {
    CmsVolume::JoinCheckpoint(this, (struct _SmsCheckpointContext **)this + 237);
    if ( a5 )
      *a5 = 1;
  }
  PerformanceCounter = KeQueryPerformanceCounter(0);
  _InterlockedAdd((volatile signed __int32 *)this + 216, 1u);
  _InterlockedAdd((volatile signed __int32 *)this + 214, 1u);
  _InterlockedExchangeAdd(
    (volatile signed __int32 *)this + 213,
    10000000 * (PerformanceCounter.QuadPart - (__int64)Event) / PerformanceFrequency.QuadPart);
  _InterlockedAdd((volatile signed __int32 *)this + 842, 1u);
  v59 = *((_QWORD *)this + 383);
  if ( v59 )
  {
    v60 = PerformanceCounter.QuadPart - *(_QWORD *)(v59 + 3688);
    if ( v60 >= 5 * PerformanceFrequency.QuadPart )
    {
      v61 = _InterlockedExchange((volatile __int32 *)(v59 + 3680), 0);
      *(LARGE_INTEGER *)(*((_QWORD *)this + 383) + 3688LL) = PerformanceCounter;
      v62 = *((_QWORD *)this + 383);
      if ( v61 )
        *(_DWORD *)(v62 + 3684) = PerformanceFrequency.QuadPart * (unsigned __int64)v61 * *((int *)this + 20) / v60;
      else
        *(_DWORD *)(v62 + 3684) = 0;
    }
  }
  ExReleaseResourceLite(Resource);
  v64 = (CmsVolumeAnalyzer *)*((_QWORD *)this + 383);
  if ( v64 && (*((_DWORD *)this + 779) & 0x800000) == 0 && !v58 )
    CmsVolumeAnalyzer::PostVolumeAnalysis(v64, v63, 0, 0);
  if ( v11 )
  {
    v65 = MEMORY[0xFFFFF78000000320];
    v11[9] = MEMORY[0xFFFFF78000000320];
    v66 = *((_QWORD *)this + 234);
    v11[9] = v65 - v93;
    v11[4] = v66;
    *((_DWORD *)v11 + 4) = updated;
    ((void (__fastcall *)(_QWORD *, _QWORD))qword_1C0136BA0)(v11, 0);
    ExFreePoolWithTag(v11, 0);
  }
  KeSetEvent((PRKEVENT)this + 63, 0, 0);
  if ( *((_BYTE *)this + 3113) )
  {
    if ( !v56 )
    {
      CmsBlockCache::TrimSystemCacheWorkingSet((CmsVolume *)((char *)this + 352));
      CmsBlockRefcount::TrimCache(*((CmsBlockRefcount **)this + 384));
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1c0038af8  mov     rax, rsp
0x1c0038afb  mov     [rax+8], rbx
0x1c0038aff  mov     [rax+10h], rsi
0x1c0038b03  mov     [rax+18h], rdi
0x1c0038b07  push    rbp
0x1c0038b08  push    r12
0x1c0038b0a  push    r13
0x1c0038b0c  push    r14
0x1c0038b0e  push    r15
0x1c0038b10  lea     rbp, [rax-128h]
0x1c0038b17  sub     rsp, 200h
0x1c0038b1e  mov     rax, cs:__security_cookie
0x1c0038b25  xor     rax, rsp
0x1c0038b28  mov     [rbp+120h+var_30], rax
0x1c0038b2f  xor     esi, esi
0x1c0038b31  mov     [rsp+220h+var_1B0], r9d
0x1c0038b36  xor     eax, eax
0x1c0038b38  mov     [rbp+120h+Source2], r8
0x1c0038b3c  mov     [rbp+120h+var_148], rax
0x1c0038b40  mov     r13d, edx
0x1c0038b43  mov     qword ptr [rbp+120h+PerformanceFrequency], rax
0x1c0038b47  mov     ebx, edx
0x1c0038b49  mov     eax, edx
0x1c0038b4b  mov     [rsp+220h+Resource], rsi
0x1c0038b50  and     eax, 20h
0x1c0038b53  mov     [rsp+220h+var_1A8], rsi
0x1c0038b58  mov     [rsp+220h+var_1B0+4], eax
0x1c0038b5c  mov     r14d, edx
0x1c0038b5f  mov     eax, [rcx+0C2Ch]
0x1c0038b65  setnz   byte ptr [rsp+220h+var_1C0+5]
0x1c0038b6a  and     r13d, 80h
0x1c0038b71  mov     [rbp+120h+var_1A0], 0C0000001h
0x1c0038b78  and     ebx, 100h
0x1c0038b7e  mov     [rbp+120h+var_19C], esi
0x1c0038b81  mov     rdi, rcx
0x1c0038b84  mov     [rbp+120h+var_150], rsi
0x1c0038b88  setnz   byte ptr [rsp+220h+var_1C0+6]
0x1c0038b8d  mov     byte ptr [rsp+220h+var_1C0], sil
0x1c0038b92  and     r14d, 0FFFFFE5Fh
0x1c0038b99  mov     byte ptr [rsp+220h+var_1C0+1], sil
0x1c0038b9e  mov     byte ptr [rsp+220h+var_1C0+4], sil
0x1c0038ba3  mov     r15d, esi
0x1c0038ba6  mov     byte ptr [rsp+220h+var_1C0+3], sil
0x1c0038bab  lea     ecx, [rsi+1]
0x1c0038bae  mov     [rbp+120h+var_198], r13d
0x1c0038bb2  mov     [rbp+120h+var_188], ebx
0x1c0038bb5  and     eax, 2
0x1c0038bb8  jz      short loc_1C0038BC6
0x1c0038bba  cmp     r14d, ecx
0x1c0038bbd  jnz     short loc_1C0038BC6
0x1c0038bbf  xor     eax, eax
0x1c0038bc1  jmp     loc_1C0039810
0x1c0038bc6  test    r14b, 2
0x1c0038bca  jz      short loc_1C0038BD9
0x1c0038bcc  test    cl, r14b
0x1c0038bcf  jnz     short loc_1C0038BD9
0x1c0038bd1  mov     byte ptr [rsp+220h+var_1C0+2], cl
0x1c0038bd5  test    eax, eax
0x1c0038bd7  jz      short loc_1C0038BDE
0x1c0038bd9  mov     byte ptr [rsp+220h+var_1C0+2], sil
0x1c0038bde  mov     r12, [rbp+120h+arg_30]
0x1c0038be5  lea     rax, [rdi+5E8h]
0x1c0038bec  mov     [rbp+120h+Event], rax
0x1c0038bf0  test    r12, r12
0x1c0038bf3  jz      short loc_1C0038C20
0x1c0038bf5  lea     r8, [rbp+120h+var_90]; struct _KWAIT_BLOCK *
0x1c0038bfc  mov     [rbp+120h+var_140], rax
0x1c0038c00  lea     rdx, [rbp+120h+var_140]; void **
0x1c0038c04  mov     [rbp+120h+var_138], r12
0x1c0038c08  mov     ecx, 2; unsigned int
0x1c0038c0d  call    ?MsWaitForMultipleObjects@@YAJKPEAPEAXPEAU_KWAIT_BLOCK@@E@Z; MsWaitForMultipleObjects(ulong,void * *,_KWAIT_BLOCK *,uchar)
0x1c0038c12  test    eax, eax
0x1c0038c14  jz      short loc_1C0038C3C
0x1c0038c16  mov     eax, 0C0000120h
0x1c0038c1b  jmp     loc_1C0039810
0x1c0038c20  xor     r9d, r9d; Alertable
0x1c0038c23  mov     [rsp+220h+Timeout], rsi; Timeout
0x1c0038c28  xor     r8d, r8d; WaitMode
0x1c0038c2b  xor     edx, edx; WaitReason
0x1c0038c2d  mov     rcx, rax; Object
0x1c0038c30  call    cs:__imp_KeWaitForSingleObject
0x1c0038c37  nop     dword ptr [rax+rax+00h]
0x1c0038c3c  mov     rcx, rdi; this
0x1c0038c3f  call    ?UpdateTreesBoundToCheckpoint@CmsVolume@@AEAAJXZ; CmsVolume::UpdateTreesBoundToCheckpoint(void)
0x1c0038c44  xor     ebx, ebx
0x1c0038c46  mov     esi, eax
0x1c0038c48  test    eax, eax
0x1c0038c4a  js      loc_1C00397F9
0x1c0038c50  cmp     [rdi+0C2Ah], bl
0x1c0038c56  jz      short loc_1C0038C9F
0x1c0038c58  xor     edx, edx; Val
0x1c0038c5a  lea     r8d, [rbx+58h]; Size
0x1c0038c5e  lea     rcx, [rbp+120h+var_F0]; void *
0x1c0038c62  call    memset
0x1c0038c67  lea     eax, [rbx+1]
0x1c0038c6a  mov     r8b, al
0x1c0038c6d  mov     [rbp+120h+var_A4], eax
0x1c0038c70  lea     rdx, [rbp+120h+var_F0]
0x1c0038c74  lea     rcx, ?VolumeLazyWriterResource@@3U_MS_ERESOURCE@@A; _MS_ERESOURCE VolumeLazyWriterResource
0x1c0038c7b  call    MsAcquireFastResourceExclusive
0x1c0038c80  lea     rdx, [rbp+120h+var_F0]
0x1c0038c84  mov     [rdi+96Ch], ebx
0x1c0038c8a  lea     rcx, ?VolumeLazyWriterResource@@3U_MS_ERESOURCE@@A; _MS_ERESOURCE VolumeLazyWriterResource
0x1c0038c91  call    MsReleaseFastResource
0x1c0038c96  lea     rcx, [rbp+120h+var_F0]
0x1c0038c9a  call    MsCleanupFastResourceOwnerEntry
0x1c0038c9f  test    r13d, r13d
0x1c0038ca2  jz      short loc_1C0038CBB
0x1c0038ca4  mov     rcx, [rdi+0BF8h]; this
0x1c0038cab  test    rcx, rcx
0x1c0038cae  jz      short loc_1C0038CBB
0x1c0038cb0  xor     r9d, r9d; unsigned __int8
0x1c0038cb3  xor     r8d, r8d; unsigned __int8
0x1c0038cb6  call    ?CancelVolumeAnalysis@CmsVolumeAnalyzer@@QEAAXEEE@Z; CmsVolumeAnalyzer::CancelVolumeAnalysis(uchar,uchar,uchar)
0x1c0038cbb  lea     rdx, [rsp+220h+Resource]; struct _SmsCheckpointContext **
0x1c0038cc0  mov     rcx, rdi; this
0x1c0038cc3  call    ?AcquireForCheckpoint@CmsVolume@@QEAAXPEAPEAU_SmsCheckpointContext@@@Z; CmsVolume::AcquireForCheckpoint(_SmsCheckpointContext * *)
0x1c0038cc8  mov     r13, [rsp+220h+Resource]
0x1c0038ccd  cmp     [rdi+0C29h], bl
0x1c0038cd3  jz      loc_1C0038D90
0x1c0038cd9  lea     rcx, [r13+68h]; Object
0x1c0038cdd  mov     [rsp+220h+Timeout], rbx; Timeout
0x1c0038ce2  xor     r9d, r9d; Alertable
0x1c0038ce5  xor     r8d, r8d; WaitMode
0x1c0038ce8  xor     edx, edx; WaitReason
0x1c0038cea  call    cs:__imp_KeWaitForSingleObject
0x1c0038cf1  nop     dword ptr [rax+rax+00h]
0x1c0038cf6  lea     rax, [r13+0A8h]
0x1c0038cfd  cmp     [rax], rax
0x1c0038d00  jz      short loc_1C0038D7E
0x1c0038d02  test    dword ptr [rdi+0C2Ch], 20000000h
0x1c0038d0c  jnz     short loc_1C0038D7E
0x1c0038d0e  mov     rbx, [rdi+6E8h]
0x1c0038d15  xor     esi, esi
0x1c0038d17  mov     r9, [rdi+608h]
0x1c0038d1e  mov     r8, r13
0x1c0038d21  mov     byte ptr [rsp+220h+var_1F8], sil
0x1c0038d26  mov     rcx, rdi
0x1c0038d29  mov     [rsp+220h+var_1A8], rbx
0x1c0038d2e  mov     [rsp+220h+Timeout], rbx
0x1c0038d33  mov     r9, [r9+70h]
0x1c0038d37  call    ?TransitionCheckpointState@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAU_SmsCheckpointContext@@T_ML_LSN@@PEAU_SmsCheckpointLocation@@E@Z; CmsVolume::TransitionCheckpointState(CmsTransactionCore *,_SmsCheckpointContext *,_ML_LSN,_SmsCheckpointLocation *,uchar)
0x1c0038d3c  mov     rdx, r13; struct _SmsCheckpointContext *
0x1c0038d3f  mov     rcx, rdi; this
0x1c0038d42  call    ?EnableNextCheckpoint@CmsVolume@@QEAAXPEAU_SmsCheckpointContext@@@Z; CmsVolume::EnableNextCheckpoint(_SmsCheckpointContext *)
0x1c0038d47  mov     rcx, r13; Resource
0x1c0038d4a  call    cs:__imp_ExReleaseResourceLite
0x1c0038d51  nop     dword ptr [rax+rax+00h]
0x1c0038d56  xor     r8d, r8d; Wait
0x1c0038d59  lea     rcx, [rdi+5E8h]; Event
0x1c0038d60  xor     edx, edx; Increment
0x1c0038d62  call    cs:__imp_KeSetEvent
0x1c0038d69  nop     dword ptr [rax+rax+00h]
0x1c0038d6e  mov     r13d, [rbp+120h+var_198]
0x1c0038d72  lea     rax, [rdi+5E8h]
0x1c0038d79  jmp     loc_1C0038BF0
0x1c0038d7e  xor     r12d, r12d
0x1c0038d81  mov     ecx, r14d
0x1c0038d84  mov     [rdi+0C50h], r12d
0x1c0038d8b  and     ecx, 1
0x1c0038d8e  jmp     short loc_1C0038D9F
0x1c0038d90  mov     ecx, r14d
0x1c0038d93  and     ecx, 1
0x1c0038d96  jnz     loc_1C00397D6
0x1c0038d9c  xor     r12d, r12d
0x1c0038d9f  test    dword ptr [rdi+0C2Ch], 20000000h
0x1c0038da9  jz      short loc_1C0038DCD
0x1c0038dab  mov     ebx, r12d
0x1c0038dae  mov     [rsp+220h+var_1B0], ebx
0x1c0038db2  mov     [rbp+120h+Source2], r12
0x1c0038db6  test    ecx, ecx
0x1c0038db8  jz      short loc_1C0038DD1
0x1c0038dba  mov     rdx, r13; struct _SmsCheckpointContext *
0x1c0038dbd  mov     rcx, rdi; this
0x1c0038dc0  call    ?EnableNextCheckpoint@CmsVolume@@QEAAXPEAU_SmsCheckpointContext@@@Z; CmsVolume::EnableNextCheckpoint(_SmsCheckpointContext *)
0x1c0038dc5  mov     rcx, r13
0x1c0038dc8  jmp     loc_1C00397E8
0x1c0038dcd  mov     ebx, [rsp+220h+var_1B0]
0x1c0038dd1  xor     ecx, ecx; PerformanceFrequency
0x1c0038dd3  call    cs:__imp_KeQueryPerformanceCounter
0x1c0038dda  nop     dword ptr [rax+rax+00h]
0x1c0038ddf  lea     rcx, [rbp+120h+PerformanceFrequency]; PerformanceFrequency
0x1c0038de3  mov     [rbp+120h+Event], rax
0x1c0038de7  call    cs:__imp_KeQueryPerformanceCounter
0x1c0038dee  nop     dword ptr [rax+rax+00h]
0x1c0038df3  cmp     cs:qword_1C0136BA0, r12
0x1c0038dfa  mov     rdx, 0FFFFF78000000320h
0x1c0038e04  jz      loc_1C0038FEA
0x1c0038e0a  cmp     [rdi+0C29h], r12b
0x1c0038e11  jz      loc_1C0038FEA
0x1c0038e17  cmp     [rsp+220h+var_1B0+4], r12d
0x1c0038e1c  jnz     loc_1C0038FEA
0x1c0038e22  cmp     [rdi+800h], r12
0x1c0038e29  jle     loc_1C0038FEA
0x1c0038e2f  mov     rax, 0FFFFF78000000014h
0x1c0038e39  mov     rax, [rax]
0x1c0038e3c  mov     rcx, rax
0x1c0038e3f  sub     rcx, [rdi+808h]
0x1c0038e46  cmp     rcx, [rdi+800h]
0x1c0038e4d  jle     loc_1C0038FD9
0x1c0038e53  mov     rcx, [rdx]
0x1c0038e56  mov     r8d, 6950534Dh; Tag
0x1c0038e5c  mov     [rbp+120h+var_148], rcx
0x1c0038e60  mov     edx, 0C8h; NumberOfBytes
0x1c0038e65  mov     ecx, 200h; PoolType
0x1c0038e6a  mov     [rdi+808h], rax
0x1c0038e71  call    cs:__imp_ExAllocatePoolWithTag
0x1c0038e78  nop     dword ptr [rax+rax+00h]
0x1c0038e7d  mov     r15, rax
0x1c0038e80  test    rax, rax
0x1c0038e83  jz      loc_1C0038FE5
0x1c0038e89  mov     eax, 1
0x1c0038e8e  mov     [r15], eax
0x1c0038e91  mov     rax, [rdi+30h]
0x1c0038e95  mov     [r15+8], rax
0x1c0038e99  mov     [r15+10h], r12d
0x1c0038e9d  mov     rax, [rdi+730h]
0x1c0038ea4  mov     [r15+18h], rax
0x1c0038ea8  mov     [r15+28h], r14d
0x1c0038eac  mov     rax, [rdi+0BD8h]
0x1c0038eb3  mov     rcx, [rax+20h]
0x1c0038eb7  mov     rax, [rcx+20h]
0x1c0038ebb  mov     [r15+60h], rax
0x1c0038ebf  mov     rax, [rdi+0BD8h]
0x1c0038ec6  mov     rdx, [rax+20h]
0x1c0038eca  mov     rcx, [rdx+8]
0x1c0038ece  sub     rcx, [rdx+20h]
0x1c0038ed2  sub     rcx, [rdx+10h]
0x1c0038ed6  mov     [r15+68h], rcx
0x1c0038eda  mov     rax, [rdi+0BD8h]
0x1c0038ee1  mov     rcx, [rax+20h]
0x1c0038ee5  mov     rax, [rcx+18h]
0x1c0038ee9  mov     [r15+70h], rax
0x1c0038eed  mov     rax, r12
0x1c0038ef0  xchg    rax, [rdi+880h]
0x1c0038ef7  mov     [r15+78h], rax
0x1c0038efb  mov     rax, r12
0x1c0038efe  xchg    rax, [rdi+888h]
0x1c0038f05  mov     [r15+80h], rax
0x1c0038f0c  mov     rax, r12
0x1c0038f0f  xchg    rax, [rdi+890h]
0x1c0038f16  mov     [r15+88h], rax
0x1c0038f1d  mov     rax, r12
0x1c0038f20  xchg    rax, [rdi+898h]
0x1c0038f27  mov     [r15+90h], rax
0x1c0038f2e  mov     eax, r12d
0x1c0038f31  xchg    eax, [rdi+8A0h]
0x1c0038f37  mov     [r15+98h], eax
0x1c0038f3e  mov     rax, r12
0x1c0038f41  xchg    rax, [rdi+8A8h]
0x1c0038f48  mov     [r15+0A0h], rax
0x1c0038f4f  mov     eax, r12d
0x1c0038f52  xchg    eax, [rdi+8B0h]
0x1c0038f58  mov     [r15+0A8h], eax
0x1c0038f5f  mov     rax, r12
0x1c0038f62  xchg    rax, [rdi+8B8h]
0x1c0038f69  mov     [r15+0B0h], rax
0x1c0038f70  mov     eax, r12d
0x1c0038f73  xchg    eax, [rdi+8C0h]
0x1c0038f79  mov     [r15+0B8h], eax
0x1c0038f80  mov     rax, r12
0x1c0038f83  xchg    rax, [rdi+8C8h]
0x1c0038f8a  mov     [r15+0C0h], rax
0x1c0038f91  mov     rcx, [rdi+0A20h]
0x1c0038f98  test    rcx, rcx
0x1c0038f9b  jz      short loc_1C0038FCF
0x1c0038f9d  mov     eax, [rdi+0C2Ch]
0x1c0038fa3  test    al, 2
0x1c0038fa5  jnz     short loc_1C0038FCF
0x1c0038fa7  mov     rax, [rcx+30h]
0x1c0038fab  mov     [r15+50h], rax
0x1c0038faf  mov     rax, [rdi+0A20h]
0x1c0038fb6  mov     rcx, [rax+38h]
0x1c0038fba  mov     [r15+58h], rcx
0x1c0038fbe  mov     rax, [rdi+0A20h]
0x1c0038fc5  mov     [rax+30h], r12
0x1c0038fc9  mov     [rax+38h], r12
0x1c0038fcd  jmp     short loc_1C0038FE5
0x1c0038fcf  mov     [r15+50h], r12
0x1c0038fd3  mov     [r15+58h], r12
0x1c0038fd7  jmp     short loc_1C0038FE5
0x1c0038fd9  test    rcx, rcx
0x1c0038fdc  jns     short loc_1C0038FE5
0x1c0038fde  mov     [rdi+808h], rax
0x1c0038fe5  mov     r13, [rsp+220h+Resource]
0x1c0038fea  mov     dl, byte ptr [rsp+220h+var_1C0+5]; unsigned __int8
0x1c0038fee  mov     rcx, rdi; this
0x1c0038ff1  call    ?AggregatedCheckpointTelemetry@CmsVolume@@QEAAXE@Z; CmsVolume::AggregatedCheckpointTelemetry(uchar)
0x1c0038ff6  lea     rdx, [rdi+58h]; struct CmsReservedPools *
0x1c0038ffa  mov     rcx, rdi; struct CmsVolume *
0x1c0038ffd  call    ?MakeFromReservedPool@CmsTransactionContext@@SAPEAV1@PEAVCmsVolume@@PEAVCmsReservedPools@@@Z; CmsTransactionContext::MakeFromReservedPool(CmsVolume *,CmsReservedPools *)
0x1c0039002  mov     rcx, [rdi+0A28h]; this
0x1c0039009  mov     r12, rax
0x1c003900c  test    rcx, rcx
0x1c003900f  jz      short loc_1C003902C
0x1c0039011  mov     r9b, byte ptr [rsp+220h+var_1C0+5]; unsigned __int8
0x1c0039016  mov     rdx, rax; struct CmsTransactionContext *
0x1c0039019  mov     r8b, byte ptr [rsp+220h+var_1C0+6]; unsigned __int8
0x1c003901e  call    ?PersistReadCacheMetadata@CmsReadCache@@QEAAJPEAVCmsTransactionContext@@EE@Z; CmsReadCache::PersistReadCacheMetadata(CmsTransactionContext *,uchar,uchar)
0x1c0039023  xor     ecx, ecx
  ... truncated ...
```
