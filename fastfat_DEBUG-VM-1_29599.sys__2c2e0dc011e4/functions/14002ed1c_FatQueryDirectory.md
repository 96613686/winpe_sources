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
  __int64 v8; // r9
  char v9; // r15
  char v10; // r12
  __int64 v11; // rsi
  char v12; // dl
  NTSTATUS v13; // r14d
  __int64 v15; // rcx
  __int64 v16; // r15
  void *v17; // rcx
  unsigned int v18; // eax
  USHORT Length; // ax
  PWSTR Buffer; // rdx
  char v21; // r13
  unsigned int i; // edx
  NTSTATUS v23; // eax
  unsigned __int64 v24; // rcx
  SIZE_T v25; // r12
  char *PoolWithTag; // rax
  char *v27; // r15
  unsigned __int64 v28; // rcx
  unsigned int j; // edx
  unsigned __int64 v30; // rbx
  int v31; // r12d
  __int64 v32; // rcx
  __int64 v33; // r8
  IRP *v34; // r15
  bool v35; // zf
  PVOID v36; // rbx
  bool IsPfile; // al
  unsigned int v38; // r13d
  ULONG v39; // r15d
  __int64 v40; // rcx
  __int64 v41; // r14
  char *v42; // r12
  __int64 v43; // rcx
  char *v44; // rcx
  __int64 v45; // r12
  __int64 v46; // rcx
  char v47; // cl
  __int64 v48; // rdx
  unsigned __int64 v49; // rax
  int v50; // eax
  int v51; // r8d
  char *v52; // r13
  ULONG v53; // edx
  ULONG v54; // r15d
  __int64 v55; // rcx
  __int64 v56; // r12
  __int64 v57; // rcx
  __int64 v58; // rcx
  char *v59; // rdx
  __int64 v60; // rcx
  char v61; // cl
  __int64 v62; // rdx
  unsigned __int64 v63; // rax
  int v64; // eax
  int v65; // r8d
  ULONG v66; // r13d
  size_t v67; // r8
  __int64 v68; // r9
  __int64 v69; // rax
  __int64 v70; // r8
  unsigned __int64 v71; // r8
  __int64 v72; // rdx
  __int64 v73; // rax
  __int64 *v74; // rdx
  __int64 v75; // r8
  __int64 v76; // rax
  __int64 v77; // r9
  __int64 v78; // rax
  __int64 v79; // r8
  unsigned __int64 v80; // r8
  __int64 v81; // rdx
  __int64 v82; // rax
  __int64 *v83; // rdx
  __int64 v84; // r8
  __int64 v85; // rax
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 v89; // r9
  char v90; // [rsp+60h] [rbp-1C8h]
  bool v91; // [rsp+61h] [rbp-1C7h]
  char v92; // [rsp+63h] [rbp-1C5h]
  __int64 v93; // [rsp+68h] [rbp-1C0h] BYREF
  int v94; // [rsp+70h] [rbp-1B8h]
  int v95; // [rsp+74h] [rbp-1B4h]
  PVOID Context1; // [rsp+78h] [rbp-1B0h]
  unsigned int v97; // [rsp+80h] [rbp-1A8h] BYREF
  int v98; // [rsp+84h] [rbp-1A4h]
  PVOID Context2; // [rsp+88h] [rbp-1A0h]
  int v100; // [rsp+90h] [rbp-198h]
  ULONG BytesInUnicodeString; // [rsp+94h] [rbp-194h] BYREF
  int v102[2]; // [rsp+98h] [rbp-190h] BYREF
  char v103; // [rsp+A0h] [rbp-188h]
  _BYTE v104[11]; // [rsp+A1h] [rbp-187h] BYREF
  unsigned int v105; // [rsp+ACh] [rbp-17Ch]
  int v106[2]; // [rsp+B0h] [rbp-178h] BYREF
  PVOID v107; // [rsp+B8h] [rbp-170h]
  unsigned __int16 v108[2]; // [rsp+C0h] [rbp-168h] BYREF
  unsigned __int16 v109; // [rsp+C4h] [rbp-164h] BYREF
  unsigned int v110; // [rsp+C8h] [rbp-160h]
  unsigned int v111; // [rsp+CCh] [rbp-15Ch]
  int v112; // [rsp+D0h] [rbp-158h] BYREF
  unsigned int v113; // [rsp+D4h] [rbp-154h]
  ULONG v114; // [rsp+D8h] [rbp-150h]
  struct _STRING DestinationString; // [rsp+E0h] [rbp-148h] BYREF
  PVOID Bcb; // [rsp+F0h] [rbp-138h] BYREF
  int v117[2]; // [rsp+F8h] [rbp-130h] BYREF
  void *Buf1[2]; // [rsp+100h] [rbp-128h] BYREF
  int v119; // [rsp+110h] [rbp-118h]
  _DWORD v120[3]; // [rsp+114h] [rbp-114h] BYREF
  __int64 v121; // [rsp+120h] [rbp-108h]
  ULONG v122; // [rsp+128h] [rbp-100h] BYREF
  unsigned int v123; // [rsp+12Ch] [rbp-FCh] BYREF
  int v124; // [rsp+130h] [rbp-F8h]
  __int64 *v125; // [rsp+138h] [rbp-F0h]
  PIRP v126; // [rsp+140h] [rbp-E8h]
  PVOID v127; // [rsp+148h] [rbp-E0h]
  void *Src[2]; // [rsp+150h] [rbp-D8h] BYREF
  int v129; // [rsp+160h] [rbp-C8h]
  char *v130; // [rsp+168h] [rbp-C0h]
  __int64 v131[2]; // [rsp+170h] [rbp-B8h] BYREF
  ANSI_STRING DbcsName; // [rsp+180h] [rbp-A8h] BYREF
  struct _STRING v133; // [rsp+190h] [rbp-98h] BYREF
  char v134; // [rsp+1A0h] [rbp-88h] BYREF
  char v135; // [rsp+1B0h] [rbp-78h] BYREF

  Context2 = Irp;
  Context1 = Entry;
  v127 = Entry;
  v126 = Irp;
  *(_QWORD *)v106 = 0;
  *(_QWORD *)v102 = 0;
  *(_QWORD *)v117 = 0;
  Bcb = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)v131 = 0;
  v112 = 0;
  v93 = 0;
  *(_OWORD *)Buf1 = 0;
  v97 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_DWORD *)&v104[7] = CurrentStackLocation->Parameters.Read.Length;
  *(_DWORD *)&v104[3] = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  EaLength = CurrentStackLocation->Parameters.Create.EaLength;
  FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
  Flags = CurrentStackLocation->Flags;
  if ( (unsigned int)FatDecodeFileObject(CurrentStackLocation->FileObject, v106, v102, v117) != 3
    || FileName && (FileName->Length & 1) != 0 )
  {
    FatCompleteRequest_Real(Entry, Irp, 3221225485LL, v8);
    return 3221225485LL;
  }
  v9 = Flags & 1;
  v10 = Flags & 4;
  v98 = 0;
  v91 = 0;
  v129 = *(_DWORD *)&v104[7];
  v121 = *(_QWORD *)&v104[3];
  v103 = Flags & 2;
  Bcb = 0;
  v92 = 1;
  v93 = 0;
  v95 = 12;
  WORD1(Buf1[0]) = 12;
  Buf1[1] = &v134;
  LODWORD(Src[0]) = 0x400000;
  Src[1] = &v135;
  v11 = *(_QWORD *)v117;
  if ( *(_QWORD *)(*(_QWORD *)v117 + 56LL) || (v12 = 1, (*(_DWORD *)(*(_QWORD *)v117 + 4LL) & 1) != 0) )
    v12 = 0;
  v90 = v12;
  v13 = 0;
  v94 = 0;
  v125 = (__int64 *)((char *)Context2 + 56);
  *((_QWORD *)Context2 + 7) = 0;
  v110 = 1 << *(_BYTE *)(*(_QWORD *)v106 + 378LL);
  v120[2] = v110;
  if ( v12 || v9 )
  {
    if ( !(unsigned __int8)FatAcquireExclusiveFcb(Context1, *(_QWORD *)v102) )
      return FatFsdPostRequest(Context1, Context2);
    if ( !v9 && *(_QWORD *)(v11 + 56) )
    {
      v90 = 0;
      ExConvertExclusiveToSharedLite(*(PERESOURCE *)(*(_QWORD *)v102 + 8LL));
    }
  }
  else if ( !(unsigned __int8)FatAcquireSharedFcb(Context1, *(_QWORD *)v102) )
  {
    return FatFsdPostRequest(Context1, Context2);
  }
  v100 = 0;
  BytesInUnicodeString = 0;
  FatLockUserBuffer(Context1, Context2, 1, *(unsigned int *)&v104[7]);
  v107 = FatMapUserBuffer(v15, (__int64)Context2);
  FatVerifyFcb(Context1, *(_QWORD *)v102);
  if ( v10 )
  {
    v98 = EaLength + 32;
  }
  else if ( v9 )
  {
    v98 = 0;
    *(_DWORD *)(v11 + 24) = 0;
  }
  else
  {
    v98 = *(_DWORD *)(v11 + 24);
  }
  if ( !v90 && (!v9 || !FileName || !FileName->Length) )
  {
    v16 = *(_QWORD *)v102;
    goto LABEL_76;
  }
  if ( v9 )
  {
    v17 = *(void **)(v11 + 56);
    if ( v17 )
    {
      if ( (*(_DWORD *)(v11 + 4) & 8) != 0 )
      {
        ExFreePoolWithTag(v17, 0x6E746146u);
        *(_DWORD *)(v11 + 4) &= ~8u;
      }
      *(_QWORD *)(v11 + 56) = 0;
      *(_DWORD *)(v11 + 48) = 0;
    }
    if ( *(_QWORD *)(v11 + 40) )
    {
      if ( (*(_DWORD *)(v11 + 4) & 4) != 0 )
      {
        RtlFreeOemString((POEM_STRING)(v11 + 32));
        *(_DWORD *)(v11 + 4) &= ~4u;
      }
      *(_QWORD *)(v11 + 40) = 0;
      *(_DWORD *)(v11 + 32) = 0;
    }
    *(_BYTE *)(v11 + 8) = 0;
    *(_DWORD *)(v11 + 4) &= ~1u;
    v18 = *(_DWORD *)(v11 + 4) & 0xFFFFFFF7;
    *(_DWORD *)(v11 + 4) = v18;
    v18 &= ~2u;
    *(_DWORD *)(v11 + 4) = v18;
    *(_DWORD *)(v11 + 4) = v18 & 0xFFFFEFFF;
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
    *(_BYTE *)(v11 + 8) = 1;
    *(_DWORD *)(v11 + 4) |= 1u;
LABEL_75:
    v16 = *(_QWORD *)v102;
    ExConvertExclusiveToSharedLite(*(PERESOURCE *)(*(_QWORD *)v102 + 8LL));
LABEL_76:
    v113 = 0;
    v30 = 0;
    v105 = 0;
    switch ( *(_DWORD *)&v104[3] )
    {
      case 1:
        v31 = 64;
        break;
      case 2:
        v31 = 68;
        break;
      case 3:
        v31 = 94;
        break;
      case 0xC:
        v31 = 12;
LABEL_90:
        v100 = v31;
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              v104[0] = 0;
              if ( v103 && (_DWORD)v30 )
                goto LABEL_245;
              if ( (*(_DWORD *)(*(_QWORD *)v106 + 200LL) & 0x400000) != 0 )
                v112 = 2;
              FatLocateDirent(
                (__int64)Context1,
                v16,
                v11,
                v98,
                &v112,
                (PVOID *)&v93,
                &Bcb,
                &v97,
                v104,
                (UNICODE_STRING *)Src,
                v131);
              if ( !v93 )
              {
                v34 = (IRP *)Context2;
                v35 = (_DWORD)v30 == 0;
                v36 = Context1;
                if ( v35 )
                {
                  v92 = 0;
                  v13 = v90 != 0 ? -1073741809 : -2147483642;
                  v94 = v13;
                }
                goto LABEL_246;
              }
              if ( (*(_DWORD *)(*(_QWORD *)v106 + 200LL) & 0x400000) == 0 )
                break;
              IsPfile = FatFileExtensionIsPfile((unsigned __int16 *)v131, 1u);
              v91 = IsPfile;
              if ( (v112 & 0x20) == 0 )
                break;
              v32 = v93;
              if ( (*(_BYTE *)(v93 + 12) & 1) == 0 || !IsPfile )
                break;
              v98 = v97 + 32;
            }
            LOBYTE(v33) = 1;
            Fat8dot3ToString(v32, v93, v33, Buf1);
            if ( (*(_DWORD *)(*(_QWORD *)v106 + 200LL) & 0x400000) == 0
              || LOWORD(Buf1[0]) != _EFS_SHORT
              || memcmp(Buf1[1], ::Buf1, LOWORD(Buf1[0])) )
            {
              break;
            }
            v98 = v97 + 32;
          }
          v38 = v129 - v30;
          v120[1] = v129 - v30;
          if ( !LOWORD(Src[0]) )
          {
            v39 = RtlxOemStringToUnicodeSize((PCOEM_STRING)Buf1) - 2;
            v114 = v39;
            if ( (_DWORD)v30 && (v39 + v31 > v38 || *(_DWORD *)&v104[7] < (unsigned int)v30) )
            {
              v13 = 0;
              v94 = 0;
              v36 = Context1;
              v34 = (IRP *)Context2;
              goto LABEL_246;
            }
            v40 = *v125;
            v41 = (unsigned int)(v31 + v30);
            *(_QWORD *)&DestinationString.Length = v41;
            v42 = (char *)v107;
            memset((char *)v107 + v40, 0, v41 - v40);
            v43 = (unsigned int)(*(_DWORD *)&v104[3] - 1);
            switch ( *(_DWORD *)&v104[3] )
            {
              case 1:
                goto LABEL_120;
              case 2:
              case 3:
                goto LABEL_119;
              case 0xC:
                v44 = (char *)v107;
                *(_DWORD *)((char *)v107 + v30 + 4) = v97;
                *(_DWORD *)&v44[v30 + 8] = v39;
                v45 = (unsigned int)v30;
                break;
              default:
                if ( (unsigned int)(*(_DWORD *)&v104[3] - 37) >= 2 )
                  KeBugCheckEx(0x23u, 0x90450u, *(int *)&v104[3], 0, 0);
LABEL_119:
                v130 = &v42[(unsigned int)v30];
                FatGetEaLength((int)Context1, v106[0]);
LABEL_120:
                v45 = (unsigned int)v30;
                v30 = (unsigned __int64)v107 + (unsigned int)v30;
                FatGetDirTimes(v43, v93, v30);
                *(_QWORD *)(v30 + 40) = *(unsigned int *)(v93 + 28);
                v46 = v93;
                if ( (*(_BYTE *)(v93 + 11) & 0x10) == 0 )
                {
                  if ( (*(_DWORD *)(*(_QWORD *)v106 + 200LL) & 0x400000) != 0 )
                  {
                    v47 = *(_BYTE *)(v93 + 12);
                    if ( (v47 & 1) != 0 && v91 )
                    {
                      if ( (v47 & 2) == 0 )
                      {
                        *(_QWORD *)(v30 + 40) -= *(unsigned int *)(*(_QWORD *)v106 + 372LL);
                        v48 = *(_QWORD *)(v30 + 40);
                        goto LABEL_126;
                      }
                      v124 = 0;
                      v123 = 0;
                      v109 = 0;
                      v51 = *(unsigned __int16 *)(v93 + 26);
                      v124 = v51;
                      if ( *(_BYTE *)(*(_QWORD *)v106 + 376LL) == 32 )
                      {
                        v51 += *(unsigned __int16 *)(v93 + 20) << 16;
                        v124 = v51;
                      }
                      FatGetEfsInfoFromHeaderOnDisk((_DWORD)Context1, v106[0], v51, (unsigned int)&v123, (__int64)&v109);
                      *(_QWORD *)(v30 + 40) -= v123;
                      v48 = *(_QWORD *)(v30 + 40);
                      if ( v109 > 0x7FFFu )
LABEL_126:
                        v49 = (*(_BYTE *)(v93 + 12) & 4 | ((unsigned __int64)*(unsigned __int8 *)(v93 + 12) >> 2) & 0x38) >> 2;
                      else
                        v49 = (unsigned __int8)(((v109 + 15) & 0xF0) - v109);
                      *(_QWORD *)(v30 + 40) = v48 - v49;
                    }
                  }
                  *(_QWORD *)(v30 + 48) = *(_DWORD *)(v93 + 28) + v110 - 1 - (*(_DWORD *)(v93 + 28) + v110 - 1) % v110;
                  v46 = v93;
                }
                v50 = *(unsigned __int8 *)(v46 + 11);
                if ( (_BYTE)v50 )
                {
                  *(_DWORD *)(v30 + 56) = v50;
                  if ( (*(_DWORD *)(*(_QWORD *)v106 + 200LL) & 0x400000) != 0
                    && (*(_BYTE *)(v93 + 12) & 1) != 0
                    && (v91 || (*(_BYTE *)(v93 + 11) & 0x10) != 0) )
                  {
                    *(_DWORD *)(v30 + 56) |= 0x4000u;
                    *(_DWORD *)(v30 + 56) &= ~0x80u;
                  }
                }
                else
                {
                  *(_DWORD *)(v30 + 56) = 0;
                  if ( (*(_DWORD *)(*(_QWORD *)v106 + 200LL) & 0x400000) != 0 && (*(_BYTE *)(v93 + 12) & 1) != 0 && v91 )
                    *(_DWORD *)(v30 + 56) |= 0x4000u;
                  else
                    *(_DWORD *)(v30 + 56) |= 0x80u;
                }
                *(_DWORD *)(v30 + 4) = v97;
                *(_DWORD *)(v30 + 60) = v39;
                LODWORD(v30) = v105;
                v44 = (char *)v107;
                break;
            }
            BytesInUnicodeString = 0;
            v13 = RtlOemToUnicodeN((PWCH)&v44[v41], v38 - v95, &BytesInUnicodeString, (PCCH)Buf1[1], LOWORD(Buf1[0]));
            v94 = v13;
            if ( BytesInUnicodeString < v39 )
              v13 = -2147483643;
            v94 = v13;
            v52 = (char *)v107;
            *(_DWORD *)((char *)v107 + v113) = v30 - v113;
            v53 = BytesInUnicodeString;
            *v125 = v95 + BytesInUnicodeString + ((*(_DWORD *)v125 + 7) & 0xFFFFFFF8);
            if ( v13 < 0 )
            {
              v36 = Context1;
              v34 = (IRP *)Context2;
              goto LABEL_246;
            }
            goto LABEL_195;
          }
          v122 = 0;
          v54 = LOWORD(Src[0]);
          v114 = LOWORD(Src[0]);
          if ( (_DWORD)v30 && ((unsigned int)LOWORD(Src[0]) + v31 > v38 || *(_DWORD *)&v104[7] < (unsigned int)v30) )
          {
            v13 = 0;
            v94 = 0;
            v36 = Context1;
            v34 = (IRP *)Context2;
            goto LABEL_246;
          }
          v55 = *v125;
          v56 = (unsigned int)(v31 + v30);
          *(_QWORD *)&DestinationString.Length = v56;
          memset((char *)v107 + v55, 0, v56 - v55);
          v57 = (unsigned int)(*(_DWORD *)&v104[3] - 1);
          if ( *(_DWORD *)&v104[3] == 1 )
            goto LABEL_165;
          if ( *(_DWORD *)&v104[3] == 2 )
            goto LABEL_164;
          v58 = (unsigned int)(*(_DWORD *)&v104[3] - 3);
          if ( *(_DWORD *)&v104[3] == 3 )
            goto LABEL_161;
          if ( *(_DWORD *)&v104[3] != 12 )
            break;
          v59 = (char *)v107;
          *(_DWORD *)((char *)v107 + v30 + 4) = v97;
          *(_DWORD *)&v59[v30 + 8] = v54;
LABEL_190:
          v66 = v38 - v95;
          if ( v66 >= v54 )
            v66 = v54;
          v67 = v66;
          BytesInUnicodeString = v66;
          v52 = (char *)v107;
          memmove((char *)v107 + v56, Src[1], v67);
          *(_DWORD *)&v52[v113] = v30 - v113;
          v53 = BytesInUnicodeString;
          *v125 = v95 + BytesInUnicodeString + ((*(_DWORD *)v125 + 7) & 0xFFFFFFF8);
          if ( v53 < v54 )
          {
            v13 = -2147483643;
            v94 = -2147483643;
            v36 = Context1;
            v34 = (IRP *)Context2;
            goto LABEL_246;
          }
          v45 = (unsigned int)v30;
LABEL_195:
          if ( *(_DWORD *)&v104[3] == 37 )
          {
            if ( *(_DWORD *)v93 == 538976302 )
            {
              v77 = *(_QWORD *)v102;
              v78 = *(_QWORD *)(*(_QWORD *)v102 + 176LL);
              if ( v78 )
              {
                if ( *(_WORD *)v78 == 1284 )
                {
                  v79 = *(_QWORD *)(v78 + 184);
                  if ( *(_BYTE *)(v79 + 376) != 32 )
                    goto LABEL_224;
                }
                v81 = *(_QWORD *)(v78 + 184);
LABEL_226:
                v80 = *(_QWORD *)(v81 + 352)
                    + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v78 + 128) - 2) << *(_BYTE *)(v81 + 378));
                goto LABEL_227;
              }
LABEL_241:
              v85 = 0;
            }
            else
            {
              if ( *(_DWORD *)v93 == 538979886 )
              {
                v77 = *(_QWORD *)(*(_QWORD *)v102 + 176LL);
                if ( !v77 )
                  goto LABEL_241;
                v78 = *(_QWORD *)(v77 + 176);
                if ( !v78 )
                  goto LABEL_241;
                v83 = (__int64 *)(v78 + 184);
                if ( *(_WORD *)v78 != 1284 || (v79 = *v83, *(_BYTE *)(*v83 + 376) == 32) )
                {
                  v81 = *v83;
                  goto LABEL_226;
                }
LABEL_224:
                v80 = *(_QWORD *)(v79 + 344);
LABEL_227:
                v82 = *(unsigned int *)(v77 + 244);
              }
              else
              {
                if ( !*(_QWORD *)v102 )
                  goto LABEL_241;
                if ( **(_WORD **)v102 != 1284
                  || (v84 = *(_QWORD *)(*(_QWORD *)v102 + 184LL), *(_BYTE *)(v84 + 376) == 32) )
                {
                  v80 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v102 + 184LL) + 352LL)
                      + ((unsigned __int64)(unsigned int)(*(_DWORD *)(*(_QWORD *)v102 + 128LL) - 2) << *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v102 + 184LL) + 378LL));
                }
                else
                {
                  v80 = *(_QWORD *)(v84 + 344);
                }
                v82 = v97;
              }
              v85 = v80 + v82;
            }
            *(_QWORD *)&v52[v45 + 96] = v85;
            goto LABEL_243;
          }
          if ( *(_DWORD *)&v104[3] != 38 )
            goto LABEL_244;
          if ( *(_DWORD *)v93 == 538976302 )
          {
            v68 = *(_QWORD *)v102;
            v69 = *(_QWORD *)(*(_QWORD *)v102 + 176LL);
            if ( !v69 )
              goto LABEL_218;
            if ( *(_WORD *)v69 == 1284 )
            {
              v70 = *(_QWORD *)(v69 + 184);
              if ( *(_BYTE *)(v70 + 376) != 32 )
                goto LABEL_201;
            }
            v72 = *(_QWORD *)(v69 + 184);
LABEL_203:
            v71 = *(_QWORD *)(v72 + 352)
                + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v69 + 128) - 2) << *(_BYTE *)(v72 + 378));
            goto LABEL_204;
          }
          if ( *(_DWORD *)v93 == 538979886 )
          {
            v68 = *(_QWORD *)(*(_QWORD *)v102 + 176LL);
            if ( !v68 || (v69 = *(_QWORD *)(v68 + 176)) == 0 )
            {
LABEL_218:
              v76 = 0;
              goto LABEL_219;
            }
            v74 = (__int64 *)(v69 + 184);
            if ( *(_WORD *)v69 != 1284 || (v70 = *v74, *(_BYTE *)(*v74 + 376) == 32) )
            {
              v72 = *v74;
              goto LABEL_203;
            }
LABEL_201:
            v71 = *(_QWORD *)(v70 + 344);
LABEL_204:
            v73 = *(unsigned int *)(v68 + 244);
            goto LABEL_217;
          }
          if ( !*(_QWORD *)v102 )
            goto LABEL_218;
          if ( **(_WORD **)v102 != 1284 || (v75 = *(_QWORD *)(*(_QWORD *)v102 + 184LL), *(_BYTE *)(v75 + 376) == 32) )
            v71 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v102 + 184LL) + 352LL)
                + ((unsigned __int64)(unsigned int)(*(_DWORD *)(*(_QWORD *)v102 + 128LL) - 2) << *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v102 + 184LL) + 378LL));
          else
            v71 = *(_QWORD *)(v75 + 344);
          v73 = v97;
LABEL_217:
          v76 = v71 + v73;
LABEL_219:
          *(_QWORD *)&v52[v45 + 72] = v76;
LABEL_243:
          v53 = BytesInUnicodeString;
LABEL_244:
          v113 = v30;
          v31 = v95;
          v30 = ((v53 + v95 + 7) & 0xFFFFFFF8) + (unsigned int)v30;
          v105 = v30;
          v98 = v97 + 32;
          v16 = *(_QWORD *)v102;
        }
        v58 = (unsigned int)(*(_DWORD *)&v104[3] - 37);
        if ( *(_DWORD *)&v104[3] == 37 )
        {
LABEL_161:
          Fat8dot3ToString(v58, v93, 0, Buf1);
          v13 = RtlOemToUnicodeN((PWCH)((char *)v107 + v30 + 70), 0x18u, &v122, (PCCH)Buf1[1], LOWORD(Buf1[0]));
          v94 = v13;
          *((_BYTE *)v107 + v30 + 68) = v122;
          if ( v13 < 0 )
          {
            v36 = Context1;
            v34 = (IRP *)Context2;
            goto LABEL_246;
          }
          v30 = v105;
        }
        else if ( *(_DWORD *)&v104[3] != 38 )
        {
          KeBugCheckEx(0x23u, 0x9056Eu, *(int *)&v104[3], 0, 0);
        }
LABEL_164:
        v130 = (char *)v107 + (unsigned int)v30;
        FatGetEaLength((int)Context1, v106[0]);
LABEL_165:
        v30 += (unsigned __int64)v107;
        FatGetDirTimes(v57, v93, v30);
        *(_QWORD *)(v30 + 40) = *(unsigned int *)(v93 + 28);
        v60 = v93;
        if ( (*(_BYTE *)(v93 + 11) & 0x10) != 0 )
        {
LABEL_174:
          v64 = *(unsigned __int8 *)(v60 + 11);
          if ( (_BYTE)v64 )
          {
            *(_DWORD *)(v30 + 56) = v64;
            if ( (*(_DWORD *)(*(_QWORD *)v106 + 200LL) & 0x400000) != 0
              && (*(_BYTE *)(v93 + 12) & 1) != 0
              && (v91 || (*(_BYTE *)(v93 + 11) & 0x10) != 0) )
            {
              *(_DWORD *)(v30 + 56) |= 0x4000u;
              *(_DWORD *)(v30 + 56) &= ~0x80u;
            }
          }
          else
          {
            *(_DWORD *)(v30 + 56) = 0;
            if ( (*(_DWORD *)(*(_QWORD *)v106 + 200LL) & 0x400000) != 0 && (*(_BYTE *)(v93 + 12) & 1) != 0 && v91 )
              *(_DWORD *)(v30 + 56) |= 0x4000u;
            else
              *(_DWORD *)(v30 + 56) |= 0x80u;
          }
          *(_DWORD *)(v30 + 4) = v97;
          *(_DWORD *)(v30 + 60) = v54;
          LODWORD(v30) = v105;
          goto LABEL_190;
        }
        if ( (*(_DWORD *)(*(_QWORD *)v106 + 200LL) & 0x400000) == 0
          || (v61 = *(_BYTE *)(v93 + 12), (v61 & 1) == 0)
          || !v91 )
        {
LABEL_173:
          *(_QWORD *)(v30 + 48) = *(_DWORD *)(v93 + 28) + v110 - 1 - (*(_DWORD *)(v93 + 28) + v110 - 1) % v110;
          v60 = v93;
          goto LABEL_174;
        }
        if ( (v61 & 2) != 0 )
        {
          v119 = 0;
          v120[0] = 0;
          v108[0] = 0;
          v65 = *(unsigned __int16 *)(v93 + 26);
          v119 = v65;
          if ( *(_BYTE *)(*(_QWORD *)v106 + 376LL) == 32 )
          {
            v65 += *(unsigned __int16 *)(v93 + 20) << 16;
            v119 = v65;
          }
          FatGetEfsInfoFromHeaderOnDisk((_DWORD)Context1, v106[0], v65, (unsigned int)v120, (__int64)v108);
          *(_QWORD *)(v30 + 40) -= v120[0];
          v62 = *(_QWORD *)(v30 + 40);
          if ( v108[0] <= 0x7FFFu )
          {
            v63 = (unsigned __int8)(((LOBYTE(v108[0]) + 15) & 0xF0) - LOBYTE(v108[0]));
            goto LABEL_172;
          }
        }
        else
        {
          *(_QWORD *)(v30 + 40) -= *(unsigned int *)(*(_QWORD *)v106 + 372LL);
          v62 = *(_QWORD *)(v30 + 40);
        }
        v63 = (*(_BYTE *)(v93 + 12) & 4 | ((unsigned __int64)*(unsigned __int8 *)(v93 + 12) >> 2) & 0x38) >> 2;
LABEL_172:
        *(_QWORD *)(v30 + 40) = v62 - v63;
        goto LABEL_173;
      case 0x25:
        v31 = 104;
        break;
      case 0x26:
        v31 = 80;
        break;
      default:
        v13 = -1073741821;
        v94 = -1073741821;
        goto LABEL_245;
    }
    v95 = v31;
    goto LABEL_90;
  }
  v21 = 0;
  DestinationString = 0;
  *(_BYTE *)(v11 + 8) = FsRtlDoesNameContainWildCards(FileName);
  for ( i = 0; ; ++i )
  {
    v111 = i;
    if ( i >= FileName->Length >> 1 )
    {
      v25 = FileName->Length + ((unsigned __int64)FileName->Length >> 1);
      PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, v25, 0x6E746146u);
      v27 = PoolWithTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
        memset(PoolWithTag, 0, v25);
      *(_QWORD *)(v11 + 56) = v27;
      *(_WORD *)(v11 + 48) = FileName->Length;
      *(_WORD *)(v11 + 50) = FileName->Length;
      v28 = FileName->Length;
      DestinationString.Buffer = &v27[v28];
      v24 = v28 >> 1;
      DestinationString.Length = v24;
      DestinationString.MaximumLength = v24;
      *(_DWORD *)(v11 + 4) |= 8u;
      for ( j = 0; ; ++j )
      {
        v111 = j;
        if ( j >= FileName->Length >> 1 )
          break;
        v24 = FileName->Buffer[j];
        if ( (unsigned int)v24 >= 0x61 && (unsigned int)v24 <= 0x7A )
          v24 = (unsigned int)(v24 - 32);
        *(_WORD *)(*(_QWORD *)(v11 + 56) + 2LL * j) = v24;
        DestinationString.Buffer[j] = v24;
      }
LABEL_64:
      if ( (*(_DWORD *)(v11 + 4) & 2) == 0 )
      {
        DbcsName = DestinationString;
        if ( !FsRtlIsFatDbcsLegal(&DbcsName, *(_BYTE *)(v11 + 8), 0, 0) )
        {
          if ( v21 )
          {
            RtlFreeOemString(&DestinationString);
            *(_DWORD *)(v11 + 4) &= ~4u;
          }
          *(_DWORD *)(v11 + 4) |= 2u;
        }
      }
      if ( (*(_DWORD *)(v11 + 4) & 2) == 0 )
      {
        if ( *(_BYTE *)(v11 + 8) )
        {
          *(struct _STRING *)(v11 + 32) = DestinationString;
        }
        else
        {
          v133 = DestinationString;
          FatStringTo8dot3(v24, &v133, v11 + 32);
          if ( (*(_DWORD *)(v11 + 4) & 4) != 0 )
          {
            RtlFreeOemString(&DestinationString);
            *(_DWORD *)(v11 + 4) &= ~4u;
          }
        }
      }
      goto LABEL_75;
    }
    if ( FileName->Buffer[i] >= 0x80u )
      break;
  }
  v13 = RtlUpcaseUnicodeString((PUNICODE_STRING)(v11 + 48), FileName, 1u);
  v94 = v13;
  if ( v13 < 0 )
    goto LABEL_245;
  *(_DWORD *)(v11 + 4) |= 8u;
  v23 = RtlUpcaseUnicodeStringToCountedOemString(&DestinationString, FileName, 1u);
  v13 = v23;
  v94 = v23;
  if ( v23 >= 0 )
  {
    *(_DWORD *)(v11 + 4) |= 4u;
LABEL_53:
    v21 = 1;
    goto LABEL_64;
  }
  if ( v23 == -1073741470 )
  {
    *(_DWORD *)(v11 + 4) |= 2u;
    goto LABEL_53;
  }
LABEL_245:
  v34 = (IRP *)Context2;
  v36 = Context1;
LABEL_246:
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)v102 + 8LL));
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  FatFreeStringBuffer(Src, v86, v87, v88);
  if ( v92 )
    *(_DWORD *)(v11 + 24) = v98;
  FatCompleteRequest_Real(v36, v34, (unsigned int)v13, v89);
  return (unsigned int)v13;
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
