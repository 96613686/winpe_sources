# FatCreateNewFile

- ea: `0x140029774`
- end: `0x14002a4a5`
- name: `FatCreateNewFile`
- size: `3377`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, UNICODE_STRING *Name, __int64, __int16, int, __int64, int, __int16, __int64, char, char, char, char, char)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, loader_planting`

## callers

- `0x1400268c0`

## callees

- `0x14000179c`
- `0x1400018a4`
- `0x140001d4c`
- `0x140002ed8`
- `0x140002f68`
- `0x140006304`
- `0x1400065a4`
- `0x14000c230`
- `0x14000c380`
- `0x14000c680`
- `0x14002023c`
- `0x140020458`
- `0x140023ad4`
- `0x140024228`
- `0x140029774`
- `0x14002ca48`
- `0x1400302d8`
- `0x14003062c`
- `0x140031468`
- `0x140031d74`
- `0x140035234`
- `0x14003db44`
- `0x14004498c`
- `0x140044bac`
- `0x1400475e8`
- `0x140047960`
- `0x14004814c`
- `0x140048184`
- `0x140048680`
- `0x1400486ec`

## import_xrefs

- `ntoskrnl!RtlClearBits` at `0x14005c123`
- `ntoskrnl!RtlClearBits` at `0x14005c123`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140029e6f`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140029ece`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140029e6f`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140029ece`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14002a14b`
- `ntoskrnl!FsRtlNotifyFullReportChange` at `0x14002a14b`
- `ntoskrnl!IoSetShareAccess` at `0x14002a178`
- `ntoskrnl!IoSetShareAccess` at `0x14002a178`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x140029e9f`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x140029e9f`
- `ntoskrnl!FsRtlFindInTunnelCache` at `0x1400299ac`
- `ntoskrnl!FsRtlFindInTunnelCache` at `0x1400299ac`
- `ntoskrnl!CcPreparePinWrite` at `0x14002a231`
- `ntoskrnl!CcPreparePinWrite` at `0x14002a231`
- `ntoskrnl!CcUnpinData` at `0x14002a25d`
- `ntoskrnl!CcUnpinData` at `0x14002a45a`
- `ntoskrnl!CcUnpinData` at `0x14002a473`
- `ntoskrnl!CcUnpinData` at `0x14005c027`
- `ntoskrnl!CcUnpinData` at `0x14005c24d`
- `ntoskrnl!CcUnpinData` at `0x14005c266`
- `ntoskrnl!CcUnpinData` at `0x14005c332`
- `ntoskrnl!CcUnpinData` at `0x14005c34b`
- `ntoskrnl!CcUnpinData` at `0x14005c3ea`
- `ntoskrnl!CcUnpinData` at `0x14005c403`
- `ntoskrnl!CcUnpinData` at `0x14005c4a1`
- `ntoskrnl!CcUnpinData` at `0x14005c4ba`
- `ntoskrnl!CcUnpinData` at `0x14002a25d`
- `ntoskrnl!CcUnpinData` at `0x14002a45a`
- `ntoskrnl!CcUnpinData` at `0x14002a473`
- `ntoskrnl!CcUnpinData` at `0x14005c027`
- `ntoskrnl!CcUnpinData` at `0x14005c24d`
- `ntoskrnl!CcUnpinData` at `0x14005c266`
- `ntoskrnl!CcUnpinData` at `0x14005c332`
- `ntoskrnl!CcUnpinData` at `0x14005c34b`
- `ntoskrnl!CcUnpinData` at `0x14005c3ea`
- `ntoskrnl!CcUnpinData` at `0x14005c403`
- `ntoskrnl!CcUnpinData` at `0x14005c4a1`
- `ntoskrnl!CcUnpinData` at `0x14005c4ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a42c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a494`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c080`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c282`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c367`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c41f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c4d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a42c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a494`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c080`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c282`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c367`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c41f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c4d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029cab`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029cab`
- `ntoskrnl!ExRaiseStatus` at `0x140029ee9`
- `ntoskrnl!ExRaiseStatus` at `0x14002a003`
- `ntoskrnl!ExRaiseStatus` at `0x14002a406`
- `ntoskrnl!ExRaiseStatus` at `0x140029ee9`
- `ntoskrnl!ExRaiseStatus` at `0x14002a003`
- `ntoskrnl!ExRaiseStatus` at `0x14002a406`

## pseudocode

```c
__int64 __fastcall FatCreateNewFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _FILE_OBJECT *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        UNICODE_STRING *Name,
        ACCESS_MASK *a9,
        unsigned __int16 a10,
        unsigned int a11,
        __int64 a12,
        int a13,
        __int16 a14,
        __int64 a15,
        char a16,
        char a17,
        char a18,
        char a19,
        char a20)
{
  UNICODE_STRING *p_LongName; // rbx
  __int64 v24; // r12
  char v25; // cl
  unsigned int v26; // r13d
  ULONG v27; // edi
  unsigned int NewDirent; // eax
  __int64 v29; // rbx
  void *v30; // r9
  PVOID PoolWithTag; // rax
  __int64 v32; // r12
  bool v33; // cf
  UNICODE_STRING *v34; // r13
  __int64 v35; // r12
  __int64 Fcb; // rdi
  NTSTATUS v37; // eax
  __int64 v38; // rcx
  _DWORD *v39; // r12
  _DWORD *v40; // rbx
  __int64 v41; // rdx
  unsigned int v42; // r11d
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 Ccb; // rbx
  __int64 v46; // rdx
  __int64 v47; // r10
  _DWORD *v48; // r13
  __int64 v49; // r8
  PFILE_OBJECT v50; // rdx
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  int v54; // edx
  int Callback; // r15d
  int v56; // ecx
  __int64 v57; // rax
  int Action; // [rsp+38h] [rbp-250h]
  char v59; // [rsp+60h] [rbp-228h]
  char v60; // [rsp+61h] [rbp-227h]
  char v61; // [rsp+62h] [rbp-226h] BYREF
  char v62; // [rsp+63h] [rbp-225h] BYREF
  char v63; // [rsp+64h] [rbp-224h] BYREF
  char v64; // [rsp+65h] [rbp-223h] BYREF
  char v65; // [rsp+66h] [rbp-222h]
  BOOLEAN v66; // [rsp+67h] [rbp-221h]
  char v67; // [rsp+68h] [rbp-220h]
  char v68; // [rsp+69h] [rbp-21Fh]
  char v69; // [rsp+6Ah] [rbp-21Eh]
  char v70; // [rsp+6Bh] [rbp-21Dh]
  size_t Size; // [rsp+70h] [rbp-218h] BYREF
  __int64 v72; // [rsp+78h] [rbp-210h]
  __int64 v73; // [rsp+80h] [rbp-208h] BYREF
  void *v74; // [rsp+88h] [rbp-200h] BYREF
  PVOID v75; // [rsp+90h] [rbp-1F8h] BYREF
  ULONG v76; // [rsp+98h] [rbp-1F0h]
  __int64 v77; // [rsp+A0h] [rbp-1E8h]
  PVOID Bcb; // [rsp+A8h] [rbp-1E0h] BYREF
  void *Src; // [rsp+B0h] [rbp-1D8h]
  struct _FILE_OBJECT *v80; // [rsp+B8h] [rbp-1D0h]
  PVOID Buffer; // [rsp+C0h] [rbp-1C8h] BYREF
  unsigned int v82; // [rsp+C8h] [rbp-1C0h]
  unsigned int v83; // [rsp+CCh] [rbp-1BCh]
  __int64 v84; // [rsp+D0h] [rbp-1B8h]
  int v85[2]; // [rsp+D8h] [rbp-1B0h]
  void *v86[2]; // [rsp+E0h] [rbp-1A8h] BYREF
  UNICODE_STRING *v87; // [rsp+F0h] [rbp-198h]
  PFILE_OBJECT FileObject; // [rsp+F8h] [rbp-190h]
  __int64 v89; // [rsp+100h] [rbp-188h]
  __int64 v90; // [rsp+108h] [rbp-180h]
  UNICODE_STRING LongName; // [rsp+110h] [rbp-178h] BYREF
  ULONG DataLength; // [rsp+120h] [rbp-168h] BYREF
  __int64 v93; // [rsp+128h] [rbp-160h]
  void *v94; // [rsp+130h] [rbp-158h]
  void *v95; // [rsp+138h] [rbp-150h]
  void *v96; // [rsp+140h] [rbp-148h] BYREF
  __int64 Data; // [rsp+148h] [rbp-140h] BYREF
  UNICODE_STRING ShortName; // [rsp+150h] [rbp-138h] BYREF
  _QWORD v99[3]; // [rsp+160h] [rbp-128h] BYREF
  ACCESS_MASK *v100; // [rsp+178h] [rbp-110h]
  __int64 v101; // [rsp+180h] [rbp-108h]
  __int64 v102; // [rsp+188h] [rbp-100h]
  __int64 v103; // [rsp+190h] [rbp-F8h]
  __int64 v104; // [rsp+198h] [rbp-F0h] BYREF
  _BYTE v105[56]; // [rsp+1A8h] [rbp-E0h] BYREF
  __int64 v106; // [rsp+1E0h] [rbp-A8h] BYREF

  FileObject = a4;
  v93 = a3;
  v90 = a2;
  v80 = a4;
  Buffer = (PVOID)a5;
  v101 = a5;
  *(_QWORD *)v85 = a6;
  v102 = a6;
  p_LongName = Name;
  v87 = Name;
  v100 = a9;
  v99[2] = a12;
  v70 = a16;
  *(_OWORD *)a1 = 0;
  v89 = 0;
  v74 = 0;
  Bcb = 0;
  v63 = 0;
  v62 = 0;
  v64 = 0;
  v75 = 0;
  v96 = 0;
  v59 = 0;
  v99[0] = 786432;
  *(_QWORD *)&ShortName.Length = 1572864;
  *(_QWORD *)&LongName.Length = 3407872;
  Data = 0;
  *(_OWORD *)v86 = 0;
  v61 = 0;
  v72 = 0;
  v69 = 0;
  v77 = 0;
  v99[1] = &v104;
  ShortName.Buffer = (PWSTR)&v106;
  LongName.Buffer = (PWSTR)v105;
  LOWORD(v73) = 0;
  if ( a17 && a13 )
  {
    *(_DWORD *)a1 = -1073741790;
    return a1;
  }
  if ( a18 && (a14 & 1) != 0 )
  {
    *(_DWORD *)a1 = -1073741535;
    return a1;
  }
  v67 = 0;
  v65 = 0;
  DataLength = 8;
  v66 = FsRtlFindInTunnelCache(
          (TUNNEL *)(a5 + 1032),
          *(_QWORD *)(a6 + 256) ^ *(unsigned int *)(a6 + 128),
          Name,
          &ShortName,
          &LongName,
          &DataLength,
          &Data);
  v24 = *(_QWORD *)v85;
  FatSelectNames(
    a2,
    *(_QWORD *)v85,
    a7,
    Name,
    v99,
    (unsigned __int64)&ShortName & -(__int64)(v66 != 0),
    &v63,
    &v62,
    &v64);
  if ( (byte_140017D4C & 1) != 0 )
  {
    v25 = v64;
    v60 = v64;
    if ( !v64 && LongName.Length )
    {
      if ( (unsigned __int8)FatLfnDirentExists(a2, v24) )
      {
        v25 = v64;
      }
      else
      {
        v67 = 1;
        v25 = 1;
        v60 = 1;
        p_LongName = &LongName;
        v87 = &LongName;
        v63 = 0;
        v62 = 0;
      }
    }
  }
  else
  {
    v63 = 0;
    v62 = 0;
    v25 = 0;
    v60 = 0;
  }
  LODWORD(Size) = 0;
  v26 = 0;
  v83 = 0;
  v95 = 0;
  v94 = 0;
  v68 = 0;
  if ( v25 )
    v27 = (((unsigned __int64)p_LongName->Length >> 1) + 12) / 0xD + 1;
  else
    v27 = 1;
  v76 = v27;
  NewDirent = FatCreateNewDirent(a2, v24, v27);
  v29 = NewDirent;
  v82 = NewDirent;
  FatPrepareWriteDirectoryFile(a2, v24, NewDirent, 32, &Bcb, &v74);
  v30 = v74;
  Src = v74;
  v94 = v74;
  v103 = v29 + 32LL * (v27 - 1);
  if ( ((v29 ^ v103) & 0xFFFFFFFFFFFFF000uLL) != 0 )
  {
    LODWORD(Size) = (v29 & 0xFFFFF000) + 4096 - v29;
    v26 = (unsigned int)Size >> 5;
    v83 = (unsigned int)Size >> 5;
    FatPrepareWriteDirectoryFile(a2, v24, ((unsigned int)v29 & 0xFFFFF000) + 4096, 32, &v75, &v96);
    v95 = Src;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, 32LL * v27, 0x44746146u);
    v30 = PoolWithTag;
    Src = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    {
      memset(PoolWithTag, 0, 32LL * v27);
      v30 = Src;
    }
    v74 = v30;
    v59 = 1;
  }
  v32 = 32LL * v27;
  v84 = (__int64)v30 + v32 - 32;
  v33 = v66 != 0;
  v66 = -v66;
  LOBYTE(v30) = v63;
  FatConstructDirent(
    (unsigned __int64)&Data & -(__int64)v33,
    v84,
    (unsigned int)v99,
    (_DWORD)v30,
    v62,
    (unsigned __int64)v87 & -(__int64)(v60 != 0),
    a14 | 0x20,
    1,
    (unsigned __int64)&Data & -(__int64)v33);
  if ( v59 )
  {
    v29 = (unsigned int)Size;
    memmove(v95, Src, (unsigned int)Size);
    memmove(v96, (char *)Src + 32 * v26, v32 - v29);
    v84 = (__int64)v96 + 32 * (v27 - v26) - 32;
    LODWORD(v29) = v82;
  }
  v34 = v87;
  v35 = *(_QWORD *)v85;
  Fcb = FatCreateFcb(
          v60 != 0 ? (unsigned int)v87 : 0,
          (_DWORD)Buffer,
          v85[0],
          v29,
          v103,
          v84,
          (unsigned __int64)v87 & -(__int64)(v60 != 0),
          (unsigned __int64)v87 & -(__int64)(v60 != 0),
          v70,
          0);
  v72 = Fcb;
  v89 = Fcb;
  v94 = 0;
  v37 = FsRtlCheckOplockEx((POPLOCK)(Fcb + 88), *(PIRP *)(a2 + 40), 2u, 0, 0, 0);
  *(_DWORD *)a1 = v37;
  if ( a19 )
  {
    if ( v37 )
      goto LABEL_30;
    v37 = FsRtlOplockFsctrl((POPLOCK)(Fcb + 88), *(PIRP *)(a2 + 40), *(_DWORD *)(Fcb + 228) + 1);
    *(_DWORD *)a1 = v37;
  }
  if ( v37
    || (v37 = FsRtlCheckOplockEx((POPLOCK)(v35 + 88), *(PIRP *)(a2 + 40), 0x10u, 0, 0, 0), (*(_DWORD *)a1 = v37) != 0) )
  {
LABEL_30:
    *(_DWORD *)(a2 + 72) = v37;
    ExRaiseStatus(*(_DWORD *)a1);
  }
  v39 = (_DWORD *)(Fcb + 192);
  if ( a20 )
    *v39 |= 0x20u;
  v40 = Buffer;
  if ( (*((_DWORD *)Buffer + 50) & 0x400000) != 0
    && (int)EfsFileRequiresEncryptionCallback(v93, *(_QWORD *)(a2 + 40), 0, &v61) >= 0
    && ((*(_DWORD *)(*(_QWORD *)v85 + 192LL) & 0x60000) != 0 || (a14 & 0x4000) != 0 || v61) )
  {
    v61 = 1;
    v39 = (_DWORD *)(Fcb + 192);
    *(_DWORD *)(Fcb + 192) |= 0x8000u;
    *(_BYTE *)(Fcb + 5) = 2;
    v41 = v84;
    *(_BYTE *)(v84 + 12) |= 1u;
    *(_DWORD *)(Fcb + 132) = v40[93];
    v42 = a11;
    v38 = (a11 + 15) & 0xFFFFFFF0;
    *(_BYTE *)(Fcb + 136) = ((a11 + 15) & 0xF0) - a11;
    *(_DWORD *)(v41 + 28) = v38;
    LOBYTE(v38) = *(_BYTE *)(v41 + 12) & 0x1B | (4 * (*(_BYTE *)(Fcb + 136) & 1 | (4 * (*(_BYTE *)(Fcb + 136) & 0xFE))));
    *(_BYTE *)(v41 + 12) = v38;
  }
  else
  {
    v42 = a11;
  }
  if ( !(unsigned __int8)FatIsIoRangeValid(v38, v42, 0, *(unsigned int *)(Fcb + 132)) )
  {
    *(_DWORD *)(a2 + 72) = -1073741697;
    ExRaiseStatus(-1073741697);
  }
  FatAddFileAllocation(a2);
  v69 = 1;
  *v39 |= 2u;
  if ( a13 )
    FatCreateEa(a2, *(_QWORD *)(Fcb + 184), Fcb + 480, (__int64)&v73);
  if ( *(_BYTE *)(*(_QWORD *)(Fcb + 184) + 376LL) != 32 )
  {
    v44 = v84;
    *(_WORD *)(v84 + 20) = v73;
  }
  if ( (v40[50] & 0x400000) != 0 && v61 )
    FatRemovePfileExtension(v34);
  if ( !*(_QWORD *)(Fcb + 536) )
    FatSetFullNameInFcb(a2, Fcb, v34);
  Ccb = FatCreateCcb(v44, v43);
  v77 = Ccb;
  FatSetFileObject(FileObject, v46, Fcb, Ccb);
  *(_QWORD *)(v47 + 40) = *(_QWORD *)(Fcb + 120);
  if ( !*(_QWORD *)(Fcb + 536) )
    FatSetFullFileNameInFcb(a2);
  v48 = Buffer;
  FsRtlNotifyFullReportChange(
    *((PNOTIFY_SYNC *)Buffer + 102),
    (PLIST_ENTRY)Buffer + 50,
    (PSTRING)(Fcb + 528),
    *(_WORD *)(Fcb + 528) - *(_WORD *)(Fcb + 544),
    0,
    0,
    1u,
    1u,
    0);
  IoSetShareAccess(*v100, a10, FileObject, (PSHARE_ACCESS)(Fcb + 200));
  ++*(_DWORD *)(Fcb + 228);
  ++*(_DWORD *)(Fcb + 232);
  v50 = FileObject;
  if ( (FileObject->Flags & 8) != 0 )
    ++*(_DWORD *)(Fcb + 236);
  ++v48[68];
  if ( !*(_WORD *)&v50->WriteAccess )
    ++v48[69];
  v68 = 1;
  if ( (v48[50] & 0x400000) != 0 && (*v39 & 0x8000) != 0 )
  {
    Size = 0;
    Buffer = 0;
    FatOpenFileHeader(a2, v50, Fcb);
    if ( CcPreparePinWrite(
           *(PFILE_OBJECT *)(Fcb + 424),
           &FatLargeZero,
           *(_DWORD *)(Fcb + 132),
           0,
           1u,
           (PVOID *)&Size,
           &Buffer) )
    {
      memset(Buffer, 0, *(unsigned int *)(Fcb + 132));
    }
    CcUnpinData((PVOID)Size);
    Size = 0;
    FatCloseFileHeader(a2, Fcb);
  }
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 2;
  if ( a18 )
    *(_DWORD *)(Ccb + 4) |= 0x400u;
  if ( !v60 && !v67 )
    *(_DWORD *)(Ccb + 4) |= 0x800u;
  if ( (*(_BYTE *)(v93 + 2) & 1) != 0 )
    LOBYTE(v49) = 1;
  else
    LOBYTE(v49) = *(_BYTE *)(*(_QWORD *)(a2 + 40) + 64LL);
  if ( (unsigned __int8)FatCheckManageVolumeAccess(v93, *(_QWORD *)(*(_QWORD *)(v93 + 8) + 8LL), v49) )
    *(_DWORD *)(Ccb + 4) |= 0x20000u;
  if ( (v48[50] & 0x400000) != 0 && (v61 || (*(_DWORD *)(*(_QWORD *)v85 + 192LL) & 0x60000) != 0 || (a14 & 0x4000) != 0) )
  {
    v54 = v93;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v93 + 8) + 8LL) + 20LL) |= *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v93 + 8) + 8LL)
                                                                             + 16LL);
    *v39 |= 0x100000u;
    *(_DWORD *)(a2 + 136) = 65537;
    Callback = EfsFileCreateCallback(
                 Fcb,
                 v85[0],
                 v54,
                 *(_DWORD *)(a2 + 136),
                 (v48[50] >> 14) & 1,
                 a2,
                 (__int64)(v48 - 104),
                 Action,
                 Fcb + 144,
                 a2 + 128);
    v56 = *(_DWORD *)(a2 + 68);
    if ( *(_QWORD *)(a2 + 128) )
    {
      *(_DWORD *)(a2 + 68) = v56 | 0x8000;
    }
    else
    {
      *(_DWORD *)(a2 + 68) = v56 & 0xFFFF7FFF;
      *v39 &= ~0x100000u;
      *v39 &= ~0x8000u;
      FatTruncateFileAllocation(a2, Fcb, a11);
      v57 = v84;
      *(_BYTE *)(v84 + 12) &= ~1u;
      *(_DWORD *)(Fcb + 132) = 0;
      *(_BYTE *)(Fcb + 136) = 0;
      *(_BYTE *)(v57 + 12) &= 0x1Bu;
    }
    if ( Callback < 0 )
    {
      *(_DWORD *)a1 = Callback;
      *(_DWORD *)(a2 + 72) = Callback;
      ExRaiseStatus(*(_DWORD *)a1);
    }
  }
  if ( (_BYTE *)LongName.Buffer != v105 )
    ExFreePoolWithTag(LongName.Buffer, 0);
  if ( v65 )
    FatFreeStringBuffer(v86, v51, v52, v53);
  if ( Bcb )
    CcUnpinData(Bcb);
  if ( v75 )
    CcUnpinData(v75);
  if ( v59 )
    ExFreePoolWithTag(Src, 0);
  return a1;
}

```

## disassembly

```asm
0x140029774  mov     r11, rsp
0x140029777  push    rbx
0x140029778  push    rsi
0x140029779  push    rdi
0x14002977a  push    r12
0x14002977c  push    r13
0x14002977e  push    r14
0x140029780  push    r15
0x140029782  sub     rsp, 250h
0x140029789  mov     rax, cs:__security_cookie
0x140029790  xor     rax, rsp
0x140029793  mov     [rsp+288h+var_48], rax
0x14002979b  mov     rax, r9
0x14002979e  mov     [rsp+288h+FileObject], rax
0x1400297a6  mov     [rsp+288h+var_160], r8
0x1400297ae  mov     rsi, rdx
0x1400297b1  mov     r14, rcx
0x1400297b4  mov     [rsp+288h+var_180], rdx
0x1400297bc  mov     [rsp+288h+var_1D0], rax
0x1400297c4  mov     r13, [rsp+288h+arg_20]
0x1400297cc  mov     [rsp+288h+Buffer], r13
0x1400297d4  mov     [rsp+288h+var_108], r13
0x1400297dc  mov     rcx, [rsp+288h+arg_28]
0x1400297e4  mov     qword ptr [rsp+288h+var_1B0], rcx
0x1400297ec  mov     [rsp+288h+var_100], rcx
0x1400297f4  mov     r12, [rsp+288h+arg_30]
0x1400297fc  mov     rbx, [rsp+288h+Name]
0x140029804  mov     [rsp+288h+var_198], rbx
0x14002980c  mov     rax, [rsp+288h+arg_40]
0x140029814  mov     [rsp+288h+var_110], rax
0x14002981c  mov     rax, [rsp+288h+arg_58]
0x140029824  mov     [rsp+288h+var_118], rax
0x14002982c  mov     rdi, [rsp+288h+arg_70]
0x140029834  mov     al, [rsp+288h+arg_78]
0x14002983b  mov     [rsp+288h+var_21D], al
0x14002983f  xorps   xmm0, xmm0
0x140029842  movups  xmmword ptr [r14], xmm0
0x140029846  xor     edx, edx
0x140029848  mov     [r11-188h], rdx
0x14002984f  mov     [r11-200h], rdx
0x140029856  mov     [r11-1E0h], rdx
0x14002985d  mov     [rsp+288h+var_224], dl
0x140029861  mov     [rsp+288h+var_225], dl
0x140029865  mov     [rsp+288h+var_223], dl
0x140029869  mov     [r11-1F8h], rdx
0x140029870  mov     [r11-148h], rdx
0x140029877  mov     [rsp+288h+var_228], dl
0x14002987b  mov     qword ptr [r11-128h], 0C0000h
0x140029886  mov     qword ptr [r11-138h], 180000h
0x140029891  mov     qword ptr [r11-178h], 340000h
0x14002989c  mov     [r11-140h], rdx
0x1400298a3  movups  xmmword ptr [rsp+288h+var_1A8], xmm0
0x1400298ab  mov     [rsp+288h+var_226], dl
0x1400298af  mov     [rsp+288h+var_210], rdx
0x1400298b4  mov     [rsp+288h+var_21E], dl
0x1400298b8  mov     [r11-1E8h], rdx
0x1400298bf  lea     rax, [r11-0F0h]
0x1400298c6  mov     [r11-120h], rax
0x1400298cd  lea     rax, [r11-0A8h]
0x1400298d4  mov     [r11-130h], rax
0x1400298db  lea     rax, [r11-0E0h]
0x1400298e2  mov     [r11-170h], rax
0x1400298e9  mov     word ptr [rsp+288h+var_208], dx
0x1400298f1  cmp     [rsp+288h+arg_80], dl
0x1400298f8  jz      short loc_140029931
0x1400298fa  cmp     [rsp+288h+arg_60], edx
0x140029901  jbe     short loc_140029931
0x140029903  mov     dword ptr [r14], 0C0000022h
0x14002990a  mov     rax, r14
0x14002990d  mov     rcx, [rsp+288h+var_48]
0x140029915  xor     rcx, rsp; StackCookie
0x140029918  call    __security_check_cookie
0x14002991d  add     rsp, 250h
0x140029924  pop     r15
0x140029926  pop     r14
0x140029928  pop     r13
0x14002992a  pop     r12
0x14002992c  pop     rdi
0x14002992d  pop     rsi
0x14002992e  pop     rbx
0x14002992f  retn
0x140029931  mov     r15d, 1
0x140029937  cmp     [rsp+288h+arg_88], dl
0x14002993e  jz      short loc_140029953
0x140029940  test    byte ptr [rsp+288h+arg_68], r15b
0x140029948  jz      short loc_140029953
0x14002994a  mov     dword ptr [r14], 0C0000121h
0x140029951  jmp     short loc_14002990A
0x140029953  mov     [rsp+288h+var_220], dl
0x140029957  mov     [rsp+288h+var_222], dl
0x14002995b  mov     [rsp+288h+var_168], 8
0x140029966  mov     edx, [rcx+80h]
0x14002996c  xor     rdx, [rcx+100h]; DirectoryKey
0x140029973  lea     rcx, [r13+408h]; Cache
0x14002997a  lea     rax, [rsp+288h+var_140]
0x140029982  mov     [rsp+288h+Data], rax; Data
0x140029987  lea     rax, [rsp+288h+var_168]
0x14002998f  mov     [rsp+288h+DataLength], rax; DataLength
0x140029994  lea     rax, [rsp+288h+var_178]
0x14002999c  mov     [rsp+288h+LongName], rax; LongName
0x1400299a1  lea     r9, [rsp+288h+ShortName]; ShortName
0x1400299a9  mov     r8, rbx; Name
0x1400299ac  call    cs:__imp_FsRtlFindInTunnelCache
0x1400299b3  nop     dword ptr [rax+rax+00h]
0x1400299b8  mov     [rsp+288h+var_221], al
0x1400299bc  mov     cl, al
0x1400299be  neg     cl
0x1400299c0  sbb     rdx, rdx
0x1400299c3  lea     rax, [rsp+288h+ShortName]
0x1400299cb  and     rdx, rax
0x1400299ce  lea     rax, [rsp+288h+var_223]
0x1400299d3  mov     [rsp+288h+TargetContext], rax
0x1400299d8  lea     rax, [rsp+288h+var_225]
0x1400299dd  mov     qword ptr [rsp+288h+Action], rax
0x1400299e2  lea     rax, [rsp+288h+var_224]
0x1400299e7  mov     [rsp+288h+Data], rax
0x1400299ec  mov     [rsp+288h+DataLength], rdx
0x1400299f1  lea     rax, [rsp+288h+var_128]
0x1400299f9  mov     [rsp+288h+LongName], rax
0x1400299fe  mov     r9, rbx
0x140029a01  mov     r8, r12
0x140029a04  mov     r12, qword ptr [rsp+288h+var_1B0]
0x140029a0c  mov     rdx, r12
0x140029a0f  mov     rcx, rsi
0x140029a12  call    FatSelectNames
0x140029a17  test    cs:byte_140017D4C, r15b
0x140029a1e  jnz     short loc_140029A35
0x140029a20  xor     edi, edi
0x140029a22  mov     [rsp+288h+var_224], dil
0x140029a27  mov     [rsp+288h+var_225], dil
0x140029a2c  mov     cl, dil
0x140029a2f  mov     [rsp+288h+var_227], cl
0x140029a33  jmp     short loc_140029A99
0x140029a35  mov     cl, [rsp+288h+var_223]
0x140029a39  mov     [rsp+288h+var_227], cl
0x140029a3d  xor     eax, eax
0x140029a3f  test    cl, cl
0x140029a41  jnz     short loc_140029A97
0x140029a43  cmp     [rsp+288h+var_178.Length], ax
0x140029a4b  jz      short loc_140029A97
0x140029a4d  mov     r9, rdi
0x140029a50  lea     r8, [rsp+288h+var_178]
0x140029a58  mov     rdx, r12
0x140029a5b  mov     rcx, rsi
0x140029a5e  call    FatLfnDirentExists
0x140029a63  xor     edi, edi
0x140029a65  test    al, al
0x140029a67  jnz     short loc_140029A91
0x140029a69  mov     [rsp+288h+var_220], r15b
0x140029a6e  mov     cl, r15b
0x140029a71  mov     [rsp+288h+var_227], cl
0x140029a75  lea     rbx, [rsp+288h+var_178]
0x140029a7d  mov     [rsp+288h+var_198], rbx
0x140029a85  mov     [rsp+288h+var_224], dil
0x140029a8a  mov     [rsp+288h+var_225], dil
0x140029a8f  jmp     short loc_140029A99
0x140029a91  mov     cl, [rsp+288h+var_223]
0x140029a95  jmp     short loc_140029A99
0x140029a97  xor     edi, edi
0x140029a99  mov     eax, [r13+0C8h]
0x140029aa0  bt      eax, 16h
0x140029aa4  jnb     loc_140029B4C
0x140029aaa  cmp     [rsp+288h+var_226], dil
0x140029aaf  jz      loc_140029B4C
0x140029ab5  movzx   edx, word ptr [rbx]
0x140029ab8  mov     ecx, 0Ch
0x140029abd  lea     rax, [rcx+rdx]
0x140029ac1  cmp     rax, 208h
0x140029ac7  jbe     short loc_140029AD5
0x140029ac9  mov     dword ptr [r14], 0C0000106h
0x140029ad0  jmp     loc_14002990A
0x140029ad5  lea     rax, [rsp+288h+var_88]
0x140029add  mov     [rsp+288h+var_1A8+8], rax
0x140029ae5  mov     dword ptr [rsp+288h+var_1A8], 400000h
0x140029af0  add     dx, cx
0x140029af3  lea     rcx, [rsp+288h+var_1A8]
0x140029afb  call    FatEnsureStringBufferEnough
0x140029b00  movzx   r8d, word ptr [rbx]; Size
0x140029b04  mov     rdx, [rbx+8]; Src
0x140029b08  mov     rcx, [rsp+288h+var_1A8+8]; void *
0x140029b10  call    memmove
0x140029b15  movzx   eax, word ptr [rbx]
0x140029b18  mov     word ptr [rsp+288h+var_1A8], ax
0x140029b20  mov     dl, r15b
0x140029b23  lea     rcx, [rsp+288h+var_1A8]
0x140029b2b  call    FatAppendPfileExtension
0x140029b30  mov     [rsp+288h+var_222], r15b
0x140029b35  lea     rbx, [rsp+288h+var_1A8]
0x140029b3d  mov     [rsp+288h+var_198], rbx
0x140029b45  mov     cl, r15b
0x140029b48  mov     [rsp+288h+var_227], cl
0x140029b4c  mov     dword ptr [rsp+288h+Size], edi
0x140029b50  mov     r13d, edi
0x140029b53  mov     [rsp+288h+var_1BC], edi
0x140029b5a  mov     [rsp+288h+var_150], rdi
0x140029b62  mov     [rsp+288h+var_158], rdi
0x140029b6a  mov     [rsp+288h+var_21F], dil
0x140029b6f  test    cl, cl
0x140029b71  jz      short loc_140029B96
0x140029b73  movzx   ecx, word ptr [rbx]
0x140029b76  shr     rcx, 1
0x140029b79  add     rcx, 0Ch
0x140029b7d  mov     rax, 4EC4EC4EC4EC4EC5h
0x140029b87  mul     rcx
0x140029b8a  mov     rdi, rdx
0x140029b8d  shr     rdi, 2
0x140029b91  add     edi, r15d
0x140029b94  jmp     short loc_140029B99
0x140029b96  mov     edi, r15d
0x140029b99  mov     [rsp+288h+var_1F0], edi
0x140029ba0  mov     r8d, edi; NumberToSet
0x140029ba3  mov     rdx, r12; int
0x140029ba6  mov     rcx, rsi; int
0x140029ba9  call    FatCreateNewDirent
0x140029bae  mov     ebx, eax
0x140029bb0  mov     [rsp+288h+var_1C0], ebx
0x140029bb7  mov     [rsp+288h+TargetContext], r14
0x140029bbc  mov     byte ptr [rsp+288h+Action], r15b
0x140029bc1  lea     rax, [rsp+288h+var_200]
0x140029bc9  mov     [rsp+288h+DataLength], rax
0x140029bce  lea     rax, [rsp+288h+Bcb]
0x140029bd6  mov     [rsp+288h+LongName], rax
0x140029bdb  mov     r9d, 20h ; ' '
0x140029be1  mov     r8d, ebx
0x140029be4  mov     rdx, r12
0x140029be7  mov     rcx, rsi
0x140029bea  call    FatPrepareWriteDirectoryFile
0x140029bef  mov     r9, [rsp+288h+var_200]
0x140029bf7  mov     [rsp+288h+Src], r9
0x140029bff  mov     [rsp+288h+var_158], r9
0x140029c07  lea     eax, [rdi-1]
0x140029c0a  shl     rax, 5
0x140029c0e  add     rax, rbx
0x140029c11  mov     [rsp+288h+var_F8], rax
0x140029c19  xor     rax, rbx
0x140029c1c  test    rax, 0FFFFFFFFFFFFF000h
0x140029c22  jz      loc_140029CF2
0x140029c28  mov     r8d, ebx
0x140029c2b  and     r8d, 0FFFFF000h
0x140029c32  add     r8d, 1000h
0x140029c39  mov     eax, r8d
0x140029c3c  sub     eax, ebx
0x140029c3e  mov     dword ptr [rsp+288h+Size], eax
0x140029c42  mov     r13d, eax
0x140029c45  shr     r13d, 5
0x140029c49  mov     [rsp+288h+var_1BC], r13d
0x140029c51  mov     [rsp+288h+TargetContext], r14
0x140029c56  mov     byte ptr [rsp+288h+Action], r15b
0x140029c5b  lea     rax, [rsp+288h+var_148]
0x140029c63  mov     [rsp+288h+DataLength], rax
0x140029c68  lea     rax, [rsp+288h+var_1F8]
0x140029c70  mov     [rsp+288h+LongName], rax
0x140029c75  mov     r9d, 20h ; ' '
0x140029c7b  mov     rdx, r12
0x140029c7e  mov     rcx, rsi
0x140029c81  call    FatPrepareWriteDirectoryFile
0x140029c86  mov     rdx, [rsp+288h+Src]
0x140029c8e  mov     [rsp+288h+var_150], rdx
0x140029c96  mov     r12d, edi
0x140029c99  shl     r12, 5
0x140029c9d  mov     r8d, 44746146h; Tag
0x140029ca3  mov     rdx, r12; NumberOfBytes
0x140029ca6  mov     ecx, 411h; PoolType
0x140029cab  call    cs:__imp_ExAllocatePoolWithTag
0x140029cb2  nop     dword ptr [rax+rax+00h]
0x140029cb7  mov     r9, rax
0x140029cba  mov     [rsp+288h+Src], rax
0x140029cc2  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140029cc9  jnz     short loc_140029CE5
0x140029ccb  test    rax, rax
0x140029cce  jz      short loc_140029CE5
0x140029cd0  mov     r8, r12; Size
0x140029cd3  xor     edx, edx; Val
0x140029cd5  mov     rcx, rax; void *
0x140029cd8  call    memset
0x140029cdd  mov     r9, [rsp+288h+Src]
0x140029ce5  mov     [rsp+288h+var_200], r9
0x140029ced  mov     [rsp+288h+var_228], r15b
0x140029cf2  mov     r12d, edi
0x140029cf5  shl     r12, 5
0x140029cf9  lea     r10, [r9-20h]
0x140029cfd  add     r10, r12
0x140029d00  mov     [rsp+288h+var_1B8], r10
0x140029d08  neg     [rsp+288h+var_221]
0x140029d0c  sbb     rcx, rcx
0x140029d0f  lea     rax, [rsp+288h+var_140]
0x140029d17  and     rcx, rax
0x140029d1a  mov     al, [rsp+288h+var_227]
0x140029d1e  neg     al
0x140029d20  sbb     rdx, rdx
0x140029d23  and     rdx, [rsp+288h+var_198]
0x140029d2b  movzx   eax, [rsp+288h+arg_68]
0x140029d33  or      ax, 20h
0x140029d37  mov     [rsp+288h+TargetContext], rcx
0x140029d3c  mov     byte ptr [rsp+288h+Action], r15b
0x140029d41  mov     word ptr [rsp+288h+Data], ax
0x140029d46  mov     [rsp+288h+DataLength], rdx
0x140029d4b  mov     al, [rsp+288h+var_225]
0x140029d4f  mov     byte ptr [rsp+288h+LongName], al
0x140029d53  mov     r9b, [rsp+288h+var_224]
  ... truncated ...
```
