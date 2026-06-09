# NtfsReadRawEncrypted

- ea: `0x1402836cc`
- end: `0x140284f05`
- name: `NtfsReadRawEncrypted`
- size: `6201`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `28`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1401f5890`

## callees

- `0x1400055f0`
- `0x140007ea0`
- `0x1400082b0`
- `0x140009710`
- `0x14000c290`
- `0x14000cb80`
- `0x140015b90`
- `0x140025830`
- `0x14002b680`
- `0x140030418`
- `0x140037db4`
- `0x14003ebc4`
- `0x140059250`
- `0x1400592c0`
- `0x1400592e0`
- `0x1400596c0`
- `0x1400bdc7c`
- `0x1400bdd18`
- `0x1400bdd54`
- `0x1400bddcc`
- `0x1400bde2c`
- `0x1400bde74`
- `0x1400bdebc`
- `0x1400bdf00`
- `0x140160be0`
- `0x140175a80`
- `0x1401c08b4`
- `0x1402836cc`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140284b97`
- `ntoskrnl!IoFreeIrp` at `0x140284ce1`
- `ntoskrnl!IoFreeIrp` at `0x1402bc841`
- `ntoskrnl!IoFreeIrp` at `0x140284b97`
- `ntoskrnl!IoFreeIrp` at `0x140284ce1`
- `ntoskrnl!IoFreeIrp` at `0x1402bc841`
- `ntoskrnl!IoFreeMdl` at `0x140284b80`
- `ntoskrnl!IoFreeMdl` at `0x140284cd2`
- `ntoskrnl!IoFreeMdl` at `0x1402bc831`
- `ntoskrnl!IoFreeMdl` at `0x140284b80`
- `ntoskrnl!IoFreeMdl` at `0x140284cd2`
- `ntoskrnl!IoFreeMdl` at `0x1402bc831`
- `ntoskrnl!MmUnlockPages` at `0x140284b5f`
- `ntoskrnl!MmUnlockPages` at `0x140284cc2`
- `ntoskrnl!MmUnlockPages` at `0x1402bc820`
- `ntoskrnl!MmUnlockPages` at `0x140284b5f`
- `ntoskrnl!MmUnlockPages` at `0x140284cc2`
- `ntoskrnl!MmUnlockPages` at `0x1402bc820`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140284780`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140284780`
- `ntoskrnl!ProbeForWrite` at `0x140283b1f`
- `ntoskrnl!ProbeForWrite` at `0x140283b1f`
- `ntoskrnl!ProbeForRead` at `0x140283b03`
- `ntoskrnl!ProbeForRead` at `0x140283b03`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140283ba0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140283ba0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140284d0a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc869`
- `ntoskrnl!ExReleaseResourceLite` at `0x140284d0a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc869`
- `ntoskrnl!CcFlushCache` at `0x140284401`
- `ntoskrnl!CcFlushCache` at `0x140284401`

## pseudocode

```c
__int64 __fastcall NtfsReadRawEncrypted(__int64 a1, IRP *a2)
{
  KPROCESSOR_MODE RequestorMode; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned __int64 FileObject; // rax
  __int64 v7; // rcx
  __int64 v8; // r13
  __int64 v9; // rsi
  int v10; // eax
  __int64 v11; // r15
  int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // r8d
  __int64 v16; // rdx
  unsigned __int16 v17; // r8
  unsigned int Options; // esi
  union _LARGE_INTEGER *v19; // r15
  unsigned int v20; // esi
  __int64 ULong64FromUser; // rdi
  __int64 v22; // rbx
  __int64 v23; // rcx
  unsigned int v24; // r8d
  __int64 v25; // r13
  __int64 v26; // r11
  int v27; // r10d
  signed __int64 v28; // rdx
  __int16 v29; // cx
  int v30; // eax
  char v31; // dl
  ULONG i; // eax
  unsigned int v33; // eax
  ULONG_PTR v34; // rcx
  IRP *v35; // rbx
  __int16 v36; // ax
  _WORD *v37; // rcx
  union _LARGE_INTEGER v38; // r8
  __int64 v39; // rbx
  char v40; // di
  ULONG k; // eax
  __int64 v42; // r8
  char v43; // dl
  char v44; // r9
  _WORD *v45; // rcx
  __int64 v46; // r8
  int v47; // ecx
  unsigned int v48; // r8d
  __int64 v49; // r8
  unsigned int v50; // edi
  _DWORD *v51; // rbx
  struct _IO_STATUS_BLOCK *v52; // rdi
  __int64 v53; // rbx
  union _LARGE_INTEGER *v54; // rcx
  unsigned int ULongFromUser; // eax
  int v56; // eax
  __int64 v57; // r8
  __int16 v58; // cx
  char v59; // al
  __int64 v60; // rdi
  __int64 v61; // r9
  __int64 v62; // rax
  __int64 v63; // rbx
  char v64; // bl
  ULONG j; // eax
  LONGLONG v66; // rdx
  ULONG v67; // r9d
  PIRP v68; // rax
  ULONG v69; // ebx
  PIRP v70; // rbx
  unsigned int Information; // ebx
  LONGLONG v72; // r8
  union _LARGE_INTEGER v73; // rcx
  __int64 v74; // r9
  union _LARGE_INTEGER v75; // r8
  DWORD v76; // r10d
  ULONG_PTR v77; // r8
  unsigned int v78; // ecx
  union _LARGE_INTEGER v79; // rcx
  int v80; // eax
  PIRP v81; // rbx
  struct _MDL *MdlAddress; // rcx
  int v83; // ecx
  PIRP v84; // rdi
  struct _MDL *v85; // rcx
  unsigned int StartingOffset; // [rsp+20h] [rbp-208h]
  unsigned int v87; // [rsp+50h] [rbp-1D8h]
  char v88; // [rsp+71h] [rbp-1B7h]
  char v89; // [rsp+72h] [rbp-1B6h]
  char v90; // [rsp+72h] [rbp-1B6h]
  char v91; // [rsp+73h] [rbp-1B5h]
  char v92; // [rsp+74h] [rbp-1B4h]
  char v93; // [rsp+75h] [rbp-1B3h]
  char IsRangeAllocated; // [rsp+76h] [rbp-1B2h]
  union _LARGE_INTEGER FileOffset; // [rsp+78h] [rbp-1B0h] BYREF
  int v96; // [rsp+80h] [rbp-1A8h]
  unsigned int v97; // [rsp+84h] [rbp-1A4h]
  int v98; // [rsp+88h] [rbp-1A0h]
  ULONG v99[2]; // [rsp+90h] [rbp-198h]
  unsigned int Size; // [rsp+98h] [rbp-190h]
  unsigned int Size_4; // [rsp+9Ch] [rbp-18Ch]
  DWORD v102; // [rsp+A0h] [rbp-188h]
  unsigned int Length; // [rsp+A4h] [rbp-184h]
  ULONG Length_4; // [rsp+A8h] [rbp-180h]
  DWORD v105; // [rsp+ACh] [rbp-17Ch]
  unsigned int v106; // [rsp+B0h] [rbp-178h]
  __int64 v107; // [rsp+B8h] [rbp-170h]
  ULONG v108[2]; // [rsp+C0h] [rbp-168h]
  __int64 v109; // [rsp+C8h] [rbp-160h]
  int v110; // [rsp+D0h] [rbp-158h]
  unsigned int v111; // [rsp+D4h] [rbp-154h]
  int v112; // [rsp+D8h] [rbp-150h]
  unsigned int v113; // [rsp+DCh] [rbp-14Ch]
  char v114; // [rsp+E0h] [rbp-148h]
  struct _IO_STATUS_BLOCK *v115; // [rsp+E8h] [rbp-140h]
  unsigned __int64 v116; // [rsp+F0h] [rbp-138h]
  __int64 v117; // [rsp+F8h] [rbp-130h]
  PIRP Irp; // [rsp+100h] [rbp-128h]
  volatile void *Address; // [rsp+108h] [rbp-120h]
  signed __int64 v120; // [rsp+110h] [rbp-118h]
  __int64 v121; // [rsp+118h] [rbp-110h]
  __int64 v122; // [rsp+120h] [rbp-108h]
  __int64 QuadPart; // [rsp+128h] [rbp-100h]
  DWORD v124; // [rsp+130h] [rbp-F8h]
  int v125; // [rsp+134h] [rbp-F4h]
  signed __int64 v126; // [rsp+138h] [rbp-F0h]
  __int64 v127; // [rsp+140h] [rbp-E8h]
  signed __int64 v128; // [rsp+148h] [rbp-E0h]
  __int64 v129; // [rsp+150h] [rbp-D8h]
  __int64 v130; // [rsp+158h] [rbp-D0h] BYREF
  __int64 v131; // [rsp+160h] [rbp-C8h]
  _OWORD v132[6]; // [rsp+170h] [rbp-B8h] BYREF
  _DWORD Src[2]; // [rsp+1D0h] [rbp-58h] BYREF
  __int128 v134; // [rsp+1D8h] [rbp-50h]
  __int64 v135; // [rsp+1E8h] [rbp-40h]

  v115 = (struct _IO_STATUS_BLOCK *)a2;
  v107 = a1;
  RequestorMode = 0;
  FileOffset.QuadPart = 0;
  v127 = 0;
  v112 = 0;
  memset(v132, 0, 0x5Cu);
  *(_DWORD *)(a1 + 12) |= 1u;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = (unsigned __int64)CurrentStackLocation->FileObject;
  v116 = FileObject;
  v7 = *(_QWORD *)(FileObject + 24);
  QuadPart = v7;
  if ( v7 )
  {
    v8 = *(_QWORD *)(FileObject + 32);
    v9 = *(_QWORD *)(v7 + 192);
    v109 = v9;
    v10 = *(_DWORD *)(v9 + 4);
    if ( (v10 & 1) == 0 && (!v8 || *(_BYTE *)(v8 + 88) != 4 || (v10 & 2) == 0) )
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
    if ( !v8 )
      goto LABEL_10;
    v11 = *(_QWORD *)(v7 + 184);
    v12 = *(unsigned __int8 *)(v8 + 88);
  }
  else
  {
    v9 = 0;
    v109 = 0;
    v8 = 0;
    v11 = 0;
    v12 = 1;
  }
  v129 = v11;
  v122 = v11;
  if ( v12 != 2 )
  {
LABEL_10:
    v13 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x124355u);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073741811, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1196886;
LABEL_14:
    NtfsStatusTraceAndDebugInternal(0, v13, v14);
    return v13;
  }
  if ( !_bittest16((const signed __int16 *)(v7 + 460), 0xEu) )
  {
    v13 = -1073740633;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC00004A7, 0x124360u);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073740633, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1196897;
    goto LABEL_14;
  }
  if ( (*(_WORD *)(v8 + 104) & 9) == 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      v16 = *(_QWORD *)(v9 + 248);
      v17 = *(_WORD *)(v16 + 6);
      if ( v17 > 0x40u || (v17 & 1) != 0 )
        v17 = 0;
      v87 = *(unsigned __int16 *)(v8 + 16) >> 1;
      McTemplateU0ppwwpiwd_EtwWriteTransfer(
        v87,
        (const EVENT_DESCRIPTOR *)fsctrl_c17258,
        KeGetCurrentThread(),
        v9,
        *(unsigned __int16 *)(v9 + 7872) >> 1,
        *(_QWORD *)(v9 + 7880),
        v17 >> 1,
        v16 + 32,
        v11,
        *(_QWORD *)(v11 + 8),
        v87,
        *(_QWORD *)(v8 + 24),
        *(unsigned __int16 *)(v8 + 104));
    }
    v13 = -1073741790;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC0000022, 0x124379u);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073741790, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1196922;
    goto LABEL_14;
  }
  if ( (*(_DWORD *)(v9 + 24) & 0x40000) != 0 )
  {
    v13 = -1073740646;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC000049A, 0x124383u);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073740646, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1196932;
    goto LABEL_14;
  }
  if ( (*(_DWORD *)(v7 + 512) & 0x1000000) != 0 )
  {
    v13 = -1073741816;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC0000008, 0x12438Cu);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073741816, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1196941;
    goto LABEL_14;
  }
  Address = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = Options;
  v19 = (union _LARGE_INTEGER *)NtfsMapUserBuffer((__int64)a2, 16);
  if ( !a2->MdlAddress )
    RequestorMode = a2->RequestorMode;
  if ( Options < 0x10 )
    goto LABEL_291;
  v117 = 0;
  Size_4 = 0;
  v108[0] = 0;
  Irp = 0;
  v102 = 0;
  v105 = 0;
  v20 = 0;
  v88 = 0;
  v91 = 0;
  IsRangeAllocated = 1;
  v93 = 0;
  v92 = 0;
  Size = CurrentStackLocation->Parameters.Read.Length;
  if ( Size < 0x30 )
  {
LABEL_291:
    v20 = -1073741789;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC0000023, 0x1243A3u);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073741789, a2 != 0, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000023, 0x1243A4u);
    return v20;
  }
  if ( a2->RequestorMode )
  {
    ProbeForRead(Address, Length, 1u);
    ProbeForWrite(v19, Size, 1u);
  }
  if ( RequestorMode )
    ULong64FromUser = RtlReadULong64FromUser(Address);
  else
    ULong64FromUser = *(_QWORD *)Address;
  v127 = ULong64FromUser;
  if ( RequestorMode )
    LODWORD(v22) = RtlReadULongFromUser((unsigned int *)Address + 2);
  else
    LODWORD(v22) = *((_DWORD *)Address + 2);
  v112 = v22;
  if ( RequestorMode )
    RtlSetUserMemory(v19, 0, Size);
  else
    RtlSetVolatileMemory(v19, 0, Size);
  v23 = *(_QWORD *)(v122 + 328);
  if ( !v23
    || (ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v23 + 136), 1u),
        v93 = 1,
        (*(_DWORD *)(*(_QWORD *)(v122 + 328) + 4LL) & 1) == 0)
    && !TxfIsCurrentHandleInTransaction(a1, v8) )
  {
    *(_DWORD *)(a1 + 4) |= 0x10000u;
    v25 = QuadPart;
    NtfsAcquireFcbWithPaging(a1, *(_QWORD *)(QuadPart + 184), QuadPart, 0);
    if ( ULong64FromUser >= *(_QWORD *)(QuadPart + 32) || ULong64FromUser >= *(_QWORD *)(QuadPart + 24) )
    {
      v20 = -1073741807;
      goto LABEL_275;
    }
    if ( ULong64FromUser < 0 || !(_DWORD)v22 )
    {
      v20 = -1073740631;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_275;
      v24 = 1197105;
      goto LABEL_62;
    }
    v26 = v109;
    v27 = *(_DWORD *)(v109 + 364);
    v98 = v27;
    Length = v27 - 1;
    v28 = -v27 & (v27 - 1 + *(_QWORD *)(QuadPart + 40));
    v128 = v28;
    if ( ULong64FromUser >= v28 )
    {
      v29 = *(_WORD *)(QuadPart + 460);
      if ( (_BYTE)v29 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC0000002, 0x124450u);
      }
      else
      {
        if ( v29 >= 0 || ((*(_DWORD *)(QuadPart + 452) - 1) & (unsigned int)ULong64FromUser) != 0 )
          v30 = -v27 & (v22 + v27 - 1);
        else
          v30 = -*(_DWORD *)(QuadPart + 452) & (v22 + *(_DWORD *)(QuadPart + 452) - 1);
        v31 = 0;
        for ( i = v30 - 1; ; i >>= 1 )
        {
          Length_4 = i;
          if ( !i )
            break;
          ++v31;
        }
        v22 = (unsigned int)(1 << v31);
        v112 = 1 << v31;
        v134 = 0;
        v135 = 0;
        Src[0] = ULong64FromUser;
        Src[1] = HIDWORD(v127);
        LODWORD(v134) = 48;
        v33 = 1 << v31;
        if ( v22 >= *(_QWORD *)(QuadPart + 32) - ULong64FromUser )
          v33 = *(_DWORD *)(QuadPart + 32) - ULong64FromUser;
        *(_QWORD *)((char *)&v134 + 4) = v33;
        WORD6(v134) = 0;
        BYTE14(v134) = v31;
        HIBYTE(v134) = v31;
        LOBYTE(v135) = *(_BYTE *)(v109 + 488);
        BYTE1(v135) = 1;
        WORD1(v135) = 1;
        if ( RequestorMode )
          RtlCopyToUser(v19, Src, 0x20u);
        else
          RtlCopyVolatileMemory(v19, Src, 0x20u);
        if ( RequestorMode )
          RtlWriteULongToUser(&v19[4], ExtendedEncryptedDataInfoSignature);
        else
          v19[4].LowPart = ExtendedEncryptedDataInfoSignature;
        if ( RequestorMode )
          RtlWriteULongToUser(&v19[4].HighPart, 16);
        else
          v19[4].HighPart = 16;
        if ( *(__int16 *)(v25 + 460) < 0 )
        {
          LODWORD(v22) = ((unsigned int)ULong64FromUser & (*(_DWORD *)(v25 + 452) - 1)) != 0 ? v22 : 0;
          v112 = v22;
          if ( RequestorMode )
            RtlWriteULongToUser(&v19[5], 1);
          else
            v19[5].LowPart = 1;
          if ( RequestorMode )
            RtlWriteUCharToUser((_BYTE *)&v19[3] + 1, 2);
          else
            BYTE1(v19[3].LowPart) = 2;
        }
        if ( (int)v22 + 48 > Size && NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC0000023, 0x1244D8u);
        if ( RequestorMode )
          RtlWriteULongToUser(&v19[3].HighPart, v22);
        else
          v19[3].HighPart = v22;
      }
      v34 = (unsigned int)(v22 + 48);
      v35 = (IRP *)v115;
      v115[3].Information = v34;
      v20 = 0;
      goto LABEL_276;
    }
    if ( ULong64FromUser + (unsigned int)v22 > v28 )
    {
      LODWORD(v22) = v28 - ULong64FromUser;
      v112 = v28 - ULong64FromUser;
      v92 = 1;
    }
    v36 = *(_WORD *)(QuadPart + 460);
    if ( (v36 & 0x80FF) != 0 )
    {
      if ( (_BYTE)v36 )
      {
        v20 = -1073741822;
        if ( NtfsStatusDebugFlags )
        {
          v48 = 1197537;
          goto LABEL_269;
        }
LABEL_270:
        v106 = v20;
LABEL_271:
        v35 = (IRP *)v115;
        goto LABEL_276;
      }
      v91 = 1;
      v44 = *(_BYTE *)(v109 + 488) + *(_BYTE *)(QuadPart + 462);
      v89 = v44;
      v45 = (_WORD *)&v19[2].QuadPart + 2;
      if ( RequestorMode )
      {
        RtlWriteUShortToUser(v45, 0);
        v44 = v89;
        v27 = v98;
        v26 = v109;
      }
      else
      {
        *v45 = 0;
      }
      v46 = ULong64FromUser & -*(_DWORD *)(v26 + 364);
      FileOffset.QuadPart = v46;
      *(_QWORD *)v99 = -*(_DWORD *)(v26 + 364)
                     & (unsigned int)(ULong64FromUser + *(_DWORD *)(v26 + 364) + v22 - v46 - 1);
      v96 = v99[0];
      v47 = *(_DWORD *)(v25 + 452);
      v117 = ULong64FromUser & -v47;
      Size_4 = -v47 & (ULong64FromUser + v47 + v22 - v117 - 1);
      v97 = Size_4 >> v44;
      if ( !(unsigned __int16)(Size_4 >> v44) )
      {
        v20 = -1073740631;
        if ( NtfsStatusDebugFlags )
        {
          v48 = 1197444;
          goto LABEL_269;
        }
        goto LABEL_270;
      }
      if ( (unsigned __int16)(Size_4 >> v44) <= 1u )
      {
        if ( v92 )
        {
          v111 = (-v27 & (v27 + (_DWORD)v19 + 31)) - (_DWORD)v19;
          if ( v111 + Size_4 > Size )
          {
            v46 = ULong64FromUser & 0x7FFFFFFFFFFF0000LL;
            FileOffset.QuadPart = ULong64FromUser & 0xFFFFFFFFFFFF0000uLL;
            v39 = ((_DWORD)ULong64FromUser + (_DWORD)v22 - (ULong64FromUser & 0xFFFF0000) + 0xFFFF) & 0xFFFF0000;
            *(_QWORD *)v99 = v39;
            v96 = v39;
          }
          else
          {
            FileOffset.QuadPart = v117;
            LODWORD(v39) = Size_4;
            *(_QWORD *)v99 = Size_4;
            v96 = Size_4;
            v46 = v117;
          }
        }
        else
        {
          LODWORD(v39) = v99[0];
        }
      }
      else
      {
        FileOffset.QuadPart = v117;
        LODWORD(v39) = Size_4;
        *(_QWORD *)v99 = Size_4;
        v96 = Size_4;
        v46 = v117;
      }
      v49 = (unsigned int)v39 + v46;
      if ( v49 >= *(_QWORD *)(v25 + 32) )
        v49 = *(_QWORD *)(v25 + 32);
      v121 = v49;
      v120 = -*(_DWORD *)(v26 + 364) & (unsigned __int64)(v49 + *(_DWORD *)(v26 + 364) - 1);
      v126 = v120;
      if ( RequestorMode )
      {
        RtlWriteUCharToUser((_BYTE *)&v19[2].QuadPart + 6, v44);
        v44 = v89;
      }
      else
      {
        BYTE6(v19[2].QuadPart) = v44;
      }
      if ( !RequestorMode )
      {
        HIBYTE(v19[2].QuadPart) = v44;
LABEL_146:
        v50 = (-v98 & (Length + (_DWORD)v19 + 4 * (unsigned __int16)v97 + 44)) - (_DWORD)v19;
        v113 = v50;
        v111 = v50;
        if ( v50 > Size || !v91 && (v50 + (unsigned int)v39 < v50 || v50 + (unsigned int)v39 > Size) )
        {
          v20 = -1073741789;
          if ( NtfsStatusDebugFlags )
          {
            v48 = 1197573;
            goto LABEL_269;
          }
          goto LABEL_270;
        }
        v51 = (_DWORD *)v19 + (unsigned __int16)v97;
        if ( RequestorMode )
          RtlWriteULongToUser(v51 + 7, ExtendedEncryptedDataInfoSignature);
        else
          v51[7] = ExtendedEncryptedDataInfoSignature;
        if ( RequestorMode )
          RtlWriteULongToUser(v51 + 8, 16);
        else
          v51[8] = 16;
        if ( *(__int16 *)(v25 + 460) < 0 )
        {
          if ( RequestorMode )
            RtlWriteULongToUser(v51 + 9, 1);
          else
            v51[9] = 1;
        }
        if ( RequestorMode )
          RtlWriteULongToUser(&v19[1], v50);
        else
          v19[1].LowPart = v50;
        if ( RequestorMode )
          RtlWriteUShortToUser((_WORD *)&v19[3] + 1, v97);
        else
          HIWORD(v19[3].u.LowPart) = v97;
        if ( (*(_DWORD *)(v25 + 512) & 0x10000) != 0 )
        {
          v20 = -1073741202;
          if ( NtfsStatusDebugFlags )
          {
            v48 = 1197609;
            goto LABEL_269;
          }
          goto LABEL_270;
        }
        v52 = v115;
        CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(v116 + 40), &FileOffset, v99[0], v115 + 3);
        NtfsNormalizeAndCleanupTransaction(a1, (NTSTATUS *)&v52[3].0);
        QuadPart = FileOffset.QuadPart;
        if ( RequestorMode )
          RtlWriteULong64ToUser(v19, FileOffset.QuadPart);
        else
          *v19 = FileOffset;
        v53 = v109;
        v54 = v19 + 3;
        if ( RequestorMode )
          RtlWriteUCharToUser(v54, *(_BYTE *)(v109 + 488));
        else
          LOBYTE(v54->LowPart) = *(_BYTE *)(v109 + 488);
        if ( RequestorMode )
          RtlWriteUCharToUser((_BYTE *)&v19[3] + 1, 1);
        else
          BYTE1(v19[3].LowPart) = 1;
        if ( !*(_QWORD *)(a1 + 208) )
          NtfsInitializeIoContext(a1, v132, 0);
        if ( RequestorMode )
          ULongFromUser = RtlReadULongFromUser((unsigned int *)&v19[1]);
        else
          ULongFromUser = v19[1].LowPart;
        v52[3].Information = ULongFromUser;
        v56 = 0;
        v57 = FileOffset.QuadPart;
        while ( 1 )
        {
          v98 = v56;
          v58 = v97;
          if ( (unsigned __int16)v56 >= (unsigned __int16)v97 )
          {
            v83 = v121 - QuadPart;
            if ( RequestorMode )
              RtlWriteULongToUser(&v19[1].HighPart, v83);
            else
              v19[1].HighPart = v83;
            if ( RequestorMode )
              RtlWriteULongToUser(&v19[2], v102);
            else
              v19[2].LowPart = v102;
            goto LABEL_271;
          }
          v90 = 0;
          Address = (char *)v19 + v113;
          v59 = v91;
          if ( v91 )
          {
            v60 = v57 >> *(_BYTE *)(v53 + 488);
            v61 = v57 + *(unsigned int *)(v25 + 452);
            v62 = v61;
            if ( v120 < v61 )
              v62 = v120;
            v63 = (v62 + *(unsigned int *)(v53 + 480)) >> *(_BYTE *)(v53 + 488);
            v130 = 0;
            if ( v120 < v61 )
              LODWORD(v61) = v120;
            *(_QWORD *)v108 = (unsigned int)(v61 - v57);
            v110 = v61 - v57;
            NtfsPreloadAllocationInternal(a1, v25, 0, v60, v63 - 1, 0);
            IsRangeAllocated = NtfsIsRangeAllocated(v25, v60, v63, 0, &v130);
            v114 = IsRangeAllocated;
            v57 = FileOffset.QuadPart;
            v52 = v115;
            v53 = v109;
            v58 = v97;
            v59 = v91;
          }
          if ( IsRangeAllocated )
          {
            if ( v59 )
            {
              if ( v58 == 1 && (v57 != v117 || v99[0] != Size_4) )
              {
                v64 = 0;
                for ( j = v99[0] - 1; ; j >>= 1 )
                {
                  Length_4 = j;
                  if ( !j )
                    break;
                  ++v64;
                }
                v116 = (unsigned int)(1 << v64);
                *(_QWORD *)v99 = v116;
                v96 = 1 << v64;
                *(_QWORD *)v108 = v116;
                v110 = 1 << v64;
                if ( RequestorMode )
                  RtlWriteUCharToUser((_BYTE *)&v19[2].QuadPart + 6, v64);
                else
                  BYTE6(v19[2].QuadPart) = v64;
                if ( RequestorMode )
                  RtlWriteUCharToUser((_BYTE *)&v19[2].QuadPart + 7, v64);
                else
                  HIBYTE(v19[2].QuadPart) = v64;
                v57 = FileOffset.QuadPart;
                v66 = FileOffset.QuadPart + (unsigned int)v116;
                if ( v66 >= *(_QWORD *)(v25 + 32) )
                  v66 = *(_QWORD *)(v25 + 32);
                v121 = (unsigned int)v66;
                v53 = v109;
                v120 = -*(_DWORD *)(v109 + 364) & (unsigned __int64)(v66 + *(_DWORD *)(v109 + 364) - 1);
                v126 = v120;
              }
              v67 = v108[0];
              if ( v57 + v108[0] > v128 )
              {
                *(_QWORD *)v108 = (unsigned int)(v128 - v57);
                v110 = v128 - v57;
                v67 = v128 - v57;
              }
              if ( v113 + v67 < v113 || v113 + v67 > Size )
              {
                v20 = -1073741789;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_270;
                v48 = 1197802;
                goto LABEL_269;
              }
            }
            else
            {
              v67 = v108[0];
            }
            v68 = IoBuildAsynchronousFsdRequest(
                    3u,
                    *(PDEVICE_OBJECT *)(*(_QWORD *)(v53 + 248) + 8LL),
                    (PVOID)Address,
                    v67,
                    &FileOffset,
                    0);
            Irp = v68;
            if ( !v68 )
            {
              v20 = -1073741670;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_270;
              v48 = 1197823;
LABEL_269:
              NtfsStatusTraceAndDebugInternal(0, v20, v48);
              goto LABEL_270;
            }
            --v68->CurrentLocation;
            --v68->Tail.Overlay.CurrentStackLocation;
            v68->Tail.Overlay.CurrentStackLocation->DeviceObject = *(PDEVICE_OBJECT *)(*(_QWORD *)(v53 + 248) + 8LL);
            v68->UserBuffer = (PVOID)Address;
            v69 = v108[0];
            NtfsLockUserBuffer(a1, v68, IoWriteAccess, v108[0]);
            v88 = 1;
            *(_BYTE *)(a1 + 32) = 3;
            StartingOffset = v69;
            v70 = Irp;
            NtfsNonCachedIo(a1, Irp, v25, FileOffset.QuadPart, StartingOffset, 2);
            Information = v70->IoStatus.Information;
            v52[3].Information += Information;
            Length = Information;
            v116 = (unsigned __int64)&v19[3].QuadPart + 4 * (unsigned __int16)v98 + 4;
            if ( RequestorMode )
              RtlWriteULongToUser(&v19[3].HighPart + (unsigned __int16)v98, Information);
            else
              *(&v19[3].HighPart + (unsigned __int16)v98) = Information;
            v113 += Information;
            v111 = v113;
          }
          else
          {
            Information = *(_DWORD *)(v25 + 452);
            *(_QWORD *)v108 = Information;
            v110 = Information;
            v90 = 1;
            if ( v58 == 1 && (v57 != v117 || v99[0] != Size_4) )
            {
              FileOffset.QuadPart = v117;
              LODWORD(QuadPart) = v117;
              if ( RequestorMode )
                RtlWriteULong64ToUser(v19, v117);
              else
                v19->QuadPart = v117;
              *(_QWORD *)v99 = Size_4;
              v96 = Size_4;
              v72 = FileOffset.QuadPart + Size_4;
              if ( v72 >= *(_QWORD *)(v25 + 32) )
                v72 = *(_QWORD *)(v25 + 32);
              v121 = (unsigned int)v72;
              v120 = -*(_DWORD *)(v109 + 364) & (unsigned __int64)(v72 + *(_DWORD *)(v109 + 364) - 1);
              v126 = v120;
            }
            Length = 0;
            v116 = (unsigned __int64)&v19[3].QuadPart + 4 * (unsigned __int16)v98 + 4;
            if ( RequestorMode )
              RtlWriteULongToUser(&v19[3].HighPart + (unsigned __int16)v98, 0);
            else
              *(&v19[3].HighPart + (unsigned __int16)v98) = 0;
          }
          v73 = *(union _LARGE_INTEGER *)(v25 + 32);
          v74 = Information;
          v131 = Information;
          v75 = FileOffset;
          if ( Information + FileOffset.QuadPart <= v73.QuadPart )
          {
            v105 += Information;
            v124 = v105;
          }
          else
          {
            v76 = v105;
            if ( FileOffset.QuadPart < v73.QuadPart )
            {
              v76 = v73.LowPart - FileOffset.LowPart + v105;
              v105 = v76;
              v124 = v76;
            }
            if ( (*(_WORD *)(v25 + 460) & 0x80FF) == 0 )
            {
              v77 = v52[3].Information - Length;
              v52[3].Information = v77;
              v78 = -*(_DWORD *)(v109 + 364) & (v76 + *(_DWORD *)(v109 + 364) - 1);
              v52[3].Information = v77 + v78;
              if ( RequestorMode )
              {
                RtlWriteULongToUser((_DWORD *)v116, v78);
                v74 = v131;
              }
              else
              {
                *(_DWORD *)v116 = v78;
              }
              v75 = FileOffset;
            }
          }
          v79 = *(union _LARGE_INTEGER *)(v25 + 40);
          if ( v74 + v75.QuadPart <= v79.QuadPart )
          {
            v102 += Information;
            v125 = v102;
          }
          else if ( v79.QuadPart > v75.QuadPart )
          {
            if ( (_WORD)v97 == 1 && !v90 )
            {
              v80 = ((v79.LowPart + 511) & 0xFFFFFE00) - v75.LowPart;
              if ( v80 > 0 && v80 < Information )
              {
                memset((char *)Address + v80, 0, Information - v80);
                v75 = FileOffset;
              }
            }
            v102 += *(_DWORD *)(v25 + 40) - v75.LowPart;
            v125 = v102;
          }
          v57 = v108[0] + v75.QuadPart;
          FileOffset.QuadPart = v57;
          v81 = Irp;
          if ( Irp )
          {
            MdlAddress = Irp->MdlAddress;
            if ( MdlAddress )
            {
              if ( v88 )
              {
                MmUnlockPages(MdlAddress);
                v88 = 0;
                *(_DWORD *)(a1 + 12) &= ~0x40000u;
              }
              IoFreeMdl(v81->MdlAddress);
              v81->MdlAddress = 0;
            }
            IoFreeIrp(v81);
            Irp = 0;
            v57 = FileOffset.QuadPart;
          }
          HIWORD(v56) = HIWORD(v98);
          LOWORD(v56) = v98 + 1;
          v53 = v109;
        }
      }
      v43 = v44;
    }
    else
    {
      v37 = (_WORD *)&v19[2].QuadPart + 2;
      if ( RequestorMode )
      {
        RtlWriteUShortToUser(v37, 0);
        v26 = v109;
        v28 = v128;
      }
      else
      {
        *v37 = 0;
      }
      v38.QuadPart = ULong64FromUser & -*(_DWORD *)(v26 + 364);
      FileOffset = v38;
      v39 = -*(_DWORD *)(v26 + 364) & (unsigned int)(*(_DWORD *)(v26 + 364) + ULong64FromUser - v38.LowPart + v22 - 1);
      *(_QWORD *)v99 = v39;
      v96 = v39;
      v40 = 0;
      for ( k = v39 - 1; ; k >>= 1 )
      {
        Length_4 = k;
        if ( !k )
          break;
        ++v40;
      }
      if ( !v92 )
      {
        LODWORD(v39) = 1 << v40;
        *(_QWORD *)v99 = (unsigned int)(1 << v40);
        v96 = 1 << v40;
        if ( v38.QuadPart + *(_QWORD *)v99 > v28 )
        {
          LODWORD(v39) = v28 - v38.LowPart;
          *(_QWORD *)v99 = (unsigned int)(v28 - v38.LowPart);
          v96 = v28 - v38.LowPart;
        }
      }
      LOWORD(v97) = 1;
      *(_QWORD *)v108 = (unsigned int)v39;
      v110 = v39;
      v42 = (1LL << v40) + v38.QuadPart;
      if ( v42 >= *(_QWORD *)(v25 + 32) )
        v42 = *(_QWORD *)(v25 + 32);
      v121 = v42;
      v120 = -*(_DWORD *)(v26 + 364) & (unsigned __int64)(v42 + *(_DWORD *)(v26 + 364) - 1);
      v126 = v120;
      if ( RequestorMode )
        RtlWriteUCharToUser((_BYTE *)&v19[2].QuadPart + 6, v40);
      else
        BYTE6(v19[2].QuadPart) = v40;
      if ( !RequestorMode )
      {
        HIBYTE(v19[2].QuadPart) = v40;
        goto LABEL_146;
      }
      v43 = v40;
    }
    RtlWriteUCharToUser((_BYTE *)&v19[2].QuadPart + 7, v43);
    goto LABEL_146;
  }
  v20 = -1072103362;
  if ( NtfsStatusDebugFlags )
  {
    v24 = 1197057;
LABEL_62:
    NtfsStatusTraceAndDebugInternal(0, v20, v24);
  }
LABEL_275:
  v35 = (IRP *)v115;
LABEL_276:
  NtfsFreeIoContext(a1);
  v84 = Irp;
  if ( Irp )
  {
    v85 = Irp->MdlAddress;
    if ( v85 )
    {
      if ( v88 )
        MmUnlockPages(v85);
      IoFreeMdl(v84->MdlAddress);
    }
    IoFreeIrp(v84);
  }
  if ( v93 )
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v122 + 328) + 136LL));
  if ( NtfsStatusDebugFlags && v20 && v20 - 298 > 1 && v20 + 2147483643 > 1 && v20 != -1073741807 )
    NtfsStatusTraceAndDebugInternal(a1, v20, 0x124844u);
  NtfsExtendedCompleteRequestInternal(a1, v35, v20, v35 != 0, (v20 & 0x80000000) == 0);
  return v20;
}

```

## disassembly

```asm
0x1402836cc  mov     r11, rsp
0x1402836cf  mov     [r11+18h], rbx
0x1402836d3  mov     [r11+20h], rsi
0x1402836d7  push    rdi
0x1402836d8  push    r12
0x1402836da  push    r13
0x1402836dc  push    r14
0x1402836de  push    r15
0x1402836e0  sub     rsp, 200h
0x1402836e7  mov     rax, cs:__security_cookie
0x1402836ee  xor     rax, rsp
0x1402836f1  mov     [rsp+228h+var_38], rax
0x1402836f9  mov     rdi, rdx
0x1402836fc  mov     [rsp+228h+var_140], rdx
0x140283704  mov     r14, rcx
0x140283707  mov     [rsp+228h+var_170], rcx
0x14028370f  xor     r12d, r12d
0x140283712  mov     qword ptr [rsp+228h+FileOffset], r12
0x140283717  mov     [r11-0E8h], r12
0x14028371e  mov     [r11-150h], r12d
0x140283725  xor     eax, eax
0x140283727  mov     [rsp+228h+var_B4], eax
0x14028372e  xor     edx, edx; Val
0x140283730  lea     r8d, [r12+5Ch]; Size
0x140283735  lea     rcx, [r11-0B8h]; void *
0x14028373c  call    memset
0x140283741  lea     r10d, [r12+1]
0x140283746  or      [r14+0Ch], r10d
0x14028374a  mov     rbx, [rdi+0B8h]
0x140283751  mov     rax, [rbx+30h]
0x140283755  mov     [rsp+228h+var_138], rax
0x14028375d  mov     rcx, [rax+18h]
0x140283761  mov     [rsp+228h+var_100], rcx
0x140283769  test    rcx, rcx
0x14028376c  jz      short loc_1402837B8
0x14028376e  mov     r13, [rax+20h]
0x140283772  mov     rsi, [rcx+0C0h]
0x140283779  mov     [rsp+228h+var_160], rsi
0x140283781  mov     eax, [rsi+4]
0x140283784  test    r10b, al
0x140283787  jnz     short loc_1402837A5
0x140283789  test    r13, r13
0x14028378c  jz      loc_140284E1F
0x140283792  cmp     byte ptr [r13+58h], 4
0x140283797  jnz     loc_140284E1F
0x14028379d  test    al, 2
0x14028379f  jz      loc_140284E1F
0x1402837a5  test    r13, r13
0x1402837a8  jz      short loc_1402837E1
0x1402837aa  mov     r15, [rcx+0B8h]
0x1402837b1  movzx   eax, byte ptr [r13+58h]
0x1402837b6  jmp     short loc_1402837CC
0x1402837b8  mov     rsi, r12
0x1402837bb  mov     [rsp+228h+var_160], r12
0x1402837c3  mov     r13, r12
0x1402837c6  mov     r15, r12
0x1402837c9  mov     eax, r10d
0x1402837cc  mov     [rsp+228h+var_D8], r15
0x1402837d4  mov     [rsp+228h+var_108], r15
0x1402837dc  cmp     eax, 2
0x1402837df  jz      short loc_14028383A
0x1402837e1  mov     al, cs:NtfsStatusDebugFlags
0x1402837e7  mov     ebx, 0C000000Dh
0x1402837ec  test    al, al
0x1402837ee  jz      short loc_140283800
0x1402837f0  mov     r8d, 124355h
0x1402837f6  mov     edx, ebx
0x1402837f8  mov     rcx, r14
0x1402837fb  call    NtfsStatusTraceAndDebugInternal
0x140283800  test    rdi, rdi
0x140283803  setnz   r9b
0x140283807  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x14028380c  mov     r8d, ebx
0x14028380f  mov     rdx, rdi
0x140283812  mov     rcx, r14
0x140283815  call    NtfsExtendedCompleteRequestInternal
0x14028381a  mov     cl, cs:NtfsStatusDebugFlags
0x140283820  test    cl, cl
0x140283822  jz      short loc_140283833
0x140283824  mov     r8d, 124356h
0x14028382a  mov     edx, ebx
0x14028382c  xor     ecx, ecx
0x14028382e  call    NtfsStatusTraceAndDebugInternal
0x140283833  mov     eax, ebx
0x140283835  jmp     loc_140284DF1
0x14028383a  bt      word ptr [rcx+1CCh], 0Eh
0x140283843  jb      short loc_140283890
0x140283845  mov     al, cs:NtfsStatusDebugFlags
0x14028384b  mov     ebx, 0C00004A7h
0x140283850  test    al, al
0x140283852  jz      short loc_140283864
0x140283854  mov     r8d, 124360h
0x14028385a  mov     edx, ebx
0x14028385c  mov     rcx, r14
0x14028385f  call    NtfsStatusTraceAndDebugInternal
0x140283864  test    rdi, rdi
0x140283867  setnz   r9b
0x14028386b  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x140283870  mov     r8d, ebx
0x140283873  mov     rdx, rdi
0x140283876  mov     rcx, r14
0x140283879  call    NtfsExtendedCompleteRequestInternal
0x14028387e  mov     cl, cs:NtfsStatusDebugFlags
0x140283884  test    cl, cl
0x140283886  jz      short loc_140283833
0x140283888  mov     r8d, 124361h
0x14028388e  jmp     short loc_14028382A
0x140283890  movzx   r9d, word ptr [r13+68h]
0x140283895  test    r9b, 9
0x140283899  jnz     loc_14028399A
0x14028389f  mov     eax, [r14+10h]
0x1402838a3  bt      rax, 14h
0x1402838a8  jb      loc_140283948
0x1402838ae  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1402838b5  test    al, 20h
0x1402838b7  jz      loc_140283948
0x1402838bd  mov     rdx, [rsi+0F8h]
0x1402838c4  movzx   r8d, word ptr [rdx+6]
0x1402838c9  cmp     r8w, 40h ; '@'
0x1402838ce  ja      short loc_1402838D5
0x1402838d0  test    r10b, r8b
0x1402838d3  jz      short loc_1402838D8
0x1402838d5  mov     r8d, r12d
0x1402838d8  movzx   ecx, word ptr [r13+10h]
0x1402838dd  shr     ecx, 1
0x1402838df  add     rdx, 20h ; ' '
0x1402838e3  movzx   r10d, r8w
0x1402838e7  shr     r10d, 1
0x1402838ea  movzx   r11d, word ptr [rsi+1EC0h]
0x1402838f2  shr     r11d, 1
0x1402838f5  mov     r8, gs:188h
0x1402838fe  mov     [rsp+228h+var_1C8], r9d
0x140283903  mov     rax, [r13+18h]
0x140283907  mov     [rsp+228h+var_1D0], rax
0x14028390c  mov     [rsp+228h+var_1D8], ecx
0x140283910  mov     rax, [r15+8]
0x140283914  mov     [rsp+228h+var_1E0], rax
0x140283919  mov     [rsp+228h+var_1E8], r15
0x14028391e  mov     [rsp+228h+var_1F0], rdx
0x140283923  mov     [rsp+228h+var_1F8], r10d
0x140283928  mov     rax, [rsi+1EC8h]
0x14028392f  mov     [rsp+228h+IoStatusBlock], rax
0x140283934  mov     dword ptr [rsp+228h+StartingOffset], r11d
0x140283939  mov     r9, rsi
0x14028393c  lea     rdx, fsctrl_c17258
0x140283943  call    McTemplateU0ppwwpiwd_EtwWriteTransfer
0x140283948  mov     al, cs:NtfsStatusDebugFlags
0x14028394e  mov     ebx, 0C0000022h
0x140283953  test    al, al
0x140283955  jz      short loc_140283967
0x140283957  mov     r8d, 124379h
0x14028395d  mov     edx, ebx
0x14028395f  mov     rcx, r14
0x140283962  call    NtfsStatusTraceAndDebugInternal
0x140283967  test    rdi, rdi
0x14028396a  setnz   r9b
0x14028396e  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x140283973  mov     r8d, ebx
0x140283976  mov     rdx, rdi
0x140283979  mov     rcx, r14
0x14028397c  call    NtfsExtendedCompleteRequestInternal
0x140283981  mov     cl, cs:NtfsStatusDebugFlags
0x140283987  test    cl, cl
0x140283989  jz      loc_140283833
0x14028398f  mov     r8d, 12437Ah
0x140283995  jmp     loc_14028382A
0x14028399a  test    dword ptr [rsi+18h], 40000h
0x1402839a1  jz      short loc_1402839F5
0x1402839a3  mov     al, cs:NtfsStatusDebugFlags
0x1402839a9  mov     ebx, 0C000049Ah
0x1402839ae  test    al, al
0x1402839b0  jz      short loc_1402839C2
0x1402839b2  mov     r8d, 124383h
0x1402839b8  mov     edx, ebx
0x1402839ba  mov     rcx, r14
0x1402839bd  call    NtfsStatusTraceAndDebugInternal
0x1402839c2  test    rdi, rdi
0x1402839c5  setnz   r9b
0x1402839c9  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x1402839ce  mov     r8d, ebx
0x1402839d1  mov     rdx, rdi
0x1402839d4  mov     rcx, r14
0x1402839d7  call    NtfsExtendedCompleteRequestInternal
0x1402839dc  mov     cl, cs:NtfsStatusDebugFlags
0x1402839e2  test    cl, cl
0x1402839e4  jz      loc_140283833
0x1402839ea  mov     r8d, 124384h
0x1402839f0  jmp     loc_14028382A
0x1402839f5  test    dword ptr [rcx+200h], 1000000h
0x1402839ff  jz      short loc_140283A53
0x140283a01  mov     al, cs:NtfsStatusDebugFlags
0x140283a07  mov     ebx, 0C0000008h
0x140283a0c  test    al, al
0x140283a0e  jz      short loc_140283A20
0x140283a10  mov     r8d, 12438Ch
0x140283a16  mov     edx, ebx
0x140283a18  mov     rcx, r14
0x140283a1b  call    NtfsStatusTraceAndDebugInternal
0x140283a20  test    rdi, rdi
0x140283a23  setnz   r9b
0x140283a27  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x140283a2c  mov     r8d, ebx
0x140283a2f  mov     rdx, rdi
0x140283a32  mov     rcx, r14
0x140283a35  call    NtfsExtendedCompleteRequestInternal
0x140283a3a  mov     cl, cs:NtfsStatusDebugFlags
0x140283a40  test    cl, cl
0x140283a42  jz      loc_140283833
0x140283a48  mov     r8d, 12438Dh
0x140283a4e  jmp     loc_14028382A
0x140283a53  mov     rax, [rbx+20h]
0x140283a57  mov     [rsp+228h+Address], rax
0x140283a5f  mov     esi, [rbx+10h]
0x140283a62  mov     dword ptr [rsp+228h+Length], esi
0x140283a69  mov     edx, 10h
0x140283a6e  mov     rcx, rdi
0x140283a71  call    NtfsMapUserBuffer
0x140283a76  mov     r15, rax
0x140283a79  cmp     [rdi+8], r12
0x140283a7d  jnz     short loc_140283A83
0x140283a7f  mov     r12b, [rdi+40h]
0x140283a83  xor     ecx, ecx
0x140283a85  cmp     esi, 10h
0x140283a88  jb      loc_140284D9C
0x140283a8e  mov     [rsp+228h+var_130], rcx
0x140283a96  mov     dword ptr [rsp+228h+Size+4], ecx
0x140283a9d  mov     [rsp+228h+var_168], ecx
0x140283aa4  mov     [rsp+228h+Irp], rcx
0x140283aac  mov     [rsp+228h+var_188], ecx
0x140283ab3  mov     [rsp+228h+var_17C], ecx
0x140283aba  mov     esi, ecx
0x140283abc  mov     [rsp+228h+var_1B7], cl
0x140283ac0  mov     [rsp+228h+var_1B5], cl
0x140283ac4  lea     r8d, [rcx+1]; Alignment
0x140283ac8  mov     [rsp+228h+var_1B2], r8b
0x140283acd  mov     [rsp+228h+var_1B8], cl
0x140283ad1  mov     [rsp+228h+var_1B3], cl
0x140283ad5  mov     [rsp+228h+var_1B4], cl
0x140283ad9  mov     eax, [rbx+8]
0x140283adc  mov     dword ptr [rsp+228h+Size], eax
0x140283ae3  cmp     eax, 30h ; '0'
0x140283ae6  jb      loc_140284D9C
0x140283aec  mov     rbx, [rsp+228h+Address]
0x140283af4  cmp     [rdi+40h], cl
0x140283af7  jz      short loc_140283B2B
0x140283af9  mov     edx, dword ptr [rsp+228h+Length]; Length
0x140283b00  mov     rcx, rbx; Address
0x140283b03  call    cs:__imp_ProbeForRead
0x140283b0a  nop     dword ptr [rax+rax+00h]
0x140283b0f  mov     edx, dword ptr [rsp+228h+Size]; Length
0x140283b16  mov     r8d, 1; Alignment
0x140283b1c  mov     rcx, r15; Address
0x140283b1f  call    cs:__imp_ProbeForWrite
0x140283b26  nop     dword ptr [rax+rax+00h]
0x140283b2b  test    r12b, r12b
0x140283b2e  jz      short loc_140283B3D
0x140283b30  mov     rcx, rbx
0x140283b33  call    RtlReadULong64FromUser
0x140283b38  mov     rdi, rax
0x140283b3b  jmp     short loc_140283B40
0x140283b3d  mov     rdi, [rbx]
0x140283b40  mov     [rsp+228h+var_E8], rdi
0x140283b48  test    r12b, r12b
0x140283b4b  jz      short loc_140283B5A
0x140283b4d  lea     rcx, [rbx+8]
0x140283b51  call    RtlReadULongFromUser
0x140283b56  mov     ebx, eax
0x140283b58  jmp     short loc_140283B5D
0x140283b5a  mov     ebx, [rbx+8]
0x140283b5d  mov     [rsp+228h+var_150], ebx
0x140283b64  mov     r8d, dword ptr [rsp+228h+Size]; Size
0x140283b6c  xor     edx, edx; Val
0x140283b6e  mov     rcx, r15; void *
0x140283b71  test    r12b, r12b
0x140283b74  jz      short loc_140283B7D
0x140283b76  call    RtlSetUserMemory
0x140283b7b  jmp     short loc_140283B83
0x140283b7d  call    RtlSetVolatileMemory
0x140283b82  nop
0x140283b83  mov     rcx, [rsp+228h+var_108]
0x140283b8b  mov     rcx, [rcx+148h]
0x140283b92  test    rcx, rcx
0x140283b95  jz      short loc_140283C01
0x140283b97  mov     dl, 1; Wait
0x140283b99  mov     rcx, [rcx+88h]; Resource
0x140283ba0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140283ba7  nop     dword ptr [rax+rax+00h]
0x140283bac  mov     edx, 1
0x140283bb1  mov     [rsp+228h+var_1B3], dl
0x140283bb5  mov     rax, [rsp+228h+var_108]
0x140283bbd  mov     rax, [rax+148h]
0x140283bc4  mov     ecx, [rax+4]
0x140283bc7  test    dl, cl
0x140283bc9  jnz     short loc_140283BDA
0x140283bcb  mov     rdx, r13
0x140283bce  mov     rcx, r14
0x140283bd1  call    TxfIsCurrentHandleInTransaction
0x140283bd6  test    al, al
0x140283bd8  jz      short loc_140283C01
0x140283bda  mov     al, cs:NtfsStatusDebugFlags
  ... truncated ...
```
