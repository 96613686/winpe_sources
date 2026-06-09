# FatCommonRead

- ea: `0x14004573c`
- end: `0x1400463f0`
- name: `FatCommonRead`
- size: `3252`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, __int64)`
- caller_count: `3`
- callee_count: `21`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140006030`
- `0x1400438e0`
- `0x140046500`

## callees

- `0x140001858`
- `0x140007408`
- `0x14000c680`
- `0x1400226b8`
- `0x14002d4a8`
- `0x14002d5a8`
- `0x14002d918`
- `0x14002e0cc`
- `0x14002e6ac`
- `0x14002e95c`
- `0x140038eb4`
- `0x14003958c`
- `0x14003d880`
- `0x14003e94c`
- `0x14004573c`
- `0x1400465f4`
- `0x1400468c4`
- `0x140046998`
- `0x1400483bc`
- `0x140049fa8`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140045906`
- `ntoskrnl!KeInitializeEvent` at `0x140045906`
- `ntoskrnl!IoFreeMdl` at `0x1400461a6`
- `ntoskrnl!IoFreeMdl` at `0x14005f79c`
- `ntoskrnl!IoFreeMdl` at `0x1400461a6`
- `ntoskrnl!IoFreeMdl` at `0x14005f79c`
- `ntoskrnl!CcFlushCache` at `0x140045bae`
- `ntoskrnl!CcFlushCache` at `0x140045bae`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140045b1a`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140045fdd`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004638d`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140045b1a`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140045fdd`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14004638d`
- `ntoskrnl!FsRtlCheckOplock` at `0x140045cd2`
- `ntoskrnl!FsRtlCheckOplock` at `0x140045cd2`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140045d15`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140045d15`
- `ntoskrnl!PsUpdateDiskCounters` at `0x140046352`
- `ntoskrnl!PsUpdateDiskCounters` at `0x140046352`
- `ntoskrnl!PsGetThreadProcess` at `0x14004632f`
- `ntoskrnl!PsGetThreadProcess` at `0x14004632f`
- `ntoskrnl!IoGetFsZeroingOffset` at `0x140045e22`
- `ntoskrnl!IoGetFsZeroingOffset` at `0x140045e22`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x140045d79`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x140045d79`
- `ntoskrnl!IoSetFsZeroingOffset` at `0x140045edf`
- `ntoskrnl!IoSetFsZeroingOffset` at `0x140045f3d`
- `ntoskrnl!IoSetFsZeroingOffset` at `0x140045edf`
- `ntoskrnl!IoSetFsZeroingOffset` at `0x140045f3d`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x14004607e`
- `ntoskrnl!CcSetReadAheadGranularity` at `0x14004607e`
- `ntoskrnl!CcCopyReadEx` at `0x1400460cc`
- `ntoskrnl!CcCopyReadEx` at `0x1400460cc`
- `ntoskrnl!CcMdlRead` at `0x140046117`
- `ntoskrnl!CcMdlRead` at `0x140046117`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045b89`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045bf1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140046216`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045b89`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140045bf1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140046216`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045bbe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045bce`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045c01`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046174`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046243`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f721`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f76a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045bbe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045bce`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045c01`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046174`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046243`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f721`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f76a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140045c28`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140045c28`
- `ntoskrnl!KeBugCheckEx` at `0x1400459f9`
- `ntoskrnl!KeBugCheckEx` at `0x1400459f9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400458b4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400458b4`
- `ntoskrnl!ExRaiseStatus` at `0x140045b28`
- `ntoskrnl!ExRaiseStatus` at `0x140045eab`
- `ntoskrnl!ExRaiseStatus` at `0x140045f0f`
- `ntoskrnl!ExRaiseStatus` at `0x140045feb`
- `ntoskrnl!ExRaiseStatus` at `0x14004604b`
- `ntoskrnl!ExRaiseStatus` at `0x14004639b`
- `ntoskrnl!ExRaiseStatus` at `0x140045b28`
- `ntoskrnl!ExRaiseStatus` at `0x140045eab`
- `ntoskrnl!ExRaiseStatus` at `0x140045f0f`
- `ntoskrnl!ExRaiseStatus` at `0x140045feb`
- `ntoskrnl!ExRaiseStatus` at `0x14004604b`
- `ntoskrnl!ExRaiseStatus` at `0x14004639b`

## pseudocode

```c
__int64 __fastcall FatCommonRead(__int64 a1, IRP *a2)
{
  struct _FILE_OBJECT *v4; // rcx
  int v5; // r12d
  ULONG Flags; // edi
  ULONG v7; // eax
  union _LARGE_INTEGER ByteOffset; // rbx
  signed __int64 Length; // r15
  int v11; // eax
  __int64 v12; // r8
  ULONG_PTR v13; // r13
  char v14; // di
  unsigned __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  unsigned int v18; // eax
  _BYTE *PoolWithTag; // rax
  PFILE_OBJECT v20; // rcx
  bool v21; // dl
  char v22; // r12
  int Status; // edi
  char *v24; // r13
  bool v25; // zf
  unsigned int v26; // ecx
  PFILE_OBJECT v27; // r15
  bool v28; // al
  int Information; // eax
  NTSTATUS v30; // eax
  __int64 v31; // rax
  char v32; // al
  unsigned int v33; // eax
  unsigned int v34; // edx
  unsigned int v35; // eax
  __int64 v36; // rcx
  unsigned int v37; // eax
  char *v38; // r9
  unsigned int v39; // edx
  unsigned int v40; // eax
  NTSTATUS v41; // eax
  int v42; // r10d
  unsigned int *v43; // rax
  PVOID v44; // rax
  __int64 v45; // r9
  __int64 v46; // r8
  ULONG v47; // r8d
  struct _ERESOURCE *v48; // rcx
  struct _MDL *v49; // rcx
  union _LARGE_INTEGER v50; // rdi
  __int64 v51; // r13
  __int64 v52; // rbx
  int v53; // eax
  unsigned int v54; // ecx
  signed __int64 v55; // rdx
  unsigned __int64 v56; // rcx
  PEPROCESS ThreadProcess; // rax
  NTSTATUS v58; // ebx
  NTSTATUS v59; // eax
  SIZE_T BugCheckParameter4; // [rsp+20h] [rbp-138h]
  char v61; // [rsp+41h] [rbp-117h]
  PFILE_OBJECT FileObject; // [rsp+48h] [rbp-110h]
  char v63; // [rsp+50h] [rbp-108h]
  unsigned int v64; // [rsp+50h] [rbp-108h]
  bool v65; // [rsp+54h] [rbp-104h]
  int v66; // [rsp+58h] [rbp-100h]
  __int64 v67; // [rsp+60h] [rbp-F8h] BYREF
  ULONG_PTR BugCheckParameter3; // [rsp+68h] [rbp-F0h] BYREF
  unsigned int v69; // [rsp+70h] [rbp-E8h]
  unsigned int v70; // [rsp+74h] [rbp-E4h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+78h] [rbp-E0h] BYREF
  BOOL v72; // [rsp+80h] [rbp-D8h]
  unsigned int v73; // [rsp+84h] [rbp-D4h]
  int v74; // [rsp+88h] [rbp-D0h]
  unsigned int v75; // [rsp+8Ch] [rbp-CCh]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+90h] [rbp-C8h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+98h] [rbp-C0h] BYREF
  _BYTE v78[168]; // [rsp+B0h] [rbp-A8h] BYREF
  __int64 v79; // [rsp+170h] [rbp+18h] BYREF
  bool v80; // [rsp+178h] [rbp+20h]

  v67 = 0;
  BugCheckParameter3 = 0;
  v79 = 0;
  memset(v78, 0, 0x70u);
  FileOffset.QuadPart = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = CurrentStackLocation->FileObject;
  FileObject = v4;
  v5 = *(_DWORD *)(a1 + 68) & 2;
  v66 = v5;
  v65 = v5 != 0;
  Flags = a2->Flags;
  v80 = (Flags & 2) != 0;
  v7 = v4->Flags;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  FileOffset = ByteOffset;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( !(_DWORD)Length )
  {
    a2->IoStatus.Information = 0;
    FatCompleteRequest_Real((PVOID)a1, a2);
    return 0;
  }
  v74 = v7 & 2;
  v11 = FatDecodeFileObject(v4, &v67, &BugCheckParameter3, &v79);
  v13 = v11;
  if ( v11 == 4 )
    v14 = 1;
  else
    v14 = Flags & 1;
  v63 = v14;
  if ( v80 )
  {
    v15 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
    v16 = *(_QWORD *)(v67 + 1024);
    if ( v11 == 2 )
    {
      ++*(_DWORD *)(v15 + v16 + 8);
      *(_DWORD *)(v15 + v16 + 12) += Length;
    }
    else if ( (unsigned int)(v11 - 5) <= 1 )
    {
      ++*(_DWORD *)(v15 + v16 + 32);
      *(_DWORD *)(v15 + v16 + 36) += Length;
    }
    v17 = *(_DWORD *)(a1 + 68);
    if ( (_DWORD)v13 == 2 )
      v18 = v17 | 0x400;
    else
      v18 = v17 & 0xFFFFFBFF;
    *(_DWORD *)(a1 + 68) = v18;
  }
  if ( !v14 )
    goto LABEL_22;
  PoolWithTag = *(_BYTE **)(a1 + 80);
  if ( !PoolWithTag )
  {
    if ( v5 )
    {
      *(_QWORD *)(a1 + 80) = v78;
      *(_DWORD *)(a1 + 68) |= 0x100u;
      PoolWithTag = v78;
    }
    else
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)528, 0x70u, 0x58746146u);
      *(_QWORD *)(a1 + 80) = PoolWithTag;
    }
  }
  memset(PoolWithTag, 0, 0x70u);
  if ( v5 )
  {
    KeInitializeEvent((PRKEVENT)(*(_QWORD *)(a1 + 80) + 24LL), NotificationEvent, 0);
LABEL_22:
    v20 = FileObject;
    v21 = v80;
    goto LABEL_23;
  }
  v21 = v80;
  if ( v80 )
    *(_QWORD *)(*(_QWORD *)(a1 + 80) + 40LL) = KeGetCurrentThread();
  else
    *(_QWORD *)(*(_QWORD *)(a1 + 80) + 40LL) = *(_QWORD *)(a1 + 80) | 3LL;
  *(_DWORD *)(*(_QWORD *)(a1 + 80) + 48LL) = Length;
  v20 = FileObject;
  *(_QWORD *)(*(_QWORD *)(a1 + 80) + 56LL) = FileObject;
LABEL_23:
  if ( (unsigned int)(v13 - 4) > 1 )
  {
    v22 = 0;
    LOBYTE(v12) = 0;
    LOBYTE(v79) = 0;
    v61 = 0;
    Status = 0;
    v73 = Length;
    if ( !FileOffset.HighPart )
    {
      if ( (_DWORD)v13 != 2 && (_DWORD)v13 != 9 )
      {
        if ( (unsigned int)(v13 - 6) > 2 )
        {
          if ( (_DWORD)v13 != 3 )
            KeBugCheckEx(0x23u, 0x1806A8u, v13, BugCheckParameter3, 0);
          Status = -1073741811;
          v24 = (char *)BugCheckParameter3;
          goto LABEL_45;
        }
        v25 = (_DWORD)v13 == 8;
        v24 = (char *)BugCheckParameter3;
        if ( v25 )
          v26 = *(_DWORD *)(BugCheckParameter3 + 440);
        else
          v26 = *(_DWORD *)(BugCheckParameter3 + 24);
        if ( ByteOffset.LowPart >= v26 )
        {
          a2->IoStatus.Information = 0;
          Status = 0;
LABEL_45:
          v27 = FileObject;
LABEL_46:
          if ( a2 )
          {
            if ( v22 )
            {
              if ( !(_BYTE)v12 )
                Status = FatFsdPostRequest((PVOID)a1, a2);
            }
            else
            {
              v28 = v80;
              if ( v74 && !v80 )
              {
                Information = 0;
                if ( (Status & 0xC0000000) != 0xC0000000 )
                  Information = a2->IoStatus.Information;
                v27->CurrentByteOffset.LowPart = ByteOffset.LowPart + Information;
                v28 = v80;
              }
              if ( Status >= 0 && !v28 )
                v27->Flags |= 0x80000u;
            }
          }
          if ( v61 && a2 )
          {
            if ( v80 )
              v48 = (struct _ERESOURCE *)*((_QWORD *)v24 + 2);
            else
              v48 = (struct _ERESOURCE *)*((_QWORD *)v24 + 1);
            ExReleaseResourceLite(v48);
          }
          if ( v22 )
            return (unsigned int)Status;
          if ( (*(_DWORD *)(a1 + 68) & 0x100) != 0 )
          {
            v49 = *(struct _MDL **)(*(_QWORD *)(a1 + 80) + 16LL);
            if ( v49 )
              IoFreeMdl(v49);
            *(_DWORD *)(a1 + 68) &= ~0x100u;
            *(_QWORD *)(a1 + 80) = 0;
          }
LABEL_159:
          FatCompleteRequest_Real((PVOID)a1, a2);
          return (unsigned int)Status;
        }
        if ( (int)Length + ByteOffset.LowPart > v26 )
        {
          LODWORD(Length) = v26 - ByteOffset.LowPart;
          v69 = v26 - ByteOffset.LowPart;
        }
        *(_DWORD *)(a1 + 68) |= 0x4000u;
        LODWORD(BugCheckParameter4) = Length;
        Status = 259;
        if ( (unsigned int)FatNonCachedIo(a1, (int)a2, (int)v24, ByteOffset.LowPart, BugCheckParameter4, Length, 0) != 259 )
        {
          Status = a2->IoStatus.Status;
          if ( Status < 0 )
          {
            *(_DWORD *)(a1 + 72) = Status;
            v30 = FsRtlNormalizeNtstatus(Status, -1073741591);
            ExRaiseStatus(v30);
          }
          goto LABEL_44;
        }
        goto LABEL_43;
      }
      if ( !v21 && v63 && v20->SectionObjectPointer->DataSectionObject )
      {
        IoStatus = 0;
        v24 = (char *)BugCheckParameter3;
        if ( !(unsigned __int8)FatAcquireExclusiveFcb(a1, BugCheckParameter3) )
        {
LABEL_62:
          v22 = 1;
          goto LABEL_44;
        }
        ExAcquireResourceExclusiveLite(*((PERESOURCE *)v24 + 2), 1u);
        CcFlushCache(FileObject->SectionObjectPointer, &FileOffset, Length, &IoStatus);
        ExReleaseResourceLite(*((PERESOURCE *)v24 + 2));
        ExReleaseResourceLite(*((PERESOURCE *)v24 + 1));
        if ( IoStatus.Status < 0 )
          goto LABEL_44;
        ExAcquireResourceExclusiveLite(*((PERESOURCE *)v24 + 2), 1u);
        ExReleaseResourceLite(*((PERESOURCE *)v24 + 2));
        v21 = v80;
      }
      else
      {
        v24 = (char *)BugCheckParameter3;
      }
      if ( v21 )
      {
        if ( !ExAcquireResourceSharedLite(*((PERESOURCE *)v24 + 2), 1u) )
          goto LABEL_62;
        if ( !v66 )
        {
          v31 = *((_QWORD *)v24 + 2);
LABEL_74:
          *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL) = v31;
        }
      }
      else
      {
        if ( !v66 && v63 )
        {
          if ( !(unsigned __int8)FatAcquireSharedFcbWaitForEx(a1, v24, v12, 0) )
            goto LABEL_62;
          v31 = *((_QWORD *)v24 + 1);
          goto LABEL_74;
        }
        if ( !(unsigned __int8)FatAcquireSharedFcb(a1, v24, v12, 0) )
          goto LABEL_62;
      }
      v61 = 1;
      FatVerifyFcb(a1, v24);
      if ( !v80 )
      {
        Status = FsRtlCheckOplock((POPLOCK)v24 + 11, a2, (PVOID)a1, FatOplockComplete, FatPrePostIrp);
        if ( Status )
        {
          LOBYTE(v12) = 1;
          v22 = 1;
          goto LABEL_45;
        }
        if ( *((_DWORD *)v24 + 49) == 1 && *(_WORD *)v24 == 1282 && FsRtlOplockIsFastIoPossible((POPLOCK)v24 + 11) )
          v32 = v24[336]
             || *(_DWORD *)(*((_QWORD *)v24 + 15) + 24LL)
             || (*(_DWORD *)(*((_QWORD *)v24 + 23) + 200LL) & 0x4000) != 0
             || (*((_DWORD *)v24 + 48) & 0x8000) != 0
              ? 2
              : 1;
        else
          v32 = 0;
        v24[5] = v32;
        if ( !FsRtlCheckLockForReadAccess((PFILE_LOCK)(v24 + 320), a2) )
        {
          Status = -1073741740;
          goto LABEL_44;
        }
      }
      v33 = *((_DWORD *)v24 + 8);
      v70 = v33;
      if ( ByteOffset.LowPart >= v33 )
      {
        Status = -1073741807;
        goto LABEL_44;
      }
      v34 = *((_DWORD *)v24 + 10);
      if ( (unsigned int)Length > v33 - ByteOffset.LowPart )
      {
        v73 = v33 - ByteOffset.LowPart;
        v75 = v33 - ByteOffset.LowPart;
        LODWORD(Length) = v33 - ByteOffset.LowPart;
        v69 = v33 - ByteOffset.LowPart;
        if ( !v63 )
          goto LABEL_120;
        if ( !v66 )
          *(_DWORD *)(*(_QWORD *)(a1 + 80) + 48LL) = v33 - ByteOffset.LowPart;
      }
      if ( v63 )
      {
        v70 = 0;
        LODWORD(v67) = *(unsigned __int16 *)(v67 + 288);
        v35 = *((_DWORD *)v24 + 70);
        if ( v34 >= v35 )
          v35 = v34;
        v64 = v35;
        v72 = (int)IoGetFsZeroingOffset(a2, &v70) >= 0;
        v36 = (unsigned int)(Length + ByteOffset.LowPart);
        v37 = v64;
        if ( (unsigned int)v36 > v64 )
        {
          v38 = (char *)FatMapUserBuffer(v36, (__int64)a2);
          v37 = v64;
          if ( ByteOffset.LowPart >= v64 )
          {
            memset(v38, 0, (unsigned int)Length);
            a2->IoStatus.Information = (unsigned int)Length;
            if ( v72 )
              IoSetFsZeroingOffset(a2, 0);
            Status = 0;
            goto LABEL_44;
          }
          v39 = -(int)v67 & (v64 - ByteOffset.LowPart + v67 - 1);
          if ( (unsigned int)Length > v39 )
          {
            memset(&v38[v39], 0, (unsigned int)Length - v39);
            v37 = v64;
          }
        }
        v40 = v37 - ByteOffset.LowPart;
        if ( v40 < (unsigned int)Length )
          LODWORD(Length) = v40;
        v69 = Length;
        if ( v72 )
          IoSetFsZeroingOffset(a2, (unsigned int)Length);
        if ( (((_DWORD)v67 - 1) & ByteOffset.LowPart) != 0
          || (~((_DWORD)v67 - 1) & (unsigned int)(Length + v67 - 1)) > CurrentStackLocation->Parameters.Read.Length )
        {
          if ( !v66 )
            goto LABEL_62;
          FatNonCachedNonAlignedRead(a1, (int)a2, Length);
        }
        else
        {
          LODWORD(BugCheckParameter4) = ~(v67 - 1) & (Length + v67 - 1);
          Status = 259;
          if ( (unsigned int)FatNonCachedIo(
                               a1,
                               (int)a2,
                               (int)v24,
                               ByteOffset.LowPart,
                               BugCheckParameter4,
                               Length,
                               *(_BYTE *)(a1 + 70) & 2) == 259 )
          {
LABEL_43:
            *(_QWORD *)(a1 + 80) = 0;
            a2 = 0;
LABEL_44:
            LOBYTE(v12) = v79;
            goto LABEL_45;
          }
        }
        Status = a2->IoStatus.Status;
        if ( Status < 0 )
        {
          *(_DWORD *)(a1 + 72) = Status;
          v41 = FsRtlNormalizeNtstatus(Status, -1073741591);
          ExRaiseStatus(v41);
        }
        a2->IoStatus.Information = v73;
        goto LABEL_44;
      }
LABEL_120:
      v42 = (int)FileObject;
      if ( !FileObject->PrivateCacheMap )
      {
        v43 = (unsigned int *)(v24 + 24);
        if ( *((_QWORD *)v24 + 3) == -1 )
        {
          FatLookupFileAllocationSize(a1, v24);
          v43 = (unsigned int *)(v24 + 24);
          v42 = (int)FileObject;
        }
        if ( v70 > *v43 )
        {
          FatPopUpFileCorrupt(a1, v24);
          *(_DWORD *)(a1 + 72) = -1073741566;
          ExRaiseStatus(-1073741566);
        }
        FatInitializeCacheMap(v42, (int)v43, 0, (int)&qword_140017D90, v24);
        CcSetReadAheadGranularity(FileObject, 0x10000u);
      }
      if ( (*(_BYTE *)(a1 + 65) & 2) != 0 )
      {
        v47 = Length;
        v27 = FileObject;
        CcMdlRead(FileObject, &FileOffset, v47, &a2->MdlAddress, &a2->IoStatus);
        Status = a2->IoStatus.Status;
        LOBYTE(v12) = v79;
      }
      else
      {
        v44 = FatMapUserBuffer((__int64)&a2->IoStatus, (__int64)a2);
        LOBYTE(v45) = v65;
        v46 = (unsigned int)Length;
        v27 = FileObject;
        if ( (unsigned __int8)CcCopyReadEx(
                                FileObject,
                                &FileOffset,
                                v46,
                                v45,
                                v44,
                                &a2->IoStatus,
                                a2->Tail.Overlay.Thread) )
          Status = a2->IoStatus.Status;
        else
          v22 = 1;
        LOBYTE(v12) = v79;
      }
      goto LABEL_46;
    }
LABEL_158:
    a2->IoStatus.Information = 0;
    Status = -1073741807;
    goto LABEL_159;
  }
  v50 = FileOffset;
  v25 = (_DWORD)v13 == 4;
  v51 = v67;
  if ( v25 )
  {
    v52 = v79;
    if ( (*(_DWORD *)(v79 + 4) & 0x50000) == 0 )
      FatQuickVerifyVcb(a1, v67);
    if ( (*(_DWORD *)(v52 + 4) & 0x40000) != 0 )
      *(_DWORD *)(a1 + 68) |= 0x1000u;
    v53 = *(_DWORD *)(v52 + 4);
    if ( (v53 & 0x100) == 0 )
    {
      ExAcquireResourceExclusiveLite((PERESOURCE)(v51 + 520), 1u);
      if ( (*(_DWORD *)(v51 + 200) & 1) == 0 )
        FatFlushVolume(a1, v51, 1);
      ExReleaseResourceLite((PERESOURCE)(v51 + 520));
      *(_DWORD *)(v52 + 4) |= 0x100u;
      v53 = *(_DWORD *)(v52 + 4);
    }
    if ( (v53 & 0x2000) == 0 )
    {
      v54 = *(unsigned __int16 *)(v51 + 298);
      if ( !*(_WORD *)(v51 + 298) )
        v54 = *(_DWORD *)(v51 + 312);
      v55 = v54 * (unsigned __int64)*(unsigned __int16 *)(v51 + 288);
      if ( v50.QuadPart >= v55 )
        goto LABEL_158;
      if ( Length > v55 - v50.QuadPart )
      {
        LODWORD(Length) = v55 - v50.LowPart;
        if ( !v5 )
          *(_DWORD *)(*(_QWORD *)(a1 + 80) + 48LL) = Length;
      }
    }
    FatLockUserBuffer(a1, a2, IoWriteAccess, Length);
  }
  else
  {
    v56 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
    ++*(_DWORD *)(v56 + *(_QWORD *)(v67 + 1024) + 40);
  }
  FatSingleAsync(a1, v51, v50.LowPart, Length, (__int64)a2);
  if ( FatDiskAccountingEnabled )
  {
    ThreadProcess = PsGetThreadProcess(KeGetCurrentThread());
    PsUpdateDiskCounters(ThreadProcess, (unsigned int)Length, 0, 1, 0, 0);
  }
  if ( v5 )
  {
    FatWaitSync(a1);
    v58 = a2->IoStatus.Status;
    if ( v58 < 0 )
    {
      *(_DWORD *)(a1 + 72) = v58;
      v59 = FsRtlNormalizeNtstatus(v58, -1073741591);
      ExRaiseStatus(v59);
    }
    if ( v74 && !v80 )
      FileObject->CurrentByteOffset.QuadPart = v50.QuadPart + a2->IoStatus.Information;
    FatCompleteRequest_Real((PVOID)a1, a2);
    return (unsigned int)v58;
  }
  else
  {
    *(_QWORD *)(a1 + 80) = 0;
    FatDeleteIrpContext_Real((PVOID)a1);
    return 259;
  }
}

```

## disassembly

```asm
0x14004573c  mov     rax, rsp
0x14004573f  mov     [rax+10h], rdx
0x140045743  mov     [rax+8], rcx
0x140045747  push    rbx
0x140045748  push    rsi
0x140045749  push    rdi
0x14004574a  push    r12
0x14004574c  push    r13
0x14004574e  push    r14
0x140045750  push    r15
0x140045752  sub     rsp, 120h
0x140045759  mov     r14, rdx
0x14004575c  mov     rsi, rcx
0x14004575f  xor     r13d, r13d
0x140045762  mov     [rsp+158h+var_F8], r13
0x140045767  mov     [rsp+158h+BugCheckParameter3], r13
0x14004576c  mov     [rax+18h], r13
0x140045770  xor     edx, edx; Val
0x140045772  lea     r8d, [r13+70h]; Size
0x140045776  lea     rcx, [rax-0A8h]; void *
0x14004577d  call    memset
0x140045782  mov     qword ptr [rsp+158h+FileOffset], r13
0x140045787  mov     rdx, [r14+0B8h]
0x14004578e  mov     [rsp+158h+var_C8], rdx
0x140045796  mov     rcx, [rdx+30h]
0x14004579a  mov     [rsp+158h+FileObject], rcx
0x14004579f  mov     r12d, [rsi+44h]
0x1400457a3  and     r12d, 2
0x1400457a7  mov     [rsp+158h+var_100], r12d
0x1400457ac  setnz   [rsp+158h+var_104]
0x1400457b1  mov     edi, [r14+10h]
0x1400457b5  mov     al, dil
0x1400457b8  shr     al, 1
0x1400457ba  and     al, 1
0x1400457bc  mov     [rsp+158h+arg_18], al
0x1400457c3  mov     eax, [rcx+50h]
0x1400457c6  mov     rbx, [rdx+18h]
0x1400457ca  mov     qword ptr [rsp+158h+FileOffset], rbx
0x1400457cf  mov     r15d, [rdx+8]
0x1400457d3  test    r15d, r15d
0x1400457d6  jnz     short loc_1400457F1
0x1400457d8  mov     [r14+38h], r13
0x1400457dc  xor     r8d, r8d
0x1400457df  mov     rdx, r14; Irp
0x1400457e2  mov     rcx, rsi; Entry
0x1400457e5  call    FatCompleteRequest_Real
0x1400457ea  xor     eax, eax
0x1400457ec  jmp     loc_1400463DC
0x1400457f1  and     eax, 2
0x1400457f4  mov     [rsp+158h+var_D0], eax
0x1400457fb  lea     r9, [rsp+158h+arg_10]
0x140045803  lea     r8, [rsp+158h+BugCheckParameter3]
0x140045808  lea     rdx, [rsp+158h+var_F8]
0x14004580d  call    FatDecodeFileObject
0x140045812  movsxd  r13, eax
0x140045815  cmp     r13d, 4
0x140045819  jnz     short loc_140045820
0x14004581b  mov     dil, 1
0x14004581e  jmp     short loc_140045824
0x140045820  and     dil, 1
0x140045824  mov     [rsp+158h+var_108], edi
0x140045828  xor     r9d, r9d
0x14004582b  cmp     [rsp+158h+arg_18], r9b
0x140045833  jz      short loc_140045893
0x140045835  mov     al, gs:184h
0x14004583d  movzx   eax, al
0x140045840  xor     edx, edx
0x140045842  div     cs:dword_140017D48
0x140045848  mov     ecx, edx
0x14004584a  shl     rcx, 7
0x14004584e  mov     rdx, [rsp+158h+var_F8]
0x140045853  mov     rdx, [rdx+400h]
0x14004585a  cmp     r13d, 2
0x14004585e  jnz     short loc_14004586B
0x140045860  inc     dword ptr [rcx+rdx+8]
0x140045864  add     [rcx+rdx+0Ch], r15d
0x140045869  jmp     short loc_14004587D
0x14004586b  lea     eax, [r13-5]
0x14004586f  cmp     eax, 1
0x140045872  ja      short loc_14004587D
0x140045874  inc     dword ptr [rcx+rdx+20h]
0x140045878  add     [rcx+rdx+24h], r15d
0x14004587d  mov     eax, [rsi+44h]
0x140045880  cmp     r13d, 2
0x140045884  jnz     short loc_14004588C
0x140045886  bts     eax, 0Ah
0x14004588a  jmp     short loc_140045890
0x14004588c  btr     eax, 0Ah
0x140045890  mov     [rsi+44h], eax
0x140045893  test    dil, dil
0x140045896  jz      short loc_140045915
0x140045898  mov     rax, [rsi+50h]
0x14004589c  test    rax, rax
0x14004589f  jnz     short loc_1400458DF
0x1400458a1  test    r12d, r12d
0x1400458a4  jnz     short loc_1400458C6
0x1400458a6  lea     edx, [rax+70h]; NumberOfBytes
0x1400458a9  mov     ecx, 210h; PoolType
0x1400458ae  mov     r8d, 58746146h; Tag
0x1400458b4  call    cs:__imp_ExAllocatePoolWithTag
0x1400458bb  nop     dword ptr [rax+rax+00h]
0x1400458c0  mov     [rsi+50h], rax
0x1400458c4  jmp     short loc_1400458DF
0x1400458c6  lea     rax, [rsp+158h+var_A8]
0x1400458ce  mov     [rsi+50h], rax
0x1400458d2  bts     dword ptr [rsi+44h], 8
0x1400458d7  lea     rax, [rsp+158h+var_A8]
0x1400458df  xor     edx, edx; Val
0x1400458e1  lea     r8d, [rdx+70h]; Size
0x1400458e5  mov     rcx, rax; void *
0x1400458e8  call    memset
0x1400458ed  xor     r9d, r9d
0x1400458f0  test    r12d, r12d
0x1400458f3  jz      loc_14004599B
0x1400458f9  mov     rcx, [rsi+50h]
0x1400458fd  add     rcx, 18h; Event
0x140045901  xor     r8d, r8d; State
0x140045904  xor     edx, edx; Type
0x140045906  call    cs:__imp_KeInitializeEvent
0x14004590d  nop     dword ptr [rax+rax+00h]
0x140045912  xor     r9d, r9d
0x140045915  mov     rcx, [rsp+158h+FileObject]
0x14004591a  mov     dl, [rsp+158h+arg_18]
0x140045921  lea     eax, [r13-4]
0x140045925  cmp     eax, 1
0x140045928  jbe     loc_1400461C3
0x14004592e  mov     r12b, r9b
0x140045931  mov     [rsp+158h+var_118], r9b
0x140045936  mov     r8b, r9b
0x140045939  mov     byte ptr [rsp+158h+arg_10], r9b
0x140045941  mov     [rsp+158h+var_117], r9b
0x140045946  mov     edi, r9d
0x140045949  mov     [rsp+158h+var_114], r9d
0x14004594e  mov     [rsp+158h+var_D4], r15d
0x140045956  cmp     dword ptr [rsp+158h+FileOffset+4], r9d
0x14004595b  jnz     loc_14004628E
0x140045961  cmp     r13d, 2
0x140045965  jz      loc_140045B34
0x14004596b  cmp     r13d, 9
0x14004596f  jz      loc_140045B34
0x140045975  lea     eax, [r13-6]
0x140045979  cmp     eax, 2
0x14004597c  jbe     loc_140045A05
0x140045982  cmp     r13d, 3
0x140045986  jnz     short loc_1400459E2
0x140045988  mov     edi, 0C000000Dh
0x14004598d  mov     [rsp+158h+var_114], edi
0x140045991  mov     r13, [rsp+158h+BugCheckParameter3]
0x140045996  jmp     loc_140045A92
0x14004599b  mov     dl, [rsp+158h+arg_18]
0x1400459a2  test    dl, dl
0x1400459a4  jz      short loc_1400459B9
0x1400459a6  mov     rcx, gs:188h
0x1400459af  mov     rax, [rsi+50h]
0x1400459b3  mov     [rax+28h], rcx
0x1400459b7  jmp     short loc_1400459C8
0x1400459b9  mov     rcx, [rsi+50h]
0x1400459bd  mov     rax, rcx
0x1400459c0  or      rax, 3
0x1400459c4  mov     [rcx+28h], rax
0x1400459c8  mov     rax, [rsi+50h]
0x1400459cc  mov     [rax+30h], r15d
0x1400459d0  mov     rax, [rsi+50h]
0x1400459d4  mov     rcx, [rsp+158h+FileObject]
0x1400459d9  mov     [rax+38h], rcx
0x1400459dd  jmp     loc_140045921
0x1400459e2  mov     r8, r13; BugCheckParameter2
0x1400459e5  mov     [rsp+158h+BugCheckParameter4], r9; BugCheckParameter4
0x1400459ea  mov     r9, [rsp+158h+BugCheckParameter3]; BugCheckParameter3
0x1400459ef  mov     edx, 1806A8h; BugCheckParameter1
0x1400459f4  mov     ecx, 23h ; '#'; BugCheckCode
0x1400459f9  call    cs:__imp_KeBugCheckEx
0x140045a05  cmp     r13d, 8
0x140045a09  mov     r13, [rsp+158h+BugCheckParameter3]
0x140045a0e  jnz     short loc_140045A29
0x140045a10  mov     ecx, [r13+1B8h]
0x140045a17  cmp     ebx, ecx
0x140045a19  jb      short loc_140045A2F
0x140045a1b  mov     [r14+38h], r9
0x140045a1f  mov     edi, r9d
0x140045a22  mov     [rsp+158h+var_114], r9d
0x140045a27  jmp     short loc_140045A92
0x140045a29  mov     ecx, [r13+18h]
0x140045a2d  jmp     short loc_140045A17
0x140045a2f  lea     eax, [r15+rbx]
0x140045a33  cmp     eax, ecx
0x140045a35  jbe     short loc_140045A42
0x140045a37  mov     r15d, ecx
0x140045a3a  sub     r15d, ebx
0x140045a3d  mov     [rsp+158h+var_E8], r15d
0x140045a42  bts     dword ptr [rsi+44h], 0Eh
0x140045a47  mov     dword ptr [rsp+158h+var_128], r9d; char
0x140045a4c  mov     [rsp+158h+var_130], r15d; int
0x140045a51  mov     dword ptr [rsp+158h+BugCheckParameter4], r15d; NumberOfBytes
0x140045a56  mov     r9d, ebx; int
0x140045a59  mov     r8, r13; int
0x140045a5c  mov     rdx, r14; int
0x140045a5f  mov     rcx, rsi; int
0x140045a62  call    FatNonCachedIo
0x140045a67  mov     edi, 103h
0x140045a6c  xor     r9d, r9d
0x140045a6f  cmp     eax, edi
0x140045a71  jnz     loc_140045B00
0x140045a77  mov     [rsi+50h], r9
0x140045a7b  mov     r14, r9
0x140045a7e  mov     [rsp+158h+arg_8], r9
0x140045a86  mov     [rsp+158h+var_114], edi
0x140045a8a  mov     r8b, byte ptr [rsp+158h+arg_10]
0x140045a92  mov     r15, [rsp+158h+FileObject]
0x140045a97  test    r14, r14
0x140045a9a  jz      loc_140046154
0x140045aa0  test    r12b, r12b
0x140045aa3  jnz     loc_14004613B
0x140045aa9  mov     al, [rsp+158h+arg_18]
0x140045ab0  cmp     [rsp+158h+var_D0], r9d
0x140045ab8  jz      short loc_140045ADF
0x140045aba  test    al, al
0x140045abc  jnz     short loc_140045ADF
0x140045abe  mov     eax, edi
0x140045ac0  mov     ecx, 0C0000000h
0x140045ac5  and     eax, ecx
0x140045ac7  cmp     eax, ecx
0x140045ac9  mov     eax, r9d
0x140045acc  jz      short loc_140045AD2
0x140045ace  mov     eax, [r14+38h]
0x140045ad2  add     eax, ebx
0x140045ad4  mov     [r15+68h], eax
0x140045ad8  mov     al, [rsp+158h+arg_18]
0x140045adf  test    edi, edi
0x140045ae1  js      loc_140046154
0x140045ae7  test    al, al
0x140045ae9  jnz     loc_140046154
0x140045aef  mov     eax, [r15+50h]
0x140045af3  bts     eax, 13h
0x140045af7  mov     [r15+50h], eax
0x140045afb  jmp     loc_140046154
0x140045b00  mov     edi, [r14+30h]
0x140045b04  mov     [rsp+158h+var_114], edi
0x140045b08  test    edi, edi
0x140045b0a  jns     loc_140045A8A
0x140045b10  mov     [rsi+48h], edi
0x140045b13  mov     edx, 0C00000E9h; GenericException
0x140045b18  mov     ecx, edi; Exception
0x140045b1a  call    cs:__imp_FsRtlNormalizeNtstatus
0x140045b21  nop     dword ptr [rax+rax+00h]
0x140045b26  mov     ecx, eax; Status
0x140045b28  call    cs:__imp_ExRaiseStatus
0x140045b34  test    dl, dl
0x140045b36  jnz     loc_140045C19
0x140045b3c  cmp     byte ptr [rsp+158h+var_108], r9b
0x140045b41  jz      loc_140045C19
0x140045b47  mov     rax, [rcx+28h]
0x140045b4b  cmp     [rax], r9
0x140045b4e  jz      loc_140045C19
0x140045b54  xorps   xmm0, xmm0
0x140045b57  movups  xmmword ptr [rsp+158h+IoStatus], xmm0
0x140045b5f  mov     r13, [rsp+158h+BugCheckParameter3]
0x140045b64  mov     rdx, r13
0x140045b67  mov     rcx, rsi
0x140045b6a  call    FatAcquireExclusiveFcb
0x140045b6f  xor     r9d, r9d
0x140045b72  test    al, al
0x140045b74  jnz     short loc_140045B83
0x140045b76  mov     r12b, 1
0x140045b79  mov     [rsp+158h+var_118], r12b
0x140045b7e  jmp     loc_140045A8A
0x140045b83  mov     dl, 1; Wait
0x140045b85  mov     rcx, [r13+10h]; Resource
0x140045b89  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140045b90  nop     dword ptr [rax+rax+00h]
0x140045b95  lea     r9, [rsp+158h+IoStatus]; IoStatus
0x140045b9d  mov     r8d, r15d; Length
0x140045ba0  lea     rdx, [rsp+158h+FileOffset]; FileOffset
0x140045ba5  mov     rax, [rsp+158h+FileObject]
0x140045baa  mov     rcx, [rax+28h]; SectionObjectPointer
0x140045bae  call    cs:__imp_CcFlushCache
0x140045bb5  nop     dword ptr [rax+rax+00h]
0x140045bba  mov     rcx, [r13+10h]; Resource
0x140045bbe  call    cs:__imp_ExReleaseResourceLite
0x140045bc5  nop     dword ptr [rax+rax+00h]
0x140045bca  mov     rcx, [r13+8]; Resource
0x140045bce  call    cs:__imp_ExReleaseResourceLite
0x140045bd5  nop     dword ptr [rax+rax+00h]
0x140045bda  xor     r9d, r9d
0x140045bdd  cmp     dword ptr [rsp+158h+IoStatus], r9d
0x140045be5  jl      loc_140045A8A
0x140045beb  mov     dl, 1; Wait
0x140045bed  mov     rcx, [r13+10h]; Resource
0x140045bf1  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140045bf8  nop     dword ptr [rax+rax+00h]
0x140045bfd  mov     rcx, [r13+10h]; Resource
0x140045c01  call    cs:__imp_ExReleaseResourceLite
0x140045c08  nop     dword ptr [rax+rax+00h]
0x140045c0d  mov     dl, [rsp+158h+arg_18]
0x140045c14  xor     r9d, r9d
0x140045c17  jmp     short loc_140045C1E
0x140045c19  mov     r13, [rsp+158h+BugCheckParameter3]
0x140045c1e  test    dl, dl
0x140045c20  jz      short loc_140045C4C
0x140045c22  mov     dl, 1; Wait
  ... truncated ...
```
