# RefsQueryAllocatedRanges

- ea: `0x1c01af5ac`
- end: `0x1c01b03ca`
- name: `RefsQueryAllocatedRanges`
- size: `3614`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1c015c128`

## callees

- `0x1c0001d74`
- `0x1c0003eb4`
- `0x1c0004300`
- `0x1c00049a0`
- `0x1c0004a30`
- `0x1c0005768`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003b27c`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c009df4c`
- `0x1c01632d4`
- `0x1c01634c8`
- `0x1c018c374`
- `0x1c018ca44`
- `0x1c018f6fc`
- `0x1c01af5ac`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c01b02ef`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01b039a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01b02ef`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c01b039a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01af9a7`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01affb7`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01af9a7`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01affb7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01af9d6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01afa10`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01b0000`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01b0064`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01af9d6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01afa10`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01b0000`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01b0064`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c01afd49`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c01afd49`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1c01afc99`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1c01afc99`
- `ntoskrnl!ProbeForWrite` at `0x1c01af905`
- `ntoskrnl!ProbeForWrite` at `0x1c01af905`
- `ntoskrnl!ProbeForRead` at `0x1c01af8ed`
- `ntoskrnl!ProbeForRead` at `0x1c01af8ed`

## pseudocode

```c
__int64 __fastcall RefsQueryAllocatedRanges(__int64 a1, struct _IO_STATUS_BLOCK *a2)
{
  struct _IO_STATUS_BLOCK *v2; // r13
  ULONG_PTR Information; // r14
  __int64 v5; // r8
  __int64 v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  signed int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // r12d
  __int64 *v16; // rdi
  int v17; // ebx
  __int64 *v18; // r12
  __int64 v19; // r13
  __int64 v20; // r12
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdi
  char v24; // r8
  __int64 v25; // r10
  __int64 v26; // r14
  __int64 v27; // r9
  __int64 v28; // rbx
  __int64 v29; // rbx
  __int64 v30; // rbx
  __int64 v31; // r12
  __int64 v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // r13
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rdi
  bool v38; // r13
  char IsRangeAllocated; // al
  char v40; // bl
  __int64 v41; // r8
  __int64 v42; // rcx
  int Flags; // [rsp+20h] [rbp-108h]
  char v44; // [rsp+41h] [rbp-E7h]
  unsigned int Status; // [rsp+44h] [rbp-E4h]
  __int64 *v46; // [rsp+48h] [rbp-E0h]
  __int64 v47; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v48; // [rsp+58h] [rbp-D0h]
  unsigned int v49; // [rsp+60h] [rbp-C8h]
  __int64 v50; // [rsp+68h] [rbp-C0h] BYREF
  __int64 *v51; // [rsp+70h] [rbp-B8h]
  __int64 v52; // [rsp+78h] [rbp-B0h]
  __int64 v53; // [rsp+80h] [rbp-A8h]
  __int64 v54; // [rsp+88h] [rbp-A0h]
  __int64 v55; // [rsp+90h] [rbp-98h]
  __int64 v56; // [rsp+98h] [rbp-90h]
  __int64 v57; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-80h]
  __int64 v59; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v60; // [rsp+B8h] [rbp-70h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v62; // [rsp+C8h] [rbp-60h]
  __int64 v63; // [rsp+D0h] [rbp-58h]
  __int64 v64; // [rsp+D8h] [rbp-50h]
  _BYTE *v65; // [rsp+E0h] [rbp-48h]
  __int64 v66; // [rsp+E8h] [rbp-40h]
  __int64 v68; // [rsp+140h] [rbp+18h]
  bool v69; // [rsp+140h] [rbp+18h]
  __int64 v70; // [rsp+148h] [rbp+20h] BYREF

  v2 = a2;
  Information = a2[11].Information;
  v44 = 0;
  v50 = 0;
  v60 = 0;
  v70 = 0;
  v59 = 0;
  v54 = 0;
  v53 = 0;
  a2[3].Information = 0;
  *(_DWORD *)(a1 + 8) |= 1u;
  if ( (unsigned int)RefsDecodeFileObject(
                       a1,
                       *(_QWORD *)(Information + 48),
                       (unsigned int)&v50,
                       (unsigned int)&v60,
                       (__int64)&v70,
                       (__int64)&v59,
                       0) != 2 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(a1, v2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 240, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return 3221225485LL;
    goto LABEL_19;
  }
  if ( v59 && (*(_DWORD *)(v59 + 4) & 0x2000) != 0 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(a1, v2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 241, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return 3221225485LL;
LABEL_19:
    RefsStatusDebug(-1073741811);
    return 3221225485LL;
  }
  LOBYTE(v5) = 1;
  v7 = v70;
  RefsAcquireExclusivePagingIoSpecifyWait(a1, *(_QWORD *)(v70 + 120), v5);
  v10 = *(_DWORD *)(v7 + 304);
  if ( (v10 & 0x10000) != 0 )
    v11 = -1073741202;
  else
    v11 = (v10 & 0x1000000) != 0 ? 0xC0000008 : 0;
  Status = v11;
  if ( v11 < 0 )
    goto LABEL_149;
  if ( !(unsigned __int8)RefsIsFileOpen(v60, v8, v9) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 242, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225768LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528);
    Status = -1073741528;
LABEL_33:
    v7 = v70;
    goto LABEL_149;
  }
  if ( *(_DWORD *)(Information + 16) < 0x10u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 243, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    Status = -1073741811;
    goto LABEL_33;
  }
  v15 = *(_DWORD *)(Information + 8);
  v49 = v15;
  v16 = (__int64 *)RefsMapUserBuffer(v2, v12, v13, v14);
  v51 = v16;
  v17 = (_DWORD)v16 - 16;
  v46 = v16 - 2;
  if ( LOBYTE(v2[4].Status) )
  {
    ProbeForRead(*(volatile void **)(Information + 32), *(unsigned int *)(Information + 16), 4u);
    ProbeForWrite(v16, v15, 4u);
    v18 = *(__int64 **)(Information + 32);
  }
  else
  {
    v18 = *(__int64 **)(Information + 32);
    if ( v18 != (__int64 *)(((unsigned __int64)v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL)
      || v16 != (__int64 *)(((unsigned __int64)v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 244, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225704LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741592);
      Status = -1073741592;
      goto LABEL_146;
    }
  }
  v19 = *v18;
  v54 = *v18;
  v20 = v18[1];
  v53 = v20;
  if ( v20 < 0 || v19 < 0 || v20 > 0x7FFFFFFFFFFFFFFFLL - v19 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 245, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    Status = -1073741811;
LABEL_129:
    v2 = a2;
    goto LABEL_146;
  }
  if ( !v20 )
  {
    v2 = a2;
    goto LABEL_148;
  }
  RefsAcquireExclusiveScbWithFlags(a1, v7, 0);
  v44 = 1;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v7 + 48));
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 156));
  v21 = *(_QWORD *)(v70 + 32);
  if ( v19 >= v21 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 156));
    ExReleaseFastMutex(*(PFAST_MUTEX *)(v7 + 48));
    v2 = a2;
LABEL_146:
    v17 = (_DWORD)v16 - 16;
    v7 = v70;
    goto LABEL_147;
  }
  v22 = v21 - v19;
  if ( v22 < v20 )
  {
    v53 = v22;
    v20 = v22;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 156));
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v7 + 48));
  v7 = v70;
  if ( *(__int16 *)(v70 + 252) >= 0 || (*(_DWORD *)(v70 + 136) & 8) != 0 )
  {
    if ( v49 >= 0x10 )
    {
      v17 = (int)v16;
      *v16 = v54;
      v46[3] = v53;
      v2 = a2;
      a2[3].Information = 16;
LABEL_147:
      LODWORD(v16) = (_DWORD)v51;
      goto LABEL_148;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 246, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225507LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789);
    Status = -1073741789;
    goto LABEL_129;
  }
  v64 = -1;
  v23 = v50;
  v65 = (_BYTE *)(v50 + 464);
  v24 = *(_BYTE *)(v50 + 464);
  v52 = v19 >> v24;
  v25 = -*(_DWORD *)(v50 + 2572);
  v26 = v25 & (v19 >> v24);
  v52 = v26;
  v27 = *(unsigned int *)(v50 + 2568);
  v28 = v20 + v19;
  if ( v20 + v19 >= (__int64)(0x8000000000000000uLL - v27) )
  {
    v48 = v28 >> v24;
    v29 = ((__int64)((unsigned int)v27 + (*(_DWORD *)(v50 + 456) & ((_DWORD)v53 + (_DWORD)v54)) - 1) >> v24)
        + (v28 >> v24);
  }
  else
  {
    v29 = (v20 + v19 + v27 - 1) >> v24;
  }
  v30 = (v25 & v29) - v26;
  v48 = v30;
  v66 = 0x2000000000LL >> v24;
  RefsBindMinstoreTransaction(a1);
LABEL_60:
  v31 = v66;
  v58 = v66;
  if ( v66 > v30 )
    v31 = v30;
  v58 = v31;
  v48 = v30 - v31;
  if ( (*(_BYTE *)(v7 + 4) & 0x20) != 0
    && (*(_DWORD *)(v7 + 304) & 0x2000) != 0
    && *(_QWORD *)(*(_QWORD *)(v7 + 240) + 8LL) )
  {
    v57 = 0;
    v55 = 0;
    v32 = v31;
    v62 = v31;
    FileOffset.QuadPart = 0;
    v33 = v26;
    v63 = v26;
    v56 = 0;
    v68 = 0x80000000LL >> *v65;
    v34 = v50;
    while ( 1 )
    {
      if ( !(unsigned __int8)RefsIsRangeAllocated(a1, v7, v33, (int)v33 + (int)v32, Flags, (__int64)&v57) )
      {
        if ( !*(_QWORD *)(v7 + 224) )
          RefsCreateInternalAttributeStream(a1, v7, 0, 0);
        RefsCheckpointCurrentTransaction(a1);
        RefsReleaseFcb(a1, *(_QWORD *)(v7 + 120));
        v35 = v57;
        v55 = v57;
        v36 = v33;
        v56 = v33;
        while ( v35 )
        {
          v37 = v35;
          if ( v35 > v68 )
            v37 = v68;
          FileOffset.QuadPart = v36 << *(_BYTE *)(v34 + 464);
          CcCoherencyFlushAndPurgeCache(
            (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v7 + 240) + 8LL),
            &FileOffset,
            v37 << *(_BYTE *)(v34 + 464),
            a2 + 3,
            3u);
          RefsNormalizeAndCleanupTransaction(a1, &a2[3]);
          RefsCheckpointCurrentTransaction(a1);
          v35 = v55 - v37;
          v55 -= v37;
          v36 = v37 + v56;
          v56 += v37;
        }
        RefsAcquireExclusiveScbWithFlags(a1, v7, 0);
        v44 = 1;
        RefsBindMinstoreTransaction(a1);
        v33 = v63;
        v32 = v62;
      }
      if ( v32 <= v57 )
        break;
      v32 -= v57;
      v62 = v32;
      v33 += v57;
      v63 = v33;
    }
    v23 = v50;
  }
  v38 = MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v7 + 240) + 8LL), 0) == 0;
  v69 = v38;
  while ( 1 )
  {
    v47 = 0;
    IsRangeAllocated = RefsIsRangeAllocated(a1, v7, v26, (int)v31 + (int)v26, Flags, (__int64)&v47);
    v40 = IsRangeAllocated;
    if ( (v38 || (*(_BYTE *)(v7 + 4) & 0x20) == 0)
      && !IsRangeAllocated
      && (unsigned __int8)RefsCheckForReservedClusters(v7, v26, &v47)
      && v47 < *(unsigned int *)(v23 + 2572) )
    {
      v40 = 1;
      v47 = *(unsigned int *)(v23 + 2572);
    }
    if ( v40 )
      break;
    v52 = v47 + v26;
LABEL_114:
    ExAcquireFastMutex(*(PFAST_MUTEX *)(v7 + 48));
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 156));
    v65 = (_BYTE *)(v50 + 464);
    if ( v52 << *(_BYTE *)(v50 + 464) >= *(_QWORD *)(v70 + 32) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v70 + 156));
      v7 = v70;
      ExReleaseFastMutex(*(PFAST_MUTEX *)(v70 + 48));
      v30 = 0;
      v48 = 0;
      goto LABEL_119;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 156));
    ExReleaseFastMutex(*(PFAST_MUTEX *)(v7 + 48));
    v31 = v58 - v47;
    v58 = v31;
    v7 = v70;
    if ( v31 <= 0 )
    {
      v30 = v48;
LABEL_119:
      if ( !v30 )
        goto LABEL_107;
      v26 = v52;
      v23 = v50;
      goto LABEL_60;
    }
    v26 = v52;
    v38 = v69;
    v23 = v50;
  }
  if ( v64 == v26 )
  {
    v46[1] += v47 << *(_BYTE *)(v23 + 464);
LABEL_90:
    v52 = v47 + v26;
    v64 = v47 + v26;
    goto LABEL_114;
  }
  if ( v49 >= 0x10 )
  {
    v49 -= 16;
    v46 += 2;
    *v46 = v26 << *(_BYTE *)(v23 + 464);
    v46[1] = v47 << *(_BYTE *)(v23 + 464);
    goto LABEL_90;
  }
  if ( v46 + 2 == v51 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 247, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225507LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789);
    Status = -1073741789;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 248, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 2147483653LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-2147483643);
    Status = -2147483643;
  }
  v48 = 0;
  v7 = v70;
LABEL_107:
  v16 = v51;
  v17 = (int)v46;
  if ( v46 != v51 - 2 )
  {
    v41 = v54;
    if ( *v51 < v54 )
    {
      v51[1] += *v51 - v54;
      *v16 = v41;
    }
    if ( *v46 + v46[1] > v53 + v41 )
      v46[1] = v41 + v53 - *v46;
  }
  v2 = a2;
LABEL_148:
  v2[3].Information = (unsigned int)(v17 - (_DWORD)v16 + 16);
  RefsCheckpointCurrentTransaction(a1);
  RefsFlushForWriteThrough(a1, v7);
LABEL_149:
  v42 = *(_QWORD *)(v7 + 120);
  if ( *(_WORD *)v42 != 2050 )
    v42 = *(_QWORD *)(v42 + 120);
  ExReleaseResourceLite(*(PERESOURCE *)(v42 + 104));
  *(_QWORD *)(a1 + 56) = 0;
  if ( v44 )
    RefsReleaseFcb(a1, *(_QWORD *)(v7 + 120));
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  RefsExtendedCompleteRequestInternal(a1, v2, Status);
  return Status;
}

```

## disassembly

```asm
0x1c01af5ac  mov     r11, rsp
0x1c01af5af  mov     [r11+10h], rdx
0x1c01af5b3  mov     [r11+8], rcx
0x1c01af5b7  push    rbx
0x1c01af5b8  push    rsi
0x1c01af5b9  push    rdi
0x1c01af5ba  push    r12
0x1c01af5bc  push    r13
0x1c01af5be  push    r14
0x1c01af5c0  push    r15
0x1c01af5c2  sub     rsp, 0F0h
0x1c01af5c9  mov     r13, rdx
0x1c01af5cc  mov     r15, rcx
0x1c01af5cf  mov     r14, [rdx+0B8h]
0x1c01af5d6  xor     r12d, r12d
0x1c01af5d9  mov     [rsp+128h+var_E7], r12b
0x1c01af5de  mov     [rsp+128h+var_C0], r12
0x1c01af5e3  mov     [r11-70h], r12
0x1c01af5e7  mov     [r11+20h], r12
0x1c01af5eb  mov     [r11-78h], r12
0x1c01af5ef  mov     [r11-0A0h], r12
0x1c01af5f6  mov     [r11-0A8h], r12
0x1c01af5fd  mov     [rdx+38h], r12
0x1c01af601  or      dword ptr [rcx+8], 1
0x1c01af605  mov     [rsp+128h+var_F8], r12b
0x1c01af60a  lea     rax, [r11-78h]
0x1c01af60e  mov     [rsp+128h+var_100], rax
0x1c01af613  lea     rax, [r11+20h]
0x1c01af617  mov     qword ptr [rsp+128h+Flags], rax
0x1c01af61c  lea     r9, [r11-70h]
0x1c01af620  lea     r8, [rsp+128h+var_C0]
0x1c01af625  mov     rdx, [r14+30h]
0x1c01af629  call    RefsDecodeFileObject
0x1c01af62e  cmp     eax, 2
0x1c01af631  jz      loc_1C01AF6BB
0x1c01af637  mov     al, cs:RefsStatusDebugEnabled
0x1c01af63d  mov     ebx, 0C000000Dh
0x1c01af642  test    al, al
0x1c01af644  jz      short loc_1C01AF65A
0x1c01af646  mov     r8d, 25C4h
0x1c01af64c  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01af653  mov     ecx, ebx; Status
0x1c01af655  call    RefsStatusDebug
0x1c01af65a  mov     r8d, ebx
0x1c01af65d  mov     rdx, r13
0x1c01af660  mov     rcx, r15
0x1c01af663  call    RefsExtendedCompleteRequestInternal
0x1c01af668  lea     rax, WPP_GLOBAL_Control
0x1c01af66f  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01af676  cmp     rcx, rax
0x1c01af679  jz      short loc_1C01AF6A2
0x1c01af67b  test    dword ptr [rcx+2Ch], 100h
0x1c01af682  jz      short loc_1C01AF6A2
0x1c01af684  cmp     byte ptr [rcx+29h], 4
0x1c01af688  jb      short loc_1C01AF6A2
0x1c01af68a  mov     edx, 0F0h
0x1c01af68f  mov     r9d, ebx
0x1c01af692  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01af699  mov     rcx, [rcx+18h]
0x1c01af69d  call    WPP_SF_D
0x1c01af6a2  mov     al, cs:RefsStatusDebugEnabled
0x1c01af6a8  test    al, al
0x1c01af6aa  jz      loc_1C01AF762
0x1c01af6b0  mov     r8d, 25C5h
0x1c01af6b6  jmp     loc_1C01AF754
0x1c01af6bb  mov     rax, [rsp+128h+var_78]
0x1c01af6c3  test    rax, rax
0x1c01af6c6  jz      loc_1C01AF778
0x1c01af6cc  mov     eax, [rax+4]
0x1c01af6cf  bt      eax, 0Dh
0x1c01af6d3  jnb     loc_1C01AF778
0x1c01af6d9  mov     al, cs:RefsStatusDebugEnabled
0x1c01af6df  mov     ebx, 0C000000Dh
0x1c01af6e4  test    al, al
0x1c01af6e6  jz      short loc_1C01AF6FC
0x1c01af6e8  mov     r8d, 25D1h
0x1c01af6ee  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01af6f5  mov     ecx, ebx; Status
0x1c01af6f7  call    RefsStatusDebug
0x1c01af6fc  mov     r8d, ebx
0x1c01af6ff  mov     rdx, r13
0x1c01af702  mov     rcx, r15
0x1c01af705  call    RefsExtendedCompleteRequestInternal
0x1c01af70a  lea     rax, WPP_GLOBAL_Control
0x1c01af711  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01af718  cmp     rcx, rax
0x1c01af71b  jz      short loc_1C01AF744
0x1c01af71d  test    dword ptr [rcx+2Ch], 100h
0x1c01af724  jz      short loc_1C01AF744
0x1c01af726  cmp     byte ptr [rcx+29h], 4
0x1c01af72a  jb      short loc_1C01AF744
0x1c01af72c  mov     edx, 0F1h
0x1c01af731  mov     r9d, ebx
0x1c01af734  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01af73b  mov     rcx, [rcx+18h]
0x1c01af73f  call    WPP_SF_D
0x1c01af744  mov     cl, cs:RefsStatusDebugEnabled
0x1c01af74a  test    cl, cl
0x1c01af74c  jz      short loc_1C01AF762
0x1c01af74e  mov     r8d, 25D2h
0x1c01af754  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01af75b  mov     ecx, ebx; Status
0x1c01af75d  call    RefsStatusDebug
0x1c01af762  mov     eax, ebx
0x1c01af764  add     rsp, 0F0h
0x1c01af76b  pop     r15
0x1c01af76d  pop     r14
0x1c01af76f  pop     r13
0x1c01af771  pop     r12
0x1c01af773  pop     rdi
0x1c01af774  pop     rsi
0x1c01af775  pop     rbx
0x1c01af776  retn
0x1c01af778  mov     r8b, 1
0x1c01af77b  mov     rsi, [rsp+128h+arg_18]
0x1c01af783  mov     rdx, [rsi+78h]
0x1c01af787  mov     rcx, r15
0x1c01af78a  call    RefsAcquireExclusivePagingIoSpecifyWait
0x1c01af78f  nop
0x1c01af790  mov     eax, [rsi+130h]
0x1c01af796  bt      eax, 10h
0x1c01af79a  jnb     short loc_1C01AF7A3
0x1c01af79c  mov     eax, 0C000026Eh
0x1c01af7a1  jmp     short loc_1C01AF7B1
0x1c01af7a3  and     eax, 1000000h
0x1c01af7a8  neg     eax
0x1c01af7aa  sbb     eax, eax
0x1c01af7ac  and     eax, 0C0000008h
0x1c01af7b1  mov     [rsp+128h+Status], eax
0x1c01af7b5  test    eax, eax
0x1c01af7b7  js      loc_1C01B02D9
0x1c01af7bd  mov     rcx, [rsp+128h+var_70]
0x1c01af7c5  call    RefsIsFileOpen
0x1c01af7ca  test    al, al
0x1c01af7cc  jnz     short loc_1C01AF841
0x1c01af7ce  lea     rax, WPP_GLOBAL_Control
0x1c01af7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01af7dc  cmp     rcx, rax
0x1c01af7df  jz      short loc_1C01AF80B
0x1c01af7e1  test    dword ptr [rcx+2Ch], 100h
0x1c01af7e8  jz      short loc_1C01AF80B
0x1c01af7ea  cmp     byte ptr [rcx+29h], 4
0x1c01af7ee  jb      short loc_1C01AF80B
0x1c01af7f0  mov     edx, 0F2h
0x1c01af7f5  mov     r9d, 0C0000128h
0x1c01af7fb  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01af802  mov     rcx, [rcx+18h]
0x1c01af806  call    WPP_SF_D
0x1c01af80b  mov     al, cs:RefsStatusDebugEnabled
0x1c01af811  test    al, al
0x1c01af813  jz      short loc_1C01AF82C
0x1c01af815  mov     r8d, 25F0h
0x1c01af81b  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01af822  mov     ecx, 0C0000128h; Status
0x1c01af827  call    RefsStatusDebug
0x1c01af82c  mov     [rsp+128h+Status], 0C0000128h
0x1c01af834  mov     rsi, [rsp+128h+arg_18]
0x1c01af83c  jmp     loc_1C01B02D9
0x1c01af841  cmp     dword ptr [r14+10h], 10h
0x1c01af846  jnb     short loc_1C01AF8B2
0x1c01af848  lea     rax, WPP_GLOBAL_Control
0x1c01af84f  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01af856  cmp     rcx, rax
0x1c01af859  jz      short loc_1C01AF889
0x1c01af85b  test    dword ptr [rcx+2Ch], 100h
0x1c01af862  jz      short loc_1C01AF889
0x1c01af864  cmp     byte ptr [rcx+29h], 4
0x1c01af868  jb      short loc_1C01AF889
0x1c01af86a  mov     edx, 0F3h
0x1c01af86f  mov     ebx, 0C000000Dh
0x1c01af874  mov     r9d, ebx
0x1c01af877  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01af87e  mov     rcx, [rcx+18h]
0x1c01af882  call    WPP_SF_D
0x1c01af887  jmp     short loc_1C01AF88E
0x1c01af889  mov     ebx, 0C000000Dh
0x1c01af88e  mov     al, cs:RefsStatusDebugEnabled
0x1c01af894  test    al, al
0x1c01af896  jz      short loc_1C01AF8AC
0x1c01af898  mov     r8d, 25FBh
0x1c01af89e  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01af8a5  mov     ecx, ebx; Status
0x1c01af8a7  call    RefsStatusDebug
0x1c01af8ac  mov     [rsp+128h+Status], ebx
0x1c01af8b0  jmp     short loc_1C01AF834
0x1c01af8b2  mov     [rsp+128h+var_E8], 1
0x1c01af8b7  mov     r12d, [r14+8]
0x1c01af8bb  mov     [rsp+128h+var_C8], r12d
0x1c01af8c0  mov     rcx, r13
0x1c01af8c3  call    RefsMapUserBuffer
0x1c01af8c8  mov     rdi, rax
0x1c01af8cb  mov     [rsp+128h+var_B8], rax
0x1c01af8d0  lea     rbx, [rax-10h]
0x1c01af8d4  mov     [rsp+128h+var_E0], rbx
0x1c01af8d9  xor     eax, eax
0x1c01af8db  cmp     [r13+40h], al
0x1c01af8df  jz      short loc_1C01AF917
0x1c01af8e1  mov     edx, [r14+10h]; Length
0x1c01af8e5  lea     r8d, [rax+4]; Alignment
0x1c01af8e9  mov     rcx, [r14+20h]; Address
0x1c01af8ed  call    cs:__imp_ProbeForRead
0x1c01af8f4  nop     dword ptr [rax+rax+00h]
0x1c01af8f9  mov     edx, r12d; Length
0x1c01af8fc  mov     r8d, 4; Alignment
0x1c01af902  mov     rcx, rdi; Address
0x1c01af905  call    cs:__imp_ProbeForWrite
0x1c01af90c  nop     dword ptr [rax+rax+00h]
0x1c01af911  mov     r12, [r14+20h]
0x1c01af915  jmp     short loc_1C01AF93E
0x1c01af917  mov     r12, [r14+20h]
0x1c01af91b  lea     rax, [r12+3]
0x1c01af920  and     rax, 0FFFFFFFFFFFFFFFCh
0x1c01af924  cmp     r12, rax
0x1c01af927  jnz     loc_1C01B01CF
0x1c01af92d  lea     rax, [rdi+3]
0x1c01af931  and     rax, 0FFFFFFFFFFFFFFFCh
0x1c01af935  cmp     rdi, rax
0x1c01af938  jnz     loc_1C01B01CF
0x1c01af93e  mov     r13, [r12]
0x1c01af942  mov     [rsp+128h+var_A0], r13
0x1c01af94a  mov     r12, [r12+8]
0x1c01af94f  mov     [rsp+128h+var_A8], r12
0x1c01af957  xor     r14d, r14d
0x1c01af95a  mov     [rsp+128h+var_E8], r14b
0x1c01af95f  test    r12, r12
0x1c01af962  js      loc_1C01B015F
0x1c01af968  test    r13, r13
0x1c01af96b  js      loc_1C01B015F
0x1c01af971  mov     rax, 7FFFFFFFFFFFFFFFh
0x1c01af97b  sub     rax, r13
0x1c01af97e  cmp     r12, rax
0x1c01af981  jg      loc_1C01B015F
0x1c01af987  test    r12, r12
0x1c01af98a  jz      loc_1C01B014F
0x1c01af990  xor     r8d, r8d
0x1c01af993  mov     rdx, rsi
0x1c01af996  mov     rcx, r15
0x1c01af999  call    RefsAcquireExclusiveScbWithFlags
0x1c01af99e  mov     [rsp+128h+var_E7], 1
0x1c01af9a3  mov     rcx, [rsi+30h]; FastMutex
0x1c01af9a7  call    cs:__imp_ExAcquireFastMutex
0x1c01af9ae  nop     dword ptr [rax+rax+00h]
0x1c01af9b3  lock inc dword ptr [rsi+9Ch]
0x1c01af9ba  mov     rax, [rsp+128h+arg_18]
0x1c01af9c2  mov     rcx, [rax+20h]
0x1c01af9c6  cmp     r13, rcx
0x1c01af9c9  jl      short loc_1C01AF9F2
0x1c01af9cb  lock inc dword ptr [rsi+9Ch]
0x1c01af9d2  mov     rcx, [rsi+30h]; FastMutex
0x1c01af9d6  call    cs:__imp_ExReleaseFastMutex
0x1c01af9dd  nop     dword ptr [rax+rax+00h]
0x1c01af9e2  mov     r13, [rsp+128h+arg_8]
0x1c01af9ea  xor     r12d, r12d
0x1c01af9ed  jmp     loc_1C01B0238
0x1c01af9f2  sub     rcx, r13
0x1c01af9f5  cmp     rcx, r12
0x1c01af9f8  jge     short loc_1C01AFA05
0x1c01af9fa  mov     [rsp+128h+var_A8], rcx
0x1c01afa02  mov     r12, rcx
0x1c01afa05  lock inc dword ptr [rsi+9Ch]
0x1c01afa0c  mov     rcx, [rsi+30h]; FastMutex
0x1c01afa10  call    cs:__imp_ExReleaseFastMutex
0x1c01afa17  nop     dword ptr [rax+rax+00h]
0x1c01afa1c  mov     rsi, [rsp+128h+arg_18]
0x1c01afa24  cmp     [rsi+0FCh], r14w
0x1c01afa2c  jge     loc_1C01B0090
0x1c01afa32  mov     eax, [rsi+88h]
0x1c01afa38  test    al, 8
0x1c01afa3a  jnz     loc_1C01B0090
0x1c01afa40  or      [rsp+128h+var_50], 0FFFFFFFFFFFFFFFFh
0x1c01afa49  mov     rdi, [rsp+128h+var_C0]
0x1c01afa4e  lea     rax, [rdi+1D0h]
0x1c01afa55  mov     [rsp+128h+var_48], rax
0x1c01afa5d  movsx   r8d, byte ptr [rax]
0x1c01afa61  mov     r14, r13
0x1c01afa64  mov     ecx, r8d
0x1c01afa67  sar     r14, cl
0x1c01afa6a  mov     [rsp+128h+var_B0], r14
0x1c01afa6f  mov     eax, [rdi+0A0Ch]
0x1c01afa75  neg     eax
0x1c01afa77  movsxd  r10, eax
0x1c01afa7a  and     r14, r10
0x1c01afa7d  mov     [rsp+128h+var_B0], r14
0x1c01afa82  mov     r9d, [rdi+0A08h]
0x1c01afa89  lea     rbx, [r12+r13]
0x1c01afa8d  mov     rax, 8000000000000000h
0x1c01afa97  sub     rax, r9
0x1c01afa9a  cmp     rbx, rax
0x1c01afa9d  jge     short loc_1C01AFAAF
0x1c01afa9f  lea     rax, [r12+r13]
0x1c01afaa3  lea     rbx, [r9-1]
0x1c01afaa7  add     rbx, rax
0x1c01afaaa  sar     rbx, cl
0x1c01afaad  jmp     short loc_1C01AFADA
0x1c01afaaf  sar     rbx, cl
0x1c01afab2  mov     [rsp+128h+var_D0], rbx
0x1c01afab7  mov     rdx, [rsp+128h+var_A0]
0x1c01afabf  mov     rax, [rsp+128h+var_A8]
0x1c01afac7  add     edx, eax
0x1c01afac9  and     edx, [rdi+1C8h]
  ... truncated ...
```
