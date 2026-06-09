# OpenFileSystemFile

- ea: `0x1c0168d30`
- end: `0x1c0169954`
- name: `OpenFileSystemFile`
- size: `3108`
- prototype: ``
- caller_count: `6`
- callee_count: `36`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c014d950`
- `0x1c016abac`
- `0x1c0171cc8`
- `0x1c0171df4`
- `0x1c0172378`
- `0x1c01734ec`

## callees

- `0x1c000193c`
- `0x1c0002bac`
- `0x1c0002ce0`
- `0x1c0003658`
- `0x1c0003eb4`
- `0x1c0004300`
- `0x1c00045c4`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c003a41c`
- `0x1c003a500`
- `0x1c003a928`
- `0x1c003adcc`
- `0x1c003af28`
- `0x1c003b27c`
- `0x1c003b2ec`
- `0x1c003b62c`
- `0x1c003b830`
- `0x1c0063db0`
- `0x1c00656a4`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c015043c`
- `0x1c0151cec`
- `0x1c0156b80`
- `0x1c01632d4`
- `0x1c0165b54`
- `0x1c0165d18`
- `0x1c0168b50`
- `0x1c0168d30`
- `0x1c016995c`
- `0x1c016a4ac`
- `0x1c016a90c`
- `0x1c017c000`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0169170`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0169333`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0169170`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0169333`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01694be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017fbbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01694be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c017fbbf`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01696c7`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01696c7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01696fa`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01696fa`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0168e94`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0168f51`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0168e94`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0168f51`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0168f0a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0168f64`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017fbf0`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0168f0a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0168f64`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017fbf0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c016919a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c016919a`

## string_xrefs

- `0x1c01692b6`: `mount.c`
- `0x1c0169490`: `mount.c`
- `0x1c01695ae`: `mount.c`
- `0x1c0169677`: `mount.c`
- `0x1c01697a2`: `mount.c`
- `0x1c0169808`: `mount.c`
- `0x1c01698cf`: `mount.c`

## pseudocode

```c
__int64 __fastcall OpenFileSystemFile(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        const UNICODE_STRING *a4,
        __int64 a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        DWORD a11,
        __int64 *a12)
{
  int v16; // r8d
  int v17; // r9d
  const UNICODE_STRING *v18; // rax
  __int64 v19; // rsi
  __int128 *PoolWithTag; // r13
  __int64 v21; // r14
  struct _FAST_MUTEX *v22; // rdi
  __int64 RootFcb; // rax
  __int64 v24; // r15
  _QWORD *v25; // rdx
  __int64 Scb; // rax
  int v27; // edx
  __int16 StreamChecksumType; // cx
  int v29; // eax
  int v30; // r9d
  __int64 v31; // r8
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // rdx
  char v35; // cl
  __int128 *v36; // rdx
  __int64 v37; // rdx
  const UNICODE_STRING *v38; // rdx
  unsigned __int16 *v39; // r8
  unsigned __int16 *v40; // r10
  int v41; // r9d
  PCUNICODE_STRING v42; // rax
  char v43; // cl
  __int128 *i; // rax
  const void **v45; // rdx
  __int64 v46; // r8
  int v47; // eax
  __int64 result; // rax
  int v49; // [rsp+20h] [rbp-228h]
  int v50; // [rsp+20h] [rbp-228h]
  char v51; // [rsp+50h] [rbp-1F8h]
  unsigned int Status; // [rsp+54h] [rbp-1F4h]
  char v53[4]; // [rsp+58h] [rbp-1F0h] BYREF
  DWORD v54; // [rsp+5Ch] [rbp-1ECh] BYREF
  PCUNICODE_STRING SourceString; // [rsp+60h] [rbp-1E8h]
  PVOID P; // [rsp+68h] [rbp-1E0h] BYREF
  _WORD *p_Length; // [rsp+70h] [rbp-1D8h]
  __int64 v58; // [rsp+78h] [rbp-1D0h]
  _QWORD v59[3]; // [rsp+80h] [rbp-1C8h] BYREF
  __int64 v60; // [rsp+98h] [rbp-1B0h]
  __int128 *v61; // [rsp+A0h] [rbp-1A8h]
  _QWORD v62[2]; // [rsp+A8h] [rbp-1A0h] BYREF
  unsigned __int16 *v63; // [rsp+B8h] [rbp-190h]
  __int128 *v64; // [rsp+C0h] [rbp-188h]
  __int64 *v65; // [rsp+C8h] [rbp-180h]
  __int64 v66; // [rsp+D0h] [rbp-178h]
  __int64 v67; // [rsp+D8h] [rbp-170h]
  const UNICODE_STRING *v68; // [rsp+E0h] [rbp-168h]
  __int128 v69; // [rsp+F0h] [rbp-158h] BYREF
  __int128 v70; // [rsp+100h] [rbp-148h] BYREF
  __int128 v71; // [rsp+110h] [rbp-138h]
  __int128 v72; // [rsp+120h] [rbp-128h] BYREF
  _BYTE v73[208]; // [rsp+130h] [rbp-118h] BYREF

  SourceString = a4;
  v59[0] = a2;
  v67 = a1;
  v66 = a2;
  v68 = a4;
  v60 = a5;
  v54 = a11;
  v65 = a12;
  *(_QWORD *)&v71 = 0;
  v58 = 0;
  P = 0;
  memset(v73, 0, sizeof(v73));
  v62[0] = 0x20000;
  v62[1] = byte_1C01059D0;
  v53[0] = 0;
  v51 = 0;
  v72 = 0;
  *a12 = 0;
  v18 = (const UNICODE_STRING *)v62;
  LOBYTE(v19) = a7;
  if ( a7 )
    v18 = &RefsFileNameIndex;
  p_Length = &v18->Length;
  PoolWithTag = &v72;
  if ( a3 )
    PoolWithTag = a3;
  v64 = PoolWithTag;
  LOBYTE(v17) = a3 == 0;
  v21 = v60;
  LOBYTE(v16) = a6;
  RefsEditFileBegin(a1, a2, v16, v17, (__int64)PoolWithTag, a7, v60, (__int64)a4, (__int64)&P);
  v22 = (struct _FAST_MUTEX *)(a2 + 536);
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 536));
  if ( a8 )
  {
    RootFcb = RefsCreateRootFcb(a2);
  }
  else if ( a7 )
  {
    v69 = *PoolWithTag;
    RootFcb = RefsCreateFcb(a1, a2, (unsigned int)&v69, 2, 0, 0, 0);
  }
  else
  {
    v70 = *PoolWithTag;
    RootFcb = RefsCreateFcb(a1, a2, (unsigned int)&v70, 0, v21, (__int64)a4, 0);
  }
  v24 = RootFcb;
  v59[2] = RootFcb;
  RefsCheckpointCurrentTransaction(a1);
  ++*(_DWORD *)(v24 + 32);
  KeReleaseGuardedMutex(v22);
  RefsAcquireExclusiveFcb(a1, v24, 0, 1);
  if ( *((_QWORD *)PoolWithTag + 1) != 1536 )
    *(_DWORD *)(v24 + 4) |= 0x100u;
  if ( *(_QWORD *)(v24 + 104) && !(unsigned __int8)RefsAcquireExclusivePagingIoSpecifyWait(a1, v24, 0) )
  {
    RefsReleaseFcb(a1, v24);
    LOBYTE(v46) = 1;
    RefsAcquireExclusivePagingIoSpecifyWait(a1, v24, v46);
    RefsAcquireExclusiveFcb(a1, v24, 0, 0);
  }
  KeAcquireGuardedMutex(v22);
  --*(_DWORD *)(v24 + 32);
  KeReleaseGuardedMutex(v22);
  if ( (*(_DWORD *)(v24 + 4) & 0x80u) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      LOBYTE(v19) = 4;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids, 3221226094LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741202);
    v29 = RefsRaiseStatusInternal(a1, 3221226094LL);
    goto LABEL_84;
  }
  if ( v21 )
  {
    *(_QWORD *)&v71 = RefsCreateLcb(a1, v21, v24, (_DWORD)SourceString, 0, 0);
    v58 = v71;
  }
  if ( !a7 && a6 )
  {
    v25 = P;
    *(_QWORD *)(v24 + 240) = *((_QWORD *)P + 14);
    v25[14] = 0;
  }
  Scb = RefsCreateScb(a1, v24, a7 != 0 ? 160 : 128, (_DWORD)p_Length, v54, (__int64)v53);
  v21 = Scb;
  p_Length = (_WORD *)Scb;
  v27 = 2;
  *(_WORD *)(Scb + 256) = 2;
  if ( a10 )
    StreamChecksumType = RefsGetStreamChecksumType(*(_QWORD *)(Scb + 128));
  else
    StreamChecksumType = 0;
  *(_WORD *)(v21 + 258) = StreamChecksumType;
  v29 = RefsInitializeFileFromDisk(a1, v21, v27 & (unsigned int)-(a6 == 0));
  LODWORD(v22) = v29;
  Status = v29;
  if ( v29 < 0 )
  {
LABEL_84:
    if ( v29 == -1073741772 || v29 == -1073741809 || v29 == -1073741275 )
    {
      v19 = v71;
      if ( (_QWORD)v71 )
      {
        ExAcquireFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(v71 + 24) + 48LL));
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v19 + 24) + 156LL));
        RefsRemovePrefixSafe(v58);
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v19 + 24) + 156LL));
        ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(v19 + 24) + 48LL));
        v22 = (struct _FAST_MUTEX *)v58;
        v47 = *(_DWORD *)(v58 + 4);
        if ( (v47 & 0x20) != 0 )
        {
          RefsRemoveHashEntry(*(_QWORD *)(*(_QWORD *)(v58 + 32) + 88LL) + 2696LL, *(unsigned int *)(v58 + 192), v58);
          v22[3].Event.Header.LockNV = 0;
          *(&v22->Count + 1) &= ~0x20u;
          v47 = *(&v22->Count + 1);
        }
        *(&v22->Count + 1) = v47 | 2;
        *(&v22[3].Contention + 1) = 0;
        *(&v22[3].Count + 1) = 0;
        LODWORD(v22) = Status;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      LOBYTE(v19) = 4;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          31,
          WPP_7031d589edf23cbf7a1abad52b310385_Traceguids,
          (unsigned int)v22);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsRaiseStatusInternal(a1, Status);
LABEL_98:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      LOBYTE(v19) = 4;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_7031d589edf23cbf7a1abad52b310385_Traceguids,
          (unsigned int)v22);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsRaiseStatusInternal(a1, Status);
LABEL_105:
    v22 = (struct _FAST_MUTEX *)SecurityDescriptor;
    if ( *(_QWORD *)PoolWithTag == v34 )
    {
LABEL_40:
      RefsCheckpointCurrentTransaction(a1);
      LODWORD(v22) = RefsModifySecurity(a1, v24, &v54, v22);
      if ( (int)v22 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= (unsigned __int8)v19 )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            WPP_7031d589edf23cbf7a1abad52b310385_Traceguids,
            (unsigned int)v22);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug((NTSTATUS)v22);
        RefsRaiseStatusInternal(a1, (unsigned int)v22);
        goto LABEL_48;
      }
LABEL_27:
      RefsCheckpointCurrentTransaction(a1);
      LOBYTE(PoolWithTag) = a7;
      if ( !a7 )
        goto LABEL_28;
      *(_QWORD *)(v21 + 368) = ExAllocatePoolWithTag((POOL_TYPE)17, SourceString->Length, 0x6F4D6552u);
      v38 = SourceString;
      *(_WORD *)(v21 + 362) = SourceString->Length;
      RtlCopyUnicodeString((PUNICODE_STRING)(v21 + 360), v38);
      *(_DWORD *)(v21 + 376) = 0;
      v39 = *(unsigned __int16 **)(v21 + 368);
      v63 = v39;
      v40 = v39 + 1;
      v41 = 0;
      while ( v39 < v40 )
      {
        v41 = *(unsigned __int16 *)(*(_QWORD *)(v59[0] + 672LL) + 2LL * *v39++) + 37 * v41;
        v63 = v39;
      }
LABEL_48:
      *(_DWORD *)(v21 + 376) = v41;
LABEL_28:
      RefsAcquireExclusiveScbWithFlags(a1, v21, 0);
      v35 = a8;
      v36 = 0;
      if ( !a8 )
        goto LABEL_29;
      goto LABEL_73;
    }
LABEL_39:
    v22 = (struct _FAST_MUTEX *)NewDescriptor;
    goto LABEL_40;
  }
  if ( !a6 )
  {
    if ( a7 )
    {
      RefsUpdateIndexScbFromAttribute(a1, v21);
    }
    else
    {
      if ( a9 && !*(_QWORD *)(v21 + 360) )
      {
        RefsBindMinstoreTransaction(a1);
        LODWORD(v22) = RefsCreateDataStream(a1, v21, 0);
        Status = (unsigned int)v22;
      }
      if ( (int)v22 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          LOBYTE(v19) = 4;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              35,
              WPP_7031d589edf23cbf7a1abad52b310385_Traceguids,
              (unsigned int)v22);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(Status);
        RefsRaiseStatusInternal(a1, Status);
        goto LABEL_120;
      }
    }
    goto LABEL_26;
  }
  if ( !a7 )
  {
    RefsBindMinstoreTransaction(a1);
    LOBYTE(v31) = 1;
    LODWORD(v22) = RefsCreateDataStream(a1, v21, v31);
    Status = (unsigned int)v22;
    if ( (int)v22 < 0 )
      goto LABEL_98;
  }
  LOBYTE(v30) = a7;
  RefsInitializeFcbAndStdInfo(a1, v24, a7 != 0 ? v21 : 0, v30, v49, 0, 0, 0, 0);
  v34 = 0;
  if ( a7 )
  {
    RefsCreateIndex(a1, v24, v32, v33, v50, 0);
    v34 = 0;
    goto LABEL_25;
  }
  if ( !a9
    || (RefsInitializeAttributeContext(v73),
        RefsInsertStreamAttribute(a1, v21, 0, 0, (__int64)v73),
        RefsCleanupAttributeContext(a1, v73),
        v51 = 0,
        LODWORD(v22) = MsInitializeEmptyStream(*(struct CmsTransactionContext **)(a1 + 24), *(CmsStream **)(v21 + 360)),
        v34 = 0,
        (int)v22 >= 0) )
  {
LABEL_25:
    if ( !*(_QWORD *)(v59[0] + 64LL) )
    {
LABEL_26:
      LOBYTE(v19) = 4;
      goto LABEL_27;
    }
    LOBYTE(v19) = 4;
    v54 = 4;
    if ( *((_QWORD *)PoolWithTag + 1) != 1536 )
      goto LABEL_39;
    goto LABEL_105;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    LOBYTE(v19) = 4;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        WPP_7031d589edf23cbf7a1abad52b310385_Traceguids,
        (unsigned int)v22);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug((NTSTATUS)v22);
  RefsRaiseStatusInternal(a1, (unsigned int)v22);
LABEL_73:
  *(_DWORD *)(v21 + 304) |= 0x100000u;
LABEL_29:
  if ( a6 != (_BYTE)v36 && (_BYTE)PoolWithTag )
  {
    v59[0] = 262146;
    v59[1] = L".";
    v61 = v36;
    v71 = 0;
    v42 = (PCUNICODE_STRING)v59;
    if ( !v35 )
      v42 = SourceString;
    p_Length = &v42->Length;
    PoolWithTag = (__int128 *)ExAllocatePoolWithTag((POOL_TYPE)17, v42->Length + 82LL, 0x6F4D6552u);
    v61 = PoolWithTag;
    v43 = 0;
    if ( !v60 )
      goto LABEL_62;
    for ( i = (__int128 *)(*(_QWORD *)(v60 + 120) + 8LL); ; i = v64 )
    {
      *PoolWithTag = *i;
      v45 = (const void **)p_Length;
      *((_WORD *)PoolWithTag + 36) = (unsigned __int8)(*p_Length >> 1);
      *((_BYTE *)PoolWithTag + 74) = v43;
      *(_DWORD *)((char *)PoolWithTag + 78) = 48;
      memmove((char *)PoolWithTag + 82, v45[1], *(unsigned __int16 *)v45);
      RefsInitializeAttributeContext(v73);
      *((_WORD *)PoolWithTag + 40) = 2;
      RefsCreateAttributeWithValue(
        a1,
        v24,
        56,
        0,
        (__int64)PoolWithTag,
        2 * *((unsigned __int16 *)PoolWithTag + 36) + 82,
        0,
        (__int64)PoolWithTag,
        (__int64)v73);
      v51 = 1;
      if ( a8 )
        break;
      RefsBindMinstoreTransaction(a1);
      *((_QWORD *)&v71 + 1) = *((_QWORD *)PoolWithTag + 1);
      LODWORD(v22) = MsSetDurableTableObjectParentId(
                       *(struct CmsTransactionContext **)(a1 + 24),
                       *(CmsBPlusTable **)(*(_QWORD *)(v24 + 248) + 384LL));
      if ( (int)v22 >= 0 )
        break;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= (unsigned __int8)v19 )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          36,
          WPP_7031d589edf23cbf7a1abad52b310385_Traceguids,
          (unsigned int)v22);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug((NTSTATUS)v22);
      RefsRaiseStatusInternal(a1, (unsigned int)v22);
LABEL_62:
      ;
    }
    ExFreePoolWithTag(PoolWithTag, 0);
    LOBYTE(PoolWithTag) = a7;
  }
  RefsUpdateFcbInfoFromDisk(a1, 0, v24, 0);
  LOBYTE(v19) = 0;
  if ( (_BYTE)PoolWithTag )
    RefsUpdateIndexScbFromAttribute(a1, v21);
LABEL_120:
  LOBYTE(v37) = 1;
  result = RefsIncrementCloseCounts(v21, v37, 0);
  if ( v51 != (_BYTE)v19 )
    result = RefsCleanupAttributeContext(a1, v73);
  if ( P )
    result = RefsEditFileEnd(P);
  if ( (int)v22 >= 0 )
  {
    result = (__int64)v65;
    *v65 = v21;
  }
  return result;
}

```

## disassembly

```asm
0x1c0168d30  push    rbx
0x1c0168d32  push    rsi
0x1c0168d33  push    rdi
0x1c0168d34  push    r12
0x1c0168d36  push    r13
0x1c0168d38  push    r14
0x1c0168d3a  push    r15
0x1c0168d3c  sub     rsp, 210h
0x1c0168d43  mov     rax, cs:__security_cookie
0x1c0168d4a  xor     rax, rsp
0x1c0168d4d  mov     [rsp+248h+var_48], rax
0x1c0168d55  mov     r12, r9
0x1c0168d58  mov     [rsp+248h+SourceString], r9
0x1c0168d5d  mov     r14, r8
0x1c0168d60  mov     r15, rdx
0x1c0168d63  mov     [rsp+248h+var_1C8], rdx
0x1c0168d6b  mov     rbx, rcx
0x1c0168d6e  mov     [rsp+248h+var_170], rcx
0x1c0168d76  mov     [rsp+248h+var_178], rdx
0x1c0168d7e  mov     [rsp+248h+var_168], r9
0x1c0168d86  mov     rax, [rsp+248h+arg_20]
0x1c0168d8e  mov     [rsp+248h+var_1B0], rax
0x1c0168d96  mov     eax, [rsp+248h+arg_50]
0x1c0168d9d  mov     [rsp+248h+var_1EC], eax
0x1c0168da1  mov     rsi, [rsp+248h+arg_58]
0x1c0168da9  mov     [rsp+248h+var_180], rsi
0x1c0168db1  xor     r13d, r13d
0x1c0168db4  mov     qword ptr [rsp+248h+var_138], r13
0x1c0168dbc  mov     [rsp+248h+var_1D0], r13
0x1c0168dc1  mov     [rsp+248h+P], r13
0x1c0168dc6  xor     edx, edx; Val
0x1c0168dc8  mov     r8d, 0D0h; Size
0x1c0168dce  lea     rcx, [rsp+248h+var_118]; void *
0x1c0168dd6  call    memset
0x1c0168ddb  mov     [rsp+248h+var_1A0], 20000h
0x1c0168de7  lea     rax, byte_1C01059D0
0x1c0168dee  mov     [rsp+248h+var_198], rax
0x1c0168df6  mov     [rsp+248h+var_1F0], r13b
0x1c0168dfb  mov     [rsp+248h+var_1F8], r13b
0x1c0168e00  mov     [rsp+248h+var_1F7], r13b
0x1c0168e05  xorps   xmm0, xmm0
0x1c0168e08  movups  [rsp+248h+var_128], xmm0
0x1c0168e10  mov     [rsi], r13
0x1c0168e13  lea     rcx, RefsFileNameIndex
0x1c0168e1a  lea     rax, [rsp+248h+var_1A0]
0x1c0168e22  mov     sil, [rsp+248h+arg_30]
0x1c0168e2a  test    sil, sil
0x1c0168e2d  cmovnz  rax, rcx
0x1c0168e31  mov     [rsp+248h+var_1D8], rax
0x1c0168e36  lea     r13, [rsp+248h+var_128]
0x1c0168e3e  test    r14, r14
0x1c0168e41  cmovnz  r13, r14
0x1c0168e45  mov     [rsp+248h+var_188], r13
0x1c0168e4d  setz    r9b
0x1c0168e51  lea     rax, [rsp+248h+P]
0x1c0168e56  mov     [rsp+248h+var_208], rax
0x1c0168e5b  mov     [rsp+248h+var_210], r12
0x1c0168e60  mov     r14, [rsp+248h+var_1B0]
0x1c0168e68  mov     [rsp+248h+var_218], r14
0x1c0168e6d  mov     byte ptr [rsp+248h+var_220], sil
0x1c0168e72  mov     [rsp+248h+var_228], r13
0x1c0168e77  mov     r8b, [rsp+248h+arg_28]
0x1c0168e7f  mov     rdx, r15
0x1c0168e82  mov     rcx, rbx
0x1c0168e85  call    RefsEditFileBegin
0x1c0168e8a  lea     rdi, [r15+218h]
0x1c0168e91  mov     rcx, rdi; Mutex
0x1c0168e94  call    cs:__imp_KeAcquireGuardedMutex
0x1c0168e9b  nop     dword ptr [rax+rax+00h]
0x1c0168ea0  mov     [rsp+248h+var_1F7], 1
0x1c0168ea5  xor     eax, eax
0x1c0168ea7  cmp     [rsp+248h+arg_38], al
0x1c0168eae  jnz     loc_1C01695D8
0x1c0168eb4  movups  xmm0, xmmword ptr [r13+0]
0x1c0168eb9  mov     [rsp+248h+var_218], rax
0x1c0168ebe  mov     rdx, r15
0x1c0168ec1  mov     rcx, rbx
0x1c0168ec4  test    sil, sil
0x1c0168ec7  jnz     loc_1C01694D7
0x1c0168ecd  movdqu  [rsp+248h+var_148], xmm0
0x1c0168ed6  mov     [rsp+248h+var_220], r12
0x1c0168edb  mov     [rsp+248h+var_228], r14
0x1c0168ee0  xor     r9d, r9d
0x1c0168ee3  lea     r8, [rsp+248h+var_148]
0x1c0168eeb  call    RefsCreateFcb
0x1c0168ef0  mov     r15, rax
0x1c0168ef3  mov     [rsp+248h+var_1B8], rax
0x1c0168efb  mov     rcx, rbx
0x1c0168efe  call    RefsCheckpointCurrentTransaction
0x1c0168f03  inc     dword ptr [r15+20h]
0x1c0168f07  mov     rcx, rdi; Mutex
0x1c0168f0a  call    cs:__imp_KeReleaseGuardedMutex
0x1c0168f11  nop     dword ptr [rax+rax+00h]
0x1c0168f16  xor     eax, eax
0x1c0168f18  mov     [rsp+248h+var_1F7], al
0x1c0168f1c  lea     r9d, [rax+1]
0x1c0168f20  xor     r8d, r8d
0x1c0168f23  mov     rdx, r15
0x1c0168f26  mov     rcx, rbx
0x1c0168f29  call    RefsAcquireExclusiveFcb
0x1c0168f2e  mov     r12d, 100h
0x1c0168f34  cmp     qword ptr [r13+8], 600h
0x1c0168f3c  jz      short loc_1C0168F42
0x1c0168f3e  or      [r15+4], r12d
0x1c0168f42  xor     eax, eax
0x1c0168f44  cmp     [r15+68h], rax
0x1c0168f48  jnz     loc_1C01695E5
0x1c0168f4e  mov     rcx, rdi; Mutex
0x1c0168f51  call    cs:__imp_KeAcquireGuardedMutex
0x1c0168f58  nop     dword ptr [rax+rax+00h]
0x1c0168f5d  dec     dword ptr [r15+20h]
0x1c0168f61  mov     rcx, rdi; Mutex
0x1c0168f64  call    cs:__imp_KeReleaseGuardedMutex
0x1c0168f6b  nop     dword ptr [rax+rax+00h]
0x1c0168f70  mov     eax, [r15+4]
0x1c0168f74  test    al, al
0x1c0168f76  js      loc_1C016962A
0x1c0168f7c  xor     edi, edi
0x1c0168f7e  test    r14, r14
0x1c0168f81  jz      short loc_1C0168FAD
0x1c0168f83  mov     [rsp+248h+var_220], rdi
0x1c0168f88  mov     byte ptr [rsp+248h+var_228], dil
0x1c0168f8d  mov     r9, [rsp+248h+SourceString]
0x1c0168f92  mov     r8, r15
0x1c0168f95  mov     rdx, r14
0x1c0168f98  mov     rcx, rbx
0x1c0168f9b  call    RefsCreateLcb
0x1c0168fa0  mov     qword ptr [rsp+248h+var_138], rax
0x1c0168fa8  mov     [rsp+248h+var_1D0], rax
0x1c0168fad  test    sil, sil
0x1c0168fb0  jnz     short loc_1C0168FD0
0x1c0168fb2  cmp     [rsp+248h+arg_28], dil
0x1c0168fba  jz      short loc_1C0168FD0
0x1c0168fbc  mov     rdx, [rsp+248h+P]
0x1c0168fc1  mov     rcx, [rdx+70h]
0x1c0168fc5  mov     [r15+0F0h], rcx
0x1c0168fcc  mov     [rdx+70h], rdi
0x1c0168fd0  mov     al, sil
0x1c0168fd3  neg     al
0x1c0168fd5  sbb     r8d, r8d
0x1c0168fd8  and     r8d, 20h
0x1c0168fdc  sub     r8d, 0FFFFFF80h
0x1c0168fe0  lea     rax, [rsp+248h+var_1F0]
0x1c0168fe5  mov     [rsp+248h+var_220], rax
0x1c0168fea  mov     eax, [rsp+248h+var_1EC]
0x1c0168fee  mov     dword ptr [rsp+248h+var_228], eax
0x1c0168ff2  mov     r9, [rsp+248h+var_1D8]
0x1c0168ff7  mov     rdx, r15
0x1c0168ffa  mov     rcx, rbx
0x1c0168ffd  call    RefsCreateScb
0x1c0169002  mov     r14, rax
0x1c0169005  mov     [rsp+248h+var_1D8], rax
0x1c016900a  mov     edx, 2
0x1c016900f  mov     [rax+100h], dx
0x1c0169016  cmp     [rsp+248h+arg_48], dil
0x1c016901e  jnz     loc_1C01691FD
0x1c0169024  mov     ecx, edi
0x1c0169026  mov     [r14+102h], cx
0x1c016902e  mov     al, [rsp+248h+arg_28]
0x1c0169035  neg     al
0x1c0169037  sbb     r8d, r8d
0x1c016903a  not     r8d
0x1c016903d  and     r8d, edx
0x1c0169040  mov     rdx, r14
0x1c0169043  mov     rcx, rbx
0x1c0169046  call    RefsInitializeFileFromDisk
0x1c016904b  mov     edi, eax
0x1c016904d  mov     [rsp+248h+Status], eax
0x1c0169051  xor     edx, edx
0x1c0169053  test    eax, eax
0x1c0169055  js      loc_1C0169695
0x1c016905b  cmp     [rsp+248h+arg_28], dl
0x1c0169062  jz      loc_1C016983A
0x1c0169068  test    sil, sil
0x1c016906b  jnz     short loc_1C0169093
0x1c016906d  mov     rcx, rbx
0x1c0169070  call    RefsBindMinstoreTransaction
0x1c0169075  mov     r8b, 1
0x1c0169078  mov     rdx, r14
0x1c016907b  mov     rcx, rbx
0x1c016907e  call    RefsCreateDataStream
0x1c0169083  mov     edi, eax
0x1c0169085  mov     [rsp+248h+Status], eax
0x1c0169089  xor     edx, edx
0x1c016908b  test    eax, eax
0x1c016908d  js      loc_1C01697BE
0x1c0169093  mov     al, sil
0x1c0169096  neg     al
0x1c0169098  sbb     r8, r8
0x1c016909b  and     r8, r14
0x1c016909e  mov     [rsp+248h+var_208], rdx
0x1c01690a3  mov     dword ptr [rsp+248h+var_210], edx
0x1c01690a7  mov     byte ptr [rsp+248h+var_218], dl
0x1c01690ab  mov     byte ptr [rsp+248h+var_220], dl
0x1c01690af  mov     r9b, sil
0x1c01690b2  mov     rdx, r15
0x1c01690b5  mov     rcx, rbx
0x1c01690b8  call    RefsInitializeFcbAndStdInfo
0x1c01690bd  xor     edx, edx
0x1c01690bf  test    sil, sil
0x1c01690c2  jnz     loc_1C0169211
0x1c01690c8  cmp     [rsp+248h+arg_40], dl
0x1c01690cf  jnz     loc_1C01694FD
0x1c01690d5  mov     rax, [rsp+248h+var_1C8]
0x1c01690dd  cmp     [rax+40h], rdx
0x1c01690e1  jnz     loc_1C0169228
0x1c01690e7  mov     esi, 4
0x1c01690ec  mov     rcx, rbx
0x1c01690ef  call    RefsCheckpointCurrentTransaction
0x1c01690f4  mov     r13b, [rsp+248h+arg_30]
0x1c01690fc  test    r13b, r13b
0x1c01690ff  jnz     short loc_1C016915D
0x1c0169101  xor     r8d, r8d
0x1c0169104  mov     rdx, r14
0x1c0169107  mov     rcx, rbx
0x1c016910a  call    RefsAcquireExclusiveScbWithFlags
0x1c016910f  mov     cl, [rsp+248h+arg_38]
0x1c0169116  xor     edx, edx
0x1c0169118  test    cl, cl
0x1c016911a  jnz     loc_1C01695CA
0x1c0169120  cmp     [rsp+248h+arg_28], dl
0x1c0169127  jz      short loc_1C0169132
0x1c0169129  test    r13b, r13b
0x1c016912c  jnz     loc_1C01692DE
0x1c0169132  xor     r9d, r9d
0x1c0169135  mov     r8, r15
0x1c0169138  xor     edx, edx
0x1c016913a  mov     rcx, rbx
0x1c016913d  call    RefsUpdateFcbInfoFromDisk
0x1c0169142  xor     esi, esi
0x1c0169144  test    r13b, r13b
0x1c0169147  jz      loc_1C01698EB
0x1c016914d  mov     rdx, r14
0x1c0169150  mov     rcx, rbx
0x1c0169153  call    RefsUpdateIndexScbFromAttribute
0x1c0169158  jmp     loc_1C01698EB
0x1c016915d  mov     rax, [rsp+248h+SourceString]
0x1c0169162  movzx   edx, word ptr [rax]; NumberOfBytes
0x1c0169165  mov     ecx, 11h; PoolType
0x1c016916a  mov     r8d, 6F4D6552h; Tag
0x1c0169170  call    cs:__imp_ExAllocatePoolWithTag
0x1c0169177  nop     dword ptr [rax+rax+00h]
0x1c016917c  mov     [r14+170h], rax
0x1c0169183  mov     rdx, [rsp+248h+SourceString]; SourceString
0x1c0169188  movzx   eax, word ptr [rdx]
0x1c016918b  mov     [r14+16Ah], ax
0x1c0169193  lea     rcx, [r14+168h]; DestinationString
0x1c016919a  call    cs:__imp_RtlCopyUnicodeString
0x1c01691a1  nop     dword ptr [rax+rax+00h]
0x1c01691a6  xor     eax, eax
0x1c01691a8  mov     [r14+178h], eax
0x1c01691af  mov     r8, [r14+170h]
0x1c01691b6  mov     [rsp+248h+var_190], r8
0x1c01691be  lea     r10, [r8+2]
0x1c01691c2  mov     r9d, eax
0x1c01691c5  lea     r11d, [rax+2]
0x1c01691c9  cmp     r8, r10
0x1c01691cc  jnb     loc_1C01692D2
0x1c01691d2  movzx   ecx, word ptr [r8]
0x1c01691d6  mov     rax, [rsp+248h+var_1C8]
0x1c01691de  mov     rax, [rax+2A0h]
0x1c01691e5  movzx   edx, word ptr [rax+rcx*2]
0x1c01691e9  imul    r9d, 25h ; '%'
0x1c01691ed  add     r9d, edx
0x1c01691f0  add     r8, r11
0x1c01691f3  mov     [rsp+248h+var_190], r8
0x1c01691fb  jmp     short loc_1C01691C9
0x1c01691fd  mov     rcx, [rax+80h]
0x1c0169204  call    RefsGetStreamChecksumType
0x1c0169209  movzx   ecx, ax
0x1c016920c  jmp     loc_1C0169026
0x1c0169211  mov     word ptr [rsp+248h+var_220], dx
0x1c0169216  mov     rdx, r15
0x1c0169219  mov     rcx, rbx
0x1c016921c  call    RefsCreateIndex
0x1c0169221  xor     edx, edx
0x1c0169223  jmp     loc_1C01690D5
0x1c0169228  mov     esi, 4
0x1c016922d  mov     [rsp+248h+var_1EC], esi
0x1c0169231  cmp     qword ptr [r13+8], 600h
0x1c0169239  jz      loc_1C0169824
0x1c016923f  mov     rdi, cs:NewDescriptor
0x1c0169246  mov     rcx, rbx
0x1c0169249  call    RefsCheckpointCurrentTransaction
0x1c016924e  mov     r9, rdi
0x1c0169251  lea     r8, [rsp+248h+var_1EC]
0x1c0169256  mov     rdx, r15
0x1c0169259  mov     rcx, rbx
0x1c016925c  call    RefsModifySecurity
0x1c0169261  mov     edi, eax
0x1c0169263  mov     [rsp+248h+Status], eax
0x1c0169267  test    eax, eax
0x1c0169269  jns     loc_1C01690EC
0x1c016926f  lea     rax, WPP_GLOBAL_Control
0x1c0169276  mov     rcx, cs:WPP_GLOBAL_Control
0x1c016927d  cmp     rcx, rax
0x1c0169280  jz      short loc_1C01692A6
0x1c0169282  test    [rcx+2Ch], r12d
0x1c0169286  jz      short loc_1C01692A6
0x1c0169288  cmp     [rcx+29h], sil
  ... truncated ...
```
