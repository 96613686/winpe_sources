# FatQueryDirectory

- ea: `0x14002ed1c`
- end: `0x1400302a1`
- name: `FatQueryDirectory`
- size: `5509`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002e9ac`

## callees

- `0x140007408`
- `0x14000c230`
- `0x14000c380`
- `0x14000c680`
- `0x14000cba0`
- `0x14002d4a8`
- `0x14002d5a8`
- `0x14002eab8`
- `0x14002ed1c`
- `0x140031938`
- `0x140031e8c`
- `0x140036394`
- `0x140036ffc`
- `0x140038eb4`
- `0x14003d880`
- `0x140044518`
- `0x140044df4`
- `0x1400465f4`
- `0x1400468c4`
- `0x1400486ec`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeStringToCountedOemString` at `0x14002f196`
- `ntoskrnl!RtlUpcaseUnicodeStringToCountedOemString` at `0x14002f196`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002f169`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002f169`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x14002f2be`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x14002f2be`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14002ef81`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14002f35e`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14002ef81`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14002f35e`
- `ntoskrnl!RtlFreeOemString` at `0x14002f075`
- `ntoskrnl!RtlFreeOemString` at `0x14002f2db`
- `ntoskrnl!RtlFreeOemString` at `0x14002f338`
- `ntoskrnl!RtlFreeOemString` at `0x14002f075`
- `ntoskrnl!RtlFreeOemString` at `0x14002f2db`
- `ntoskrnl!RtlFreeOemString` at `0x14002f338`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14002f129`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14002f129`
- `ntoskrnl!RtlxOemStringToUnicodeSize` at `0x14002f5c6`
- `ntoskrnl!RtlxOemStringToUnicodeSize` at `0x14002f5c6`
- `ntoskrnl!RtlOemToUnicodeN` at `0x14002f9a9`
- `ntoskrnl!RtlOemToUnicodeN` at `0x14002fb51`
- `ntoskrnl!RtlOemToUnicodeN` at `0x14002f9a9`
- `ntoskrnl!RtlOemToUnicodeN` at `0x14002fb51`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030200`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ceda`
- `ntoskrnl!ExReleaseResourceLite` at `0x140030200`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ceda`
- `ntoskrnl!CcUnpinData` at `0x140030219`
- `ntoskrnl!CcUnpinData` at `0x14005cef2`
- `ntoskrnl!CcUnpinData` at `0x140030219`
- `ntoskrnl!CcUnpinData` at `0x14005cef2`
- `ntoskrnl!KeBugCheckEx` at `0x14002f67f`
- `ntoskrnl!KeBugCheckEx` at `0x14002fae3`
- `ntoskrnl!KeBugCheckEx` at `0x14002f67f`
- `ntoskrnl!KeBugCheckEx` at `0x14002fae3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f04d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f04d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002f1e8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002f1e8`

## pseudocode

```c
__int64 __fastcall FatQueryDirectory(PVOID Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  ULONG EaLength; // r13d
  UNICODE_STRING *FileName; // rbx
  UCHAR Flags; // si
  __int64 v8; // r8
  __int64 v9; // r9
  char v10; // r15
  char v11; // r12
  __int64 v12; // rsi
  char v13; // dl
  NTSTATUS v14; // r14d
  __int64 v16; // rcx
  __int64 v17; // r15
  void *v18; // rcx
  unsigned int v19; // eax
  USHORT Length; // ax
  PWSTR Buffer; // rdx
  char v22; // r13
  unsigned int i; // edx
  NTSTATUS v24; // eax
  unsigned __int64 v25; // rcx
  SIZE_T v26; // r12
  char *PoolWithTag; // rax
  char *v28; // r15
  unsigned __int64 v29; // rcx
  unsigned int j; // edx
  unsigned __int64 v31; // rbx
  int v32; // r12d
  __int64 v33; // rcx
  __int64 v34; // r8
  IRP *v35; // r15
  bool v36; // zf
  PVOID v37; // rbx
  bool IsPfile; // al
  unsigned int v39; // r13d
  ULONG v40; // r15d
  __int64 v41; // rcx
  __int64 v42; // r14
  char *v43; // r12
  __int64 v44; // rcx
  char *v45; // rcx
  __int64 v46; // r12
  __int64 v47; // rcx
  char v48; // cl
  __int64 v49; // rdx
  unsigned __int64 v50; // rax
  int v51; // eax
  int v52; // r8d
  char *v53; // r13
  ULONG v54; // edx
  ULONG v55; // r15d
  __int64 v56; // rcx
  __int64 v57; // r12
  __int64 v58; // rcx
  __int64 v59; // rcx
  char *v60; // rdx
  __int64 v61; // rcx
  char v62; // cl
  __int64 v63; // rdx
  unsigned __int64 v64; // rax
  int v65; // eax
  int v66; // r8d
  ULONG v67; // r13d
  size_t v68; // r8
  __int64 v69; // r9
  __int64 v70; // rax
  __int64 v71; // r8
  unsigned __int64 v72; // r8
  __int64 v73; // rdx
  __int64 v74; // rax
  __int64 *v75; // rdx
  __int64 v76; // r8
  __int64 v77; // rax
  __int64 v78; // r9
  __int64 v79; // rax
  __int64 v80; // r8
  unsigned __int64 v81; // r8
  __int64 v82; // rdx
  __int64 v83; // rax
  __int64 *v84; // rdx
  __int64 v85; // r8
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 v90; // r9
  char v91; // [rsp+60h] [rbp-1C8h]
  bool v92; // [rsp+61h] [rbp-1C7h]
  char v93; // [rsp+63h] [rbp-1C5h]
  __int64 v94; // [rsp+68h] [rbp-1C0h] BYREF
  int v95; // [rsp+70h] [rbp-1B8h]
  int v96; // [rsp+74h] [rbp-1B4h]
  PVOID Context1; // [rsp+78h] [rbp-1B0h]
  unsigned int v98; // [rsp+80h] [rbp-1A8h] BYREF
  int v99; // [rsp+84h] [rbp-1A4h]
  PVOID Context2; // [rsp+88h] [rbp-1A0h]
  int v101; // [rsp+90h] [rbp-198h]
  ULONG BytesInUnicodeString; // [rsp+94h] [rbp-194h] BYREF
  int v103[2]; // [rsp+98h] [rbp-190h] BYREF
  char v104; // [rsp+A0h] [rbp-188h]
  _BYTE v105[11]; // [rsp+A1h] [rbp-187h] BYREF
  unsigned int v106; // [rsp+ACh] [rbp-17Ch]
  int v107[2]; // [rsp+B0h] [rbp-178h] BYREF
  PVOID v108; // [rsp+B8h] [rbp-170h]
  unsigned __int16 v109[2]; // [rsp+C0h] [rbp-168h] BYREF
  unsigned __int16 v110; // [rsp+C4h] [rbp-164h] BYREF
  unsigned int v111; // [rsp+C8h] [rbp-160h]
  unsigned int v112; // [rsp+CCh] [rbp-15Ch]
  int v113; // [rsp+D0h] [rbp-158h] BYREF
  unsigned int v114; // [rsp+D4h] [rbp-154h]
  ULONG v115; // [rsp+D8h] [rbp-150h]
  struct _STRING DestinationString; // [rsp+E0h] [rbp-148h] BYREF
  PVOID Bcb; // [rsp+F0h] [rbp-138h] BYREF
  int v118[2]; // [rsp+F8h] [rbp-130h] BYREF
  void *Buf1[2]; // [rsp+100h] [rbp-128h] BYREF
  int v120; // [rsp+110h] [rbp-118h]
  _DWORD v121[3]; // [rsp+114h] [rbp-114h] BYREF
  __int64 v122; // [rsp+120h] [rbp-108h]
  ULONG v123; // [rsp+128h] [rbp-100h] BYREF
  unsigned int v124; // [rsp+12Ch] [rbp-FCh] BYREF
  int v125; // [rsp+130h] [rbp-F8h]
  __int64 *v126; // [rsp+138h] [rbp-F0h]
  PIRP v127; // [rsp+140h] [rbp-E8h]
  PVOID v128; // [rsp+148h] [rbp-E0h]
  void *Src[2]; // [rsp+150h] [rbp-D8h] BYREF
  int v130; // [rsp+160h] [rbp-C8h]
  char *v131; // [rsp+168h] [rbp-C0h]
  __int64 v132[2]; // [rsp+170h] [rbp-B8h] BYREF
  ANSI_STRING DbcsName; // [rsp+180h] [rbp-A8h] BYREF
  struct _STRING v134; // [rsp+190h] [rbp-98h] BYREF
  char v135; // [rsp+1A0h] [rbp-88h] BYREF
  char v136; // [rsp+1B0h] [rbp-78h] BYREF

  Context2 = Irp;
  Context1 = Entry;
  v128 = Entry;
  v127 = Irp;
  *(_QWORD *)v107 = 0;
  *(_QWORD *)v103 = 0;
  *(_QWORD *)v118 = 0;
  Bcb = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)v132 = 0;
  v113 = 0;
  v94 = 0;
  *(_OWORD *)Buf1 = 0;
  v98 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_DWORD *)&v105[7] = CurrentStackLocation->Parameters.Read.Length;
  *(_DWORD *)&v105[3] = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  EaLength = CurrentStackLocation->Parameters.Create.EaLength;
  FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
  Flags = CurrentStackLocation->Flags;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, v107, v103, v118) != 3
    || FileName && (FileName->Length & 1) != 0 )
  {
    FatCompleteRequest_Real(Entry, Irp, 3221225485LL, v9);
    return 3221225485LL;
  }
  v10 = Flags & 1;
  v11 = Flags & 4;
  v99 = 0;
  v92 = 0;
  v130 = *(_DWORD *)&v105[7];
  v122 = *(_QWORD *)&v105[3];
  v104 = Flags & 2;
  Bcb = 0;
  v93 = 1;
  v94 = 0;
  v96 = 12;
  WORD1(Buf1[0]) = 12;
  Buf1[1] = &v135;
  LODWORD(Src[0]) = 0x400000;
  Src[1] = &v136;
  v12 = *(_QWORD *)v118;
  if ( *(_QWORD *)(*(_QWORD *)v118 + 56LL) || (v13 = 1, (*(_DWORD *)(*(_QWORD *)v118 + 4LL) & 1) != 0) )
    v13 = 0;
  v91 = v13;
  v14 = 0;
  v95 = 0;
  v126 = (__int64 *)((char *)Context2 + 56);
  *((_QWORD *)Context2 + 7) = 0;
  v111 = 1 << *(_BYTE *)(*(_QWORD *)v107 + 378LL);
  v121[2] = v111;
  if ( v13 || v10 )
  {
    if ( !(unsigned __int8)FatAcquireExclusiveFcb(Context1, *(_QWORD *)v103) )
      return FatFsdPostRequest(Context1, Context2);
    if ( !v10 && *(_QWORD *)(v12 + 56) )
    {
      v91 = 0;
      ExConvertExclusiveToSharedLite(*(PERESOURCE *)(*(_QWORD *)v103 + 8LL));
    }
  }
  else if ( !(unsigned __int8)FatAcquireSharedFcb(Context1, *(_QWORD *)v103, v8, v9) )
  {
    return FatFsdPostRequest(Context1, Context2);
  }
  v101 = 0;
  BytesInUnicodeString = 0;
  FatLockUserBuffer((__int64)Context1, (IRP *)Context2, IoWriteAccess, *(ULONG *)&v105[7]);
  v108 = FatMapUserBuffer(v16, (__int64)Context2);
  FatVerifyFcb(Context1, *(_QWORD *)v103);
  if ( v11 )
  {
    v99 = EaLength + 32;
  }
  else if ( v10 )
  {
    v99 = 0;
    *(_DWORD *)(v12 + 24) = 0;
  }
  else
  {
    v99 = *(_DWORD *)(v12 + 24);
  }
  if ( !v91 && (!v10 || !FileName || !FileName->Length) )
  {
    v17 = *(_QWORD *)v103;
    goto LABEL_76;
  }
  if ( v10 )
  {
    v18 = *(void **)(v12 + 56);
    if ( v18 )
    {
      if ( (*(_DWORD *)(v12 + 4) & 8) != 0 )
      {
        ExFreePoolWithTag(v18, 0x6E746146u);
        *(_DWORD *)(v12 + 4) &= ~8u;
      }
      *(_QWORD *)(v12 + 56) = 0;
      *(_DWORD *)(v12 + 48) = 0;
    }
    if ( *(_QWORD *)(v12 + 40) )
    {
      if ( (*(_DWORD *)(v12 + 4) & 4) != 0 )
      {
        RtlFreeOemString((POEM_STRING)(v12 + 32));
        *(_DWORD *)(v12 + 4) &= ~4u;
      }
      *(_QWORD *)(v12 + 40) = 0;
      *(_DWORD *)(v12 + 32) = 0;
    }
    *(_BYTE *)(v12 + 8) = 0;
    *(_DWORD *)(v12 + 4) &= ~1u;
    v19 = *(_DWORD *)(v12 + 4) & 0xFFFFFFF7;
    *(_DWORD *)(v12 + 4) = v19;
    v19 &= ~2u;
    *(_DWORD *)(v12 + 4) = v19;
    *(_DWORD *)(v12 + 4) = v19 & 0xFFFFEFFF;
  }
  if ( !FileName
    || (Length = FileName->Length) == 0
    || (Buffer = FileName->Buffer) == 0
    || Length == 2 && *Buffer == 42
    || Length == 24
    && *(_QWORD *)Buffer == Fat8QMdot3QM
    && *((_QWORD *)Buffer + 1) == qword_1400172C8
    && *((_QWORD *)Buffer + 2) == qword_1400172D0 )
  {
    *(_BYTE *)(v12 + 8) = 1;
    *(_DWORD *)(v12 + 4) |= 1u;
LABEL_75:
    v17 = *(_QWORD *)v103;
    ExConvertExclusiveToSharedLite(*(PERESOURCE *)(*(_QWORD *)v103 + 8LL));
LABEL_76:
    v114 = 0;
    v31 = 0;
    v106 = 0;
    switch ( *(_DWORD *)&v105[3] )
    {
      case 1:
        v32 = 64;
        break;
      case 2:
        v32 = 68;
        break;
      case 3:
        v32 = 94;
        break;
      case 0xC:
        v32 = 12;
LABEL_90:
        v101 = v32;
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              v105[0] = 0;
              if ( v104 && (_DWORD)v31 )
                goto LABEL_245;
              if ( (*(_DWORD *)(*(_QWORD *)v107 + 200LL) & 0x400000) != 0 )
                v113 = 2;
              FatLocateDirent(
                (__int64)Context1,
                v17,
                v12,
                v99,
                &v113,
                (PVOID *)&v94,
                &Bcb,
                &v98,
                v105,
                (UNICODE_STRING *)Src,
                v132);
              if ( !v94 )
              {
                v35 = (IRP *)Context2;
                v36 = (_DWORD)v31 == 0;
                v37 = Context1;
                if ( v36 )
                {
                  v93 = 0;
                  v14 = v91 != 0 ? -1073741809 : -2147483642;
                  v95 = v14;
                }
                goto LABEL_246;
              }
              if ( (*(_DWORD *)(*(_QWORD *)v107 + 200LL) & 0x400000) == 0 )
                break;
              IsPfile = FatFileExtensionIsPfile((unsigned __int16 *)v132, 1u);
              v92 = IsPfile;
              if ( (v113 & 0x20) == 0 )
                break;
              v33 = v94;
              if ( (*(_BYTE *)(v94 + 12) & 1) == 0 || !IsPfile )
                break;
              v99 = v98 + 32;
            }
            LOBYTE(v34) = 1;
            Fat8dot3ToString(v33, v94, v34, Buf1);
            if ( (*(_DWORD *)(*(_QWORD *)v107 + 200LL) & 0x400000) == 0
              || LOWORD(Buf1[0]) != _EFS_SHORT
              || memcmp(Buf1[1], ::Buf1, LOWORD(Buf1[0])) )
            {
              break;
            }
            v99 = v98 + 32;
          }
          v39 = v130 - v31;
          v121[1] = v130 - v31;
          if ( !LOWORD(Src[0]) )
          {
            v40 = RtlxOemStringToUnicodeSize((PCOEM_STRING)Buf1) - 2;
            v115 = v40;
            if ( (_DWORD)v31 && (v40 + v32 > v39 || *(_DWORD *)&v105[7] < (unsigned int)v31) )
            {
              v14 = 0;
              v95 = 0;
              v37 = Context1;
              v35 = (IRP *)Context2;
              goto LABEL_246;
            }
            v41 = *v126;
            v42 = (unsigned int)(v32 + v31);
            *(_QWORD *)&DestinationString.Length = v42;
            v43 = (char *)v108;
            memset((char *)v108 + v41, 0, v42 - v41);
            v44 = (unsigned int)(*(_DWORD *)&v105[3] - 1);
            switch ( *(_DWORD *)&v105[3] )
            {
              case 1:
                goto LABEL_120;
              case 2:
              case 3:
                goto LABEL_119;
              case 0xC:
                v45 = (char *)v108;
                *(_DWORD *)((char *)v108 + v31 + 4) = v98;
                *(_DWORD *)&v45[v31 + 8] = v40;
                v46 = (unsigned int)v31;
                break;
              default:
                if ( (unsigned int)(*(_DWORD *)&v105[3] - 37) >= 2 )
                  KeBugCheckEx(0x23u, 0x90450u, *(int *)&v105[3], 0, 0);
LABEL_119:
                v131 = &v43[(unsigned int)v31];
                FatGetEaLength((int)Context1, v107[0]);
LABEL_120:
                v46 = (unsigned int)v31;
                v31 = (unsigned __int64)v108 + (unsigned int)v31;
                FatGetDirTimes(v44, v94, v31);
                *(_QWORD *)(v31 + 40) = *(unsigned int *)(v94 + 28);
                v47 = v94;
                if ( (*(_BYTE *)(v94 + 11) & 0x10) == 0 )
                {
                  if ( (*(_DWORD *)(*(_QWORD *)v107 + 200LL) & 0x400000) != 0 )
                  {
                    v48 = *(_BYTE *)(v94 + 12);
                    if ( (v48 & 1) != 0 && v92 )
                    {
                      if ( (v48 & 2) == 0 )
                      {
                        *(_QWORD *)(v31 + 40) -= *(unsigned int *)(*(_QWORD *)v107 + 372LL);
                        v49 = *(_QWORD *)(v31 + 40);
                        goto LABEL_126;
                      }
                      v125 = 0;
                      v124 = 0;
                      v110 = 0;
                      v52 = *(unsigned __int16 *)(v94 + 26);
                      v125 = v52;
                      if ( *(_BYTE *)(*(_QWORD *)v107 + 376LL) == 32 )
                      {
                        v52 += *(unsigned __int16 *)(v94 + 20) << 16;
                        v125 = v52;
                      }
                      FatGetEfsInfoFromHeaderOnDisk((_DWORD)Context1, v107[0], v52, (unsigned int)&v124, (__int64)&v110);
                      *(_QWORD *)(v31 + 40) -= v124;
                      v49 = *(_QWORD *)(v31 + 40);
                      if ( v110 > 0x7FFFu )
LABEL_126:
                        v50 = (*(_BYTE *)(v94 + 12) & 4 | ((unsigned __int64)*(unsigned __int8 *)(v94 + 12) >> 2) & 0x38) >> 2;
                      else
                        v50 = (unsigned __int8)(((v110 + 15) & 0xF0) - v110);
                      *(_QWORD *)(v31 + 40) = v49 - v50;
                    }
                  }
                  *(_QWORD *)(v31 + 48) = *(_DWORD *)(v94 + 28) + v111 - 1 - (*(_DWORD *)(v94 + 28) + v111 - 1) % v111;
                  v47 = v94;
                }
                v51 = *(unsigned __int8 *)(v47 + 11);
                if ( (_BYTE)v51 )
                {
                  *(_DWORD *)(v31 + 56) = v51;
                  if ( (*(_DWORD *)(*(_QWORD *)v107 + 200LL) & 0x400000) != 0
                    && (*(_BYTE *)(v94 + 12) & 1) != 0
                    && (v92 || (*(_BYTE *)(v94 + 11) & 0x10) != 0) )
                  {
                    *(_DWORD *)(v31 + 56) |= 0x4000u;
                    *(_DWORD *)(v31 + 56) &= ~0x80u;
                  }
                }
                else
                {
                  *(_DWORD *)(v31 + 56) = 0;
                  if ( (*(_DWORD *)(*(_QWORD *)v107 + 200LL) & 0x400000) != 0 && (*(_BYTE *)(v94 + 12) & 1) != 0 && v92 )
                    *(_DWORD *)(v31 + 56) |= 0x4000u;
                  else
                    *(_DWORD *)(v31 + 56) |= 0x80u;
                }
                *(_DWORD *)(v31 + 4) = v98;
                *(_DWORD *)(v31 + 60) = v40;
                LODWORD(v31) = v106;
                v45 = (char *)v108;
                break;
            }
            BytesInUnicodeString = 0;
            v14 = RtlOemToUnicodeN((PWCH)&v45[v42], v39 - v96, &BytesInUnicodeString, (PCCH)Buf1[1], LOWORD(Buf1[0]));
            v95 = v14;
            if ( BytesInUnicodeString < v40 )
              v14 = -2147483643;
            v95 = v14;
            v53 = (char *)v108;
            *(_DWORD *)((char *)v108 + v114) = v31 - v114;
            v54 = BytesInUnicodeString;
            *v126 = v96 + BytesInUnicodeString + ((*(_DWORD *)v126 + 7) & 0xFFFFFFF8);
            if ( v14 < 0 )
            {
              v37 = Context1;
              v35 = (IRP *)Context2;
              goto LABEL_246;
            }
            goto LABEL_195;
          }
          v123 = 0;
          v55 = LOWORD(Src[0]);
          v115 = LOWORD(Src[0]);
          if ( (_DWORD)v31 && ((unsigned int)LOWORD(Src[0]) + v32 > v39 || *(_DWORD *)&v105[7] < (unsigned int)v31) )
          {
            v14 = 0;
            v95 = 0;
            v37 = Context1;
            v35 = (IRP *)Context2;
            goto LABEL_246;
          }
          v56 = *v126;
          v57 = (unsigned int)(v32 + v31);
          *(_QWORD *)&DestinationString.Length = v57;
          memset((char *)v108 + v56, 0, v57 - v56);
          v58 = (unsigned int)(*(_DWORD *)&v105[3] - 1);
          if ( *(_DWORD *)&v105[3] == 1 )
            goto LABEL_165;
          if ( *(_DWORD *)&v105[3] == 2 )
            goto LABEL_164;
          v59 = (unsigned int)(*(_DWORD *)&v105[3] - 3);
          if ( *(_DWORD *)&v105[3] == 3 )
            goto LABEL_161;
          if ( *(_DWORD *)&v105[3] != 12 )
            break;
          v60 = (char *)v108;
          *(_DWORD *)((char *)v108 + v31 + 4) = v98;
          *(_DWORD *)&v60[v31 + 8] = v55;
LABEL_190:
          v67 = v39 - v96;
          if ( v67 >= v55 )
            v67 = v55;
          v68 = v67;
          BytesInUnicodeString = v67;
          v53 = (char *)v108;
          memmove((char *)v108 + v57, Src[1], v68);
          *(_DWORD *)&v53[v114] = v31 - v114;
          v54 = BytesInUnicodeString;
          *v126 = v96 + BytesInUnicodeString + ((*(_DWORD *)v126 + 7) & 0xFFFFFFF8);
          if ( v54 < v55 )
          {
            v14 = -2147483643;
            v95 = -2147483643;
            v37 = Context1;
            v35 = (IRP *)Context2;
            goto LABEL_246;
          }
          v46 = (unsigned int)v31;
LABEL_195:
          if ( *(_DWORD *)&v105[3] == 37 )
          {
            if ( *(_DWORD *)v94 == 538976302 )
            {
              v78 = *(_QWORD *)v103;
              v79 = *(_QWORD *)(*(_QWORD *)v103 + 176LL);
              if ( v79 )
              {
                if ( *(_WORD *)v79 == 1284 )
                {
                  v80 = *(_QWORD *)(v79 + 184);
                  if ( *(_BYTE *)(v80 + 376) != 32 )
                    goto LABEL_224;
                }
                v82 = *(_QWORD *)(v79 + 184);
LABEL_226:
                v81 = *(_QWORD *)(v82 + 352)
                    + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v79 + 128) - 2) << *(_BYTE *)(v82 + 378));
                goto LABEL_227;
              }
LABEL_241:
              v86 = 0;
            }
            else
            {
              if ( *(_DWORD *)v94 == 538979886 )
              {
                v78 = *(_QWORD *)(*(_QWORD *)v103 + 176LL);
                if ( !v78 )
                  goto LABEL_241;
                v79 = *(_QWORD *)(v78 + 176);
                if ( !v79 )
                  goto LABEL_241;
                v84 = (__int64 *)(v79 + 184);
                if ( *(_WORD *)v79 != 1284 || (v80 = *v84, *(_BYTE *)(*v84 + 376) == 32) )
                {
                  v82 = *v84;
                  goto LABEL_226;
                }
LABEL_224:
                v81 = *(_QWORD *)(v80 + 344);
LABEL_227:
                v83 = *(unsigned int *)(v78 + 244);
              }
              else
              {
                if ( !*(_QWORD *)v103 )
                  goto LABEL_241;
                if ( **(_WORD **)v103 != 1284
                  || (v85 = *(_QWORD *)(*(_QWORD *)v103 + 184LL), *(_BYTE *)(v85 + 376) == 32) )
                {
                  v81 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v103 + 184LL) + 352LL)
                      + ((unsigned __int64)(unsigned int)(*(_DWORD *)(*(_QWORD *)v103 + 128LL) - 2) << *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v103 + 184LL) + 378LL));
                }
                else
                {
                  v81 = *(_QWORD *)(v85 + 344);
                }
                v83 = v98;
              }
              v86 = v81 + v83;
            }
            *(_QWORD *)&v53[v46 + 96] = v86;
            goto LABEL_243;
          }
          if ( *(_DWORD *)&v105[3] != 38 )
            goto LABEL_244;
          if ( *(_DWORD *)v94 == 538976302 )
          {
            v69 = *(_QWORD *)v103;
            v70 = *(_QWORD *)(*(_QWORD *)v103 + 176LL);
            if ( !v70 )
              goto LABEL_218;
            if ( *(_WORD *)v70 == 1284 )
            {
              v71 = *(_QWORD *)(v70 + 184);
              if ( *(_BYTE *)(v71 + 376) != 32 )
                goto LABEL_201;
            }
            v73 = *(_QWORD *)(v70 + 184);
LABEL_203:
            v72 = *(_QWORD *)(v73 + 352)
                + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v70 + 128) - 2) << *(_BYTE *)(v73 + 378));
            goto LABEL_204;
          }
          if ( *(_DWORD *)v94 == 538979886 )
          {
            v69 = *(_QWORD *)(*(_QWORD *)v103 + 176LL);
            if ( !v69 || (v70 = *(_QWORD *)(v69 + 176)) == 0 )
            {
LABEL_218:
              v77 = 0;
              goto LABEL_219;
            }
            v75 = (__int64 *)(v70 + 184);
            if ( *(_WORD *)v70 != 1284 || (v71 = *v75, *(_BYTE *)(*v75 + 376) == 32) )
            {
              v73 = *v75;
              goto LABEL_203;
            }
LABEL_201:
            v72 = *(_QWORD *)(v71 + 344);
LABEL_204:
            v74 = *(unsigned int *)(v69 + 244);
            goto LABEL_217;
          }
          if ( !*(_QWORD *)v103 )
            goto LABEL_218;
          if ( **(_WORD **)v103 != 1284 || (v76 = *(_QWORD *)(*(_QWORD *)v103 + 184LL), *(_BYTE *)(v76 + 376) == 32) )
            v72 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v103 + 184LL) + 352LL)
                + ((unsigned __int64)(unsigned int)(*(_DWORD *)(*(_QWORD *)v103 + 128LL) - 2) << *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v103 + 184LL) + 378LL));
          else
            v72 = *(_QWORD *)(v76 + 344);
          v74 = v98;
LABEL_217:
          v77 = v72 + v74;
LABEL_219:
          *(_QWORD *)&v53[v46 + 72] = v77;
LABEL_243:
          v54 = BytesInUnicodeString;
LABEL_244:
          v114 = v31;
          v32 = v96;
          v31 = ((v54 + v96 + 7) & 0xFFFFFFF8) + (unsigned int)v31;
          v106 = v31;
          v99 = v98 + 32;
          v17 = *(_QWORD *)v103;
        }
        v59 = (unsigned int)(*(_DWORD *)&v105[3] - 37);
        if ( *(_DWORD *)&v105[3] == 37 )
        {
LABEL_161:
          Fat8dot3ToString(v59, v94, 0, Buf1);
          v14 = RtlOemToUnicodeN((PWCH)((char *)v108 + v31 + 70), 0x18u, &v123, (PCCH)Buf1[1], LOWORD(Buf1[0]));
          v95 = v14;
          *((_BYTE *)v108 + v31 + 68) = v123;
          if ( v14 < 0 )
          {
            v37 = Context1;
            v35 = (IRP *)Context2;
            goto LABEL_246;
          }
          v31 = v106;
        }
        else if ( *(_DWORD *)&v105[3] != 38 )
        {
          KeBugCheckEx(0x23u, 0x9056Eu, *(int *)&v105[3], 0, 0);
        }
LABEL_164:
        v131 = (char *)v108 + (unsigned int)v31;
        FatGetEaLength((int)Context1, v107[0]);
LABEL_165:
        v31 += (unsigned __int64)v108;
        FatGetDirTimes(v58, v94, v31);
        *(_QWORD *)(v31 + 40) = *(unsigned int *)(v94 + 28);
        v61 = v94;
        if ( (*(_BYTE *)(v94 + 11) & 0x10) != 0 )
        {
LABEL_174:
          v65 = *(unsigned __int8 *)(v61 + 11);
          if ( (_BYTE)v65 )
          {
            *(_DWORD *)(v31 + 56) = v65;
            if ( (*(_DWORD *)(*(_QWORD *)v107 + 200LL) & 0x400000) != 0
              && (*(_BYTE *)(v94 + 12) & 1) != 0
              && (v92 || (*(_BYTE *)(v94 + 11) & 0x10) != 0) )
            {
              *(_DWORD *)(v31 + 56) |= 0x4000u;
              *(_DWORD *)(v31 + 56) &= ~0x80u;
            }
          }
          else
          {
            *(_DWORD *)(v31 + 56) = 0;
            if ( (*(_DWORD *)(*(_QWORD *)v107 + 200LL) & 0x400000) != 0 && (*(_BYTE *)(v94 + 12) & 1) != 0 && v92 )
              *(_DWORD *)(v31 + 56) |= 0x4000u;
            else
              *(_DWORD *)(v31 + 56) |= 0x80u;
          }
          *(_DWORD *)(v31 + 4) = v98;
          *(_DWORD *)(v31 + 60) = v55;
          LODWORD(v31) = v106;
          goto LABEL_190;
        }
        if ( (*(_DWORD *)(*(_QWORD *)v107 + 200LL) & 0x400000) == 0
          || (v62 = *(_BYTE *)(v94 + 12), (v62 & 1) == 0)
          || !v92 )
        {
LABEL_173:
          *(_QWORD *)(v31 + 48) = *(_DWORD *)(v94 + 28) + v111 - 1 - (*(_DWORD *)(v94 + 28) + v111 - 1) % v111;
          v61 = v94;
          goto LABEL_174;
        }
        if ( (v62 & 2) != 0 )
        {
          v120 = 0;
          v121[0] = 0;
          v109[0] = 0;
          v66 = *(unsigned __int16 *)(v94 + 26);
          v120 = v66;
          if ( *(_BYTE *)(*(_QWORD *)v107 + 376LL) == 32 )
          {
            v66 += *(unsigned __int16 *)(v94 + 20) << 16;
            v120 = v66;
          }
          FatGetEfsInfoFromHeaderOnDisk((_DWORD)Context1, v107[0], v66, (unsigned int)v121, (__int64)v109);
          *(_QWORD *)(v31 + 40) -= v121[0];
          v63 = *(_QWORD *)(v31 + 40);
          if ( v109[0] <= 0x7FFFu )
          {
            v64 = (unsigned __int8)(((LOBYTE(v109[0]) + 15) & 0xF0) - LOBYTE(v109[0]));
            goto LABEL_172;
          }
        }
        else
        {
          *(_QWORD *)(v31 + 40) -= *(unsigned int *)(*(_QWORD *)v107 + 372LL);
          v63 = *(_QWORD *)(v31 + 40);
        }
        v64 = (*(_BYTE *)(v94 + 12) & 4 | ((unsigned __int64)*(unsigned __int8 *)(v94 + 12) >> 2) & 0x38) >> 2;
LABEL_172:
        *(_QWORD *)(v31 + 40) = v63 - v64;
        goto LABEL_173;
      case 0x25:
        v32 = 104;
        break;
      case 0x26:
        v32 = 80;
        break;
      default:
        v14 = -1073741821;
        v95 = -1073741821;
        goto LABEL_245;
    }
    v96 = v32;
    goto LABEL_90;
  }
  v22 = 0;
  DestinationString = 0;
  *(_BYTE *)(v12 + 8) = FsRtlDoesNameContainWildCards(FileName);
  for ( i = 0; ; ++i )
  {
    v112 = i;
    if ( i >= FileName->Length >> 1 )
    {
      v26 = FileName->Length + ((unsigned __int64)FileName->Length >> 1);
      PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, v26, 0x6E746146u);
      v28 = PoolWithTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
        memset(PoolWithTag, 0, v26);
      *(_QWORD *)(v12 + 56) = v28;
      *(_WORD *)(v12 + 48) = FileName->Length;
      *(_WORD *)(v12 + 50) = FileName->Length;
      v29 = FileName->Length;
      DestinationString.Buffer = &v28[v29];
      v25 = v29 >> 1;
      DestinationString.Length = v25;
      DestinationString.MaximumLength = v25;
      *(_DWORD *)(v12 + 4) |= 8u;
      for ( j = 0; ; ++j )
      {
        v112 = j;
        if ( j >= FileName->Length >> 1 )
          break;
        v25 = FileName->Buffer[j];
        if ( (unsigned int)v25 >= 0x61 && (unsigned int)v25 <= 0x7A )
          v25 = (unsigned int)(v25 - 32);
        *(_WORD *)(*(_QWORD *)(v12 + 56) + 2LL * j) = v25;
        DestinationString.Buffer[j] = v25;
      }
LABEL_64:
      if ( (*(_DWORD *)(v12 + 4) & 2) == 0 )
      {
        DbcsName = DestinationString;
        if ( !FsRtlIsFatDbcsLegal(&DbcsName, *(_BYTE *)(v12 + 8), 0, 0) )
        {
          if ( v22 )
          {
            RtlFreeOemString(&DestinationString);
            *(_DWORD *)(v12 + 4) &= ~4u;
          }
          *(_DWORD *)(v12 + 4) |= 2u;
        }
      }
      if ( (*(_DWORD *)(v12 + 4) & 2) == 0 )
      {
        if ( *(_BYTE *)(v12 + 8) )
        {
          *(struct _STRING *)(v12 + 32) = DestinationString;
        }
        else
        {
          v134 = DestinationString;
          FatStringTo8dot3(v25, &v134, v12 + 32);
          if ( (*(_DWORD *)(v12 + 4) & 4) != 0 )
          {
            RtlFreeOemString(&DestinationString);
            *(_DWORD *)(v12 + 4) &= ~4u;
          }
        }
      }
      goto LABEL_75;
    }
    if ( FileName->Buffer[i] >= 0x80u )
      break;
  }
  v14 = RtlUpcaseUnicodeString((PUNICODE_STRING)(v12 + 48), FileName, 1u);
  v95 = v14;
  if ( v14 < 0 )
    goto LABEL_245;
  *(_DWORD *)(v12 + 4) |= 8u;
  v24 = RtlUpcaseUnicodeStringToCountedOemString(&DestinationString, FileName, 1u);
  v14 = v24;
  v95 = v24;
  if ( v24 >= 0 )
  {
    *(_DWORD *)(v12 + 4) |= 4u;
LABEL_53:
    v22 = 1;
    goto LABEL_64;
  }
  if ( v24 == -1073741470 )
  {
    *(_DWORD *)(v12 + 4) |= 2u;
    goto LABEL_53;
  }
LABEL_245:
  v35 = (IRP *)Context2;
  v37 = Context1;
LABEL_246:
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)v103 + 8LL));
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  FatFreeStringBuffer(Src, v87, v88, v89);
  if ( v93 )
    *(_DWORD *)(v12 + 24) = v99;
  FatCompleteRequest_Real(v37, v35, (unsigned int)v14, v90);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14002ed1c  mov     r11, rsp
0x14002ed1f  mov     [r11+18h], rbx
0x14002ed23  mov     [r11+20h], rsi
0x14002ed27  push    rdi
0x14002ed28  push    r12
0x14002ed2a  push    r13
0x14002ed2c  push    r14
0x14002ed2e  push    r15
0x14002ed30  sub     rsp, 200h
0x14002ed37  mov     rax, cs:__security_cookie
0x14002ed3e  xor     rax, rsp
0x14002ed41  mov     [rsp+228h+var_38], rax
0x14002ed49  mov     r15, rdx
0x14002ed4c  mov     [rsp+228h+Context2], rdx
0x14002ed54  mov     r14, rcx
0x14002ed57  mov     [rsp+228h+Context1], rcx
0x14002ed5c  mov     [rsp+228h+var_E0], rcx
0x14002ed64  mov     [rsp+228h+var_E8], rdx
0x14002ed6c  xor     edi, edi
0x14002ed6e  mov     [r11-178h], rdi
0x14002ed75  mov     [r11-190h], rdi
0x14002ed7c  mov     [r11-130h], rdi
0x14002ed83  mov     [r11-138h], rdi
0x14002ed8a  xorps   xmm0, xmm0
0x14002ed8d  movups  xmmword ptr [rsp+228h+Src], xmm0
0x14002ed95  xorps   xmm1, xmm1
0x14002ed98  movups  xmmword ptr [rsp+228h+var_B8], xmm1
0x14002eda0  mov     dword ptr [rsp+228h+var_158], edi
0x14002eda7  mov     [rsp+228h+var_1C0], rdi
0x14002edac  movups  xmmword ptr [rsp+228h+Buf1], xmm0
0x14002edb4  mov     dword ptr [rsp+228h+var_1A8], edi
0x14002edbb  mov     rcx, [rdx+0B8h]
0x14002edc2  mov     eax, [rcx+8]
0x14002edc5  mov     dword ptr [rsp+228h+var_187+7], eax
0x14002edcc  mov     eax, [rcx+18h]
0x14002edcf  mov     dword ptr [rsp+228h+var_187+3], eax
0x14002edd6  mov     r13d, [rcx+20h]
0x14002edda  mov     rbx, [rcx+10h]
0x14002edde  mov     sil, [rcx+2]
0x14002ede2  lea     r9, [r11-130h]
0x14002ede9  lea     r8, [r11-190h]
0x14002edf0  lea     rdx, [r11-178h]
0x14002edf7  mov     rcx, [rcx+30h]
0x14002edfb  call    FatDecodeFileObject
0x14002ee00  cmp     eax, 3
0x14002ee03  jnz     loc_14003025E
0x14002ee09  test    rbx, rbx
0x14002ee0c  jz      short loc_14002EE17
0x14002ee0e  test    byte ptr [rbx], 1
0x14002ee11  jnz     loc_14003025E
0x14002ee17  mov     r15b, sil
0x14002ee1a  and     r15b, 1
0x14002ee1e  mov     r12b, sil
0x14002ee21  and     r12b, 4
0x14002ee25  mov     dword ptr [rsp+228h+var_1A8+4], edi
0x14002ee2c  mov     [rsp+228h+var_1C7], dil
0x14002ee31  mov     eax, dword ptr [rsp+228h+var_187+7]
0x14002ee38  mov     dword ptr [rsp+228h+var_108+4], eax
0x14002ee3f  mov     [rsp+228h+var_C8], eax
0x14002ee46  mov     eax, dword ptr [rsp+228h+var_187+3]
0x14002ee4d  mov     dword ptr [rsp+228h+var_108], eax
0x14002ee54  and     sil, 2
0x14002ee58  mov     [rsp+228h+var_188], sil
0x14002ee60  mov     [rsp+228h+Bcb], rdi
0x14002ee68  mov     [rsp+228h+var_1C5], 1
0x14002ee6d  mov     [rsp+228h+var_1C0], rdi
0x14002ee72  mov     eax, 0Ch
0x14002ee77  mov     [rsp+228h+var_1B4], eax
0x14002ee7b  mov     word ptr [rsp+228h+Buf1+2], ax
0x14002ee83  lea     rax, [rsp+228h+var_88]
0x14002ee8b  mov     [rsp+228h+Buf1+8], rax
0x14002ee93  mov     dword ptr [rsp+228h+Src], 400000h
0x14002ee9e  lea     rax, [rsp+228h+var_78]
0x14002eea6  mov     [rsp+228h+Src+8], rax
0x14002eeae  mov     rsi, qword ptr [rsp+228h+var_130]
0x14002eeb6  cmp     [rsi+38h], rdi
0x14002eeba  jnz     short loc_14002EEC5
0x14002eebc  mov     eax, [rsi+4]
0x14002eebf  test    al, 1
0x14002eec1  mov     dl, 1
0x14002eec3  jz      short loc_14002EEC8
0x14002eec5  mov     dl, dil
0x14002eec8  mov     [rsp+228h+var_1C6], dl
0x14002eecc  mov     [rsp+228h+var_1C8], dl
0x14002eed0  mov     r14d, edi
0x14002eed3  mov     [rsp+228h+var_1B8], edi
0x14002eed7  mov     rax, [rsp+228h+Context2]
0x14002eedf  add     rax, 38h ; '8'
0x14002eee3  mov     [rsp+228h+var_F0], rax
0x14002eeeb  mov     [rax], rdi
0x14002eeee  mov     rcx, qword ptr [rsp+228h+var_178]
0x14002eef6  mov     cl, [rcx+17Ah]
0x14002eefc  mov     eax, 1
0x14002ef01  shl     eax, cl
0x14002ef03  mov     [rsp+228h+var_160], eax
0x14002ef0a  mov     [rsp+228h+var_10C], eax
0x14002ef11  test    dl, dl
0x14002ef13  jnz     short loc_14002EF32
0x14002ef15  test    r15b, r15b
0x14002ef18  jnz     short loc_14002EF32
0x14002ef1a  mov     rdx, qword ptr [rsp+228h+var_190]
0x14002ef22  mov     rcx, [rsp+228h+Context1]
0x14002ef27  call    FatAcquireSharedFcb
0x14002ef2c  test    al, al
0x14002ef2e  jnz     short loc_14002EF8E
0x14002ef30  jmp     short loc_14002EF48
0x14002ef32  mov     rdx, qword ptr [rsp+228h+var_190]
0x14002ef3a  mov     rcx, [rsp+228h+Context1]
0x14002ef3f  call    FatAcquireExclusiveFcb
0x14002ef44  test    al, al
0x14002ef46  jnz     short loc_14002EF5F
0x14002ef48  mov     rdx, [rsp+228h+Context2]; Context2
0x14002ef50  mov     rcx, [rsp+228h+Context1]; Context1
0x14002ef55  call    FatFsdPostRequest
0x14002ef5a  jmp     loc_140030273
0x14002ef5f  test    r15b, r15b
0x14002ef62  jnz     short loc_14002EF8E
0x14002ef64  cmp     [rsi+38h], rdi
0x14002ef68  jz      short loc_14002EF8E
0x14002ef6a  mov     al, dil
0x14002ef6d  mov     [rsp+228h+var_1C8], al
0x14002ef71  mov     [rsp+228h+var_1C6], al
0x14002ef75  mov     rax, qword ptr [rsp+228h+var_190]
0x14002ef7d  mov     rcx, [rax+8]; Resource
0x14002ef81  call    cs:__imp_ExConvertExclusiveToSharedLite
0x14002ef88  nop     dword ptr [rax+rax+00h]
0x14002ef8d  nop
0x14002ef8e  mov     [rsp+228h+var_198], edi
0x14002ef95  mov     [rsp+228h+BytesInUnicodeString], edi
0x14002ef9c  mov     r9d, dword ptr [rsp+228h+var_187+7]
0x14002efa4  mov     r8d, 1
0x14002efaa  mov     rdx, [rsp+228h+Context2]
0x14002efb2  mov     rcx, [rsp+228h+Context1]
0x14002efb7  call    FatLockUserBuffer
0x14002efbc  mov     rdx, [rsp+228h+Context2]
0x14002efc4  call    FatMapUserBuffer
0x14002efc9  mov     [rsp+228h+var_170], rax
0x14002efd1  mov     rdx, qword ptr [rsp+228h+var_190]
0x14002efd9  mov     rcx, [rsp+228h+Context1]
0x14002efde  call    FatVerifyFcb
0x14002efe3  test    r12b, r12b
0x14002efe6  jz      short loc_14002EFF5
0x14002efe8  lea     ecx, [r13+20h]
0x14002efec  mov     dword ptr [rsp+228h+var_1A8+4], ecx
0x14002eff3  jmp     short loc_14002F010
0x14002eff5  test    r15b, r15b
0x14002eff8  jz      short loc_14002F006
0x14002effa  mov     dword ptr [rsp+228h+var_1A8+4], edi
0x14002f001  mov     [rsi+18h], edi
0x14002f004  jmp     short loc_14002F010
0x14002f006  mov     eax, [rsi+18h]
0x14002f009  mov     dword ptr [rsp+228h+var_1A8+4], eax
0x14002f010  cmp     [rsp+228h+var_1C8], dil
0x14002f015  jnz     short loc_14002F033
0x14002f017  test    r15b, r15b
0x14002f01a  jz      short loc_14002F026
0x14002f01c  test    rbx, rbx
0x14002f01f  jz      short loc_14002F026
0x14002f021  cmp     [rbx], di
0x14002f024  jnz     short loc_14002F033
0x14002f026  mov     r15, qword ptr [rsp+228h+var_190]
0x14002f02e  jmp     loc_14002F36A
0x14002f033  test    r15b, r15b
0x14002f036  jz      short loc_14002F0AA
0x14002f038  mov     rcx, [rsi+38h]; P
0x14002f03c  test    rcx, rcx
0x14002f03f  jz      short loc_14002F064
0x14002f041  mov     eax, [rsi+4]
0x14002f044  test    al, 8
0x14002f046  jz      short loc_14002F05D
0x14002f048  mov     edx, 6E746146h; Tag
0x14002f04d  call    cs:__imp_ExFreePoolWithTag
0x14002f054  nop     dword ptr [rax+rax+00h]
0x14002f059  and     dword ptr [rsi+4], 0FFFFFFF7h
0x14002f05d  mov     [rsi+38h], rdi
0x14002f061  mov     [rsi+30h], edi
0x14002f064  cmp     [rsi+28h], rdi
0x14002f068  jz      short loc_14002F08C
0x14002f06a  mov     eax, [rsi+4]
0x14002f06d  test    al, 4
0x14002f06f  jz      short loc_14002F085
0x14002f071  lea     rcx, [rsi+20h]; OemString
0x14002f075  call    cs:__imp_RtlFreeOemString
0x14002f07c  nop     dword ptr [rax+rax+00h]
0x14002f081  and     dword ptr [rsi+4], 0FFFFFFFBh
0x14002f085  mov     [rsi+28h], rdi
0x14002f089  mov     [rsi+20h], edi
0x14002f08c  mov     [rsi+8], dil
0x14002f090  and     dword ptr [rsi+4], 0FFFFFFFEh
0x14002f094  mov     eax, [rsi+4]
0x14002f097  and     eax, 0FFFFFFF7h
0x14002f09a  mov     [rsi+4], eax
0x14002f09d  and     eax, 0FFFFFFFDh
0x14002f0a0  mov     [rsi+4], eax
0x14002f0a3  btr     eax, 0Ch
0x14002f0a7  mov     [rsi+4], eax
0x14002f0aa  test    rbx, rbx
0x14002f0ad  jz      loc_14002F34A
0x14002f0b3  movzx   eax, word ptr [rbx]
0x14002f0b6  test    ax, ax
0x14002f0b9  jz      loc_14002F34A
0x14002f0bf  mov     rdx, [rbx+8]
0x14002f0c3  test    rdx, rdx
0x14002f0c6  jz      loc_14002F34A
0x14002f0cc  mov     r15d, 2
0x14002f0d2  cmp     ax, r15w
0x14002f0d6  jnz     short loc_14002F0E2
0x14002f0d8  cmp     word ptr [rdx], 2Ah ; '*'
0x14002f0dc  jz      loc_14002F34A
0x14002f0e2  mov     r8d, 18h
0x14002f0e8  cmp     ax, r8w
0x14002f0ec  jnz     short loc_14002F118
0x14002f0ee  mov     rcx, [rdx]
0x14002f0f1  cmp     rcx, cs:Fat8QMdot3QM
0x14002f0f8  jnz     short loc_14002F118
0x14002f0fa  mov     rcx, [rdx+8]
0x14002f0fe  cmp     rcx, cs:qword_1400172C8
0x14002f105  jnz     short loc_14002F118
0x14002f107  mov     rcx, [rdx+10h]
0x14002f10b  cmp     rcx, cs:qword_1400172D0
0x14002f112  jz      loc_14002F34A
0x14002f118  mov     r13b, dil
0x14002f11b  xorps   xmm0, xmm0
0x14002f11e  movups  xmmword ptr [rsp+228h+DestinationString.Length], xmm0
0x14002f126  mov     rcx, rbx; Name
0x14002f129  call    cs:__imp_FsRtlDoesNameContainWildCards
0x14002f130  nop     dword ptr [rax+rax+00h]
0x14002f135  mov     [rsi+8], al
0x14002f138  mov     edx, edi
0x14002f13a  mov     r12d, 80h
0x14002f140  mov     [rsp+228h+var_15C], edx
0x14002f147  movzx   ecx, word ptr [rbx]
0x14002f14a  mov     eax, ecx
0x14002f14c  shr     eax, 1
0x14002f14e  cmp     edx, eax
0x14002f150  jnb     short loc_14002F1D1
0x14002f152  mov     ecx, edx
0x14002f154  mov     rax, [rbx+8]
0x14002f158  cmp     [rax+rcx*2], r12w
0x14002f15d  jb      short loc_14002F1CA
0x14002f15f  lea     rcx, [rsi+30h]; DestinationString
0x14002f163  mov     r8b, 1; AllocateDestinationString
0x14002f166  mov     rdx, rbx; SourceString
0x14002f169  call    cs:__imp_RtlUpcaseUnicodeString
0x14002f170  nop     dword ptr [rax+rax+00h]
0x14002f175  mov     r14d, eax
0x14002f178  mov     [rsp+228h+var_1B8], eax
0x14002f17c  test    eax, eax
0x14002f17e  js      loc_1400301E7
0x14002f184  or      dword ptr [rsi+4], 8
0x14002f188  mov     r8b, 1; AllocateDestinationString
0x14002f18b  mov     rdx, rbx; SourceString
0x14002f18e  lea     rcx, [rsp+228h+DestinationString]; DestinationString
0x14002f196  call    cs:__imp_RtlUpcaseUnicodeStringToCountedOemString
0x14002f19d  nop     dword ptr [rax+rax+00h]
0x14002f1a2  mov     r14d, eax
0x14002f1a5  mov     [rsp+228h+var_1B8], eax
0x14002f1a9  test    eax, eax
0x14002f1ab  jns     short loc_14002F1BE
0x14002f1ad  cmp     eax, 0C0000162h
0x14002f1b2  jnz     loc_1400301E7
0x14002f1b8  or      [rsi+4], r15d
0x14002f1bc  jmp     short loc_14002F1C2
0x14002f1be  or      dword ptr [rsi+4], 4
0x14002f1c2  mov     r13b, 1
0x14002f1c5  jmp     loc_14002F294
0x14002f1ca  inc     edx
0x14002f1cc  jmp     loc_14002F140
0x14002f1d1  mov     r12, rcx
0x14002f1d4  shr     r12, 1
0x14002f1d7  add     r12, rcx
0x14002f1da  mov     r8d, 6E746146h; Tag
0x14002f1e0  mov     rdx, r12; NumberOfBytes
0x14002f1e3  mov     ecx, 411h; PoolType
0x14002f1e8  call    cs:__imp_ExAllocatePoolWithTag
0x14002f1ef  nop     dword ptr [rax+rax+00h]
0x14002f1f4  mov     r15, rax
0x14002f1f7  cmp     cs:ExPoolZeroingNativelySupported, dil
0x14002f1fe  jnz     short loc_14002F212
0x14002f200  test    rax, rax
0x14002f203  jz      short loc_14002F212
0x14002f205  mov     r8, r12; Size
0x14002f208  xor     edx, edx; Val
0x14002f20a  mov     rcx, rax; void *
0x14002f20d  call    memset
0x14002f212  mov     [rsi+38h], r15
0x14002f216  movzx   eax, word ptr [rbx]
0x14002f219  mov     [rsi+30h], ax
0x14002f21d  movzx   eax, word ptr [rbx]
0x14002f220  mov     [rsi+32h], ax
0x14002f224  movzx   ecx, word ptr [rbx]
0x14002f227  lea     rax, [r15+rcx]
0x14002f22b  mov     [rsp+228h+DestinationString.Buffer], rax
0x14002f233  shr     rcx, 1
0x14002f236  mov     [rsp+228h+DestinationString.Length], cx
0x14002f23e  mov     [rsp+228h+DestinationString.MaximumLength], cx
0x14002f246  or      dword ptr [rsi+4], 8
0x14002f24a  mov     edx, edi
0x14002f24c  mov     [rsp+228h+var_15C], edx
0x14002f253  movzx   eax, word ptr [rbx]
  ... truncated ...
```
